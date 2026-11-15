# Instrukcje dla agentów sprawdzających tłumaczenie

Polecenia, którymi agenci (modele językowe) sprawdzali polską wersję Escape Academy 2. Każde dostaje paczkę tekstów w
JSON (id, postać, notatka twórców, EN, ES/FR/DE, PL) i zwraca listę podejrzanych kwestii z propozycją poprawki. Wynik
trafia do pliku w `poprawki/` i przeglądamy go na kartach w warsztacie (Import → „Przeglądaj kartami”).

| Plik | Co sprawdza | Kiedy użyty |
|---|---|---|
| `przeglad_rozmow_zadanie.md` | pierwszy przegląd rozmów | po tłumaczeniu maszynowym |
| `kalambury.md` | gry słów w tytułach i nazwach | runda kalamburów |
| `czytanie_probne_aktorzy.md` | „aktorzy” czytają swoje postaci w kontekście scen | dialogi |
| `czytanie_probne_krzyki.md` | to samo dla krótkich kwestii w tle (dopisek do instrukcji aktora) | krzyki w tle |
| `druga_para_oczu_dialogi.md` | niezależne sprawdzenie z EN/ES/FR/DE, podział na „w porządku” / „podejrzane” | teksty „do sprawdzenia” |
| `druga_para_oczu_teksty.md` | to samo dla interfejsu, przedmiotów, podpowiedzi, napisów i nazw postaci | teksty nigdy niesprawdzone |

## Wnioski
- Agenci trafnie **znajdują** problemy, ale ich **propozycje** często są słabsze od samego zgłoszenia. Dlatego zawsze
  przegląda je człowiek, a karty mają przycisk edycji.
- Wąskie, konkretne polecenie działa lepiej niż ogólne „popraw”. Najwięcej dają: lista ustalonych nazw, zasady rodzaju
  gramatycznego (gracz bez płci, Reed niebinarny) i notatki twórców przy kalamburach.
- Przy grze w kilku częściach (Escape Academy 1 i 2) te same pliki da się użyć ponownie – trzeba tylko podmienić listę
  postaci i ustalonych nazw. Zasady pisowni i typografii są w `translations/GLOSARIUSZ.md`.
