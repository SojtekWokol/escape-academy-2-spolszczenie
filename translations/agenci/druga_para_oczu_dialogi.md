# Druga para oczu: weryfikacja polskich tłumaczeń Escape Academy 2

Dostajesz plik JSON z kwestiami gry. Każda ma: `id`, `who` (postać; „GRACZ” = gracz, puste = napis/interfejs), `note` (kontekst), `en` (oryginał), `es`/`fr`/`de` (oficjalne tłumaczenia – pomagają zrozumieć sens, gdy angielski jest dwuznaczny), `pl` (nasze tłumaczenie), `before` (2 poprzednie kwestie).

Twoje zadanie: dla KAŻDEJ kwestii zdecyduj, czy polski tekst jest **w porządku**, czy **podejrzany**.

**Podejrzany** tylko gdy jest realny problem:
- zły lub zgubiony sens (porównaj z EN i z ES/FR/DE), przeinaczenie, brak części zdania,
- błąd gramatyczny, odmiany, składni, literówka, zdanie się sypie,
- wyraźna kalka, która brzmi nienaturalnie po polsku,
- forma z rodzajem gramatycznym u gracza lub wobec gracza albo u Reeda Wrighta / o Reedzie (osoba niebinarna): „zrobiłem/zrobiłam”, „gotowy/gotowa”, „sam/sama”, „zrobiłeś/zrobiłaś”,
- znaczniki (`<i>`, `<b>`, `<color=…>`, `{0}`, `<br>` itd.) zgubione lub inna liczba niż w EN; samotne `<i>I</i>`,
- niezgodność z ustalonymi nazwami (lista niżej).

- **Nie objaśniaj ani nie doklejaj żartu.** Gra słów ma siedzieć w jednym słowie albo zwrocie; drugie znaczenie dopowiada kontekst (przedmiot, przy którym pada kwestia, jest na ekranie). Złe wzorce: porównanie dopisane na końcu („Czas się stąd zmyć – jak kreda z tablicy”), drugie znaczenie wtrącone w środek („Oby na moim koncie – i na tej tablicy – zapisała się…”), objaśnienie („…znaczy, później”, „klucz… a właściwie klawisz”), dwa tłumaczenia sklejone spójnikiem („załatwiona na amen i otrzepana z kredy”). Dobrze: „Czas się stąd zmyć.” przy tablicy z kredą. Jeśli żart działa tylko z dopowiedzeniem – zaproponuj zwykłe naturalne zdanie.

**W porządku** – wszystko inne, także gdy dałoby się „trochę ładniej”. Nie szukaj na siłę. Swobodne tłumaczenie, zmieniony żart lub gra słów działająca po polsku są OK. Wielokropek „...”, formy męskoosobowe dla grup i „oboje” są OK.

## Ustalone nazwy (poprawne – nie zgłaszaj ich jako błąd)
zajęcia wprowadzające (orientation), gaz niepamięci, Sala Eskapistów, Fabryka Łamigłówek, wieża meteo, Karcer (miejsce) / koza (kara), Czerwony Śledź (statek), śledź-zmyłka (znajdźki), Kurkuma (szczurzyca, rodzaj żeński), Naukowcy Przeciwko Ucieczkom / Liga Naukowców Przeciwko Ucieczkom, Skrzynia cudów Sameera, Szyfrezuma, Sudokąska, Żywo-Cola, Pizzeria Zjarany Piec, BąbloKlucz, „Rozwiązane nie kradzione”, Limetkada, Binarny elementarz, Taniec z kłódkami, Eska-Cola, Bertrand Rozwiązalski, Peter Tropiński, Chet Łotrowicz, Ruby Niewinowska, wołacz „Kiro”. Przyciski akcji w nawiasach: (Kontynuuj historię), (Daj {0} $) itd.

## Wynik
Zapisz plik (ścieżka w poleceniu) jako poprawny JSON:
```
{"sprawdzone": <liczba kwestii w paczce>, "podejrzane": [
  {"id": "...", "powod": "1 zdanie po polsku, konkretnie co jest nie tak", "propozycja": "pełny poprawiony tekst PL (z tymi samymi znacznikami)", "waga": "wysoka|średnia|niska"}
]}
```
„wysoka” = zły sens / błąd gramatyczny / rodzaj; „średnia” = kalka, nienaturalne; „niska” = drobiazg. Kwestie, których nie ma w „podejrzane”, uznajemy za w porządku. Escapuj cudzysłowy w JSON.
