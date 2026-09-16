# Zásady ochrany osobních údajů — Uttero

**Účinné od:** 16. září 2026
**Verze:** 2.1
**Platí pro:** Uttero pro Android (`app.uttero.android`)
**Provozovatel:** Pavel Vokoun, fyzická osoba, Česká republika
**Kontakt:** pavel.vokoun@gmail.com

---

## 1. Úvod

Tyto zásady popisují, jaké údaje aplikace **Uttero** (dále jen „aplikace") zpracovává, kde je ukládá a komu je předává. Uttero je diktovací klávesnice pro Android, která převádí mluvené slovo na text.

Aplikace nemá uživatelské účty a nevyžaduje registraci. Všechna data vznikají a zůstávají v telefonu, s výjimkou toho, co je popsáno v bodu 4.

Uttero pro Android je port [iOS aplikace Uttero](https://danielgamrot.cz/nastroje/uttero-ios/) od Daniela Gamrota. Jde o samostatnou aplikaci se samostatným kódem — data se mezi verzemi nesdílejí a tyto zásady platí výhradně pro verzi pro Android.

---

## 2. Jaké údaje aplikace zpracovává

### 2.1 Zvuk z mikrofonu

Aplikace přistupuje k mikrofonu **pouze tehdy, když aktivně diktujete** — po klepnutí na tlačítko mikrofonu v klávesnici. Během nahrávání běží trvalé oznámení v liště, takže je vždy vidět, že mikrofon pracuje.

- Zvuk se zpracovává průběžně a **neukládá se do žádného souboru** — v telefonu ani na serveru. Aplikace nemá funkci „nahrávky" a žádné audio si neuchovává.
- V **online režimu** se zvuk šifrovaně streamuje službě Soniox, která z něj dělá přepis (viz bod 4.1).
- V **offline režimu** zvuk zpracovává rozpoznávač řeči přímo v telefonu (viz bod 4.4).

### 2.2 Přepsaný text

- Vkládá se do aplikace, ve které právě píšete (Zprávy, e-mail, poznámky).
- Ukládá se do lokální **Historie** v telefonu. Historii lze kdykoli smazat v menu Historie.
- Pokud použijete **styl** (Vyčištění, Formátování, E-mail, Angličtina, Myšlenky) nebo režim **Asistent**, odešle se text poskytovateli AI, kterého jste vybrali v Nastavení: Anthropic nebo OpenAI (viz body 4.2 a 4.3). Styl **Přepis** žádnou AI službu nevolá — text zůstane v telefonu.

Odesílá se **pouze text**, nikdy zvuk.

### 2.3 API klíče

Aplikace nemá vlastní servery ani sdílené klíče. Zadáváte vlastní klíč pro Soniox a, pokud používáte styly nebo Asistenta, také pro Anthropic nebo OpenAI.

- Klíče jsou uloženy **jen v telefonu**, v šifrovaném úložišti (`EncryptedSharedPreferences`); šifrovací klíč je v Android Keystore, tedy v hardwarově chráněné části zařízení.
- Klíč se posílá **výhradně té službě, které patří**, a nikomu jinému.

### 2.4 Slovník, zkratky a styly

Vlastní slovník (např. „Vokoun" místo „Wokoun"), textové zkratky (např. „adr" → adresa) a nastavení stylů:

- Jsou uloženy **jen v telefonu**.
- **Neodesílají se** nikam ven — s jedinou výjimkou: pokud se slovníkový výraz nebo rozvinutá zkratka objeví v diktovaném textu a použijete styl, odejde jako součást textu vybranému poskytovateli AI, aby ho model neopravil na jiný tvar.

### 2.5 Statistiky

Aplikace si lokálně počítá přepsaná slova a odhad ušetřeného času. Tato čísla **zůstávají v telefonu** a nikam se neposílají.

### 2.6 Diagnostický log

Aplikace umí zapisovat technický log pro hledání chyb.

- Je **ve výchozím stavu vypnutý**. Zapíná se ručně v Nastavení → Diagnostika.
- Zapisuje se do souboru **uvnitř aplikace**, nikam se neodesílá. Obsah si můžete prohlédnout, zkopírovat, sdílet nebo smazat — odeslání je vždy vaše vědomé rozhodnutí.

### 2.7 Co aplikace NEZPRACOVÁVÁ

Aplikace neobsahuje žádnou analytiku, žádné SDK pro hlášení pádů ani reklamní knihovny. Konkrétně v ní **není** Firebase, Google Analytics, Sentry, TelemetryDeck ani Supabase. Nesleduje, které aplikace používáte, a nevytváří o vás žádný profil ani identifikátor.

---

## 3. Kde jsou data uložena

| Údaj | Kde | Zálohuje se? |
|---|---|---|
| Zvuk | Nikde — neukládá se | — |
| Přepsaný text (Historie) | Databáze v telefonu | Ne |
| Slovník, zkratky, styly | Databáze v telefonu | Ne |
| Statistiky | Databáze v telefonu | Ne |
| API klíče | Šifrované úložiště + Android Keystore | Ne |
| Diagnostický log | Soubor uvnitř aplikace | Ne |

Aplikace má **vypnuté zálohování** (`allowBackup="false"`) a navíc výslovně vyloučená svá data z přímého přenosu mezi telefony. Diktovaný text se tak nedostane do zálohy na Google účtu ani na nový telefon při jeho nastavování. Aplikace nemá žádnou synchronizaci mezi zařízeními.

---

## 4. Třetí strany — komu se data předávají

### 4.1 Soniox, Inc. (USA) — online přepis

- **Co se odesílá:** zvuk z mikrofonu, streamem, jen po dobu diktování
- **Účel:** převod řeči na text v reálném čase
- **Kdy:** v online režimu, tedy ve výchozím nastavení
- **Přenos:** šifrovaně (WSS/TLS)
- **Uchování:** dle [zásad Soniox](https://soniox.com/privacy)
- **Předání mimo EU:** ano (USA)

### 4.2 Anthropic, PBC (USA) — volitelné zpracování textu

- **Co se odesílá:** přepsaný text. Nikdy zvuk.
- **Účel:** úprava textu podle vybraného stylu nebo odpověď na požadavek Asistenta
- **Kdy:** jen když je v Nastavení vybrán Anthropic a použijete styl, který model volá, nebo režim Asistent. Styl Přepis text neodesílá.
- **Přenos:** šifrovaně (HTTPS/TLS)
- **Uchování:** dle [zásad Anthropic](https://www.anthropic.com/privacy)
- **Předání mimo EU:** ano (USA)

### 4.3 OpenAI, LLC (USA) — volitelné zpracování textu

- **Co se odesílá:** přepsaný text. Nikdy zvuk.
- **Účel:** úprava textu podle vybraného stylu nebo odpověď na požadavek Asistenta
- **Kdy:** jen když je v Nastavení vybráno OpenAI a použijete styl, který model volá, nebo režim Asistent. Styl Přepis text neodesílá.
- **Přenos:** šifrovaně (HTTPS/TLS)
- **Uchování:** aplikace nastavuje `store=false`, takže Responses API neuchovává stav požadavku pro pozdější načtení. OpenAI může vstupy a výstupy API ponechat v logu pro kontrolu zneužití až 30 dnů, pokud váš účet OpenAI nemá přísnější režim uchování. Vstupy a výstupy API se ve výchozím nastavení nepoužívají k trénování modelů OpenAI. Podrobnosti uvádí [pravidla OpenAI pro data v API](https://platform.openai.com/docs/models/default-usage-policies-by-endpoint).
- **Předání mimo EU:** ano (USA)

### 4.4 Google — rozpoznávání řeči v telefonu (offline režim)

Offline režim používá rozpoznávač řeči vestavěný v Androidu, který dodává Google.

- Na **Androidu 13 a novějším** aplikace používá rozhraní, které pracuje výhradně v zařízení — zvuk telefon neopustí.
- Na **starším Androidu** aplikace o zpracování v zařízení požádá, ale systém není povinen vyhovět. Pokud v telefonu chybí offline jazykový balíček, může Google zvuk zpracovat na svých serverech. Zaručeně offline je proto jen Android 13 a novější.
- Offline režim v praxi funguje **jen pro angličtinu** — Google pro češtinu rozpoznávání v zařízení nenabízí. Česky lze diktovat pouze online přes Soniox.

Zpracování v tomto režimu se řídí [zásadami Google](https://policies.google.com/privacy).

### 4.5 Google Play (Google LLC) — distribuce

Aplikace se šíří přes Google Play. Samotná aplikace do Play nic neposílá a neobsahuje Play Services, ale obchod na úrovni systému sbírá anonymní údaje o instalacích a pádech (Android Vitals). To je mimo kontrolu aplikace a řídí se [zásadami Google](https://policies.google.com/privacy).

---

## 5. Oprávnění klávesnice

Android klávesnice je systémová komponenta a při jejím zapnutí vás systém varuje, že „může sbírat veškerý text, který píšete". Je to obecné upozornění, které Android zobrazuje u každé klávesnice.

Uttero čte obsah pole jen v rozsahu nutném pro vložení diktovaného textu na správné místo. **Nezaznamenává, co píšete na klávesnici, a nic z toho neodesílá.** Ven odchází výhradně to, co sami nadiktujete, a to způsobem popsaným v bodu 4.

Aplikace požaduje tato oprávnění:

| Oprávnění | K čemu |
|---|---|
| Mikrofon | Nahrávání řeči při diktování |
| Internet, stav sítě | Přepis přes Soniox a volitelné zpracování textu přes Anthropic nebo OpenAI |
| Služba na popředí (mikrofon) | Aby nahrávání nepřerušil systém |
| Oznámení | Trvalé oznámení během nahrávání |
| Vibrace, probuzení obrazovky | Odezva při vkládání textu, obrazovka nezhasne během diktátu |

---

## 6. Doba uchovávání

- **V telefonu:** dokud data nesmažete — v menu Historie, Slovník, Zkratky, Statistiky, Diagnostika, nebo odinstalováním aplikace. Odinstalace smaže úplně všechno včetně API klíčů.
- **U třetích stran:** dle jejich zásad (viz bod 4).

---

## 7. Vaše práva (GDPR)

Máte právo:

- **Na přístup** k údajům, které o vás zpracováváme. Prakticky jsou všechny vidět přímo v aplikaci — provozovatel k nim nemá přístup, protože neopouštějí váš telefon.
- **Na opravu** nepřesných údajů.
- **Na výmaz** — lokální data smažete v aplikaci nebo jejím odinstalováním. U dat předaných třetím stranám se obraťte přímo na ně (Soniox, Anthropic, OpenAI, Google).
- **Na omezení zpracování** — offline režim, případně nepoužívání stylů.
- **Na přenositelnost** — historii přepisů si můžete exportovat z menu Historie.
- **Vznést námitku** proti zpracování.
- **Podat stížnost** u dozorového úřadu (v ČR [Úřad pro ochranu osobních údajů](https://uoou.gov.cz)).

Právním základem je plnění smlouvy u samotného přepisu, váš souhlas u stylování (odvoláte ho tím, že styly nepoužijete) a oprávněný zájem u lokální historie a diagnostiky.

---

## 8. Děti

Aplikace není navržena speciálně pro děti. Osoba, která podle práva své země nemůže samostatně souhlasit se zpracováním údajů, by ji měla používat jen se souhlasem rodiče nebo zákonného zástupce. Rodič nebo zákonný zástupce nás může požádat o pomoc se smazáním místních dat a s žádostí o výmaz u příslušného poskytovatele služby.

---

## 9. Reklama a sledování

Aplikace neobsahuje reklamu, sledovací pixely ani reklamní identifikátory. Data se **neprodávají** a nepředávají nikomu kromě služeb uvedených v bodu 4, které je zpracovávají výhradně pro popsaný účel.

---

## 10. Bezpečnost

- Veškerá komunikace se službami běží **šifrovaně** (HTTPS / WSS / TLS 1.2+).
- API klíče jsou uloženy v šifrovaném úložišti, jehož klíč sedí v Android Keystore.
- Data aplikace jsou chráněna standardní izolací aplikací v Androidu a vyloučena ze záloh.

---

## 11. Změny zásad

Změny zveřejníme na této stránce s aktualizovaným datem účinnosti. U podstatných změn upozorníme přímo v aplikaci.

---

## 12. Kontakt

**Pavel Vokoun**
E-mail: pavel.vokoun@gmail.com

V případě dotazů, žádosti o výmaz nebo uplatnění jiných práv napište na uvedený e-mail. Odpovíme do 30 dnů.

---

*English version of this document: [English version](./privacy-en.md)*
