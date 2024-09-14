# Cantori

## Opis

Projekt Cantori to prosty system statystyk odwiedzin i monitorowania szybkości ładowania strony, napisany w PHP. System umożliwia zbieranie danych o odwiedzinach, średnim czasie ładowania strony oraz zarządzanie hasłem dostępu i wykluczaniem adresów IP.

## Instalacja

Instalacja:

1. Dodaj do głównego pliku strony: `include "cantori/loadFile/ContatoreVisitatori.php";`
2. Aby mierzyć czas ładowania strony:

  - Na początku kodu: `startTimer();`
  - Na końcu kodu: `endTimer();`


```
<?php
@include "cantori/loadFile/ContatoreVisitatori.php";
if (function_exists('startTimer')) {
    startTimer();
}

?>
<!-- Twój kod -->

<?php
//na zakończenie strony
if (function_exists('endTimer')) {
    $results = endTimer();
    echo 'Czas ładowania: ' . $results['currentLoadTime'] . ' ms';
    echo ' (średni czas: ' . $results['averageLoadTime'] . ' ms)';
}

?>

<?php
// Wyświetl statystyki na dzień, na miesiąc..
echo '<p class="copy">';

echo "Wizyty: ogółem, dzień, tydzień, miesiąc - " . $_SESSION['unique_visits_day'] . " / ";
echo $_SESSION['unique_visits_week'] . " / ";
echo $_SESSION['unique_visits_month'] . " / "; 
echo VISITORS_UNIK_IP;

echo "</p>";
 
  ?>
  
```

Logi w 'error.log' w katalogu głównym.
Panel dostępny w 'info.php'.
Hasło: '321' (zmiana w 'cantori/loadFile/password.php').
