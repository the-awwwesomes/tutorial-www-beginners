# Dołączanie fontów Google Fonts

Pora na chwilę oddechu – nauczymy się wreszcie dołączać inne kroje pisma.

Kolory i typografia niewątpliwie wpływają na charakter strony i to jak ją odbieramy. Na całe szczęście dołączanie różnych, niestandardowych krojów pisma stało się możliwe i całkiem proste, o czym zaraz się przekonacie.

Zanim jednak zaczniemy szukać odpowiedniego kroju, musimy pamiętać, że jedynie fonty zapisane w odpowiednich formatach będą renderowane w konkretnych przeglądarkach internetowych.  Pamiętajmy, że posiadanie danego fontu na komputerze i jego poprawne wyświetlanie na naszym systemie, nie oznacza, że będzie się on poprawnie wyświetlać u wszystkich innych użytkowników. Cała magia tkwi w tym, by font został wyrenderowany, pomimo faktu, iż użytkownicy nie mają danego kroju pisma zainstalowanego na swoich komputerach. W tym celu najlepiej korzystać z <a href="https://www.google.com/fonts">Google Fonts</a> lub fontów webowych, których pliki należy zaimportować do CSS-a. Tę drugą metodę poznamy nieco później.

Obecnie istnieje wiele portali, które darmowo udostępniają bardzo wiele różnych fontów. Jednym z najczęściej używanych jest <a href="https://www.google.com/fonts">Google Fonts</a>.

## Jak podłączyć font z Google Fonts?

Odwiedźmy stronę <a href="https://www.google.com/fonts">Google Fonts</a> i wybierzmy font. W naszym layoucie [Planty](../appendix/layouts/README.md) wykorzystane zostały trzy różne rodziny fontów: <i>Playfair Display</i>, <i>Montserat</i> oraz <i>Muli</i>. Znajdziemy je na <a href="https://www.google.com/fonts">Google Fonts</a>.
Fonty te poza tym, że mogą zostać podpięte pod naszą stronę, mogą także zostać ściągnięte i zainstalowane na naszych komputerach.

Na stronie Google Fonts w oknie wyszukiwania, z prawej strony wpisujemy nazwę fontu.


> ![](/images/googlefonts-1.jpg "Google Fonts i zaznaczona wyszukiwarka z prawej strony.")
>
>



Następnie będąc na stronie danego fontu, klikamy w „Select this font”.


> ![](/images/googlefonts-2.jpg "")


Na samym dole klikamy w czarny panel „Family Selected”.

> ![](/images/googlefonts-3.jpg "")


Powinien pokazać się pop-up, gdzie znajdziemy najważniejsze dla nas informację, które wykorzystamy do podpięcia wybranego fontu. Interesować nas będzie znacznik `<link ...>`, który umieszczamy w sekcji `<head>` oraz właściwość `font-family: "..."`, którą nadajemy danemu elementowi w pliku CSS. Dokładniejszy opis jak to zrobić znajdziecie poniżej.






W zakładce „Customize” wybierzmy interesujące nas style danego kroju. W projekcie Planty będziemy korzystać z „Normal 400” oraz „Normal 400 Italic”. W przypadkach, gdy współpracujemy z projektantami graficznymi zapytajmy o to, które style użyte są w projekcie.


> ![](/images/googlefonts-4.jpg "Zakłaka 'Customize'"")


Jeśli tworzymy stronę w języku polskim, upewnijmy się czy font wyposażony jest w polskie znaki. Można to sprawdzić wpisując tekst w Google Fonts i obserwując jak te znaki są wyświetlane. Domyślnie font nie ma zaznaczonego checkboksa „Latin extended”, który zawiera m.in. polskie znaki.


Pamiętajmy, żeby zaznaczyć tę opcję, jeśli potrzebujemy polskich znaków. W przypadku Planty możemy zostawić opcję domyślną (teksty są w języku angielskim).


Poniższy znacznik należy umieścić w sekcji` <head>`.
```html
<link href='https://fonts.googleapis.com/css?family=Playfair+Display:400,400italic&subset=latin,latin-ext' rel='stylesheet' type='text/css'>
```
Dzięki znacznikowi `<link>`, podłączyliśmy do naszej strony font "Playfair Display", ale na samej stronie nic się nie zmieniło – ciągle wyświetlany jest domyślny font systemowy. Pozostało jeszcze podpięcie wybranego fonta do arkusza stylów. Dzieje się to dzięki właściwości `font-family`. W punkcie 4. na stronie Google Fonts znajdziemy nazwę fontu, którą trzeba zastosować.

```css
ul li {
	font-family: 'Playfair Display', serif;
}
```
Zastanówmy się jeszcze, co oznacza wartość `'Playfair Display', serif;` i dlaczego występuje tam nazwa `serif`?
Otóż jeśli nie zostanie znaleziony font o nazwie `'Playfair Display'` (np. nie dołączymy do naszego kodu skryptu ze strony Google Fonts), to przeglądarka wyświetli dowolny, dostępny font szeryfowy właśnie dzięki wartości `serif`.
Deklarację możemy też rozbudować o większą liczbę krojów, np.

```css
ul li {
	font-family: 'Playfair Display', 'Georgia', serif;
}
```

Kod ten oznacza: "wyświetl font 'Playfair Display'; jeśli nie jest to możliwe, to wyświetl font 'Georgia'; jeśli 'Georgia' nie została znaleziona, to wyświetl dowolny font szeryfowy".

Teraz możemy sprawdzić czy nasza lista na stronie zmieniła font. W celu weryfikacji dla elementu listy odznaczmy właściwość `font-family` w narzędziach developerskich. Czy zaobserwowaliście zmianę fontu?

> #### Exercise::Ćwiczenie 9
>
> Pora na podłączenie pozostałych dwóch fontów do naszego layoutu. 
>
> Jakie to fonty? Możesz sprawdzić to za pomocą programu graficznego, który otwiera pliki `.psd` (Photoshop), jednak dla ułatwienia przygotowaliśmy dla Ciebie informacje o rodzajach fontów w pliku tekstowym. 
>
> Taki plik znajdziecie w folderach z zasobami dla każdego layoutu pod nazwą `info.txt`.
>
> Uwaga &ndash; renderowanie fontów może nieco różnić się w zależności od przeglądarki, więc nie przejmuj się na razie, jeśli u Ciebie fonty wyglądają na "cieńsze" lub "bardziej tłuste". Pomińmy też na tym etapie wielkości fontów.

Możecie dodawać dowolną liczbę niesystemowych fontów. Pamiętajcie jednak, że fonty ładowane są wraz z ładowaniem strony internetowej. Przy wolniejszym transferze internetowym zauważyć można doładowywanie fontów.
