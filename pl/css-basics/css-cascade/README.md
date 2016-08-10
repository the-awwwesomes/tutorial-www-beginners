## Kaskadowość i dziedziczenie w CSS

W [rozdziale 8](../../css-code/README.md), przy okazji pokazania, jak dołączać arkusze stylów do strony, zwróciliśmy Waszą uwagę na kolejność dołączania plików. Niektórym z Was już pewnie w tamtym momencie zaświtało, że style dla naszej strony mogą pochodzić z różnych źródeł.

### Kaskada CSS

Co to znaczy, że style pochodzą z różnych źródeł? Czy na wygląd naszej strony wpływają też arkusze stylów z nieznanego nam miejsca, które są poza naszą kontrolą?

W gruncie rzeczy dokładnie tak się dzieje. Oprócz stylów, nad którymi pracujemy samodzielnie, na elementy na stronie mają wpływ również <b>domyślne style przeglądarki</b> (ang. <i>user agent stylesheets</i>) oraz <b>style zdefiniowane przez użytkownika</b>. Te pierwsze zdążyliście już zobaczyć w akcji podczas tworzenia "gołego" pliku HTML. Dokładnie, gdyby nie domyślne style, które nadaje przeglądarka, zawartość strony pomimo zastosowania różnych znaczników wyglądałaby jak jednolity blok zwykłego tekstu. Dzięki domyślnym stylom przeglądarki, nawet w wypadku, kiedy nie zostanie dołączony kod CSS stworzony przez autora strony, dla użytkownika wszystko będzie czytelne.

> #### Important::Ważne
>
> Warto w tym momencie zauważyć, że domyślne style różnych przeglądarek (Chrome, Firefox, Internet Explorer, Safari, itp.) różnią się nieco od siebie. W związku z tym, zanim zaczniemy aplikować własne style do naszego dokumentu, warto zadbać, aby zniwelować te różnice.
>
> Brzmi jak wyzwanie? Na szczęście, jak w wielu przypadkach w programowaniu, istnieje na to gotowe rozwiązanie. Społeczność programistów WWW jest bardzo duża oraz chętnie dzieli się wiedzą i doświadczeniem.
>
> W sieci można znaleźć sporo rozwiązań - do najpopularniejszych należą [`normalize.css`](https://necolas.github.io/normalize.css/) i [`reset.css`](http://meyerweb.com/eric/tools/css/reset/). Są to po prostu gotowe arkusze stylów, które należy dołączyć do naszej strony **przed** własnymi stylami. "Wyrównują" one wszelkie różnice pomiędzy domyślnymi stylami w różnych przeglądarkach, w związku z czym nie musimy już sobie zawracać głowy większością różnic między przeglądarkami.
>
> `normalize.css` i `reset.css` nieco się od siebie różnią w koncepcji działania:
> - `reset.css`, jak wskazuje nazwa, resetuje wszystkie domyślne style, w związku z czym wszystkie elementy (nagłówki, akapity, itp.) po jego zastosowaniu wyglądają jednakowo.
> - `normalize.css` normalizuje style – po zastosowaniu tego arkusza wciąż będzie widoczna np. hierarchia nagłówków. Nasze elementy HTML wciąż będą wizualnie rozróżnialne.
>
> Przypomnijmy jeszcze na koniec, że powyższe "normalizujące" arkusze stylów należy dołączać do naszego dokumentu HTML **w pierwszej kolejności**.

Na początku pracy ze stroną polecamy dołączyć do dokumentu style niwelujące różnice między przeglądarkami.

> #### Exercise::Ćwiczenie 10
>
> - Przejdź do folderu `layout`.
> - Przejdź do strony [`normalize.css`](https://necolas.github.io/normalize.css/) i kilknij <i>Download</i> (<i>Pobierz</i>). Skopiuj zawartość.
> - Utwórz w folderze `layout/styles` plik o nazwie `normalize.css` i wklej do niego skopiowane przed chwilą style.
> - Podłącz arkusz stylów `normalize.css` do `index.html` uważając na to, aby był zalinkowany **przed** Twoim własnym arkuszem stylów.

Style zdefiniowane przez użytkownika to dość rzadki przypadek. Warto jednak w tym momencie zauważyć, że istnieje taka możliwość, aby CSS został zdefiniowany po stronie użytkownika. Dobrym przykładem takich arkuszy stylów są te stosowane np. przez wtyczki przełączające stronę w tryb polepszonej czytelności (przydatny do czytania artykułów – usuwa z pola widzenia wszystkie "rozpraszacze").

Mając do dyspozycji style z różnych źródeł, w jaki sposób przeglądarka decyduje, które z reguł zastosuje dla danego elementu? Skrót CSS w języku angielskim rozwija się jako <i>Cascading StyleSheets</i>, co oznacza <i>kaskadowe arkusze stylów</i>.

<b>Kaskada</b> jest właściwością CSS, która decyduje, w jaki sposób określić ważność stylów pochodzących z różnych źródeł. Kolejność kaskady (zaczynając od stylów o najmniejszej ważności):

1. Zwykłe style domyślne przeglądarki.
2. Domyślne style przeglądarki z `!important`.
3. Zwykłe style zdefiniowane przez użytkownika.
4. Zwykłe style zdefiniowane przez programistę strony.
5. Style zdefiniowane przez programistę strony z użyciem `!important`.
6. Style zdefiniowane po stronie użytkownika z użyciem `!important`.

Czym jest `!important`, dowiemy się niebawem, już w kolejnym rozdziale.

### Dziedziczenie stylów

Wykonując ćwiczenie 8 zauważyliście, że udało Wam się pokolorować tekst na całej stronie używając tylko selektora `body`.

```css
body {
  color: #f14b5c;
}
```

Mimo, że nie odwoływaliśmy się <i>bezpośrednio</i> do poszczególnych akapitów i nagłówków za pomocą selektorów, w pewien magiczny sposób uzyskały one ten sam kolor co `body`.

Cechę CSS, dzięki której wartości poszczególnych właściwości są przekazywane od elementu rodzica do elementu dziecka, nazywamy <b>dziedziczeniem</b>. Zademonstrujmy to na przykładzie:

```html
<h1>Jestem przykładowym nagłówkiem</h1>

<div class="inheritance-example">
  <p>Jestem akapitem tekstu, który odziedziczy kolor po rodzicu.</p>
  <p>Ja również zostanę pokolorowany.</p>
</div>

<p>Jestem przykładowym tekstem, który nie zostanie pokolorowany.</p>
```

```css
.inheritance-example {
  color: deeppink;
}
```

<div class="example-wrapper">
  <h1>Jestem przykładowym nagłówkiem</h1>
  <div style="color:deeppink;">
    <p style="color:deeppink;">Jestem akapitem tekstu, który odziedziczy kolor po rodzicu.</p>
    <p style="color:deeppink;">Ja również zostanę pokolorowany.</p>
  </div>
  <p>Jestem przykładowym tekstem, który nie zostanie pokolorowany.</p>
</div>

<a href="http://codepen.io/theawwwesomes/pen/GqONLB" class="codepen-link">Edytuj na CodePen</a>

Nie wszystkie właściwości CSS są dziedziczone. Nie dzieje się tak na przykład w przypadku ramek, co jest zresztą dość intuicyjne. Spróbujcie sobie tylko wyobrazić, jakby wyglądałby efekt, gdyby dodano obramowanie do `body` a pozostałe elementy dziedziczyły tę właściwość! Poniżej podajemy, które ze znanych już Wam właściwości są dziedziczone, a które nie.

Właściwości, które są dziedziczone:

- `color`
- `font-family`
- `font-size`
- `font-style`
- `font-weight`
- `text-align`

Właściwości, które nie są dziedziczone:

- `background`
- `border`
- `margin`
- `padding`
- `width`
- `height`
