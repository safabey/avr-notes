<h1>Bit Shifts</h1>
---

| Mnemonic 	|         Description        	| Cycles 	|
|:--------:	|:--------------------------:	|:------:	|
|    ``lsl``   	|     logical shift left     	|    1   	|
|    ``lsr``   	|     logical shift Right    	|    1   	|
|    ``rol``   	|  rotate left through carry 	|    1   	|
|    ``ror``   	| rotate right through carry 	|    1   	|
|    ``asr``   	|   arithmetic shift right   	|    1   	|

## ::`lsl`

Performs logical bit shift to **LEFT** with a ***zero***.

```asm
ldi   r16, 0b00001111
lsl   r16   ; r16 :> 0b00011110
<---
```

## ::`lsr`

Performs logical bit shift to **RIGHT** with a ***zero***.

```asm
ldi   r16, 0b00001111
lsr   r16   ; r16 :> 0b0000111
-->
```

## ::`rol`

Similar with `lsl`. Adds ***zero*** or ***one*** according to the carry bit _(status register)_.

```asm
ldi   r16, 0b10101010
ldi   r17, 0b10101010

lsl   r16   ; r16 :> 0b01010100
rol   r17   ; r17 :> 0b01010101 adds last bit shift to first bit
```

## ::`ror`

Similar with `lsr`. Adds ***zero*** or ***one*** according to the carry bit _(status register)_.

```asm
ldi   r16, 0b10101010
ldi   r17, 0b10101010

lsl   r16   ; r16 :> 0b01010101
ror   r17   ; r17 :> 0b01010101 adds previous first bit shift to last bit
```

## ::`asr`

Without changing sign of the value, this allows us to divide the value with 2.
This keeps 7<sup>th</sup> Bit unchanged. And 6<sup>th</sup> Bit will be carry bit.

```asm
ldi   r16, 0b10000001   ; -127
asr   r16   ; r16 :> 0b11000000 = -64
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
