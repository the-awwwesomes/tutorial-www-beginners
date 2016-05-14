# Tworzenie layoutu strony

Po przeczytaniu poprzednich rozdziałów zapewne głowy pękają Wam od teorii. Jeśli udało się Wam przez to wszystko przebrnąć - jesteśmy z Was bardzo dumni! I zapraszamy w podróż do świata layoutu stron internetowych. Tutaj również można zagubić się w gąszczu różnych zagadnień, jednak każde z nich jest bardzo ważne i potrzebne w codziennej pracy frontendowca. Gotowi?

## Elementy liniowe i blokowe oraz właściwość `display`

W poprzednich rozdziałach poznaliście dwa generyczne tagi HTML: `<div>` oraz `<span>`. Zapewne udało się Wam już użyć ich w swoim kodzie. Skąd wzięła się potrzeba wprowadzania aż dwóch rodzajów domyślnych znaczników? Zostało to już krótko wspomniane - `<div>` odnosi się do elementów, które mają być wyświetlane jako **blokowe**, natomiast `<span>` zwykle jest używany dla elementów **liniowych**.

### Elementy blokowe

Elementy blokowe to elementy, które mają  być wyświetlane jako **bloki**. 

- Jeśli nie określimy jego szerokości wprost, każdy blok domyślnie będzie zajmował 100% szerokości swojego rodzica.
- Możemy określić jego marginesy oraz wypełnienie (padding).
- Każdy element blokowy umieszczany jest pod poprzedzającym elementem, a element następny w kolejności również umieszczany jest pod spodem. Przypomina to złamanie linii w tekście.

```html
<div class="container">
  <div class="block"></div>
  <div class="block"></div>
  <div class="block"></div>
</div>
```

```css
.block {
  width: 200px;
  height: 100px;
  margin: 10px;
  padding: 5px;
  background: salmon;
}
```

<div class="example-wrapper">
  <div class="container">
    <div style="width: 200px;height: 100px;margin: 10px;padding: 5px;background: salmon;"></div>
    <div style="width: 200px;height: 100px;margin: 10px;padding: 5px;background: salmon;"></div>
    <div style="width: 200px;height: 100px;margin: 10px;padding: 5px;background: salmon;"></div>
  </div>
</div>

Przykładami elementów HTML, które przez przeglądarkę są domyślnie wyświetlane jako blokowe to wspomniany już `<div>`, `<p>`, `<header>`, `<section>`, `<nav>`, `<footer>`, `<article>`, `<form>`, `<ul>`, `<ol>` oraz nagłówki, np. `<h1>`.

### Elementy liniowe

Elementy liniowe to takie, które zachowują się jak linie tekstu, czyli innymi słowy "płyną" razem z tekstem.

- Nie można określić im wymiarów za pomocą właściwości `width` i `height`.
- Nie można nadwać im górnych (`margin-top`), ani dolnych (`margin-bottom`) marginesów. Nadanie `margin-left` lub `margin-right` oraz wypełnień jednak w ich przypadku zadziała.
- Biorąc pod uwagę, że elementy liniowe zachowują się podobnie, jak linie tekstu, można określać ich wyrównanie w pionie za pomocą właściwości `vertical-align`. Zachowanie [`vertical-align`](https://developer.mozilla.org/en/docs/Web/CSS/vertical-align) zostało bardzo przejrzyście wytłumaczone w [tym artykule](https://bitsofco.de/the-vertical-align-property/).

```html
<p>
  Hipster cornhole celiac kickstarter asymmetrical cred meggings. 
  Retro pitchfork semiotics you 
  <span class="inline">probably haven't heard of them</span>, 
  thundercats occupy raw denim DIY.
</p>
```

```css
.inline {
  padding: 5px;
  vertical-align: super;
  color: lightblue;
}
```

<div class="example-wrapper">
  <p>Hipster cornhole celiac kickstarter asymmetrical cred meggings. Retro pitchfork semiotics you <span style="padding: 5px;vertical-align:super;color: lightblue;">probably haven't heard of them</span>, thundercats occupy raw denim DIY.</p>
</div>

Przykładowe elementy liniowe, które już udało nam się poznać to `<span>` oraz `<a>`.

Warto w tym momencie wspomnieć, że istnieją elementy, których domyślne zachowanie nieco różni się od blokowych i liniowych - można powiedzieć, że łączą w sobie rózne ich cechy. Są to tzw. [*replaced elements*](http://www.impressivewebs.com/difference-block-inline-css/). Należą do nich m.in. `<img>`, `<input>` oraz `<select>`. Można określać ich wymiary za pomocą właściwości CSS, jednak w przeciwieństwie do elementów blokowych za żadnym z nich nie następuje złamanie linii. Zauważyliście to z pewnością podczas tworzenia formularzy w czystym HTML.

### Określamy zachowanie elementów za pomocą właściwości `display`

Każdy z elementów HTML posiada swój domyślny rodzaj zachowania, jednak można w bardzo łatwy sposób go zmienić i sprawić, żeby np. `<div>` zaczął zachowywać się jak element liniowy.

Jak to zrobić? Poznajmy właściwość `display`, która odpowiada za określanie rodzaju sposobu wyświetlania elementu na stronie. Wartości właściwości display jest [bardzo dużo](https://developer.mozilla.org/en-US/docs/Web/CSS/display) i sporo z nich brzmi tajemniczo nawet dla całkiem zaawansowanych deweloperów CSS.

Poznajmy trzy używane zdecydowanie najczęściej:

- `display: inline` - sprawia, że element będzie wyświetlany jako element liniowy
- `display: block` - element zostanie wyświetlony jako element blokowy
- `display: inline-block` - łączy cechy elementów liniowych i blokowych, za jego pomocą możemy sprawić, że będzie możliwe nadanie naszemu elementowi wymiarów i wszystkich marginesów, a także nie nastąpi po nim przejście do kolejnej linii.

```html
<div class="container">
  <div class="inline-block-item"></div>
  <span class="inline-block-item"></span>
  <p class="inline-block-item"></p>
</div>
```

```css
.inline-block-item {
  display: inline-block;
  width: 150px;
  height: 150px;
  margin: 5px 10px 6px 12px;
  background-color: lightblue;
}
```

<div class="example-wrapper">
  <div style="display:inline-block;width:150px;height:150px;margin:5px 10px 6px 12px;background-color:lightblue"></div>
  <span style="display:inline-block;width:150px;height:150px;margin:5px 10px 6px 12px;background-color:lightblue"></span>
  <p style="display:inline-block;width:150px;height:150px;margin: 5px 10px 6px 12px;background-color:lightblue"></p>
</div>

Poniżej podsumowujemy w tabeli cechy elementów liniowych, blokowych oraz liniowo-blokowych:

|  | Prawe i lewe marginesy | Górne i dolne marginesy | Możliwość ustawienia `width` i `height` | Wymuszenie złamania linii za elementem | `vertical-align` |
| -------------- |:---:| :---:| :---:| :---:| :---:|
| `inline`       | ✔ | ✘ | ✘ | ✘ | ✔ |
| `block`        | ✔ | ✔ | ✔ | ✔ | ✘ |
| `inline-block` | ✔ | ✔ | ✔ | ✘ | ✔ |

## Opływanie

Kolejną właściwością, która pomaga nam w budowaniu layoutów jest `float`, który definiuje **opływanie** elementów.

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
    <img src="../images/float-latte.jpg" alt="cup of latte" style="float:left">
    Cred paleo whatever, portland distillery microdosing pabst. Salvia seitan cardigan kinfolk yuccie, chia umami viral blog. Waistcoat tilde next level, tote bag stumptown four loko franzen. Small batch vice swag, offal chia kickstarter helvetica pitchfork. 
    <img src="../images/float-bicycle.jpg" alt="hipster bicycle" style="float:right">
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
> Nasz ostatni element otrzymał właściwość `clear: both`, co oznacza, że zamiast opływać sąsiadujące elementy - i zostać umieszczony w tym samym rzędzie, co zielone kwadraty - pojawił się w następnej linii.
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
> Niestety, nie jest to wcale idealne rozwiązanie. Nie chcemy w końcu zaśmiecać naszej strony pustymi elementami użytymi tylko ze względu na wygląd. Istnieje nieco lepszy sposób oparty na *pseudo-elementach* (co to takiego, dowiemy się już niebawem) - tzw. [*micro-clearfix*](http://nicolasgallagher.com/micro-clearfix-hack/).

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
}

.clear {
  clear: both;
}
```

<div class="example-wrapper">
  <div style="border: 5px solid lightgreen;padding: 15px;">
    <img src="../images/float-hipster.jpg" alt="random hipster" style="float:left;margin-right:15px;">
    <h1>Rafael Williamson</h1>
    <p>Vinyl fanny pack cardigan tousled umami slow-carb meh. Kinfolk post-ironic synth DIY heirloom, vegan schlitz.</p>
    <div style="clear:both"></div>
  </div>
</div>


## Umieszczanie elementów na siatce

## Pozycjonujemy elementy na stronie

## Jak wycentrować elementy w pionie i poziomie?

### Flexbox

