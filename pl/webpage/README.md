# Co zawiera strona internetowa?

W poprzednim rozdziale wspomnieliśmy o edycji tekstu w Wordzie i formatowaniu. Jak pewnie zauważyliście, strony internetowe mają trochę wspólnego z tekstem zapisanym w [RTF](https://pl.wikipedia.org/wiki/Rich_Text_Format): można na nich wyróżnić nagłówki, główny tekst i ilustracje. Zwykle nie są też monochromatyczne – tekst może występować w różnych kolorach i krojach.

Skoro występuje tyle podobieństw – mógłbyś zapytać – czemu nie piszemy stron w programach typu Word? Skąd w ogóle potrzeba używania tych wszystkich edytorów tekstowych, o których była mowa w poprzednim rozdziale? Czemu tworzenie stron internetowych jest na tyle złożone, żeby zatrudniać w tym celu specjalistów albo zapisywać się na klikunastogodzinne kursy?

## Dokumenty HTML, czyli jaki język rozumie przeglądarka?

Zdążyliśmy już wspomnieć, że dokumenty, które mają być otwierane przez przeglądarkę, powinny być zapisywane w specjalnym formacie (`*.html`). Czym on się różni od zwykłego tekstu? Przecież zawartość naszego pliku jak dotąd była tylko zwykłym tekstem! Jak zatem "powiedzieć" przeglądarce, żeby został sformatowany w określony przez nas sposób?

### Język HTML

HTML jest to specjalny język znaczników, które umożliwiają nam określenie ról naszych elementów na stronie. Możemy za jego pomocą przekazać, że dany elemenent będzie nagłówkiem, akapitem bądź obrazkiem.

Jak pewnie już wiesz, strony internetowe nie składają się tylko z bloków tekstu. Zwykle zawierają też nawigację, nagłówek, stopkę, odnośniki do innych stron, itd. W tych przypadkach HTML także okazuje się bardzo przydatny.

Właściwie możemy myśleć o naszych elementach strony jak o <i>klockach lego</i>, z których będziemy budować. Każdy taki "klocek" musi być zapisany w specjalny sposób. Nasze elementy opisywane są przez <b>tagi HTML</b>. Jak wygląda przykładowy tag?

```html
<element>
```

Oto właśnie nasz pojedynczy tag. Jest on otoczony nawiasami trójkątnymi: otwierającym `<` i zamykającym `>`. Umożliwia to przeglądarce określenie, że właśnie w tym miejscu znajduje się nasz element i może ona określić jego przeznaczenie.

Co bardzo ważne, większość elementów musi być zawarta między **otwierającymi** i **zamykającymi** tagami. Tagi zamykające zawierają charakterystyczny `/`:

```html
<element>Tutaj znajduje się treść.</element>
```

Poszczególne elementy HTML mogą być zwykle zagnieżdżane jeden wewnątrz drugiego, na przykład:

```html
<element>
  Jestem rodzicem.
  <element>
    Jestem dzieckiem.
  </element>
</element>
```

Warto już tutaj zaznaczyć, że nie wszystkie elementy wymagają tagów zamykających. Nie można też zagnieżdżać wewnątrz nich innych elementów. Są to tak zwane <i>puste elementy</i>. Które to konkretnie, dowiecie się już niedługo w rozdziale zapoznającym z tajnikami HTML.

```html
<empty>
```

Elementy mogą również zawierać <i>atrybuty</i>. Atrybuty elementów zapisywane są w ten sposób:

```html
<element attribute="value"></element>

<empty attribute="otherValue">
```

### Separacja zawartości i prezentacji

Zanim zabierzesz się do pisania swojego pierwszego kodu, warto wspomnieć o bardzo ważnej regule, która obowiązuje programistów stron internetowych, a jest nią **separacja zawartości i prezentacji**.

Dowiedzieliśmy się już, że język HTML służy do opisu treści stron internetowych. Nie zawiera on żadnych informacji o tym, jak powinna wyglądać nasza strona. Aby nadać jej nasz wymarzony wygląd, musimy stworzyć "skórkę". W programowaniu WWW do tego celu służą <b>kaskadowe arkusze stylów</b>, czyli <b>CSS</b> (ang. <i>Cascading Style Sheets</i>).

> #### Important::Ważne
>
>Istnieje możliwość deklarowania stylów bezpośrednio w kodzie HTML (za pomocą atrybutu `style`):
>```html
<div style="color:red;"></div>
```
>Nie jest to jednak dobrą praktyką, ponieważ kod opisujący prezentację strony jest ściśle powiązany z kodem opisującym jej treść. Dużo łatwiej wprowadzać zmiany w wyglądzie strony oraz utrzymywać kod, kiedy te dwie warstwy są logicznie od siebie oddzielone. To właśnie nazywamy **separacją zawartości i prezentacji**.
>
>Style piszemy w osobnych plikach z rozszerzeniem `*.css` i dołączamy do naszego dokumentu HTML w specjalny sposób. Jak? Dowiesz się już niedługo!

### Język CSS

Język CSS różni się znacznie w zapisie od HTML. HTML pozwala nam stworzyć treść (strukturę) strony, natomiast CSS to lista reguł opisujących w jaki sposób jej elementy mają zostać wyświetlone przez przeglądarkę.

Składnia CSS operuje na <b>selektorach</b>. Za pomocą selektorów wybieramy elementy strony, którym chcemy nadać określony wygląd. Kod zapisuje się w sposób:

```css
selektor {
  właściwość: wartość;
}
```

Przykładowo:

```css
p {
  color: blue;
}
```

Powyższy kod ustawia kolor fontu na niebieski dla wszystkich elementów typu `p` (`p` to znacznik reprezentujący akapit, z angielskiego <i>paragraph</i>).
