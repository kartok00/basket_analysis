# Skrypt Mówcy — Analiza Koszykowa (15 minut)

> Styl: krótko, konkretnie, biznes + dane. Nie czytaj slajdu, dopowiadaj sens.

---

## Plan czasu (na stoper)

1. Slajd 1: 0:35
2. Slajd 2: 0:50
3. Slajd 3: 0:55
4. Slajd 4: 0:55
5. Slajd 5: 1:20
6. Slajd 6: 1:15
7. Slajd 7: 0:55
8. Slajd 8: 1:15
9. Slajd 9: 1:40
10. Slajd 10: 1:40
11. Slajd 11: 1:00
12. Slajd 12: 1:10
13. Slajd 13: 0:35
14. Slajd 14: 0:55

Suma: 15:00

---

## SLAJD 1: Tytuł (0:35)

> „Dzisiaj odpowiadam na jedno pytanie biznesowe: co promować z Nivea i Health & Beauty, żeby zwiększać GMV 1P. Pokażę pełną drogę: od pytania, przez dane, do decyzji biznesowej.”

---

## SLAJD 2: Kontekst zespołu 1P (0:50)

> „To analiza zespołu 1P. Pracujemy między biznesem a data engineeringiem: bierzemy pytania brand managerów, przekładamy je na analizę i wracamy z rekomendacją. Ten case dokładnie tak wyglądał.”

---

## SLAJD 3: Problem biznesowy (0:55)

> „Michał, opiekun Nivei, potrzebował argumentów do rozmowy z marką: co klienci kupują razem z Niveą i gdzie jest potencjał cross-sellingu. Rozbiliśmy to na trzy pytania: H&B ogółem, Nivea, i sezonowość.”

---

## SLAJD 4: Ograniczenia danych (0:55)

> „Pracujemy na danych 1P, więc to nie jest pełny rynek. Widzimy tylko nasze transakcje. To ważne, bo taki insight idzie później do negocjacji z marką i musi być poprawnie osadzony.”

---

## SLAJD 5: Metoda - Apriori (1:20)

> „Wybraliśmy analizę koszykową Apriori, bo odpowiada na pytanie: co występuje razem w koszyku. Dostajemy reguły i trzy metryki: support, confidence i lift. Najważniejsze: wynik jest czytelny dla biznesu i da się go przełożyć na działanie.”

---

## SLAJD 6: SQL - przygotowanie danych (1:15)

> „W SQL były dwa kluczowe kroki: usunięcie koszyków jednoproduktowych i dodanie sezonu: Summer, Winter, Other. Dzięki temu w Pythonie pracujemy już na danych gotowych do porównań sezonowych.”

---

## SLAJD 7: Słownik metryk (0:55)

> „Support mówi o skali, confidence o prawdopodobieństwie, a lift o sile ponad przypadek. Praktycznie: lift poniżej 1.2 traktujemy ostrożnie, powyżej 1.5 to mocny sygnał. Metryki czytamy zawsze razem.”

---

## SLAJD 8: Python - implementacja (1:15)

> „W Pythonie robimy macierz koszykową, uruchamiamy Apriori i filtrujemy reguły dla H&B albo Nivea jako antecedent. Dla całego roku min_support jest wyższy, dla sezonów niższy, bo próbki są mniejsze.”

---

## SLAJD 9: Health & Beauty - wyniki i sezonowość (1:40)

> „W H&B najmocniejsze relacje to Supermarket + Home oraz Home Decoration. W sezonowości widać to jeszcze lepiej: Summer 1.89, Winter 1.68, Other 1.80 dla Supermarket + Home. Home Decoration też jest stabilnie wysokie.
>
> Dodatkowo zimą dochodzi Electronics z liftem 1.06, czyli sygnał prezentowy, ale słabszy niż główne relacje.
>
> Wniosek: H&B ma mocny kontekst domowo-zakupowy przez cały rok, z lekką domieszką sezonowych okazji.”

---

## SLAJD 10: Nivea - wyniki i sezonowość (1:40)

> „W ujęciu całorocznym: Fashion + Supermarket 1.26, Fashion 1.06, Home Decoration 1.13, Building & Industry 1.03. To wygląda przeciętnie, dopóki nie zrobimy segmentacji sezonowej.
>
> Latem najmocniej działają Sport & Leisure 1.56 i Garden 1.21. Zimą rosną Fashion + Supermarket 1.37 oraz Building & Industry 1.10, a Home ma 1.07. W Other dominuje Home 1.19.
>
> Klucz: Nivea ma wyraźny scenariusz sezonowy, którego nie widać w średniej rocznej.”

---

## SLAJD 11: Najczęstsze błędy analityczne (1:00)

> „Trzy ryzyka: po pierwsze nadinterpretacja niskiego lifta, po drugie czytanie lifta bez skali i confidence, po trzecie pomijanie ograniczeń 1P. I najczęstszy błąd: brak segmentacji sezonowej.”

---

## SLAJD 12: Efekt biznesowy (1:10)

> „Michał poszedł do Nivei z naszymi danymi, nie z intuicją. Konkret: letni sygnał Sport 1.56. Efekt: decyzja o starcie letniego mix brand selling. To pokazuje wartość analityki jako narzędzia negocjacyjnego.”

---

## SLAJD 13: Materiały (0:35)

> „Oddajemy komplet: notebook, SQL i wizualizacje. Ten framework można łatwo przenieść na inną markę i kategorię.”

---

## SLAJD 14: 5 rzeczy do zapamiętania (0:55)

> „Po pierwsze, lift interpretujemy z support i confidence. Po drugie, sezonowość to obowiązek, nie dodatek. Po trzecie, 1P to nie cały rynek. Po czwarte, jakość SQL decyduje o jakości insightu. I po piąte, analityka ma prowadzić do decyzji biznesowej.”

---

*Wersja 12 minut: skróć slajdy 6 i 7 do 30 sekund każdy oraz slajd 11 do 40 sekund.*
