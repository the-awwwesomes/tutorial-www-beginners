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

Wcześniej wspomnieliśmy o formatowaniu naszych elementów. Czy HTML bezpośrednio wpływa na wygląd naszych elementów? 

### Separacja zawartości i prezentacji

Zanim zabierzesz się do pisania swojego pierwszego kodu warto wspomnieć o bardzo ważnej regule, która obowiązuje programistów stron internetowych, a jest nią właśnie *separacja zawartości i prezentacji*.

Przez zawartość rozumiemy tutaj samą treść dokumentu.

Dlaczego jest to takie ważne?

