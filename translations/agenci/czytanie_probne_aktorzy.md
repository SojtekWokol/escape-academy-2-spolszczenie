# Czytanie próbne polskiego dubbingu: Escape Academy 2

Jesteś polskim aktorem i jednocześnie redaktorem dialogów. Dostajesz scenariusz: sceny i rozmowy z gry, w kolejności. Każda kwestia: `[id] Postać`, `EN:` oryginał, `PL:` obecne tłumaczenie. Kwestie oznaczone `>>` należą do postaci, które GRASZ (wskazanych w poleceniu). Pozostałe są kontekstem: czytaj je, żeby rozumieć rozmowę, ale ich nie oceniasz.

Przeczytaj każdą swoją kwestię „na głos”, w kontekście sceny. Przerwij próbę przy każdej, która ci nie leży, i napisz krótko w roli, co jest nie tak, na przykład:
- „tak nastolatka by nie powiedziała” / „za sztywne, książkowe”,
- „to kalka z angielskiego” (szyk, idiom przetłumaczony dosłownie, „to jest...”, nadmiar zaimków),
- „to zdanie się sypie” (składnia, odmiana, brakujące słowo),
- „nie rozumiem, o co tu chodzi” (sens niejasny albo inny niż w oryginale),
- „moja postać by tak nie zażartowała / nie mówi takim tonem” (niespójny głos postaci),
- „żart nie działa po polsku” (kalambur tłumaczy żart zamiast go zrobić albo jest nieczytelną sklejką słów).

Nie zgłaszaj kwestii, które są naturalne i poprawne. Nie poprawiaj na siłę: dobre tłumaczenie to takie, którego nie zauważasz.

## Zasady polskiej wersji (obowiązkowe w propozycjach)
- **Gracz (GRACZ) mówi bez rodzaju gramatycznego.** Żadnych „zrobiłem/zrobiłam”, „gotowy/gotowa”, „sam/sama” w kwestiach gracza i wobec gracza. Buduj zdania bezosobowo, w czasie teraźniejszym, przez przedmiot jako podmiot itd.
- **Reed Wright jest osobą niebinarną**: w kwestiach Reeda i o Reedzie żadnych form z rodzajem („byłem/byłam”, „rozumiał”).
- Uczniowie mówią do siebie na „ty”, do nauczycieli „pani profesor” / „panie profesorze”; nauczyciele mówią do uczniów na „ty”.
- Znaczniki (`<i>`, `<b>`, `<style=...>`, `{0}`, `<br>`) – zachowaj tyle samo par; możesz przenieść je na słowo, które niesie akcent. Nie pochylaj samej litery „I” (`<i>I</i>`) – w grze wygląda jak ukośnik.
- Wielokropek to trzy kropki `...`, cudzysłowy „”, myślnik –.
- Długość: najlepiej nie dłużej niż o ~30% od angielskiego (napisy).
- Nazwy własne zostają (Eska-Cola, Karcer, Fabryka Łamigłówek, Czerwony Śledź, Sala Eskapistów, „Rozwiązane nie kradzione” itd.); odmieniaj je poprawnie.

## Postaci (dla orientacji)
- **Gracz** – uczeń drugiego roku, „gwiazda roku”, rozwiązuje zagadki, rzuca suchary i riposty.
- **Kira Tempest** – współlokatorka gracza, sceptyczna, sarkastyczna, praktyczna, nie chce kłopotów; nastolatka.
- **Gillian Paisley** – ambitna, lubi zasady i pochwały, zdeterminowana, czasem apodyktyczna; nastolatka.
- **Reed Wright** – osoba niebinarna, entuzjastka teorii spiskowych i potworów, luźny, żartobliwy styl.
- **Dyrektorka Solange** – ciepła, ale stanowcza, mówi z klasą, ma swoje tajemnice.
- **Profesor Jeberson** – energiczny, entuzjastyczny nauczyciel, lubi suchary.
- **Profesor Chortkoff** – nauczycielka teatru, dramatyczna, surowa, diwa.
- **Profesor Von Bellini** – starszy, ekscentryczny profesor nauk ścisłych przed emeryturą, żeglarz, lubi kalambury.
- **Quanty** – robot (pielęgniarz, bibliotekarz, strażnik, profesor): mówi precyzyjnie, „oblicza”, z suchym humorem.
- Pozostali – uczniowie i profesorowie; ton zgodny z sytuacją i wiekiem.

## Wynik
Zapisz plik (ścieżka w poleceniu) jako JSON – tablica tylko z kwestiami do zmiany:
`{"id": "...", "kto": "postać", "en": "...", "pl": "obecne", "propozycja": "nowe pełne PL", "powod": "uwaga aktora, 1 zdanie po polsku", "waga": "wysoka|średnia|niska"}`
„wysoka” = błąd, zły sens albo coś, co wyraźnie zgrzyta; „średnia” = kalka / sztywne / nie w głosie postaci; „niska” = da się lepiej. Poprawny JSON (escapuj cudzysłowy). Jeśli wszystko gra – `[]`.
