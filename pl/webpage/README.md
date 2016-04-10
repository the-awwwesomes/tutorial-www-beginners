# Co zawiera strona internetowa?

W poprzednim rozdziale wspomnieliśmy o edycji tekstu w Wordzie i formatowaniu. Jak pewnie zauważyłeś, strony internetowe mają trochę wspólnego z takim sformatowanym tekstem: można na nich wyróżnić nagłówki, główny tekst i ilustracje. Zwykle nie są też monochromatyczne - tekst może występować w różnych kolorach i krojach. 

Skoro występuje tyle podobieństw - mógłbyś zapytać - czemu nie piszemy stron w programach typu Word, skąd w ogóle potrzeba używania tych wszystkich edytorów tekstowych, o których była mowa w poprzednim rozdziale? Czemu tworzenie stron internetowych jest na tyle złożone, żeby zatrudniać w tym celu specjalistów albo zapisywać się na klikunastogodzinne kursy?

## Dokumenty HTML, czyli jaki język rozumie przeglądarka?

Zdążyliśmy już wspomnieć, że dokumenty, które mają być otwierane przez przeglądarkę powinny być zapisywane w specjalnym formacie (`*.html`). Czym on się różni od zwykłego tekstu? Przecież zawartość naszego pliku jak dotąd była tylko zwykłym tekstem!

Wróćmy do naszego przykładu czyli strony [grafmag.pl](http://grafmag.pl/). Przyjrzyjmy się stronie z artykułem i spróbujmy wyróżnić poszczególne elementy strony. Artykuł składa się z nagłówka, ilustracji oraz treści, która to składa się z paragrafów tekstu rozdzielonych nagłówkami niższego rzędu.

Przyjrzyj się ilustracji:

Wyróżniliśmy tutaj elementy według ich przeznaczenia na stronie. Skoro kod strony internetowej zapisany jest zwykłym tekstem, jak "powiedzieć" przeglądarce, żeby został sformatowany w określony przez nas sposób?

### Język HTML

HTML jest to specjalny język znaczników, które umożliwiają nam określenie roli naszych elementów na stronie. Możemy za jego pomocą przekazać, że dany elemenent będzie nagłówkiem, paragrafem tekstu bądź obrazkiem. 

Jak pewnie już wiesz, strony internetowe nie składają się tylko z bloków tekstu, zwykle zawierają też nawigację, nagłówek, stopkę, odnośniki do innych stron, itd. W tych przypadkach HTML także okazuje się bardzo przydatny.

Właściwie możemy myśleć o naszych elementach strony jak o *klockach lego* z których będziemy budować. Każdy taki "klocek" musi być zapisany w specjalny sposób. Nasze elementy opisywane są przez **tagi HTML**. Jak wygląda przykładowy tag?

```html
<element>
```

Oto właśnie nasz pojedynczy tag - musi on być zamnknięty i otwarty przez specjalne nawiasy trójkątne. Umożliwia to przeglądarce określenie, że właśnie w tym miejscu znajduje się nasz element i może określić jego przeznaczenie.

Co bardzo ważne, większość elementów musi być zawarta między **otwierającymi** i **zamykającymi** tagami. Tagi zamykające zawierają charakterystyczny `/`:

```html
<element>Tutaj znajduje się treść.</element>
```

Warto już tutaj zaznaczyć, że nie wszystkie elementy wymagają tagów zamykających - są to tzw. *puste elementy*. Które to konkretnie, dowiecie się już niedługo w rozdziale zapoznającym z tajnikami HTML.

Poszczególne elementy HTML mogą być zagnieżdżane jeden wewnątrz drugiego, na przykład:

```html
<element>
  Jestem rodzicem.
  <element>
    Jestem dzieckiem.
  </element>
</element>
```

Elementy mogą również zawierać *atrybuty*. Atrybuty elementów zapisywane są w ten sposób:

```html
<element attribute="value">
```

### Separacja zawartości i prezentacji

Zanim zabierzesz się do pisania swojego pierwszego kodu warto wspomnieć o bardzo ważnej regule, która obowiązuje programistów stron internetowych, a jest nią **separacja zawartości i prezentacji**.

Dowiedzieliśmy się już, że język HTML służy do opisu treści stron internetowych. Nie zawiera on żadnych informacji o tym, jak powinna wyglądać nasza strona. Aby nadać jej nasz wymarzony wygląd musimy stworzyć "skórkę". W programowaniu WWW do tego celu służą **kaskadowe arkusze styli**, czyli **CSS** (Cascading Style Sheets).

> #### Important::Ważne
>
>Istnieje możliwość deklarowania styli bezpośrednio w kodzie HTML (za pomocą atrubutu `style`). Nie jest to jednak dobrą praktyką, ponieważ kod opisujący prezentację strony jest ściśle powiązany z kodem opisującym jego treść. Dużo łatwiej wprowadzać zmiany w wyglądzie strony oraz utrzymywać kod, kiedy te dwie warstwy są logicznie od siebie oddzielone - to właśnie nazywamy **separacją zawartości i prezentacji**.
>
>Style piszemy w osobnych plikach z rozszerzeniem `*.css` i dołączamy do naszego dokumentu HTML w specjalny sposób. Jak? Dowiesz się już niedługo!

### Język CSS

Język CSS różni się znacznie w zapisie od HTML. HTML to język znaczników, natomiast CSS to po prostu lista reguł opisujących w jaki sposób dany element ma zostać wyświetlony przez przeglądarkę. 

Składnia CSS operuje na **selektorach**. Za pomocą selektorów wybieramy elementy HTML i nadajemy im *style*. Wygląda to w następujący sposób:

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

Ustawia kolor fontu na niebieski dla wszystkich elementów `p`.
