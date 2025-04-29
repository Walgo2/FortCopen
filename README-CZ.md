# 🛡️ FortCopen

FortCopen je obranná aplikace určená pro Minecraft servery. Byl jsem obětí projektu **Copenheimer**, což mě motivovalo vytvořit tento nástroj, který chrání servery před útoky podobných skupin a zároveň posílá upozornění na **Discord**.

## 🚨 Proč FortCopen?

Po útoku z organizované skupiny útočníků jsem si uvědomil, že běžné zabezpečení Minecraft serverů není dostatečné. FortCopen vznikl jako reakce – jednoduchý, ale účinný firewallový nástroj s integrací do Discordu, který automaticky rozpozná podezřelé připojení, zablokuje IP adresu a upozorní adminy.

## ⚙️ Jak to funguje?

- **Monitoruje připojení na zvoleném portu (např. 25565)** pomocí knihovny `scapy`.
- Analyzuje Minecraft handshake packety a pokusy o přihlášení.
- Porovnává IP adresy s whitelistem.
- Automaticky:
  - blokuje neautorizované IP pomocí Windows Firewall (`netsh`),
  - posílá upozornění na Discord webhook s informací o IP a přezdívce hráče.
- Má **grafické rozhraní (Tkinter GUI)**, kde můžeš:
  - spravovat whitelist/blacklist,
  - přidávat Discord webhooky,
  - měnit cílový port,
  - zobrazit firewall logy.

## 📁 Co obsahuje projekt

- `FortCopen.py` – hlavní kód aplikace.
- `env.txt` – konfigurační soubor s whitelistem, webhooky a portem.
- `_internal/` – interní závislosti, které musí být součástí instalace.
- `dogo.ico` – ikona aplikace.
- `.iss` soubor – instalační skript pro Inno Setup.

## 🧪 Požadavky

- Windows (s povoleným záznamem firewall logů)
- Administrátorská oprávnění

## 🔗 Instalace

Instalátor vytvoří všechny potřebné soubory, včetně `env.txt`. Pokud `Npcap` není nainstalován, nabídne jeho stažení automaticky.

## 📡 Discord notifikace

Do GUI lze zadat libovolný počet Discord webhook URL. Pokud dojde k podezřelému připojení, FortCopen odešle upozornění s IP adresou a jménem hráče.

---

💬 Pokud máš dotazy nebo návrhy na zlepšení, otevři issue nebo vytvoř pull request.

