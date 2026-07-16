# BREPO_MITI — Master IT Integrator

**[PL]** Menedżer połączeń i kluczy SSH/SFTP dla Windows. Natywna aplikacja C++/Win32 — jeden plik `.exe`, bez instalatora.

**[EN]** An SSH/SFTP connection and key manager for Windows. A native C++/Win32 application — a single `.exe`, no installer.

**PL** — wersja polska poniżej · **EN** — English version below.

**Pobierz / Download:** [Releases → `BREPO_MITI.exe`](https://github.com/brepo-poland/MITI/releases/latest)

> ### 💬 Community & Support · Społeczność i wsparcie
>
> **[PL]** Dołącz do społeczności, pytaj o pomoc, zgłaszaj błędy i pomóż testować:
> - 💬 **[r/miti_app](https://www.reddit.com/r/miti_app/)** — oficjalna społeczność MITI na Reddicie.
> - 🐛 **Błąd?** Otwórz [Issue](https://github.com/brepo-poland/MITI/issues) (szablon „Bug report") albo napisz na r/miti_app.
> - 💡 **Pomysł na funkcję?** Chętnie posłuchamy — Issues lub społeczność.
> - 🧪 **Testy v2:** szykujemy **v2** (obecne wydanie na [Releases](https://github.com/brepo-poland/MITI/releases) to v1.0.0.0). Pobierz `BREPO_MITI.exe`, sprawdź swój codzienny scenariusz SSH/SFTP i zgłoś uwagi. Wymagania: Windows 10 (1809+) 64-bit.
>
> **[EN]** Join the community, ask for help, report bugs, and help test:
> - 💬 **[r/miti_app](https://www.reddit.com/r/miti_app/)** — the official MITI community on Reddit.
> - 🐛 **Found a bug?** Open an [issue](https://github.com/brepo-poland/MITI/issues) (use the "Bug report" template) or post in r/miti_app.
> - 💡 **Feature idea?** We'd love to hear it — Issues or the community.
> - 🧪 **Testing v2:** we're preparing **v2** (current [Releases](https://github.com/brepo-poland/MITI/releases) build is v1.0.0.0). Download `BREPO_MITI.exe`, try your everyday SSH/SFTP workflow, and report back. Requirements: Windows 10 (1809+) 64-bit.
>
> Dziękujemy! 🙏 · Thanks! 🙏

---

## PL — Polski

**Aplikacja konsolowa** — otwiera się w oknie terminala (to „czarne okno" podobne do wiersza
poleceń). Tak jest **celowo**: sesja SSH (plink) płynie w **tym samym oknie**, z prawdziwym
TTY, zamiast wyskakiwać w osobnym.

Loguje się kluczem lub hasłem, generuje i wgrywa klucze Ed25519 na serwer, a klucze
prywatne trzyma zaszyfrowane mechanizmem **DPAPI** — odczyta je tylko Twoje konto
Windows, nic nie leży jawnie na dysku.

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

## EN — English

**An SSH/SFTP connection and key manager for Windows.** A native C++/Win32 application —
a single `.exe`, no installer.

**A console application** — it opens in a terminal window (the "black window" that looks like
a command prompt). This is **by design**: the SSH session (plink) runs in **that same window**
with a real TTY, instead of popping up separately.

It logs in with a key or a password, generates and uploads Ed25519 keys to the server, and
keeps private keys encrypted with **DPAPI** — only your Windows account can read them,
nothing is stored in plaintext.

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

## Podziękowania · Acknowledgements

**PL** — Ogromne podziękowania dla autorów poniższych narzędzi — zrobili świetną robotę, a BREPO_MITI jedynie łączy je w wygodną całość dla Windows. Narzędzia są pobierane w czasie działania z oficjalnych źródeł i pozostają na własnych licencjach.

**EN** — Huge thanks to the authors of the tools below — they did great work; BREPO_MITI merely brings them together into one convenient whole for Windows. The tools are downloaded at runtime from their official sources and remain under their own licenses.

| Narzędzie · Tool | Autor · Author | Licencja · License |
|---|---|---|
| [PuTTY](https://www.chiark.greenend.org.uk/~sgtatham/putty/) / plink | Simon Tatham | MIT |
| [WinSCP](https://winscp.net/) | Martin Prikryl | GNU GPL |
| [winssh-pageant](https://github.com/ndbeals/winssh-pageant) | ndbeals | patrz repo · see repo |

Pełne informacje o licencjach · full license info: [LICENSE_PL_EN](LICENSE_PL_EN).

---

© 2026 [POLAND] Brepo Sp. z o.o. · <https://brepo.pl>
