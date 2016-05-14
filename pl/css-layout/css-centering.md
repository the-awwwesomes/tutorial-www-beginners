## Jak wyśrodkować elementy w pionie i poziomie?

Częstym problemem w kodowaniu layoutu strony jest środkowanie elementów. Poinstruowanie przeglądarki, aby umieściła nasz wybrany element wydaje się dość skomplikowanym zadaniem.

W tym rodziale postaramy się pokazać Wam, że nie jest to wcale takie trudne i wystarczy poznać kilka prostych technik, aby stać się mistrzem środkowania w CSS.

### Środkowanie w poziomie

To, jakiej techniki środkowania w poziomie użyć zależy w dużej mierze od tego, czy nasz element jest elementem blokowym czy liniowym (lub liniowo-blokowym).

- Jak wyśrodkować element blokowy? Wystarczy nadać mu określoną szerokość oraz automatycznie wyliczone marginesy po lewej i prawej.

```html
<div class="container">
  <div class="center-me">
    Jestem elementem blokowym
  </div>
</div>
```

```css
.center-me {
  background: lightgreen;
  height: 100px;
  width: 300px;
  margin: 0 auto; /* Środkuję blokowy element */
}
```

<div class="example-wrapper">
  <div style="background:lightgreen;height:100px;width:300px;margin:0 auto;">
    Jestem elementem blokowym
  </div>
</div>

- Jeśli nasz element jest liniowy (lub liniowo-blokowy), sztuczka z automatycznymi marginesami nie zadziała. Należy go wtedy potraktować jako zwykły tekst i wycentrować w odpowiedni temu sposób.

```html
<div class="container">
  <div class="center-me">
    Jestem elementem liniowo-blokowym
  </div>
</div>
```

```css
/* 
  Ważne, aby wyśrodkowanie 
  zdefiniować na elemencie otaczającym
*/
.container {
  text-align: center;
}

.center-me {
  display: inline-block;
  background: lightgreen;
  height: 100px;
  width: 300px;
}
```

<div class="example-wrapper" style="text-align:center">
  <div style="display:inline-block;background:lightgreen;height:100px;width:300px;margin:0 auto;">
    Jestem elementem liniowo-blokowym
  </div>
</div>

### Środkowanie w pionie

Środkowanie elementów w pionie jest nieco bardziej skomplikowane, niż środkowanie w poziomie. Techniki środkowania w pionie dla elementów liniowych wymagają już nieco wprawy i zaawansowania w CSS, to samo dotyczy elementów blokowych, których wymiary nie są określone wprost. Wszystkich ambitnych, którzy chcą zapoznać się z tajnikami środkowania, odsyłamy do [tego artykułu](https://css-tricks.com/centering-css-complete-guide/).

Dowiedzmy się zatem, w jaki sposób wyśrodkować element blokowy o znanej wysokości.

```html
<div class="container">
  <div class="center-me">
    Jestem wyśrodkowany w pionie
  </div>
</div>
```

```css
.container {
  position: relative;
}

.center-me {
  background: crimson;
  width: 200px;
  height: 200px;
  position: absolute;
  top: 50%;
  margin-top: -100px; /* 200px / 2 = 100px */
}
```

<div class="example-wrapper" style="height:400px;position:relative">
  <div style="background:crimson;width:200px;height:200px;position:absolute;top:50%;margin-top:-100px;">
    Jestem wyśrodkowany w pionie
  </div>
</div>

Powyższa technika bazuje na pozycjonowaniu. Aby wyśrodkować element w pionie, musimy najpierw umieścić jego górną krawędź 50% od góry kontenera. W tym momencie element nie będzie jeszcze wizualnie wyśrodkowany, należy go wtedy przesunąć do góry o połowę jego wysokości. Przydatne tu okazują się ujemne marginesy.

### Flexbox