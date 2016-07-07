## Opływanie elementów

Kolejną właściwością, która pomaga nam w budowaniu layoutów, jest `float`, który definiuje <b>opływanie</b> elementów.

```html
<p>
  <img src="latte.jpg" alt="cup of latte" class="latte">
  Cred paleo whatever, portland distillery microdosing pabst. Salvia seitan cardigan kinfolk yuccie, chia umami viral blog. Waistcoat tilde next level, tote bag stumptown four loko franzen. Small batch vice swag, offal chia kickstarter helvetica pitchfork.
  <img src="bicycle.jpg" alt="hipster bicycle" class="bicycle">
  Cornhole schlitz master cleanse, fap flannel plaid you probably haven't heard of them flexitarian tousled echo park fanny pack viral. Bushwick paleo pour-over, schlitz cred 3 wolf moon try-hard flexitarian chartreuse sustainable vegan beard. Asymmetrical pabst tumblr neutra helvetica.
</p>
```

```css
.latte {
  float: left;
}

.bicycle {
  float: right;
}
```

<div class="example-wrapper">
  <p>
    <img src="../../images/float-latte.jpg" alt="cup of latte" style="float:left">
    Cred paleo whatever, portland distillery microdosing pabst. Salvia seitan cardigan kinfolk yuccie, chia umami viral blog. Waistcoat tilde next level, tote bag stumptown four loko franzen. Small batch vice swag, offal chia kickstarter helvetica pitchfork.
    <img src="../../images/float-bicycle.jpg" alt="hipster bicycle" style="float:right">
    Cornhole schlitz master cleanse, fap flannel plaid you probably haven't heard of them flexitarian tousled echo park fanny pack viral. Bushwick paleo pour-over, schlitz cred 3 wolf moon try-hard flexitarian chartreuse sustainable vegan beard. Asymmetrical pabst tumblr neutra helvetica.
  </p>
</div>

Powyższy przykład demonstruje klasyczny przypadek użycia `float` i odnosi się wprost do opływania elementu tekstem. `float` wyjmuje element z jego naturalnej pozycji na stronie i wyrównuje odpowiednio do lewej lub prawej strony kontenera (rodzica). Pozostałe elementy, które znajdują się wewnątrz tego samego kontenera, będą go opływać.

> ####Important::Ważne
>
> Siostrzaną właściwością `float` jest `clear`. Służy ona do "resetowania" opływania kolejnych elementów. Spójrzmy na przykład:
> ```html
<div class="container">
  <div class="item"></div>
  <div class="item"></div>
  <div class="item"></div>
  <div class="item item-cleared"></div>
</div>
```
> ```css
.item {
  background: lightgreen;
  width: 100px;
  height: 100px;
  margin: 5px;
  float: left;
}
.item-cleared {
  clear: both;
  background: lightblue;
}
```
>
> <div class="example-wrapper" style="height: 300px">
  <div style="float:left;width:100px;height:100px;margin:5px;background:lightgreen"></div>
  <div style="float:left;width:100px;height:100px;margin:5px;background:lightgreen"></div>
  <div style="float:left;width:100px;height:100px;margin:5px;background:lightgreen"></div>
  <div style="float:left;width:100px;height:100px;margin:5px;background:lightblue;clear:both"></div>
</div>
>
> Nasz ostatni element otrzymał właściwość `clear: both`, co oznacza, że zamiast opływać sąsiadujące elementy – i zostać umieszczony w tym samym rzędzie, co zielone kwadraty – pojawił się w następnej linii.
>
> Spójrzmy jeszcze na przykład, gdzie wewnątrz kontenera znajdują się elementy z `float`.
>
> ```html
<div class="container">
  <div class="item"></div>
  <div class="item"></div>
  <div class="item"></div>
  <div class="item"></div>
</div>
```
> ```css
.container {
  border: 1px solid blue;
  padding: 3px;
}
.item {
  background: lightgreen;
  width: 100px;
  height: 100px;
  margin: 5px;
  float: left;
}
```
>
> <div class="example-wrapper" style="height:200px">
  <div style="border:1px solid blue;padding:3px">
    <div style="float:left;width:100px;height:100px;margin:5px;background:lightgreen"></div>
    <div style="float:left;width:100px;height:100px;margin:5px;background:lightgreen"></div>
    <div style="float:left;width:100px;height:100px;margin:5px;background:lightgreen"></div>
    <div style="float:left;width:100px;height:100px;margin:5px;background:lightgreen"></div>
  </div>
</div>
>
> Wygląda trochę kiepsko, prawda? Wszystkie elementy z `float: left` wylądowały poza kontenerem, a sam kontener wygląda na pusty. Takiemu zachowaniu można zaradzić czyszcząc opływanie i tutaj również jest pomocna właściwość `clear`.
>
> ```html
<div class="container">
  <div class="item"></div>
  <div class="item"></div>
  <div class="item"></div>
  <div class="item"></div>
  <div class="clear"></div>
</div>
```
> ```css
.clear {
  clear: both;
}
```
>
> <div class="example-wrapper" style="height:200px">
  <div style="border:1px solid blue;padding:3px">
    <div style="float:left;width:100px;height:100px;margin:5px;background:lightgreen"></div>
    <div style="float:left;width:100px;height:100px;margin:5px;background:lightgreen"></div>
    <div style="float:left;width:100px;height:100px;margin:5px;background:lightgreen"></div>
    <div style="float:left;width:100px;height:100px;margin:5px;background:lightgreen"></div>
    <div style="clear:both"></div>
  </div>
</div>
>
> Niestety, nie jest to wcale idealne rozwiązanie. Nie chcemy w końcu zaśmiecać naszej strony pustymi elementami użytymi tylko ze względu na wygląd. Istnieją nieco lepsze sposób, oparte na <i>pseudoelementach</i> (co to takiego, dowiemy się już niebawem) – tzw. [*micro-clearfix*](http://nicolasgallagher.com/micro-clearfix-hack/) – oraz [własności `overflow`](http://www.forumweb.pl/porady-i-tutoriale-www/css-clearowanie-czyli-problemy-z-float,47914).

Opływanie w CSS często przydaje się do tworzenia całych layoutów oraz poszczególnych komponentów strony.

```html
<div class="profile">
  <img src="hipster.jpg" alt="random hipster" class="profile-pic">
  <h1>Rafael Williamson</h1>
  <p>Vinyl fanny pack cardigan tousled umami slow-carb meh. Kinfolk post-ironic synth DIY heirloom, vegan schlitz.</p>
  <div class="clear"></div>
</div>
```

```css
.profile {
  border: 5px solid lightgreen;
  padding: 15px;
}

.profile-pic {
  float: left;
  margin-right: 15px;
  border: 5px solid lightgreen;
}

.clear {
  clear: both;
}
```

<div class="example-wrapper">
  <div style="border: 5px solid lightgreen;padding: 15px;">
    <img src="../../images/float-hipster.jpg" alt="random hipster" style="float:left;margin-right:15px;border: 5px solid lightgreen;">
    <h1>Rafael Williamson</h1>
    <p>Vinyl fanny pack cardigan tousled umami slow-carb meh. Kinfolk post-ironic synth DIY heirloom, vegan schlitz.</p>
    <div style="clear:both"></div>
  </div>
</div>
