# MITI v2 — lista kontrolna dla testerów · testing checklist

**PL** — wersja polska poniżej · **EN** — English version below.

Zgłoszenia: [Issues](https://github.com/brepo-poland/MITI/issues) (szablon „Bug report")
albo [r/miti_app](https://www.reddit.com/r/miti_app/).

---

## PL — Polski

Wymagania: Windows 10 1809 (build 17763) lub nowszy, 64-bit.

### Start i konfiguracja
- [ ] Ekran startowy pokazuje stan narzędzi: `ssh.exe`, `ssh-keygen.exe` (składniki Windows),
      `WinSCP.exe`, `bws.exe`, Bitwarden — z wersją i wynikiem weryfikacji podpisu.
- [ ] Linia zgodności systemu podaje Twój build i mówi, że jest zgodny.
- [ ] Kontrola wersji aplikacji odpowiada (nowsza / taka sama / starsza niż w repo).
- [ ] **999** przełącza PL/EN. W obu językach polskie znaki wyświetlają się poprawnie,
      a żadna pozycja nie pokazuje gołego klucza tłumaczenia (np. `menu.5`).

### Codzienne funkcje (menu główne)
- [ ] **1. SSH / TTY** — logowanie kluczem, sesja w tym samym oknie: strzałki, historia,
      zaznaczanie i kopiowanie QuickEdit, `exit` wraca do menu.
- [ ] **2. WinSCP / SFTP** — otwiera się i przechodzi przez katalogi, przesyła plik w obie strony.
- [ ] **3. Moje klucze SSH** — lista, zmiana nazwy, usuwanie. Nad listą stoi legenda:
      znaczenie rozszerzeń oraz wszystkich 19 pól standardu MITI KEY FORMAT V11.
- [ ] **4. Nowy serwer** — hasłem oraz z `-k` (tylko klucz). Klucz Ed25519 ląduje na serwerze,
      kolejne logowanie idzie już kluczem. Sprawdź też przejście na root (sudo/su).
- [ ] **5. Pomoc** — numery i opisy zgadzają się z tym, co program faktycznie robi.

### Opcje zaawansowane (900; numery 901-907 działają też z wiersza poleceń)
- [ ] **901** — aktualizacja narzędzi portable i sprawdzenie nowszej wersji aplikacji.
- [ ] **902** — otwiera plik INI.
- [ ] **903** — wymiana klucza na serwerze: nowy działa, stare zniknęły.
- [ ] **904** — test kluczy: poprawnie rozpoznaje, które logują, i naprawia co się da.
- [ ] **905** — zapis tokenu/sekretu do konfiguracji; wartość w INI jest zaszyfrowana (`dpapi:`).
- [ ] **906** — odszyfrowanie i podgląd: klucz SSH, hasło i token wyświetlają się tak samo,
      z 19 polami i sekretem w osobnej linii gotowej do skopiowania.
- [ ] **906 / Ctrl+C** — pierwszy przerywa wypis i **zostawia go na ekranie**, dopiero drugi
      wraca do menu.
- [ ] **907** — import plików MITI `.dpapi` z innego folderu oraz obcego klucza OpenSSH.

### Dwa magazyny
- [ ] Bez skonfigurowanego Bitwarden Secrets Manager program działa normalnie, na samym DPAPI.
- [ ] Po skonfigurowaniu BWS listy pokazują, **z którego magazynu** pochodzi odczyt, a przy
      rekordach BWS podają projekt i jego identyfikator.
- [ ] Zapis do projektu bez prawa zapisu kończy się **czytelnym błędem**, nie ciszą.

### Awaria i odzysk
- [ ] Polecenie PowerShella z pomocy odszyfrowuje wszystkie artefakty i sekrety z INI
      **bez uruchamiania MITI**, i pokazuje ten sam układ 19 pól co program.
- [ ] **1337** — deinstalacja usuwa dane, klucze i EXE.

### Czego NIE ma być w v2
- [ ] Nigdzie nie pojawia się plink, PuTTY ani winssh-pageant — SSH stoi na systemowym OpenSSH.
- [ ] Program nie tworzy ani nie kasuje wpisów w `HKCU\Software\SimonTatham\PuTTY`.
- [ ] Nie powstają pliki `.ppk`.

### Co dopisać w zgłoszeniu
Wersja MITI z ekranu startowego, build Windows, wersje narzędzi, magazyn którego dotyczy
problem (DPAPI / BWS / oba) oraz — opcjonalnie — logi z
`%LOCALAPPDATA%\BREPO_MITI\v<N>\logs\`. **Usuń dane wrażliwe** (hosty, loginy, adresy IP).

---

## EN — English

Requirements: Windows 10 1809 (build 17763) or newer, 64-bit.

### Startup and configuration
- [ ] The startup screen lists tool status: `ssh.exe`, `ssh-keygen.exe` (Windows components),
      `WinSCP.exe`, `bws.exe`, Bitwarden — with version and signature verification result.
- [ ] The compatibility line reports your build and says it is supported.
- [ ] The application version check answers (newer / same / older than the repo).
- [ ] **999** switches PL/EN. Polish characters render correctly in both, and no item shows
      a bare translation key (e.g. `menu.5`).

### Everyday features (main menu)
- [ ] **1. SSH / TTY** — key login, session in the same window: arrows, history,
      QuickEdit select-and-copy, `exit` returns to the menu.
- [ ] **2. WinSCP / SFTP** — opens, browses directories, transfers a file both ways.
- [ ] **3. My SSH keys** — list, rename, delete. Above the list there is a legend: what the
      extensions and all 19 fields of MITI KEY FORMAT V11 mean.
- [ ] **4. New server** — by password and with `-k` (key only). The Ed25519 key lands on the
      server and the next login uses it. Also check the switch to root (sudo/su).
- [ ] **5. Help** — the numbers and descriptions match what the program actually does.

### Advanced options (900; numbers 901-907 also work from the command line)
- [ ] **901** — update portable tools and check for a newer application version.
- [ ] **902** — opens the INI file.
- [ ] **903** — key rotation on a server: the new one works, the old ones are gone.
- [ ] **904** — key test: correctly identifies which ones log in, and repairs what it can.
- [ ] **905** — save a token/secret into config; the INI value is encrypted (`dpapi:`).
- [ ] **906** — decrypt and view: SSH key, password and token all render the same way,
      with 19 fields and the secret on its own line ready to copy.
- [ ] **906 / Ctrl+C** — the first one stops the output and **keeps it on screen**; only the
      second returns to the menu.
- [ ] **907** — import MITI `.dpapi` files from another folder, and a foreign OpenSSH key.

### Two stores
- [ ] Without Bitwarden Secrets Manager configured the program works normally, on DPAPI alone.
- [ ] With BWS configured, the lists show **which store** a read came from, and BWS records
      also carry the project and its identifier.
- [ ] Writing to a read-only project fails with a **clear error**, not silence.

### Failure and recovery
- [ ] The PowerShell command from the help decrypts all artifacts and INI secrets
      **without running MITI**, and shows the same 19-field layout as the program.
- [ ] **1337** — uninstall removes data, keys and the EXE.

### What must NOT be in v2
- [ ] plink, PuTTY and winssh-pageant appear nowhere — SSH runs on the system OpenSSH.
- [ ] The program neither creates nor deletes entries under `HKCU\Software\SimonTatham\PuTTY`.
- [ ] No `.ppk` files are produced.

### What to include in a report
The MITI version from the startup screen, the Windows build, tool versions, the store the
problem concerns (DPAPI / BWS / both) and — optionally — logs from
`%LOCALAPPDATA%\BREPO_MITI\v<N>\logs\`. **Remove sensitive data** (hosts, logins, IPs).
