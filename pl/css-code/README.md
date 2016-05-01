# Kod CSS

Mamy nadzieję, że po lekturze ostatnich rozdziałów język HTML stał się Wam bliski. Teraz pora na zaznajomienie się z CSS-em, dzięki któremu wreszcie będziecie mogli nadać swojej stronie wymarzony wygląd.

Przypomnijmy sobie, jak wygląda składnia języka CSS:

```css
selektor {
  właściwość: wartość;
}
```

Za pomocą selektorów wybieramy elementy strony, którym chcemy nadać określony wygląd. Na przykład:

```css
p {
  color: blue;
}
```

W powyższy sposób ustawiamy kolor tekstu wszystkich paragrafów na stronie na niebieski. Z tego przykładu łatwo wysnuć wniosek, że za pomocą CSS-a możemy wybierać elementy podając nazwy znaczników. Nie jest to jednak jedyny sposób - zapoznajmy się z kilkoma podstawowymi rodzajami **selektorów CSS**.

## Podstawowe selektory

Elementy na stronie można wybierać na bardzo różne sposoby. W tym rodziale poznamy podstawowe i najczęściej używane selektory CSS, czyli:

- nazwa tagu (`tagname`)
- klasa (`.classname`)
- ID (`#idname`)
- atrybut (`[attr=value]`)

Selektor wybierający element na podstawie tagu już przed chwilą widzieliśmy. Patrząc na selektory ID oraz atrybutu zapewne zaczyna już coś Wam świtać - oznacza to, że możemy wybierać elementy również bazując na wartościach ich atrybutów `id` oraz obecności innych atrybutów. Jedyny rodzaj, który pewnie wydaje się w tej chwili tajemniczy to *klasa*.

### Klasa

Przyjrzyjmy się przykładowemu elementowi strony:

```html
<input type="email" id="myEmail" class="awwwesome-input">
```

Obok znanych już Wam atrybutów `type` oraz `id` pojawił się nowy: `class`. Jest on bardzo ważny w kontekście stylowania.

W zasadzie jedynym celem atrybutu `class` jest nadanie naszemu elementowi *identyfikatora*, który będzie służył jako selektor. Pewnie pomyślicie teraz *"ale przecież on ma już identyfikator `id`!"*. Słusznie, jednak wartość atrybutu `class` nie musi być unikalna w zakresie dokumentu. Tę samą wartość możemy nadać więcej niż jednemu elementowi, nie muszą też być one tego samego rodzaju.

```html
<body>
  <h1 class="awwwesome">Tytuł strony</h1>

  <p class="awwwesome">Jestem paragrafem tekstu. Nadano mi atrybut class, aby umożliwić stylowanie.</p>
  <p>Jestem paragrafem tekstu.</p>

  <form name="myForm">
    <label for="name">Twoje imię:</label>
    <input id="name" type="text" class="awwwesome">
  </form>
</body>
```

Nadajmy tekstowi każdego elementu z powyższego przykładu posiadającego klasę `awwwesome` kolor zielony:

```css
.awwwesome {
  color: green;
}
```

<div class="example-wrapper">
  <h1 class="awwwesome" style="color:green !important;">Tytuł strony</h1>

  <p class="awwwesome" style="color:green  !important; ">Jestem paragrafem tekstu. Nadano mi atrybut class, aby umożliwić stylowanie.</p>
  <p>Jestem paragrafem tekstu.</p>

  <form name="myForm">
    <label for="name">Twoje imię:</label>
    <input id="name" type="text" class="awwwesome" style="color:green; ">
  </form>
</div>

### ID

Wróćmy jeszcze na chwilę do elementu z naszego poprzedniego przykładu:

```html
<input type="email" id="myEmail" class="awwwesome-input">
```

Nadajmy tekstowi w naszej kontrolce kolor czerwony, odnosząc się do niego po `id`. Możemy to zrobić w ten sposób:

```css
#myEmail {
  color: red;
}
```

Przypomnijmy, że w jednym dokumencie wartości atrybutu `id` powinny być unikalne. W związku z tym style zawarte wewnątrz tego selektora nie są zbyt reużywalne - możemy je zastosować tylko dla jednego, konkretnego elementu na stronie.

### Atrybut

Stylować można również elementy zawierające konkretny atrybut. Dobrym przykładem jest np. tag `<input type="text">`. W tym wypadku deklaracja CSS będzie dotyczyła kontrolek `input` typu text. 

```css
input[type="text"] {
    border: 2px solid blue; 
}
```
W wyniku powyższego kodu do kontrolki zostanie dodana ramka o grubości 2px i kolorze niebieskim.

<div class="example-wrapper">
<input type="text" style="border: 2px solid blue; ">
</div>

### Nazwa tagu

Wróćmy jeszcze na chwilę do selektorów po nazwie tagu.

## Podstawowe właściwości CSS i ich wartości

CSS umożliwia zastosowanie całej palety różnych właściwości - od koloru tekstu, tła, przez zastosowanie dowolnego kroju pisma, dodania cieniowania, gradientu  aż do definiowania ustawiania elementów. W tym rozdziale zajmiemy się tymi najbardziej podstawowymi. 

### Kolorowanie tekstu (`color`)

Służy nam do tego właściwość `color`, której przypisujemy kolor. Najczęściej definiuje się je w kodzie heksadecymalnym, czyli szestnastkowym z charakterystycznym znakiem `#`. Kody te pobiera się z tzw. <i>color pickerów</i>, np. <a href="http://htmlcolorcodes.com/" target="_blank">tutaj</a>. w programach graficznych lub innych narzędzi. Jeśli zainteresowałeś się kodem heksadecymalnym więcej do poczytania <a href="https://pl.wikipedia.org/wiki/Kolory_w_Internecie#Zapis_szesnastkowy">tutaj</a>. 
```css
p {
  color: #f14b5c ; //kolor pomarańczowy
}
```

Wynik:<p style="color: #f14b5c;">To jest paragraf o kolorze pomarańczowym.</p>
### Kolorowanie tła (`background-color`)
Służy do tego właściwość: `background-color: #fff;`

```css
p {
  color: #f14b5c ; //kolor pomarańczowy
  background-color: #FFE7EC //kolor jasnoróżowy
}
```
Wynik:<p style="color: #f14b5c ;background-color:#FFE7EC;">To jest paragraf o kolorze pomarańczowym na jasnoróżowym tle.</p>

### Obramowanie

Za obramowanie odpowiada właściwość `border`, której przypisać możemy grubość, rodzaj linii (przerywana, ciągła, kropkowana) i kolor. Przy nadawaniu wartości powinna być zachowana powyższa kolejność, czyli
```css
 border: 2px solid #f14b5c;
 ```


```css
p {
  color: #f14b5c ; //kolor pomarańczowy
  background-color: #FFE7EC //kolor jasnoróżowy
  border: 2px solid #f14b5c;
}
```
Wynik:<p style="color: #f14b5c ;background-color:#FFE7EC;border: 1px solid #f14b5c;">To jest paragraf o kolorze pomarańczowym na jasnoróżowym tle.</p>

### Dodawanie dopełnień (`padding`)
Dopełnienie definiowane jest jako odległość między obramowaniem elementu a jego zawartością. Dla każdej strony mogą być to inne wartości. 
Np 'padding: 5px 10px 15px 20px', oznacza, że dopełnienie od góry wynosi 5px, od prawej 10px, od dołu 15px a od góry 20px. Żeby łatwiej było Ci wpisywać te wartości zapamiętaj, że są one definiowane zgodnie z kierunkiem wskazówek zegara (od góry, prawo, dół, lewo).


```css
p {
  color: #f14b5c ; //kolor pomarańczowy
  background-color: #FFE7EC //kolor jasnoróżowy
  border: 2px solid #f14b5c;
  padding: 20px 10px 20px 10px; //dopełnienia kolejno od: góry, prawej strony, dołu i lewej strony
}
```
Wynik:<p style="color: #f14b5c ;background-color:#FFE7EC;border: 1px solid #f14b5c; padding: 20px 10px 20px 10px;">To jest paragraf o kolorze pomarańczowym na jasnoróżowym tle.</p>

### Ułożenie tekstu (`text-align`)

Tekst może zostać wyrównany na trzy różne sposoby:
- do prawej `text-align: right;`
- do lewej `text-align: left;`
- do środka `text-align: center;`
``

```css
p {
  text-align: center;
  color: #f14b5c ; //kolor pomarańczowy
  background-color: #FFE7EC //kolor jasnoróżowy
  border: 2px solid #f14b5c;
  padding: 20px 10px 20px 10px; //dopełnienia kolejno od: góry, prawej strony, dołu i lewej strony
}
```

### Dodawanie marginesu (`margin`)

```css
p {
  margin: 20px 60px;
  text-align: center;
  color: #f14b5c ; //kolor pomarańczowy
  background-color: #FFE7EC //kolor jasnoróżowy
  border: 2px solid #f14b5c;
  padding: 20px 10px 20px 10px; //dopełnienia kolejno od: góry, prawej strony, dołu i lewej strony
}
```
Wynik:<p style="color: #f14b5c; text-align: center; margin: 20px 60px; background-color:#FFE7EC;border: 1px solid #f14b5c; padding: 20px 10px 20px 10px;">To jest paragraf o kolorze pomarańczowym na jasnoróżowym tle.</p><p style="color: #f14b5c; text-align: center; background-color:#FFE7EC;border: 1px solid #f14b5c; padding: 20px 10px 20px 10px; margin: 20px 60px;">To jest paragraf o kolorze pomarańczowym na jasnoróżowym tle.</p>


## Jak dołączyć style do strony?

Istnieje kilka sposobów na to żeby dołączyć CSS do naszego kodu HTML.
Pierwszym z nich jest dołączenie zewnętrznego pliku z rozszrzeniem .css, w którym będzie zawarty nasz CSS-owy kod. Jest to najczęściej stosowana metoda i to właśnie jej będziemy się trzymać. 


```html
<link href="tu wpisz ścieżkę do pliku css" rel="stylesheet">
``` 
Znacznik <link> znajduje się w części <head> naszego dokumentu HTML.
```html
<html lang="pl-PL">
  <head>
    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width, initial-scale=1">
    <meta name="description" content="Darmowe warsztaty z programowania HTML i CSS.">
    <title>The Awwwesomes - Darmowe warsztaty z programowania HTML & CSS</title>
    <!--poniżej załączony jest plik z arkuszami stylów, czyli plik CSS-->
    <link rel="stylesheet" href="/styles/website.css"> 
  </head>
  <body>
```  

> #### Important::Ważne
>
> Kolejność załączania plików CSS ma znaczenie. Jeśli w Waszym projekcie dołączać będziecie do strony więcej niż jeden plik CSS i gdy w obu z nich będą występować te same selektory, lecz różne właściwości, to przeglądarka z priorytetem będzie traktować ten selektor, który został załączony jako ostatni. Najlepiej zrozumieć to poprzez prosty przykład:
W naszym pliku index.html dołączone są następujące deklaracje:
```html
<link href="/styles/style-1.css" rel="stylesheet">
<link href="/styles/style-2.css" rel="stylesheet">
```
Jeśli w pliku style-1.css występuje deklaracja:
```css
h1 {
  color: red;
}
``` 
A w pliku style-2.css
```css
h1 {
  color: green;
}
``` 
To przeglądarka nada naszemu nagłówkowi zielony kolor, gdyż występuje on jako 'ostatni'. W związku z tym nadpisze wszystkie inne właściwości (domyślne przeglądarki - kolor czarny oraz kolor czerwony z pierwszego pliku CSS).
```
>

.
.

> #### Exercise::Ćwiczenie 7
>
> W tym ćwiczeniu nauczysz się jak poprawnie załączać plik CSS do Twojej strony.
>Otwórz folder z projektem `planty`, zawierający podstawowy kod z poprzednich zajęć (patrz Ćwiczenie 6). A następnie stwórz pusty plik `style.css` i zapisz go do nowo-utworzonego folderu `/styles`. 

>Plik CSS został stworzony, zatem należy go teraz podpiąć do pliku index.html. W tym celu stosujemy znacznik `<link href="ścieżka do Twojego pliku css" rel="stylesheet">` z odpowiednio uzupełnionymi atrybutami. Przy okazji przećwiczysz ścieżki względne. 

>**Ważne** - znacznik `<link...>` dodawany jest pomiędzy znacznikami `<head>` i `</head>`, najlepiej po znacznikach `<meta>`. 
>

Jak sprawdzić czy plik CSS został poprawnie dołączont do strony? Najlepiej poprzez sprawdzenie czy zdefiniowane przez nas style prawidłowo się wyświetlają. Plik `style.css` jest pusty. Pora zatem na napisanie pierwszych CSS-owych deklaracji!


> #### Exercise::Ćwiczenie 8
>
> W tym ćwiczeniu postawisz swoje pierwsze CSS-owe kroki. Nareszcie Twój kod HTML nabierze życia i zmieni kolory! Gotowy?
Zacznijmy od stworzenia nowego folderu z exercise-8 i pliku index.html zawartego w tym katalogu. Stwórz szkielet strony na podstawie poniższego widoku. 

><div class="example-wrapper" style="background: #ffcbd7; ">
  <article>
    <header>
      <p style="color: #FF7684 !important; text-style: underline;">Opublikowano przez: The Awwwesomes,
        <time datetime="2016-04-20T18:00+01:00" style="color: #f14b5c !important;">20 kwietnia 2016</time>
      </p>
      <h1 style="color: #f14b5c !important;">Uczymy się CSS razem z The Awwwesomes!</h1>
    </header>
    <img src="/images/img-css.png" alt="The Awwwesomes">
    <p style="color:#282f5f !important;">Warsztaty ruszyły pełną parą! Grupa 20 zdolnych uczestników zabrała się do kodowania z godnym podziwu zapałem.</p>
    <p style="color:#282f5f !important;">Mentorzy mieli trudne zadanie, ponieważ padło bardzo dużo ciekawych pytań. Nasi uczestnicy są naprawdę <strong style="color:#282f5f !important;">awwwesome</strong>!</p>
    <h3 style="color: #f14b5c !important;">Najpierw semantyczny HTML, potem estetyczny CSS</h3>
    <p style="color:#282f5f !important;">Naukę zaczęliśmy od HTML, który jest absolutną podstawą dla każdego kodera stron internetowych. Nie obejdzie się jednak bez zapoznania z CSS, dzięki któremu każdy może upiększyć swoją stronę jak tylko sobie wymarzy!</p>
  </article>
  <form>
    <p>Zostaw swój komentarz:</p>
    <label for="email">Twój email:</label>
    <input type="email" id="email" style="border:1px solid #000; background: transparent;">
    <label for="name">Twoje imię:</label>
    <input type="text" id="name" style="border:1px solid #000; background: transparent;">
    <label for="comment">Twój komentarz:</label>
    <textarea id="comment" style="border:1px solid #000; background: transparent;"></textarea>
    <button type="submit" style="background: #282f5f; color:#fff !important; border: 0; ">Prześlij</button>
  </form>
</div>





