# Elementy blokowe i liniowe 

W naszym tutorialu pojawiło się już kilkanaście znaczników HTML. Przyszła pora na kolejne, bardzo ważne tagi jakimi są `<div>` i `<span>`. Być może zetknęliście się już z tymi nazwami. Jeśli nie to nic straconego - zaczynamy!
W tym rozdziale dowiecie się co to znaczy, że element jest blokowy lub liniowy. Ta wiedza bardzo przyda się przy budowaniu layoutu.

## `<div>`, czyli kontener

Znacznik `<div>` spełnia funkcję kontenera, w którym zawarte są powiązane ze sobą elementy. Ma bardziej ogólne i mniej specfyiczne zastosowanie niż wspomniany wcześniej `<section>`. Może być używany w różnoraki sposób. 

Wyobraźmy sobie, że na naszej stronie występuje sekcja "Autorzy", w której zawartych jest kilka kontenerów ze zdjęciami i opisami osób. 
Jak by wyglądał kod HTML takiego rozwiązania?

```html
<section id="authors">
	<!--kontener dla autora-->
	<div class="author-box">
		<h2>Jane Doe</h2>
		<img src="images/jane-img.jpg"/>
		<p>Jane loves cookies and spend her time riding a bike</p>
	</div>
	<!--koniec kontenera-->

	<!--kontener dla autora-->
	<div class="author-box">
		<h2>Sam Smith</h2>
		<img src="images/sam-img.jpg"/>
		<p>Sam likes swimming and eating burgers.</p>
	</div>
	<!--koniec kontenera-->

	<!--kontener dla autora-->
	<div class="author-box">
		<h2>Kim Sofa</h2>
		<img src="images/kim-img.jpg"/>
		<p>Kim is keen on watching movies and jogging</p>
	</div>
	<!--koniec kontenera-->
</section>
```

Tak jak widzcie sylwetka każdego autora, zosała umieszczona w konterze, jakim jest `<div>`. 
Znacznik ten zatem umożliwia nam powiązać elementy w dany sposób. Dzięki czemu zawartość staje się jeszcze bardziej uporządkowana.

<!-- ![Przykładowy layout strony][1]
[1]: /images/ps-units.png
 -->



> #### Important::Ważne
>
> Pamiętajcie, żeby znacznik `<div>` zawsze został zamknięty `</div>`. W przypadku bardziej rozbudowanego layoutu i wielokrotnego pojawienia się tego tagu można się łatwo pogubić, więc starajmy się o to by każdy `<div>` zamykał się w odpowiednim miejscu.
>
> Kolejna ważna informacja to fakt, że `<div>` jest **elementem blokowym**. Co to oznacza? Możecie zauważyć, korzystając z Narzędzi Developerskich, że `<div>` zajmuje całą szerokość naszej strony. Jest blokiem, który 'rozpycha się' na całej szerokości dostępnego miejsca w przeglądarce. Pomimo, że jego zawartość zajmuje jedynie jej część. 
>
>Elementem blokowym jest także nagłówek dowolnego stopnia. W celu weryfikacji, stwórzmy nagłówek np. `<h1>Cześć</h1>` i sprawdź jak jest on odczytywany w Narzędziach Developerskich. Pomimo, że tekst zajmuje część całej szerokości, to nagłówek 'rozpycha się' na całą szerokość.


