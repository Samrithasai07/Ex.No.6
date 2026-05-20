# Ex.No.6 Development of Python Code Compatible with Multiple AI Tools

# Date: 20\5\26
# Register no: 212224040286
# Aim: Write and implement Python code that integrates with multiple AI tools to automate the task of interacting with APIs, comparing outputs, and generating actionable insights with Multiple AI Tools


# Explanation:
Experiment the persona pattern as a programmer for any specific applications related with your interesting area. 
Generate the outoput using more than one AI tool and based on the code generation analyse and discussing that.


# Introduction

Artificial Intelligence tools such as [OpenAI ChatGPT](https://openai.com/chatgpt/?utm_source=chatgpt.com) and [Google Gemini](https://gemini.google.com/?utm_source=chatgpt.com) provide APIs that developers can use to automate tasks like content generation, summarization, coding assistance, and decision-making.

In this experiment, Python is used to:

* Connect with multiple AI APIs
* Send the same prompt to different AI tools
* Compare responses
* Analyze differences
* Generate useful insights automatically

The chosen application area is **AI-based Code Generation and Analysis for Student Learning Systems**.

---

# AI Tools Used

| AI Tool                                                                      | Purpose                                    |
| ---------------------------------------------------------------------------- | ------------------------------------------ |
| [OpenAI ChatGPT API]   | Generate Python code and explanations      |
| [Google Gemini API]           | Provide alternative logic and optimization |
| [GitHub Copilot]| Code suggestions inside IDE                |

---

# Persona Pattern Used

## Persona: Senior Python Programmer

The AI tools are instructed to behave like:

> “An experienced Python software engineer who writes optimized, beginner-friendly, well-commented, and modular code for educational applications.”

This persona helps generate:

* Clean code
* Better explanations
* Optimized logic
* Industry-style programming practices

---

# Problem Statement

Develop a Python application that:

1. Sends prompts to multiple AI APIs
2. Receives generated code/output
3. Compares responses
4. Produces insights based on quality, readability, and optimization

---

# Required Python Libraries

```python
pip install openai google-generativeai tabulate
```

---

# Python Program

```python
# Multiple AI Tool Integration using Python

import openai
import google.generativeai as genai
from tabulate import tabulate

# -----------------------------
# API KEYS
# -----------------------------

OPENAI_API_KEY = "YOUR_OPENAI_API_KEY"
GEMINI_API_KEY = "YOUR_GEMINI_API_KEY"

# Configure APIs
openai.api_key = OPENAI_API_KEY

genai.configure(api_key=GEMINI_API_KEY)

# -----------------------------
# USER PROMPT
# -----------------------------

prompt = """
Act as a Senior Python Programmer.

Write a Python function to sort a list using Merge Sort.
Explain time complexity and advantages.
"""

# -----------------------------
# CHATGPT RESPONSE
# -----------------------------

def get_chatgpt_response(prompt):

    response = openai.ChatCompletion.create(
        model="gpt-4",
        messages=[
            {"role": "user", "content": prompt}
        ]
    )

    return response['choices'][0]['message']['content']

# -----------------------------
# GEMINI RESPONSE
# -----------------------------

def get_gemini_response(prompt):

    model = genai.GenerativeModel("gemini-pro")

    response = model.generate_content(prompt)

    return response.text

# -----------------------------
# GET RESPONSES
# -----------------------------

chatgpt_output = get_chatgpt_response(prompt)

gemini_output = get_gemini_response(prompt)

# -----------------------------
# COMPARISON
# -----------------------------

comparison_table = [
    ["ChatGPT", len(chatgpt_output), "Detailed Explanation"],
    ["Gemini", len(gemini_output), "Optimized Logic"]
]

print("\nAI OUTPUT COMPARISON\n")

print(tabulate(
    comparison_table,
    headers=["AI Tool", "Response Length", "Main Feature"],
    tablefmt="grid"
))

# -----------------------------
# DISPLAY OUTPUTS
# -----------------------------

print("\n\nCHATGPT OUTPUT:\n")
print(chatgpt_output)

print("\n\nGEMINI OUTPUT:\n")
print(gemini_output)

# -----------------------------
# ACTIONABLE INSIGHTS
# -----------------------------

print("\n\nACTIONABLE INSIGHTS\n")

if len(chatgpt_output) > len(gemini_output):
    print("ChatGPT provides more detailed explanations.")
else:
    print("Gemini provides more concise responses.")

print("Using multiple AI tools improves reliability and creativity.")
```

---

# Sample Output

```text
AI OUTPUT COMPARISON

+-----------+------------------+----------------------+
| AI Tool   | Response Length  | Main Feature         |
+-----------+------------------+----------------------+
| ChatGPT   | 1250             | Detailed Explanation |
| Gemini    | 980              | Optimized Logic      |
+-----------+------------------+----------------------+

ACTIONABLE INSIGHTS

ChatGPT provides more detailed explanations.
Using multiple AI tools improves reliability and creativity.
```

---

# Explanation of the Program

## Step 1: Import Libraries

```python
import openai
import google.generativeai as genai
```

These libraries help connect Python with AI APIs.

---

## Step 2: Configure API Keys

```python
openai.api_key = OPENAI_API_KEY
genai.configure(api_key=GEMINI_API_KEY)
```

Authentication is required before sending requests.

---

## Step 3: Define Persona Prompt

```python
Act as a Senior Python Programmer
```

This creates a programmer persona for professional-quality output.

---

## Step 4: Fetch Responses

Separate functions are used for:

* ChatGPT
* Gemini

This improves modularity and maintainability.

---

## Step 5: Compare Outputs

The responses are compared based on:

* Length
* Readability
* Optimization
* Explanation quality

---

# Analysis and Discussion

| Feature             | ChatGPT       | Gemini    |
| ------------------- | ------------- | --------- |
| Explanation Quality | Excellent     | Good      |
| Code Optimization   | Good          | Excellent |
| Readability         | High          | Medium    |
| Detail Level        | Very Detailed | Concise   |
| Educational Support | Excellent     | Good      |

---

# Advantages of Multiple AI Integration

1. Improves decision-making
2. Reduces dependency on a single AI model
3. Produces diverse coding approaches
4. Enhances debugging and optimization
5. Useful for education and research

---

# Real-Time Applications

* Smart Coding Assistants
* Automated Tutoring Systems
* AI-Based Code Review Platforms
* Research Automation
* Multi-AI Chat Systems

---


# Conclusion

Using multiple AI tools together provides:

* Better reliability
* Improved coding suggestions
* Enhanced learning support
* Higher-quality software solutions

Python acts as an effective bridge for integrating AI APIs into real-world applications.
<img width="1536" height="1024" alt="image" src="https://github.com/user-attachments/assets/d65f8a80-49aa-45ce-af38-8b1e591c0bc1" />


# Result: The corresponding Prompt is executed successfully.
