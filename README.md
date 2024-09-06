# Cantori

## Opis

Projekt Cantori to prosty system statystyk odwiedzin i monitorowania szybkości ładowania strony, napisany w PHP. System umożliwia zbieranie danych o odwiedzinach, średnim czasie ładowania strony oraz zarządzanie hasłem dostępu i wykluczaniem adresów IP.

## Instalacja

Instalacja:

1. Dodaj do głównego pliku strony: `include "cantore/Contatore_visitatori.php";`
2. Aby mierzyć czas ładowania strony:

  - Na początku kodu: `startTimer();`
  - Na końcu kodu: `endTimer();`


```
@include "cantore/Contatore_visitatori.php";
if (function_exists('startTimer')) {
    startTimer();
}

// Twój kod

if (function_exists('endTimer')) {
    $results = endTimer();
    echo 'Czas ładowania: ' . $results['currentLoadTime'] . ' ms';
    echo ' (średni czas: ' . $results['averageLoadTime'] . ' ms)';
}
```

Logi w 'error.log' w katalogu głównym.<BR>
Panel dostępny w 'info.php'.<BR>
Hasło: '321' (zmiana w 'cantori/password.php').
