# Cantori

## Opis

Projekt Cantori to prosty system statystyk odwiedzin i monitorowania szybkości ładowania strony, napisany w PHP. System umożliwia zbieranie danych o odwiedzinach, średnim czasie ładowania strony oraz zarządzanie hasłem dostępu i wykluczaniem adresów IP.

## Instalacja

1. **Podłącz skrypt do swojej strony:**
   Umieść pierwszą linię kodu w głównym pliku strony, np. `index.php`:
   ```php
   include "php/Contatore_visitatori.php";
Mierzenie czasu ładowania strony:
Jeśli chcesz otrzymywać dane o szybkości ładowania strony, umieść funkcję na początku pliku, czyli:

   ```php
// Pełne statystyki info.php
include "cantori/ContatoreVisitatori.php";

// Zabezpiecz
if (function_exists('startTimer')) {
    startTimer();
}

Na końcu kodu strony dodaj:

if (function_exists('endTimer')) {
    $results = endTimer();
    echo 'Strona została załadowana w czasie: ' . $results['currentLoadTime'] . ' ms';
    echo " (średni czas ładowania: " . $results['averageLoadTime'] . " ms) ";
}

Foldery i pliki:
Po dodaniu include "php/Contatore_visitatori.php";, niezbędne foldery i pliki zostaną automatycznie utworzone. Dane, w tym szybkość odświeżania strony, będą dostępne w pliku info.php, np. strona.eu/info.php.

Obsługa błędów
Informacja o każdej akcji jest zapisywana w pliku errorFile.log. Używane są także bloki try-catch do przechwytywania szczególnych błędów. Informacje te są wyświetlane w logach w interfejsie oraz zapisywane w tym samym pliku.

Token CSRF
Więcej informacji o generowaniu tokena CSRF znajdziesz w pliku readme.txt.

Wersje
v1.1 - Aktualizacja - 29 czerwca 2024.

Bezpieczeństwo
Hasło dostępu: Domyślne hasło to '321'. Należy je zmienić. Hasło jest zapisane metodą 'hashing', co zapewnia ochronę przed przejęciem uprawnień. Używane polecenia to password_hash i password_verify.
Wykluczenie IP: Dodaj swoje IP oraz IP localhosta do wykluczeń, aby uniknąć błędnego nabijania licznika.

Backup danych
Gdy używasz polecenia reset, tworzona jest kopia danych w folderze cantori/backup/.

Autor
Autor: Freelancer, webdesigner, osoba prywatna, pasjonat i hobbysta - Marcin Dresnok (Darr) - marcin.dresnok@gmail.com
