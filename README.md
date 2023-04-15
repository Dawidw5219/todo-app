# Aplikacja do zarządzania zadaniami napisana w Phyton 3 przy uzyciu bibliotek SQLite oraz PyQt5

Użytkownik moze tworzyć zadania, przypisywać im kategorie, ustawiać daty wykonania oraz oznaczać zadania jako ukończone.

## Wymagania techniczne:

- aplikacja powinna być napisana w języku Python z wykorzystaniem biblioteki PyQt5 do tworzenia interfejsu graficznego,
- aplikacja powinna używać SQLite do przechowywania danych o zadaniach,
- aplikacja powinna składać się z trzech klas: Task, TaskManager oraz MainWindow.

## Opis klas:

- Task - klasa reprezentująca pojedyncze zadanie. Powinna zawierać pola takie jak: nazwa zadania, opis, kategoria, data utworzenia, data wykonania oraz informację o tym, czy zadanie zostało ukończone. Klasa powinna mieć możliwość zapisania zadania do bazy danych oraz odczytania z bazy danych,
- TaskManager - klasa odpowiedzialna za zarządzanie zadaniami. Powinna posiadać metody do dodawania nowych zadań, usuwania zadań, oznaczania zadań jako ukończone oraz pobierania listy zadań. Klasa powinna mieć możliwość zapisania stanu listy zadań do bazy danych oraz odczytania z bazy danych,
- MainWindow - klasa reprezentująca główne okno aplikacji. Powinna zawierać pola takie jak: pole tekstowe do wpisywania nazwy zadania, pole tekstowe do wpisywania opisu zadania, pole wyboru kategorii zadania, pole do wpisywania daty wykonania zadania oraz przyciski do dodawania nowego zadania, usuwania zaznaczonego zadania oraz oznaczania zaznaczonego zadania jako ukończone. Klasa powinna mieć możliwość wyświetlenia listy zadań oraz zmiany ich stanu.

## Bibliografia:

- Dokumentacja PyQt5: https://www.riverbankcomputing.com/static/Docs/PyQt5/
- Dokumentacja SQLite w Pythonie: https://docs.python.org/3/library/sqlite3.html

Klasa Task zawiera konstruktor, który inicjuje pola klasy oraz metodę save_to_database(), która zapisuje zadanie do bazy danych, oraz metodę get_all_from_database(), która zwraca listę wszystkich zadań z bazy danych.

Klasa TaskManager zawiera konstruktor, który inicjuje pustą listę zadań oraz metody add_task(), remove_task(), mark_task_as_completed() i get_all_tasks(), które odpowiednio dodają nowe zadanie do listy i zapisują je do bazy danych, usuwają zadanie z listy i bazy danych, oznaczają zadanie jako ukończone w liście i bazie danych oraz zwracają listę wszystkich zadań z bazy danych.

Klasa MainWindow tworzy interfejs użytkownika i implementuje logikę aplikacji. Użytkownik może dodawać nowe zadania, usuwać je, oznaczać jako ukończone oraz wyświetlać ich szczegóły. Aplikacja korzysta z klasy TaskManager do zarządzania zadaniami oraz klasy Task do reprezentowania pojedynczych zadań i zapisywania ich do bazy danych.
Plik należy umieścić w tym samym katalogu co plik z kodem aplikacji.

## Wymagania systemowe

- Zainstalowany w systemie Pythona w wersji 3
- Zainstalowany domyślny dla Python3 system zarządzania pakietami o nazwie pip3
- Zainstalowany w systemie SQLite
- Zainstalowane zaleznosci programu np. za pomocą ponizszych komend

```bash
pip3 install PyQt5
pip3 install pysqlite3
```

## Instrukcja instalacji i pierwszego uruchomienia programu

1. Upewnij się, spełniasz wszystkie opsiane powyzej wymagania sprzetowe.
2. Utwórz plik tasks.db z tabelą o następującej strukturze:

```sql
CREATE TABLE tasks (
    created_at TEXT PRIMARY KEY,
    name TEXT,
    description TEXT,
    category TEXT,
    due_date TEXT,
    completed INTEGER
);
```

3. Uruchom program z pliku main.py
4. Gotowe!

## Rozwiązywanie problemów

W przypadku wystąpienia następującego błędu w tracie instalacją pakietu pysqlite3:

```bash
ERROR: Failed building wheel for pysqlite3
Running setup.py clean for pysqlite3
Failed to build pysqlite3
ERROR: Could not build wheels for pysqlite3, which is required to install pyproject.toml-based projects
```

nalezy skorzystac z intrukcji opisanej na stronie https://www.pythonpool.com/error-legacy-install-failure/
