# Proste formularze

Na pewno niejednokrotnie zdarzyło się Wam, korzystając ze strony internetowej, podawać swoje dane (na przykład dokonując zakupu w sklepie internetowym) albo dodawać komentarze pod artykułem. HTML, oprócz tego, że umożliwia nam wyświetlanie zawartości strony pobranej z serwera, pozwala również na takie podstawowe interakcje, jak <i>wypełnianie formularzy</i>.

## Jak wstawić formularz na stronę?

W Ćwiczeniu 3 na pewno zauważyliście pod artykułem kontrolki, dzięki którym użytkownik mógł wpisać swoje podstawowe dane oraz treść komentarza.

Kiedy umieszczamy na stronie formularz, najpierw musimy "powiedzieć" przeglądarce za pomocą odpowiedniego znacznika, że *tutaj będzie znajdował się nasz formularz*:

```html
<form name="myBasicForm">
  <!-- Tu wstawię kontrolki mojego formularza -->
</form>
```

Wiedząc, jak zadeklarować sam formularz, możemy po kolei zapoznać się z różnymi rodzajami kontrolek.

### Podstawowe interaktywne kontrolki (`<input>`)

Załóżmy, że chcemy umieścić w naszym formularzu kilka prostych pól, dzięki którym użytkownik będzie mógł podać swoje imię, nazwisko oraz miejsce zamieszkania. Spójrzcie na kod poniżej:

```html
<input type="text">
```

<div class="example-wrapper">
  <input type="text">
</div>

Znacznik `<input>` w większości przypadków służy do przyjmowania od użytkownika danych tekstowych (choć z powodzeniem możecie wpisywać tam również liczby oraz znaki specjalne!). Musimy jednak pamiętać, że zachowanie pola `<input>` jest zależne od jego typu, który podajemy za pomocą atrybutu `type`. Dla pola tekstowego będzie to wyglądało jak powyżej: `type="text"`.

Wygląda bardzo prosto, prawda? Tak prosto, że użytkownik nie widzi informacji o tym, jakich danych się od niego oczekuje.

Do opisu pól formularza używamy znacznika `<label>` i właśnie wewnątrz niego umieszczamy informację, co powinno znajdować się w danym polu:

```html
<label for="name">Podaj swoje imię:</label>
<input type="text" id="name">
```

<div class="example-wrapper">
  <label for="name">Podaj swoje imię:</label>
  <input type="text" id="name">
</div>

Zauważcie, że pojawiły się dwa nowe atrybuty: `id` oraz `for`.

- Atrybut `id` jest identyfikatorem elementu HTML. Jego wartość musi być **unikalna** w obrębie całej strony. Atrybut `id` nie jest charakterystyczny tylko dla pól typu `<input>`, może być używany wraz z *dowolnym* znacznikiem HTML.
- Atrybut `for` jest już charakterystyczny dla znacznika `<label>`. Łączy on `<label>` wraz z kontrolką formularza, której dotyczy. W takim wypadku wartość atrybutu `for` musi być **identyczna** jak wartość `id` pola tekstowego, do którego się odnosi. Dokładnie tak, jak w przykładzie powyżej.

A teraz zapoznajmy się z pozostałymi typami pola `<input>`!

#### Kontrolki do podawania danych o określonym formacie

Zapoznaliśmy się przed chwilą ze zwykłym polem tekstowym, do którego można wpisać w zasadzie dowolny ciąg znaków. Często jednak dane, jakich oczekujemy od użytkownika, muszą być podane w specjalnym formacie. Takim przypadkiem jest na przykład adres e-mail.

Od niedawna (wraz z pojawieniem się specyfikacji HTML5) programiści WWW zyskali taką możliwość, ponieważ HTML został wzbogacony o nowe, specjalne typy kontrolek na potrzeby wprowadzania adresów e-mail, adresów stron internetowych, dat, numerów oraz wielu innych formatów.

```html
<label for="emailData">Adres e-mail:</label>
<input type="email" id="emailData">

<label for="urlData">Adres strony internetowej:</label>
<input type="url" id="urlData">

<label for="dateData">Data:</label>
<input type="date" id="dateData">

<label for="numberData">Numer:</label>
<input type="number" id="numberData">
```

<div class="example-wrapper">
  <label for="emailData">Adres e-mail:</label>
  <input type="email" id="emailData">

  <label for="urlData">Adres strony internetowej:</label>
  <input type="url" id="urlData">

  <label for="dateData">Data:</label>
  <input type="date" id="dateData">

  <label for="numberData">Numer:</label>
  <input type="number" id="numberData">
</div>

#### Pola wielokrotnego wyboru

Pola wielokrotnego wyboru, czyli <i>checkboksy</i>. Dla tego typu pól atrybut `type` przyjmie wartość `checkbox`:

```html
<label for="checkbox1">
  <input type="checkbox" id="checkbox1" name="myGroup">
  Wybierz mnie!
</label>
<label for="checkbox2">
  <input type="checkbox" id="checkbox2" name="myGroup">
  Nie, nie, mnie wybierz!
</label>
<label for="checkbox3">
  <input type="checkbox" id="checkbox3" name="myGroup">
  Ja też chcę być wybrany!
</label>
```

<div class="example-wrapper">
  <label for="checkbox1">
    <input type="checkbox" id="checkbox1" name="myGroup">
    Wybierz mnie!
  </label>
  <label for="checkbox2">
    <input type="checkbox" id="checkbox2" name="myGroup">
    Nie, nie, mnie wybierz!
  </label>
  <label for="checkbox3">
    <input type="checkbox" id="checkbox3" name="myGroup">
    Ja też chcę być wybrany!
  </label>
</div>

#### Pola jednokrotnego wyboru

Oprócz checkboksów możemy umieścić w swoim formularzu pola jednokrotnego wyboru, czyli radiobuttony:

```html
<label for="radiobutton1">
  <input type="radio" id="radiobutton1" name="myGroup">
  Wybierz mnie!
</label>
<label for="radiobutton2">
  <input type="radio" id="radiobutton2" name="myGroup">
  Nie, nie, mnie wybierz!
</label>
<label for="radiobutton3">
  <input type="radio" id="radiobutton3" name="myGroup">
  Ja też chcę być wybrany!
</label>
```

<div class="example-wrapper">
  <label for="radiobutton1">
    <input type="radio" id="radiobutton1" name="myGroup">
    Wybierz mnie!
  </label>
  <label for="radiobutton2">
    <input type="radio" id="radiobutton2" name="myGroup">
    Nie, nie, mnie wybierz!
  </label>
  <label for="radiobutton3">
    <input type="radio" id="radiobutton3" name="myGroup">
    Ja też chcę być wybrany!
  </label>
</div>

W przypadku checkboksów i radiobuttonów również potrzebujemy dodać do `<label>` atrybut `for`. Poeksperymentujcie i usuńcie ten atrybut – co się stanie? Jak wpłynie to na doświadczenie użytkownika podczas używania formularza?

Zauważcie również, że w naszych powyższych przykładach używamy atrybutu `name`. Jest on istotny w przypadku radiobuttonów i checkboksów, bo wskazuje, że wybieramy elementy spośród konkretnej grupy.

#### Wybieranie plików z dysku

W formularzach istnieje również możliwość dodania pola, dzięki któremu możemy wybrać plik ze swojego dysku i przesłać go na serwer:

```html
<label for="fileUpload">Wybierz plik:</label>
<input type="file" id="fileUpload">
```
<div class="example-wrapper">
  <label for="fileUpload">Wybierz plik:</label>
  <input type="file" id="fileUpload">
</div>

### Pole tekstowe z wieloma liniami (`<textarea>`)

Wiemy już, jak wstawiać do naszego formularza pola tekstowe, czyli `<input type="text">`. Co, jeśli jednak użytkownik potrzebuje wpisać większą porcję tekstu, tak jak w przypadku komentarzy pod artykułem na blogu?

Z pomocą przychodzi nam znacznik `<textarea>`, dzięki któremu umożliwimy naszym użytkownikom wpisywanie tekstu w wielu liniach. Będą mieli wtedy więcej miejsca na wyrażenie, na przykład swoich opinii o naszym tekście.

```html
<textarea rows="10" cols="30">Napisz coś tutaj</textarea>
```

<div class="example-wrapper">
  <textarea rows="10" cols="30">Napisz coś tutaj</textarea>
</div>

### Listy rozwijalne (pola typu <i>dropdown</i>)

Do wstawiania elementu rozwijalnej listy do formularza służy nam znacznik `<select>`.

```html
<label for="favFruit">Wybierz swój ulubiony owoc:</label>
<select id="favFruit">
  <option value="apple">Jabłko</option>
  <option value="pear">Gruszka</option>
  <option value="plum">Śliwka</option>
  <option value="cherry">Wiśnia</option>
</select>
```

<div class="example-wrapper">
  <label for="favFruit">Wybierz swój ulubiony owoc:</label>
  <select id="favFruit">
    <option value="apple">Jabłko</option>
    <option value="pear">Gruszka</option>
    <option value="plum">Śliwka</option>
    <option value="cherry">Wiśnia</option>
  </select>
</div>

### Przyciski

Wymieniliśmy już większość bardzo przydatnych kontrolek, jakie można umieścić w formularzu. I na razie moglibyśmy na tym zakończyć, gdyby nie jedna, bardzo popularna – bez której właściwie większość formularzy byłaby mało użyteczna – przyciski. Deklarujemy je w poniższy sposób:

```html
<button>Kliknij mnie!</button>
```

<div class="example-wrapper">
  <button>Kliknij mnie!</button>
</div>

> #### Exercise::Ćwiczenie 4
>
> Wróćmy do naszego przykładu z Ćwiczenia 3:
>
><div class="example-wrapper">
  <article>
    <header>
      <p>Opublikowano przez: <em>Kasia Niesamowita</em>,
        <time datetime="2016-04-20T18:00+01:00">20 kwietnia 2016</time>
      </p>
      <h1>The Awwwesomes podbijają świat!</h1>
    </header>
    <img src="/images/screen.jpg" alt="The Awwwesomes">
    <p>Warsztaty ruszyły pełną parą! Grupa 20 zdolnych uczestników zabrała się do kodowania z godnym podziwu zapałem.</p>
    <p>Mentorzy mieli trudne zadanie, ponieważ padło bardzo dużo ciekawych pytań. Nasi uczestnicy są naprawdę <em>awwwesome</em>!</p>
    <h2>Najpierw semantyczny HTML, potem estetyczny CSS</h2>
    <p>Naukę zaczęliśmy od HTML, który jest absolutną podstawą dla każdego kodera stron internetowych. Nie obejdzie się jednak bez zapoznania z CSS, dzięki któremu każdy może upiększyć swoją stronę jak tylko sobie wymarzy!</p>
  </article>
  <form>
    <p>Zostaw swój komentarz:</p>
    <label for="email">Twój email:</label>
    <input type="email" id="email">
    <label for="name">Twoje imię:</label>
    <input type="text" id="name">
    <label for="comment">Twój komentarz:</label>
    <textarea id="comment"></textarea>
    <button type="submit">Prześlij</button>
  </form>
</div>
>
> W poprzednim ćwiczeniu umieściliśmy całą zawartość jako zwykły tekst. Chcemy jednak, aby nasze elementy były odczytywane i wyświetlane prawidłowo.
>
> - Korzystając ze zdobytej dotąd wiedzy, uzupełnij kod w odpowiednie znaczniki opisujące zawartość. Nie zapomnij o formularzu!
> - Zadbaj o poprawne umieszczenie obrazka w artykule!
