# BREPO_MITI — Master IT Integrator

**Menedżer połączeń i kluczy SSH/SFTP dla Windows** — natywna aplikacja C++/Win32,
która w czasie działania **nie uruchamia cmd ani PowerShell**.

🇵🇱 Wersja polska poniżej · 🇬🇧 English version below.

**Pobierz / Download:** [Releases → `BREPO_MITI.exe`](https://github.com/brepo-poland/MITI/releases/latest)

---

## 🇵🇱 Polski

Menedżer połączeń i kluczy SSH/SFTP dla Windows. Loguje się kluczem lub hasłem, generuje
i wgrywa klucze Ed25519 na serwer, a klucze prywatne trzyma zaszyfrowane mechanizmem
**DPAPI** — odczyta je tylko Twoje konto Windows, nic nie leży jawnie na dysku.

### Co potrafi
- **SSH / TTY** — interaktywna sesja terminalowa (silnik plink), prawdziwy TTY w tym samym oknie.
- **WinSCP / SFTP** — graficzne przeglądanie i przesyłanie plików.
- **Klucze DPAPI** — podgląd kluczy w magazynie, logowanie hasłem oraz wgranie/wygenerowanie klucza (Ed25519) na serwerze, z opcją przejścia na root (sudo/su).
- **Narzędzia portable** — pobiera i weryfikuje plink / WinSCP / winssh-pageant (podpis cyfrowy + SHA-256 zapamiętane w DPAPI).
- **Bitwarden SSH Agent** — opcjonalnie logowanie kluczem trzymanym w Bitwardenie.
- **Samoaktualizacja** — sprawdza nowszą wersję i (za zgodą) sama się aktualizuje.

### Wymagania
Windows 10 1809 (build 17763) lub nowszy, 64-bit.

### Pierwsze uruchomienie
Plik `BREPO_MITI.exe` jest **podpisany cyfrowo** (certyfikat EV, Brepo Sp. z o.o.). Jeśli
SmartScreen pokaże „nierozpoznana aplikacja" (nowe wydanie dopiero buduje reputację) —
kliknij **Więcej informacji → Uruchom mimo to**, albo we Właściwościach pliku zaznacz **Odblokuj**.

### Licencja
MIT — pełny tekst w pliku [LICENSE](LICENSE). Pełne informacje PL/EN oraz podziękowania dla
autorów narzędzi: [LICENSE_PL_EN](LICENSE_PL_EN). Narzędzia (plink / WinSCP / winssh-pageant)
są **pobierane** w czasie działania z oficjalnych źródeł i pozostają na własnych licencjach.

---

## 🇬🇧 English

An SSH/SFTP connection and key manager for Windows. It logs in with a key or a password,
generates and uploads Ed25519 keys to the server, and keeps private keys encrypted with
**DPAPI** — only your Windows account can read them, nothing is stored in plaintext.

### Features
- **SSH / TTY** — interactive terminal session (plink engine), a real TTY in the same window.
- **WinSCP / SFTP** — graphical file browsing and transfer.
- **DPAPI keys** — view keys in the store, password login and uploading/generating an Ed25519 key on the server, with an optional switch to root (sudo/su).
- **Portable tools** — downloads and verifies plink / WinSCP / winssh-pageant (digital signature + SHA-256 remembered in DPAPI).
- **Bitwarden SSH Agent** — optionally log in with a key kept in Bitwarden.
- **Self-update** — checks for a newer version and (on approval) updates itself.

### Requirements
Windows 10 1809 (build 17763) or newer, 64-bit.

### First run
`BREPO_MITI.exe` is **digitally signed** (EV certificate, Brepo Sp. z o.o.). If SmartScreen
shows an "unrecognized app" warning (a new release is still building reputation), click
**More info → Run anyway**, or tick **Unblock** in the file's Properties.

### License
MIT — full text in [LICENSE](LICENSE). Full PL/EN information and acknowledgements to the
tool authors: [LICENSE_PL_EN](LICENSE_PL_EN). The tools (plink / WinSCP / winssh-pageant) are
**downloaded** at runtime from their official sources and remain under their own licenses.

---

© 2026 [POLAND] Brepo Sp. z o.o. · <https://brepo.pl>
