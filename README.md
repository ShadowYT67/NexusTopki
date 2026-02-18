# NexusTopki — Rankingi + GUI + PvP Points (Paper 1.21.8-1.21.11)

Nowoczesny plugin na serwery **Paper** dodający rozbudowane rankingi graczy (topki), wygodne GUI oraz system punktów PvP z limiterem farmienia. Projektowany z myślą o serwerach survival/PvP, gdzie liczy się czytelna rywalizacja i szybki podgląd statystyk.

---

## Najważniejsze funkcje

### Rankingi (Topki)
Plugin prowadzi rankingi graczy w kilku kategoriach, m.in.:
- **Punkty (POINTS)** — główny ranking rywalizacji (np. PvP).
- **Zabójstwa (KILLS)** i **Śmierci (DEATHS)**.
- **Czas gry (TIME)** — zliczany w sekundach, z doliczaniem aktualnej sesji online.
- **Ekonomia (MONEY)** — integracja z Vault (saldo gracza).
- **Bloki postawione (PLACED)** i **Wykopane (BROKEN)**.

> Kategorie i kolory TOP są konfigurowalne w plikach ustawień.

---

## GUI (Menu rankingów)

Plugin posiada wygodne GUI:
- Menu główne z przyciskami do poszczególnych rankingów.
- Lista TOP z paginacją (następna/poprzednia strona, powrót).
- Wyświetlanie pozycji gracza oraz wartości wyniku w czytelnej formie.
- Automatyczny refresh otwartych GUI (opcjonalny).

### Ranking klanów (TOP 60)
W GUI (pod `/topki` lub `/ranking`) dostępna jest również zakładka **Ranking Klanów** prezentująca **TOP 60 klanów** (z paginacją).

- Zakładka rankingu klanów jest obecna w GUI **zawsze** – niezależnie od tego, czy na serwerze działa plugin klanowy.
- Jeżeli na serwerze **nie** ma pluginu **NexusKlan** (lub nie ma danych o klanach), ranking pozostanie **pusty**.
- Jeżeli serwer posiada **NexusKlan**, punkty klanu są liczone jako **suma punktów (POINTS) wszystkich graczy należących do klanu**. W GUI widać łączny wynik klanu oraz jego pozycję w rankingu.

#### Planowane (v1.1)
W wersji **v1.1** zostanie dodana możliwość włączenia/wyłączenia rankingu klanów w konfiguracji NexusTopki:
- `rankingKlan: false` — zakładka rankingu klanów nie będzie widoczna w GUI.
- `rankingKlan: true` — zakładka rankingu klanów będzie widoczna w GUI.

---

## PvP Points + Limiter (anty-farma)

System PvP:
- Losowanie punktów w zakresie **min/max** za zabójstwo (dla killera) oraz utratę punktów (dla ofiary).
- Limiter farmienia tej samej osoby:
    - blokada przy przekroczeniu limitu w oknie czasowym,
    - informacja dla killera w bossbarze z czasem do następnej możliwości,
    - informacja dla ofiary, że punkty nie zostały odjęte.

---

## Integracje

### Vault (wymagane dla MONEY)
- Plugin obsługuje ranking **MONEY** przez Vault/Economy (saldo gracza).

### PlaceholderAPI (opcjonalnie)
- Jeżeli PlaceholderAPI jest zainstalowane, plugin może rejestrować własne placeholdery (zależnie od konfiguracji serwera).
- Dodatkowo w GUI możliwe jest użycie placeholderów klanowych (np. tag i punkty klanu) w lore “Twoje Statystyki”.

### NexusKlan (opcjonalnie)
- Jeśli serwer posiada plugin **NexusKlan**, NexusTopki automatycznie wypełnia **ranking klanów** danymi.
- Punkty klanu są obliczane jako **suma punktów graczy w klanie** (na podstawie rankingu POINTS).

---

## Baza danych (MySQL)

Plugin zapisuje statystyki do bazy danych **MySQL** (konfiguracja w `database.yml`).

### Wbudowany sterownik MySQL
W paczce znajduje się **wbudowany sterownik MySQL**, dzięki czemu nie musisz instalować żadnych dodatkowych bibliotek na serwerze ani dogrywać sterowników ręcznie.  
Wystarczy poprawnie uzupełnić dane połączenia w `database.yml`, a plugin połączy się z MySQL bez dodatkowych zależności.

> Uwaga: serwer musi mieć możliwość połączenia z Twoją bazą MySQL (poprawny host, port, login/hasło oraz dostęp sieciowy).

---

## Baza danych i zapisy (Autosave)

- Statystyki są zapisywane do bazy danych (konfiguracja w `database.yml`).
- Wbudowany autosave:
    - możliwość włączenia/wyłączenia,
    - ustawiany interwał,
    - opcjonalny bossbar informacyjny dla graczy z permisją.

---

## Konfiguracja

Plugin korzysta z:
- `settings.yml` — ustawienia mechanik, TTL cache, GUI, PvP, taski
- `messages.yml` — wszystkie wiadomości i formaty (bossbary, linie TOP, teksty GUI)
- `database.yml` — konfiguracja bazy danych

Konfiguracje są przygotowane tak, aby dało się je przeładować bez restartu serwera (komenda reload).

---

## Komendy

### Gracze
- `/topki` — otwiera menu GUI  
  lub
- `/ranking` — otwiera menu GUI

### Administracja
- `/atopki rl` — przeładowanie konfiguracji i ustawień runtime
- `/atopki rldb` — przeładowanie połączenia/ustawień bazy danych
- `/atopki add <typ> <wartość> <gracz>` — dodaje wartość do danej kategorii
- `/atopki remove <typ> <wartość> <gracz>` — odejmuje wartość z danej kategorii

Przykłady:
- `/atopki add points 25 Nick`
- `/atopki remove deaths 1 Nick`

---

## Uprawnienia

- `NexusTopki.admin` — dostęp do komend administracyjnych (`/atopki ...`)
- `NexusTopki.info` — otrzymywanie bossbara o autosave (jeśli włączone)

---

## Wymagania

- **Paper 1.21.8+**
- **Java 21+**
- **Vault 1.7.1 – 1.7.3**
- **PlaceholderAPI** (opcjonalnie, jeśli używasz placeholderów)
- Plugin ekonomii zgodny z Vault (np. EssentialsX / CMI)

---

## Wsparcie / Kontakt

- Discord: **https://discord.gg/XbfP2gXVD7**
- Sklep / zakup: **https://discord.gg/XbfP2gXVD7**
- Autor: **ShadowYT**

---

## Cena

**Cena: PLN**

Licencja przypisana do jednego właściciela:
- **1 serwer** lub **1 sieć serwerów** (Network)

---

## Wsparcie

- Godziny wsparcia: **12:00–20:00** (CET).
- Standardowy czas odpowiedzi: do **48 godzin** (w zależności od kolejki i złożoności zgłoszenia).
- Szczegóły i zasady obsługi zgłoszeń znajdziesz w regulaminie systemu biletów na Discordzie.

---

## Warunki zakupu i licencja

- Po zakupie otrzymujesz **stały dostęp** do produktu (zgodnie z warunkami licencji).
- Rozwój produktu jest oparty o sugestie społeczności — propozycje można zgłaszać na kanale „propozycje” na naszym Discordzie.
- Licencja: **1 serwer** lub **1 sieć serwerów** (do użytku przez jednego właściciela/organizację).

### Zwroty
- Produkt jest dostarczany w formie cyfrowej, dlatego co do zasady **nie podlega zwrotowi** po udostępnieniu plików/dostępu.
