# Escape Academy 2 po polsku

Nieoficjalne, fanowskie tłumaczenie gry **Escape Academy 2: Back 2 School** na język polski.
Obejmuje menu, zagadki, notatki, napisy, scenki fabularne, rozmowy na kampusie i napisy końcowe.

## Instalacja

1. Pobierz najnowszy plik **EA2-Spolszczenie-….exe** z zakładki [Releases](../../releases).
2. Zamknij grę i uruchom pobrany program. Sam znajdzie grę (aplikacja Xbox / Game Pass albo Steam), w razie potrzeby wskaż jej folder.
3. Kliknij **Zainstaluj**, a potem w ustawieniach gry wybierz język **POLSKI**.

Ten sam program przywraca oryginalną wersję gry (**Przywróć wersję oryginalną**). Po aktualizacji gry zainstaluj spolszczenie ponownie.

## Jak pomóc

Błędy i propozycje zgłaszaj w [Issues](../../issues): napisz, gdzie w grze jest tekst (zrzut ekranu bardzo pomaga) i jak powinien brzmieć.

Chcesz poprawiać tłumaczenie samodzielnie?

1. Zrób fork i sklonuj to repozytorium.
2. Pobierz **EA2 Warsztat.exe** z wydań [repozytorium warsztatu](https://github.com/SojtekWokol/warsztat/releases) i włóż go do sklonowanego folderu.
3. Uruchom warsztat. Przy pierwszym uruchomieniu wyciągnie teksty z Twojej kopii gry (tekstów gry nie ma w repozytorium).
4. Poprawiaj w warsztacie, sprawdzaj w grze przyciskiem **Wgraj do gry**, a zmienione pliki z `translations/pl/` wyślij jako pull request.

Zasady i nazewnictwo: [translations/GLOSARIUSZ.md](translations/GLOSARIUSZ.md).

## Co jest w repozytorium

| Ścieżka | Zawartość |
|---|---|
| `translations/pl/` | polskie teksty, podzielone według miejsc w grze: `pokoje/` (escape roomy), `rozmowy/`, `kampus/`, `scenki.json`, `interfejs.json`, `nazwy.json`, `okrzyki.json`, `napisy-koncowe.json`; w każdym pliku klucz z gry → tekst i status |
| `translations/glossary.json`, `GLOSARIUSZ.md` | słownik i przewodnik stylu |
| `translations/releases/` | wydane wersje tłumaczenia |
| `fonts/` | fonty, z których dorysowujemy polskie litery w grze |
| `.github/workflows/wydanie.yml` | budowa instalatora i wydanie na GitHubie |

## Wydanie nowej wersji

W warsztacie: zakładka **Zmiany** → **Wydaj wersję** (np. `1.1.0`). Zapisz zmiany, zrób commit i wypchnij tag `v1.1.0`.
GitHub Actions zbuduje instalator z tej wersji i dołączy go do wydania.

---

Projekt fanowski, niezwiązany z twórcami gry (Coin Crew Games) ani wydawcą (iam8bit). Do działania potrzebna jest legalna kopia gry.
