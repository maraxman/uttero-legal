# Privacy Policy — Uttero

**Effective date:** May 5, 2026
**Version:** 1.0
**Operator:** Pavel Vokoun, individual, Czech Republic
**Contact:** pavel.vokoun@gmail.com

---

## 1. Introduction

This Privacy Policy describes what data the **Uttero** application (the "App") collects, how it uses the data, and to whom it is shared. The App is a dictation keyboard that converts speech to text.

By using the App, you agree to the data processing described in this document.

---

## 2. What Data the App Processes

### 2.1 Microphone Audio

The App accesses the device microphone **only when you actively dictate** (the user taps the microphone button in the keyboard). The audio:

- Is streamed in real time to a transcription service (see Section 4 — third parties).
- **Is not permanently stored** on the device or on servers (except for a temporary buffer required for processing).
- Is sent only in encrypted form (HTTPS / WSS).

### 2.2 Transcribed Text

The text resulting from transcription:

- Is shown to the user and inserted into the active app (e.g., Messages, email).
- Is stored locally on the device under "History" (unless the user disables this feature).
- If the user enables a style for text editing (e.g., "rephrase professionally"), the text is sent to an AI service for styling (see Section 4).

### 2.3 API Keys

If the user enters their own API key for OpenAI or Anthropic, the key:

- Is stored **only on the device** in encrypted storage (Android Keystore).
- **Is not shared** with anyone other than the corresponding service (OpenAI / Anthropic).

### 2.4 Personal Dictionary and Shortcuts

The user can save a custom dictionary (pronunciation corrections, e.g., "Vokoun" instead of "Wokoun") and shortcuts (e.g., "addr" → "Praha 5, Anglická 26"). This data:

- Is stored **only on the device**.
- **Is not shared** with any third party.

### 2.5 Statistics and Logs

The App locally records:

- Time-saved statistics (number of transcribed words, time).
- Diagnostic logs (optional, can be disabled).

This data **stays on the device** and is not sent anywhere.

---

## 3. How We Use Data

| Purpose | Data | Legal basis (GDPR) |
|---------|------|--------------------|
| Speech-to-text transcription | Microphone audio | Performance of contract (service provision) |
| Text styling (optional) | Transcribed text | User consent (revocable any time) |
| Local transcript history | Transcribed text | Legitimate user interest |
| Diagnostic logs (optional) | Technical data | Legitimate interest (bug fixing) |

---

## 4. Third Parties — Data Recipients

The App works in both **online** (cloud transcription) and **offline** (on-device transcription) modes. Data is shared with third parties **only in online mode**.

### 4.1 Soniox, Inc. (USA)

- **What:** Microphone audio (streamed)
- **Purpose:** Real-time speech-to-text transcription
- **Retention:** Per [Soniox policy](https://soniox.com/privacy)
- **Transfer outside EU:** Yes (USA — adequacy ensured by [DPF](https://www.dataprivacyframework.gov/))

### 4.2 OpenAI, L.L.C. (USA) — Optional

- **What:** Transcribed text (when the user uses the styling feature with an OpenAI key)
- **Purpose:** Text editing (rephrasing, proofreading)
- **Retention:** Per [OpenAI policy](https://openai.com/policies/privacy-policy)
- **Activation:** Only if the user provides their own API key

### 4.3 Anthropic, PBC (USA) — Optional

- **What:** Transcribed text (when the user uses the styling feature with an Anthropic key)
- **Purpose:** Text editing (rephrasing, proofreading)
- **Retention:** Per [Anthropic policy](https://www.anthropic.com/privacy)
- **Activation:** Only if the user provides their own API key

### 4.4 Google Play (Google LLC)

- **What:** Anonymized installation, crash, and usage data (via Google Play Services)
- **Purpose:** App distribution, stability tracking
- **Retention:** Per [Google policy](https://policies.google.com/privacy)

---

## 5. What Is NEVER Sent Anywhere

When using **offline mode** (local transcription via the whisper.cpp library):

- Audio **never leaves the device**.
- Transcription happens entirely locally.
- No data is sent to any server.

Locally stored data (history, dictionary, shortcuts, statistics) **never leaves the device**.

---

## 6. Data Retention

- **On the device:** until the user deletes the data (manually or by uninstalling the App).
- **At third parties:** per their policies (see Section 4).

---

## 7. User Rights (GDPR)

As a user, you have the right to:

- **Access** the data we process about you — contact us (see Section 11).
- **Rectification** of inaccurate data.
- **Erasure** — you can delete all local data by uninstalling the App or via the menu History / Statistics / Dictionary / Shortcuts → delete. For data shared with third parties, contact them directly (Soniox, OpenAI, Anthropic).
- **Restriction of processing**.
- **Data portability** — you can export the transcript history from the "History" menu.
- **Object** to processing.
- **Lodge a complaint** with a supervisory authority (in the Czech Republic: [Office for Personal Data Protection](https://uoou.gov.cz)).

---

## 8. Children

The App is not intended for persons under **16 years of age**. If you are a parent and believe your child has provided us with data, please contact us — we will delete the data.

---

## 9. Security

- All communication with third parties is exclusively **encrypted** (HTTPS / WSS / TLS 1.2+).
- API keys are stored on the device in **Android Keystore** (hardware-backed storage).
- Local data is protected by the standard security of the Android operating system.

---

## 10. Policy Changes

Any changes to this Policy will be published on the same page with an updated effective date. For substantial changes, we will notify you directly within the App.

---

## 11. Contact

**Pavel Vokoun**
Email: pavel.vokoun@gmail.com

For questions, deletion requests, or other rights, please write to the email above. We will respond within 30 days.

---

*A Czech version of this document is available at: [Česká verze](./privacy-cs.md)*
