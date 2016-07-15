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

Nadawanie nazw w kodzie (na przykład selektorom CSS) nie jest tak prostym tematem, jak z początku się wydaje. Z punktu widzenia przeglądarki możemy nasze elementy nazywać w zasadzie jakkolwiek, byle w efekcie strona działała zgodnie z oczekiwaniami. Jednak musimy starać się również nie utrudniać pracy samym sobie. Jak powinniśmy nadawać nazwy, aby nie przyprawiać się o ból głowy, kiedy edytujemy kod?

### CSS

#### Źle <span class="wrong">✘</span>

```css
.box1 {
  border: 1px solid #ccc;
  border-radius: 1rem;
  padding: 1.5rem;
}

.boxaaa {
  border: 1px solid crimson;
  border-radius: 2rem;
  padding: 1rem;
}

#b2 {
  font-weight: bold;
  text-decoration: underline;
}
```

Powyżej widzimy kilka przykładów źle nazwanych selektorów. Jeśli odpowiadają im konretne elementy w kodzie HTML, wszystko będzie działać poprawnie. Co się jednak stanie, kiedy będziecie zmuszeni wrócić do takiego kodu po jakimś czasie? Podejrzewamy, że nazwy typu `box1` albo nawet `b2` nie będą Wam wiele mówić.

Powinniśmy starać się używać takich nazw, aby móc jak najkrócej się zastanawiać "do czego służy ten selektor?". W powyższym przykładzie nazwa `box1` jest prawie w porządku, nie za bardzo wiadomo tylko, do czego służy `1`. Co, jeśli w kodzie z jakichś powodów umieścimy selektor `box2`? Trudno będzie określić co je różni i w jakich konkretnie sytuacjach został użyty pierwszy, a w jakich drugi. Nie bójcie się bycia opisowym w nazywaniu elementów, oczywiście w ramach zdrowego rozsądku (zbyt długie nazwy selektorów też mogą utrudniać życie).

#### Źle <span class="wrong">✘</span>

```css
.box {
  border: 1px solid #ccc;
  border-radius: 1rem;
  padding: 1.5rem;
}

.boxAlert {
  border: 1px solid crimson;
  border-radius: 2rem;
  padding: 1rem;
}

#tytul-sekcji {
  font-weight: bold;
  text-decoration: underline;
}
```

Już jest lepiej, dużo lepiej &ndash; powiecie &ndash; dlaczego umieszczacie to jako antyprzykład?

Chcemy Wam zwrócić uwagę na konsekwencję w nadawaniu nazw. W powyższym przykładzie <b>brak konsekwencji w języku</b>, w jakim są pisane nazwy selektorów. Niby nic, a jednak szybko w kodzie robi się bałagan. Warto na początku określić, czy będziemy nazywać selektory w naszym ojczystym języku (wymuszony brak znaków diakrytycznych może jednak razić purystów), czy zdecydujemy się na uniwersalny angielski.

Mocno zalecamy Wam już od początku przyzwyczajać się do pisania kodu w <b>języku angielskim</b>, ponieważ, rzecz jasna w tym przypadku Wasz kod jest zrozumiały dla dużo większej grupy osób. Obecnie przyjmuje się to jako <b>standard</b>. Środowisko programistów frontend jest międzynarodowe, więc bez znajomości angielskiego ani rusz!

#### Źle <span class="wrong">✘</span>

```css
.box {
  border: 1px solid #ccc;
  border-radius: 1rem;
  padding: 1.5rem;
}

.boxAlert {
  border: 1px solid crimson;
  border-radius: 2rem;
  padding: 1rem;
}

#section-title {
  font-weight: bold;
  text-decoration: underline;
}

.text_highlighted {
  color: lime;
}
```

Super, umiemy już nadawać naszym elementom nazwy. Niestety, brakuje nam jeszcze konsekwencji w ich <b>zapisie</b>. Często zdarza się, że nasza nazwa musi składać się z więcej niż jednego słowa i chcąc zwiększyć jej czytelność chcemy w jakiś sposób wyróżnić początek każdego z nich.

W powyższym przykładzie użyliśmy aż trzech sposobów: separowanie myślnikami (`-`), znakami podkreślenia (`_`) oraz tzw. [`camelCase`](https://en.wikipedia.org/wiki/CamelCase). Warto wybrać sobie spośród nich jeden i cały czas go trzymać &ndash; wtedy nasz kod będzie się dużo przyjemniej czytało.

#### Dobrze <span class="good">✔</span>

```css
.box {
  border: 1px solid #ccc;
  border-radius: 1rem;
  padding: 1.5rem;
}

.box-alert {
  border: 1px solid crimson;
  border-radius: 2rem;
  padding: 1rem;
}

#section-title {
  font-weight: bold;
  text-decoration: underline;
}

.text-highlighted {
  color: lime;
}
```

Brawo, teraz umiemy już nadawać nazwy naszym elementom!

## Piszemy komentarze

Kolejnym ułatwieniem podczas naszej pracy z kodem są <b>komentarze</b>. Pomagają nam one w opisie niezbyt oczywistych na pierwszy rzut oka rozwiązań. W przypadku CSS mogą się wydawać niemal zupełnie zbędne, jeśli używamy wystarczająco opisowych nazw selektorów. To tylko pozory, ponieważ w miarę rozbudowywania się bazy kodu, a także stosowania bardziej złożonych rozwiązań może być już trudniej odgadnąć, co miał na myśli inny programista albo my sami jakiś czas temu. Komentarze w CSS umieszczamy wewnątrz specjalnych znaków `/* */`. 

Spójrzmy na przykład bardziej rozbudowanego komentarza w CSS:

```css
/**
 * Apply this class for an element which should be
 * centered both horizontally and vertically
 * inside its parent element
 *
 * 1. The centered container should live inside
 *    a relatively positioned parent element to allow
 *    absolute positioning
 * 2. Move both the top and left edges of an element to 
 *    the center of the parent block
 * 3. Adjust the element's position to the center
 *    using CSS 2D transforms
 */
.centered {
  position: absolute; /* [1] */
  top: 50%; /* [2] */
  left: 50%; /* [2] */
  transform: translate(-50%, -50%); /* [3] */
}
```

W kodzie HTML również możemy umieszczać komentarze:

```html
<!-- There should be only one instance of `header-lead` on a single page -->
<header>
  <h1 class="header-lead">Wiadomość z ostatniej chwili</h1>
  <h2 class="header-sub">Szczegóły wiadomości z ostatniej chwili</h2>
</header>
```

## Ustawienia edytora tekstowego

Aby pisać czytelny kod, trzeba bardzo się pilnować. Czy jest jakiś sposób, aby sobie pomóc i zautomatyzować formatowanie kodu? 

Oczywiście! Pokażemy Wam kilka skrótów i ustawień na przykładzie edytora [Sublime Text](https://www.sublimetext.com/3), które pomogą Wam okiełznać kod. Warto zastosować te wszystkie ustawienia jeszcze <b>zanim</b> zaczynacie pracę nad projektem. Jeśli pracuje nad nim więcej niż jedna osoba, należy zadbać, aby każda miała identyczne ustawienia edytora.

### Ustawiamy rozmiar wcięć w kodzie

Najprostszym sposobem dodawania wcięcia jest wciśnięcie klawisza <kbd>Tab</kbd>. Nie każdy jednak gustuje w znakach tabulacji (przyznajcie szczerze, zajmują dużo miejsca), dlatego istnieje możliwość zmapowania sobie znaku tabulacji na odpowiednią liczbę spacji (domyślnie wielkość znaku tabulacji równa jest 4 spacjom).

W Sublime Text ustawienia użytkownika są przechowywane w specjalnym pliku [JSON](https://en.wikipedia.org/wiki/JSON#Example). Aby je wyedytować, wchodzimy w menu do `Preferences`→`Settings – User`. Powinien otworzyć się w osobnej zakładce gotowy do edycji plik. Wewnątrz nawiasów klamrowych należy dodać dwie linijki:

```json
  "tab_size": 2,
  "translate_tabs_to_spaces": true
```

Powiedzą one edytorowi o tym, jaki powinien stosować rozmiar wcięcia (w naszym przypadku dwie spacje) oraz żeby "tłumaczył" znak tabulacji na spacje.

W prawym dolnym rogu Sublime wyświetla informacje na temat wcięć w kodzie. Można zmienić to ustawienie dla konkretnego pilku.

!["Rozmiar wcięcia w kodzie w edytorze Sublime"](/images/sublime-tabs.png "Rozmiar wcięcia w kodzie w edytorze Sublime")

!["Zmiana rozmiaru wcięcia w kodzie w edytorze Sublime"](/images/sublime-change-indent.png "Zmiana rozmiaru wcięcia w kodzie w edytorze Sublime")

### Szybkie formatowanie

Jeśli nie chcemy się przemęczać, możemy kazać edytorowi automatycznie sformatować cały kod w pliku, nad którym pracujemy. W Sublime domyślnie można to zrobić zaznaczając kawałek kodu, który chcemy sformatować (lub <kbd>Ctrl</kbd>/<kbd>Cmd</kbd>+<kbd>A</kbd>, jeśli chcemy zaznaczyć całą zawartość pliku) i następnie wybierając w menu `Edit`→`Line`→`Reindent`.

Żeby nie musieć za każdym razem, kiedy zajdzie taka potrzeba, wyklikiwać tego w menu, warto dodać sobie w ustawieniach Sublime skrót klawiaturowy. Skróty klawiaturowe dodaje się w bardzo podobny sposób, jak ustawienia. W tym celu wchodzimy do `Preferences`→`Key Bindings – User` i wewnątrz nawiasów klamrowych wklejamy jedną z poniższych linijek.

Dla Windowsa:

```json
{ "keys": ["ctrl+shift+r"], "command": "reindent" , "args": { "single_line": false }
```

Dla MacOS:

```json
{ "keys": ["cmd+shift+r"], "command": "reindent" , "args": { "single_line": false }
```

Za pomocą linijek powyżej mapujemy formatowanie kodu na skrót klawiszowy <kbd>Ctrl</kbd>/<kbd>Cmd</kbd>+<kbd>Shift</kbd>+<kbd>R</kbd>.

### Pilnujemy maksymalnej długości linii

Czasem zdarza się (zwłaszcza w HTML), że z powodu dużej liczby wcięć bądź po prostu samej zawartości linie kodu przestają się mieścić na ekranie. W tym wypadku należy po prostu złamać zbyt długą linię. W którym momencie to zrobić? Bardzo często jako standard maksymalnej długości linii przyjmuje się 80 znaków.

W Sublime możemy w widoku edycji umieścić sobie linijkę pilnującą nas przed nieprzekraczaniem maksymalnej liczby znaków w linii. Na początku dodajmy w ustawieniach linijkę mówiącą o tym, ile znaków chcemy maksymalnie mieścić w linii.

```json
"rulers": [ 80 ]
```

Po zapisaniu ustawień możemy już włączyć opcję pokazywania pionowej linijki w menu `View`→`Ruler`

!["Linijka w Sublime"](/images/sublime-ruler.png "Linijka w Sublime")
