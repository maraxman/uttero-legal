# Privacy Policy — Uttero

**Effective date:** September 16, 2026
**Version:** 2.1
**Applies to:** Uttero for Android (`app.uttero.android`)
**Operator:** Pavel Vokoun, individual, Czech Republic
**Contact:** pavel.vokoun@gmail.com

---

## 1. Introduction

This policy describes what data the **Uttero** application (the "App") processes, where it stores it, and to whom it is disclosed. Uttero is an Android dictation keyboard that converts speech to text.

The App has no user accounts and requires no registration. All data is created and stays on your phone, except for what is described in Section 4.

Uttero for Android is a port of the [iOS app Uttero](https://danielgamrot.cz/nastroje/uttero-ios/) by Daniel Gamrot. It is a separate application with a separate codebase — no data is shared between the versions, and this policy applies to the Android version only.

---

## 2. What Data the App Processes

### 2.1 Microphone Audio

The App accesses the microphone **only while you are actively dictating** — after you tap the microphone button in the keyboard. A persistent notification runs during recording, so it is always visible that the microphone is in use.

- Audio is processed on the fly and **is never written to a file** — neither on the phone nor on a server. The App has no "recordings" feature and keeps no audio.
- In **online mode**, audio is streamed encrypted to Soniox, which turns it into text (see 4.1).
- In **offline mode**, audio is processed by a speech recognizer on the phone itself (see 4.4).

### 2.2 Transcribed Text

- It is inserted into whatever app you are typing in (Messages, email, notes).
- It is saved to the local **History** on the phone. History can be deleted at any time from the History menu.
- If you apply a **style** (Cleanup, Formatting, Email, English, Thoughts) or use **Assistant mode**, the text is sent to the AI provider you selected in Settings: Anthropic or OpenAI (see 4.2 and 4.3). The **Transcript** style calls no AI service — the text stays on the phone.

Only **text** is ever sent, never audio.

### 2.3 API Keys

The App has no servers and no shared keys. You enter your own key for Soniox and, if you use styles or Assistant mode, for Anthropic or OpenAI.

- Keys are stored **only on the phone**, in encrypted storage (`EncryptedSharedPreferences`); the encryption key lives in the Android Keystore, a hardware-backed part of the device.
- A key is sent **only to the service it belongs to**, and to no one else.

### 2.4 Dictionary, Shortcuts, and Styles

Your custom dictionary (e.g., "Vokoun" instead of "Wokoun"), text shortcuts (e.g., "addr" → an address), and style settings:

- Are stored **only on the phone**.
- Are **not sent** anywhere, with one exception: if a dictionary term or an expanded shortcut appears in dictated text and you use a style, it travels to the selected AI provider as part of that text, so the model does not "correct" it into a different form.

### 2.5 Statistics

The App locally counts transcribed words and an estimate of time saved. These figures **stay on the phone** and are not sent anywhere.

### 2.6 Diagnostic Log

The App can write a technical log for troubleshooting.

- It is **off by default**. You turn it on manually in Settings → Diagnostics.
- It is written to a file **inside the App** and is never sent anywhere. You can view, copy, share, or delete its contents — sending it is always your deliberate choice.

### 2.7 What the App Does NOT Process

The App contains no analytics, no crash-reporting SDK, and no advertising libraries. Specifically, it does **not** include Firebase, Google Analytics, Sentry, TelemetryDeck, or Supabase. It does not track which apps you use and builds no profile or identifier about you.

---

## 3. Where Data Is Stored

| Data | Where | Backed up? |
|---|---|---|
| Audio | Nowhere — not stored | — |
| Transcribed text (History) | Database on the phone | No |
| Dictionary, shortcuts, styles | Database on the phone | No |
| Statistics | Database on the phone | No |
| API keys | Encrypted storage + Android Keystore | No |
| Diagnostic log | File inside the App | No |

The App has **backups disabled** (`allowBackup="false"`) and additionally excludes its data from direct phone-to-phone transfer. Dictated text therefore never reaches a Google account backup or a new phone during setup. The App has no cross-device synchronization.

---

## 4. Third Parties — Who Receives Data

### 4.1 Soniox, Inc. (USA) — online transcription

- **What is sent:** microphone audio, streamed, only while you dictate
- **Purpose:** real-time speech-to-text
- **When:** in online mode, which is the default
- **Transport:** encrypted (WSS/TLS)
- **Retention:** per [Soniox policy](https://soniox.com/privacy)
- **Transfer outside the EU:** yes (USA)

### 4.2 Anthropic, PBC (USA) — optional text processing

- **What is sent:** the transcribed text. Never audio.
- **Purpose:** rewriting the text according to the selected style or answering an Assistant request
- **When:** only when Anthropic is selected in Settings and you use a style that calls the model or Assistant mode. The Transcript style sends nothing.
- **Transport:** encrypted (HTTPS/TLS)
- **Retention:** per [Anthropic policy](https://www.anthropic.com/privacy)
- **Transfer outside the EU:** yes (USA)

### 4.3 OpenAI, LLC (USA) — optional text processing

- **What is sent:** the transcribed text. Never audio.
- **Purpose:** rewriting the text according to the selected style or answering an Assistant request
- **When:** only when OpenAI is selected in Settings and you use a style that calls the model or Assistant mode. The Transcript style sends nothing.
- **Transport:** encrypted (HTTPS/TLS)
- **Retention:** the App sets `store=false`, so the Responses API does not keep application state for later retrieval. OpenAI may retain API prompts and responses in abuse-monitoring logs for up to 30 days unless your OpenAI organization has stricter retention controls. API inputs and outputs are not used to train OpenAI models by default. See [OpenAI API data controls](https://platform.openai.com/docs/models/default-usage-policies-by-endpoint).
- **Transfer outside the EU:** yes (USA)

### 4.4 Google — on-device speech recognition (offline mode)

Offline mode uses the speech recognizer built into Android and supplied by Google.

- On **Android 13 and newer**, the App uses an interface that works strictly on the device — audio does not leave the phone.
- On **older Android**, the App asks for on-device processing, but the system is not obliged to comply. If the offline language pack is missing, Google may process the audio on its servers. Guaranteed offline processing therefore applies to Android 13 and newer only.
- In practice, offline mode works **for English only** — Google offers no on-device recognition for Czech. Czech dictation is possible only online via Soniox.

Processing in this mode is governed by the [Google privacy policy](https://policies.google.com/privacy).

### 4.5 Google Play (Google LLC) — distribution

The App is distributed through Google Play. The App itself sends nothing to Play and contains no Play Services, but the store collects anonymous installation and crash data at the system level (Android Vitals). This is outside the App's control and is governed by the [Google privacy policy](https://policies.google.com/privacy).

---

## 5. Keyboard Permissions

An Android keyboard is a system component, and when you enable one, the system warns you that it "may be able to collect all the text you type". This is a generic warning Android shows for every keyboard.

Uttero reads the content of a text field only as far as it needs to place dictated text in the right spot. **It does not record what you type on the keyboard and sends none of it anywhere.** The only thing that leaves the device is what you dictate, in the way described in Section 4.

The App requests these permissions:

| Permission | What for |
|---|---|
| Microphone | Recording speech while dictating |
| Internet, network state | Transcription via Soniox and optional text processing via Anthropic or OpenAI |
| Foreground service (microphone) | So the system does not interrupt recording |
| Notifications | The persistent notification shown while recording |
| Vibration, wake lock | Feedback when text is inserted; screen stays on while dictating |

---

## 6. Data Retention

- **On the phone:** until you delete the data — via the History, Dictionary, Shortcuts, Statistics, or Diagnostics menus, or by uninstalling the App. Uninstalling removes everything, including API keys.
- **At third parties:** per their policies (see Section 4).

---

## 7. Your Rights (GDPR)

You have the right to:

- **Access** the data processed about you. In practice all of it is visible directly in the App — the operator has no access to it, because it never leaves your phone.
- **Rectification** of inaccurate data.
- **Erasure** — delete local data in the App or by uninstalling it. For data passed to third parties, contact them directly (Soniox, Anthropic, OpenAI, Google).
- **Restriction of processing** — use offline mode, or simply do not use styles.
- **Data portability** — you can export the transcript history from the History menu.
- **Object** to processing.
- **Lodge a complaint** with a supervisory authority (in the Czech Republic, the [Office for Personal Data Protection](https://uoou.gov.cz)).

The legal basis is performance of a contract for the transcription itself, your consent for styling (withdrawn by not using styles), and legitimate interest for the local history and diagnostics.

---

## 8. Children

The App is not designed specifically for children. A person who cannot consent to data processing independently under the law of their country should use the App only with a parent or guardian's permission. A parent or guardian can contact us for help deleting local data and requesting deletion from the relevant service provider.

---

## 9. Advertising and Tracking

The App contains no advertising, no tracking pixels, and no advertising identifiers. Data is **not sold** and is not passed to anyone other than the services listed in Section 4, which process it solely for the stated purpose.

---

## 10. Security

- All communication with services is **encrypted** (HTTPS / WSS / TLS 1.2+).
- API keys are held in encrypted storage whose key sits in the Android Keystore.
- App data is protected by standard Android app sandboxing and excluded from backups.

---

## 11. Policy Changes

Changes will be published on this page with an updated effective date. For substantial changes, we will notify you within the App.

---

## 12. Contact

**Pavel Vokoun**
Email: pavel.vokoun@gmail.com

For questions, deletion requests, or to exercise other rights, write to the address above. We will respond within 30 days.

---

*Česká verze tohoto dokumentu: [Česká verze](./privacy-cs.md)*
