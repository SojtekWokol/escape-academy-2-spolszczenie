# Escape Academy 2 po polsku

Nieoficjalne, fanowskie tłumaczenie gry **Escape Academy 2: Back 2 School** na język polski.
Obejmuje menu, zagadki, notatki, napisy, scenki fabularne, rozmowy na kampusie i napisy końcowe.

## Instalacja

1. Pobierz najnowszy plik **EA2-Spolszczenie-….exe** z zakładki [Releases](../../releases).
2. Zamknij grę i uruchom pobrany program. Sam znajdzie grę (aplikacja Xbox / Game Pass albo Steam), w razie potrzeby wskaż jej folder.
3. Kliknij **Zainstaluj**, a potem w ustawieniach gry wybierz język **POLSKI**.

Ten sam program przywraca oryginalną wersję gry (**Przywróć wersję oryginalną**).

**Żeby spolszczenie samo się aktualizowało**, kliknij w instalatorze **Utwórz skrót na pulpicie** i uruchamiaj grę tym skrótem
(„Escape Academy 2 (PL)”). Przed każdym startem sprawdzi, czy spolszczenie jest na miejscu (aktualizacja gry je usuwa) i czy
nie ma nowszej wersji tłumaczenia, i zaproponuje instalację. Pobiera z GitHuba tylko plik z tekstami.

## Jak pomóc

Błędy i propozycje zgłaszaj w [Issues](../../issues): napisz, gdzie w grze jest tekst (zrzut ekranu bardzo pomaga) i jak powinien brzmieć.

Chcesz poprawiać tłumaczenie samodzielnie?

1. Zrób fork i sklonuj to repozytorium.
2. Pobierz **EA2 Warsztat.exe** z wydań [repozytorium warsztatu](https://github.com/SojtekWokol/warsztat/releases) i włóż go do sklonowanego folderu.
3. Uruchom warsztat. Przy pierwszym uruchomieniu wyciągnie teksty z Twojej kopii gry (tekstów gry nie ma w repozytorium).
4. Poprawiaj w warsztacie, sprawdzaj w grze przyciskiem **Wgraj do gry**, a zmienione pliki z `translations/pl/` wyślij jako pull request.

Zasady i nazewnictwo: [translations/GLOSARIUSZ.md](translations/GLOSARIUSZ.md) – przeczytaj, zanim zaczniesz.

### Podpowiedzi od Bielika (opcjonalnie)

Warsztat może podpowiadać tłumaczenia lokalnym, polskim modelem językowym **Bielik**: dokańcza zdanie, które piszesz
(szara podpowiedź, **Tab** przyjmuje), i proponuje trzy warianty całej kwestii. Model działa na Twoim komputerze, bez
internetu. Żeby go włączyć:

1. Zainstaluj [Ollama](https://ollama.com).
2. W PowerShellu pobierz model (ok. 7 GB): `ollama pull SpeakLeash/bielik-11b-v3.0-instruct:Q4_K_M`
3. Uruchom warsztat ponownie – w karcie „Warianty od Bielika” pojawi się „Bielik działa”.

Najlepiej działa z kartą graficzną z 8 GB pamięci; na samym procesorze potrzebuje ok. 12 GB RAM i jest wolniejszy.
Bez Bielika warsztat działa normalnie, tylko bez podpowiedzi.

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
