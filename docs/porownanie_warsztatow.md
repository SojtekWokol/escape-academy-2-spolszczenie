# Porównanie warsztatów: Persona 5 Royal i Escape Academy 2

Stan na 2026-11-12. Cel: ustalić, co trafia do wspólnej bazy, a co zostaje w adapterze gry.

## Największa różnica: technologia

| | P5R (`C:\Games\Persona 5 Royal\_PL\app`) | EA2 (`escapeacademypl`) |
|---|---|---|
| Backend | Rust w Tauri, 28 komend `invoke` (~3,5 tys. linii) | Python stdlib, serwer HTTP na 8770 (~720 linii + data.py) |
| Powłoka | pełna aplikacja Tauri | Tauri jako cienka ramka, która ładuje stronę z serwera |
| Python u gracza | niepotrzebny (jeden .exe) | potrzebny (venv, UnityPy) |
| Obróbka plików gry | w Rust (CPK, BMD/BF/PAK, TBL/FTD, DDS, FNT) | w Pythonie (UnityPy, fonty SDF, katalog Addressables) |
| UI | czysty JS, warstwa `API_NATIVE` mapuje stare `/api/*` na komendy | czysty JS, `fetch` na `/api/*` |

P5R zaczynał w Pythonie (`tools/`, stary `webui`) i został przepisany na Rust. Mapowanie `/api/*` na komendy już istnieje, więc oba UI mówią tym samym „językiem” endpointów.

## Model danych

| | P5R | EA2 |
|---|---|---|
| Klucz kwestii | `#` + 16 znaków SHA-256 z angielskiego tekstu | klucz z gry: `g:KEY`, `v:plik`, `y:line`, `n:line`, `b:`, `c:` |
| Plik tłumaczeń | wiele warstw `text/pl/*.json` (alfabetycznie, późniejszy wygrywa), zakres plików przez regex | jeden `translations/pl.json` |
| Pola wpisu | tylko tekst PL (opcjonalnie osobny dla pliku) | `pl`, `status` (todo/draft/review/done), `t` (czas) |
| Poprawki gracza | osobne `zz_user_scene.json` / `zz_user_all.json` w `%APPDATA%` | zapis wprost do `pl.json` |
| Gdzie leżą dane | trzy miejsca: ship (repo) / cache (`%LOCALAPPDATA%`) / edits (`%APPDATA%`) | wszystko w folderze projektu |
| Publikacja bez tekstów gry | jest (`--publish`, klucze-hashe, kontrola, że nie został angielski) | brak |

Wniosek: P5R jest lepiej przygotowany do repo publicznego i rozdawania (hashe zamiast angielskiego, warstwy zamiast jednego pliku, dane gracza poza repo). EA2 ma bogatszy stan kwestii (statusy, „do sprawdzenia”), którego P5R nie ma.

## Funkcje: co jest gdzie

| Funkcja | P5R | EA2 | Do bazy? |
|---|---|---|---|
| Okno bez ramki, własne przyciski min/max/zamknij | ✓ | ✓ | baza |
| Zakładki + tabele z filtrami | ✓ (limit 600 wierszy) | ✓ | baza (lista zakładek z adaptera) |
| Edytor: lista kwestii, pole PL, warstwa „lustra” z szarą podpowiedzią | ✓ | ✓ | baza |
| Skróty: Tab, Ctrl+Enter, Ctrl+↑/↓, Esc | ✓ | ✓ | baza |
| Dopełnianie słów z naszych tłumaczeń | ✓ | ✓ | baza |
| Bielik: ciąg dalszy + 4 warianty (Ollama) | ✓ | ✓ | baza; prompt i zamiana znaków z adaptera |
| Słownik | z `bible_*.md` + karty postaci | `glossary.json` + nazwy z gry | baza; źródło z adaptera |
| Pamięć tłumaczeń | ✓ | ✓ | baza |
| „Zmień w każdym miejscu” | ✓ | ✓ | baza |
| Kontrola kwestii | `{tagi}`, znaki w foncie, liczba i szerokość linii | `{kody}`, `<tagi>` TMP z zagnieżdżeniem, długość, rodzaj, hasła L,I,T,E,R,Y | szkielet w bazie, reguły w adapterze |
| Blokada zapisu przy błędzie | ✓ (odmawia) | ✗ (tylko ostrzega) | do ustalenia (opcja) |
| Wstążka znaczników | ✗ | ✓ | baza (znaczniki z reguł adaptera) |
| Status kwestii / „do sprawdzenia” | ✗ | ✓ | baza |
| Wyszukiwanie po całym tekście | ✗ | ✓ | baza |
| Zakładka Nazwy z edycją w wierszu | ✓ (limit bajtów) | ✓ | baza; limit z adaptera |
| Zmiany względem wydania (wgrane/niewgrane) + wydania | ✗ | ✓ | baza |
| Licznik postępu | tylko `zrobione/strony` | pasek, licznik całości | baza |
| Okno wgrywania z etapami i paskiem | ✗ (tylko dziennik) | ✓ | baza |
| Poprawki z pliku (eksport/przegląd/przyjęcie) | ✓ (wersja 2, bez angielskiego, status „konflikt”) | ✓ (prostsza) | baza, wersja z P5R |
| Kreator pierwszego uruchomienia (folder gry, kroki) | ✓ | ✗ | baza; kroki z adaptera |
| Szukanie gry (Steam `libraryfolders.vdf`) | ✓ | ✗ (ścieżka na sztywno, Xbox) | baza (Steam, Xbox, ręcznie) |
| Gra uruchomiona → odmowa wgrywania | ✓ | ✓ | baza; nazwa procesu z adaptera |
| Jedno zadanie w tle + wspólny dziennik | ✓ (`jobs.rs`) | ✓ (`BUILD`, `LOG`) | baza |
| Podgląd | dymek z portretem i fontem gry (PNG), czat telefonu | scenka VN (tła, postacie), przycisk, menu, notatka, napisy | adapter |
| Test w grze ze skokiem do sceny | ✓ | ✗ | adapter (P5R) |
| Kolejka scen, kalendarz, arkana | ✓ | ✗ | adapter (P5R) |
| Grafiki z napisami (OCR, bank liter, generator, kolejka ChatGPT) | ✓ (`app_napisy`) | ✗ (zbieramy zrzuty) | przepływ pracy do bazy, źródła tekstur w adapterze |
| Wygląd | czerwień/czerń/papier, skos −12°, Anton + Inter | bordo/żółty/koral, Chunk + Urbanist + Jersey | motyw z adaptera |

## Uwaga do `app_napisy`

To osobna kopia `app` z zakładką Grafiki. Jest **za** `app` (brakuje w niej `keys::SAME`). Zanim cokolwiek wydzielimy, trzeba ją wmerge'ować do `app`, inaczej będą trzy rozjechane wersje zamiast dwóch.

## Decyzja do podjęcia: w czym pisać bazę

1. **Baza w Rust (z P5R), adaptery w Rust albo jako zewnętrzny program.** P5R podłącza się natywnie. EA2 zostawia swoje skrypty w Pythonie tylko do wyciągania tekstów i wgrywania, spakowane jako osobny .exe (PyInstaller, „sidecar” Tauri), a funkcje z `server.py` (statusy, zmiany, wydania, wstążka, okno wgrywania) przechodzą do bazy w Rust. Plus: jeden .exe bez Pythona u ludzi. Minus: najwięcej przepisywania.
2. **Baza w Pythonie (z EA2).** Adapter to moduł Pythona, P5R wraca do Pythona (stare `tools/` jeszcze są, ale nieaktualne). Plus: prościej pisać adaptery, bogate biblioteki do formatów gier. Minus: cofnięcie P5R i trzeba pakować Pythona do rozdania.
3. **Wspólne tylko UI i protokół.** Jeden wspólny frontend i lista endpointów `/api/*`, a każda gra ma własny backend w czym chce. Plus: najmniej pracy na start. Minus: logika (zmiany, poprawki, pamięć, Bielik) dalej podwójna.

Rekomendacja: **wariant 1**. Formaty gier i tak są w adapterach. Wszystko, co wspólne, raz napisane w Rust daje jeden .exe, który każdy może pobrać bez instalowania Pythona, a o to chodzi w planie „każdy może używać warsztatu”. EA2 i tak potrzebuje Pythona tylko do dwóch rzeczy (wyciągnij, wgraj), a to dobrze zamyka się w sidecarze.

## Wspólny model danych (propozycja)

- Klucz: stały klucz z gry, jeśli gra go ma (EA2), albo hash angielskiego (P5R). W repo nigdy angielski tekst.
- Wpis: `pl`, opcjonalnie `status` i `t`. P5R zyskuje „do sprawdzenia”.
- Pliki: warstwy jak w P5R, ale podzielone po miejscach w grze (scena, pokój), jedna kwestia w linii, stała kolejność. Wtedy pull requesty są czytelne i rzadko się kłócą.
- Dane gracza w `%APPDATA%`, tekst gry w `%LOCALAPPDATA%`, w repo tylko polski.
