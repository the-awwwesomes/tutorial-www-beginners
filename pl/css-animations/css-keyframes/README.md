# Tworzenie animacji - `@keyframes`

Tworzenie animacji następuje przez regułę `@keyframes`. Zobaczmy jak wygląda przykładowa animacja.
```css
@keyframes changeColors
{
  0% { background-color: salmon; }
  50% { background-color: #263479; }
  100% { background-color: salmon; }
}
```

`changeColors` to nazwa animacji, którą nadajemy sami. Nastepuje zawsze po deklaracji `@keyframes `.
W środku animacji, pomiędzy nawiasami klamrowymi definiujemy co będzie działo się w danych przedziałach czasowych animacji. W przypadku CSS przypisuje się to postępowi animacji, wyrażonemu w procentach, gdzie `0%` to początek animacji, zaś `100%` to jej koniec.

Animacja `changeColors` będzie zatem zmieniać kolory tła przycisku z pomarańczowego na granatowy, i na odwrót.

<a href="" class="awww-exercise-link added-transition" style="background-color: salmon; animation-name: changeColors; animation-duration: 5s; padding: 10px 120px; margin: 20px 0;  color: #fff;">to jest link</a>

Animację dodajemy do wybranego selektora lub selektorów CSS. 
Jak to się robi?Zerknijmy na kod odpowiedzialny za link.

```html
<a href="" class="link">to jest link</a>
```

```css
a.link {
	padding: 10px 120px;
	background-color: salmon;
	color: #fff;
	animation-name: changeColors; 
	animation-duration: 5s;
}
```
Dodaliśmy dwie nowe właściwości: `animation-name`, której wartością jest nazwa naszej animacji (`changeColors`) oraz `animation-duration`, czyli dowolny czas trwania animacji.
Dzięki tym dwóm właściwościom dodaliśmy do naszego linku z klasą `link` stworzoną przez nas animację.

Animacje CSS posiadają jeszcze inne parametry.

