# Jak pisać czytelny kod?

Kiedy zaczynacie swoją przygodę z kodowaniem, zapewne nie zaprzątacie sobie głów tym, jak wygląda Wasz kod &ndash; zależy Wam po prostu, żeby działał. Problem czytelności kodu może się z pozoru wydawać mało istotny, jednak ma kluczowe znaczenie dla całego procesu tworzenia strony. Czysty kod łatwo jest utrzymywać, łatwo też wyłapywać w nim błędy.

Pisząc znaczniki HTML nietrudno pominąć zamykające tagi, kodując w CSS szybko można przeoczyć średnik zamykający linię. Takie błędy, z pozoru niewinne, powodują, że nasza strona źle się wyświetla.

Warto dbać o poprawność i czytelność naszego kodu nie tylko dla nas samych, ale też innych osób, którym kiedykolwiek zdarzy się go edytować.

## Pilnujemy odpowiednich wcięć w kodzie

HTML i CSS to języki, w których w zasadzie możemy umieszczać cały swój kod w jednej linii &ndash; przeglądarka i tak go zrozumie. Ten brak wymuszonej dyscypliny może rozleniwić i doprowadzić do niezłego bałaganu i bardzo nieczytelnego kodu. Jak temu zapobiec? Starać się konsekwentnie używać wcięć w kodzie!

### HTML

W przypadku HTML-a dobrą praktyką jest otwieranie nowego tagu od nowej linii i umieszczanie wcięcia, jeśli zagnieżdżamy grupę tagów wewnątrz innego.

#### Źle <span class="wrong">✘</span>

```html
<div class="expert">
<img src="/images/anna.png"><h3>Anna Smith</h3>
<div class="expert-info"><p>Health goth freegan craft beer, crucifix green juice synth deep v squid hashtag semiotics chambray.</p>
  <a href="http://fb.com/a.smith">Facebook</a>
  <a href="http://twitter.com/asmith">Twitter</a>
  </div>
</div>
```

#### Źle <span class="wrong">✘</span>

```html
<div class="expert"><img src="/images/anna.png">
  <h3>Anna Smith</h3>

<div class="expert-info">
  <p>Health goth freegan craft beer, crucifix green juice synth deep v squid hashtag semiotics chambray.</p>
  <a href="http://fb.com/a.smith">Facebook</a><a href="http://twitter.com/asmith">Twitter</a>
</div>
```

A tu zgubiliśmy nawet zamykającego `div`a &ndash; czy już widzicie, gdzie?

#### Dobrze <span class="good">✔</span>

```html
<div class="expert">
  <img src="/images/anna.png">
  <h3>Anna Smith</h3>
  <div class="expert-info">
    <p>Health goth freegan craft beer, crucifix green juice synth deep v squid hashtag semiotics chambray.</p>
    <a href="http://fb.com/a.smith">Facebook</a>
    <a href="http://twitter.com/asmith">Twitter</a>
  </div>
</div>
```

Prawda, że jest o wiele bardziej czytelny?

### CSS

W CSS również nie ma znaczenia, czy deklaracja kolejnej właściwości nastąpi od nowej linii czy w jej kontynuacji. Przyjęło się jednak, że dla zmaksymalizowania czytelności każdą deklarację właściwości powinno zapisywać się w kolejnej linii.

#### Źle <span class="wrong">✘</span>

```css
.expert-img{position: absolute;top: 50%;
  margin-top: -75px;
    border-radius: 50%;
border: 3px solid darkseagreen;}
```

Wszystko działa, ale jest bardzo nieczytelnie.

#### Źle <span class="wrong">✘</span>

```css
.expert-img {
  position: absolute;
  top: 50%;
  margin-top: -75px
  border-radius: 50%;
  border: 3px solid darkseagreen;
}
```

Dużo lepiej, jednak wkradł się tu błąd. Brakuje średnika po deklaracji wartości `margin-top`, w związku z czym przeglądarka pominie wszystkie właściwości zadeklarowane po `top` (i nasz element nie będzie posiadał m.in. zielonej ramki).

#### Dobrze <span class="good">✔</span>

```css
.expert-img {
  position: absolute;
  top: 50%;
  margin-top: -75px;
  border-radius: 50%;
  border: 3px solid darkseagreen;
}
```

Teraz jest idealnie!

## Staramy się konsekwentnie formatować kod

Ta rada jest bardzo podobna do powyższej, jednak dotyczy nieco szerszego zakresu, niż tylko wcięć.

<!-- tabs vs spaces -->

### HTML

#### Źle <span class="wrong">✘</span>

```html
<label FOR='new-file'>Plik do przesłania:</label>
<input type="file" Accept="image/*" id=new-file class='my-file-input'>
```

Powyższy przykład jest nieco przerysowany, ale zwraca uwagę na problem konsekwencji w używaniu m.in. cudzysłowów. W HTML5 nie ma nawet przymusu owijania wartości artybutów w cudzysłowy! Oczywiście, nie sprzyja to w utrzymywaniu porządku w kodzie.

Co konkretnie jest nie tak w powyższym przykładzie?

- Używanie dwóch różnych rodzajów cudzysłowów: `''` oraz `""`,
- Niekonsekwentne używanie cudzysłowów &ndash; w większości przypadków są one używane dla wartości atrybutów, jednak w jednym przypadku ich brakuje (`id=new-file`),
- Niektóre atrybuty pisane są z użyciem dużych liter (`FOR`, `Accept`), niektóre nie.

#### Dobrze <span class="good">✔</span>

```html
<label for="new-file">Plik do przesłania:</label>
<input type="file" accept="image/*" id="new-file" class="my-file-input">
```

### CSS

#### Źle <span class="wrong">✘</span>

```css
.expert{ 
  position:relative;
}
.expert-name {
  color: darkseagreen;
  font-size:2rem;
    text-transform:uppercase;
    letter-spacing: 1px;
}

.expert-contact {
  font-size: .8rem;
}
```

Uff, prawie! Czy potraficie wymienić przykłady niekonsekwencji w formatowaniu powyższego kodu?

#### Dobrze <span class="good">✔</span>

```css
.expert { 
  position: relative;
}

.expert-name {
  color: darkseagreen;
  font-size: 2rem;
  text-transform: uppercase;
}

.expert-contact {
  font-size: .8rem;
}
```

Powyżej widzimy ten sam kod, lepiej sformatowany. Co poprawilśmy? Tu głównie widać, że konsekwentnie używamy spacji i znaków nowej linii:

- Stawiamy spację między nazwą klasy a otwarciem nawiasu klamrowego `{`,
- Stawiamy spację między dwukropkiem po nazwie właściwości a jej wartością (czyli nie `color:darkseagreen;` ani `color :darkseagreen;`, tylko `color: darkseagreen;`), 
- Deklarację każdego selektora zaczynamy od nowej linii i separujemy je znakiem nowej linii,
- Konsekwentnie używamy wcięć w kodzie &ndash; są one tej samej głębokości dla każdej deklaracji właściwości CSS.

## Jesteśmy konsekwentni w nadawaniu nazw

<!-- Mieszanie nazw w różnych językach, używanie na zmianę camelCase, myślników, itd. -->

## Piszemy komentarze

## Ustawienia edytora tekstowego

<!-- Na przykładzie Sublime Text -->
