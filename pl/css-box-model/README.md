# Model pudełkowy CSS

*"Życie jest jak pudełko czekoladek - nigdy nie wiesz, co Ci się trafi"* - powiedział kiedyś Forest Gump. Z pisaniem kodu CSS może być podobnie - nigdy nie wiadomo, co się trafi, jeśli nie zna się reguł nim rządzących. Dowiedzieliśmy się właśnie, w jaki sposób przeglądarka decyduje, jakie style nadawać elementom HTML. Kolejnym stopniem wtajemniczenia kodera WWW jest zaznajomienie się z zasadami, w jaki sposób owe elementy są wyświetlane i rozmieszczane na stronie. Tutaj bowiem kryje się najwięcej zabawy!

Na początku tej przygody warto zawrzeć bliską znajomość z **modelem pudełkowym**. Model pudełkowy pozwala nam precyzyjnie określić wymiary elementu HTML na stronie. Każdy z elementów na stronie można bowiem potraktować jako prostokąt o określonych wymiarach, który może posiadać wypełnienie (*padding*), obramowanie (*border*) oraz margines (*margin*). 

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

Czy wiedzieliście, że w CSS możecie określić długość linii tekstu w liczbie znaków? Tak, jest wiele opcji do wyboru, nie tylko piksele. Te przeróżne jednostki przydają się nam do określenia wymiarów elementów (model pudełkowy!), a także rozmiaru fontu. Zapoznajmy się zatem z kilkoma najpopularniejszymi.

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

- `vw` oraz `vh`. Są to jednostki dotyczące wysokości i szerokości **okna przeglądarki**. `1vw` oznacza `1/100` szerokości okna, a `1vh` - `1/100` wysokości okna.

```css
.scalable-element {
  width: 50vh; /* Zajmuję połowę wysokości okna przeglądarki */
  height: 100vw; /* Zajmuję całą szerokość okna */
}
```
