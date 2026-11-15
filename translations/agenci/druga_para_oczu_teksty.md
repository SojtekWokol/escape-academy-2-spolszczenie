# Druga para oczu: teksty z gry Escape Academy 2 (napisy, interfejs, przedmioty, podpowiedzi, krzyki w tle, nazwy postaci)

Dostajesz plik JSON z tekstami gry. Każdy ma: `id`, `who` (kto mówi; puste = napis/interfejs), `note` (notatka twórców gry – często wyjaśnia grę słów: „pun on …”), `en` (oryginał), `es`/`fr`/`de` (oficjalne tłumaczenia – pomagają zrozumieć sens), `pl` (nasze tłumaczenie), `puzzle` (true = część zagadki). Teksty są posortowane po id, więc obok siebie leżą teksty z tego samego pokoju/zadania – używaj ich jako kontekstu i pilnuj spójności między nimi.

Dla KAŻDEGO tekstu zdecyduj: w porządku czy podejrzany. Zgłaszaj tylko realne problemy:

1. **Gra słów przetłumaczona dosłownie** – najczęstszy błąd. Jeśli `note` lub oryginał ma kalambur, a polski tekst jest dosłownym tłumaczeniem, które po polsku nic nie znaczy (np. „Sosnowe marzenia o wygranej” z „Pining for a Win”, „Jeszcze raz, z węgorzem” z „Once More With Eeling”), zgłoś i zaproponuj polski kalambur, który działa od razu (np. znany idiom z podmienionym słowem: „I po zagadkach!” z „po ptakach”, „Zagadki są po to, żeby je rozwiązywać”). Sklejki słów nie do wymówienia („asy-klucz-tent”) są złe. Jeśli dobrego kalamburu nie ma – naturalne zdanie bez żartu jest lepsze niż żart, który nie działa.
2. Zły lub zgubiony sens (porównaj z EN/ES/FR/DE), błąd gramatyczny, odmiana, literówka, kalka brzmiąca nienaturalnie.
3. **Rodzaj gramatyczny wobec gracza** (gracz nie ma płci) i u/o Reedzie Wrighcie (osoba niebinarna): żadnych „zrobiłeś/zrobiłaś”, „gotowy/gotowa”, „sam/sama”, męskich rzeczowników w wołaczu do gracza („uciekinierze”). W kwestiach postaci o znanej płci (Uczeń/Uczennica, profesorowie) rodzaj mówiącego jest OK.
4. Cele zadań: „Odblokuj X” przy przedmiocie zamkniętym na kłódkę brzmi jak menu gry – lepiej „Zdobądź/Otwórz X”. „Odblokuj” zostaje przy osiągnięciach i odblokowywaniu obszarów gry.
5. Znaczniki (`<i>`, `<b>`, `<style=…>`, `<color=…>`, `<br>`, `{0}`, `{@…}`) – ta sama liczba co w EN; samotne `<i>I</i>` złe. Myślnik w zdaniu to „–”, nie „-”. Wielokropek „...”.
6. **Zagadki (`puzzle: true`) i hasła:** hasła tylko A–Z bez polskich liter. Jeśli zmiana tekstu zepsułaby logikę zagadki (liczby, kolejność, litery na kłódce), nie proponuj jej – opisz tylko problem w „powod”.
7. Spójność nazw z listą niżej i między tekstami w paczce.

**Nie zgłaszaj** rzeczy poprawnych tylko dlatego, że da się „ładniej”. Nazwy własne postaci z gry (Reina Wym, Sameer Gaspard, Eel Barnes, Solange itp.) zostają.

## Ustalone nazwy
gwiazda roku (gracz), zajęcia wprowadzające (orientation), gaz niepamięci, Sala Eskapistów, Fabryka Łamigłówek, wieża meteo, Karcer (miejsce) / koza (kara), Czerwony Śledź (statek), śledzie-zmyłki (znajdźki, Red Herrings), Łódź Ucieczek (Escape Boat), magazyn (Store Room), Wydział Nauk Ścisłych / Humanistyczny / Sztuki, Kurkuma (szczurzyca), Liga Naukowców Przeciwko Ucieczkom, Skrzynia cudów Sameera, Szyfrezuma, Sudokąska, Żywo-Cola, Eska-Cola, Pizzeria Zjarany Piec, BąbloKlucz, „Rozwiązane nie kradzione”, Limetkada, Binarny elementarz, Taniec z kłódkami, Kurier Eskapisty (The Escapist Times), Zgadzwonki (Cluebells), Kłódkoczuby (Lockscombs), Szyfreston, Krok kłódkowy, Szyfrówka (Clueliard), Bertrand Rozwiązalski, Peter Tropiński, Chet Łotrowicz, Ruby Niewinowska, „dla bystrzaków” (For Dummies). Eel Barnes to legendarny eskapista (człowiek) – „eel” w kalamburach to on, nie ryba.

## Wynik
Zapisz plik (ścieżka w poleceniu) jako poprawny JSON:
```
{"sprawdzone": <liczba tekstów w paczce>, "podejrzane": [
  {"id": "...", "powod": "1–2 zdania po polsku: co jest nie tak (przy kalamburze: na czym polega oryginalny żart)", "propozycja": "pełny poprawiony tekst PL z tymi samymi znacznikami (pusty \"\" przy zagadce, której nie da się bezpiecznie zmienić)", "waga": "wysoka|średnia|niska"}
]}
```
„wysoka” = zły sens, błąd, rodzaj, zepsuta zagadka; „średnia” = kalambur nie działa, kalka; „niska” = drobiazg. Teksty spoza listy uznajemy za w porządku. Escapuj cudzysłowy w JSON.
