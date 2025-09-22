<h1>All Instructions</h1>
___

## Arithmatic Instructions

| Mnemonic 	|                       Description                       	| Cycles 	| Flags |
|:--------:	|:-------------------------------------------------------:	|:------:	| :---:|
|   `add`  	|                   _add without carry_                   	|    1   	|Z,C,N,V,H|
|   `adc`  	|                     _add with carry_                    	|    1   	|Z,C,N,V,H|
|  `adiw`  	|                 _add immediate to word_                 	|    2   	|Z,C,N,V,S|
|   `sub`  	|                 _subtract without carry_                	|    1   	|Z,C,N,V,H|
|  `subi`  	|                   _subtract immediate_                  	|    1   	|Z,C,N,V,H|
|   `sbc`  	|                  _subtract with carry_                  	|    1   	|Z,C,N,V,H|
|  `sbci`  	|             _subtract immediate with carry_             	|    1   	|Z,C,N,V,H|
|  `sbiw`  	|              _subtract immediate from word_             	|    2   	|Z,C,N,V,S|
|   `inc`  	|                       _increment_                       	|    1   	|Z,N,V|
|   `dec`  	|                       _decrement_                       	|    1   	|Z,N,V|
|   `mul`  	|             *multiply unsigned <sup>*</sup>*            	|    2   	|Z,C|
|  `muls`  	|              *multiply signed <sup>*</sup>*             	|    2   	|Z,C|
|  `mulsu` 	|       *multiply signed with unsigned <sup>*</sup>*      	|    2   	|Z,C|
|  `fmul`  	|       *fractional multiply unsigned <sup>*</sup>*       	|    2   	|Z,C|
|  `fmuls` 	|        *fractional multiply signed <sup>*</sup>*        	|    2   	|Z,C|
| `fmulsu` 	| *fractional multiply signed with unsigned <sup>*</sup>* 	|    2   	|Z,C|

## Logic Instructions

| Mnemonic | Description | Cycles | Flags |
| :--------: | :----------: | :---: | :---: |
| `and`   | *logical AND*    |1|Z,N,V|
| `andi` | *logical AND with immediate (with constant)*     |1|Z,N,V|
| `or`    | *logical OR*    |1|Z,N,V|
| `ori`   | *logical OR with immediate*    |1|Z,N,V|
| `eor` | *exclusive OR (ya da)*     |1|Z,N,V|
| `com`    | *one's complement*    |1|Z,C,N,V|
| `neg`   | *two's complement*    |1|Z,C,N,V,H|

## Bit Instructions

| Mnemonic 	|        Description       	| Cycles 	| Flags 	|
|:--------:	|:------------------------:	|:------:	|:------:	|
|   ``sbr``   	|  *set bit(s) in register*  	|    1   	|    Z,N,V   	|
|   ``cbr``   	| *clear bit(s) in register* 	|    1   	|    Z,N,V   	|
|   ``ser``   	|       *set register*       	|    1   	|    -   	|
|   ``clr``   	|     *clear register*      	|    1   	|    Z,N,V   	|
|   ``swap``   	|       *swap nibbles*       	|    1   	|    -   	|
|   ``lsl``   	|     *logical shift left*     	|    1   	|  Z,C,N,V   	|
|   ``lsr``   	|     *logical shift Right*    	|    1   	|  Z,C,N,V   	|
|   ``rol``   	|  *rotate left through carry* 	|    1   	|  Z,C,N,V   	|
|   ``ror``   	| *rotate right through carry* 	|    1   	|  Z,C,N,V   	|
|   ``asr``   	|   *arithmetic shift right*   	|    1   	|  Z,C,N,V   	|
|   ``tst``   	|   *test for zero or minus*   	|    1   	|  Z,N,V   	|
|   ``sbi``   	|   *set bit in I/O register*   	|    2   	|  -   	|
|   ``cbi``   	|   *clear bit in I/O register*   	|    2   	|  -   	|
|   ``bset``   	|   *flag set*  	|    1   	|  SREG   	|
|   ``bclr``   	|   *flag clear*  	|    1   	|  SREG   	|
|   ``bst``   	|   *bit store from register to T*  	|    1   	|  T   	|
|   ``bld``   	|   *bit load from T to register*  	|    1   	|  -   	|
|   ``sec``   	|   *set carry*  	|    1   	|  C   	|
|   ``clc``   	|   *clear carry*  	|    1   	|  C   	|
|   ``sen``   	|   *set negative flag*  	|    1   	|  N   	|
|   ``cln``   	|   *clear negative flag*  	|    1   	|  N   	|
|   ``sez``   	|   *set zero flag*  	|    1   	|  Z   	|
|   ``clz``   	|   *clear zero flag*  	|    1   	|  Z   	|
|   ``sei``   	|   *global interrupt enable*  	|    1   	|  I   	|
|   ``cli``   	|   *global interrupt disable*  	|    1   	|  I   	|
|   ``ses``   	|   *set signed test flag*  	|    1   	|  S   	|
|   ``cls``   	|   *clear signed test flag*  	|    1   	|  S   	|
|   ``sev``   	|   *set two's complement overflow*  	|    1   	|  V   	|
|   ``clv``   	|   *clear two's complement overflow*  	|    1   	|  V   	|
|   ``set``   	|   *set T in SREG*  	|    1   	|  T   	|
|   ``clt``   	|   *clear T in SREG*  	|    1   	|  T   	|
|   ``seh``   	|   *set half carry flag in SREG*  	|    1   	|  H   	|
|   ``clh``   	|   *clear half carry flag in SREG*  	|    1   	|  H   	|

## Branch Instructions

| Mnemonic 	|        Description       	| Cycles 	| Flags 	|
|:--------:	|:------------------------:	|:------:	|:------:	|
|   ``rjmp``   	|  *relative jump > **limited to ± 2K words from current pos***  	|    2   	|    -   	|
|   ``ijmp``   	|  *indirect jump to Z*  	|    2   	|    -   	|
|   ``jmp``   	|  *direct jump > **limitless jump***  	|    2   	|    -   	|
|   ``rcall``   	|  *relative subroutine call*  	|    3   	|    -   	|
|   ``icall``   	|  *indirect call to Z*  	|    3   	|    -   	|
|   ``call``   	|  *direct subroutine call*  	|    4   	|    -   	|
|   ``ret``   	|  *subroutine return*  	|    4   	|    -   	|
|   ``reti``   	|  *interrupt return*  	|    4   	|    I   	|
|   ``cpse``   	|  *compare, skip if equal*  	|   1/2/3   	|    -   	|
|   ``cp``   	|  *compare*  	|    4   	|    Z,N,V,C,H   	|
|   ``cpc``   	|  *compare with carry*  	|    1   	|   Z,N,V,C,H   	|
|   ``cpi``   	|  *compare register with immediate*  	|    1   	|   Z,N,V,C,H   	|
|   ``sbrc``   	|  *skip if bit in register cleared > **if (Rr (b) = 0) PC***  	|    1/2/3   	| - 	|
|   ``sbrs``   	|  *skip if bit in register is set > **if (Rr (b) = 1) PC***  	|    1/2/3   	| - 	|
|   ``sbic``   	|  *skip if bit in I/O register cleared > **if (P (b) = 0) PC***  	|    1/2/3   	| - 	|
|   ``sbis``   	|  *skip if bit in I/O register is set > **if (P (b) = 1) PC***  	|    1/2/3   	| - 	|
|   ``brbc``   	|  *branch if status flag cleared > **if (SREG(s) = 0) then PC***  	|    1/2   	| - 	|
|   ``brbs``   	|  *branch if status flag is set > **if (SREG(s) = 1) then PC***  	|    1/2   	| - 	|
|   ``brne``   	|  *branch if not equal > **if (Z = 0) then PC***  	|    1/2   	| - 	|
|   ``breq``   	|  *branch if equal > **if (Z = 1) then PC***  	|    1/2   	| - 	|
|   ``brcc``   	|  *branch if carry cleared > **if (C = 0) then PC***  	|    1/2   	| - 	|
|   ``brcs``   	|  *branch if carry set > **if (C = 1) then PC***  	|    1/2   	| - 	|
|   ``brsh``   	|  *branch if same or higher > **if (C = 0) then PC***  	|    1/2   	| - 	|
|   ``brlo``   	|  *branch if lower > **if (C = 1) then PC***  	|    1/2   	| - 	|
|   ``brmi``   	|  *branch if minus > **if (N = 1) then PC***  	|    1/2   	| - 	|
|   ``brpl``   	|  *branch if plus > **if (N = 0) then PC***  	|    1/2   	| - 	|
|   ``brge``   	|  *branch if greater or equal, signed > **if (N ⊕ V = 0) then PC***  	|    1/2   	| - 	|
|   ``brlt``   	|  *branch if less than zero, signed > **if (N ⊕ V = 1) then PC***  	|    1/2   	| - 	|
|   ``brhs``   	|  *branch if half carry flag set > **if (H = 1) then PC***  	|    1/2   	| - 	|
|   ``brhc``   	|  *branch if half carry flag cleared > **if (H = 0) then PC***  	|    1/2   	| - 	|
|   ``brts``   	|  *branch if T flag set > **if (T = 1) then PC***  	|    1/2   	| - 	|
|   ``brtc``   	|  *branch if T flag cleared > **if (T = 0) then PC***  	|    1/2   	| - 	|
|   ``brvs``   	|  *branch if overflow flag is set > **if (V = 1) then PC***  	|    1/2   	| - 	|
|   ``brvc``   	|  *branch if overflow flag is cleared > **if (V = 0) then PC***  	|    1/2   	| - 	|
|   ``brie``   	|  *branch if interrupt enabled > **if (I = 1) then PC***  	|    1/2   	| - 	|
|   ``brid``   	|  *branch if interrupt disabled > **if (I = 0) then PC***  	|    1/2   	| - 	|

``word`` means 2 Bytes.
So `rjmp` limited with ± 4096 Byte.


## Data Transfer Instructions

| Mnemonic 	|        Description       	| Cycles 	| Flags 	|
|:--------:	|:------------------------:	|:------:	|:------:	|
| ``mov``   |       *move between registers* 	    |    1   	|    -   	|
| ``movw``   |       *copy register word*	    |    1   	|    -   	|
| ``ldi``   |       *load immediate*	    |    1   	|    -   	|
| ``ld``   |       *load indirect*	    |    2   	|    -   	|
| ``ldd``   |       *load indirect with displacement*	    |    2   	|    -   	|
| ``lds``   |       *load direct from SRAM*	    |    2   	|    -   	|
| ``st``   |      *store indirect*	    |    2   	|    -   	|
| ``std``   |      *store indirect	with displacement*    |    2   	|    -   	|
| ``sts``   |      *store diretc from SRAM*	    |    2   	|    -   	|
| ``lpm``   |     *load program memory*	    |    3   	|    -   	|
| ``spm``   |      *store program memory*	    |    -   	|    -   	|
| ``in``   |      *in port*	    |    1   	|    -   	|
| ``out``   |      *out port*	    |    1   	|    -   	|
| ``push``   |      *push register on stack*	    |    2   	|    -   	|
| ``pop``   |    *pop register on stack*		    |    2   	|    -   	|


## MCU Control Instructions

| Mnemonic 	|        Description       	| Cycles 	| Flags 	|
|:--------:	|:------------------------:	|:------:	|:------:	|
|   ``nop``   	|  *no operation*  	|    1   	|    -   	|
|   ``sleep``   	|  *sleep*  	|    1   	|    -   	|
|   ``wdr``   	|  *watchdog reset*  	|    1   	|    -   	|
|   ``break``   	|  *break*  	|    N/A   	|    -   	|

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