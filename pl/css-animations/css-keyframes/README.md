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

Animacje CSS posiadają jeszcze inne parametry. Poznajmy te najczęściej używane:
- `animation-name` - nazwa animacji
- `animation-duration` - czas trwania animacji
- `animation-timing-function`
- `animation-delay` - opóźnienie, czyli czas po jakim animacja zacznie działać
- `animation-direction` - kierunek rozpoczęcia i powtarzania się animacji, więcej o tej właściwości poniżej
- `animation-iteration-count` - liczba powtórzeń (iteracji) animacji
- `animation-fill-mode` - określa jakie cechy będzie miał animowany obiekty, gdy jego animacja będzie gdy animacja się zakończy i nie będzie powtarzana.
- `animation-play-state`- zatrzymywanie bądź wznowienie animacji, dozwolone wartości to `paused` (zatrzymana) i `running` (w toku)

## Kierunek animacji, czyli `animation-direction`
- `alternate` - animacja będzie powtarzać się w odwrotnym kierunku niż przy rozpoczęciu

<div class="circle-ch-anim" style="animation-direction: alternate;"></div>

- `reverse` - animacja rozpoczynać się od miejsca, w którym się zakończyła

<div class="circle-ch-anim" style="animation-direction: reverse;"></div>

- `alternate-reverse` - animacja będzie powtarzana od końca i zostanie powtarzana w w miejscu, w którym się zakonczyła

<div class="circle-ch-anim" style="animation-direction: alternate-reverse;"></div>

- `normal` animacja będzie rozpoczynała się od początku, w miejscu, w którym pierwotnie zaczęła

<div class="circle-ch-anim" style="animation-direction: normal;"></div>


## Skrótowy zapis
Tak samo jak do `transition`, do animacji również możemy zastosować skrót właściwości. 
Zamiast pisać wypisywać oddzielnie kolejne właściwości, możemy wymienić je w jednej linii.
`animation: 3s ease-in 1s 2 reverse both paused changeColors;`

Skrót ten tworzymy według wzorca:
`animation: duration | timing-function | delay | iteration-count | direction | fill-mode | play-state | name`, 
podając przy tym odpowiednie wartości.

