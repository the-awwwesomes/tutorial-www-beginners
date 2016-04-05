# Kod HTML

## Co powinien zawierać prawidłowy kod HTML?

Uwaga, uwaga, zapnijcie pasy, bo przechodzimy wreszcie do konkretów! Za chwilę napiszecie swój pierwszy kod HTML, jesteście już podekscytowani? Przygotowaliśmy dla Was małe ćwiczenie, którego efektem będzie bardzo prosta strona z artykułem. Przyjrzyjcie się zrzutowi ekranu:

Strona zawiera artykuł, który składa się z nagłówka, daty publikacji, obrazka i treści. Pod artykułem znajduje się prosty formularz zgłoszeniowy dla mentorów. Jak przenieść wymienione elementy do kodu HTML?

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

> #### Exercise::Ćwiczenie 3
>
> - W folderze `the-awwwesomes` stwórz podfolder `exercise-3`, w którym będziesz przechowywał wynik ćwiczenia. Otwórz ten folder w Sublime Text i utwórz w nim plik `index.html`.
> - W pliku `index.html` utwórz szkielet strony, który zawiera wszystkie wymienione wyżej niezbędne elementy.