# Kaskadowość i dziedziczenie w CSS

Właśnie postawiliście swoje pierwsze kroki w stylowaniu dokumentu HTML - gratulujemy! Z pewnością rozbudziło to Wasze apetyty na więcej, ale też zrodziło nieco pytań i wątpliwości. 

W [rozdziale 8](../css-code/README.md) - przy okazji pokazania, jak dołączać arkusze styli do strony - zwróciliśmy Waszą uwagę na kolejność dołączania plików. Niektórym z Was już pewnie w tamtym momencie zaświtało, że style dla naszej strony mogą pochodzić z różnych źródeł.

## Kaskada CSS

Co to znaczy, że style pochodzą z różnych źródeł? Czy na wygląd naszej strony wpływają też arkusze styli z nieznanego nam miejsca, które są poza naszą kontrolą?

W gruncie rzeczy dokładnie tak się dzieje. Oprócz styli, nad którymi pracujemy samodzielnie, na elementy na stronie mają wpływ również **domyślne style przeglądarki** (ang. *user agent stylesheets*) oraz **style zdefiniowane przez użytkownika**. Te pierwsze zdążyliście już zobaczyć w akcji podczas tworzenia "gołego" pliku HTML. Dokładnie - gdyby nie domyślne style, które nadaje przeglądarka, zawartość strony pomimo zastosowania różnych znaczników wyglądałaby jak jednolity blok zwykłego tekstu. Dzięki domyślnym stylom przeglądarki, nawet w wypadku, kiedy nie zostanie dołączony kod CSS stworzony przez autora strony, dla użytkownika wszystko będzie czytelne.

> #### Important::Ważne
>
> Warto w tym momencie zauważyć, że domyślne style różnych przeglądarek (Chrome, Firefox, Internet Explorer, Safari, itp.) różnią się nieco od siebie. W związku z tym, zanim zaczniemy aplikować własne style do naszego dokumentu, warto zadbać, aby zniwelować te różnice.
>
> Brzmi jak wyzwanie? Na szczęście, jak w wielu przypadkach w programowaniu, istnieje na to gotowe rozwiązanie. Społeczność programistów WWW jest bardzo duża i chętnie dzieli się wiedzą i doświadczeniem. 
>
> W sieci można znaleźć sporo rozwiązań - do najpopularniejszych należą [`normalize.css`](https://necolas.github.io/normalize.css/) i [`reset.css`](http://meyerweb.com/eric/tools/css/reset/). Są to po prostu gotowe arkusze styli które należy dołączyć do naszej strony **przed** własnymi stylami. "Wyrównują" one wszelkie różnice w związku z czym nie musimy już sobie zawracać głowy z większością różnic między przeglądarkami.
>
> `normalize.css` i `reset.css` nieco się od siebie różnią w koncepcji działania:
> - `reset.css`, jak wskazuje nazwa, resetuje wszystkie domyślne style, w związku z czym wszystkie elementy (nagłówki, paragrafy, itp.) po jego zastosowaniu wyglądają jednakowo.
> - `normalize.css` normalizuje style - po zastosowaniu tego arkusza wciąż będzie widoczna np.  hierarchia nagłówków. Nasze elementy HTML wciąż będą wizualnie rozróżnialne.
>
> Przypomnijmy jeszcze na koniec, że powyższe "normalizujące" arkusze styli należy dołączać do naszego dokumentu HTML **w pierwszej kolejności**.

Style zdefiniowane przez użytkownika to dość rzadki przypadek. Warto jednak w tym momencie zauważyć, że istnieje taka możliwość, aby CSS został zdefiniowany po stronie użytkownika. Dobrym przykładem takich arkuszy styli są te stosowane np. przez wtyczki przełączające stronę w tryb polepszonej czytelności (przydatny do czytania artykułów - usuwa z pola widzenia wszystkie "rozpraszacze").

Mając do dyspozycji style z różnych źródeł, w jaki sposób przeglądarka decyduje, które z reguł zastosuje dla danego elementu? Skrót CSS w języku angielskim rozwija się jako *Cascading StyleSheets*, co oznacza *kaskadowe arkusze styli*. 

**Kaskada** jest właściwością CSS, która decyduje, w jaki sposób określić ważność styli pochodzących z różnych źródeł. Kolejność kaskady (zaczynając od styli o najmniejszej ważności):

1. Zwykłe style domyślne przeglądarki
2. Domyślne style przeglądarki z `!important`
3. Zwykłe style zdefiniowane przez użytkownika
4. Zwykłe style zdefiniowane przez programistę strony
5. Style zdefiniowane przez programistę strony z użyciem `!important`
6. Style zdefiniowane po stronie użytkownika z użyciem `!important`

Co to takiego jest `!important` dowiemy się jeszcze w tym rozdziale - już niebawem.

## Dziedziczenie styli