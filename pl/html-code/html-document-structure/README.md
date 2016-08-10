## Definiowanie struktury strony

Hurra! Potraficie już zakodować prostą stronę w HTML. Jednak to jeszcze nie koniec! Zanim zabierzecie się za trudniejsze wyzwania, warto zapoznać się ze znacznikami, które pomagają nam logicznie porządkować i grupować zawartość strony według jej znaczenia.

Spójrzcie na zrzut ekranu przedstawiający artykuł ze strony internetowej [The Guardian](https://www.theguardian.com/technology/2016/apr/23/facebook-global-takeover-f8-conference-messenger-chatbots):

![Przykład struktury strony - artykuł z The Guardian][1]

[1]: /images/page-layout-example.png

Spróbujmy pogrupować jej zawartość i wyróżnić główne elementy znajdujące się na stronie:

![Przykład struktury strony - objaśnienia][2]

[2]: /images/page-layout-example-sections.png


W pierwszej kolejności rzuca się w oczy <b>nagłówek</b> strony (oraz <b>stopka</b>, która akurat nie jest widoczna na naszym zrzucie ekranu). Moglibyśmy w tym momencie pójść o krok dalej i w nagłówku strony wyróżnić, na przykład, menu służące do <b>nawigacji</b>.

Pod nagłówkiem (a w zasadzie pomiędzy nagłówkiem a stopką) znajduje się główna zawartość strony. Jej najważniejszym elementem jest <b>artykuł</b>. Artykuł składa się z <b>nagłówka</b> oraz treści, która złożona jest z <b>ilustracji</b> oraz <b>akapitów</b>. W nagłówku artykułu możemy wyróżnić <b>tytuł</b> i <b>podtytuł</b>, a także informacje dotyczące autora oraz daty publikacji. Obok artykułu widzimy listę innych popularnych artykułów, która jest <b>elementem pobocznym</b>, ponieważ nie dotyczy bezpośrednio głównej zawartości strony.

Do wszystkich wymienionych powyżej elementów możemy zastosować odpowiednie znaczniki HTML.

```html
<header>
  Tu umieszczamy zawartość nagłówka strony
  <nav>
    Tu umieszczamy nawigację
  </nav>
</header>

<article>
  <header>
    Tu umieszczamy zawartość nagłówka artykułu
  </header>

  Tu umieszczamy zawartość treści artykułu

  <footer>
    Tu umieszczamy zawartość stopki artykułu
  </footer>
</article>

<aside>
  Tu umieszczamy elementy poboczne (np. reklamy, zajawki innych artykułów)
</aside>

<footer>
  Tu umieszczamy zawartość stopki strony
</footer>
```

Sporo nowych różnych znaczników, prawda? Czujecie się zdezorientowani?

Dzięki znacznikom `<header>` i `<footer>` możemy określić, że dany element strony pełni rolę nagłówka bądź stopki. Z pewnością już w tej chwili zwróciło Twoją uwagę, że również elementy umieszczone wewnątrz strony mogą posiadać swój nagłówek i stopkę (na przykład artykuł). Również w takich przypadkach z powodzeniem sprawdzą się znaczniki `<header>` i `<footer>`.

Tak, jak pokazaliśmy w przykładzie wyżej, znacznika `<nav>` używamy kiedy chcemy zaznaczyć, że wewnątrz danego elementu znajduje się nawigacja strony. Może być on użyty więcej niż raz w obrębie tego samego dokumentu.

Znacznik `<aside>` pozwala nam na określenie danego elementu jako niepowiązanego ściśle tematycznie z główną zawartością strony, choć wciąż ważnego z punktu widzenia odbiorcy. Klasycznym przykładem są tu reklamy umieszczane na stronie.

Tag `<article>` jest przydatny dla elementów takich jak artykuł na blogu lub stronie z wiadomościami, post na forum albo komentarz pozostawiony pod artykułem. Używamy go dla tych elementów, które z powodzeniem mogłyby istnieć samodzielnie, wyjęte z kontekstu całej strony.

### Podział strony na sekcje

Nie wymieniliśmy powyżej jeszcze jednego ważnego znacznika, który pomaga nam organizować zawartość strony:

```html
<section>Jestem sekcją strony</section>
```

Znacznik `<section>` ma już nieco bardziej ogólne zastosowanie. Używamy go, aby tematycznie pogrupować naszą zawartość. Zwykle każda z tak uzyskanych sekcji powinna posiadać nagłówek odpowiedniego poziomu (`<h1>`-`<h6>`).

> #### Important::Ważne
>
> Pamiętaj, aby nie używać znacznika `<section>` jako generycznego kontenera "do wszystkiego"! `<section>`, jak wspomnieliśmy powyżej, pozwala nam na tematyczne grupowanie zawartości strony. Natomiast `<div>` jest znacznikiem, który powinien być używany tylko w przypadkach, kiedy żaden inny znacznik nie będzie odpowiedni dla zawartości.

Sekcje z powodzeniem mogą być zagnieżdżane wewnątrz siebie.

```html
<section>
  <h1>Oto strona o żywych stworzeniach</h1>

  <section>
    <h2>Tutaj są zwierzęta</h2>

    <section>
      <h3>Tutaj są ryby</h3>
    </section>

    <section>
      <h3>Tutaj są owady</h3>
    </section>

    <section>
      <h3>Tutaj są ssaki</h3>

      <section>
        <h4>Tutaj są ludzie</h4>
      </section>
    </section>
  </section>

  <section>
    <h2>Tutaj są rośliny</h2>
  </section>

  <section>
    <h2>Tutaj są grzyby i bakterie</h2>
  </section>
</section>
```

> #### Exercise::Ćwiczenie 5
>
> Otwórz [stronę z artykułem](https://www.theguardian.com/technology/2016/apr/23/facebook-global-takeover-f8-conference-messenger-chatbots), która była źródłem przykładu z początku tego rozdziału.
> - Uruchom narzędzia deweloperskie. Spróbuj zbadać różne elementy strony i sprawdzić, jakich znaczników użyli autorzy strony i w jakich celach?

Pora na rozpoczęcie pracy z docelowym layoutem!

> #### Exercise::Ćwiczenie 6
>
> Zaczynamy pracę nad docelowym layoutem. W [Dodatku III](../../appendix/layouts/README.md) możesz znaleźć dostępne layouty oraz zasoby potrzebne do kodowania. 
> Jeśli pracujesz podczas warsztatów, wybierz layout zaproponowany podczas Twojej edycji. 
>
> - W folderze `the-awwwesomes` (który jest przeznaczony na przechowywanie folderów ze wszystkimi ćwiczeniami) stwórz folder, np. `layout`. Od tej pory to właśnie w tym folderze będziesz umieszczać wszystkie pliki dotyczące layoutu.
> - Wewnątrz `the-awwwesomes/layout/` utwórz plik `index.html`. Będziesz tam tworzyć kod strony.
> - Stwórz szkielet dokumentu HTML dbając, aby zawrzeć wszystkie potrzebne metadane w sekcji `<head>`.
> - Bazując na projekcie layoutu oceń, jak należy pogrupować poszczególne elementy layoutu. Użyj odpowiednich znaczników. Pamiętaj, że budowanie layoutu można rozwiązać na różne sposoby, więc nie zrażaj się, jeśli Twój kod będzie różnił się od kodu koleżanek i kolegów. W budowaniu szkieletu warto rozrysować sobie layout na kartce w postaci kontenerów, nadając im odpowiednie znaczenie.
> - Rozpocznij pracę nad kodem HTML strony. Zadbaj o to, aby dla każdego elementu użyć odpowiednich znaczników.
