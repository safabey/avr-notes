<h1>Data transfers</h1>
---

>We have __32__ _General purpose register_ (**r0** - **r31**)

| Mnemonic    | Description |
| -------- | :----------: |
| `ldi`   | *load immediate*    |
| `mov` | *copy register*     |
| `movw`    | *copy register pair*    |


## ::`ldi`

``ldi`` is part of a special set of immediate instructions. Immediate instructions operate on a register and require a constant be supplied as an operand. Immediate instructions are very useful as they allow you to operate with a number you supply in the code itself.

```asm
ldi   r16, 85   ; load 85 into register 16 (decimal)
ldi   r16, $55   ; load 85 into register 16 (also hex)
ldi   r16, 0x55   ; load 85 into register 16 (hex)
ldi   r16, 0125   ; load 85 into register 16 (octal)
ldi   r16, 0b01010101   ; load 85 into register 16 (binary)
```

| ⚠️ REMINDER          |
|:--------------------------:|
| **Immediate instructions only work with registers 16 through 31. Trying to use them with registers 0 through 15 will result in an error.**      |

## ::`mov`

The contents of one register can be copied to another register using the mov instruction. Since ldi only works on registers 16 through 31, the mov instruction is a useful way to load a constant into one of the lower 16 registers.

```asm
ldi   r16, 0x55   ; load 0x55 to r16
mov   r0, r16   ; copy content of r16 to r0
```

| ⚠️ REMINDER          |
|:--------------------------:|
| **It only copies the contents to first arg, but second arg remain unchanged.**      |

## ::`movw`

This allows us to operate on 16-Bit values. Allows to copy the contents of one register pair into another pair.

```asm
ldi   r16, 0x34   ; load lower byte of 0x5734 into r16
ldi   r17, 0x57   ; load upper byte of 0x5734 into r17

movw    r1:r0, r17:r16   ; copy contents of r17 to r1; r16 to r0 
```

Instead of typing all pair, just write lower byte register, it knows what have to do. :D

```asm
movw    r0, r16   ; copy contents of r17 to r1; r16 to r0
```

| ⚠️ REMINDER          |
|:--------------------------:|
| **Lower Byte Register should be EVEN! ( 0,2, ...)**      |

| ⚠️ REMINDER          |
|:--------------------------:|
| **Source registers will be remain unchanged!!!**      |

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
