# Co dalej?

Gratulacje! Udało się Wam dotrzeć do końca tutoriala, naprawdę jesteśmy z Was dumni. Mamy nadzieję, że nauka HTML i CSS dała Wam sporo satysfakcji i okaże się przydatna w Waszych projektach lub pracy.

Jednak to jeszcze nie koniec. Zakres naszego tutoriala obejmuje podstawy kodowania w HTML i CSS, a do momentu zostania "pełnoprawnymi" frontend developerami czeka Was jeszcze sporo pracy. Kolejnym kamieniem milowym jest z pewnością zapoznanie się z tajnikami języka JavaScript, który umożliwi Wam między innymi tworzenie interaktywnych efektów, a także łączenie się i wymianę danych z backendem strony.

Zatem jakie wyzwania teraz na Was czekają?

## HTML i CSS

W tym zakresie macie już solidne podstawy (zakładając, że bardzo uważnie przerobiliście tutorial!). Mamy tu dla Was jedną radę: "ćwiczyć, ćwiczyć i jeszcze raz &ndash; ćwiczyć!". W [Dodatku III](../appendix/bonus-exercise/README.md) przygotowaliśmy dla Was kilka dodatkowych layoutów do samodzielnego zakodowania. Z pewnością możecie też przeszukać Internet &ndash; nietrudno znaleźć proste, darmowe szablony `psd` i spróbować przenieść je do kodu. 

W ramach naszego kursu zapoznaliśmy się z niektórymi tagami, dzięki którym można zakodować prostą, statyczną stronę. Część z nich pojawiła się niedawno (choć w świecie web developmentu to już spory kawał czasu!) w ramach standardu [HTML5](https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/HTML5). HTML5 można rozumieć dwojako:

- jako rozszerzenie specyfikacji HTML o nowe tagi oraz standardy kodowania,
- zbiór technologii, które umożliwiają tworzenie bardziej wydajnych i funkcjonalnych stron oraz aplikacji webowych.

Za każdym razem, kiedy próbujecie korzystać z ciekawej nowej technologii bądź triku w CSS, warto pamiętać o wsparciu dla różnych (niekoniecznie najnowszych) przeglądarek. Przypominamy Wam o stronie [caniuse.com](http://caniuse.com), na której w przejrzysty sposób zaprezentowane są dane na temat wsparcia danej technologii/właściwości CSS/tagu HTML przez przeglądarki oraz najczęściej występujące problemy. Polecamy zapoznać się z filozofią kodowania zwaną jako [<i>progressive enhancement</i>](https://en.wikipedia.org/wiki/Progressive_enhancement) (nie znamy ładnego polskiego odpowiednika). Jest to staranie się w trakcie tworzenia strony o zapewnienie minimalnej funkcjonalności użytkownikom starych przeglądarek bądź korzystających z wolnego połączenia i dalej uzupełnianie o ciekawe elementy wizualne oraz interakcje.

Przy okazji <i>progressive enhancement</i> warto wspomnieć o ważnym zagadnieniu, jakim jest <a href="https://pl.wikipedia.org/wiki/Dost%C4%99pno%C5%9B%C4%87_(WWW)">dostępność</a> stron internetowych. W trakcie tworzenia strony powinniśmy dbać o to, aby nie wykluczać żadnego z naszych odbiorców. Szczególnym przypadkiem są tu niepełnosprawni, na przykład niewidomi (którzy korzystają z czytników ekranu). Na początek polecamy Wam [artykuł, który podsumowuje absolutne podstawy tworzenia dostępnej strony](https://www.marcozehe.de/2015/12/14/the-web-accessibility-basics/). Co ciekawe, większość pracy sprowadza się do stworzenia poprawnego, semantycznego kodu HTML!

Kolejnym istotnym zagadnieniem jest nauczenie się zarządzania kodem w czasie. CSS jako język ma bardzo niską barierę wejścia i dość szybko można nauczyć się podstaw oraz zakodować elegancką, prostą stronę. Zapewne zdążyliście to zauważyć podczas warsztatów. Jednak w praktyce często zdarza się, że trzeba pracować nad większą bazą kodu wraz z zespołem programistów. CSS wraz ze swoją kaskadą i specyficznością nie raz potrafi doprowadzić frontendowca do bólu głowy.

Polecamy kilka źródeł, które mogą pomóc Wam w przyszłości rozprawić się z problemami ze skalowalnością CSS:

- [CSS Guidelines](http://cssguidelin.es/)
- Metodyka nazewnictwa klas [BEM (z ang. <i>Block, Element, Modifier</i>)](http://getbem.com/introduction/)
- [CSS zorientowany obiektowo (OOCSS)](https://www.smashingmagazine.com/2011/12/an-introduction-to-object-oriented-css-oocss/)
- Blog [CSS Wizardry](http://csswizardry.com/)

### Preprocesory CSS

Pisanie kodu CSS może czasem okazać się powtarzalne i męczące. Ten problem został zauważony przez programistów już jakiś czas temu. Światło dzienne ujrzały preprocesory CSS.

Preprocesor to nic innego jak narzędzie, które rozszerza składnię CSS na przykład o rzeczy znane z języków programowania (możliwość definiowania zmiennych, pętle i instrukcje warunkowe `if`) albo przyspieszające pisanie kodu (zagnieżdżanie selektorów). Najpopularniejszymi obecnie preprocesorami są [Sass](http://sass-lang.com/) i [LESS](http://lesscss.org/). Jeśli staniecie się fanami Sass'a, polecamy blog [The Sass Way](http://thesassway.com/), gdzie znajduje się mnóstwo ciekawostek i artykułów na temat dobrych praktyk w pisaniu kodu.

Ciekawą "nowością" jest również [PostCSS](http://postcss.org/), który jednak nie jest preprocesorem, choć wśród jego zastosowań również można znaleźć rozszerzanie składni CSS. Zaawansowani programiści mogą tworzyć własne wtyczki do PostCSS.

### SVG

[SVG](https://developer.mozilla.org/en-US/docs/Web/SVG) to format zapisu grafik wektorowych, który jest wspierany przez wszystkie nowoczesne przeglądarki. Podobnie jak HTML jest językiem znaczników. Warto nauczyć się dobrze SVG, ponieważ można za jego pomocą zaimplementować wiele ciekawych efektów na stronie, które nie udałyby się z wykorzystaniem samego HTML i CSS. Bardzo dobrym źródłem artykułów i tutoriali na temat SVG jest [blog frontend developerki Sary Soueidan](https://sarasoueidan.com/articles/).

## JavaScript

Zanim zabierzecie się za naukę implementowania interaktywnych efektów na stronie (na przykład używając jQuery), polecamy zapoznać się z podstawami języka JavaScript. Dlaczego? jQuery jest biblioteką, czyli dostarcza programiście zestaw gotowych funkcji, które po prostu działają i nie trzeba zawracać sobie głowy tym, w jaki sposób zostały napisane. Czysta oszczędność czasu. Jednak im dłużej będziecie programować, tym więcej błędów napotkacie i będziecie musieli nauczyć się je eliminować. Aby być w tym skutecznym, warto wiedzieć, co w trawie piszczy i spróbować rozgryźć czysty JavaScript.

Na początek polecamy Wam:

- [interaktywny kurs na Codeacademy](https://www.codecademy.com/learn/javascript), gdzie możecie nauczyć się składni języka,
- [dokumentację na MDN](https://developer.mozilla.org/pl/docs/Web/JavaScript),
- kiedy poczujecie się już nieco pewniej, warto zabrać się za lekturę książki [Eloquent JavaScript](http://eloquentjavascript.net/), dostępnej za darmo do przeczytania w Internecie.

## Programowanie aplikacji webowych

Jeśli poważnie myślicie o rozpoczęciu kariery jako programista/programistka frontend, powyższe zagadnienia nie wyczerpują tematyki programowania aplikacji webowych.

Przypomnijcie sobie treść pierwszego rozdziału "Jak działa Internet?". Czy wydaje się Wam to trudne?

Programista frontend zwykle zna technologie, dzięki którym działa Internet, aby móc efektywnie tworzyć rozwiązania umożliwiające komunikację części klienckiej z backendem. Na pewno warto dogłębnie zrozumieć, jak działają [zapytania HTTP](https://en.wikipedia.org/wiki/Hypertext_Transfer_Protocol), [ciasteczka](https://en.wikipedia.org/wiki/HTTP_cookie) (<i>cookies</i>), a także w jaki sposób przeglądarka renderuje stronę. Warto też mieć chociaż ogólne pojęcie na temat technologii backendowych, między innymi baz danych.

Poza tym znajomość czystego JavaScriptu może okazać się niewystarczająca. Obecnie często zdarza się, że część kliencka aplikacji jest bardzo rozbudowana, dużo danych jest wyświetlanych w czasie rzeczywistym, itd. Aby rozwiązać wiele związanych z tym problemów stworzono <i>frameworki</i>, czyli rozbudowane biblioteki wymuszające tworzenie aplikacji zgodnie z określonymi regułami i strukturą. Nauka każdego <i>frameworka</i> jest osobnym wyzwaniem. Obecnie jednymi z najpopularniejszych są [AngularJS](https://angularjs.org/) (wraz ze swoją odświeżoną wersją [Angular 2](https://angular.io/)) oraz [ReactJS](https://facebook.github.io/react/).

## Narzędzia

Im więcej kodu piszecie, im dłużej pracujecie nad jednym projektem, tym więcej powtarzalnych zadań trzeba wykonywać. Programiści z natury są leniwi, uwielbiają automatyzować swoją pracę.

W pracy frontendowca takimi powtarzalnymi zadaniami mogą być optymalizacja plików graficznych, [minifikacja kodu](https://pl.wikipedia.org/wiki/Minifikacja) albo kompilowanie CSS przy użyciu preprocesora.

Używanie popularnych narzędzi frontendowych automatyzujących pracę wymaga znajomości JavaScript. Poniżej odsyłamy Was do kilku najpopularniejszych obecnie narzędzi:

- [Gulp](http://gulpjs.com/)
- [Grunt](http://gruntjs.com/)
- [Webpack](https://webpack.github.io/)

### Systemy kontroli wersji

Bardzo ważnym narzędziem, wręcz niezbędnym, zwłaszcza w przypadku zespołowej pracy są systemy kontroli wersji. W trakcie pracy nad kodem konieczne jest okresowe zapisywanie jego stanu (zwłaszcza po zakończeniu konkretnego zadania) i przesłanie na zdalny serwer. Wszystko to umożliwia śledzenie zmian oraz wersjonowanie kodu. Istnieje wiele różnych systemów kontroli wersji, jednym z najlepszych jest [Git](https://git-scm.com/).

## Jak rozwijać się jako web developer?

Wszystkie powyżej wymienione zagadnienia to tylko główne drogowskazy. Temat web developmentu jest niezwykle szeroki nawet ze swojej frontendowej strony. 

Z pewnością warto posiadać umiejętność... szybkiego uczenia się oraz dostosowywania do zmian. Programowanie WWW to bardzo dynamiczna dziedzina, wciąż pojawiają się nowe narzędzia i technologie, które coś usprawniają.

Pocieszające jest to, że społeczność programistów webowych jest bardzo duża i bardzo otwarta. Ludzie chętnie dzielą się swoją wiedzą &ndash; prowadzą blogi, wrzucają na swoje twitterowe profile mnóstwo linków do ciekawych artykułów, organizują spotkania i konferencje. Nie bójcie się korzystać z takich okazji! Nie bójcie się też [zadawania pytań](mailto:contact@theawwwesomes.org).

My trzymamy mocno kciuki za Was i Wasz rozwój w dziedzinie frontendu. Powodzenia!

PS. Na koniec podsyłamy Wam jeszcze [książkę bardzo szczegółowo opisującą umiejętności, które powinien posiadać frontend developer](http://www.frontendhandbook.com/).