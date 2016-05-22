## Pseudoklasy CSS

Czy wiecie, że możecie tworzyć interaktywne efekty za pomocą CSS? Poznajcie **pseudoklasy**! Można je rozpoznać po charakterystycznym dwukropku przed nazwą - `:`.

```css
selektor:pseudoklasa {
  właściwość: wartość;
}
```

Pseudoklasy zazwyczaj dotyczą **stanu** w jakim może znajdować się dany element. Przykładowo, w przypadku linków mogą to być:

```css
/*
  Link odwiedzony przez użytkownika
*/
a:visited {
  color: purple;
}

/*
  Link, nad którym znajduje się kursor myszy
*/
a:hover {
  color: red;
}

/*
  Link, na którym jest ustawiony fokus
  (np. za pomocą klawiatury)
*/
a:focus {
  color: navy;
}

/*
  Link, który w danym momencie jest aktywny
*/
a:active {
  color: green;
}
```

```html
<a href="http://theawwwesomes.org">Hej! Jestem linkiem!</a>
```

<div class="example-wrapper" id="awww-pseudoclasses-exercise">
  <a href="http://theawwwesomes.org">Hej! Jestem linkiem!</a>
</div>

Kiedy na przykład najedziemy kursorem myszy na nasz element, zmieni on swój kolor na czerwony. 

Różne pseudoklasy możemy aplikować dla różnych elementów, w zależności od ich własności.

```css
/*
  Wyszarzenie przycisku,
  którego działanie blokujemy
  dla użytkownika
*/
button:disabled {
  border: 1px solid gray;
  color: rgb(133, 133, 133);
  background-color: rgba(198, 198, 198, 0.8);
}

/*
  Nadanie tła etykietom,
  wewnątrz których checkboksy
  zostały zaznaczone
*/
label > input[type="checkbox"]:checked {
  background: lightblue;
}
```

Ciekawymi typami pseudoklas są `:first-child`, `:last-child` oraz `:nth-child()`. Zapewne domyślacie się już, że pomagają nam one wybrać elementy w zależności od tego, w którym miejscu występują wobec nadrzędnego elementu. Zaprezentujmy działanie powyższych selektorów na przykładzie... listy zakupów!

```html
<label>Do kupienia:</label>
<ul class="shopping-list">
  <li>Cukier</li>
  <li>Mąka</li>
  <li>Makaron</li>
  <li>Chleb razowy</li>
  <li>Jajka</li>
  <li>Jogurt naturalny</li>
  <li>Pomidory</li>
</ul>
```

```css
/*
  Wskaż pierwszy element listy
*/
.shopping-list li:first-child {
  font-weight: bold;
}

/*
  Wskaż ostatni element listy
*/
.shopping-list li:last-child {
  text-decoration: line-through;
}

/*
  Wskaż trzeci element listy
*/
.shopping-list li:nth-child(3) {
  color: deeppink;
}
```

<div class="example-wrapper">
<label>Do kupienia:</label>
<ul class="shopping-list">
  <li style="font-weight:bold">Cukier</li>
  <li>Mąka</li>
  <li style="color:deeppink">Makaron</li>
  <li>Chleb razowy</li>
  <li>Jajka</li>
  <li>Jogurt naturalny</li>
  <li style="text-decoration:line-through">Pomidory</li>
</ul>
</div>

Pseudoselektor `:first-child` pozwala nam na wskazanie pierwszego elementu na liście, `:last-child` natomiast ostatniego. `:nth-child()` jest nieco bardziej uniwersalny, ponieważ wewnątrz nawiasów `()` możemy podać dowolną liczbę naturalną a także warunek, który powinien spełniać element. Przykładowo `:nth-child(2n)` wskaże wszystkie elementy zajmujące parzyste pozycje na liście, a `nth-child(2n + 1)` - nieparzyste.

Pełną listę dostępnych pseudoklas (a jest ona całkiem długa!) możecie znaleźć [tutaj](https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-classes).