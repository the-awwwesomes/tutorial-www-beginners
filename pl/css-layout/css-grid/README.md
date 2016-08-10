## Umieszczamy elementy na siatce

Każdy z Was, kto miał już do czynienia z projektowaniem graficznym stron internetowych, z pewnością wie, do czego służy siatka. Jest ona bardzo ważna dla kompozycji strony, ułatwia harmonijne i estetyczne rozmieszczenie jej elementów. Spójrzmy, jak wygląda siatka layoutu Planty:

![Siatka projektu layoutu Planty][1]

[1]: /images/planty-grid.jpg

Zauważmy, że wszystkie elementy znajdują się w głównym kontenerze o szerokości <b>960 pikseli</b>, a sama siatka składa się z <b>12 kolumn</b>. Czy jest jakiś sposób, dzięki któremu możemy sprawić, aby można było łatwo rozmieszczać elementy bazując na siatce projektu?

W zasadzie podczas kodowania każdego projektu strony będziemy musieli skorzystać z gotowej siatki. Na szczęście również w tym wypadku można znaleźć sporo już istniejących rozwiązań i dołączyć wybrane do projektu.

W tym tutorialu zaprezentujemy Wam możliwości korzystania z siatki na przykładzie [Bootstrapa](http://getbootstrap.com/css/#grid). Bootstrap jest tzw. <i>frameworkiem</i>, czyli gotowym zestawem narzędzi (m.in. klas CSS) pomocnych w rozwiązywaniu powtarzających się, standardowych problemów <i>webdesignu</i>, na przykład responsywnego menu lub właśnie siatki.

### Budowanie kolumn w oparciu o siatkę z Boostrapa

Do zbudowania layoutu w oparciu o siatkę bootstrapową potrzebny nam plik CSS, w którym siatka jest opisana poprzez style. Kontener zawierający kolumny zdefiniowany jest dla kilku szerokości ekranu: dla desktopu, tabletu i smartfona. Jej poszczególne składniki, czyli kolumny, procentowo dostowują się do szerokości kontenera. Dzięki temu nasza strona odpowiednio wyświetla się na różnych urządzeniach. Niestety, w naszym kursie nie starczy nam czasu, aby omówić zagadnienia związane z <b>projektowaniem responsywnym</b> (ang. <i>responsive web design</i>), alę dzięki zastosowaniu responsywnej siatki będziemy mogli zaobserwować przynamniej jego częściowe efekty.

Maksymalna liczba kolumn zawartych w danym kontenerze to 12. Żeby nasz element został spozycjonowany według siatki, musi się on zajmować między znacznikami takimi jak:
`<div class="container">`, czyli kontener,
`<div class="row">`, czyli rząd, w którym będą wyświetlać się nasze elementy
oraz `<div class="col-md-12">`, czyli `<div>` zbudowany z zadanej ilości kolumn (w tym wypadku <i>12</i>)

Jeśli chcemy, żeby nasz element zajmował całą całą szerokość kontenera, zastosujemy kod
```html
<div class="container">
	<div class="row">   
    	<div class="col-md-12">
    		element zajmujący maksymalną liczbę kolumn, czyli 12
        </div>
	</div>   
</div>                 
```   

![Siatka z frameworka Bootstrap][2]
[2]: /images/grid.png


Jeśli chcemy zbudować dwie kolumny o tej samej szerokości, musimy podzielić liczbę dostępnych kolumn w kontenerze na dwa: `12/2 = 6`, czyli `<div class="col-md-6">`. Obie kolumny powinny znajdować się obok siebie, czyli w obrębie tego samego rzędu.  Muszą być zatem objęte znacznikiem `<div class="row">`.


```html
<div class="container">
	<div class="row">   
    	<div class="col-md-6">
			kolumna lewa
        </div>
        <div class="col-md-6">
        	kolumna prawa
        </div>
	</div>   
</div>                 
```      

Może być też tak, że bedzięmy chcieli utworzyć obok siebie 3 kolumny tej samej szerokości. Zasada jest podobna jak wyżej: `12/3 = 4`, zatem stosujemy `<div class="col-md-4">` dla każdej z kolumn.

```html
<div class="container">
	<div class="row">   
    	<div class="col-md-4">
			kolumna lewa
        </div>
        <div class="col-md-4">
        	kolumna środkowa  
        </div>
        <div class="col-md-4">
        	kolumna prawa
        </div>
	</div>   
</div>                 
```  
Tworząc layout możemy również budować kolumny o różnych szerokościach zawarte w obrębie tego samego rzędu. Pamiętajmy jednak, że maksymalnie możemy zmieścić 12 kolumn w jednym rzędzie tworząc różne kombinacje np. `8+4`,`7+5`,`2+2+3+5`, `9+2+1` itd.

```html
<div class="container">
	<div class="row">   
    	<div class="col-md-8">
			szerokość zawierająca 8 kolumn siatki
        </div>
        <div class="col-md-4">
        	szerokość zawierająca 4 kolumny siatki
        </div>
	</div>   
</div>                 
```  

### Budowanie siatki w zależności od szerokości urządzenia
Zastanawiacie się pewnie, jak uzyskać efekt zmiany szerokości różnych elementów layoutu w zależności od szerokości wyświetlacza.
Przykładowo: chcielibyśmy, żeby dla wysokich i średnich rozdzielczości kolumna z definicją i zadaniem zawarte były w dwóch, równych szerokością kolumnach. Niestety, takie rozwiązanie niekorzystnie prezentuje się na telefonie, gdyż podział szerokości kontenera na pół daje nam ostatecznie bardzo wąskie kolumny, w których ograniczona jest czytelność. Możemy wykorzystać wbudowaną właściwość siatki boostrapowej nadając zawartości danego `<div>` różne szerokości w zależności od urządzenia, na którym wyświetlana jest strona.
Co należy zrobić? Popatrzmy na kod poniżej.
```html
<div class="container">
	<div class="row">   
    	<div class="col-xs-12 col-sm-6 col-md-6 col-lg-12">
			definicja
        </div>
        <div class="col-xs-12 col-sm-6 col-md-6 col-lg-12">
        	zadanie
        </div>
	</div>   
</div>                 
```  
Jak zauważyliście, dodane zostały nowe klasy `col-xs-12` – definiująca szerokość dla telefonu (dzieki czemu tekst będzie zajmował <i>12</i> kolumn) – oraz `col-sm-6` – definiująca szerokość dla tabletu (tekst zajmie pół szerokości kontenera, czyli <i>6</i> kolumn). `col-md-12` definiuje nam zatem szerokość desktopową (typową dla wyświetlaczy laptopów > 992px). `col-lg-12` przypisany jest dla wyświetlaczy o rozdzielczości >= 1200 px, czyli laptopów o większym wyświetlaczu.

Zerknijcie na poniższą tabelę

|  | Bardzo małe urządzenia <br>smartfony (<768px) | Małe urządzenia<br>tablety (≥768px) | Średnie urządzenia<br>tzw. desktop (≥992px) | Duże urządzenia<br>duże rozdzielczości (≥1200px)
| -------------- |:---:| :---:| :---:| :---:|
| Prefix klasy       | `.col-xs-` | `.col-sm-` |`.col-md-`| `.col-lg-` |
| Szerokość kontenera       | brak (auto) | 750px | 960px | 1170px |



> #### Exercise::Ćwiczenie 12
>
> Porą dołączyć plik CSS, zawierający grid pochodzący z Bootstrapa do naszego projektu. Co warto podkreślić, na zajęciach wykorzystujemy jedynie siatkę bootstrapową. Nie będziemy zajmować się innymi komponentami z frameworku Boostrap.
> <a href="../resources/bootstrap-grid.css" target="_blank">Ściągnij plik `bootstrap-grid.css`</a> i zapisz go do folderu ze stylami, czyli `styles`. Następnie dodaj plik do Twojego kodu HTML, korzystając ze znacznika
>`<link href="tu wpisz ścieżkę do pliku css" rel="stylesheet">`. Pamiętaj o napisaniu prawidłowej ścieżki!
>
> Wykorzystaj zdobytą wiedzę o siatce i rozmieść w budowanym layoucie elementy w kolumnach, używając do tego siatki Bootstrapa.
