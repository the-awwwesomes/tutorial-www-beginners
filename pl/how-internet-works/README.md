# Jak działa Internet?

> #### Info::Ta sekcja została zaczerpnięta z tutoriala warsztatów Django Girls
>
> Bardzo dziękujemy twórcom [tutoriala Django Girls](http://tutorial.djangogirls.org/pl/) za udostępnienie nam tekstu rozdziału!

Możemy się założyć, że używacie go każdego dnia. Ale czy naprawdę wiecie co się dzieje, gdy wpisujecie w przeglądarce adres http://theawwwesomes.org i wciskacie *enter*?

Aby zrozumieć jak działa Internet powinniście najpierw dowiedzieć się czym tak naprawdę jest strona internetowa, a jest ona tylko zbiorem plików zapisanych na dysku twardym. Tak samo jak Wasze zdjęcia, muzyka czy filmy. Aczkolwiek strony internetowe różnią się od nich tym, że zawierają kod komputerowy zwany HTML.

Jeśli nie mieliście wcześniej do czynienia z programowaniem, może być Wam na początku trudno zrozumieć HTML, ale przeglądarki internetowe (takie jak Chrome, Safari, Firefox itd.) uwielbiają go. Zostały one zaprojektowane po to, by czytać ten kod, przetwarzać go i postępować zgodnie z jego instrukcjami. Prezentują pliki, z których składa się Twoja strona - by wyglądała dokładnie tak jak Ty chcesz.

Tak jak w przypadku każdego innego pliku, musimy umiejscowić pliki HTML na dysku twardym. Do przechowywania plików HTML używamy specjalnych, potężnych komputerów zwanych *serwerami (ang. servers)*. Serwery nie posiadają monitorów, myszy ani klawiatur, ich głównym celem jest przechowywanie danych i serwowanie ich. Dlatego są one nazywane *serwerami* - ponieważ służą do *serwowania* danych.

Ok, ale pewnie chcielibyście wiedzieć jak wygląda Internet?

Narysowaliśmy Ci schemat Internetu! Wygląda tak:

![Rysunek 1.1][1]

 [1]: images/internet_1.png

Wygląda dość chaotycznie, prawda? W rzeczywistości jest to sieć połączonych między sobą maszyn (wspomnianych wyżej *serwerów*). Setki tysięcy maszyn! Wiele, wiele kilometrów kabli na całym świecie! Możecie wejść na stronę [Submarine Cable Map](http://submarinecablemap.com) i sami zobaczyć jak skomplikowana jest ta sieć. Oto zrzut ekranu ze strony internetowej:

![Rysunek 1.2][2]

 [2]: images/internet_3.png

To fascynujące, prawda? Ale oczywiście niemożliwe jest stworzenie bezpośredniego połączenia kablowego między każdym komputerem w Internecie. Więc aby dostać się do maszyny dostępnej w Internecie (na przykład tej, na której zapisane jest http://theawwwesomes.org) potrzebujemy wykonać zapytanie przechodzące przez wiele, wiele różnych maszyn.

Wygląda to tak:

![Rysunek 1.3][3]

 [3]: /images/img1-3.png

Wyobraźcie sobie, że po wpisaniu http://theawwwesomes.org, wysyłacie list o treści: "Drodzy Awwwesomes, chcę zobaczyć stronę theawwwesomes.org. Wyślijcie ją do mnie, proszę!"

List trafia do urzędu pocztowego najbliżej Was. Potem idzie do drugiego urzędu, który znajduje się trochę bliżej Waszego adresata. Potem do kolejnego, kolejnego, kolejnego, aż w końcu zostanie doręczony do miejsca przeznaczenia. Ciekawa rzecz - jeśli wyślecie wiele listów (*pakietów danych*) do tego samego adresata, mogą przejść przez zupełnie inne urzędy pocztowe (*routery*). To zależy od tego w jaki sposób zostaną rozdzielone w każdym urzędzie.

![Rysunek 1.4][4]

 [4]: /images/img1-4.png

Tak, to takie proste. Wysyłacie wiadomości i oczekujecie jakiejś odpowiedzi. Oczywiście, zamiast papieru i długopisu używacie bitów danych, ale koncepcja jest dokładnie taka sama!

Zamiast adresów z nazwą ulicy, miastem, kodem pocztowym oraz nazwą kraju, używa się adresów IP. Wasze komputery najpierw pytają serwer DNS (system nazw domenowych, ang. DNS - Domain Name System) o przetłumaczenie theawwwesomes.org na adres IP. Działa to podobnie do dawnych książek telefonicznych, w których mogliście poszukać adresu czy numeru po nazwisku osoby, z którą chcieliście się skontaktować.

Listy muszą spełniać konkretne warunki, żeby zostały poprawnie doręczone: muszą posiadać adres, znaczek itd. Muszą być też napisane językiem zrozumiałym dla odbiorcy. To samo dotyczy *pakietów danych*, które wysyłacie, by zobaczyć jakąś stronę. Używany jest protokół HTTP (Hypertext Transfer Protocol).

Tak więc, ogólnie rzecz ujmując, jeśli chcecie mieć swoją stronę internetową musicie mieć *serwer* (komputer), gdzie będzie ona funkcjonować. Gdy *serwer* odbiera przychodzące *żądania* (Wasz list), wysyła Wam w odpowiedzi Waszą stronę (kolejny list).
