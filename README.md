# 📝 Exam Simulator

A Python-based exam simulator that allows users to take multiple-choice tests with customizable settings and review their results.

## ✨ Features

- **🌙 Dark Mode Interface**: Clean and eye-friendly dark theme
- **⚙️ Configurable Test Settings**:
  - Choose number of questions (1-50)
  - Enable/disable penalties for wrong answers
  - Enable/disable penalties for unanswered questions
  - Select penalty weight (1, 0.5, or 0.33)
- **🔄 Test Navigation**:
  - Move between questions using Previous/Next buttons
  - Finish test at any time
- **📊 Results Analysis**:
  - View total correct answers
  - View total wrong answers
  - View total unanswered questions
  - See final score with penalty calculations
- **📋 Test Review**:
  - Review all questions after completion
  - See correct and wrong answers highlighted
  - Compare your answers with correct ones

## 🔧 Requirements

- Python 3.x
- tkinter (usually comes with Python)
- json

## 💻 Installation

1. Clone this repository
2. Ensure you have Python 3.x installed
3. Create a `questions` folder in the project directory
4. Add your `questions.json` file in the `questions` folder

## 🚀 Usage

Run the script:
```bash
python simulador.ipynb
```

## 📄 JSON Question Format

The questions should be stored in `questions/questions.json` with the following format:

```json
{
  "perguntas": [
    {
      "id": 1,
      "enunciado": "Question text goes here?",
      "alternativas": [
        "Option 1",
        "Option 2",
        "Option 3",
        "Option 4"
      ],
      "respostaCorreta": 2
    }
  ]
}
```

### 🔍 JSON Fields Explanation:

- `perguntas`: Array containing all questions
- `id`: Unique identifier for each question
- `enunciado`: The question text
- `alternativas`: Array of answer options
- `respostaCorreta`: Index of the correct answer (0-based)

## 🧮 Score Calculation

The final score is calculated using the following formula:

```
score = correct - (wrong * penalty_weight * penalize_wrong) - (unanswered * penalty_weight * penalize_unanswered)
```

Where:
- `correct`: Number of correct answers ✅
- `wrong`: Number of wrong answers ❌
- `unanswered`: Number of unanswered questions ⭕
- `penalty_weight`: Selected penalty weight (1, 0.5, or 0.33)
- `penalize_wrong`: Boolean (true/false) for wrong answer penalty
- `penalize_unanswered`: Boolean (true/false) for unanswered penalty

The final score is never negative (minimum is 0).

## 📜 License

This project is open source and available under the MIT License.