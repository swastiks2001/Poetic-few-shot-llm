# 🎭 Poetic Chatbot Project

## 📖 About the Project

This project demonstrates the creation of a **Poetic Chatbot** utilizing **Large Language Models (LLMs)**. Unlike standard AI assistants that provide direct factual answers, this chatbot is engineered to respond in **rhythmic, rhyming verse**.

The project showcases the power of **Few-Shot Prompting**, where the model is taught a specific persona and response style through a series of examples within the conversation context.

---

# 📌 Overview

The notebook is structured to take the user through the complete lifecycle of an AI application.

### Key Components

- **Dependency Management:** Loading the required OpenAI and OS libraries.
- **Security & Configuration:** Safely handling API credentials using environment variables.
- **Prompt Engineering:** Designing a System Message and Few-Shot examples to guide the chatbot's poetic responses.
- **Execution & Analysis:** Generating responses and observing the model's behavior.

---

# 📚 Summary

The system effectively bridges the gap between **factual retrieval** and **creative writing**. By setting the **temperature** parameter to **1**, the chatbot produces expressive and imaginative poetic responses.

This project demonstrates how **System Prompts** and **Few-Shot Prompting** can dramatically influence the personality and creativity of a Large Language Model.

---

# 🎯 Conclusion

The Poetic Chatbot successfully transforms historical and general knowledge into engaging poetry.

Future enhancements may include:

- 💬 Adding conversation memory for multi-turn interactions.
- 🤖 Supporting multiple LLMs for comparison.
- 🎨 Allowing different poetic styles such as Haiku, Sonnet, or Free Verse.
- 🌐 Deploying the chatbot as a web application.

---

# 🔄 Project Workflow

```text
+------------------------------------------+
|          START: Initialize System        |
+------------------------------------------+
                    |
                    v
+------------------------------------------+
|  Cell 1 & 2: Load Libraries & API Keys   |
|  (Import openai, os / Set Environment)   |
+------------------------------------------+
                    |
                    v
+------------------------------------------+
|  Cell 3 & 4: Configure Client            |
|  (Retrieve Key & Initialize OpenAI)      |
+------------------------------------------+
                    |
                    v
+------------------------------------------+
|  Cell 5: Define Poetic Logic             |
|  - Set System Persona                    |
|  - Inject Few-Shot Examples              |
|  - Configure Creativity (Temperature)    |
+------------------------------------------+
                    |
                    v
+------------------------------------------+
|  Cell 6: User Input & Processing         |
|  (Example: "When was cheese first made?")|
+------------------------------------------+
                    |
                    v
+------------------------------------------+
|        OUTPUT: Poetic Response           |
+------------------------------------------+
                    |
                    v
+------------------------------------------+
|           END: Process Complete          |
+------------------------------------------+
```

---

# 📒 Notebook Cells & Explanation

## Cell 1: Importing Libraries

### Code

```python
from openai import OpenAI
import os
```

### Explanation

This cell imports the required Python libraries.

- **OpenAI** enables communication with the language model.
- **os** manages environment variables securely.

---

## Cell 2: Environment Setup

### Code

```python
import os

os.environ["your_llm_key"] = "your_api_key"
```

### Explanation

The API key is stored as an environment variable instead of being hardcoded, improving security.

---

## Cell 3: API Key Retrieval

### Code

```python
api_key = os.getenv("your_llm_key")
```

### Explanation

Retrieves the API key from the operating system's environment variables.

---

## Cell 4: Client Initialization

### Code

```python
client = OpenAI(
    base_url="your_llm_key_url",
    api_key=api_key
)
```

### Explanation

Creates the OpenAI client that communicates with the selected LLM.

---

## Cell 5: The Poetic Chatbot Function

### Code

```python
def poetic_chatbot(prompt):
    response = client.chat.completions.create(
        model="your-llm-model",
        messages=[
            {
                "role": "system",
                "content": "You are a poetic chatbot."
            },
            {
                "role": "user",
                "content": "When was Google founded?"
            },
            {
                "role": "assistant",
                "content": "In the late '90s, a spark did ignite, Google emerged, a radiant light. By Larry and Sergey, in '98, it was born, a search engine new, on the web it was sworn."
            },
            {
                "role": "user",
                "content": "Which country has the youngest president?"
            },
            {
                "role": "assistant",
                "content": "Ah, the pursuit of youth in politics, a theme we explore. In Austria, Sebastian Kurz did implore, at the age of 31, his journey did begin, leading with vigor, in a world filled with din."
            },
            {
                "role": "user",
                "content": prompt
            }
        ],
        temperature=1,
        max_tokens=256
    )

    return response.choices[0].message.content.strip()
```

### Explanation

This function contains the core chatbot logic.

- Defines the chatbot's persona using a **System Message**.
- Uses **Few-Shot Prompting** to teach the chatbot how to generate poetic responses.
- Sets **temperature = 1** to encourage creativity.
- Limits responses to **256 tokens**.

---

## Cell 6: Testing the Chatbot

### Code

```python
prompt = "When was cheese first made?"

poetic_chatbot(prompt)
```

### Explanation

A sample question is sent to the chatbot. The model interprets the factual query and transforms it into a poetic response.

---

# 💡 Expected Output

> **User Question**

```
When was cheese first made?
```

> **Example Response**

```
Cheese has roots in ages old,
A story ancient, brave and bold.
From Poland's pots the traces came,
A timeless craft, a lasting name.
Though history's pages leave some doubt,
Its savory tale still rings throughout.
```

---

# 🛠 Technologies Used

- Python
- OpenAI Python SDK
- Large Language Models (LLMs)
- Few-Shot Prompting
- Prompt Engineering
- Environment Variables

---

# 🚀 Future Enhancements

- Add conversation memory.
- Support multiple LLM providers.
- Enable different poetry styles.
- Build a Streamlit or Flask web interface.
- Deploy on cloud platforms.

---

## 👨‍💻 Author

**Swastik Samal**

Artificial Intelligence & Machine Learning Enthusiast
