# Zadanie: polskie kalambury w Escape Academy 2

Jesteś polskim redaktorem lokalizacji gier, specjalistą od gier słownych. W swojej paczce (JSON) masz teksty, przy których twórcy gry napisali w notatce (`note`), że to kalambur. Każdy wpis: `id`, `room` (pokój), `note` (notatka twórców, wyjaśnia żart), `en` (oryginał), `es`/`fr`/`it`/`de` (jak to zrobiły inne wersje – inspiracja, nie wzór), `pl` (obecne polskie tłumaczenie).

Większość to komentarze **postaci gracza** do przedmiotów w pokoju (gracz ogląda rzecz i rzuca suchar), czasem napisy, tytuły książek, szyldy.

Dla każdego wpisu zdecyduj: czy obecny polski tekst **działa jako żart po polsku**? Jeśli tak – pomiń go (nie wpisuj do wyniku). Jeśli nie – zaproponuj nowy.

## Czego chcemy (decyzje redaktora z dzisiejszej weryfikacji)

Dobre przykłady (przyjęte):
- *Dorm Sweet Dorm* → „Mój akademik, moja twierdza” (polskie powiedzonko zamiast kalki „Akademik, słodki akademik”).
- *A tad shelfish…* → „Zająć całą półkę? Można było chociaż <i>pół na pół</i>, nie?”
- *Too cool to have a bone to pick* (szkielet) → „Zbyt wyluzowany na jakiekolwiek kości niezgody...”
- *looking pretty hip* (szkielet w okularach) → „Ten gość to luzak do szpiku kości.”
- *science was my only vise* (imadło) → „Nauka wciągnęła mnie na dobre... trzyma jak w imadle.”
- *Dish baby* (antena) → „Ten talerz pewnie serwuje same pyszne sygnały.”
- *RAM my way in* → „Chyba lepiej nie wyważać tych drzwi RAM-ieniem, co?”
- *dis-plaster* (wiadro gipsu) → „Jeśli nie wejdę na szczyt wieży na czas, to chyba skończę w gipsie!”
- *Checking Out Uranus* → „Odkrywanie Dupitera – przewodnik dla początkujących miłośników teleskopów”
- *In Escape We Trust* (banknot) → „Veni, vidi, evasi”
- *Snackdoku* → „Sudokąska”
- *staple of dessert* (zszywka w galaretce) → „Galaretka z nadzieniem... biurowym.” (jeśli kalambur się nie da, lepiej zabawne zdanie bez gry słów niż na siłę)
- *putt-ing Turmeric to the test* → „...lubi wystawiać Turmeric na próbę... na każdym dołku.”
- *That's not wheely a good idea* → „Nie, to się dobrze nie potoczy.”

Odrzucone (tak NIE):
- sklejki i słowotwory, których nikt nie odczyta: „deska wędlin-wskazówek”, „gips-katastrofa”, „półka-chciwość”, „Sameer-pał”;
- **Nie objaśniaj ani nie doklejaj żartu.** Gra słów ma siedzieć w jednym słowie albo zwrocie; drugie znaczenie dopowiada kontekst (przedmiot, przy którym pada kwestia, jest na ekranie). Złe wzorce: porównanie dopisane na końcu („Czas się stąd zmyć – jak kreda z tablicy”), drugie znaczenie wtrącone w środek („Oby na moim koncie – i na tej tablicy – zapisała się…”), objaśnienie („…znaczy, później”, „klucz… a właściwie klawisz”), dwa tłumaczenia sklejone spójnikiem („załatwiona na amen i otrzepana z kredy”). Dobrze: „Czas się stąd zmyć.” przy tablicy z kredą. Jeśli żart działa tylko z dopowiedzeniem – zaproponuj zwykłe naturalne zdanie.
- tłumaczenie żartu zamiast żartu: „Oto prawdziwa zszywka... znaczy podstawa deserów!”;
- doklejone zdanie, które nie wynika z poprzedniego: „...pozwoli mi jeszcze sobie pomóc. Ser-decznie proszę!”;
- kalki idiomów: „mieć z kimś kości do obgryzienia”, „W świecie śmieciowych nie dam rady”;
- zwroty z innym znaczeniem w polszczyźnie: „to się nie kręci” (kojarzy się z „nie kręci mnie to”);
- dopisywanie postaci cech, których nie ma w oryginale (np. „pikantny w żartach”, gdy oryginał mówi o odwadze);
- dopisywanie zdań, których nie ma w oryginale.

## Zasady
1. Najlepiej: **naturalne polskie powiedzonko/idiom z podwójnym sensem**, związane z przedmiotem, krótkie. Suchar może być suchy – tak jak w oryginale.
2. **Gracz bez rodzaju gramatycznego**: żadnych form -łem/-łam, -łeś/-łaś, „gotowy/gotowa”, „sam/sama” o graczu. Buduj zdania bezosobowo, w czasie teraźniejszym, przez przedmiot jako podmiot itd.
3. Długość: najlepiej nie dłużej niż o ~30% od angielskiego (napisy i dymki mają ograniczone miejsce).
4. Znaczniki (`<i>`, `<b>`, `<u>`, `<style=...>`, `{0}`, `<br>`) – ta sama liczba par co w oryginale; możesz je przenieść na polskie słowo, które niesie żart.
5. Jeśli żart jest **częścią zagadki** (wyróżnione litery, symbole chemiczne, cyfry, kolory, liczby, coś, co gracz ma odczytać) – zachowaj to, co zagadka koduje, i zaznacz w powodzie „ZAGADKA”. W razie wątpliwości lepiej pominąć wpis niż zepsuć zagadkę.
6. Imiona i nazwy własne postaci zostają; odmieniaj je poprawnie.
7. Wielokropek to trzy kropki `...` (nie znak „…”), cudzysłowy „”, myślnik –.
8. Przeczytaj też, co zrobiły inne wersje językowe – często mają dobry pomysł na kierunek.

## Wynik
Zapisz plik (ścieżka w poleceniu) jako JSON – tablica obiektów tylko dla wpisów do zmiany:
`{"id": "...", "en": "...", "pl": "obecne", "propozycja": "nowe", "powod": "1–2 zdania po polsku: na czym polega żart w oryginale i w propozycji", "waga": "wysoka|średnia|niska"}`
„wysoka” = obecne nie działa / jest dziwne lub błędne, „średnia” = da się wyraźnie lepiej, „niska” = drobna poprawa. Poprawny JSON (escapuj cudzysłowy). Jeśli wszystko działa – `[]`.
