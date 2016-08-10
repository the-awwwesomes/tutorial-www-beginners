## Jednostki w CSS

Czy wiedzieliście, że w CSS możecie określić długość linii tekstu w liczbie znaków? Tak, jest [wiele opcji do wyboru, nie tylko piksele](https://developer.mozilla.org/en/docs/Web/CSS/length). Te przeróżne jednostki przydają się nam do określenia wymiarów elementów (model pudełkowy!), a także rozmiaru fontu. Zapoznajmy się zatem z kilkoma najpopularniejszymi.

- `%`, czyli procenty. Możemy określać wymiary elementu w procentach. Będą one wtedy wyrażały te wymiary względem rodzica elementu (czyli kontenera, w którym dany element się znajduje). Procenty są przydatne, jeśli chcemy uzyskać elastyczny layout, którego elementy zmieniają wymiary płynnie wraz ze skalowaniem okna.

```css
.fluid-container {
  width: 33.33%;
}
```

- `em` – podczas, gdy piksele reprezentują fizyczne piksele na ekranie i są jednostką bezwzględną, `em` jest jednostką względną i odnosi się do rozmiaru fontu rodzica elementu. Jeśli nadamy elementowi rozmiar lub wielkość fontu równą `1em`, będzie to oznaczało, że wymiar ten jest równy rozmiarowi fontu jego bezpośredniego rodzica. Spójrzmy na przykład:

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

<a href="http://codepen.io/theawwwesomes/pen/grXgoJ" class="codepen-link">Edytuj na CodePen</a>

Widzicie więc, że pomimo, iż każdy z elementów posiada identyczną wartość `font-size` – `1.5em` – wynikowe wielkości się różnią. Na początku może się Wam to wydawać mało intuicyjne, jednak w miarę jak będziecie się stawać bardziej zaawansowani, odkryje się przed Wami bogactwo zastosowań dla `em`.

- `rem` – również jest to jednostka względna. Jej nazwę można rozwinąć jako "<i>root</i> `em`". Działa więc podobnie do `em` z tą różnicą, że wartość wynikowa jest obliczana względem <b>korzenia</b> (<i>root</i>) drzewa dokumentu HTML. Zwykle oznacza to, że wartości `rem` obliczane są względem wielkości fonta zadeklarowanego wewnątrz selektora `html`.

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

<div class="example-wrapper">
  <section style="font-size:24px">
    <h1>Nagłówek zewnętrzny</h1>
    <p>Paragraf umieszczony w zewnętrznej sekcji.</p>
    <section style="font-size:32px">
        <h2>Nagłówek wewnętrzny</h2>
        <p>Paragraf umieszczony w wewnętrznej sekcji.</p>
    </section>
  </section>
</div>

<a href="http://codepen.io/theawwwesomes/pen/QEOdmy" class="codepen-link">Edytuj na CodePen</a>

- `vw` (ang. <i>vieport witdh</i>) oraz `vh` (ang. <i>viewport height</i>). Są to jednostki dotyczące wysokości i szerokości <b>okna przeglądarki</b>. `1vw` oznacza `1/100` szerokości okna, a `1vh` – `1/100` wysokości okna.

```css
.scalable-element {
  width: 50vh; /* Zajmuję połowę wysokości okna przeglądarki */
  height: 100vw; /* Zajmuję całą szerokość okna */
}
```