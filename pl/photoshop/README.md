# Photoshop dla front-endowca

Wydawać by się mogło, że podział pracy pomiędzy koderem a projektantem graficznym jest już od dawna ustalony - grafik tworzy w Photoshopie, a front-endowiec pisze kod. Jednak zawód front-endowca ma to do siebie, że kod jest ściśle powiązany z warstwą wizualną. Dlatego też dbałość o szczegóły i jak najbliższe odwzorowanie projektu graficznego są istotnymi cechami każdego kodera stron WWW.

Bywa tak, że grafik szczegółowo opisuje programiście swój projekt wraz z rozmiarami poszczególnych elementów, wielkością tekstu, kolorami itp. Zdarzają się również sytuacje, kiedy grafik kończy pracę na stworzeniu pliku `.psd`, który następnie trafia do front-endowca. Zatem część dalszych działań związanych z wygenerowaniem zasobów tzw. <i>assetów</i> czy pomiarem elementów leży po stronie programisty. Właśnie dlatego zachęcamy Was do zapoznania się z podstawowymi możliwościami Photoshopa. 

Zapraszamy na krótki kurs, dzięki któremu dowiemy się:
<ul>
	<li>jak definiować jednostki,</li>
	<li>jak sprawdzać kroje pisma,</li>
	<li>jak mierzyć wielkości elementów,</li>
	<li>jak generować assety.</li>

Jeśli jesteś projektantem graficznym lub stawiałeś już pierwsze kroki w Photoshopie możesz pominąć ten rozdział.

## Ustawienie wybranych jednostek

Najbardziej wygodną dla nas jednostką jest piksel (px). 
Wybieramy ją wchodząc do ustawień: `Photoshop -> Preferences -> Units & Rulers`.


![Ustwienie jednostek w Photoshopie][1]
[1]: /images/ps-units.png

Zalecamy ustawić piksele zarówno dla linijek (Rulers), jak i dla rozmiaru tekstu (Type).

![Ustwienie pikseli zarówno dla obiektów, jak i rozmiaru tekstu][2]
[2]: /images/ps-units-panel.jpg

Dzięki temu od tej pory wszystkie wielkości prezentowane będą w pikselach.

## Sprawdzanie krojów pisma i wielkości fontu

W celu spradzenia m.in. nazwy kroju, wielkości czy interlinii przyda się nam panel `Character`. Uruchamiamy go poprzez: `Window -> Character`.

![Uruchomienie okna "Character"][3]
[3]: /images/ps-character.jpg

Powinno pokazać nam się nowe okno, zawierające detale dotyczące naszego tekstu.

![Okno "Character"][4]
[4]: /images/ps-character-panel.jpg

Klikajc klawisz `T` automatycznie przechodzimy do narzędzia `Horizontal Type Tool`, oznaczonego charakterystycznym `T` w panelu narzędzi po lewej stronie.
Dzięki temu możemy kliknąć w dany tekst i odczytać w panelu `Character`, jaki krój pisma został użyty, jaka jest wielkość itd.
W panelu `Character` znajdziecie wszystko, co będzie potrzebne do wprowadzenia w akurszu stylów, czyli `font-family`, `font-size`, `font-style` oraz `line-height`. 
Wyjaśnijmy jeszcze czym jest `line-height`. Otóz jest to interlinia, którą możemy określać bezwględnie (w pikselach) lub względnie (w procentach), np.

````css
	line-height: 150%;
	line-height: 27px;
```


## Pomiar elementów
Dowiedzieliśmy się już jak sprawdzać wielkość fontu. Pora teraz na obiekty - kontenery, ramki, obrazki. 
Do pomiaru innych elementów możemy skorzystać z linijki, czyli `Ruler Tool`, która znajduje się w panelu z narzędziami.

!["Wybranie linijki z zestawu narzędzi"][5]
[5]: /images/ps-ruler.gif

Żeby mieć podgląd do wymiarów przyda nam się panel `Info`. Uruchamiamy go poprzez: `Window -> Info`.

!["Panel Info"][6]
[6]: /images/ps-info-panel.jpg

W panelu `Info` odczytać możecie wartość dla W ( <i>width</i> ), czyli szerokości oraz H ( <i>height</i> ) wysokości.

W przypadku kształtów, oznaczonymi w warstwach kwadracikiem <img src="/images/ps-shape.jpg" style="width: 200px; display: inline-block; vertical-align: middle;" />, 
do pomiaru możemy wykorzystać panel na samej górze aplikacji, który pokazuje m.in jaki kolor wypełnienia, obramowania oraz wysokość (H) i szerokość (W) ma dany element. 


!["Górny panel z informacjami dotyczącymi elementu"][7]
[7]: /images/ps-top-panel.jpg

!["Warstwa zawierająca kształt"][8]
[8]: /images/ps-shape-layer.jpg


Należy jedynie kliknąć na element wykorzystując `Path Selection Tool`

!["Path Selection Tool"][9]
[9]: /images/ps-path-selection.gif




> #### Important::Ważne
>
> Ze względu na pojawienie się wysokiej rozdzielczości, czyli <i>Retiny</i> w komputerach Mac grafiki zaczęto przygotowywać w "podwójnej gęstości". Na czym to polega?
>
>Jeśli chcemy, żeby obrazek docelowo wyświetlił się w rozdzielczości 100x100 pikseli, to plik który przygotowujemy "pod Retinę" powinien mieć wymiary 200x200 pikseli, czyli dwukrotnie większą wysokość i szerokość. 
Dlatego też od jakiegoś czasu graficy zwykli projektować strony www w dwukrotnie większej rozdzielczości. Dzięki temu bez problemu można przygotować assety w dwóch rozmiarach: @2x (oznaczenie dla Retiny) oraz normalnych rozmiarach 1:1.

>W przypadku grafik takich jak ikony czy logotypy warto jest stosować pliki wektorowe. Najlepszym formatem wektorowym przyjaznym środowisku webowemu jest format `SVG`. 
>
>`SVG` (ang. <i>Scalable Vector Graphic</i>) jest skalowalny i odpowiada naszym potrzebom w temacie responsywności, o której być może już słyszeliście. Dzięki temu możemy zwiększać wymiary obrazka bez utraty jakości w odróżnieniu np. od plików `JPG`.

Jeśli chcesz zagłębić się w temat pikseli oraz Retiny przydatna może być lektura <a href="https://www.smashingmagazine.com/2012/08/towards-retina-web/" target="_blank"> artykułu na Smashing Magazine</a>.

Biorąc pod uwagę, to co przeczytaliście w paragrafie powyżej, w pliku `planty.psd` wszystkie elementy oraz wielkość tekstów są dwukrotnie większe. Zatem jeśli będziecie sprawdzać rozmiary elementów i fontów, pamiętajcie o podzieleniu ich przez 2 przy przypisywaniu wartości w CSS.

Przykładowo: jeśli tekst "because we care for plants" ma wielkość `36px`, docelowo nadamy w pliku CSS wartość: 
`font-size: 18px;  /* ponieważ 36px/2 = 18px */`.



## Wygenerowanie assetów w Photoshop Creative Cloud

Photoshop Creative Cloud umożliwia wygenerowanie assetów w bardzo prosty i szybki sposób. Wszystko opiera się na warstwach (ang. <i>layers</i>). Zanim przejdziemy do szczegółów warto zajrzeć do zawartości pliku `planty.psd` (plik znajduje się w <a href="../resources/planty-assets/planty-assets.zip">zaktualizowanej paczce z zasobami</a> ). Z reguły każdy z elementów - zdjęcia, obiekty, teksty są tworzone w oddzielnej warstwie. Umożliwia to łatwą modyfikację poszczególnych elementów, jak i późniejsze łatwe zapisanie odseparowanych elementów na potrzeby zakodowania layoutu. 

### Warstwy
Spróbujmy zajrzeć co kryje się w poszczególnych warstawch, uruchamiając panel warstw: `Window -> Layers`

![Panel z warstwami][10]
[10]: /images/ps-layers-panel.jpg

Poszczególne warstwy powiązane są w grupy, czyli foldery. Dzięki temu każdy element strony pogrupowany jest według swojej przynależności do sekcji na stronie. Warto trzymać porządek i usunąć zbędne warstwy - dzięki temu nie pogubimy się. Rozwijając grupy znajdziecie konkretne elementy.

### Automatyczne generowanie assetów
Pora na wygenerowanie plików z naszego layoutu. Skorzystamy z funkcjonalności, która zawarta jest w najnowszej wersji programu. Włączamy ją poprzez: `File -> Generate -> Image Assets`.

Zwróć uwagę, czy opcja ta jest zaznaczona. Jeśli tak, to automatyczne generowanie assetów na podstawie nazwy warstw jest włączone. Możemy zatem przejść do kolejnego kroku.

W wersji Photohop Creative Cloud mamy możliwość szybkiego zapisywania assetów z poziomu warstw. Wystarczy zmienić nazwę danej warsty np. z `flower-2` na `flower-2.png`, wtedy w folderze, gdzie znajduje się nasz plik .psd, zostaną automatycznie wygenerowane assety z zadaną przez nas nazwą i rozszerzeniem. Assety są zapisywane w podfolderze `planty-assets`. Sprawdźmy teraz czy pojawił się tam plik z danym assetem. 


!["Automatyczne generowanie assetów][11]
[11]: /images/ps-generate-assets.gif

Taką czynność powtarzamy dla elementów, których będziemy potrzebować do zbudowania layoutu. Pamiętajcie, że CSS umożliwia stworzenie wielu obiektów takich jak ramki lub proste figury geometryczne, więc nie musimy zapisywać każdej z warstw do pliku. W przypadku Planty potrzebować będziemy jedynie zdjęć i ikon mediów społecznościowych.










