<h1>Bit Manipulations</h1>
---


| Mnemonic 	|        Description       	| Cycles 	|
|:--------:	|:------------------------:	|:------:	|
|    sbr   	|  set bit(s) in register  	|    1   	|
|    cbr   	| clear bit(s) in register 	|    1   	|
|    ser   	|       set register       	|    1   	|
|    clr   	|      clear register      	|    1   	|
|   swap   	|       swap nibbles       	|    1   	|

## ::`sbr`

Second argument selects bits that will be one.

```nasm
ldi   r16, 0b01000000
sbr   r16, 0b00001111
; r16 :>   0b01001111
```

It is identical with `ori`. Assembler will generate the exact same machine code.

## ::`cbr`

Second argument selects bits that will be zero.

```asm
ldi   r16, 0b01001111
sbr   r16, 0b00001111
; r16 :>   0b01000000
```

It is almost identical with `andi`. But not the same !!!

| ⚠️ REMINDER          |
|:--------------------------:|
| **Even though they don't have the word immediate in the name, sbr and cbr only work on registers 16 through 31.** |

## ::`ser`

Sets register's all bits on.
Only work with ***r16 : r31***

## ::`clr`

Sets register's all bit off.
Only work with ***r16 : r31***

| ⚠️ REMINDER          |
|:--------------------------:|
| **`ser` and `clr` are not actual instructions implemented in the architecture, but are provided by the assembler as aliases for other instructions.** |

## ::`swap`

Allows us to swap the lower 4 Bits with the upper 4 Bits of a register.

```asm
ldi   r16, 0x0F
swap  r16
; r16 :> 0xF0
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
