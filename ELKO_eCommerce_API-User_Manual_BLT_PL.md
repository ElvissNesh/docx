# ELKO eCommerce API – Instrukcja użytkownika (tłumaczenie na język polski)

> Uwaga: źródłowy plik PDF ma układ graficzny (broszura/infografika), a nie klasyczny dokument tekstowy. Poniżej znajduje się wierne **tłumaczenie treści merytorycznej** do formatu edytowalnego.

## Spis treści

1. Czym jest ELKO eCommerce API?
2. Jakie procesy można zautomatyzować?
3. Jak działa API?
4. Typy API ELKO eCommerce
5. Jak znaleźć właściwą metodę API?
6. Integracja API
   - Konfiguracja
   - Ograniczenia IP
   - Token
   - Dokumentacja API
7. Wsparcie techniczne
8. Kody odpowiedzi

---

## 1) Czym jest ELKO eCommerce API?

ELKO eCommerce API (Application Programming Interface) to narzędzie, które umożliwia automatyczną wymianę danych pomiędzy Twoim sklepem internetowym lub systemem magazynowym a systemem eCom ELKO.

Dzięki temu możliwe jest odzwierciedlanie stanów magazynowych ELKO w czasie rzeczywistym w Twoim sklepie internetowym, a także uproszczenie i przyspieszenie procesów zamawiania towarów.

ELKO eCommerce API udostępnia szeroki zakres funkcji, które pozwalają wysyłać i odbierać dane do/z eCom ELKO.

Pełna lista funkcji API:

- https://api.elko.cloud

---

## 2) Jakie procesy można zautomatyzować?

- Pobieranie informacji o produktach (opisy, zdjęcia, dostępność, ceny) — gotowe treści do wykorzystania w sklepach internetowych.
- Tworzenie rezerwacji — gwarancja dostępności towaru, np. przy łączeniu zamówień klientów zebranych w ciągu dnia.
- Składanie i modyfikowanie zamówień:
  - dodawanie pozycji,
  - zmiana ilości,
  - usuwanie pozycji.
- Pobieranie statusów i szczegółów zamówień.

---

## 3) Jak działa API?

W dokumentacji metod API zwykle widoczne są:

- **Example Value** — przykładowa wartość / przykładowy kod (np. plain, JSON, XML).
- **Model/Scheme** — model danych zawierający typy oraz opisy parametrów.
- **Code examples** — przykłady kodu dla technologii takich jak Java, .NET, PHP.

---

## 4) Typy API ELKO eCommerce

W praktyce wykorzystywane są m.in. metody:

- `GET` — pobieranie danych,
- `PUT` / `POST` — dodawanie lub modyfikacja,
- `DELETE` — usuwanie danych.

---

## 5) Jak znaleźć właściwą metodę API?

1. Wejdź do dokumentacji API.
2. Wybierz odpowiednią kategorię (np. katalog, zamówienia, dostępność i ceny).
3. Sprawdź wymagane parametry wejściowe i format odpowiedzi.
4. Przetestuj wywołanie w sekcji dokumentacji (autoryzacja tokenem Bearer).

---

## 6) Integracja API

### 6.1 Konfiguracja

- Upewnij się, że masz aktywny dostęp API.
- Skonfiguruj adresy IP (jeśli stosowane jest ograniczenie po adresach).
- Wygeneruj lub pobierz token autoryzacyjny.

### 6.2 Ograniczenia IP

Dostęp może być ograniczony do wskazanych adresów IP po stronie klienta.

### 6.3 Token (autoryzacja)

W dokumentacji/testerze API (np. Swagger):

1. Kliknij **Authorize**.
2. W polu **Value** wpisz:

```text
Bearer {Token}
```

3. Zatwierdź przyciskiem **Authorize**, a następnie **Close**.

### 6.4 Dokumentacja API

Dokumentacja metod, modeli i przykładów znajduje się pod adresem:

- https://api.elko.cloud

---

## 7) Wsparcie techniczne

W razie problemów z integracją lub działaniem metod API skontaktuj się z opiekunem ELKO / zespołem wsparcia technicznego.

---

## 8) Kody odpowiedzi

Przykładowe statusy odpowiedzi:

- `200` — sukces,
- `400` — błędne zapytanie (Bad request),
- `401` / `403` — brak autoryzacji lub brak uprawnień,
- `500` — błąd po stronie serwera.

---

## Dodatkowe uwagi implementacyjne

- Dla bezpieczeństwa liczba zapytań jest limitowana.
- Zgodnie z treścią materiału: system pozwala na około **50 zapytań API na 10 sekund**.
- Po przekroczeniu limitu nowe zapytania mogą zostać zablokowane czasowo (np. na 1 minutę).
- Dla najlepszej jakości danych produktowych zaleca się:
  - cykliczne wywołanie `GET:Catalog/Products` (np. raz dziennie),
  - wywołanie `GET:Catalog/AvailabilityAndPrice` podczas składania zamówienia.

