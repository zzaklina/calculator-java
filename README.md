# Izveštaj - Metrika i statička analiza

## LOC (Lines of Code)
Ukupan broj linija koda u projektu Start.java: 21 linija
Ukupan broj linija koda u projektu Calculator.java: 168 linija

---

## Neformalni pregled i statička analiza

fajl – broj linije koda – zapažanje
## Start.java
Start.java – 8 – Scanner se kreira unutar while petlje (loše upravljanje resursima)
Start.java – 12 – Scanner se ne koristi optimalno (ponovno instanciranje u svakoj iteraciji)
Start.java – 14 – equals("exit") je case-sensitive bez dodatne validacije
Start.java – 15 – scanner.close() se poziva unutar petlje (loš kontrolni tok)
Start.java – 9 – varijabla Expression nije po Java naming konvenciji (trebalo expression)
## Calculator.java
Calculator.java – 1 – nepotrebni importi (List, ArrayList nisu optimizovani)
Calculator.java – 6 – globalna varijabla finalResult (loš dizajn, side effects)
Calculator.java – 10 – nested class Operations ima utility ulogu, ali nije idealno strukturisana
Calculator.java – 17 – metoda ToString() krši Java naming konvenciju (trebalo toString)
Calculator.java – 23 – metoda Run() je nepotreban wrapper
Calculator.java – 27 – evaluateExpression() ima previše odgovornosti (parsing + evaluacija)
Calculator.java – 31 – implicitno dodavanje “0” može dovesti do neočekivanih rezultata
Calculator.java – 35 – split regex zavisi od ručno konstruisanog stringa operatora
Calculator.java – 38 – ručno parsiranje operatora umesto tokenizer-a
Calculator.java – 42 – lista operationList se puni linearno bez optimizacije
Calculator.java – 49 – Float.parseFloat bez prethodne validacije ulaza
Calculator.java – 52 – korišćenje String "ERROR" umesto exception handling-a
Calculator.java – 55 – metoda Calculate() je rekurzivna (rizik stack overflow-a)
Calculator.java – 57 – korišćenje globalne promenljive finalResult
Calculator.java – 62 – duplicirana logika za množenje i deljenje
Calculator.java – 82 – duplicirana logika za sabiranje i oduzimanje
Calculator.java – 110 – nema zaštite od deljenja nulom (division by zero)
Calculator.java – 140 – mešanje više odgovornosti u jednoj klasi (SRP violation)
Calculator.java – 150 – mutiranje lista tokom rekurzije (rizično ponašanje)

---

## Zaključak
Kod je funkcionalan, ali postoji prostor za poboljšanje:
-loša arhitektura (spojeno parsiranje + računanje)
-globalno stanje 
-neoptimalno upravljanje Scanner resursima
