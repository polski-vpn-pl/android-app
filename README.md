<div align="center">

# 🇵🇱 Polski VPN

**Prosty, szybki klient VPN dla Androida i Android TV — z obsługą protokołów: OpenVPN i SoftEther.**

![Platform](https://img.shields.io/badge/platform-Android%20%7C%20Android%20TV-3DDC84?logo=android&logoColor=white)
![Flutter](https://img.shields.io/badge/Flutter-3.44-02569B?logo=flutter&logoColor=white)
![Protocols](https://img.shields.io/badge/VPN-OpenVPN%20%2B%20SoftEther-blue)
![minSdk](https://img.shields.io/badge/minSdk-24-orange)
![Version](https://img.shields.io/badge/version-1.2.0-success)

<a href="https://play.google.com/store/apps/details?id=com.polski_vpn.pl">
  <img alt="Pobierz z Google Play"
       src="https://play.google.com/intl/pl/badges/static/images/badges/pl_badge_web_generic.png"
       height="64">
</a>

</div>

---

## ✨ W skrócie

**Polski VPN** to aplikacja kliencka VPN, działająca na telefonach z Androidem oraz na Android TV. Łączy się z serwerami usługi <a href="https://polski-vpn.pl/">*Polski-VPN.pl*</a> przy użyciu jednego z dwóch protokołów: sprawdzonego **OpenVPN** lub **SoftEther VPN** (TCP over HTTPS/TLS). Interfejs jest stworzony w języku polskim, minimalistyczny — wybierz serwer, wpisz dane dostępowe które otrzymałeś po zakupie usługi i połącz się.

---

## 👤 Dla kogo

| Odbiorca | Dlaczego |
|---|---|
| 🧑‍💻 Użytkownicy usługi **Polski VPN** | Dedykowany, lekki klient serwerów Polski VPN |
| 📺 Posiadacze **Android TV** | Pełna obsługa pilota (*) |
| 🔒 Szukający alternatywy dla OpenVPN | Klient SoftEther na Androida |
| 🛡️ Omijający blokady VPN | SoftEther over HTTPS/TLS |

---

## 🚀 Funkcje

| Funkcja | Opis | Status |
|---|---|:---:|
| Dwa protokoły VPN | OpenVPN oraz SoftEther | ✅ |
| Lista serwerów | Wybór z poziomu aplikacji | ✅ |
| Zapamiętywanie danych | Login/hasło w `flutter_secure_storage` | ✅ |
| Auto-reconnect | Ponawianie w przypadku zerwania sesji | ✅ |
| Limit prób | Konfigurowalny | ✅ |
| Obsługa tła | „Zawsze połączony" / oszczędzanie przy wygaszonym ekranie / deep sleep | ✅ |
| Android TV | Pełne wsparcie Android TV | ✅ |
| Pełny tunel | Cały ruch (`0.0.0.0/0`) jest tunelowany przez VPN | ✅ |

---

## 🔌 Protokoły — co dokładnie działa

| Cecha | OpenVPN | SoftEther |
|---|:---:|:---:|
| Transport | TCP / UDP | TCP (HTTPS/TLS) |
| Uwierzytelnianie | Login / Hasło | Login / Hasło |
| Przydział IP | DHCP | DHCP |
| Szyfrowanie | AES-256-GCM / AES-128-* | TLS 1.2 (AES) |
| Stan połączenia | pełny cykl | pełny cykl |
| UDP | ✅ | 🚧 |

> **Uwaga odnośnie protokołu SoftEther:** Weryfikacja certyfikatu **nie jest obecnie obsługiwana** (weryfikacja jest świadomie wyłączona i nie stanowi zagrożenia).

---

## ⚙️ Więcej o protokole SoftEther (uproszczony przebieg)

```
Klient                                   Serwer SoftEther
  │                                            │
  │── TCP connect ────────────────────────────▶│
  │── TLS handshake (OpenSSL) ────────────────▶│
  │── Watermark  ─────────────────────────────▶│
  │◀── Hello (random) ─────────────────────────│
  │── Auth  ──────────────────────────────────▶│
  │◀── Auth OK + sesja ────────────────────────│
  │── DHCP request ───────────────────────────▶│
  │◀── przydzielony IP / GW / DNS ─────────────│
  │═══ ramki Ethernet (L2) w tunelu TLS ══════▶│  ◀── TUN ◀── system Android
```

---

## 🖥️ Na czym działa

| Element | Wymaganie |
|---|---|
| System | Android 7.0+ (API 24) |
| Urządzenia | Telefony, tablety, **Android TV** |
| Architektury (ABI) | `arm64-v8a`, `armeabi-v7a`, `x86`, `x86_64` |
| Uprawnienia | VPN (`BIND_VPN_SERVICE`), Internet, Foreground Service |

---

## 📜 Licencje

- Kod aplikacji — własność dostawcy usługi Polski-VPN.pl
- SoftEther VPN — Apache 2.0 · OpenSSL 1.1.1w — OpenSSL/SSLeay License · ics-openvpn — GPLv2.

---

<div align="center">
<sub>Zbudowane dla użytkowników Polski-VPN.pl</sub>
</div>
