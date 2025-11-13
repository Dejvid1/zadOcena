rozdzial3
=========

Opanowanie czterech filarów to podstawa, ale efektywne programowanie
obiektowe wymaga również znajomości wzorców i zasad projektowania, które
pomagają tworzyć kod elastyczny, łatwy w utrzymaniu i odporny na błędy.

**Konstruktory i Destruktory**

Obiekty mają swój cykl życia.

-  **Konstruktor:** To specjalna metoda, która jest automatycznie
   wywoływana w momencie tworzenia nowego obiektu (instancjacji). Jej
   głównym zadaniem jest inicjalizacja atrybutów obiektu, czyli nadanie
   im wartości początkowych (np. ustawienie salda na 0 dla nowego konta
   bankowego).

-  **Destruktor:** To metoda (rzadziej używana w językach z
   automatycznym zarządzaniem pamięcią, jak Python czy Java) wywoływana
   tuż przed zniszczeniem obiektu. Może służyć do "posprzątania" po
   obiekcie, np. zamknięcia połączenia z bazą danych lub zwolnienia
   zasobów systemowych.

**Dziedziczenie a Kompozycja**

Dziedziczenie (relacja "jest") to potężne narzędzie, ale bywa
nadużywane. Często lepszym podejściem jest **kompozycja** (relacja
"ma").

-  **Dziedziczenie (relacja "jest"):** Samochod **jest** Pojazdem.

-  **Kompozycja (relacja "ma"):** Samochod **ma** Silnik.

Zamiast tworzyć klasę SamochodKtoryMaRadio dziedziczącą z Samochod,
lepszym podejściem jest, aby klasa Samochod *zawierała w sobie* (jako
atrybut) obiekt klasy Radio.

Dlaczego kompozycja jest często preferowana? Jest bardziej elastyczna.
Możesz łatwo podmienić silnik w samochodzie (zmienić obiekt Silnik) w
trakcie działania programu, czego nie da się zrobić z dziedziczeniem
(samochód nie może przestać być pojazdem).

**Porównanie: Dziedziczenie vs Kompozycja**

Poniższa tabela podsumowuje kluczowe różnice między tymi dwoma
podejściami do ponownego wykorzystania kodu.

+------------+-------------------------+-------------------------------+
| **Cecha**  | **Dziedziczenie         | **Kompozycja (Relacja         |
|            | (Relacja "IS-A")**      | "HAS-A")**                    |
+============+=========================+===============================+
| **D        | Klasa pochodna          | Klasa "główna" zawiera        |
| efinicja** | dziedziczy po klasie    | instancję innej klasy jako    |
|            | bazowej.                | atrybut.                      |
+------------+-------------------------+-------------------------------+
| **         | Kwadrat dziedziczy po   | Samochod zawiera obiekt       |
| Przykład** | Prostokat.              | Silnik.                       |
+------------+-------------------------+-------------------------------+
| **         | Silne (ang. *tight      | Luźne (ang. *loose            |
| Wiązanie** | coupling*). Zmiany w    | coupling*). Zmiany w klasie   |
|            | klasie bazowej mocno    | "zawartej" (Silnik) mają      |
|            | wpływają na pochodne.   | mniejszy wpływ na             |
|            |                         | "zawierającą" (Samochód).     |
+------------+-------------------------+-------------------------------+
| **Elas     | Mniejsza. Relacja jest  | Większa. Obiekty "zawarte"    |
| tyczność** | ustalana na etapie      | można podmieniać w trakcie    |
|            | kompilacji.             | działania programu (np.       |
|            |                         | wymiana silnika).             |
+------------+-------------------------+-------------------------------+
| **Kiedy    | Gdy nowa klasa jest     | Gdy klasa *potrzebuje*        |
| używać?**  | faktycznie *specjalnym  | funkcjonalności innej klasy,  |
|            | typem* klasy bazowej i  | ale nie jest jej specjalnym   |
|            | chcemy korzystać z      | typem. "Preferuj kompozycję   |
|            | polimorfizmu.           | nad dziedziczeniem".          |
+------------+-------------------------+-------------------------------+

**Zasady SOLID**

Pisanie dobrego kodu obiektowego to sztuka. Zbiór pięciu fundamentalnych
zasad projektowania, znanych pod akronimem **SOLID**, pomaga tworzyć
oprogramowanie, które jest zrozumiałe, elastyczne i łatwe w utrzymaniu.

1. **S (Single Responsibility Principle):** Zasada jednej
   odpowiedzialności.

   -  *Mówi, że:* Każda klasa powinna mieć tylko jeden powód do zmiany
      (powinna być odpowiedzialna tylko za jeden aspekt
      funkcjonalności).

   -  *Przykład:* Klasa odpowiedzialna za logikę biznesową użytkownika
      nie powinna jednocześnie zajmować się zapisywaniem go do bazy
      danych. Zapis do bazy powinien być w osobnej klasie.

2. **O (Open/Closed Principle):** Zasada otwarte/zamknięte.

   -  *Mówi, że:* Klasy powinny być otwarte na rozszerzenia, ale
      zamknięte na modyfikacje.

   -  *Przykład:* Zamiast modyfikować klasę kalkulatora wysyłki za
      każdym razem, gdy dodajemy nową firmę kurierską, klasa ta powinna
      korzystać ze wspólnego interfejsu, a nowe firmy (DPD, InPost)
      powinny implementować ten interfejs.

3. **L (Liskov Substitution Principle):** Zasada podstawienia Liskov.

   -  *Mówi, że:* Obiekty klasy pochodnej muszą być w stanie zastąpić
      obiekty klasy bazowej bez powodowania błędów i zmiany oczekiwanego
      zachowania programu.

   -  *Przykład:* Jeśli funkcja działa poprawnie z obiektem klasy
      Ptaszek, musi działać tak samo poprawnie, gdy przekażemy jej
      obiekt Kaczka (która dziedziczy po Ptaszek).

4. **I (Interface Segregation Principle):** Zasada segregacji
   interfejsów.

   -  *Mówi, że:* Lepiej jest mieć wiele małych, specyficznych
      interfejsów niż jeden duży, ogólny. Klienci (klasy) nie powinni
      być zmuszani do implementowania metod, których nie używają.

   -  *Przykład:* Zamiast jednego interfejsu "Pracownik" z metodami
      "pracuj" i "zarządzaj zespołem", lepiej stworzyć dwa osobne
      interfejsy dla pracownika i dla menedżera.

5. **D (Dependency Inversion Principle):** Zasada odwrócenia zależności.

   -  *Mówi, że:* Moduły wysokiego poziomu (logika biznesowa) nie
      powinny zależeć od modułów niskiego poziomu (np. obsługa bazy
      danych). Oba powinny zależeć od abstrakcji (interfejsów).

   -  *Przykład:* Klasa generująca raporty nie powinna być na sztywno
      powiązana z bazą danych MySQL. Powinna polegać na abstrakcyjnym
      interfejsie "BazaDanych", co pozwoli w przyszłości łatwo podmienić
      MySQL na inną bazę.
