# Zásady ochrany osobních údajů — Uttero

**Účinné od:** 5. května 2026
**Verze:** 1.0
**Provozovatel:** Pavel Vokoun, fyzická osoba, Česká republika
**Kontakt:** pavel.vokoun@gmail.com

---

## 1. Úvod

Tyto zásady ochrany osobních údajů popisují, jaké údaje aplikace **Uttero** (dále jen „aplikace") shromažďuje, jak je používá a komu je předává. Aplikace je diktovací klávesnice, která převádí mluvené slovo na text.

Používáním aplikace souhlasíte se zpracováním údajů popsaným v tomto dokumentu.

---

## 2. Jaké údaje aplikace zpracovává

### 2.1 Zvuk z mikrofonu

Aplikace přistupuje k mikrofonu zařízení **pouze tehdy, když aktivně diktujete** (uživatel klepne na tlačítko mikrofonu v klávesnici). Zvuk:

- Je v reálném čase streamován do služby pro přepis (viz bod 4 — třetí strany).
- **Není trvale ukládán** v zařízení ani na serverech (s výjimkou dočasného bufferu nutného pro zpracování).
- Je odeslán pouze v zašifrované podobě (HTTPS / WSS).

### 2.2 Přepsaný text

Text vzniklý přepisem:

- Je zobrazen uživateli a vložen do aktuální aplikace (např. Zprávy, e‑mail).
- Je uložen lokálně v zařízení v sekci „Historie" (pokud uživatel tuto funkci nevypne).
- Pokud má uživatel zapnutý styl pro úpravu textu (např. „přeformulovat profesionálně"), je text odeslán do AI služby pro stylování (viz bod 4).

### 2.3 API klíče

Pokud uživatel zadá vlastní API klíč pro službu OpenAI nebo Anthropic, klíč:

- Je uložen **pouze v zařízení** v zašifrovaném úložišti (Android Keystore).
- **Není odesílán** nikomu jinému než dané službě (OpenAI / Anthropic).

### 2.4 Osobní slovník a zkratky

Uživatel může uložit vlastní slovník (oprava výslovnosti, např. „Vokoun" místo „Wokoun") a zkratky (např. „adr" → „Praha 5, Anglická 26"). Tyto údaje:

- Jsou uloženy **pouze v zařízení**.
- **Nejsou odesílány** žádné třetí straně.

### 2.5 Statistiky a logy

Aplikace lokálně zaznamenává:

- Statistiku ušetřeného času (počet přepsaných slov, čas).
- Diagnostické logy (volitelné, lze vypnout).

Tyto údaje **zůstávají v zařízení** a nejsou odesílány nikam ven.

---

## 3. K čemu údaje používáme

| Účel | Údaje | Právní základ (GDPR) |
|------|-------|----------------------|
| Přepis řeči na text | Zvuk z mikrofonu | Plnění smlouvy (poskytnutí služby) |
| Stylování textu (volitelné) | Přepsaný text | Souhlas uživatele (lze kdykoli odvolat) |
| Lokální historie přepisů | Přepsaný text | Oprávněný zájem uživatele |
| Diagnostické logy (volitelné) | Technická data | Oprávněný zájem (oprava chyb) |

---

## 4. Třetí strany — komu předáváme data

Aplikace funguje **online** (cloud přepis) i **offline** (přepis přímo v zařízení). Předávání údajů třetím stranám probíhá **pouze v online režimu**.

### 4.1 Soniox, Inc. (USA)

- **Co:** Zvuk z mikrofonu (streamem)
- **Účel:** Real-time přepis řeči na text
- **Doba uchování:** Dle [politiky Soniox](https://soniox.com/privacy)
- **Předání mimo EU:** Ano (USA — adekvátnost zajištěna [DPF](https://www.dataprivacyframework.gov/))

### 4.2 OpenAI, L.L.C. (USA) — volitelné

- **Co:** Přepsaný text (pokud uživatel použije funkci stylování s OpenAI klíčem)
- **Účel:** Úprava textu (přeformulování, korektura)
- **Doba uchování:** Dle [politiky OpenAI](https://openai.com/policies/privacy-policy)
- **Aktivace:** Pouze pokud uživatel sám zadá svůj API klíč

### 4.3 Anthropic, PBC (USA) — volitelné

- **Co:** Přepsaný text (pokud uživatel použije funkci stylování s Anthropic klíčem)
- **Účel:** Úprava textu (přeformulování, korektura)
- **Doba uchování:** Dle [politiky Anthropic](https://www.anthropic.com/privacy)
- **Aktivace:** Pouze pokud uživatel sám zadá svůj API klíč

### 4.4 Google Play (Google LLC)

- **Co:** Anonymizovaná data o instalacích, pádech a používání (přes Google Play Services)
- **Účel:** Distribuce aplikace, sledování stability
- **Doba uchování:** Dle [politiky Google](https://policies.google.com/privacy)

---

## 5. Co se NEPOSÍLÁ nikam ven

Při použití **offline režimu** (lokální přepis pomocí knihovny whisper.cpp):

- Zvuk **neopouští zařízení**.
- Přepis probíhá výhradně lokálně.
- Žádná data se neposílají na žádný server.

Lokálně uložená data (historie, slovník, zkratky, statistiky) **nikdy neopouštějí zařízení**.

---

## 6. Doba uchovávání údajů

- **V zařízení:** do doby, než uživatel data smaže (manuálně nebo odinstalováním aplikace).
- **U třetích stran:** dle jejich politik (viz bod 4).

---

## 7. Práva uživatele (GDPR)

Jako uživatel máte právo:

- **Na přístup** k údajům, které o vás zpracováváme — kontaktujte nás (viz bod 11).
- **Na opravu** nepřesných údajů.
- **Na výmaz** — všechna lokální data smažete odinstalováním aplikace nebo přes menu Historie / Statistiky / Slovník / Zkratky → smazat. U dat předaných třetím stranám se obraťte přímo na ně (Soniox, OpenAI, Anthropic).
- **Na omezení zpracování**.
- **Na přenositelnost údajů** — historii přepisů si můžete exportovat z menu „Historie".
- **Vznést námitku** proti zpracování.
- **Podat stížnost** u dozorového úřadu (v ČR: [Úřad pro ochranu osobních údajů](https://uoou.gov.cz)).

---

## 8. Děti

Aplikace není určena pro osoby mladší **16 let**. Pokud jste rodič a domníváte se, že nám vaše dítě poskytlo údaje, kontaktujte nás — údaje smažeme.

---

## 9. Bezpečnost

- Veškerá komunikace s třetími stranami probíhá výhradně **šifrovaně** (HTTPS / WSS / TLS 1.2+).
- API klíče jsou v zařízení uloženy v **Android Keystore** (hardwarově chráněném úložišti).
- Lokální data jsou chráněna standardním zabezpečením operačního systému Android.

---

## 10. Změny zásad

Jakékoli změny těchto zásad zveřejníme na stejné stránce s aktualizovaným datem účinnosti. U podstatných změn vás upozorníme přímo v aplikaci.

---

## 11. Kontakt

**Pavel Vokoun**
Email: pavel.vokoun@gmail.com

V případě dotazů, žádostí o výmaz nebo jiných práv napište na uvedený email. Odpovíme do 30 dnů.

---

*Anglická verze tohoto dokumentu je k dispozici na: [English version](./privacy-en.md)*
