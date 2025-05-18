# 🛡️ FortCopen

**FortCopen** je obranná aplikace určená pro ochranu Minecraft serverů. Byl jsem obětí projektu **Copenheimer**, což mě motivovalo vytvořit tento nástroj, který chrání servery před podobnými skupinovými útoky a odesílá upozornění v reálném čase na **Discord**.

## 🚨 Proč FortCopen?

Poté, co byl můj server cílem koordinovaného útoku, jsem zjistil, že běžná ochrana Minecraft serverů nestačí. FortCopen vznikl jako reakce — jednoduchý, ale účinný nástroj, který detekuje podezřelou aktivitu a okamžitě upozorňuje správce.

## ⚙️ Jak to funguje

- Monitoruje síťový provoz na zvoleném portu.
- Analyzuje Minecraft handshake a login pakety.
- Porovnává IP adresy s whitelistem.
- Automaticky:
  - blokuje nepovolené IP adresy,
  - odesílá upozornění na Discord webhooky s IP adresou a uživatelským jménem,
  - vytváří zálohy světa serveru při specifických událostech.
- Obsahuje grafické rozhraní (**Tkinter GUI**), ve kterém lze:
  - spravovat whitelist a blacklist,
  - přidávat/mazat Discord webhooky,
  - měnit cílový port,
  - nastavit RCON konfiguraci,
  - otevírat log firewallu.

## 🔐 Integrace s RCON (NOVINKA ve verzi 1.5)

FortCopen nově umožňuje vzdálené ovládání serveru přes **RCON**:

- Udělování a odebírání **OP** práv hráčům.
- Přepínání hráčů mezi módy **Spectator** a **Survival**.
- Odeslání příkazu **`reload`** přímo z aplikace.
- Nastavení `rcon.port`, `rcon.password` a `enable-rcon` pomocí GUI.
- Server se po změně RCON nastavení automaticky vypne a znovu spustí.

## 💾 Automatické zálohy

FortCopen chrání svět serveru pomocí pravidelných záloh:

- Automatická záloha **každou hodinu**.
- Další zálohy probíhají při:
  - pokusu o připojení nepovoleného hráče,
  - změně OP statusu nebo herního režimu hráče,
  - ručním vypnutí serveru přes GUI,
  - ručním spuštění zálohy tlačítkem v aplikaci.

Zálohy jsou ukládány do složek s časovým razítkem uvnitř adresáře serveru.

## 🚀 Automatické spuštění serveru

- Pokud je v `env.txt` nastaven `BAT_PATH`, Minecraft server se při spuštění FortCopen **automaticky spustí**, pokud již neběží.

## 🧪 Požadavky

- Windows (s aktivovaným logováním firewallu)
- Práva správce (administrator)
- Nainstalovaný [Npcap](https://npcap.com/) (instalátor nabídne stažení, pokud chybí)

## 📡 Upozornění na Discord

Do GUI lze přidat jeden nebo více Discord webhooků. Když dojde k pokusu o neautorizované připojení, FortCopen odešle upozornění s IP adresou a jménem hráče.

---

💬 **Neváhej vytvořit issue nebo pull request**, pokud máš návrh, otázku nebo se chceš zapojit do vývoje.
