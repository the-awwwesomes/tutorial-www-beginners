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

### Określamy zachowanie elementów za pomocą właściwości `display`

## Opływanie

## Umieszczanie elementów na siatce

## Pozycjonujemy elementy na stronie

## Jak wycentrować elementy w pionie i poziomie?

### Flexbox

