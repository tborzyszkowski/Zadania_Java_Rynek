# Zadanie: Regulowany rynek

| Termin oddania | Punkty     |
|----------------|:-----------|
| 30.05.2025  23:00   |    10      |

--- 
Przekroczenie terminu o **n** zajęć wiąże się z karą:
- punkty uzyskanie za realizację zadania są dzielone przez **2<sup>n</sup>**.

--- 

### Napisz program, który ...
 będzie modelował następującą sytuację rynkową:

- **Sprzedawcy** posiadają ograniczoną liczbę produktów w jednostce czasu, 
	które oferują na wolnym rynku po cenach, które zależą od:
    - kosztu wytworzenia produktu
    - inflacji (w czasie spada wartość pieniądza)
    - marży (ile chce na produkcie zarobić sprzedawca).

    Celem sprzedawcy jest osiągnięcie jak największego zysku.

- **Kupujący** posiadają potrzeby, zasady i pieniądze. 
    Obserwują oferty produktów na rynku. Ich zachowanie opisują następujące reguły:
    - chcą kupić określone produkty (podzielone na: pierwszej potrzeby i luksusowe) i śledzą ich ceny ale nie muszą ich kupić natychmiast (można ustalić ile produktów pierwszej potrzeby 
    wymagane jest do przeżycia)
    - mają wiedzę o skali inflacji
    - ich skłonność do zakupu produktu spada wraz z rosnącą ceną produktu, 
	niezależnie czy wzrost cen był spowodowany inflacją czy marżą
    - celem **Kupującego** jest zaspokojenie swoich potrzeb jak najmniejszym kosztem, mieszcząc się w budżecie
    
- **Bank Centralny** obserwuje wzrost cen produktów oraz obroty na rynku.
    Ustala bieżący poziom inflacji. Bank stara się utrzymać stałe wpływy podatkowe liczone jako 
    iloczyn inflacji i obrotów przy danej inflacji. Przygotować odpowiednie testy sprawdzające stabilność wpływów Banku oraz ich odporność na zakłócenia.
    
    
### Wykorzystaj:
- [**Wzorzec odwiedzający**](https://refactoring.guru/pl/design-patterns/visitor/java/example) do aktualizacji danych o produktach u sprzedawców oraz parametrów kupujących.
- [**Wzorzec obserwator**](https://refactoring.guru/pl/design-patterns/observer/java/example) do pasywnego obserwowania następujących zmian:
    - Sprzedawcy i Kupujący obserwują Bank Centralny by dowiedzieć się jaki jest poziom inflacji
    - Kupujący obserwują oferty Sprzedawców i mogą na nie reagować ale nie muszą
	- Bank Centralny obserwuje Sprzedawców i Kupujących, by korygować algorytm inflacyjny utrzymujący 
	stałe wpływy podatkowe.
  
Zaimplementowana gra turowa powinna po wielu turach stabilizować się na poziomach będących celem poszczególnych grup uczestników.
	
### Uwaga 1
Projekt powinien również zawierać odpowiednie testy jednostkowe do implementowanej funkcjonalności.

### Uwaga 2
Dla uproszczenia implementacji można rozważyć implementację opartą na turach.
