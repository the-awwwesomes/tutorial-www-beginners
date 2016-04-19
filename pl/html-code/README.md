# Kod HTML

Uwaga, uwaga, zapnijcie pasy, bo przechodzimy wreszcie do konkretów! Za chwilę napiszecie swój pierwszy kod HTML, jesteście już podekscytowani? 

## Co powinien zawierać prawidłowy kod HTML?

Jak wygląda HTML w akcji? Spójrzcie poniżej, przygotowaliśmy dla Was przykładowy kod kompletnej strony:

```html
<!doctype html>
<html lang="pl-PL">
  <head>
    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width, initial-scale=1">
    <meta name="description" content="Darmowe warsztaty z programowania HTML i CSS.">
    <title>The Awwwesomes - Darmowe warsztaty z programowania HTML & CSS</title>
    <link rel="stylesheet" href="/styles/website.css">
  </head>
  <body>
    <header>
      <h1>Zapraszamy na darmowe warsztaty HTML i CSS dla początkujących!</h1>
    </header>
    <main>
      <h2>Czy to dla mnie?</h2>
      <p>Czy kiedykolwiek zastanawiałeś się, jak zbudowane są strony WWW?</p>
      <p>Planujesz karierę jako programistka/programista front-end i potrzebujesz merytorycznego wsparcia na start?</p>
      <p>A może prowadzisz własnego bloga i chcesz wprowadzić poprawki w szablonie, ale nie wiesz, jak to zrobić?</p>
      <p>To tylko niektóre z powodów, dla których warto zaaplikować na warsztaty The Awwwesomes.</p>
    </main>
    <footer>
      Copyright &copy; The Awwwesomes 2016
    </footer>
  </body>
</html>
```

Prawidłowy plik HTML zawiera kilka niezbędnych elementów:

- Deklarację `DOCTYPE`:

```html
<!DOCTYPE html>
```

Deklaracja `DOCTYPE` mówi nam o wersji i typie dokumentu HTML. Nie ma znaczenia z punktu widzenia treści, jednak jest bardzo ważna dla przeglądarki interpretującej nasz kod.

- Cały kod strony po deklaracji `DOCTYPE` powinien być zamknięty w tagi `<html>`:

```html
<html>

...

</html>
```

- Wewnątrz tagów `<html>` wyróżniamy dwie sekcje: `<head>`, czyli "głowa" dokumentu, w której będziemy umieszczać *metadane* oraz `<body>`, która zawiera całą treść dokumentu.

```html
<html>
  <head>

  ...

  </head>

  <body>

  ...

  </body>
</html>
```

Co to takiego są [metadane](https://pl.wikipedia.org/wiki/Metadane)? W tym przypadku są to wszystkie informacje istotne dla strony jednak niewidoczne bezpośrednio w jej treści. Kilka przykładów:

- Znacznika `<title>` używamy do podania tytułu strony, który jest zwykle widoczny na górnej belce przeglądarki, jako tytuł karty oraz w wynikach wyszukiwania strony.

```html
<title>Moja pierwsza strona internetowa</title>
```

- Znacznik `<meta>` służy do przechowywania różnego rodzaju metadanych. Na przykład:

```html
<meta charset="utf-8">
```

Powyższa wartość atrybutu ustawia kodowanie dokumentu na [UTF-8](https://pl.wikipedia.org/wiki/UTF-8). Jest to szczególnie ważne, kiedy chcemy używać na naszej stronie polskich (i nie tylko polskich) znaków diakrytycznych.

```html
<meta name="viewport" content="width=device-width, initial-scale=1">
``` 

Użycie atrybutów `name` oraz `content` dokładnie w powyższy sposób pozwala nam na [zoptymalizowanie naszej strony do wyświetlania na urządzeniach mobilnych](https://developer.mozilla.org/pl/docs/Mozilla/Mobile/Viewport_meta_tag). Dzięki temu strona pojawi się w oknie mobilnej przeglądarki dokładnie w rozmiarze dostępnego okna. Nie są to wszystkie działania niezbędne do tego, aby witryna wyświetlała się dobrze. Jest to znacznie szerszy temat, zwany *[Responsive Web Design](https://developer.mozilla.org/pl/docs/Mozilla/Mobile/Viewport_meta_tag)*, czyli projektowanie stron responsywnych.

- Za pomocą atrybutu `<link>` możemy załączyć do naszego dokumentu na przykład plik `*.css`.

```html
 <link rel="stylesheet" href="/styles/website.css">
```
- Używając znacznika `<script>` umieszczamy na stronie skrypty JavaScript.

```html
<script src="/scripts/main.js"></script>
```

> #### Exercise::Ćwiczenie 3
>
> Przyjrzyjcie się zrzutowi ekranu:
>
><div class="example-wrapper">
  <article>
    <header>
      <p>Opublikowano przez: <em>Kasia Niesamowita</em>,
        <time datetime="2016-04-20T18:00+01:00">20 kwietnia 2016</time>
      </p>
      <h1>The Awwwesomes podbijają świat!</h1>
    </header>
    <img src="/images/screen.jpg" alt="The Awwwesomes">
    <p>Warsztaty ruszyły pełną parą! Grupa 20 zdolnych uczestników zabrała się do kodowania z godnym podziwu zapałem.</p>
    <p>Mentorzy mieli trudne zadanie, ponieważ padło bardzo dużo ciekawych pytań. Nasi uczestnicy są naprawdę <em>awwwesome</em>!</p>
    <h2>Najpierw semantyczny HTML, potem estetyczny CSS</h2>
    <p>Naukę zaczęliśmy od HTML, który jest absolutną podstawą dla każdego kodera stron internetowych. Nie obejdzie się jednak bez zapoznania z CSS, dzięki któremu każdy może upiększyć swoją stronę jak tylko sobie wymarzy!</p>
  </article>
  <form>
    <p>Zostaw swój komentarz:</p>
    <label for="email">Twój email:</label>
    <input type="email" id="email">
    <label for="name">Twoje imię:</label>
    <input type="text" id="name">
    <label for="comment">Twój komentarz:</label>
    <textarea id="comment"></textarea>
    <button type="submit">Prześlij</button>
  </form>
</div>
>
> Strona zawiera artykuł, który składa się z nagłówka, daty publikacji, obrazka i treści. Pod artykułem znajduje się prosty formularz do dodawania komentarzy. Jak przenieść wymienione elementy do kodu HTML?
>
> Na początku zadbamy, aby otrzymać w efekcie prawidłowy kod HTML. W tej chwili nie przejmuj się jeszcze tym, jak powinny być kodowane poszczególne elementy, czyli np. nagłówki bądź paragrafy.
> - W folderze `the-awwwesomes` stwórz podfolder `exercise-3`, w którym będziesz przechowywał wynik ćwiczenia. Otwórz ten folder w Sublime Text i utwórz w nim plik `index.html`.
> - W pliku `index.html` utwórz szkielet strony, który zawiera wszystkie wymienione wyżej niezbędne elementy, takie, jak `doctype`, `<title>` bądź znaczniki `<meta>`.
> - Podstawową treść strony umieść wewnątrz znaczników `<body>` jako zwykły tekst. Otwórz `index.html` w przeglądarce. Co widzisz? Czego brakuje?