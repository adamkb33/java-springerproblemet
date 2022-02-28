<div class="description user_content enhanced">Et klassisk problem som er beslektet med dronningproblemet, og som angivelig ble
løst av den tyske matematikeren <a href="http://en.wikipedia.org/wiki/Carl_Friedrich_Gauss" class="external" target="_blank" rel="noreferrer noopener"><span>Gauss</span><span aria-hidden="true" class="ui-icon ui-icon-extlink ui-icon-inline" title="Lenker til en ekstern side."></span><span class="screenreader-only">&nbsp;(Lenker til en ekstern side.)</span></a> da
han var 4 år, er det såkalte <b>springerproblemet</b>.

<p>
En springer (eller hest) er en sjakkbrikke som kan gå to skritt frem
(i vilkårlig retning) og ett til siden. Figuren nedenfor viser de
lovlige posisjonene som en springer kan flyttes til.

</p><p>
<img src="https://it.hiof.no/algdat/oblig/springertrekk.jpg" style="max-width: 259px;">

</p><p>
Springerproblemet består av å finne en måte å bevege en springer rundt på et
sjakkbrett, fra en gitt utgangsposisjon, slik at den er innom <i>alle</i>
ruter på brettet en og bare en gang. Her er en animasjon av en løsning på problemet:
</p><p>
<img src="https://it.hiof.no/algdat/oblig/springertur.gif" width="300" style="max-width: 300px;">

</p><p>
Det skal lages et Java-program som løser springerproblemet for
et
<i>n&nbsp;X&nbsp;n</i> sjakkbrett. Størrelsen på sjakkbrettet, <i>n</i>, og
springerens startposisjon skal oppgis av bruker. Det er tilstrekkelig at
programmet finner kun én løsning av problemet. Løsningen skal skrives ut som en sekvens av sjakktrekk/springerflytt, f.eks. på denne måten for et 5x5 brett:
</p><p>
</p><pre style="position: relative;">  1 10  5 18  3
 14 19  2 11  6
  9 22 13  4 17
 20 15 24  7 12
 23  8 21 16 25 
<div class="open_grepper_editor" title="Edit &amp; Save To Grepper"></div></pre>
<p>
 Det vil ikke alltid  finnes en løsning på springerproblemet,
dette avhenger av brettstørrelse og utgangsposisjon. I så fall skal
programmet skrive ut at det ikke fant noen løsning.

</p><p>
Oppgaven kan løses ved først å lage en rekursiv
funksjon som genererer alle mulige "springerturer" med lengde
<i>n&nbsp;X&nbsp;n</i> (også utenfor brettet). Man kan så
legge inn avskjæring slik at springeren holder seg innenfor
brettet og aldri oppsøker en rute to ganger. 
</p><p>
Dere anbefales å lage en løsning som tar utgangspunkt i
programmet for å 
<a href="https://it.hiof.no/algdat/kode/labyrint_2.java" class="external" target="_blank" rel="noreferrer noopener"><span>finne veien i en labyrint</span><span aria-hidden="true" class="ui-icon ui-icon-extlink ui-icon-inline" title="Lenker til en ekstern side."></span><span class="screenreader-only">&nbsp;(Lenker til en ekstern side.)</span></a>. Det er her lagt inn en del 
kommentarer i koden, som gir hint om hva som må endres for at
programmet skal kunne skrives om til i stedet å løse
springerproblemet.
</p><p>
  Merk at en slik "standardløsning" som prøver alle 8 mulige veier videre fra hvert felt, vil få en enormt stor arbeidsmengde. For f.eks. et 8x8 brett finnes det
  mer enn 10<sup>51</sup> mulige trekksekvenser. Programmet vil som oftest
  "aldri bli ferdig" for <i>n</i>&nbsp;&gt;&nbsp;7.
</p><p>
  Begynn derfor med
små verdier av <i>n</i> når programmet skal testes.
  Dere kan f.eks. prøve disse tre tilfellene, der en løsning på springerproblemet skal kunne finnes raskt:
</p><p>
  </p><table border="1" cellpadding="4">
    <tbody><tr><td align="center"><i>n</i></td><td align="center">5</td><td align="center">6</td><td align="center">7</td></tr>
    <tr><td align="center"><i>start*</i></td><td align="center">(1,1)</td><td align="center">(1,1)</td><td align="center">(2,2)</td></tr>
  </tbody></table>
<p></p><p>
  Det finnes flere raskere måter å løse springerproblemet på. En kjent heuristisk effektivisering er den såkalte Warnsdorf's regel:
  </p><ul>
    <p></p><li>Prøv bare én vei videre fra hvert felt.
	</li><li>Springeren flyttes alltid videre til det feltet som har <i>færrest</i> mulige trekk videre.
  </li></ul>
I figuren nedenfor vil man velge å flytte til feltet merket med "2" ved bruk av denne regelen.
<p>
<img src="https://it.hiof.no/algdat/oblig/warnsdorf.png" width="300" style="max-width: 300px;">
</p><p>
Warnsdorf-strategien finner oftest en løsning mye raskere, og fungerer også for større verdier av <i>n</i>. Dere kan gjerne implementere denne effektiviseringen, men det er ikke et krav for å få godkjent løsningen.
</p><p>
  </p><hr>
  <font size="-1">*: (1,1) betegner her feltet øverst til venstre på brettet.</font>
</div>
