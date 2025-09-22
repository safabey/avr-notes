<h1>Arithmetic Instructions</h1>
---


| Mnemonic 	|                       Description                       	| Cycles 	|
|:--------:	|:-------------------------------------------------------:	|:------:	|
|   `add`  	|                   _add without carry_                   	|    1   	|
|   `adc`  	|                     _add with carry_                    	|    1   	|
|  `adiw`  	|                 _add immediate to word_                 	|    2   	|
|   `sub`  	|                 _subtract without carry_                	|    1   	|
|  `subi`  	|                   _subtract immediate_                  	|    1   	|
|   `sbc`  	|                  _subtract with carry_                  	|    1   	|
|  `sbci`  	|             _subtract immediate with carry_             	|    1   	|
|  `sbiw`  	|              _subtract immediate from word_             	|    2   	|
|   `inc`  	|                       _increment_                       	|    1   	|
|   `dec`  	|                       _decrement_                       	|    1   	|
|   `mul`  	|             *multiply unsigned <sup>*</sup>*            	|    2   	|
|  `muls`  	|              *multiply signed <sup>*</sup>*             	|    2   	|
|  `mulsu` 	|       *multiply signed with unsigned <sup>*</sup>*      	|    2   	|
|  `fmul`  	|       *fractional multiply unsigned <sup>*</sup>*       	|    2   	|
|  `fmuls` 	|        *fractional multiply signed <sup>*</sup>*        	|    2   	|
| `fmulsu` 	| *fractional multiply signed with unsigned <sup>*</sup>* 	|    2   	|

( <sup>*</sup> ) : means, these are not implemented in ATtiny.

## Addition and Subtraction

### Addition

#### ::`add`
`add` takes two arg. Computes their sum and stores the value int the first arg.

```asm
ldi   r16, 5
ldi   r17, 6
add   r16, r17
; r16 :> 5 + 6 = 11
```

#### ::`adc`

Similary, `adc` - add with _carry_ - takes two registers as input and computes their sum, then adds carry bit if needed. This is very usefull for adding more than 8-Bit values. 

```asm
; 0x1234
ldi   r16, 0x34   ; lower
ldi   r17, 0x12   ; upper

; 0xABCD
ldi   r18, 0xCD   ; lower
ldi   r19, 0xAB   ; upper

add   r16, r18    ; first lower bytes, this may activates carry bit
adc   r17, r19    ; adds upper bytes, then adds carry bit
; r17, r16 :> 0xBE01
```

### Subtraction

#### ::`sub` & `sbc`

Same as `add` & `adc`.

#### ::`sbi`

Subtraction with constant.

```asm
ldi   r16, 0x05
sbi   r16, 0x05
; r16 :> 0x00
```

| ⚠️ REMINDER          |
|:--------------------------:|
| **Unfortunately, there is NO immediate instruction of `add`.**      |

### ::`inc`

Increase the value of register by one.

```asm
clr   r16   ; clears r16 :> 0
inc   r16   ; r16 :> 1
```

### ::`dec`

Decrease the value of register by one.

```asm
clr   r16   ; clears r16 :> 0
inc   r16   ; r16 :> 1
dec   r16   ; r16 :> 0
```

### ::`adiw` & `sbiw`

These instructions allow us to operate on 16-Bit values.
Needs 2 Cycle.
Allows you to add a constant value of the range **_0 - 63_** to the register pair.

**X** ( r26 **:** r27 ) , **Y** ( r28 **:** r29 ) , **Z** ( r30 **:** r31 )
If only one register is specified the compiler will automatically fill in the next ( i.e. **r24 → r25:r24** ).

```asm
;  Load 0x1000 into two register
ldi   r24, 0x00
ldi   r25, 0x10
adiw    r24, 0x0A   ; add 0x0A to r24:r25 (result = 0x100A)

;  Load 0x8080 into two register
ldi   XL, 0x80
ldi   XH, 0x80
adiw    X, 1    ; increment X pointer (result = 0x8081)

;  Load 0x55AA into two register
ldi   YL, 0xAA
ldi   YH, 0x55
sbiw    Y, 0x10   ; subtract 0x10 from Y (result = 0x559A) 
```

| ⚠️ REMINDER          |
|:--------------------------:|
| **`adiw` and `sbiw` can only be used on the registers from _r24_ through _r31_. Also, they will only work on register pairs for which the lower is an even number, i.e. _r25:r24_ are valid operands, but _r26:r25_ are not.** |

### Multiplication

ATtiny family has no hardware multiplication instruction.

#### ::`mul`

`mul` allows us to compute unsigned product of ***any 32 register***. Result needs two register. Result always be stored in ***r1*** for *upper* and ***r0*** for *lower* bytes.

```asm
ldi   r16, 0x18   ; 22
ldi   r17, 0x37   ; 55
mul   r16, r17    ; r1:r0 :> 0x0528 = 1210
```

#### ::`muls`

`muls` allows us to compute signed product of only ***r16*** through ***r31***. Signed arg must be in Two's Complement format.

```asm
ldi   r16, 0xF2   ; -14 in Two's Complement
ldi   r17, 0x37   ; -33 in Two's Complement
mul   r16, r17    ; r1:r0 :> 0x01CE = 462
```

| ❓ QUICK CHEAT          |
|:--------------------------:|
| **To convert a value to Two's Complement format, simply add 256 if it is less than zero.** |
|`-14 + 256 = 242 (0xF2) in Two's Comp.: -14`|

#### ::`mulsu`

`mulsu` allows us to compute product of two arg when one of them is signed and the second one is unsigned. But some limitations, there are. It works only on ***r16*** through ***r23***. 

### Fractional Multiplication

ATmega supports limited multiplication of fractional numbers.
Fractional number between _[0,2)_ can be presented by an 8-Bit number in a _1.7 Format_.

|   **Bit 7**   	|    **Bit 6**   	|    **Bit 5**   	|    **Bit 4**   	|    **Bit 3**   	|    **Bit 2**   	|    **Bit 1**   	|    **Bit 0**   	|
|:-------------:	|:--------------:	|:--------------:	|:--------------:	|:--------------:	|:--------------:	|:--------------:	|:--------------:	|
| 2<sup>0</sup> 	| 2<sup>-1</sup> 	| 2<sup>-2</sup> 	| 2<sup>-3</sup> 	| 2<sup>-4</sup> 	| 2<sup>-5</sup> 	| 2<sup>-6</sup> 	| 2<sup>-7</sup> 	|
|       1       	|       0.5      	|      0.25      	|      0.125     	|     0.0625     	|     0.03125    	|    0.015625    	|    0.0078125   	|

For example:
**0b01001100** would equal _0x1 + 1x0.5 + 0x0.25 + 0x0.125 + 1x0.0625 + 1x0.03125 + 0x0.015625 + 0x0.0078125 = **0.59375**_ using this format.

#### ::`fmul`

`fmul` computes the sum of two 8-bit numbers in the _1.7 format_ and outputs the result in **r1** and **r0** in a _1.15 format_. In 1.15, the first bit of the higher byte represents an integer component and the rest of the bits represent fractional components. fmul will only work with **r16** through **r23**.

```asm
ldi   r16, 0xC0   ; 1.5
ldi   r17, 0xA0   ; 1.25
fmul  r16, r17    ; r1:r0 :> 0xF000 = 1.875
```

#### ::`fmuls`

`fmuls` is signed version of `fmul`. Range is _[-1,1)_.

```asm
ldi   r16, 0xA0   ; -0.75
ldi   r17, 0xF0   ; -0.125
fmuls r16, r17    ; r1:r0 :> 0x0C00 = 0.04375
```

| ❓ QUICK CHEAT          |
|:--------------------------:|
| **To convert a fractional value to Two's Complement format, simply add 2 if it is less than zero.** |
|`-0.75 + 2 = 1.25 (0xA0) in Two's Comp.: -0.75`|

#### ::`fmulsu`

And also we have first signed, second unsigned version.

```asm
ldi   r16, 0xC0   ; -0.5
ldi   r17, 0x60   ; 0.75
fmuls r16, r17    ; r1:r0 :> 0xD000 = -0x375
```

---

<script src="https://giscus.app/client.js"
        data-repo="safabey/avr-notes"
        data-repo-id="R_kgDOP0lO_A"
        data-category="Comments"
        data-category-id="DIC_kwDOP0lO_M4CvwBX"
        data-mapping="pathname"
        data-strict="0"
        data-reactions-enabled="1"
        data-emit-metadata="0"
        data-input-position="bottom"
        data-theme="preferred_color_scheme"
        data-lang="en"
        crossorigin="anonymous"
        async>
</script>
