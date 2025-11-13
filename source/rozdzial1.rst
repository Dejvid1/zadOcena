rozdzial1
=========

**Czym jest Programowanie Obiektowe (OOP)?**

Programowanie obiektowe (z ang. **Object-Oriented Programming**, w
skrócie **OOP**) to paradygmat programowania, który zrewolucjonizował
sposób tworzenia oprogramowania. Zamiast myśleć o programie jako o
sekwencji instrukcji i funkcji operujących na danych (jak w
programowaniu proceduralnym), OOP proponuje modelowanie rzeczywistości
za pomocą **obiektów**.

Wyobraźmy sobie programowanie proceduralne jako listę zadań dla
kucharza: "Weź mąkę", "Dodaj wodę", "Wymieszaj", "Wstaw do pieca". Jeśli
coś pójdzie nie tak (np. zabraknie mąki), cały proces może się załamać,
a zmiana jednego kroku może wymagać modyfikacji wielu innych.

Programowanie obiektowe jest jak zorganizowana kuchnia. Zamiast jednej
listy zadań, mamy obiekty: "Kucharz", "Piekarnik", "Miska". Każdy obiekt
ma swoje własne dane (**atrybuty**, np. zawartość miski) oraz własne
funkcje (**metody**, np. zdolność kucharza do mieszania lub zdolność
piekarnika do pieczenia). Kucharz nie musi wiedzieć, *jak* działa
piekarnik; musi tylko wiedzieć, jak go użyć (wywołać jego funkcję
pieczenia).

**Główne Założenia i Korzyści**

Paradygmat obiektowy opiera się na idei łączenia danych oraz funkcji,
które na nich operują, w spójne jednostki zwane obiektami. Prowadzi to
do wielu korzyści, szczególnie w dużych i złożonych projektach:

-  **Modułowość:** Każdy obiekt jest niezależną jednostką. Możesz
   rozwijać i testować klasę Samochod bez martwienia się o to, jak
   działa klasa Uzytkownik.

-  **Wielokrotne użycie kodu (Reusability):** Raz zdefiniowana klasa
   (np. Przycisk) może być używana wielokrotnie w różnych częściach
   aplikacji. Co więcej, dzięki dziedziczeniu, można tworzyć nowe klasy
   na bazie istniejących.

-  **Łatwiejsze utrzymanie i skalowalność:** Gdy chcesz coś zmienić (np.
   sposób obliczania podatku), modyfikujesz tylko jedną klasę
   (KalkulatorPodatku), a nie przeszukujesz całego kodu w poszukiwaniu
   odpowiednich funkcji.

-  **Lepsze odwzorowanie rzeczywistości:** Struktura kodu oparta na
   obiektach (Klient, Produkt, Zamówienie) jest często bardziej
   intuicyjna i łatwiejsza do zrozumienia dla programistów, ponieważ
   przypomina obiekty ze świata rzeczywistego.

-  **Elastyczność:** Dzięki polimorfizmowi (omówionemu później), systemy
   obiektowe mogą łatwo adaptować się do nowych typów danych bez
   konieczności fundamentalnych zmian w logice.

**Klasa vs. Obiekt: Plan i Budynek**

Dwa najbardziej fundamentalne pojęcia w OOP to **klasa** i **obiekt**.

1. **Klasa (Class):** To jest plan, szablon, przepis lub projekt. Klasa
   Samochod definiuje, że samochód *będzie miał* kolor, markę i prędkość
   maksymalną oraz że *będzie potrafił* wykonywać akcje takie jak "jedź"
   i "hamuj". Sama klasa nie jest samochodem – to tylko opis.

2. **Obiekt (Object):** To jest konkretna, fizyczna **instancja** klasy.
   To prawdziwy byt stworzony na podstawie planu. Na podstawie klasy
   Samochod możemy stworzyć wiele obiektów:

   -  mojeAuto (czerwone Ferrari, prędkość 300 km/h)

   -  autoSasiada (niebieski Fiat, prędkość 180 km/h)

Oba obiekty mają te same atrybuty (kolor, marka) i metody (jedź, hamuj),
ale wartości ich atrybutów są niezależne i przechowywane oddzielnie.

Kiedy tworzymy obiekt (proces zwany **instancjacją**), zazwyczaj używamy
specjalnej metody zwanej **konstruktorem**. Konstruktor pozwala nam
ustawić początkowe wartości atrybutów dla nowo tworzonego obiektu (np.
podać markę i liczbę przerzutek podczas tworzenia nowego roweru).
