# Zaawansowane selektory CSS

Umiecie już korzystać z większości dostępnych rodzajów selektorów CSS i to w zasadzie wystarcza do zakodowania prostej strony internetowej. Czasem jednak zdarza się, że potrzeba użyć triku, aby zakodować ciekawy efekt albo po prostu poprawić jakość interakcji użytkownika ze stroną.

Zapoznajmy się zatem z selektorami do zadań specjalnych. 

## Selektor dziecka

Spotkaliście się już z selektorem, który wskazywał na wszystkie elementy danego rodzaju będące potomkami danego elementu. Na przykład:

```css
ul li {
  color: rgb(134, 134, 134);
  padding: 1rem 0;
}
```

Taki rodzaj selektora nazywamy selektorem potomka (ponieważ wskazuje na elementy będące w relacji nie tylko dziecka, ale też "wnuka", "prawnuka" i tak dalej).

W niektórych przypadkach może on się okazać zbyt ogólny, ponieważ chcemy wskazać na elementy, które następują wyłącznie *bezpośrednio* wewnątrz nadrzędnego elementu.

```html
<label>Lista zakupów:</label>
<ul class="shopping-list">
  <li>
    Jedzenie i picie:
    <ul>
      <li>Woda niegazowana</li>
      <li>Ser żółty</li>
      <li>Mleko</li>
    </ul>
  </li>
  <li>
    Kosmetyki i chemia domowa:
    <ul>
      <li>Szampon do włosów</li>
      <li>Proszek do prania</li>
      <li>Płyn do mycia naczyń</li>
    </ul>
  </li>
  <li>
    Dom i ogród:
    <ul>
      <li>Biała farba emulsyjna</li>
      <li>Nawóz do trawnika</li>
      <li>Kosiarka spalinowa</li>
    </ul>
  </li>
  <li>
    Ubrania:
    <ul>
      <li>Biały t-shirt</li>
      <li>Dżinsy</li>
      <li>Czarne skarpetki (3 pary)</li>
    </ul>
  </li>
</ul>
```

```css
.shopping-list > li {
  padding: 1rem 0;
  color: dodgerblue;
}
```

<div class="example-wrapper">
<label>Lista zakupów:</label>
<ul class="shopping-list">
  <li style="padding:1rem 0;color:dodgerblue;">
    Jedzenie i picie:
    <ul>
      <li>Woda niegazowana</li>
      <li>Ser żółty</li>
      <li>Mleko</li>
    </ul>
  </li>
  <li style="padding:1rem 0;color:dodgerblue;">
    Kosmetyki i chemia domowa:
    <ul>
      <li>Szampon do włosów</li>
      <li>Proszek do prania</li>
      <li>Płyn do mycia naczyń</li>
    </ul>
  </li>
  <li style="padding:1rem 0;color:dodgerblue;">
    Dom i ogród:
    <ul>
      <li>Biała farba emulsyjna</li>
      <li>Nawóz do trawnika</li>
      <li>Kosiarka spalinowa</li>
    </ul>
  </li>
  <li style="padding:1rem 0;color:dodgerblue;">
    Ubrania:
    <ul>
      <li>Biały t-shirt</li>
      <li>Dżinsy</li>
      <li>Czarne skarpetki (3 pary)</li>
    </ul>
  </li>
</ul>
</div>

Zatem wstawienie znaku `>` w miejsce spacji oznacza, że tylko elementy bezpośrednio następujące po elemencie nadrzędnym będą brane pod uwagę.

## Selektory braci

Oprócz relacji, w której selektor wskazuje na elementy znajdujące się jeden wewnątrz drugiego, CSS pozwala na wybieranie elementów następujących obok siebie. Możemy wybierać tylko jeden element, następujący bezpośrednio po wskazanym albo wszystkie kolejne.

```html
<ul>
  <li>Jabłka</li>
  <li class="select-my-first-sibling">Banany</li>
  <li>Śliwki</li>
  <li>Pomarańcze</li>
  <li>Mango</li>
</ul>

<ul>
  <li>Pietruszka</li>
  <li class="select-all-my-siblings">Seler</li>
  <li>Por</li>
  <li>Marchew</li>
  <li>Cebula</li>
</ul>
```

```css
/*
  Wybierz jeden element
  następujący bezpośrednio
  po elemencie z klasą
  `.select-my-first-sibling`
*/
.select-my-first-sibling + li {
  color: mediumvioletred;
}

/*
  Wybierz wszystkie elementy 
  następujące po elemencie
  z klasą `.select-all-my-siblings`
*/
.select-all-my-siblings ~ li {
  color: seagreen;
}
```

<div class="example-wrapper">
  <ul>
    <li>Jabłka</li>
    <li>Banany</li>
    <li style="color:mediumvioletred;">Śliwki</li>
    <li>Pomarańcze</li>
    <li>Mango</li>
  </ul>

  <ul>
    <li>Pietruszka</li>
    <li>Seler</li>
    <li style="color:seagreen;">Por</li>
    <li style="color:seagreen;">Marchew</li>
    <li style="color:seagreen;">Cebula</li>
  </ul>
</div>
