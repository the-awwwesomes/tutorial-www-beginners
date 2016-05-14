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

## Umieszczanie elementów na siatce

## Pozycjonujemy elementy na stronie

## Jak wycentrować elementy w pionie i poziomie?

### Flexbox

