# Właściwość `transition`

W CSS możemy wykorzystać poznane we wcześniejszym rozdziale pseudoklasy do wywoływania zmiany stanu. Brzmi enigmatycznie, ale zerknijcie na przykład poniżej.

<div class="awww-ch-animations-exercise">
	<a href="" class="awww-exercise-link">to jest link</a>
</div>

```html
<a href="" class="link">to jest link</a>
```

```css
a.link {
	padding: 10px 20px;
	background-color: salmon;
	color: #fff;
}

a.link:hover {
	background-color: #1F2B6C;
}
```

Zauważyć możemy zmianę koloru tła linku po najechaniu na niego kursorem. Zawdzięczamy to pseudoklasie `:hover`. Zmiana koloru jest nagła. Możemy nadać jej bardziej 'delikatnego', stopniowego charakteru, dodając właściwość `transition`, czyli płynnego przejścia w czasie między stanami zdefiniowanymi w CSS.
Najedź kursorem na poniższy link. Czy widzisz różnicę?

<div class="awww-ch-animations-exercise">
<a href="" class="awww-exercise-link added-transition" style="transition: all .7s ease-in-out;">to jest link</a>
</div>

```html
<a href="" class="link">to jest link</a>
```

```css
a.link {
	padding: 10px 20px;
	background-color: salmon;
	color: #fff;
	transition: all 0.7s ease-in-out; /*dodanie funkcji przejścia*/
}

a.link:hover {
	background-color: #1F2B6C;
}
```

Sprawdźmy teraz, z czego składa się funkcja `transition`. Zapis `transition: all 0.7s ease-in-out` jest zapisem skrótowym. Rozłóżmy go na czynniki pierwsze:

```css
    transition-property: all;
    transition-duration: 0.7s;
	transition-timing-function: ease-in-out;

```
- `transition-property` określa nam, na które właściwości CSS wpłynie funkcja przejścia. Wartość `all` odpowiada za wszystkie właściwości. Jeśli chcielibyśmy animować tylko kolor tekstu, to wpisalibyśmy `color`, jeśli tło to `background-color` itd.

```css
	transition-property: color;
	transition-property: background-color;
	transition-property: border;

```

- `transition-duration`, czyli czas trwania przejścia. Im dłuższy, tym bardziej subtelna będzie animacja. Pamiętajmy o dodawaniu jednostek – sekund (`s`) lub milisekund (`ms`).

- `transition-timing-function`, czyli sposób, w jaki przejście będzie zachodzić. Opisuje to funkcja czasu. W CSS występuje kilka ich predefiniowanych rodzajów:

```css
	transition-timing-function: linear; /* zmiana następuje wg funkcji liniowej */
	transition-timing-function: ease;   /* zmiana następuje wg funkcji liniowej */
	transition-timing-function: ease-in; /* animacja na początku ma wolniejsze tempo, i przyspiesza na końcu */
	transition-timing-function: ease-out;  /* animacja na początku ma szybsze tempo, i zwalnia na końcu */
	transition-timing-function: ease-out;  /* animacja na początku ma szybsze tempo, i zwalnia na końcu */
	transition-timing-function: cubic-bezier(); /* przejście następuje wg zadanej fukcji Beziera */

```
Jak działają podstawowe funkcje i funkcje Beziera na animowanych elementach, możesz <a href="http://cubic-bezier.com/" target="_blank">zobaczyć na stronie cubic-bezier.com</a>.

Występuje jeszcze jeden parametr:
- `transition-delay` – czyli opóźnienie danego przejścia, również podajemy go w jednostkach czasowych.

Pełny zapis funkcji transition wygląda następująco:
`transition : <transition-property> || <transition-duration> || <transition-timing-function> || <transition-delay>`

Tutaj przykład animacji z zastosowanym opóźnieniem (`transition-delay`):
`transition: all 0.7s ease-in-out 0.7s;`

<div class="awww-ch-animations-exercise">
<a href="" class="awww-exercise-link added-transition" style="transition: all 0.7s ease-in-out 0.7s;">to jest link</a>
</div>

> #### Exercise::Ćwiczenie 13
>
>Pora na ożywienie linków na stronie. Niech każdy link z nawigacji po najechaniu kursorem zmieni kolor. Wykorzystaj funkcję `transition` z dobranymi przez Ciebie parametrami czasu.
>
> Zmień kolor tła przycisków po najechaniu kursorem, tak aby osiągnąć podobny do poniższego efekt:
>
>![Animacja][2]
[2]: /images/button-animation.gif
