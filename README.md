cantori/
│
├── cantori/
│   ├── backup/
│   ├── css/
│   ├── downloadFile/
│   ├── dorme/
│   ├── dodatki/
│   ├── last_year/
│   ├── loadFile/
│   ├── ContatoreVisitatori.php
│   ├── login.php
│   ├── password.php
│   ├── susip.txt
│   ├── visitors.txt
│   ├── visits2.php
│   └── visits.php
│
├── info.php
├── errorFile.log
└── README.md

# Cantori

## Opis

Projekt Cantori to prosty system statystyk odwiedzin i monitorowania szybkości ładowania strony, napisany w PHP. 
System umożliwia zbieranie danych o odwiedzinach, średnim czasie ładowania strony oraz zarządzanie hasłem dostępu i wykluczaniem adresów IP.

## Instalacja

Instalacja:
 * 1. Dodaj do głównego pliku strony:
 *    include "cantore/Contatore_visitatori.php";
 * 
 * 2. Aby mierzyć czas ładowania strony:
 *    Na początku kodu: startTimer();
 *    Na końcu kodu: endTimer();
 *
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
 *
 * Logi w 'error.log' w katalogu głównym.
 * Panel dostępny w 'info.php'.
 *
 * Hasło: '321' (zmiana w 'cantori/password.php').
 *
 * Wersja: v.1.1
 *
 * Aktualizacja: 29.06.2024 - 24.08.2024.ading README.md…]()

   Na końcu kodu: endTimer();

  @include "php/Contatore_visitatori.php";
  if (function_exists('startTimer')) {
      startTimer();
  }
  
  // Twój kod
  
  if (function_exists('endTimer')) {
      $results = endTimer();
      echo 'Czas ładowania: ' . $results['currentLoadTime'] . ' ms';
      echo ' (średni czas: ' . $results['averageLoadTime'] . ' ms)';
  }

 Logi w 'error.log' w katalogu głównym.
 Panel dostępny w 'info.php'.

 Hasło: '321' (zmiana w 'cantori/password.php').

 Wersja: v.1.11

 Aktualizacja: 29.06.2024 - 24.08.2024.
