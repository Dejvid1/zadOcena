rozdzial2
=========

Siła programowania obiektowego opiera się na czterech fundamentalnych
koncepcjach, często nazywanych filarami OOP. Zrozumienie ich jest
kluczone do efektywnego projektowania systemów obiektowych.

**1. Hermetyzacja (Enkapsulacja)**

**Hermetyzacja** (ang. *Encapsulation*) to idea łączenia danych
(atrybutów) i metod, które na nich operują, w jedną całość (czyli
klasę). Co ważniejsze, hermetyzacja oznacza **ukrywanie wewnętrznego
stanu obiektu** przed światem zewnętrznym.

Inne obiekty nie powinny mieć bezpośredniego dostępu do atrybutów
"właściciela". Zamiast tego, dostęp do danych odbywa się za
pośrednictwem publicznych metod (tzw. *getterów* i *setterów*).

-  **Po co?** Wyobraźmy sobie klasę KontoBankowe z atrybutem saldo.
   Gdyby każdy mógł bezpośrednio zmienić saldo na ujemną wartość,
   doprowadziłoby to do chaosu.

-  **Rozwiązanie:** Atrybut saldo jest *prywatny*. Oferujemy publiczną
   metodę "wypłać", która przyjmuje żądaną kwotę. Ta metoda, zanim
   zmieni saldo, sprawdzi, czy kwota jest dodatnia i czy na koncie są
   wystarczające środki.

Hermetyzacja chroni obiekt przed nieprawidłowym użyciem i pozwala
autorowi klasy zmienić jej wewnętrzną implementację (np. sposób
przechowywania salda) bez psucia kodu, który z tej klasy korzysta.

**2. Dziedziczenie**

**Dziedziczenie** (ang. *Inheritance*) to mechanizm, który pozwala
tworzyć nową klasę (nazywaną *klasą pochodną* lub *podklasą*) na
podstawie istniejącej klasy (*klasy bazowej* lub *nadklasy*).

Klasa pochodna "dziedziczy" wszystkie atrybuty i metody klasy bazowej,
może je rozszerzać o nowe lub modyfikować (nadpisywać) istniejące.

-  **Przykład:** Mamy klasę bazową Pojazd, która ma atrybut
   predkosc_maksymalna i metodę "jedź".

-  Możemy stworzyć klasy pochodne: Samochod i Motocykl.

-  Zarówno Samochod, jak i Motocykl automatycznie dziedziczą
   predkosc_maksymalna i metodę "jedź". Nie musimy pisać tego kodu od
   nowa.

-  Samochod może dodać nową metodę, np. "włącz wycieraczki", której
   Motocykl nie będzie miał.

Dziedziczenie modeluje relację "jest" (ang. *is-a*). Samochod **jest**
Pojazdem. Motocykl **jest** Pojazdem.

**3. Polimorfizm**

**Polimorfizm** (ang. *Polymorphism*) to greckie słowo oznaczające
"wielopostaciowość". W OOP oznacza to zdolność obiektów różnych klas do
odpowiadania na to samo wywołanie metody (ten sam komunikat) w sposób
specyficzny dla ich typu.

Najczęściej polimorfizm występuje w parze z dziedziczeniem.

-  **Przykład:** Kontynuując przykład z Pojazdem. Załóżmy, że zarówno
   Samochod, jak i Motocykl inaczej implementują metodę "jedź"
   odziedziczoną z Pojazd:

   -  Metoda "jedź" w Samochod wydrukuje: "Wrum, wrum, jadę czterema
      kołami."

   -  Metoda "jedź" w Motocykl wydrukuje: "Wrrrr, jadę na dwóch kołach!"

-  Teraz, jeśli mamy listę różnych pojazdów (niektóre to samochody, inne
   to motocykle), możemy przejść przez tę listę i na każdym obiekcie
   wywołać *tę samą* metodę "jedź".

-  System automatycznie rozpozna, czy dany obiekt to Samochod, czy
   Motocykl i uruchomi właściwą (specyficzną dla niego) wersję tej
   metody.

**4. Abstrakcja**

**Abstrakcja** (ang. *Abstraction*) to proces ukrywania złożonych
szczegółów implementacyjnych i pokazywania użytkownikowi tylko
niezbędnych funkcji. Jest to "wyższy poziom" hermetyzacji.

Celem abstrakcji jest uproszczenie interakcji z obiektem.

-  **Przykład:** Kiedy prowadzisz samochód, używasz pedału gazu. Jest to
   **abstrakcja**. Naciskasz pedał, a samochód przyspiesza.

-  Nie musisz wiedzieć (i nie chcesz wiedzieć) o tym, jak działa
   przepustnica, wtrysk paliwa, jaki jest skład mieszanki
   paliwowo-powietrznej i jak steruje tym komputer pokładowy. Te
   skomplikowane detale są **ukryte** (zaimplementowane wewnątrz).

-  Twój interfejs jest prosty: pedał gazu.

W programowaniu abstrakcję często realizuje się za pomocą **klas
abstrakcyjnych** lub **interfejsów**. Definiują one, *co* obiekt musi
potrafić zrobić (np. "każdy pojazd musi umieć jechać i hamować"), ale
nie mówią, *jak* ma to zrobić. Dopiero konkretne klasy (jak Samochod)
implementują te metody.
