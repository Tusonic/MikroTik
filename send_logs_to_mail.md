# Wysyłanie logów na poczte
## Send logs to mail

```
/log print file=logs
:delay 10s
:local logContent ""
:foreach logLine in=[/file find name="logs.txt"] do={
    :set logContent ($logContent . [/file get $logLine contents] . "\r\n") }
/tool e-mail send server="0.0.0.0" port=587 user="logindopoczty" password="haslodopoczty" to="dokogo@dokogo.pl" subject="logMT" body=$logContent
/file remove "logs.txt"

```

# Objaśnienie
## Zapisywanie logów do pliku
/log print file=logs

## Opóźnienie, aby zapewnić zapisanie logów
:delay 10s

## Inicjalizacja zmiennej do przechowywania treści logów
:local logContent ""

## Odczytywanie logów z pliku i zapisywanie ich do zmiennej
:foreach logLine in=[/file find name="logs.txt"] do={
    :set logContent ($logContent . [/file get $logLine contents] . "\r\n")
}

## Wysyłanie e-maila z zawartością logów w treści
/tool e-mail send server="0.0.0.0" port=587 user="logindopoczty" password="haslodopoczty" to="dokogo@dokogo.pl" subject="logMT" body=$logContent

## Usuwanie pliku z logami
/file remove "logs.txt"