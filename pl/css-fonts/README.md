# Dołączanie krojów pisma (fontów)

Pora na chwilę oddechu - nauczymy się wreszcie dołączać inne kroje pisma.

Kolory i typografia niewątpliwie wpływają na charakter strony i to jak ją odbieramy. Całe szczęście dołączanie różnych, niestandardowych krojów pisma stało się możliwe i całkiem proste. 

Zanim jednak zaczniesz szukać odpowiedniego kroju, musisz pamiętać, że jedynie fonty zapisane w formatach będą renderowane w przeglądarce internetowej. 
Pamiętaj, że fakt, iż posiadasz dany font u siebie lokalnie na komputerze i jest on odpowiednio wyświetlany u Ciebie na komputerze nie znaczy, że będzie się on poprawnie wyświetlać u innych użytkowników. Cała magia twki w tym, by font został wyrenderowany, pomimo iż użytkownicy nie mają danego fontu u siebie w systemie. W tym celu najlepiej korzystać z Google Fonts lub fontów webowych, których pliki należy 

Obecnie istnieje wiele portali, które darmowo udostępniają bardzo wiele różnych <i>fontów</i>. Jednym z najczęściej używanych jest <a href="https://www.google.com/fonts">Google Fonts</a>.

## Jak podłączyć font z Google Fonts?
Odwiedź stronę <a href="https://www.google.com/fonts">Google Fonts</a> i wybierz font. W naszym layoucie Planty wykorzystane zostały trzy różne rodziny fontów: <i>Playfair Display</i>, <i>Montserat</i> oraz <i>Muli</i>. Znajdzimy je na <a href="https://www.google.com/fonts">Google Fonts</a>. 
Fonty z Google Fonts poza tym, że mogą zostać podpięte pod naszą stronę, możesz również ściągnąć na swój komputer.
Jeśli znalazłeś już <i>Playfair Display</i> należy kliknąć w <i>Quick use</i> zaznaczoną pomarańczowym kółkiem.

> ![](/images/googlefonts-quickuse.png "")

W punkcie 1. wybierz interesujące Cię style. W projekcie Planty będziemy korzystać z "Normal 400" oraz "Normal 400 Italic". W przypadkach, gdy współpracujesz z projektantem graficznym zapytaj o to, które style zawarte są w projekcie.

> ![Layout do zakodowania](/images/googlefonts-styles.png "Layout do zakodowania")

Jeśli tworzysz stronę w języku polskim upewnij się czy font wyposażony jest w polskie znaki. Możesz to sprawdzić wpisując tekst w Google Fonts i obserwując jak te znaki są wyświetlone. Domyślnie font nie ma zaznaczonego checkboksa "Latin extended", które zawiera polskie znaki. 



Pamiętaj, żeby zaznaczyć tę opcję, jeśli potrzebujesz polskich znaków. W przypadku Planty możemy zostawić opcję domyślną.


Zgodnie z tym, co znajdziesz w punkcie na stronie z danym fontem na Google Fonts, należy umieścić poniższy tag w sekcji <head>.
```html
<link href='https://fonts.googleapis.com/css?family=Playfair+Display:400,400italic&subset=latin,latin-ext' rel='stylesheet' type='text/css'>
```
Dzięki znacznikowi link, podłączyliśmy do naszej strony font "Playfair Display", ale na stronie nic się nie zmieniło - ciągle wyświetlany jest domyślny font systemowy. Należy podpiąć jeszcze wybrany font do arkusza stylów. Dzieję się to dzięki właściwości `font-family`. W punkcie 4. na stronie Google Fonts znajdziesz nazwę fontu, której należy użyć. 

``` html
ul li {
	font-family: 'Playfair Display', serif;
}
```

Teraz możesz sprawdzić czy nasza lista na stronie Planty zmieniła font. Dla porównania dla elementu listy odznacz właściwość `font-family` w Narzędziach Developerskich. Czy zauważasz zmianę fontu?

> #### Exercise::Ćwiczenie 8
>
> Pora na podłączenie pozostałych dwóch fontów do Planty - są to <i>Muli (Normal 400)</i> oraz <i>Montserrat (Bold 700)</i>. Po podłączeniu fontów, przejdź do pliku CSS i nadaj paragrafom font <i>Muli</i>, natomiast tekstowi "because we care for plants" font <i>Montserrat</i>. 
Żeby osiągnąc poniższy efekt: 

> ![Podłączone fonty: Muli, Montserrat oraz Playfair Display](/images/googlefonts-layout.png "Podłączone fonty: Muli, Montserrat oraz Playfair Display")
>Renderowanie fontów może nieco różnić się w zależności od przeglądarki, więc nie przejmuj się na razie, jeśli u Ciebie fonty są "cieńsze" lub "bardziej tłuste". Pomińmy też tym etapie wielkości fontów.
>

Możesz dodawać dowolną ilość niesystemowych fontów. Pamiętaj jednak, że fonty ładowane są wraz z ładowaniem strony internetowej. Im jest ich więcej, tym wolniej strona będzie się ładować. Przy wolniejszym transferze internetowym zauważyć można doładowywanie fontów.












