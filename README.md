# Prompt Engineering: A Practical Example

## Motivation & Academic Context

Prompt engineering is a rapidly emerging discipline at the intersection of data science, artificial intelligence, and human-computer interaction. As large language models (LLMs) become foundational tools in research and industry, the ability to systematically design, evaluate, and document prompts is critical for reproducibility, interpretability, and responsible AI deployment. This repository extends and critically documents the Real Python tutorial on prompt engineering, providing a reproducible, research-oriented workflow for iterative prompt development and evaluation.

---

## Project Overview

This repository implements a customer support chat sanitization system using various prompt engineering techniques. The goal is to clean conversations by removing personally identifiable information, replacing profanities, and analyzing the sentiment of the chats. The project is designed as a practical case study for advanced students and researchers in data science and AI, emphasizing the iterative, evidence-driven process of prompt optimization.

## 🚀 Key Features

- **Data Sanitization**: Remove personal information and replace profanities
- **Sentiment Analysis**: Automatically classify the tone of conversations
- **Structured JSON Output**: Organized, machine-readable results
- **Prompt Engineering Log**: Detailed documentation of the iterative prompt engineering process
- **Support for Multiple Models**: Works with both Completions API and Chat Completions API
- **Academic Reproducibility**: All steps, prompts, and results are logged for transparent evaluation

## 📋 Prerequisites

- Python 3.10 or higher
- OpenAI account with a valid API key
- Basic command-line knowledge

## ⚙️ Setup

### 1. Clone the repository
```bash
git clone <your-repo-url>
cd "Prompt Engineering A Practical Example"
```

### 2. Create a virtual environment
```bash
python -m venv venv
```

### 3. Activate the virtual environment
**Windows (PowerShell):**
```powershell
.\venv\Scripts\Activate.ps1
```
If you encounter execution policy issues:
```powershell
Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope Process
.\venv\Scripts\Activate.ps1
```

**Windows (Command Prompt):**
```cmd
.\venv\Scripts\activate.bat
```

**Linux/macOS:**
```bash
source venv/bin/activate
```

### 4. Install dependencies
```bash
pip install -r requirements.txt
```

### 5. Set your OpenAI API Key
```bash
# Windows (PowerShell)
$env:OPENAI_API_KEY="your-api-key-here"

# Windows (Command Prompt)
set OPENAI_API_KEY=your-api-key-here

# Linux/macOS
export OPENAI_API_KEY="your-api-key-here"
```

## 🎮 Usage

### Run with example data
```bash
python app.py chats.txt
```

### Run with test data
```bash
python app.py testing-chats.txt
```

### Run with a custom file
```bash
python app.py your-file.txt
```

## 📊 Output

The script processes the conversations and generates a structured JSON output including:

- **Sanitized conversation**: Personal information replaced with asterisks
- **Sentiment analysis**: Tone classification (positive, negative, neutral)
- **Profanities replaced**: With the 😤 emoji
- **Dates preserved**: To maintain temporal context

### Example output:
```json
{
  "conversation": "[Agent] 2023-07-15 : Hello! What can I help you with today?\n[Customer] 2023-07-15 : Hey, my promo code isn't applying the discount in my cart.",
  "sentiment": "neutral",
  "sanitized": "[Agent] 2023-07-15 : Hello! What can I help you with today?\n[Customer] 2023-07-15 : Hey, my promo code isn't applying the discount in my cart."
}
```

## 🔬 Prompt Engineering Log

The `prompt_tests_log.txt` file contains a detailed, step-by-step record of the prompt engineering process, including:

- **6 different prompt iterations**
- **Techniques applied**: Zero-shot, Few-shot, Delimiters, Chain-of-Thought
- **Results of each test** with success/failure analysis
- **Prompt evolution** from the basic implementation to the final optimized version

This log is especially valuable for:
- Understanding the iterative nature of prompt engineering
- Seeing how different techniques affect results
- Learning from mistakes and improvements
- Documenting the process for future reference and academic reproducibility

## 🛠️ Prompt Engineering Techniques Implemented

### 1. Zero-Shot Prompting
- Simple task description without examples
- Result: Poor performance

### 2. Few-Shot Prompting
- Added examples to the prompt
- Result: Significant improvement but inconsistent

### 3. Delimiters
- Used special markers to structure the prompt
- Result: Greater clarity and consistency

### 4. Numbered Instructions
- Broke down the task into explicit steps
- Result: Nearly perfect sanitization

### 5. Role Prompting
- Assigned specific roles to the model
- Result: Improved tone and consistency

### 6. Chain-of-Thought (CoT)
- Included reasoning steps in the examples
- Result: Perfect and consistent output

## 📁 Project Structure

```
├── app.py                    # Main script
├── settings.toml             # Final prompt configuration
├── settings-final.toml       # Original tutorial configuration
├── chats.txt                 # Example data
├── testing-chats.txt         # Test data
├── prompt_tests_log.txt      # Prompt engineering log
├── requirements.txt          # Dependencies
├── TUTORIAL.md               # Original Real Python tutorial
└── README.md                 # This file
```

## 🔧 Advanced Configuration

### Change OpenAI model
Edit `settings.toml` to change the model:
```toml
[api]
model = "gpt-3.5-turbo"  # or "gpt-4" for better results
```

### Adjust temperature
```toml
[api]
temperature = 0.0  # For more consistent responses
```

## 🧑‍🔬 Reproducibility
- All prompt versions, test data, and results are versioned and logged.
- For strict reproducibility, use the same Python and package versions as in `requirements.txt`.
- API responses may vary due to model updates or non-determinism in LLMs; set `temperature = 0.0` for maximum consistency.
- If using for research, consider archiving the exact prompt and output for each experiment.

## 📚 References & Further Reading
- [Original Real Python Tutorial](TUTORIAL.md)
- [OpenAI API Documentation](https://platform.openai.com/docs)
- [Prompt Engineering Guide](https://www.promptingguide.ai/)
- [Learn Prompting](https://learnprompting.org/)
- Wei, J., et al. (2022). "Chain-of-Thought Prompting Elicits Reasoning in Large Language Models." arXiv:2201.11903.
- Bommasani, R., et al. (2021). "On the Opportunities and Risks of Foundation Models." arXiv:2108.07258.

## 📏 Scope & Limitations
- This project is intended for educational and research purposes only.
- It is **not** a production-grade anonymization tool; outputs depend on LLM behavior and prompt quality.
- The approach is best suited for controlled experiments and prompt engineering studies.
- API costs and rate limits may apply when using OpenAI endpoints.

## 📝 Citing
If you use this repository or its methodology in your research, please cite as:

```
@misc{promptengineering2024,
  title={Prompt Engineering: A Practical Example},
  author={Your Name},
  year={2024},
  howpublished={\url{https://github.com/yourusername/yourrepo}}
}
```

## 🤝 Contributing

This project is for educational and research purposes. If you find any issues or have suggestions for improvement, feel free to open an issue or pull request.

## 📄 License

This project is licensed under the MIT License. See `LICENSE` for details.

---

**Note**: This project demonstrates the power of iterative prompt engineering. The `prompt_tests_log.txt` file is especially valuable as an example of how to systematically document and improve prompts. 