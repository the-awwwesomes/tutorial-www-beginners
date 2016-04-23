# Definiowanie struktury strony

Hurra! Potraficie już zakodować prostą stronę w HTML. Jednak to jeszcze nie koniec! Zanim zabierzecie się za trudniejsze wyzwania, warto zapoznać się ze znacznikami, które pomagają nam logicznie porządkować i grupować zawartość strony według jej znaczenia.

Spójrzcie na zrzut ekranu przedstawiający artykuł ze strony internetowej [The Guardian](https://www.theguardian.com/technology/2016/apr/23/facebook-global-takeover-f8-conference-messenger-chatbots):

![Przykład struktury strony - artykuł z The Guardian][1]

[1]: /images/page-layout-example.png

Spróbujmy pogrupować jej zawartość i wyróżnić główne elementy znajdujące się na stronie:

![Przykład struktury strony - objaśnienia][2]

[2]: /images/page-layout-example-sections.png


W pierwszej kolejności rzuca się w oczy **nagłówek** strony (oraz **stopka**, która akurat nie jest widoczna na naszym zrzucie ekranu). Moglibyśmy w tym momencie iść krok dalej i w nagłówku strony wyróżnić, na przykład, menu służące do **nawigacji**.

Pod nagłówkiem (a w zasadzie pomiędzy nagłówkiem a stopką) znajduje się główna zawartość strony. Jej najważniejszym elementem jest **artykuł**. Artykuł składa się z **nagłówka** oraz treści, która złożona jest z **ilustracji** oraz **akapitów tekstu**. W nagłówku artykułu możemy wyróżnić **tytuł** i **podtytuł**, a także informacje dotyczące autora oraz daty publikacji. Obok artykułu widzimy listę innych popularnych artykułów, która jest **elementem pobocznym** ponieważ nie dotyczy bezpośrednio głównej zawartości strony.

Do wszystkich wymienionych powyżej elementów możemy zastosować odpowiednie znaczniki HTML.

```html
<header>
  Tu umieszczamy zawartość nagłówka.
</header>

<footer>
  Tu umieszczamy zawartość stopki
</footer>
```


### Elementy generyczne (ogólne)

*"Pomocy! Muszę zakodować element na stronie, jednak nie jestem w stanie dopasować jego znaczenia do żadnego z powyższych tagów!"*

Właśnie w takich przypadkach na ratunek spieszą nam elementy generyczne. 

```html
<div>Jestem generycznym elementem blokowym</div>
```

```html
<span>Jestem generycznym elementem liniowym</span>
```