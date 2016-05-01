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
  <h1 class="awwwesome">Tytuł strony</h1>

  <p class="awwwesome">Jestem paragrafem tekstu. Nadano mi atrybut class, aby umożliwić stylowanie.</p>
  <p>Jestem paragrafem tekstu.</p>

  <form name="myForm">
    <label for="name">Twoje imię:</label>
    <input id="name" type="text" class="awwwesome">
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

### Nazwa tagu

Wróćmy jeszcze na chwilę do selektorów po nazwie tagu.

## Podstawowe właściwości CSS i ich wartości

CSS umożliwia zastosowanie całej palety różnych właściwości - od koloru tekstu, tła, przez zastosowanie dowolnego kroju pisma, dodania cieniowania, gradientu  aż do definiowania ustawiania elementów. W tym rozdziale zajmiemy się tymi najbardziej podstawowymi. 

Kolor i wielkość tekstu
Kolor tła elementów
Obramowanie
Krój pisma
Marginesy
Paddingi


> #### Exercise::Ćwiczenie 7
>
> W tym ćwiczeniu postawisz swoje pierwsze CSS-owe kroki. Nareszcie Twój kod HTML nabierze życia i zmieni kolory! Gotowy?
Zacznijmy od stworzenia nowego folderu z exercise-7 i pliku index.html zawartego w tym katalogu. Stwórz szkielet strony 



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
```html
h1 {
  color: red;
}
``` 
A w pliku style-2.css
```html
h1 {
  color: green;
}
``` 
To przeglądarka nada naszemu nagłówkowi zielony kolor, gdyż występuje on jako 'ostatni'. W związku z tym nadpisze wszystkie inne właściwości (domyślne przeglądarki - kolor czarny oraz kolor czerwony z pierwszego pliku CSS).

A teraz pora na podłączenie stylów do Twojego pliku HTML.

> #### Exercise::Ćwiczenie 8
>
> W tym ćwiczeniu nauczysz się jak poprawnie załączać plik CSS do Twojej strony.
>Otwórz folder z projektem `planty`, zawierający podstawowy kod z poprzednich zajęć (patrz Ćwiczenie 6). A następnie stwórz pusty plik `style.css` i zapisz go do nowo-utworzonego folderu `/styles`. 

>Plik CSS został stworzony, zatem należy go teraz podpiąć do pliku index.html. W tym celu stosujemy znacznik `<link href="ścieżka do Twojego pliku css" rel="stylesheet">` z odpowiednio uzupełnionymi atrybutami. Przy okazji przećwiczysz ścieżki względne. 

>**Ważne** - znacznik `<link...>` dodawany jest pomiędzy znacznikami `<head>` i `</head>`, najlepiej po znacznikach `<meta>`. 
>





