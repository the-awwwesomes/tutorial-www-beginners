# Przekształcanie `transform`

Dzięki właściwości `transform` możemy przekształcić nasze obiekty w różny sposób. Zajmiemy się przypadkami w przestrzeni 2D. Możliwe operacje to skalowanie (zwiększanie, zmniejszanie), przesuwanie po osi X i po osi Y, obrót oraz pochylenie.

## Przesuwanie
### Przesuwanie wzdłuż osi X
Przesuwanie wzdłuż osi X, czyli w prawo lub w lewo, to właściwość `translateX(wartość)`.
W poniższym przykładzie element zostanie przesunięty o 150px w prawo.
```css
	transform: translateX(150px);
```

Spróbujmy do naszej wartości dodać znak `-`. W wyniku poniższej deklaracji element zostanie przesunięty o 150px w lewo.
```css
	transform: translateX(-150px);
```

### Przesuwanie wzdłuż osi Y
Przesuwanie wzdłuż osi Y, czyli w górę lub w dół, to właściwość `translateY(wartość)`.
W poniższym przykładzie element zostanie przesunięty w górę o 150px.
```css
	transform: translateY(150px);
```

Zaś w tym przykładzie, element przesunięty zostanie 150px w dół, gdyż przed wartością pojawił się znak `-`.
```css
	transform: translateY(-150px);
```

## Obracanie
Dowolne elementy możemy obracać przy wykorzystaniu właściwości `rotate(wartość)`. Wartość podawana jest w stopniach (`deg`).

Zobaczmy, co stanie się z kwadratem, do którego przypiszemy poniższą właściwość:
```css
	transform: rotate(45deg);
```
Jak widać, element został obrócony o 45 stopni.

<div class="rectangle-ch-anim"></div>

<div class="rectangle-ch-anim" style="transform: rotate(45deg);"></div>

Obroty mogą być dokonywane według trzech osi: X, Y i Z.
```css
	rotateX(45deg);
	rotateY(45deg);
	rotateZ(45deg);
```

## Skalowanie
Wybrany element możemy powiększać lub pomniejszać podając odpowiednie wartości we właściwości
```css
	transform: scale(wartość);
```
Wartości poniżej 1 będą pomniejszać element, zaś powyżej 1 – powiększać nasz obiekt.
Obiekty od lewej posiadają wartości `scale(0.8)`, `scale(1)` i `scale(1.2)`.

<div class="rectangle-ch-anim" style="transform: scale(0.8); background-color: #FF9F94;"></div>
<div class="rectangle-ch-anim" style="transform: scale(1.0);"></div>
<div class="rectangle-ch-anim" style="transform: scale(1.2); background-color: #F96655;"></div>

### Skalowanie na `:hover`

Przy zastosowaniu pseudoklasy `:hover` możemy tworzyć ciekawe efekty związane ze skalowaniem.
<div class="container-button-ch-anim"><div class="button-ch-anim-scale" style=" transition: all 0.7s ease-in-out;">kliknij!</div></div>

```css
.button-ch-anim-scale {
    background-color: salmon;
    padding: 20px 100px;
    display: inline-block;
    margin: 20px 0;
    transition: all 0.3 ease-in-out;
}

.button-ch-anim-scale:hover {
    transform: scale(1.2);  
}
```
### Skalowanie na osi X i Y
Skalowanie może się też odbywać tylko na wybranej osi. Służą do tego właściwości:

`transform: scaleX(wartość);`

`transform: scaleY(wartość);`

## Pochylenie
Pochylenie ("przekoszenie") elementu może wystepować na dwóch osiach: X i Y.
Pochylenie na osi X definiujemy poprzez właściwość: ` transform: skewX(wartość);`
zaś na osi Y: ` transform: skewY(wartość);`. Wartość podawana jest w stopniach (`deg`).

Elementy o właściwościach (od lewej) `skewX(10deg)`, `skewX(0)` i `skewX(-10deg)`:
<div class="rectangle-ch-anim" style="transform: skewX(10deg); width:50px; "></div>
<div class="rectangle-ch-anim" style="width:50px;"></div>
<div class="rectangle-ch-anim" style="transform: skewX(-10deg); width:50px;"></div>

Elementy o właściwościach (od lewej) `skewY(10deg)`, `skewY(0)` i `skewY(-10deg)`:
<div class="rectangle-ch-anim" style="transform: skewY(10deg); width:50px;"></div>
<div class="rectangle-ch-anim" style="width:50px;"></div>
<div class="rectangle-ch-anim" style="transform: skewY(-10deg); width:50px; top: -20px; position: relative;"></div>

## Złożone przekształcenia
Przekształcenia mogą być kombinacją kilku operacji.
Jeśli chcielibyśmy, aby nasz element przeskalował się i przesunął wzdłuż osi X, dodajemy do niego poniższą właściwość:

`transform: scale(1.05) translateX(150px);`

Czyli połączenie operacji polega na wymienieniu ich w odpowiedniej kolejności, jedna po drugiej, oddzielonych spacją.
