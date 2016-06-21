## Pozycjonujemy elementy na stronie

Domyślnie elementy na stronie umieszczane są jeden za drugim (z uwzględnieniem wartości właściwości `display`). Czasem jednak zdarza się, że potrzebujemy uzyskać efekt nałożenia jednego elementu na drugi bądź przesunięcia. Na szczęście język CSS jest wyposażony w narzędzia, które nam to umożliwiają. Są to właściwości związane z <b>pozycjonowaniem</b>.

Do pozycjonowania służy właściwość `position`, która może przyjmować poniższe wartości:

- `static` – jest to wartość domyślna dla każdego elementu, nie trzeba deklarować jej wprost.
- `relative` – zmienia położenie elementu względem niego samego.
- `absolute` – wyjmuje element z jego pierwotnego położenia i umieszcza go we wskazanym miejscu względem najbliższego kontenera, który ma zdefiniowane `position: relative`.
- `fixed` – umieszcza element na stałej pozycji względem okna przeglądarki (<i>viewport</i>). Dobrym przykładem użycia jest menu na stałe "przyklejone" u góry strony.

Oprócz deklaracji `position` musimy również zadeklarować wartości współrzędnych, dzięki którym możemy precyzyjnie określić położenie naszego elementu: `top`, `bottom`, `right` oraz `left`.

Na prostych przykładach zobaczymy, jak opanować pozycjonowanie w CSS.

```html
<div class="container">
  <div class="item"></div>
  <div class="item"></div>
  <div class="item item-relative"></div>
  <div class="item"></div>
</div>
```

```css
.item {
  width: 150px;
  height: 150px;
  margin: 5px;
  background: salmon;
}

.item-relative {
  background: lightblue;
  position: relative;
  top: -20px;
  right: 25px;
}
```

<div class="example-wrapper">
  <div style="width:150px;height:150px;background:salmon;margin:5px"></div>
  <div style="width:150px;height:150px;background:salmon;margin:5px"></div>
  <div style="width:150px;height:150px;background:lightblue;position:relative;top:-20px;right:25px;margin:5px"></div>
  <div style="width:150px;height:150px;background:salmon;margin:5px"></div>
</div>

Powyżej przykład elementu wypozycjonowamego relatywnie (czyli względem samego siebie).

Pozycjonowanie absolutne wymaga od nas nieco ostrożności, jednak jeśli wiemy, jak działa, nie wpadniemy w żadną pułapkę.

```html
<div class="container">
  <div class="item"></div>
  <div class="item"></div>
  <div class="item item-absolute"></div>
  <div class="item"></div>
</div>
```

```css
.item {
  width: 150px;
  height: 150px;
  margin: 5px;
  background: salmon;
}

.item-absolute {
  background: lightblue;
  position: absolute;
  top: -20px;
  right: 25px;
}
```

<div class="example-wrapper" style="position:relative">
  <div style="width:150px;height:150px;background:salmon;margin:5px"></div>
  <div style="width:150px;height:150px;background:salmon;margin:5px"></div>
  <div style="width:150px;height:150px;background:lightblue;position:absolute;top:-20px;right:25px;margin:5px"></div>
  <div style="width:150px;height:150px;background:salmon;margin:5px"></div>
</div>

Powyższy element został wyjęty ze swojego miejsca (jak widać, nie pozostawia również po sobie wolnej przestrzeni – cóż za oszczędność!) i umieszczony zupełnie gdzie indziej, w prawym górnym rogu strony.

Jeśli używamy pozycjonowania absolutnego nieostrożnie, nasz element może wylądować w dość niespodziewanym miejscu. Musimy więc pamiętać, że każdy element z `position: absolute` jest pozycjonowany **względem** jakiegoś innego elementu. Takim odniesieniem jest najbliższy element, któremu nadaliśmy `position: relative`. Musimy też pamiętać, że element pozycjonowany absolutnie musi znajdować się **wewnątrz** elementu z `position: relative`.

```html
<div class="item"></div>

<div class="item item-outer">
  <div class="item item-inner">
</div>

<div class="item"></div>
```

```css
.item {
  width: 100%;
  height: 100px;
  margin: 5px 0;
  background: salmon;
}

/*
  Względem tego elementu będziemy
  pozycjonować inny element.
  Nie jest konieczne podawanie
  współrzędnych `top` itp.
  ponieważ chcemy, aby pozostał
  na swoim miejscu
*/
.item-outer {
  position: relative;
}

/*
  To element, który pozycjomujemy
  względem `.item-outer`
*/
.item-inner {
  width: 50px;
  height: 50px;
  background: lightblue;

  /* Zostanie umieszczony w prawym górnym rogu */
  position: absolute;
  top: 0;
  right: 0;
}
```

<div class="example-wrapper">
  <div style="width:100%;height:100px;margin:5px 0;background:salmon"></div>
  <div style="width:100%;height:100px;margin:5px 0;background:salmon;position:relative;"><div style="width:50px;height:50px;background:lightblue;position:absolute;top:0;right:0"></div></div>
  <div style="width:100%;height:100px;margin:5px 0;background:salmon"></div>
</div>
