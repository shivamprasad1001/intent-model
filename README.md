
# intent-model

A simple and efficient intent classification model for Natural Language Understanding (NLU) tasks. This project allows users to train their own intent classifier using labeled example data. Ideal for chatbots, desktop assistants, and voice interfaces.

## Features

- Customizable intents
- Easy to train using a single script
- JSON-based training data format
- Can be integrated into any NLU or assistant pipeline

## Project Structure

```

intent-model/
├── train.py            # Main training script
├── intentData.json     # Dataset containing labeled intents and examples
├── model/              # (Optional) Directory to store the trained model
└── README.md           # Project documentation

````

## intentData.json Format

Example structure for training data:

```json
[
  {
    "intent": "play_music",
    "examples": [
      "Play some music",
      "Start the playlist",
      "I want to listen to songs"
    ]
  },
  {
    "intent": "set_alarm",
    "examples": [
      "Set an alarm for 7 AM",
      "Wake me up at 6",
      "Alarm at 8 in the morning"
    ]
  }
]
````

## Getting Started

1. Clone the repository:

```bash
git clone https://github.com/shivamprasad1001/intent-model
cd intent-model
```
2. Train the model using your custom data:

```bash
python train.py
```

This will read `intentData.json`, process the data, train the intent classification model, and save it for use in your application.

## Todo

* [ ] Improve training speed and model accuracy
* [ ] Add more sample intent data
* [ ] Provide basic usage instructions for integrating the trained model into external projects

## License

This project is licensed under the MIT License. See the `LICENSE` file for details.

## Author

Shivam Prasad [GitHub](https://github.com/shivamprasad1001)


