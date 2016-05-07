# Model pudełkowy CSS

*"Życie jest jak pudełko czekoladek - nigdy nie wiesz, co Ci się trafi"* - powiedział kiedyś Forest Gump. Z pisaniem kodu CSS może być podobnie - nigdy nie wiadomo, co się trafi, jeśli nie zna się reguł nim rządzących. Dowiedzieliśmy się właśnie, w jaki sposób przeglądarka decyduje, jakie style nadawać elementom HTML. Kolejnym stopniem wtajemniczenia kodera WWW jest zaznajomienie się z zasadami, w jaki sposób owe elementy są wyświetlane i rozmieszczane na stronie. Tutaj bowiem kryje się najwięcej zabawy!

Na początku tej przygody warto zawrzeć bliską znajomość z **modelem pudełkowym**. Model pudełkowy pozwala nam precyzyjnie określić wymiary elementu HTML na stronie. Każdy z elementów na stronie można bowiem potraktować jako prostokąt o określonych wymiarach, który może posiadać wypełnienie (*padding*), obramowanie (*border*) oraz margines (*margin*). 

### Wymiary elementu

Elementom HTML możemy nadawać wysokość i szerokość za pomocą właściwości `height` oraz `width`.

```html
<div class="box-of-chocolates">
  Jestem przykładowym elementem.
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
    Jestem przykładowym elementem.
  </div>
</div>

### Wypełnienie (`padding`)

Widzicie pewnie, że w naszym powyższym przykładzie tekst przylega do krawędzi elementu. Nie wygląda to zbyt estetycznie. W CSS istnieje możliwość zdefiniowania wypełnienia elementu. Nie jest to nic innego jak odległość od zawartości do krawędzi elementu. Wypełnienie definiujemy w poniższy sposób:

```html
<div class="box-of-chocolates">
  Jestem przykładowym elementem.
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
    Jestem przykładowym elementem.
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
  Jestem przykładowym elementem.
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
    Jestem przykładowym elementem.
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
  Jestem przykładowym elementem.
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
    Jestem przykładowym elementem.
  </div>
</div>

Co ciekawe, marginesy mogą również przybierać wartości **ujemne**, w przeciwieństwie do wypełnień i ramek, które to powinny zawsze przyjmować wartości dodatnie (ujemne w tych przypadkach zostaną zignorowane przez przeglądarkę).

To, jak model pudełkowy został wyliczony przez przeglądarkę, możemy podejrzeć w narzędziach deweloperskich w sekcji dotyczącej CSS w zakładce *Computed* (dla Chrome).

![Podgląd modelu pudełkowego w narzędziach deweloperskich][2]

[2]: /images/box-model-devtools.png

## Jednostki w CSS