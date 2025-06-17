# CodeVerse Genie 🧞‍♂️✨  
**An AI-driven coding assistant integrated into the [CodeVerse]([https://github.com/Lavanyalakhiani/codeverse]) platform.**  

CodeVerse Genie is a Python-based Flask API that leverages advanced Large Language Models (LLMs) to provide coding assistance within the Codehive collaborative platform. It specializes in generating, debugging, and optimizing code, designed to empower developers with seamless and accurate coding support.

---

## ✨ Features  

### 🌟 Core Capabilities  
- 🚀 **Code Assistance**: Generate, debug, and optimize code snippets.  
- 🌐 **Supported Languages**: Python, C, JavaScript, Java, TypeScript, and C++ (CPP).  
- 🔧 **High-Quality Output**: Delivers well-structured, production-ready code with inline comments and concise explanations.  
- 🌀 **Streaming Responses**: Enables real-time responses to ensure minimal latency.  
- ❌ **Strict Query Handling**: Ignores non-coding-related queries with polite and concise error messages.  

### 🔒 Security Enhancements  
- 🌍 **Language Detection**: Ensures input is in English for consistency and accuracy.  
- 🛡️ **Authentication**: API access secured with an `Authorization` header.  
- 📜 **Robust Logging**: Detailed query and response logging for improved monitoring and debugging.  

### 🌐 Deployment  
- 🖥️ **Hosted on Vercel**: Optimized deployment using Vercel's Flask template for high performance and scalability.  

---

## 💻 Tech Stack  

### Backend  
- 🐍 **Flask**: Lightweight and efficient framework for API development.  
- 🤖 **Groq AI Cloud**: LLM parameterization using **Llama 3.3-70B Versatile**.  
- 📚 **Python Libraries**:  
  - 🔄 `flask-cors`: To handle cross-origin requests.  
  - 🔐 `dotenv`: For secure environment variable management.  
  - 🧩 `langdetect`: For detecting input language.  


## 🌐 API Overview  

### 📜 Endpoints  

#### 1. **Home Endpoint**  
- **GET** `/`  
- **Description**: Basic health check for the server.  
- **Response**:  
```text  
Hello, World!  
```  

#### 2. **CodeVerse Genie Endpoint**  
- **POST** `/genie`  
- **Description**: Processes user queries to provide AI-generated coding assistance.  

- **Headers**:  
  - 🔐 `Authorization`: The authorization secret key for secure access.  

- **Request Body**:  
  ```json  
  {
    "query": "Write a Python function to reverse a string."
  }  
  ```  

- **Response**:  
  - ✅ **For Valid Queries** (Streamed Response):  
    ```plaintext  
    def reverse_string(s):  
        # Return the string in reverse order  
        return s[::-1]
    ```  

  - 🚫 **For Invalid Queries**:  
    ```json  
    {
      "error": "Invalid authorization secret."
    }
    ```  

  - ⚠️ **For Non-Coding Queries**:  
    ```plaintext  
    Sorry, I am an AI assistant tuned for coding and programming purposes only. I cannot assist with this query.  
    ```  

---
