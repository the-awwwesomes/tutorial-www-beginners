# Znaczniki HTML

Właśnie napisaliście swój pierwszy kod HTML, gratulacje! Kiedy jednak spojrzycie na niego, poza podstawowym szkieletem zawiera on jednolity blok tekstu. Brakuje nam wyróżnienia nagłówków, hiperłączy, obrazka i formularzy. Pora na zapoznanie Was z różnymi znacznikami HTML.

## Podstawowe znaczniki

Wiemy już, że aby uzyskać HTML-owy element należy "owinąć" go w *tagi* (*znaczniki*). Nie poznaliśmy jednak jak dotąd żadnych nazw znaczników, których moglibyśmy użyć na rzeczywistym przykładzie strony.

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

### Formatowanie tekstu

```html
<strong></strong>
```

### Hiperłącza

```html
<a href="http://theawwwesomes.org" target="_blank">Darmowe warsztaty HTML & CSS</a>
```

### Obrazki

```html
<img src="/images/awwwesome.png" alt="Nasi niesamowici uczestnicy">
```

### Elementy generyczne (ogólne)

```html
<div>Jestem generycznym elementem blokowym</div>
```

```html
<span>Jestem generycznym elementem liniowym</span>
```
