
# AIDesktopAssistant

## Overview

AIDesktopAssistant is a modular, intelligent desktop assistant that understands and executes natural language commands using custom-trained **Intent Classification** and **Named Entity Recognition (NER)** models. It can perform tasks like launching apps, setting reminders, controlling media, and managing system functions.

This assistant is fully offline, customizable, and designed to work across platforms — making it a powerful personal productivity tool for your desktop.

> **Project Started:** 8th June 2025  
> **Status:** Actively under development

---

## Key Features

- 🧠 Custom-trained **Intent Classifier** to detect user commands
- 🔎 Custom **NER model** to extract key details like time, app names, etc.
- ⚙️ Modular action system for adding new capabilities easily
- 🗂️ Local JSON-based data and configuration (no external APIs needed)
- 🧰 Works with your own data and assistant logic — fully extensible

---

## Architecture

```mermaid
graph TD
    A[User Input] --> B[NLU Engine]
    B --> C[Intent Classifier]
    B --> D[NER Model]
    C --> E[Intent Label]
    D --> F[Extracted Entities]
    E --> G[Action Router]
    F --> G
    G --> H[System Modules]
    H --> I[App Control, Reminders, Files, etc.]
````

---

## Project Structure

```
AIDesktopAssistant/
├── main.py                     # Entry point of the assistant
├── nlu/                        # NLU models and processing (Intent & NER)
├── utils/                      # Helper functions and utilities
├── modules/                    # Action modules (apps, reminders, media, etc.)
├── app_registry.json           # Registered applications data
├── config.json                 # Assistant settings and preferences
├── unlisted_apps.log           # Logs for unidentified applications
└── .github/workflows/          # GitHub Actions workflows (CI/CD, Linting)
```

---

## Installation

1. Clone the repository:

```bash
git clone https://github.com/shivamprasad1001/AIDesktopAssistant.git
cd AIDesktopAssistant
```
2. Configure your data:

* Edit `intent_model/intentData.json` to define your intents.
* Setup your custom entity tags and logic inside `nlu/`.

---

## Training the Models

This assistant uses **custom-trained NLU models**. Train them via the companion repo:

### Intent Model:

➡ [Train intent model using this repository](https://github.com/shivamprasad1001/intent-model)

### NER Model:

➡ (Soon!!)

Once trained:

* Save your intent model inside `intent_model/`
* Save your NER model inside `nlu/`
* Ensure the assistant loads them at startup in `main.py` or `nlu/engine.py`

---

## Usage

Start the assistant:

```bash
python main.py
```

Speak or type commands such as:

* **"Open Chrome"** → Launches app
* **"Set a reminder for 9 PM to study"** → Adds to `reminders.json`
* **"Play some music"** → Triggers media module

The assistant will:

1. Classify intent
2. Extract entities
3. Route to the correct module
4. Execute the command

---

## Usage Examples

| Command                          | Intent         | Entities                                  | Result                |
| -------------------------------- | -------------- | ----------------------------------------- | --------------------- |
| Open Notepad                     | `open_app`     | `{"app": "Notepad"}`                      | Launches Notepad      |
| Remind me at 5 PM to drink water | `set_reminder` | `{"time": "5 PM", "task": "drink water"}` | Sets a reminder       |
| Play music                       | `play_music`   | -                                         | Starts media playback |

---

## Development Roadmap

```mermaid
gantt
    title AIDesktopAssistant Roadmap
    dateFormat  YYYY-MM-DD
    section Core System
    Intent Classifier     :done,    ic, 2025-06-08, 2025-06-12
    NER Model              :done,    ner, 2025-06-13, 2025-06-17
    Assistant Engine       :active,  core, 2025-06-17, 2025-06-30
    section Features
    App Launcher Module   :done,    app, 2025-06-17, 2025-06-20
    Reminder Module       :active,  rem, 2025-06-21, 2025-06-28
    Media Control         :planned, media, 2025-07-01, 2025-07-10
    Voice Input           :planned, voice, 2025-07-11, 2025-07-20
    GUI Interface         :planned, gui, 2025-07-21, 2025-08-05
```

---

## Contributing

Contributions are welcome. Please:

* Fork the repo
* Submit a pull request
* Or open issues with ideas or bugs

---

## License

This project is licensed under the MIT License.
See the `LICENSE` file for details.

---

## Author

**Shivam Prasad**
GitHub: [shivamprasad1001](https://github.com/shivamprasad1001)

---

## Acknowledgements

* Built from scratch using custom-trained NLP models
* No external cloud APIs – focused on local, private AI

```

---

Let me know if you’d like to:
- Add contributor badges
- Build a full `/docs` folder with individual pages
- Generate `CONTRIBUTING.md`, `CODE_OF_CONDUCT.md`, or CLI help pages
```
