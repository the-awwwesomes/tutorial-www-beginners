# Model pudełkowy CSS

*"Życie jest jak pudełko czekoladek - nigdy nie wiesz, co Ci się trafi"* - powiedział kiedyś Forest Gump. Z pisaniem kodu CSS może być podobnie - nigdy nie wiadomo, co się trafi, jeśli nie zna się reguł nim rządzących. Dowiedzieliśmy się właśnie, w jaki sposób przeglądarka decyduje, jakie style nadawać elementom HTML. Kolejnym stopniem wtajemniczenia kodera WWW jest zaznajomienie się z zasadami, w jaki sposób owe elementy są wyświetlane i rozmieszczane na stronie. Tutaj bowiem kryje się najwięcej zabawy!

Na początku tej przygody warto zawrzeć bliską znajomość z **modelem pudełkowym**. Model pudełkowy pozwala nam precyzyjnie określić wymiary elementu HTML na stronie. Każdy z elementów na stronie można bowiem potraktować jako prostokąt o określonych wymiarach, który może posiadać wypełnienie (*padding*), obramowanie (*border*) oraz margines (*margin*). 

![Model pudełkowy][1]

[1]: /images/box-model.png

### Wymiary elementu

Elementom HTML możemy nadawać wysokość i szerokość za pomocą właściwości `height` oraz `width`.

```html
<div class="box-of-chocolates">
  Tu siedzą czekoladki!
</div>
```

```css
.box-of-chocolates {
  width: 200px;
  height: 100px;
  background-color: lightsalmon;
}
```

<div class="example-wrapper">
  <div style="width: 200px;height: 100px;background-color: lightsalmon;">
    Tu siedzą czekoladki!
  </div>
</div>

### Wypełnienie (`padding`)

Widzicie pewnie, że w naszym powyższym przykładzie tekst przylega do krawędzi elementu. Nie wygląda to zbyt estetycznie. W CSS istnieje możliwość zdefiniowania wypełnienia elementu. Nie jest to nic innego jak odległość od zawartości do krawędzi elementu. Wypełnienie definiujemy w poniższy sposób:

```html
<div class="box-of-chocolates">
  Tu siedzą czekoladki!
</div>
```

```css
.box-of-chocolates {
  width: 200px;
  height: 100px;
  padding: 30px; /* Dodaję do elmementu wypełnienie o szerokości 30px */
  background-color: lightsalmon;
}
```

<div class="example-wrapper">
  <div style="width: 200px;height: 100px;background-color: lightsalmon;padding: 30px;">
    Tu siedzą czekoladki!
  </div>
</div>

Wypełnienie może przyjmować różne wartości z każdej strony elementu: z lewej, od góry, z prawej i od dołu. Możemy wtedy wypisać każdą wartość osobno:

```css
padding-top: 10px;
padding-right: 15px;
padding-bottom: 20px;
padding-left: 12px;
```

Albo zastosować zapis skrótowy:

```css
padding: 10px 15px 20px 12px;
```

Żeby nie pogubić się w zapisie skrótowym spróbujcie zapamiętać, że wartości wypełnienia zapisujemy zgodnie z ruchem wskazówek zegara, zaczynając od góry. Możecie również wykorzystać do tego kolejność liter w słowie `TRouBLe` - `Top Right Bottom Left`.

### Obramowanie (`border`)

O obramowaniu dowiedzieliśmy się w [rozdziale 8](../css-code/README.md). Przypomnijmy, że możemy nadawać naszym elementom ramki o różnych stylach.

```html
<div class="box-of-chocolates">
  Tu siedzą czekoladki!
</div>
```

```css
.box-of-chocolates {
  width: 200px;
  height: 100px;
  padding: 30px; /* Dodaję do elmementu wypełnienie o szerokości 30px */
  border: 2px dashed navy; /* Dodaję do elementu przerywaną ramkę o szerokości 2px w kolorze granatowym */
  background-color: lightsalmon;
}
```

<div class="example-wrapper">
  <div style="width: 200px;height: 100px;background-color: lightsalmon;padding: 30px; border: 2px dashed navy;">
    Tu siedzą czekoladki!
  </div>
</div>

Warto tutaj dodać, że zapis `border: 2px dashed salmon` jest zapisem skrótowym. Właściwości ramki możemy zdefiniować także osobno:

```css
border-width: 2px;
border-style: dashed;
border-color: salmon;
```

### Margines (`margin`)

Margines jest to odległość między krawędzią (ramką) elementu a innym, sąsiadującym elementem. Marginesy definiujemy podobnie, jak wypełnienie - możemy użyć również zapisu skrótowego.

```html
<div class="box-of-chocolates">
  Tu siedzą czekoladki!
</div>
```

```css
.box-of-chocolates {
  width: 200px;
  height: 100px;
  padding: 30px; /* Dodaję do elmementu wypełnienie o szerokości 30px */
  border: 2px dashed navy; /* Dodaję do elementu przerywaną ramkę o szerokości 2px w kolorze granatowym */
  margin: 20px; /* Dodaję do elmementu margines o szerokości 20px */
  background-color: lightsalmon;
}
```

<div class="example-wrapper">
  <div style="width: 200px;height: 100px;background-color: lightsalmon;padding: 30px; border: 2px dashed navy;margin: 20px;">
    Tu siedzą czekoladki!
  </div>
</div>

Co ciekawe, marginesy mogą również przybierać wartości **ujemne**, w przeciwieństwie do wypełnień i ramek, które to powinny zawsze przyjmować wartości dodatnie (ujemne w tych przypadkach zostaną zignorowane przez przeglądarkę).


To, jak model pudełkowy został wyliczony przez przeglądarkę, możemy podejrzeć w narzędziach deweloperskich w sekcji dotyczącej CSS w zakładce *Computed* (dla Chrome).

![Podgląd modelu pudełkowego w narzędziach deweloperskich][2]

[2]: /images/box-model-devtools.png

## Jednostki w CSS

Czy wiedzieliście, że w CSS możecie określić długość linii tekstu w liczbie znaków? Tak, jest [wiele opcji do wyboru, nie tylko piksele](https://developer.mozilla.org/en/docs/Web/CSS/length). Te przeróżne jednostki przydają się nam do określenia wymiarów elementów (model pudełkowy!), a także rozmiaru fontu. Zapoznajmy się zatem z kilkoma najpopularniejszymi.

- `%`, czyli procenty. Możemy określać wymiary elementu w procentach - będą one wtedy wyrażały te wymiary względem rodzica elementu (czyli kontenera, w którym dany element się znajduje). Procenty są przydatne, jeśli chcemy uzyskać elastyczny layout, którego elementy zmieniają wymiary płynnie wraz ze skalowaniem okna.

```css
.fluid-container {
  width: 33.33%;
}
```

- `em` - podczas, gdy piksele reprezentują fizyczne piksele na ekranie i są jednostką bezwzględną, `em` jest jednostką względną i odnosi się do rozmiaru fontu rodzica elementu. Jeśli nadamy elementowi rozmiar lub wielkość fontu równą `1em`, będzie to oznaczało, że wymiar ten jest równy rozmiarowi fontu jego bezpośredniego rodzica. Spójrzmy na przykład:

```html
<div class="grandpa">
  Jestem dziadkiem
  <div class="father">
    Jestem ojcem
    <div class="son">
      Jestem synem
    </div>
  </div>
</div>
```

```css
.grandpa {
  font-size: 1.5em; /* 16px */
}
 
.father {
  font-size: 1.5em; /* 1.5 * 16px = 24px */
}
 
 
.son {
  font-size: 1.5em; /* 1.5 * 24px = 36px */
}
```

<div class="example-wrapper">
  <div style="font-size: 1.5em;">
    Jestem dziadkiem
    <div style="font-size: 1.5em;">
      Jestem ojcem
      <div style="font-size: 1.5em;">
        Jestem synem
      </div>
    </div>
  </div>
</div>

Widzicie więc, że pomimo, iż każdy z elementów posiada identyczną wartość `font-size` - `1.5em`, wynikowe wielkości się różnią. Na początku może się Wam to wydawać mało intuicyjne, jednak w miarę im będziecie się stawać bardziej zaawansowani, odkryje się przed Wami bogactwo zastosowań dla `em`.

- `rem` - również jest to jednostka względna. Jej nazwę można rozwinąć jako "*root* `em`". Działa więc podobnie do `em` z tą różnicą, że wartość wynikowa jest obliczana względem **korzenia** (*root*) drzewa dokumentu HTML. Zwykle oznacza to, że wartości `rem` obliczane są względem wielkości fonta zadeklarowanego wewnątrz selektora `html`.

```html
<section class="outer">
  <h1>Nagłówek zewnętrzny</h1>
  <p>Paragraf umieszczony w zewnętrznej sekcji.</p>
  <section class="inner">
      <h2>Nagłówek wewnętrzny</h2>
      <p>Paragraf umieszczony w wewnętrznej sekcji.</p>
  </section>
</section>
```

```css
html {
  font-size: 16px;
}
 
.outer {
  font-size: 1.5rem; /* 1.5 * 16px = 24px */
}
 
.inner {
  font-size: 2rem; /* 2 * 16px = 32px */
}
```

- `vw` (ang. <i>vieport witdh</i>) oraz `vh` (ang. <i>viewport height</i>). Są to jednostki dotyczące wysokości i szerokości **okna przeglądarki**. `1vw` oznacza `1/100` szerokości okna, a `1vh` - `1/100` wysokości okna.

```css
.scalable-element {
  width: 50vh; /* Zajmuję połowę wysokości okna przeglądarki */
  height: 100vw; /* Zajmuję całą szerokość okna */
}
```


> #### Exercise::Ćwiczenie 12* (dla chętnych)
>
> Jeśli masz ochotę zakodować nowy layout to ćwiczenie jest dla Ciebie! Wykorzystaj zdobytą dotychczasową wcześniej wiedzę i postaraj się stworzyć stronę, wizualnie zbliżoną do poniższego projektu. 
>
> ![Layout Moodly](/resources/moodly-assets/moodly-layout.png "Layout Moodly")
>
> <a href="../resources/moodly-assets/moodly-assets.zip">Ściągnij paczkę z zasobami</a> - w pliku `moodly.txt` podano nazwy potrzebnych fontów. W paczce znajdziesz również plik `background.jpg`, który będziesz mógł użyć do projektu. Jeśli pojawił się u Ciebie problem z formatowaniem tekstu w pliku `.txt`, otwórz go w Sublime Text.

>Być może nasuwa Ci się pytanie jak dołączać obrazki jako tło? Odpowiedź znajdziesz pod ćwiczeniem.

> Do pozostałych elementów użyj znanych tagów i właściwości CSS m.in. 
>
>- `height` i `width` (do zdefiniowania rozmiarów),
>- `text-align` (do wycentrowania tekstu),
>-`border` (do obramowania guzika "download"),
>- `background-color` (do nadania koloru tła dla sekcji "Features"),
>- świeżo zdobytej wiedzy o modelu pudełkowym.


> Nie przejmuj się, jeśli nie uda Ci się wiernie odwzorować layoutu. Wrócimy do niego po kolejnych zajęciach, kiedy nauczymy się nowych rzeczy :) 
> Poniżej znajdziecie jeszcze kilka przydatnych informacji, w tym właściwości CSS, które pomogą Wam w tym ćwiczeniu.

### Inne właściwości CSS

#### Obrazek jako tło `background-image`

Żeby wypełnić dany element (sekcje, kontener, czy nawet całą zawartość strony, czyli `<body>`) stosujemy właściwość:
```css
  background-image: url('tutaj podaję ścieżkę do obrazka');
```

Przykładowo: 
```
section {
  background-image: url('./images/background.jpg'); 
}```
Pamiętajcie o prawidłowym podaniu względnej ścieżki do obrazka.

Tło może przyjmować jeszcze wiele ciekawych właściwości, które <a href="https://developer.mozilla.org/en/docs/Web/CSS/background-image" target="_blank">znajdziesz tutaj</a>.

Warto potestować różne opcje dla rozmiaru tła, czyli `background-size`
```css
    background-size: cover;
    background-size: 100%;
    background-size: contain;
    background-size: 50%;
```
Sprawdźcie jak zmienia się tło pod wpływem zmiany szerokości okna przeglądarki.

#### Stylowanie listy
Pewnie zastanawiacie się jak pozbyć się kropeczek przy elementach listy (`<ul>`). 
Służy do tego właściwość:
```css
  ul.list{
    list-style: none;
  }
```
Dzięki wartości `none` usunięte zostaną domyślne symbole oznaczające element listy.



###`<div>`, czyli kontener 
<a href="../html-document-structure/index.html">W rozdziale 7.</a> wspomnieliśmy o znaczniku `<div>`, czyli elemencie blokowym. Znacznik ten bardzo często służy nam przy budowaniu layoutów, kiedy żaden z innych tagów nie pasuje znaczeniowo do zawartości, którą umieszczamy.

Najlepiej zobrazuje to poniższy przykład.
Wyobraźmy sobie, że na naszej stronie występuje sekcja "Autorzy", w której zawartych jest kilka kontenerów ze zdjęciami i opisami osób. 
Jak by wyglądał kod HTML takiego rozwiązania?

```html
<section id="authors">
  <!--kontener dla autora-->
  <div class="author-box">
    <h2>Jane Doe</h2>
    <img src="images/jane-img.jpg"/>
    <p>Jane loves cookies and likes spending her time riding a bike</p>
  </div>
  <!--koniec kontenera-->

  <!--kontener dla autora-->
  <div class="author-box">
    <h2>Sam Smith</h2>
    <img src="images/sam-img.jpg"/>
    <p>Sam likes swimming and eating burgers.</p>
  </div>
  <!--koniec kontenera-->

  <!--kontener dla autora-->
  <div class="author-box">
    <h2>Kim Sofa</h2>
    <img src="images/kim-img.jpg"/>
    <p>Kim is keen on watching movies and jogging</p>
  </div>
  <!--koniec kontenera-->
</section>
```

Tak jak widzcie sylwetka każdego autora, zosała umieszczona w konterze, jakim jest `<div>`. 
Znacznik ten zatem umożliwia nam powiązać elementy w dany sposób. Dzięki czemu zawartość staje się jeszcze bardziej uporządkowana, a my możemy wykorzystać CSS-ową klasę kontenera i przypisać mu konkretne style.

Podglądając kod innych stron w sieci, zauważycie, że `<div>` jest badzo popularnym tagiem. Jednak pamiętajcie, że dla treści, których znaczenie może być precyzyjniej określone, warto stosować konkretne tagi np.`<article>` dla artykułów, `<footer>` dla stopki, `<aside>` dla elementów pobocznych, `<nav>` dla nawigacji itd.

