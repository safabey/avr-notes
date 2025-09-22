<h1>Logical Instructions</h1>
---

| Mnemonic | Description |
| -------- | :----------: |
| `and`   | *logical AND*    |
| `andi` | *logical AND with immediate (with constant)*     |
| `or`    | *logical OR*    |
| `ori`   | *logical OR with immediate*    |
| `eor` | *exclusive OR (ya da)*     |
| `com`    | *one's complement*    |
| `neg`   | *two's complement*    |

## ::`and` || `andi` & `or` || `ori` & `eor`


<style type="text/css">.tg-sort-header::-moz-selection{background:0 0}.tg-sort-header::selection{background:0 0}.tg-sort-header{cursor:pointer}.tg-sort-header:after{content:'';float:right;margin-top:7px;border-width:0 5px 5px;border-style:solid;border-color:#404040 transparent;visibility:hidden}.tg-sort-header:hover:after{visibility:visible}.tg-sort-asc:after,.tg-sort-asc:hover:after,.tg-sort-desc:after{visibility:visible;opacity:.4}.tg-sort-desc:after{border-bottom:none;border-width:5px 5px 0}@media screen and (max-width: 767px) {.tg {width: auto !important;}.tg col {width: auto !important;}.tg-wrap {overflow-x: auto;-webkit-overflow-scrolling: touch;margin: auto 0px;}}</style>
<div class="tg-wrap"><table id="tg-RVL3Z" style="border-collapse:collapse;border-color:#ccc;border-spacing:0;margin:0px auto;table-layout: fixed; width: 844px" class="tg"><colgroup><col style="width: 25px"><col style="width: 42px"><col style="width: 142px"><col style="width: 49px"><col style="width: 54px"><col style="width: 210px"><col style="width: 60px"><col style="width: 47px"><col style="width: 215px"></colgroup>
<thead>
<tr><th style="background-color:#656565;border-color:inherit;border-style:solid;border-width:1px;color:#ffffff;font-family:inherit;font-size:14px;font-weight:normal;overflow:hidden;padding:10px 5px;position:-webkit-sticky;position:sticky;text-align:center;top:-1px;vertical-align:top;will-change:transform;word-break:normal" colspan="3">AND</th><th style="background-color:#656565;border-color:inherit;border-style:solid;border-width:1px;color:#ffffff;font-family:inherit;font-size:14px;font-weight:normal;overflow:hidden;padding:10px 5px;position:-webkit-sticky;position:sticky;text-align:center;top:-1px;vertical-align:top;will-change:transform;word-break:normal" colspan="3">OR</th>
<th style="background-color:#656565;border-color:inherit;border-style:solid;border-width:1px;color:#ffffff;font-family:inherit;font-size:14px;font-weight:normal;overflow:hidden;padding:10px 5px;position:-webkit-sticky;position:sticky;text-align:center;top:-1px;vertical-align:top;will-change:transform;word-break:normal" colspan="3">EOR</th></tr>
</thead>
<tbody>
<tr><td style="background-color:#9b9b9b;border-color:inherit;border-style:solid;border-width:1px;color:#ffffff;font-family:inherit;font-size:14px;overflow:hidden;padding:10px 5px;text-align:center;vertical-align:top;word-break:normal">p</td><td style="background-color:#9b9b9b;border-color:inherit;border-style:solid;border-width:1px;color:#ffffff;font-family:inherit;font-size:14px;overflow:hidden;padding:10px 5px;text-align:center;vertical-align:top;word-break:normal">q</td><td style="background-color:#9b9b9b;border-color:inherit;border-style:solid;border-width:1px;color:#ffffff;font-family:inherit;font-size:14px;overflow:hidden;padding:10px 5px;text-align:center;vertical-align:top;word-break:normal">`or p, q`</td><td style="background-color:#9b9b9b;border-color:inherit;border-style:solid;border-width:1px;color:#ffffff;font-family:inherit;font-size:14px;overflow:hidden;padding:10px 5px;text-align:center;vertical-align:top;word-break:normal">p</td>
<td style="background-color:#9b9b9b;border-color:inherit;border-style:solid;border-width:1px;color:#ffffff;font-family:inherit;font-size:14px;overflow:hidden;padding:10px 5px;text-align:center;vertical-align:top;word-break:normal">q</td><td style="background-color:#9b9b9b;border-color:inherit;border-style:solid;border-width:1px;color:#ffffff;font-family:inherit;font-size:14px;overflow:hidden;padding:10px 5px;text-align:center;vertical-align:top;word-break:normal">`or p, q`</td><td style="background-color:#9b9b9b;border-color:inherit;border-style:solid;border-width:1px;color:#ffffff;font-family:inherit;font-size:14px;overflow:hidden;padding:10px 5px;text-align:center;vertical-align:top;word-break:normal">p</td><td style="background-color:#9b9b9b;border-color:inherit;border-style:solid;border-width:1px;color:#ffffff;font-family:inherit;font-size:14px;overflow:hidden;padding:10px 5px;text-align:center;vertical-align:top;word-break:normal">q</td>
<td style="background-color:#9b9b9b;border-color:inherit;border-style:solid;border-width:1px;color:#ffffff;font-family:inherit;font-size:14px;overflow:hidden;padding:10px 5px;text-align:center;vertical-align:top;word-break:normal">`eor p, q`</td></tr>
<tr><td style="background-color:#fff;border-color:inherit;border-style:solid;border-width:1px;color:#333;font-family:inherit;font-size:14px;overflow:hidden;padding:10px 5px;text-align:center;vertical-align:top;word-break:normal">1</td><td style="background-color:#fff;border-color:inherit;border-style:solid;border-width:1px;color:#333;font-family:inherit;font-size:14px;overflow:hidden;padding:10px 5px;text-align:center;vertical-align:top;word-break:normal">1</td><td style="background-color:#fdf6e3;border-color:inherit;border-style:solid;border-width:1px;color:#333;font-family:inherit;font-size:14px;overflow:hidden;padding:10px 5px;text-align:center;vertical-align:top;word-break:normal">1</td><td style="background-color:#fff;border-color:inherit;border-style:solid;border-width:1px;color:#333;font-family:inherit;font-size:14px;overflow:hidden;padding:10px 5px;text-align:center;vertical-align:top;word-break:normal">1</td>
<td style="background-color:#fff;border-color:inherit;border-style:solid;border-width:1px;color:#333;font-family:inherit;font-size:14px;overflow:hidden;padding:10px 5px;text-align:center;vertical-align:top;word-break:normal">1</td><td style="background-color:#fdf6e3;border-color:inherit;border-style:solid;border-width:1px;color:#333;font-family:inherit;font-size:14px;overflow:hidden;padding:10px 5px;text-align:center;vertical-align:top;word-break:normal">1</td><td style="background-color:#fff;border-color:inherit;border-style:solid;border-width:1px;color:#333;font-family:inherit;font-size:14px;overflow:hidden;padding:10px 5px;text-align:center;vertical-align:top;word-break:normal">1</td><td style="background-color:#fff;border-color:inherit;border-style:solid;border-width:1px;color:#333;font-family:inherit;font-size:14px;overflow:hidden;padding:10px 5px;text-align:center;vertical-align:top;word-break:normal">1</td>
<td style="background-color:#fdf6e3;border-color:inherit;border-style:solid;border-width:1px;color:#333;font-family:inherit;font-size:14px;overflow:hidden;padding:10px 5px;text-align:center;vertical-align:top;word-break:normal">0</td></tr>
<tr><td style="background-color:#f9f9f9;border-color:inherit;border-style:solid;border-width:1px;color:#333;font-family:inherit;font-size:14px;overflow:hidden;padding:10px 5px;text-align:center;vertical-align:top;word-break:normal">1</td><td style="background-color:#f9f9f9;border-color:inherit;border-style:solid;border-width:1px;color:#333;font-family:inherit;font-size:14px;overflow:hidden;padding:10px 5px;text-align:center;vertical-align:top;word-break:normal">0</td><td style="background-color:#fdf6e3;border-color:inherit;border-style:solid;border-width:1px;color:#333;font-family:inherit;font-size:14px;overflow:hidden;padding:10px 5px;text-align:center;vertical-align:top;word-break:normal">0</td><td style="background-color:#f9f9f9;border-color:inherit;border-style:solid;border-width:1px;color:#333;font-family:inherit;font-size:14px;overflow:hidden;padding:10px 5px;text-align:center;vertical-align:top;word-break:normal">1</td>
<td style="background-color:#f9f9f9;border-color:inherit;border-style:solid;border-width:1px;color:#333;font-family:inherit;font-size:14px;overflow:hidden;padding:10px 5px;text-align:center;vertical-align:top;word-break:normal">0</td><td style="background-color:#fdf6e3;border-color:inherit;border-style:solid;border-width:1px;color:#333;font-family:inherit;font-size:14px;overflow:hidden;padding:10px 5px;text-align:center;vertical-align:top;word-break:normal">1</td><td style="background-color:#f9f9f9;border-color:inherit;border-style:solid;border-width:1px;color:#333;font-family:inherit;font-size:14px;overflow:hidden;padding:10px 5px;text-align:center;vertical-align:top;word-break:normal">1</td><td style="background-color:#f9f9f9;border-color:inherit;border-style:solid;border-width:1px;color:#333;font-family:inherit;font-size:14px;overflow:hidden;padding:10px 5px;text-align:center;vertical-align:top;word-break:normal">0</td>
<td style="background-color:#fdf6e3;border-color:inherit;border-style:solid;border-width:1px;color:#333;font-family:inherit;font-size:14px;overflow:hidden;padding:10px 5px;text-align:center;vertical-align:top;word-break:normal">1</td></tr>
<tr><td style="background-color:#fff;border-color:inherit;border-style:solid;border-width:1px;color:#333;font-family:inherit;font-size:14px;overflow:hidden;padding:10px 5px;text-align:center;vertical-align:top;word-break:normal">0</td><td style="background-color:#fff;border-color:inherit;border-style:solid;border-width:1px;color:#333;font-family:inherit;font-size:14px;overflow:hidden;padding:10px 5px;text-align:center;vertical-align:top;word-break:normal">1</td><td style="background-color:#fdf6e3;border-color:inherit;border-style:solid;border-width:1px;color:#333;font-family:inherit;font-size:14px;overflow:hidden;padding:10px 5px;text-align:center;vertical-align:top;word-break:normal">0</td><td style="background-color:#fff;border-color:inherit;border-style:solid;border-width:1px;color:#333;font-family:inherit;font-size:14px;overflow:hidden;padding:10px 5px;text-align:center;vertical-align:top;word-break:normal">0</td>
<td style="background-color:#fff;border-color:inherit;border-style:solid;border-width:1px;color:#333;font-family:inherit;font-size:14px;overflow:hidden;padding:10px 5px;text-align:center;vertical-align:top;word-break:normal">1</td><td style="background-color:#fdf6e3;border-color:inherit;border-style:solid;border-width:1px;color:#333;font-family:inherit;font-size:14px;overflow:hidden;padding:10px 5px;text-align:center;vertical-align:top;word-break:normal">1</td><td style="background-color:#fff;border-color:inherit;border-style:solid;border-width:1px;color:#333;font-family:inherit;font-size:14px;overflow:hidden;padding:10px 5px;text-align:center;vertical-align:top;word-break:normal">0</td><td style="background-color:#fff;border-color:inherit;border-style:solid;border-width:1px;color:#333;font-family:inherit;font-size:14px;overflow:hidden;padding:10px 5px;text-align:center;vertical-align:top;word-break:normal">1</td>
<td style="background-color:#fdf6e3;border-color:inherit;border-style:solid;border-width:1px;color:#333;font-family:inherit;font-size:14px;overflow:hidden;padding:10px 5px;text-align:center;vertical-align:top;word-break:normal">1</td></tr>
<tr><td style="background-color:#f9f9f9;border-color:inherit;border-style:solid;border-width:1px;color:#333;font-family:inherit;font-size:14px;overflow:hidden;padding:10px 5px;text-align:center;vertical-align:top;word-break:normal">0</td><td style="background-color:#f9f9f9;border-color:inherit;border-style:solid;border-width:1px;color:#333;font-family:inherit;font-size:14px;overflow:hidden;padding:10px 5px;text-align:center;vertical-align:top;word-break:normal">0</td><td style="background-color:#fdf6e3;border-color:inherit;border-style:solid;border-width:1px;color:#333;font-family:inherit;font-size:14px;overflow:hidden;padding:10px 5px;text-align:center;vertical-align:top;word-break:normal">0</td><td style="background-color:#f9f9f9;border-color:inherit;border-style:solid;border-width:1px;color:#333;font-family:inherit;font-size:14px;overflow:hidden;padding:10px 5px;text-align:center;vertical-align:top;word-break:normal">0</td>
<td style="background-color:#f9f9f9;border-color:inherit;border-style:solid;border-width:1px;color:#333;font-family:inherit;font-size:14px;overflow:hidden;padding:10px 5px;text-align:center;vertical-align:top;word-break:normal">0</td><td style="background-color:#fdf6e3;border-color:inherit;border-style:solid;border-width:1px;color:#333;font-family:inherit;font-size:14px;overflow:hidden;padding:10px 5px;text-align:center;vertical-align:top;word-break:normal">0</td><td style="background-color:#f9f9f9;border-color:inherit;border-style:solid;border-width:1px;color:#333;font-family:inherit;font-size:14px;overflow:hidden;padding:10px 5px;text-align:center;vertical-align:top;word-break:normal">0</td><td style="background-color:#f9f9f9;border-color:inherit;border-style:solid;border-width:1px;color:#333;font-family:inherit;font-size:14px;overflow:hidden;padding:10px 5px;text-align:center;vertical-align:top;word-break:normal">0</td>
<td style="background-color:#fdf6e3;border-color:inherit;border-style:solid;border-width:1px;color:#333;font-family:inherit;font-size:14px;overflow:hidden;padding:10px 5px;text-align:center;vertical-align:top;word-break:normal">0</td></tr>
</tbody></table></div>
<script charset="utf-8">var TGSort=window.TGSort||function(n){"use strict";function r(n){return n?n.length:0}function t(n,t,e,o=0){for(e=r(n);o<e;++o)t(n[o],o)}function e(n){return n.split("").reverse().join("")}function o(n){var e=n[0];return t(n,function(n){for(;!n.startsWith(e);)e=e.substring(0,r(e)-1)}),r(e)}function u(n,r,e=[]){return t(n,function(n){r(n)&&e.push(n)}),e}var a=parseFloat;function i(n,r){return function(t){var e="";return t.replace(n,function(n,t,o){return e=t.replace(r,"")+"."+(o||"").substring(1)}),a(e)}}var s=i(/^(?:\s*)([+-]?(?:\d+)(?:,\d{3})*)(\.\d*)?$/g,/,/g),c=i(/^(?:\s*)([+-]?(?:\d+)(?:\.\d{3})*)(,\d*)?$/g,/\./g);function f(n){var t=a(n);return!isNaN(t)&&r(""+t)+1>=r(n)?t:NaN}function d(n){var e=[],o=n;return t([f,s,c],function(u){var a=[],i=[];t(n,function(n,r){r=u(n),a.push(r),r||i.push(n)}),r(i)<r(o)&&(o=i,e=a)}),r(u(o,function(n){return n==o[0]}))==r(o)?e:[]}function v(n){if("TABLE"==n.nodeName){for(var a=function(r){var e,o,u=[],a=[];return function n(r,e){e(r),t(r.childNodes,function(r){n(r,e)})}(n,function(n){"TR"==(o=n.nodeName)?(e=[],u.push(e),a.push(n)):"TD"!=o&&"TH"!=o||e.push(n)}),[u,a]}(),i=a[0],s=a[1],c=r(i),f=c>1&&r(i[0])<r(i[1])?1:0,v=f+1,p=i[f],h=r(p),l=[],g=[],N=[],m=v;m<c;++m){for(var T=0;T<h;++T){r(g)<h&&g.push([]);var C=i[m][T],L=C.textContent||C.innerText||"";g[T].push(L.trim())}N.push(m-v)}t(p,function(n,t){l[t]=0;var a=n.classList;a.add("tg-sort-header"),n.addEventListener("click",function(){var n=l[t];!function(){for(var n=0;n<h;++n){var r=p[n].classList;r.remove("tg-sort-asc"),r.remove("tg-sort-desc"),l[n]=0}}(),(n=1==n?-1:+!n)&&a.add(n>0?"tg-sort-asc":"tg-sort-desc"),l[t]=n;var i,f=g[t],m=function(r,t){return n*f[r].localeCompare(f[t])||n*(r-t)},T=function(n){var t=d(n);if(!r(t)){var u=o(n),a=o(n.map(e));t=d(n.map(function(n){return n.substring(u,r(n)-a)}))}return t}(f);(r(T)||r(T=r(u(i=f.map(Date.parse),isNaN))?[]:i))&&(m=function(r,t){var e=T[r],o=T[t],u=isNaN(e),a=isNaN(o);return u&&a?0:u?-n:a?n:e>o?n:e<o?-n:n*(r-t)});var C,L=N.slice();L.sort(m);for(var E=v;E<c;++E)(C=s[E].parentNode).removeChild(s[E]);for(E=v;E<c;++E)C.appendChild(s[v+L[E-v]])})})}}n.addEventListener("DOMContentLoaded",function(){for(var t=n.getElementsByClassName("tg"),e=0;e<r(t);++e)try{v(t[e])}catch(n){}})}(document)</script>

<br>

```asm
ldi   r16, 0b01010101   ; load 0x55 to r16
andi  r16, 0b00001111
;resultat r16:0b00000101

ldi   r16, 0b01010101   ; load 0x55 to r16
ori   r16, 0b00001111
;resultat r16:0b01011111

ldi   r16, 0b01010101
ldi   r17, 0b11111111
eor   r16, r17
; r17 :>   0b10101010
```

We can use `and` or `or` for masking purposes!

| ⚠️ REMINDER          |
|:--------------------------:|
| **Again! Immediate modes only work for r16 - r31**      |

We can clear a register with `eor`.

```asm
ldi   r16, 0b11010101
eor   r16, r16
;   r16 :> 0b00000000
```
## Complements and Negatives

### ::`com`

Allows toggle all bits of a register!

```asm
ldi   r16, 0b11110011
com   r16
;   r16 :> 0b00001100
```

### ::`neg`

Negates a register's content

```asm
ldi   r16, 5   ; load 5 into r16
neg   r16   ; negates r16 
;  r16 :> -5 (0xFB)
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
