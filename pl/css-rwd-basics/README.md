# Podstawy kodowania responsywnych stron

W dzisiejszych czasach przeglądamy internet nie tylko siedząc w domu przed biurkiem, ale też korzystając ze smartfona jadąc autobusem, spoglądając na smartwatcha albo przesuwając palcem po tablecie. Mnogość typów urządzeń, ich rozdzielczości wydaje się oszałamiająca i sprawia wrażenie, że zaprojektowanie i zakodowanie strony, która będzie się na każdym prawidłowo wyświetlać, wydaje się niewykonalne.

Bardzo ważne jest zatem, aby już na etapie projektowania, a także później kodowania, zadbać o to, aby strona była responsywna. Termin <i>Responsive Web Design</i> [istnieje w obiegu już od 2010 roku](http://alistapart.com/article/responsive-web-design). Od tamtej pory zgromadzono całkiem spory zasób wiedzy na temat tego, jak dostosowywać strony do wyświetlania za pomocą różnych mediów.

Niestety, wyjaśnienie wszystkiego dogłębnie spowodowałoby, że objętość tego tutoriala podwoiłaby się, a wraz z nią i czas trwania naszego kursu. Zapoznajmy się zatem z podstawami kodowania responsywnych stron i dowiedzmy się, czym są <i>media queries</i>.

## Zanim zaczniesz pisać kod CSS

Upewnij się, że w nagłówku pliku HTML (`<head>`) znajduje się poniższy kod:

```html
<meta name="viewport" content="width=device-width, initial-scale=1">
```

Właściwość `width` określa domyślną szerokość strony. Moglibyśmy wstępnie ustawić ją w pikselach, np. `width=800`, jednak jak można się domyślić nie prezentowałaby się najlepiej na urządzeniach o szerokości ekranu różnej od 800 pikseli. Wartość `device-width` oznacza tyle, że szerokość naszej strony ma dostosować się do szerokości wyświetlacza.

Właściwość `initial-scale=1` mówi przeglądarce, że tuż po załadowaniu strona powinna pokazać się bez powiększenia (<i>zoom</i>), w swojej naturalnej wielkości.

## Kontrolowanie responsywnego layoutu za pomocą CSS

Po zapoznaniu się z siatką zapewne zaczęliście się zastanawiać, jak to się dzieje, że elementy siatki mogą przyjmować różne szerokości dla różnych szerokości ekranu. Niektórzy z Was pewnie zajrzeli do kodu źródłowego i dostrzegli zagadkowe `@media`.

Reguła `@media` umożliwia nam serwowanie różnych wartości stylów w zależności od medium, na jakim wyświetlana jest strona. Możemy zastosować tę regułę również dla wydruku strony, ale nie tylko – [lista typów i właściwości mediów jest całkiem długa](https://developer.mozilla.org/en-US/docs/Web/CSS/@media).

```css
/*
  Style działające dla szerokości
  ekranu mniejszej od 768px
*/
@media screen and (max-width: 768px) {
 .class { ... }
}

/*
  Style działające dla szerokości
  ekranu większej od 60em
*/
@media screen and (min-width: 60em) {
 .class1 { ... }
}

/*
  Style dla ekranu pracującego w trybie
  `landscape` i jednocześnie o podwójnej
  gęstości pikseli (ta gęstość pikseli jest
  charakterystyczna dla wyświetlaczy Retina)
*/
@media screen and (orientation: landscape) and (-webkit-min-device-pixel-ratio: 2) {
 .class2 { ... }
}

/*
  Style dla wydruku strony
*/
@media print {
  .class3 { ... }
}
```

Istotne jest, aby wewnątrz nawiasów `@media { }` zawrzeć nie tylko same właściwości, ale całe deklaracje stylów, łącznie z selektorami.

```css
/*
  Style dla elementów z klasą `.example`
  dostępne globalnie
*/
.example {
  color: deeppink;
}

@media screen and (min-width: 996px) {
  /*
    Style dla elementów z klasą `.example`
    działające tylko w przypadku, kiedy
    ekran ma szerokość większą niż 996px
  */
  .example {
    color: black;
  }
}
```

W projektowaniu stron dość popularne jest podejście <i>mobile first</i>, czyli skupienie się w pierwszej kolejności na layoucie dla małych ekranów mobilnych urządzeń. Małe ekrany oznaczają mniej dostępnej przestrzeni i jednocześnie więcej ograniczeń dla projektanta lub programisty stron.

W kodzie CSS oznacza to zaczęcie kodowania globalnych stylów od tych, które będą działać dla urządzeń o małych ekranach i zawężanie zakresu stylów potrzebnych dla urządzeń o większych ekranach za pomocą <i>media query</i> z `min-width`.
W praktyce często oznacza to mniej napisanego kodu.

```css
.mobile-first-component {
  width: 100%;
}

@media screen and (min-width: 992px) {
   .mobile-first-component {
      width: 50%;
   }
}

@media screen and (min-width: 1200px) {
   .mobile-first-component {
      width: 33%;
   }
}
```
