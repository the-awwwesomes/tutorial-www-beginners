# Podstawowe znaczniki HTML

Właśnie napisaliście swój pierwszy kod HTML, gratulacje! Kiedy jednak spojrzycie na niego, poza podstawowym szkieletem zawiera on jednolity blok tekstu. Brakuje nam wyróżnienia nagłówków, hiperłączy, obrazka i formularzy. Pora na zapoznanie Was z różnymi znacznikami HTML.

## Podstawowe znaczniki

Wiemy już, że aby uzyskać HTML-owy element należy "owinąć" go w *tagi* (*znaczniki*). Nie poznaliśmy jednak jak dotąd żadnych nazw znaczników, których moglibyśmy użyć na rzeczywistym przykładzie strony.

### Komentarze

Często bywa tak, że kod jednej strony edytuje przynajmniej kilku programistów. Zdarza się też, że trzeba wrócić do kodu, który został napisany dość dawno temu. W takich przypadkach bywa, że pojawiają się niejasności i pytania *"Co ten koder miał na myśli?"*.

Pomocne bywają nam wtedy komentarze. Są one ignorowane przez przeglądarkę podczas wyświetlania strony i widoczne tylko podczas podglądania jej kodu źródłowego. Komentarze bywają bardzo użyteczne przy opisie kodu i umożliwiają jego dokumentowanie.

```html
<!-- To jest komentarz do naszego kodu -->
```

### Nagłówki i paragrafy

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

Przy okazji omawiania składni CSS napomknęliśmy o znaczniku `p`. Jego nazwa pochodzi od słowa *paragraph* - służy do definiowania akapitów w tekście.

```html
<p>To jest akapit tekstu. Możesz w nim umieścić tekst dowolnej długości.</p>
```

<div class="example-wrapper">
  <p>To jest akapit tekstu. Możesz w nim umieścić tekst dowolnej długości.</p>
</div>

Paragrafy zwykle prezentowane są w przeglądarce jako bloki tekstu, wizualnie odseparowane od siebie pionowym odstępem.

### Znak łamania linii

Kiedy kodujesz paragrafy tekstu, czasem zachodzi potrzeba złamania linii w określonym miejscu. Warto wiedzieć, że nie wystarczy tam wcisnąć *enter* w edytorze tekstu - do łamania linni w HTML-u służy specjalny znacznik `<br>`:

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
> Nie stosuj znacznika `<br>` aby wizualnie odseparować od siebie elementy w pionie! HTML powinien być używany **wyłącznie do definiowania treści**. W tym przypadku należy nadać elementom **pionowe marginesy za pomocą CSS** (już niedługo dowiecie się dokładnie, jak to zrobić). 

### Hiperłącza

Dzięki hiperłączom (czyli po prostu linkom) możemy przenieść się w niemal dowolne inne miejsce w sieci. Link możecie umieścić na stronie używając znacznika `<a>` (od angielskiego słowa *anchor*) - podając adres linkowanej strony jako wartość atrybutu `href`.

Można powiedzieć, że hiperłącza są solą Internetu!

```html
<a href="http://theawwwesomes.org">Przeniosę Cię na stronę The Awwwesomes!</a>

<a href="http://theawwwesomes.org" target="_blank">
  Przeniosę Cię na stronę The Awwwesomes otwierając ją w osobnej karcie przeglądarki!
</a>
```

<div class="example-wrapper">
  <a href="http://theawwwesomes.org">Przeniosę Cię na stronę The Awwwesomes!</a>
  <br>
  <a href="http://theawwwesomes.org" target="_blank">
    Przeniosę Cię na stronę The Awwwesomes otwierając ją w osobnej karcie przeglądarki!
  </a>
</div>

Tak, jak pokazaliśmy w przykładzie wyżej - użycie `target="_blank"` spowoduje, że strona, do której prowadzi Wasz link zostanie otwarta w nowej karcie przeglądarki.

### Obrazki

Obrazki w kodzie wstawiamy za pomocą znacznika `<img>`. Jest on *pustym* elementem i nie posiada znacznika zamykającego. Dwa najważniejsze atrybuty, jakie może przyjmować `<img>` to:

- `src`, który zawiera ścieżkę do obrazka na dysku serwera lub w sieci. Jeśli wskazuje on na ścieżkę na dysku, zwykle jest to ścieżka względna - względem pliku HTML w którym znajduje się konkretny element `<img>`.

```html
<img src="/images/awwwesome.png" alt="Nasi niesamowici uczestnicy">
```

### Listy

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

### Elementy generyczne (ogólne)

```html
<div>Jestem generycznym elementem blokowym</div>
```

```html
<span>Jestem generycznym elementem liniowym</span>
```

Powyżej przedstawiliśmy Wam najczęściej używane znaczniki - a to zdecydowanie [nie wszystkie](https://developer.mozilla.org/pl/docs/Web/HTML/Element)! W kolejnych rozdziałach dowiecie się natomiast, jak kodować proste formularze oraz określać strukturę dokumentu.
