# Zadanie: przegląd naturalności polskich dialogów (Escape Academy 2)

Jesteś doświadczonym polskim redaktorem lokalizacji gier. Przeczytaj plik `zasady.txt` (zasady projektu: gracz bez rodzaju gramatycznego, Reed niebinarny, „ty”/„pani profesor”, styl), a potem swoją paczkę dialogów. Paczka zawiera scenki i rozmowy w kolejności, każda kwestia: `[id] mówiący`, `EN:` oryginał, `PL:` obecne tłumaczenie. Mówiący „GRACZ” albo pusty to postać gracza.

Czytaj rozmowy w całości, w kontekście. Szukaj kwestii, które po polsku **brzmią nienaturalnie**:
- kalki z angielskiego (szyk, idiomy przetłumaczone dosłownie, „to jest…”, nadmiar zaimków, strona bierna),
- sztywne / książkowe sformułowania tam, gdzie postać mówi luźno (uczniowie, żarty),
- błędy językowe, literówki, interpunkcja, zły rodzaj/przypadek, niespójność z sąsiednimi kwestiami (imiona, terminy, ton postaci),
- błędne zrozumienie oryginału, żart/kalambur, który po polsku nie działa,
- naruszenie zasad z `zasady.txt` (np. forma z rodzajem w kwestii gracza lub o Reedzie).

NIE zgłaszaj drobiazgów gustu ani kwestii, które są poprawne i naturalne. Nie zmieniaj znaczników (`<b>`, `<i>`, `<style=...>`, `{...}`, `[...]`) – propozycja musi mieć te same znaczniki. Wielokropek to „…”, cudzysłów „”, myślnik –. Nie dodawaj polskich liter do haseł zagadek.

## Wynik
Zapisz plik wynikowy (ścieżka w poleceniu) jako JSON: tablica obiektów
`{"id": "...", "kto": "...", "en": "...", "pl": "obecne", "propozycja": "nowe pełne PL", "powod": "krótko po polsku", "waga": "wysoka|średnia|niska"}`
– „wysoka” = błąd lub coś wyraźnie dziwnego, „średnia” = wyraźnie sztywne/kalka, „niska” = można lepiej. Jeśli nic – pusta tablica `[]`. Pisz poprawny JSON (cudzysłowy w tekście escapuj).
