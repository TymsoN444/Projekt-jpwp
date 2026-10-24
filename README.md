# 🧩 Ukryty Wzór – Serious Game (WCST)

**Projekt z przedmiotu:** Języki Programowania Wysokiego Poziomu (JPWP)  
**Politechnika Gdańska** | Wydział Elektrotechniki , Telekomunikacji  i Informatyki
**Autor:** Tymoteusz Kłodawski (EiT, nr albumu: 202395)  
**Technologia:** C# (.NET 8 / Windows Forms)  

---

## 📌 O projekcie
**Ukryty Wzór** to komputerowa adaptacja klasycznego testu neuropsychologicznego *Wisconsin Card Sorting Test (WCST)* zrealizowana w konwencji *Serious Game*. Main targetem aplikacji jest trening elastyczności poznawczej, przełączania uwagi oraz samokontroli poprzez oduczanie sztywnych schematów myślenia i unikanie tzw. błędów perseweracyjnych.

Aplikacja jest przystosowana dla zróżnicowanych grup odbiorców (osoby po urazach i udarach, dzieci i młodzież z ADHD, seniorzy oraz entuzjaści *Brain Fitness*).

---

## 🎮 Mechanika i Opis Rozgrywki
1. **Dopasowywanie kart:** Gracz dopasowuje wylosowaną kartę do jednej z 4 kart wzorcowych na podstawie określonej cechy (np. kolor, kształt, liczba figur).
2. **Ukryta reguła:** Obowiązujące kryterium nie jest podane wprost – gracz odkrywa je metodą prób i błędów dzięki natychmiastowym komunikatom zwrotnym (`DOBRZE` / `BŁĄD`).
3. **Dynamiczna zmiana zasad:** Po serii poprawnych wyborów system po cichu zmienia regułę sortowania, zmuszając gracza do szybkiej adaptacji i porzucenia dotychczasowej strategii.

### 🌟 Moduły i rozbudowa gry:
* **Stopniowanie trudności:** 
  * *Łatwy:* 2 cechy kart, krótsza seria do zaliczenia.
  * *Średni:* Klasyczny WCST (3 cechy, seria 6 poprawnych prób).
  * *Trudny:* Ograniczenie czasowe na ruch / dodatkowe cechy kart.
* **Tematyczne zestawy kart:** Klasyczne figury geometryczne, ikony zwierząt/owoców, symbole pojazdów.
* **Deklaracja hipotezy:** Faza, w której gracz po udanej serii może jawnie zadeklarować odkrytą regułę, otrzymując bonus punktowy.
* **Profilowanie i statystyki:** Rejestracja profilu gracza, dokładny pomiar czasów reakcji, analiza liczby błędów perseweracyjnych oraz eksport wyników do pliku `CSV`.

---

## 🛠️ Dostępność i UX
* **Dostępność dla osób z zaburzeniami rozpoznawania barw (Daltonizm):** Informacja zwrotna nie opiera się wyłącznie na kolorze (użycie jednoznacznych ikon `✓` / `✗` oraz czytelnych komunikatów tekstowych).
* **Intuicyjne GUI:** Przejrzysty podział na Menu Główne, Ekran Gry oraz Historię Wyników.

---

## 📐 Architektura Projektu na dzień 24.10
Aplikacja została zaprojektowana w oparciu o architekturę obiektową z podziałem na modularne klasy:
* `Card` – reprezentacja karty i jej cech (kolor, kształt, liczba, zasób graficzny).
* `Rule` – logika reguł sortowania oraz weryfikacja poprawności ruchów.
* `GameEngine` – sterowanie pętlą gry, punktacją i zmianą reguł.
* `UserProfile` – zarządzanie tożsamością i sesją gracza.
* `GameSessionResult` – struktura danych przechowująca statystyki sesji.
* `StorageManager` – obsługa trwałego zapisu i odczytu profili oraz historii z plików (`.txt` / `.csv`).
* `FormMain` / `GameForm` – warstwa interfejsu użytkownika (Windows Forms).
