# Port Scanner (Python)

🇬🇧 [English](#english) | 🇵🇱 [Polski](#polski)

---

## English

A simple TCP port scanner written in Python using the built-in `socket` library. Scans a given IP address across a range of ports and reports which ones are open.

### How to run
```bash
python scanner.py
```
By default it scans `127.0.0.1` on ports `1–512`. Edit the `target_ip`, `start_port`, and `end_port` values in the script to scan a different target/range.

### Example output
```
Skanuję 127.0.0.1 na portach 1-512...

  [OTWARTY] Port 135
  [OTWARTY] Port 445

Skanowanie zakończone. Znaleziono 2 otwartych portów.
Otwarte porty: [135, 445]
```

### What I learned
- Working with TCP sockets in Python (`AF_INET`, `SOCK_STREAM`)
- Using `connect_ex()` for non-blocking-style connection checks instead of exception-based `connect()`
- Why timeouts matter when scanning closed/filtered ports
- Structuring code into reusable functions (`check_port`, `scan_range`)

### Next steps
- Add multithreading (`concurrent.futures`) to speed up scanning
- Add CLI arguments (`argparse`) for target IP and port range
- Map common ports to service names (e.g. 22 → SSH, 80 → HTTP)

---

## Polski

Prosty skaner portów TCP napisany w Pythonie z wykorzystaniem wbudowanej biblioteki `socket`. Skanuje podany adres IP w zadanym zakresie portów i pokazuje, które są otwarte.

### Jak uruchomić
```bash
python scanner.py
```
Domyślnie skanuje `127.0.0.1` na portach `1–512`. Aby zmienić cel/zakres, edytuj wartości `target_ip`, `start_port` i `end_port` w skrypcie.

### Przykładowy wynik
```
Skanuję 127.0.0.1 na portach 1-512...

  [OTWARTY] Port 135
  [OTWARTY] Port 445

Skanowanie zakończone. Znaleziono 2 otwartych portów.
Otwarte porty: [135, 445]
```

### Czego się nauczyłem
- Pracy z gniazdami TCP w Pythonie (`AF_INET`, `SOCK_STREAM`)
- Używania `connect_ex()` zamiast opartego na wyjątkach `connect()`
- Dlaczego timeouty są ważne przy skanowaniu zamkniętych/filtrowanych portów
- Dzielenia kodu na funkcje wielokrotnego użytku (`check_port`, `scan_range`)

### Następne kroki
- Dodanie wielowątkowości (`concurrent.futures`) dla przyspieszenia skanowania
- Dodanie argumentów CLI (`argparse`) dla adresu IP i zakresu portów
- Mapowanie popularnych portów na nazwy usług (np. 22 → SSH, 80 → HTTP)
