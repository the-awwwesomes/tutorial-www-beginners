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

## Jak dołączyć style do strony?
