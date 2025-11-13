rozdzial4
=========

Zrozumienie teorii programowania obiektowego to pierwszy krok. Drugim,
znacznie ważniejszym, jest przełożenie tej teorii na praktykę i
utrwalenie jej poprzez budowanie konkretnych aplikacji. Wiedza, która
nie jest aktywnie wykorzystywana, szybko zanika. Poniżej znajduje się
lista zasobów – klasycznych książek, materiałów dodatkowych oraz
przykładowych projektów – które pomogą Ci nie tylko pogłębić wiedzę, ale
przede wszystkim stać się lepszym programistą obiektowym.

**Przykładowe Projekty do Nauki OOP**

Najlepszym sposobem na naukę jest samodzielne zmaganie się z problemami
projektowymi. Oto kilka pomysłów na projekty o rosnącym stopniu
skomplikowania, które idealnie nadają się do przećwiczenia zasad OOP:

**1. Projekt: Prosty System Biblioteczny (konsolowy)**

-  **Cel:** Przećwiczenie podstaw: tworzenia klas, atrybutów, metod i
   relacji między obiektami.

-  **Kluczowe obiekty (Klasy):**

   -  Ksiazka: Powinna mieć atrybuty takie jak tytul, autor, ISBN.

   -  Czytelnik: Powinien mieć atrybuty imie, nazwisko, id_czytelnika
      oraz listę aktualnie wypożyczonych książek.

   -  Biblioteka: Główna klasa zarządzająca. Powinna zawierać listy
      wszystkich książek i wszystkich czytelników. Metody tej klasy to
      np. dodajKsiazke, dodajCzytelnika, wypozyczKsiazke (która sprawdza
      dostępność i dodaje książkę do listy czytelnika) oraz
      zwrocKsiazke.

-  **Co ćwiczysz?** **Hermetyzację** (np. Biblioteka zarządza stanem
   książek, a nie sam czytelnik) oraz proste relacje (Biblioteka "ma"
   Książki i Czytelników).

**2. Projekt: Gra Tekstowa (Text-based RPG)**

-  **Cel:** Zastosowanie dziedziczenia i polimorfizmu.

-  **Kluczowe obiekty (Klasy):**

   -  Postac (Klasa bazowa/abstrakcyjna): Powinna definiować wspólne
      cechy, jak punktyZycia, silaAtaku oraz metody atakuj i
      otrzymajObrazenia.

   -  Bohater (dziedziczy po Postac): Dodaje specyficzne cechy, jak
      ekwipunek (który sam może być listą obiektów klasy Przedmiot) oraz
      metodę uzyjPrzedmiotu.

   -  Przeciwnik (dziedziczy po Postac): Może mieć dodatkowy atrybut typ
      (np. Goblin, Smok).

   -  Bron (dziedziczy po Przedmiot): Może nadpisywać metodę uzyj z
      klasy Przedmiot, aby zwiększać siłę ataku bohatera.

   -  Mikstura (dziedziczy po Przedmiot): Nadpisuje metodę uzyj, aby
      leczyć bohatera.

-  **Co ćwiczysz?** **Dziedziczenie** (Bohater "jest" Postacią, Smok
   "jest" Postacią) oraz **Polimorfizm** (wywołanie metody atakuj na
   obiekcie Bohater i na obiekcie Smok działa inaczej; wywołanie uzyj na
   Mikstura i na Bron daje zupełnie różne efekty).

**3. Projekt: Symulator Bankomatu**

-  **Cel:** Zrozumienie hermetyzacji, kompozycji i obsługi wyjątków w
   kontekście OOP.

-  **Kluczowe obiekty (Klasy):**

   -  KontoBankowe: Przechowuje saldo. Powinno mieć *prywatny* atrybut
      saldo i publiczne metody wplac, wyplac oraz sprawdzSaldo. Metoda
      wyplac musi zawierać logikę sprawdzającą, czy na koncie są
      wystarczające środki.

   -  Uzytkownik: Posiada imie, nazwisko oraz (poprzez **kompozycję**)
      obiekt KontoBankowe.

   -  Bank: Zarządza listą użytkowników i ich kont.

   -  Bankomat: Główna klasa aplikacji, która dostarcza interfejsu (np.
      konsolowego). Używa obiektu Bank do weryfikacji użytkownika (np.
      po numerze PIN) i wykonywania operacji na jego koncie.

-  **Co ćwiczysz?** **Hermetyzację** (nikt poza KontoBankowe nie może
   bezpośrednio zmienić saldo), **Kompozycję** (Użytkownik "ma"
   KontoBankowe) oraz zasady SOLID (np. zasada jednej odpowiedzialności
   – Bankomat odpowiada za interfejs, a KontoBankowe za logikę salda).

**Klasyczne Książki o OOP i Projektowaniu**

Gdy już zaczniesz pisać własne projekty, szybko natkniesz się na
powtarzalne problemy. W tym momencie warto sięgnąć po literaturę, która
opisuje sprawdzone rozwiązania. Istnieje kilka książek, które są
uznawane za kanon w świecie inżynierii oprogramowania.

-  **"Wzorce Projektowe. Elementy oprogramowania obiektowego
   wielokrotnego użytku"** (autorzy: Erich Gamma, Richard Helm, Ralph
   Johnson, John Vlissides - tzw. "Banda Czterech" lub "GoF").

   -  To absolutna biblia wzorców projektowych. Opisuje 23 fundamentalne
      wzorce, które rozwiązują typowe problemy w projektowaniu
      oprogramowania (np. wzorzec Fabryka, Obserwator, Dekorator). Jest
      to lektura gęsta i akademicka, ale niezwykle wartościowa dla
      zaawansowanych programistów.

-  **"Czysty kod. Podręcznik dobrego programisty"** (autor: Robert C.
   Martin - "Wujek Bob").

   -  Choć nie jest to książka *tylko* o OOP, to zasady w niej zawarte
      (jak zasada SOLID, czytelne nazewnictwo, dobre funkcje) są
      fundamentem dojrzałego programowania obiektowego. Uczy, jak pisać
      kod, który jest czytelny dla innych ludzi i łatwy w utrzymaniu.
      Jest to pozycja obowiązkowa.

   -  .. image:: media/media/image1.png
         :width: 4.97917in
         :height: 3.05208in

-  **"Rusz głową! Wzorce projektowe"** (autorzy: Eric Freeman, Elisabeth
   Robson).

   -  Jeśli książka "Bandy Czterech" wydaje się zbyt sucha i
      odstraszająca, ta pozycja jest idealnym startem. Tłumaczy te same
      wzorce projektowe w znacznie bardziej przystępny, wizualny i
      humorystyczny sposób, używając wielu analogii i przykładów z
      życia.

-  **"Refaktoryzacja. Ulepszanie struktury istniejącego kodu"** (autor:
   Martin Fowler).

   -  OOP nie polega tylko na pisaniu kodu od zera, ale także na
      ulepszaniu istniejącego. Często dołączamy do projektu, gdzie kod
      jest źle zorganizowany. Ta książka to katalog "ruchów
      refaktoryzacyjnych" – małych, bezpiecznych kroków, które pozwalają
      przekształcić zły kod w dobry, często wykorzystując do tego zasady
      OOP i wzorce projektowe.

**Inne Zasoby i Dalsza Ścieżka**

Poza książkami i własnymi projektami, istnieje wiele innych miejsc, z
których można czerpać wiedzę i inspirację:

-  **Platformy e-learningowe:** Strony takie jak Udemy, Coursera,
   Pluralsight czy polskie (np. Strefa Kursów) oferują dziesiątki kursów
   wideo na temat OOP, wzorców projektowych i zasad SOLID w kontekście
   konkretnych języków (Java, C#, Python, JavaScript). Często prowadzą
   one krok po kroku przez budowę projektu podobnego do tych
   wymienionych powyżej.

-  **Oficjalna Dokumentacja:** Jeśli uczysz się OOP w konkretnym języku
   (np. Pythonie), czytanie oficjalnej dokumentacji na temat klas,
   dziedziczenia i wbudowanych modułów jest nieocenione. To podstawowe
   źródło prawdy.

-  **Społeczności i Blogi:** Strony takie jak Stack Overflow (do
   rozwiązywania konkretnych problemów) oraz blogi prowadzone przez
   doświadczonych programistów (np. blog Martina Fowlera lub polskie
   blogi branżowe) to kopalnia wiedzy o rzeczywistych zastosowaniach i
   problemach związanych z OOP.

-  **Repozytoria Open Source (GitHub):** Analizowanie kodu dobrze
   napisanych projektów open source to jedna z najlepszych metod nauki.
   Możesz zobaczyć, jak doświadczeni programiści stosują zasady OOP,
   wzorce projektowe i zasady SOLID w praktyce do rozwiązywania
   realnych, skomplikowanych problemów. To jak czytanie książek
   napisanych przez mistrzów, ale w formie kodu.
