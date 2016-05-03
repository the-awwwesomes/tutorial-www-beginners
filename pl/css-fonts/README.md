# Dołączanie fontów Google Fonts

Pora na chwilę oddechu - nauczymy się wreszcie dołączać inne kroje pisma.

Kolory i typografia niewątpliwie wpływają na charakter strony i to jak ją odbieramy. Całe szczęście dołączanie różnych, niestandardowych krojów pisma stało się możliwe i całkiem proste, o czym zaraz się przekonacie.

Zanim jednak zaczniemy szukać odpowiedniego kroju, musimy pamiętać, że jedynie fonty zapisane w odpowiednich formatach będą renderowane w konkretnych przeglądarkach internetowych.  Pamiętajmy, że posiadanie danego fontu na komputerze i jego poprawne wyświetlanie na naszym systemie, nie oznacza, że będzie się on poprawnie wyświetlać u wszystkich innych użytkowników. Cała magia tkwi w tym, by font został wyrenderowany, pomimo faktu, iż użytkownicy nie mają danego kroju pisma zainstalowanego na swoich komputerach. W tym celu najlepiej korzystać z <a href="https://www.google.com/fonts">Google Fonts</a> lub fontów webowych, których pliki należy zaimportować do CSS-a. Tę drugą metodę poznamy nieco później.

Obecnie istnieje wiele portali, które darmowo udostępniają bardzo wiele różnych fontów. Jednym z najczęściej używanych jest <a href="https://www.google.com/fonts">Google Fonts</a>.

## Jak podłączyć font z Google Fonts?
Odwiedźmy stronę <a href="https://www.google.com/fonts">Google Fonts</a> i wybierzmy font. W naszym layoucie Planty wykorzystane zostały trzy różne rodziny fontów: <i>Playfair Display</i>, <i>Montserat</i> oraz <i>Muli</i>. Znajdziemy je na <a href="https://www.google.com/fonts">Google Fonts</a>. 
Fonty te poza tym, że mogą zostać podpięte pod naszą stronę, mogą także zostać ściągnięte i zainstalowane na naszych komputerach.
Jeśli <i>Playfair Display</i> został już znaleziony, należy kliknąć w ikonę <i>Quick use</i> zaznaczoną pomarańczowym kółkiem.

> ![](/images/googlefonts-quickuse.png "")

W punkcie 1. wybierzmy interesujące nas style danego kroju. W projekcie Planty będziemy korzystać z "Normal 400" oraz "Normal 400 Italic". W przypadkach, gdy współpracujemy z projektantami graficznymi zapytajmy o to, które style użyte są w projekcie.

> ![Layout do zakodowania](/images/googlefonts-styles.png "Layout do zakodowania")

Jeśli tworzymy stronę w języku polskim upewnijmy się czy font wyposażony jest w polskie znaki. Można to sprawdzić wpisując tekst w Google Fonts i obserwując jak te znaki są wyświetlane. Domyślnie font nie ma zaznaczonego checkboksa "Latin extended", który zawiera m.in. polskie znaki. 


Pamiętajmy, żeby zaznaczyć tę opcję, jeśli ich potrzebujemy. W przypadku Planty możemy zostawić opcję domyślną (teksty są w języku angielskim).


Zgodnie z tym, co znajdziesz w punkcie 3 - należy umieścić poniższy tag w sekcji` <head>`.
```html
<link href='https://fonts.googleapis.com/css?family=Playfair+Display:400,400italic&subset=latin,latin-ext' rel='stylesheet' type='text/css'>
```
Dzięki znacznikowi link, podłączyliśmy do naszej strony font "Playfair Display", ale na samej stronie nic się nie zmieniło - ciągle wyświetlany jest domyślny font systemowy. Pozostało jeszcze podpięcie wybranego fonty do arkusza stylów. Dzieję się to dzięki właściwości `font-family`. W punkcie 4. na stronie Google Fonts znajdziemy nazwę fontu, którą trzeba zastosować. 

```css
ul li {
	font-family: 'Playfair Display', serif;
}
```
Zastanówmy się jeszcze co oznacza wartość `'Playfair Display', serif;` i dlaczego występuje tam nazwa `serif`. 
Otóż jeśli nie zostanie znaleziony font o nazwie `'Playfair Display'` (np. nie dołączymy do naszego kodu skryptu ze strony Google Fonts), to przeglądarka wyświetli dowolny, dostępny font szeryfowy właśnie dzięki wartości `serif`. 
Deklarację możemy też rozbudować o większą liczbę krojów, np.

```css
ul li {
	font-family: 'Playfair Display', 'Georgia', serif;
}
```
Co oznacza - wyświetl font 'Playfair Display', jeśli nie jest to możliwe, to wyświetl font 'Georgia', jeśli 'Georgia' nie została znaleziona to wyświetl dowolny font szeryfowy.


Teraz możemy sprawdzić czy nasza lista na stronie Planty zmieniła font. W celu weryfikacji dla elementu listy odznaczmy właściwość `font-family` w Narzędziach Developerskich. Czy zaobserwowaliście zmianę fontu?

> #### Exercise::Ćwiczenie 9
>
> Pora na podłączenie pozostałych dwóch fontów do Planty - są to <i>Muli (Normal 400)</i> oraz <i>Montserrat (Bold 700)</i>. Po podłączeniu fontów, przejdź do pliku CSS i przypisz paragrafom font <i>Muli</i>, natomiast tekstowi "because we care for plants" font <i>Montserrat</i>, tak żeby osiągnąc poniższy efekt: 

> ![Podłączone fonty: Muli, Montserrat oraz Playfair Display](/images/googlefonts-layout.png "Podłączone fonty: Muli, Montserrat oraz Playfair Display")
>Renderowanie fontów może nieco różnić się w zależności od przeglądarki, więc nie przejmuj się na razie, jeśli u Ciebie fonty wyglądają na "cieńsze" lub "bardziej tłuste". Pomińmy też na tym etapie wielkości fontów.
>

Możesz dodawać dowolną ilość niesystemowych fontów. Pamiętaj jednak, że fonty ładowane są wraz z ładowaniem strony internetowej. Przy wolniejszym transferze internetowym zauważyć można doładowywanie fontów.