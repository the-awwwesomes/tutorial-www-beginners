# Podstawowe znaczniki HTML

Właśnie napisaliście swój pierwszy kod HTML, gratulacje! Kiedy jednak spojrzycie na niego, poza podstawowym szkieletem zawiera on jednolity blok tekstu. Brakuje nam wyróżnienia nagłówków, hiperłączy, obrazka i formularzy. Pora na zapoznanie Was z różnymi znacznikami HTML.

Wiemy już, że aby uzyskać HTML-owy element należy "owinąć" go w <i>tagi</i> (<i>znaczniki</i>). Nie poznaliśmy jednak jak dotąd żadnych nazw znaczników, których moglibyśmy użyć na rzeczywistym przykładzie strony.

## Komentarze

Często bywa tak, że kod jednej strony edytuje przynajmniej kilku programistów. Zdarza się też, że trzeba wrócić do kodu, który został napisany dość dawno temu. W takich przypadkach bywa, że pojawiają się niejasności i pytania "Co autor miał na myśli?".

Pomocne dla nas bywają wtedy komentarze. Są one ignorowane przez przeglądarkę podczas wyświetlania strony i widoczne tylko podczas podglądania jej kodu źródłowego. Komentarze są bardzo użyteczne przy opisie kodu i umożliwiają jego dokumentowanie.

```html
<!-- To jest komentarz do naszego kodu -->
```

## Nagłówki i akapity

Tak samo, jak w dokumentach tekstowych, w HTML-u możemy zdefiniować nagłówki dla naszego tekstu:

```html
<h1>Nagłówek 1</h1>
<h2>Nagłówek 2</h2>
<h3>Nagłówek 3</h3>
<h4>Nagłówek 4</h4>
<h5>Nagłówek 5</h5>
<h6>Nagłówek 6</h6>
```

Co zostanie zinterpretowane przez przeglądarkę jako:

<div class="example-wrapper">
  <h1 style="margin-top:0">Nagłówek 1</h1>
  <h2>Nagłówek 2</h2>
  <h3>Nagłówek 3</h3>
  <h4>Nagłówek 4</h4>
  <h5>Nagłówek 5</h5>
  <h6>Nagłówek 6</h6>
</div>

> #### Important::Ważne
>
> Pamiętajcie, że numery nagłówków nie odnoszą się do rozmiaru wyrenderowanego tekstu, ale oznaczają **hierarchię** zawartości.

Przy okazji omawiania składni CSS napomknęliśmy o znaczniku `<p>`. Jego nazwa pochodzi od słowa <i>paragraph<i>, a on sam służy do definiowania akapitów w tekście.

```html
<p>To jest akapit tekstu. Możesz w nim umieścić tekst dowolnej długości.</p>
```

<div class="example-wrapper">
  <p>To jest akapit tekstu. Możesz w nim umieścić tekst dowolnej długości.</p>
</div>

Akapity zwykle prezentowane są w przeglądarce jako bloki tekstu, wizualnie odseparowane od siebie pionowym odstępem.

Kiedy kodujesz akapity, czasem zachodzi potrzeba złamania linii w określonym miejscu. Warto wiedzieć, że nie wystarczy tam wcisnąć <kbd>Enter</kbd> w edytorze tekstu – do łamania linii w HTML-u służy specjalny znacznik `<br>`:

```html
<p>Jestem bardzo długim tekstem, który nie mieści się w jednej linii, <br> zatem muszę zostać złamany.</p>
```

<div class="example-wrapper">
  <p>
    Jestem bardzo długim tekstem, który nie mieści się w jednej linii, <br>
    zatem muszę zostać złamany.
  </p>
</div>

> #### Important::Ważne
>
> Nie stosuj znacznika `<br>`, aby wizualnie odseparować od siebie elementy w pionie! HTML powinien być używany **wyłącznie do definiowania treści**. W tym przypadku należy nadać elementom **pionowe marginesy za pomocą CSS** (już niedługo dowiecie się dokładnie, jak to zrobić).

## Hiperłącza

Dzięki hiperłączom (czyli po prostu linkom) możemy przenieść się w niemal dowolne inne miejsce w sieci. Link możecie umieścić na stronie używając znacznika `<a>` (od angielskiego słowa <i>anchor</i>) i podając adres linkowanej strony jako wartość atrybutu `href`.

Można powiedzieć, że hiperłącza są solą Internetu!

```html
<a href="http://theawwwesomes.org" target="_blank">
  Przeniosę Cię na stronę The Awwwesomes otwierając ją w osobnej karcie przeglądarki!
</a>
```

<div class="example-wrapper">
  <a href="http://theawwwesomes.org" target="_blank">Przeniosę Cię na stronę The Awwwesomes!</a>
</div>

Użycie `target="_blank"` spowoduje, że strona, do której prowadzi Wasz link, zostanie otwarta w nowej karcie przeglądarki.

> #### Important::Ważne
>
> W Sieci trwa nieustanna debata nad tym, czy atrybut `target` i wymuszanie otwierania strony w nowej karcie powinny być używane. [Bardzo wiele osób](http://www.forumweb.pl/forumweb-pl/drobne-pomysly/516489#516489) wskazuje na fakt, że jest to [odbieranie kontroli użytkownikowi](https://kornel.ski/pl/target).

## Obrazki

Obrazki w kodzie wstawiamy za pomocą znacznika `<img>`. Jest on <i>pustym elementem</i> i nie posiada znacznika zamykającego. Dwa najważniejsze atrybuty, jakie może przyjmować `<img>` to:

- `src`, który zawiera ścieżkę do obrazka na dysku serwera lub w sieci. Jeśli wskazuje on na ścieżkę na dysku, zwykle jest to ścieżka względna – względem pliku HTML w którym znajduje się konkretny element `<img>`.

> #### Important::Ważne
>
> W tym momencie chcemy zwrócić Waszą uwagę na ścieżki do zasobów (nie tylko obrazków, niedługo zaczniemy dołączać do naszej strony arkusze stylów).
> **Ścieżka bezwzględna** to taka, która zawiera pełny adres internetowy do zasobu, wraz z domeną.
> ```html
 <img src="http://theawwwesomes.org/images/example.png" alt="Jestem obrazkiem ze ścieżką bezwzględną">
 ```
 > W zasadzie moglibyśmy w tym momencie zakończyć temat ścieżek i przestać zawracać sobie tym głowę. Jednak co się stanie, kiedy adres strony ulegnie zmianie? Musielibyśmy wtedy pozmieniać adresy do wszystkich obrazków na naszej stronie – bardzo dużo roboty!
 > Z pomocą przychodzi nam linkowanie za pomocą <b>ścieżek względnych</b>, czyli wskazywanie na położenie zasobu w systemie plików względem miejsca, w którym przechowujemy plik `html` z naszą stroną.
 > Najprostszym przykładem jest ten, w którym plik grafiki oraz plik ze stroną znajdują się w tym samym miejscu (folderze):
 > ```html
 <img src="example.png" alt="Jestem w tym samym folderze, co strona">
 ```
 > Jednak wrzucanie plików z różnymi zasobami do tego samego folderu mogłoby spowodować w krótkim czasie spory bałagan. Zwykle tworzymy specjalne podfoldery – osobny dla obrazków (możemy go nazwać np. `images`), dla plików ze stylami, dla skryptów JavaScript itp..
 > Spróbujmy w prosty sposób zobrazować strukturę katalogu plików (dla uproszczenia uwzględnimy tylko obrazki):
 > ```html
 /my-website
  |
  |-- index.html
  |-- /images
       |
       |--apples.png
       |--cherries.jpg
       |--bananas.svg
```
<img src="/images/img-path-examples.gif" class="image-full-width">

> W takim wypadku, chcąc wyświetlić na stronie obrazek przedstawiający jabłka, odwołamy się do niego w ten sposób:
> ```html
 <img src="images/apples.png" alt="Tu widzimy jabłka">
 ```
> Możemy się również odwoływać do zasobów znajdujących się w strukturze folderów "wyżej". Używamy wtedy w ścieżce charakterystycznych dwóch kropek `../`.
>
> Przykładowo: plik `index.html`, w którym piszemy kod html, znajduje się folderze `/html` umieszczonym w `/my-website`, a `/images` stanowi podfolder `/my-website`.
> ```html
 /my-website
  |-- /html
       |--index.html
  |-- /images
    |-- apples.png
    |-- cherries.jpg
    |-- bananas.svg
```
> Musimy wtedy wyjść z folderu `/html` o poziom wyżej, stosując "magiczne" dwie kropki, a następnie wejść do folderu z obrazkami. Być może brzmi to zawile, ale wszystko wyjaśni się jak zaczniecie testować ścieżki względne w praktyce.
> ```html
 <img src="../images/apples.png" alt="Tu widzimy jabłka">
 ```

> Natomiast jeśli chcemy cofnąć się jeszcze bardziej w głąb struktury katalogów stosujemy zapis:
> ```html
 <img src="../../images/apples.png" alt="Tu widzimy jabłka">
 ```
> i tak dalej.
> Ścieżki bezwględne będą bardzo przydatne np. przy podłączniu pliku, zawierającego style. Przetestujemy to już niebawem podczas nauki o CSS.

- `alt` służy do definiowania pomocniczego tekstu, który zostanie wyświetlony w przypadku, kiedy obrazek z różnych powodów nie zostanie poprawnie załadowany. Jest też używany przez <i>[czytniki ekranowe](https://pl.wikipedia.org/wiki/Czytnik_ekranowy)</i> do informowania osób niewidomych lub niedowidzących o zawartości konkretnej ilustracji. Tym samym `alt` jest jednym z **podstawowych elementów [<i>dostępności stron WWW</i>](https://pl.wikipedia.org/wiki/Dost%C4%99pno%C5%9B%C4%87_(WWW))**.

```html
<img src="images/example-img.jpg" alt="Uczymy się kodować">

<img src="images/example-img-broken.jpg" alt="Ten obrazek nie został poprawnie załadowany">
```

<div class="example-wrapper">
  <img src="/images/example-img.jpg" alt="Nasi niesamowici uczestnicy">
  <img src="/images/example-img-broken.jpg" alt="Ten obrazek nie został poprawnie załadowany">
</div>

## Listy

Za pomocą znacznika `<ul>` definiujemy listy nieuporządkowanych elementów, natomiast listy uporządkowane zamykamy wewnątrz znaczników `<ol>`:

```html
<ul>
  <li>Jestem elementem listy</li>
  <li>Jestem elementem listy</li>
  <li>Jestem elementem listy</li>
</ul>

<ol>
  <li>Jestem pierwszym elementem listy</li>
  <li>Jestem drugim elementem listy</li>
  <li>Jestem trzecim elementem listy</li>
</ol>
```

<div class="example-wrapper">
  <ul>
    <li>Jestem elementem listy</li>
    <li>Jestem elementem listy</li>
    <li>Jestem elementem listy</li>
  </ul>

  <ol>
    <li>Jestem pierwszym elementem listy</li>
    <li>Jestem drugim elementem listy</li>
    <li>Jestem trzecim elementem listy</li>
  </ol>
</div>

Pomimo, że najbardziej intuicyjnym (i oczywiście poprawnym) przypadkiem użycia list jest wyliczenie w tekście, znaczników listy możemy używać na przykład do definiowania elementów menu strony.

Powyżej przedstawiliśmy Wam najczęściej używane znaczniki – a to zdecydowanie [nie wszystkie](https://developer.mozilla.org/en/docs/Web/HTML/Element)! W kolejnych rozdziałach dowiecie się natomiast, jak kodować proste formularze oraz określać strukturę dokumentu.
