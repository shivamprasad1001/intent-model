
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

* Setup your custom entity tags and logic inside `nlu/`.

---

## Training the Models

This assistant uses **custom-trained NLU models**. Train them via the companion repo:

### Intent Model:

➡ [Train intent model using this repository](https://github.com/shivamprasad1001/intent-model)

### NER Model:

➡ (Soon!!)

Once trained:

* Save your intent model inside `nlu/`
* Save your NER model inside `nlu/simple_ner_model`

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

| Feature                          | Status        | Start Date   | End Date     |
|----------------------------------|---------------|--------------|--------------|
| Intent Classification            | ✅ Done        | 2024-01-01   | 2024-02-28   |
| Basic Command Execution          | ✅ Done        | 2024-03-01   | 2024-04-15   |
| Reminder Management              | 🔄 In Progress | 2024-04-16   | 2024-06-30   |
| Voice Input (Speech-to-Text)     | ✅ Done        | 2024-07-01   | 2024-08-15   |
| Text-to-Speech (TTS)             | ✅ Done        | 2024-08-16   | 2024-09-30   |
| GUI Interface                    | ⏳ Planned     | 2024-10-01   | 2024-11-15   |
| Plugin System                    | ⏳ Planned     | 2024-11-16   | 2024-12-31   |


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
