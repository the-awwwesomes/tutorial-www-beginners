## Pseudoelementy

Pseudoelementy, w odróżnieniu od pseudoklas pozwalają nam na stylowanie części dokumentu bez uciekania się do dodawania czysto dekoracyjnych elementów HTML. Zwiększają znacznie nasze możliwości w kodowaniu ciekawych efektów zawartych w projektach stron.

```css
selektor::pseudoelement {
  właściwość: wartość;
}
```

### Tworzenie "wirtualnych" elementów

Jednymi z najczęściej używanych pseudoelementów są `::before` oraz `::after`. Umożliwiają nam one dodanie "wirtualnej" zawartości, która nie będzie dodana do dokumentu HTML, ale będzie pełnić funkcję dekoracyjną bądź wzbogacającą zawartość tego dokumentu. Do każdego elementu HTML możemy dodać dokładnie jeden pseudoelement `::before` oraz dokładnie jeden element `::after`.

> ####Important::Ważne
>
> Istotne jest, aby wewnątrz selektora pseudoelementu (`::before` tak samo jak `::after`) znajdowała się właściwość `content` mówiąca o zawartości tekstowej pseudoelementu. Może się zdarzyć, że nie chcemy wstawiać żadnego tekstu do pseudoelementu, ponieważ jest on tam całkowicie zbędny – wtedy jako wartość właściwości `content` wystarczy podać spację lub pusty ciąg (` ` lub ``).

Powyższe pseudoelementy mogą mieć [wiele różnorodnych zastosowań](https://css-tricks.com/pseudo-element-roundup/). Poniżej prezentujemy kilka z najczęściej używanych.

Przykładowo, możemy zmienić domyślne, nudne kropki przy elementach listy na złote gwiazdki.

```html
<ul class="stars">
  <li>Betelgeza</li>
  <li>Syriusz</li>
  <li>Gwiazda Polarna</li>
</ul>
```

```css
.stars {
  list-style-type: none;
  padding-left: 0;
}

.stars li::before {
  content: '\2605';
  color: gold;
  margin-right: 1rem;
}
```

<div id="awww-pseudoselectors-stars" class="example-wrapper">
  <ul style="list-style-type:none;padding-left:0;">
    <li>Betelgeza</li>
    <li>Syriusz</li>
    <li>Gwiazda Polarna</li>
  </ul>
</div>

Pseudoelementy okazują się także bardzo przydatne, kiedy chcemy dodać podpowiedzi (<i>tooltipy</i>) w jakimś miejscu na stronie.

```html
<a href="http://theawwwesomes.org" class="tooltip">
  The Awwwesomes
</a>
```

```css
.tooltip {
  position: relative;
}

.tooltip::before {
  content: 'Darmowe warsztaty HTML i CSS';
  position: absolute;
  left: 100%;
  top: 0;
  background: coral;
  color: white;
  width: 100%;
  padding: 0.5em;
  margin-left: 1em;
  border-radius: 5px; /* dodaje zaokrąglenia rogów */
  display: none;
}

.tooltip:hover::before {
  display: inline-block;
}
```

<div id="awww-pseudoselectors-tooltip" class="example-wrapper">
  <a href="http://theawwwesomes.org" class="tooltip">The Awwwesomes</a>
</div>

Przypomnijmy sobie teraz przykład z [rozdziału 14.2](../../css-layout/css-floats/README.md), w którym próbowaliśmy sobie radzić z <i>czyszczeniem</i> opływania za pomocą dodatkowego, pustego elementu HTML. Zapowiedzieliśmy już wtedy, że można to zrobić w dużo bardziej elegancki sposób używając właśnie pseudoelementów.

Poniżej prezentujemy [<i>micro-clearfix</i>](http://nicolasgallagher.com/micro-clearfix-hack/)

```css
.clearfix::before,
.clearfix::after {
  content: ' ';
  display: table;
}

.clearfix::after {
  clear: both; /* Pseudoelement zamiast pustego div'a */
}
```

```html
<div class="container clearfix">
  <div class="item"></div>
  <div class="item"></div>
  <div class="item"></div>
  <div class="item"></div>
</div>
```

<div class="example-wrapper" style="height:200px">
  <div style="border:1px solid blue;padding:3px">
    <div style="float:left;width:100px;height:100px;margin:5px;background:lightgreen"></div>
    <div style="float:left;width:100px;height:100px;margin:5px;background:lightgreen"></div>
    <div style="float:left;width:100px;height:100px;margin:5px;background:lightgreen"></div>
    <div style="float:left;width:100px;height:100px;margin:5px;background:lightgreen"></div>
    <div style="clear:both"></div>
  </div>
</div>

Dodanie zadeklarowanej powyżej klasy `clearfix` sprawi, że wewnątrz kontenera powstanie pseudoelement i nie będzie już potrzeby dodawania zupełnie zbędnego, pustego elementu HTML.

> ####Important::Ważne
>
> Niestety, nie jest możliwe dodanie powyższych pseudoelementów dla elementów <i>pustych</i>, czyli między innymi `<img>` lub `<input>.`

### Inne pseudoelementy

Powyższe przykłady nie wyczerpują [wszystkich rodzajów selektorów pseudoelementów](https://developer.mozilla.org/en/docs/Web/CSS/Pseudo-elements).

Za pomocą pseudoelementu `::selection` możemy zmieniać kolor tła zaznaczonego tekstu (domyślnie zwykle jest to niebieski).

```css
/*
  Uwaga! Aby nasz pseudoelement
  działał prawidłowo w Firefoksie
  należy dodać przedrostek `-moz-`
*/
::-moz-selection {
  background: hotpink;
}

::selection {
  background: hotpink;
}
```

Zaznaczcie fragment poniższego akapitu i sprawdźcie sami, jak to działa:

<div id="awww-pseudoselectors-selection" class="example-wrapper">
  Readymade yuccie man bun distillery yr twee. Pitchfork etsy salvia quinoa put a bird on it synth. Mixtape craft beer semiotics vice. Chartreuse swag blog drinking vinegar blue bottle brunch meh echo park shabby chic yuccie next level. Flannel small batch semiotics selfies, gastropub forage fingerstache you probably haven't heard of them synth keytar before they sold out. Mumblecore brooklyn meggings put a bird on it, beard pabst kale chips VHS godard typewriter. Swag ethical hashtag man braid locavore small batch.
</div>

Innym ciekawym pseudoelementem jest `::first-letter`, dzięki któremu możemy uzyskać na przykład efekt znany z książek, czyli wyróżnienie pierwszej litery akapitu.

```css
::first-letter {
  font-size: 3em;
}
```  

<div id="awww-pseudoselectors-letter" class="example-wrapper">
  <p>Typewriter 90's man braid, banh mi stumptown drinking vinegar XOXO sustainable pabst cronut gluten-free truffaut biodiesel. Locavore pickled freegan, plaid fingerstache bitters ramps gastropub craft beer readymade deep v cornhole aesthetic. Semiotics lo-fi affogato, microdosing single-origin coffee aesthetic tumblr lomo 3 wolf moon iPhone swag marfa pour-over vegan. Vinyl jean shorts squid, 8-bit brooklyn everyday carry viral YOLO stumptown shoreditch locavore slow-carb.</p>
</div>
