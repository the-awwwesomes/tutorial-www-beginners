# Narzędzia dewelopera stron internetowych

Zanim przystąpicie do pisania pierwszych linijek kodu zaprzyjaźnijcie się z podstawowymi narzędziami kodera, czyli edytorem tekstu oraz przeglądarką!

## Edytor tekstowy

Czy do kodowania stron będzie nam potrzebny jakiś specjalny rodzaj edytora? Być może moglibyśmy użyć do tego na przykład Worda, który przydaje się często do tworzenia dokumentów? Niestety, programy typu Word zapisują tekst w specjalny sposób, który umożliwia formatowanie tekstu (czyli m.in. zmianę wielkości, koloru albo kroju fonta) - jest to tzw. *[RTF (Rich Text Format)](https://pl.wikipedia.org/wiki/Rich_Text_Format)*.

Wasz kod natomiast musi być zapisany w postaci **zwykłego tekstu** (*plain text*), w związku z tym Word na pewno nie będzie dobrym wyborem jako edytor!.

Prostą stronę internetową możecie zakodować używając Notatnika lub innej domyślnej aplikacji, która umożliwia edycję zwykłych plików tekstowych. Nie jest to jednak najlepszy pomysł w dzisiejszych czasach. Pokażemy Wam, że używanie nieco bardziej zaawansowanych narzędzi nie jest takie straszne, a może bardzo ułatwić pracę.

Kiedy już bardzo się wprawicie w programowaniu stron, na pewno Wasze potrzeby w stosunku do edytora kodu wzrosną - zarówno odnośnie wydajności jak i funkcjonalności. Zwykle w swojej codziennej pracy programiści korzystają z tzw. *IDE* (*Integrated Development Environment*, czyli **zintegrowanego środowiska programistycznego**), które potrafi bardzo przyspieszyć pracę. W tej chwili jednak nie musicie zajmować sobie tym głów!

> #### Exercise::Ćwiczenie 1
>
>- Utwórz w dowolnym miejscu na dysku folder, w którym będziesz przechowywać efekty swojej pracy. 
>- Możesz go nazwać np. `the-awwwesomes`, a wewnątrz utworzyć podfolder `exercise-1` jako miejsce dla naszego pierwszego ćwiczenia.
>- Otwórz Notatnik i utwórz w nim plik tekstowy o dowolnej zawartości (na przykład: `Witaj świecie!`).
>- Zapisz ten plik w utworzonym przed chwilą folderze pod nazwą `index.html`. Dokładnie tak! Zwróć uwagę, że nie zapisujemy go pod zwykłym rozszerzeniem `*.txt`.Chcemy w ten sposób zaznaczyć, że jest to specjalny plik, który może odczytać przeglądarka interentowa. O tym, czym tak naprawdę jest HTML opowiemy szerzej w kolejnym rozdziale.
>- Otwórz plik `index.html` w przeglądarce i obejrzyj efekt swojej pracy!

## Sublime Text, czyli Twoje środowisko pracy

Na początek polecamy [Sublime Text](https://www.sublimetext.com/3) - pobierzcie ze strony wersję odpowiednią dla Waszego systemu operacyjnego i zainstalujcie. Sublime Text, oprócz edycji kodu umożliwia m.in. podgląd struktury projektu oraz podświetlanie kodu. 

> #### Exercise::Ćwiczenie 2
>
>- Po zainstalowaniu otwórz Sublime Text.
>- Z menu wybierz `Plik -> Otwórz folder...` i przejdź do folderu, w którym zapisałeś przed chwilą `index.html`
>- Po lewej zobaczysz widok struktury folderu. Rozwijając folder możesz zobaczyć jego zawartość, czyli jak na razie jest to tylko `index.html`. Możesz otworzyć go w widoku edycji po lewej (klikając dwukrotnie na jego nazwę).

## Narzędzia dewelopera w przeglądarce stron internetowych

Być może kiedyś, kiedy korzystaliście z jakiejś aplikacji na swoim komputerze lub smartfonie kusiło Was, aby podejrzeć jej kod. Jeśli akurat nie było to otwarte oprogramowanie, to treść tego kodu pozostała tajemnicą dla Was, jako zwykłych użytkowników.

Ze stronami internetowymi sytuacja przedstawia się nieco inaczej. Będąc zwykłym odbiorcą, który czyta wiadomości przy śniadaniu, możecie podejrzeć kod strony i zobaczyć, w jaki sposób została zakodowana! Niemożliwe? Wchodząc na dowolną stronę, klikając prawym przyciskiem myszy ukaże się menu kontekstowe. W tym menu powinna znajdować się pozycja `Wyświetl źródło strony` (lub `Pokaż źródło strony`, w zależności od przeglądarki). Po kliknięciu na nią Waszym oczom powinien ukazać się wtedy blok kodu źródłowego strony. To jednak nie koniec możliwości przeglądarki w badaniu kodu stron.

Praca programisty byłaby prosta, a jego życie usłane różami, gdyby wszystkie linijki kodu działały prawidłowo, a rezultaty były przewidywalne. Niestety, jak pewnie się domyślacie tak nie jest. Kiedy kod nie działa tak, jak trzeba, bardzo przydatna jest wiedza na temat tego, jak znaleźć przyczynę błędu. Proces szukania błędów w kodzie nazywamy [debugowaniem](https://pl.wikipedia.org/wiki/Debugowanie).

> #### Important::Ważne
>
>Koder stron w swojej pracy do debugowania używa narzędzi deweloperskich wbudowanych w przeglądarkę. Aby z nich skorzystać, wystarczy wcisnąć F12 kiedy wyświetlacie dowolną stronę. Oto, jak narzędzia deweloperskie wyglądają w najpopularniejszych przeglądarkach:
>
>- Chrome:
>
>![Narzędzia dewelopera Chrome](/images/chrome-devtools.png "Narzędzia dewelopera Chrome")
>
>- Firefox:
>
>![Narzędzia dewelopera Firefox](/images/ff-devtools.png "Narzędzia dewelopera Firefox")
>
>- Internet Explorer:
>
>![Narzędzia dewelopera Internet Explorer](/images/ie-devtools.png "Narzędzia dewelopera Internet Explorer")

Dla ustalenia uwagi od tej pory skupimy się na narzędziach deweloperskich w Chrome. Jak widać, wszystkie z powyższych są do siebie podobne (również w funkcjonalności), jednak naszym zdaniem Google Chrome oferuje najwygodniejsze i najbardziej funkcjonalne narzędzia.

### Jak poruszać się w narzędziach deweloperskich?

Dopóki nie posiadacie wiedzy na temat kodu HTML i CSS, poruszanie się w *devtoolsach* może wydawać się Wam prawdziwą *czarną magią*. Na początek pokażemy Wam tylko najbardziej podstawowe funkcjonalności, a wraz z nabywaniem nowych umiejętności będziecie się już coraz sprawniej odnajdować w korzystaniu z narzędzi programistycznych.

Zauważyliście pewnie, że *devtoolsy* zawierają dużo przycisków i zakładek. Jednak na potrzeby warsztatów i kodowania tylko w HTML i CSS będziemy korzystać właściwie tylko z jednej - *Elementy* (*Elements*).

Wejdźcie na swoją ulubioną stronę (może to być portal z wiadomościami albo Facebook) i za pomocą F12 otwórzcie narzędzia deweloperskie. W sekcji po prawej możecie zobaczyć narzędzie *Inspektor kodu HTML*. Spróbujcie chwilę poeksperymentować i wypróbować intuicyjnie jego możliwości. Na pewno zauważycie, że po najechaniu myszą na jedną z *gałęzi* podświetlony zostanie odpowiadający jej element na stronie.

W lewym górnym rogu widnieje ikonka - po jej kliknięciu uruchomicie *tryb inspektora*. W tym trybie możecie wybierać elementy bezpośrednio na stronie i podglądać ich kod w narzędziach deweloperskich. Oprócz kodu HTML można w ten sposób badać również style CSS. Służy do tego sekcja po prawej stronie. Więcej na temat badania styli dowiecie się w rozdziałach poświęconych językowi CSS.

Podsumowując, od tej pory Waszymi przyjaciółmi staną się edytor tekstowy i narzędzia deweloperskie! Nie obawiajcie się używać ich, aby podglądać i weryfikować efekty swojej pracy.