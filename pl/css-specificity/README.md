# Złożone selektory i specyficzność

Wiemy już, jak tworzyć proste selektory w CSS. Umiemy stylować elementy wykorzystując ich nazwy, atrybuty, `id` lub klasy. Przyszła pora, aby przenieść się na nieco wyższy poziom i zaznajomić z nieco trudniejszymi zagadnieniami.

W CSS możemy tworzyć złożone (kombinowane) selektory. Umożliwia to nam zawężenie kryterium wyboru elementu. Przyjrzyjmy się kilku przykładom:

```css

/*
  Wybieram wszystkie elementy typu `a`,
  których wartość atrybutu `href`
  to dokładnie `http://theawwwesomes.org`
*/
a[href="http://theawwwesomes.org"] {
  color: #f14b5c;
}

/*
  Wybieram wszystkie elementy typu `li`,
  które jednocześnie przyjmują klasę
  `active`
*/
li.active {
  background-color: yellow;
}

/*
  Wybieram wszystkie elementy,
  które przyjmują jednocześnie
  klasy `classy` i `awesome`
*/
.classy.awesome {
  color: deeppink;
}
```

Tak, jak wyżej – jeśli umieścimy obok siebie dwa (lub więcej) selektory (bez spacji!) oznacza to, że dane reguły CSS zostaną zastosowane dla elementów spełniających wszystkie te kryteria **jednocześnie**.

Możemy również wskazywać na elementy według relacji, w jakich znajdują się wobec siebie w drzewie dokumentu HTML.

```css
/*
  Wybieram wszystkie elementy typu `input`,
  które znajdują się wewnątrz elementu,
  który ma nadaną klasę `awesome-form`
*/
.awesome-form input {
  border: 1px solid #f14b5c;
}

/*
  Wybieram wszystkie elementy typu `p`,
  które znajdują się wewnątrz elementu
  o id `unicorn`
*/
#unicorn p {
  color: green;
}
```

W takim wypadku należy umieszczać kolejne selektory po spacji. Zobaczcie zresztą sami, jak to działa:

```html
<nav class="main-nav">
  <ul>
    <li><a href="/about">O nas</a></li>
    <li><a href="/pricing">Cennik</a></li>
    <li class="active"><a href="/contact">Kontakt</a></li>
  </ul>
</nav>
```

```css
.main-nav li {
  background-color: yellow;
}

.main-nav li.active {
  background-color: green;
}
```

<div class="example-wrapper">
  <nav class="main-nav">
    <ul>
      <li style="background-color: yellow;"><a href="">O nas</a></li>
      <li style="background-color: yellow;"><a href="">Cennik</a></li>
      <li style="background-color: green;"><a href="">Kontakt</a></li>
    </ul>
  </nav>
</div>

## Specyficzność

Wybierając za pomocą CSS dowolny element w dokumencie HTML można zazwyczaj zastosować więcej niż jeden selektor.

```html
<nav class="main-nav">
  <ul>
    <li><a href="http://theawwwesomes.org" class="active">O nas</a></li>
    <li><a href="/pricing">Cennik</a></li>
    <li><a href="/contact">Kontakt</a></li>
  </ul>
</nav>
```

```css
ul li a[href="http://theawwwesomes.org"] {
  border: 1px dashed azure;
  color: deeppink;
}

.main-nav li.active {
  border: 2px solid #fca890;
  background-color: silver;
}
```

Mając tę świadomość, a także wiedząc, że style mogą pochodzić z różnych źródeł, w jaki sposób przeglądarka określa, jakie style mają zostać zastosowane dla naszego elementu? Aby odpowiedzieć na to pytanie, musimy zapoznać się z pojęciem [<b>specyficzności</b>](https://css-tricks.com/specifics-on-css-specificity/) (ang. <i>specificity</i>).

Każdy rodzaj selektora możemy umieścić na ściśle określonej pozycji w szeregu ważności. Wymieńmy je w kolejności od najmniej do najbardziej ważnych:

1) Element oraz pseudoelement

```css
div { }
p::after { }
```

2) Klasa, pseudoklasa oraz atrybut

```css
.container { }
.list-item:first-child { }
[type="url"] { }
```

3) ID

```css
#users-chart { }
```
4) Styl zapisany <i>inline</i>

```html
<ul style="list-style-type: none"></ul>
```

O tym, co to są pseudoklasy i pseudoelementy dowiemy się w późniejszych rozdziałach.

> ####Important::Ważne
>
> Wróćmy w tym momencie do wspomnianego w poprzednim rozdziale słowa kluczowego `!important`. Jak pewnie się domyślacie, służy ono do nadawania wybranym regułom specjalnej ważności.
>
> ```html
<p class="stylish" style="color: gold">Jestem przykładowym paragrafem.</p>
```
>
> ```css
.stylish {
  color: silver !important;
  padding: 5px 10px;
}
```
>
> W powyższym przykładzie tekst naszego akapitu zostanie pokolorowany na szaro (`silver`), pomimo że według reguł specyficzności to style `inline` powinny zyskać najwyższy priorytet.
>
> Musicie być bardzo ostrożni używając `!important`, ze względu na to, że takie style są bardzo trudne do nadpisania – bardzo łatwo o bałagan w kodzie. Radzimy Wam zatem, aby **unikać** używania tego słowa kluczowego jak tylko się da!

Jeśli zatem na nasz element wskazuje kilka prostych selektorów, określenie, jakie style powinny zostać mu nadane jest całkiem proste. Jak sprawa ma się w przypadku selektorów kombinowanych? W tym wypadku specyficzność jest wyliczana bazując na 4-elementowej [krotce](https://pl.wikipedia.org/wiki/Krotka_%28struktura_danych%29):

```css
0 0 0 0
```

1) Dla każdego selektora elementu bądź pseudoelementu zwiększ 4-ty element o 1.
```css
0 0 0 1
```

2) Dla każdej klasy, pseudoklasy lub atrybutu zwiększ 3-ci element o 1.
```css
0 0 1 0
```

3) Dla każdego ID zwiększ 2-gi element o 1.
```css
0 1 0 0
```

4) Dla każdego stylu `inline` zwiększ pierwszy element o 1.
```css
1 0 0 0
```

>####Important::Ważne
>
> Zwróćcie w tym momencie uwagę, że powyższe wartości są krotką, nie bazują na systemie dziesiętnym. Zatem użycie selektora złożonego nawet z 11 klas nie "przebije" selektora złożonego z jednego ID.

Wróćmy teraz do naszego przykładu menu:

```html
<nav class="main-nav">
  <ul>
    <li><a href="http://theawwwesomes.org" class="active">O nas</a></li>
    <li><a href="/pricing">Cennik</a></li>
    <li><a href="/contact">Kontakt</a></li>
  </ul>
</nav>
```

```css
ul li a[href="http://theawwwesomes.org"] {
  border: 1px dashed azure;
  color: deeppink;
}

.main-nav li.active {
  border: 2px solid #fca890;
  background-color: silver;
}
```

I obliczmy specyficzność naszych selektorów:

```css
ul li a[href="http://theawwwesomes.org"]

/* Mamy tu 3 selektory elementu oraz 1 selektor atrybutu */
0 0 1 3

.main-nav li.active

/* Mamy tu 1 selektor elementu oraz 2 selektory klasy */
0 0 2 1
```

Zatem w tej rywalizacji wygra drugi selektor `.main-nav li.active`. Zauważmy, że rywalizacja dotyczy wartości właściwości wewnątrz selektora. Nasz element wynikowo uzyska zatem style:

```css
  background-color: silver;
  border: 2px solid #fca890;
  color: deeppink;
```

> ####Exercise::Ćwiczenie 11
>
> Popatrz na przykładowy kod:
> ```html
<section id="authors" class="section-wrapper">
  <div class="author-box">
    <h2>Jane Doe</h2>
    <p>Jane loves cookies and likes spending her time riding a bike.</p>
    <a href="http://jdoe.com" class="author-website">Jane's website</a>
  </div>
  <div class="author-box">
    <h2>Sam Smith</h2>
    <p>Sam likes swimming and eating burgers.</p>
    <a href="http://sam-smith.co.uk" class="author-website">Sam's website</a>
  </div>
</section>
```
> ```css
.author-box a.author-website {
  color: green;
}
.section-wrapper [href="http://jdoe.com"] {
  color: yellow;
}
#authors .author-box a {
  color: orange;
}
```
> Wiedząc, w jaki sposób przeglądarka oblicza specyficzność określ, jaki kolor uzyska element `<a href="http://jdoe.com" class="author-website">Jane's website</a>`.
