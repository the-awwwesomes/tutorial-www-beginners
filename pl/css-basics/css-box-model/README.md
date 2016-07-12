## Model pudełkowy CSS

"Życie jest jak pudełko czekoladek – nigdy nie wiesz, co Ci się trafi" – powiedział kiedyś Forrest Gump. Z pisaniem kodu CSS może być podobnie – nigdy nie wiadomo, co się trafi, jeśli nie zna się reguł nim rządzących. Dowiedzieliśmy się właśnie, w jaki sposób przeglądarka decyduje, jakie style nadawać elementom HTML. Kolejnym stopniem wtajemniczenia kodera WWW jest zaznajomienie się z zasadami, w jaki sposób owe elementy są wyświetlane i rozmieszczane na stronie. Tutaj bowiem kryje się najwięcej zabawy!

Na początku tej przygody warto zawrzeć bliską znajomość z <b>modelem pudełkowym</b>. Model pudełkowy pozwala nam precyzyjnie określić wymiary elementu HTML na stronie. Każdy z elementów na stronie można bowiem potraktować jako prostokąt o określonych wymiarach, który może posiadać wypełnienie (<i>padding</i>), obramowanie (<i>border</i>) oraz margines (<i>margin</i>).

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
  width: 400px;
  height: 200px;
  background-color: lightsalmon;
}
```

<div class="example-wrapper">
  <div style="width: 400px;height: 200px;background-color: lightsalmon;box-sizing: content-box;">
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
  width: 400px;
  height: 200px;
  padding: 30px; /* Dodaję do elmementu wypełnienie o szerokości 30px */
  background-color: lightsalmon;
}
```

<div class="example-wrapper">
  <div style="width: 400px;height: 200px;background-color: lightsalmon;padding: 30px;box-sizing: content-box;">
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

Żeby nie pogubić się w zapisie skrótowym, spróbujcie zapamiętać, że wartości wypełnienia zapisujemy zgodnie z ruchem wskazówek zegara, zaczynając od góry. Możecie również wykorzystać do tego kolejność liter w słowie `TRouBLe` – `Top Right Bottom Left`.

### Obramowanie (`border`)

O obramowaniu dowiedzieliśmy się w [rozdziale 8](../../css-code/README.md). Przypomnijmy, że możemy nadawać naszym elementom ramki o różnych stylach.

```html
<div class="box-of-chocolates">
  Tu siedzą czekoladki!
</div>
```

```css
.box-of-chocolates {
  width: 400px;
  height: 200px;
  padding: 30px; /* Dodaję do elmementu wypełnienie o szerokości 30px */
  border: 2px dashed navy; /* Dodaję do elementu przerywaną ramkę o szerokości 2px w kolorze granatowym */
  background-color: lightsalmon;
}
```

<div class="example-wrapper">
  <div style="width: 400px;height: 200px;background-color: lightsalmon;padding: 30px; border: 2px dashed navy;box-sizing: content-box;">
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

Margines jest to odległość między krawędzią (ramką) elementu a innym, sąsiadującym elementem. Marginesy definiujemy podobnie, jak wypełnienie. Możemy użyć również zapisu skrótowego.

```html
<div class="box-of-chocolates">
  Tu siedzą czekoladki!
</div>
```

```css
.box-of-chocolates {
  width: 400px;
  height: 200px;
  padding: 30px; /* Dodaję do elmementu wypełnienie o szerokości 30px */
  border: 2px dashed navy; /* Dodaję do elementu przerywaną ramkę o szerokości 2px w kolorze granatowym */
  margin: 20px; /* Dodaję do elmementu margines o szerokości 20px */
  background-color: lightsalmon;
}
```

<div class="example-wrapper">
  <div style="width: 400px;height: 200px;background-color: lightsalmon;padding: 30px; border: 2px dashed navy;margin: 20px;box-sizing: content-box;">
    Tu siedzą czekoladki!
  </div>
</div>

<a href="http://codepen.io/theawwwesomes/pen/YWENGj" class="codepen-link">Edytuj na CodePen</a>

Co ciekawe, marginesy mogą również przybierać <b>wartości ujemne</b>, w przeciwieństwie do wypełnień i ramek, które to powinny zawsze przyjmować <b>wartości dodatnie</b> (ujemne w tych przypadkach zostaną zignorowane przez przeglądarkę).


To, jak model pudełkowy został wyliczony przez przeglądarkę, możemy podejrzeć w narzędziach deweloperskich w sekcji dotyczącej CSS w zakładce <i>Computed</i> (w Chrome).

![Podgląd modelu pudełkowego w narzędziach deweloperskich][2]

[2]: /images/box-model-devtools.png

### Właściwość `box-model`

Przyjrzyjmy się jeszcze raz stylom dla naszego przykładu:

```css
.box-of-chocolates {
  width: 200px;
  height: 100px;
  padding: 30px; 
  border: 2px dashed navy;
  margin: 20px;
  background-color: lightsalmon;
}
```

Ile miejsca będzie w rzeczywistości zajmował na stronie? W domyślnym przypadku, wyrenderowaną szerokość elementu możemy obliczyć jako:

```css
200px + 2 * 30px + 2 * 2px = 264px /* szerokość zawartości + wypełnienie + ramka */
```

Zatem:

```css
wyrenderowana szerokość = szerokość zawartości zadeklarowana za pomocą width 
  + wypełnienie + ramka
```

Biorąc pod uwagę, że zadeklarowaliśmy `width` na `200px` nie brzmi to intuicyjne, prawda? Chcielibyśmy móc ustalać rzeczywiste wymiary elementu deklarując wprost jego wymiary, nie dokonując w głowie żadnych kalkulacji. Sprawa dodatkowo może się skomplikować, jeśli zdecydowalibyśmy się określić te wymiary na przykład w procentach.

Na szczęście w CSS istnieje możliwość zmiany interpretacji modelu pudełkowego. Służy do tego [właściwość `box-sizing`](https://developer.mozilla.org/en/docs/Web/CSS/box-sizing). Możemy dzięki niej określić, że wartość nadanego przez nas wymiaru będzie równa szerokości/wysokości zawartości zsumowanej z wymiarami wypełnienia i ramki.

W przypadku szerokości będzie to:

```css
wyrenderowana szerokość = szerokość zawartości zadeklarowana za pomocą width 
```

Aby uzyskać taki efekt, należy określić wartość tej właściwości jako `box-sizing: border-box`. 

```css
.box-of-chocolates {
  width: 200px;
  height: 100px;
  padding: 30px; 
  border: 2px dashed navy;
  margin: 20px;
  background-color: lightsalmon;
}

.border-box {
  box-sizing: border-box;
}
```

```html
<div class="box-of-chocolates">
  Tu siedzą czekoladki!
</div>

<div class="box-of-chocolates border-box">
  Tu siedzą czekoladki!
</div>
```

<div class="example-wrapper">
  <div style="width: 400px;height: 200px;background-color: lightsalmon;padding: 30px; border: 2px dashed navy;margin: 20px;box-sizing: content-box;">
    Tu siedzą czekoladki!
  </div>
  <div style="width: 400px;height: 200px;background-color: lightsalmon;padding: 30px; border: 2px dashed navy;margin: 20px;box-sizing: border-box;">
    Tu siedzą czekoladki!
  </div>
</div>

<a href="http://codepen.io/theawwwesomes/pen/XKzpNr" class="codepen-link">Edytuj na CodePen</a>


Obecnie taką interpretację modelu pudełkowego przyjmuje się to jako <b>standard</b>. Najlepiej zrobić to od razu dla wszystkich elementów na stronie. Aby to się udało, musimy umieścić <b>na początku</b> naszego arkusza stylów taki kod:

```css
*, *::before, *::after {
  box-sizing: border-box;
}
```

`*` to nic innego jak <i>uniwersalny selektor</i>, który nadaje podane właściwości dosłownie <b>wszystkim</b> elementom naszej strony. Selektorami `::before` oraz `::after` nie musicie się teraz przejmować, wrócimy do nich [za chwilę](../../css-advanced-selectors/css-pseudoelements/README.md).

Nieco więcej o `box-sizing` możecie doczytać w [artykule na CSS-Tricks](https://css-tricks.com/box-sizing/).
