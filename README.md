🧠 Multi-Agent Fake Product Review Detection System

This project implements a multi-agent review validation system using LangGraph and Google Gemini (Generative AI) to analyze and decide whether a product review should be approved or rejected.
The system evaluates reviews from multiple perspectives (credibility, authenticity, and purchase verification) and then makes a final decision using a dedicated decision agent.



🚀 Features

1) Multi-Agent Architecture using LangGraph

2) Parallel analysis (fan-out) and final aggregation (fan-in)

3) Uses Google Gemini Flash model

4) Structured input via text file

5) Final decision with confidence score and action


🧩 Agents Overview

1) Reviewer Credibility Agent
   Analyzes reviewer information (history, tone, trustworthiness)

2) Content Authenticity Agent
   Checks review text for spam, exaggeration, or fake patterns

3) Purchase Verification Agent
   Verifies whether the reviewer likely purchased the product

4) Final Decision Agent
   Aggregates all agent outputs and produces the final verdict
   

🗂️ Project Structure

├── main.py            # LangGraph workflow and execution

├── agents.py          # All agent definitions

├── prompts.py         # Prompt templates for agents

├── input.txt          # Review input file

├── .env               # API keys (not committed)

├── requirements.txt

└── README.md


📝 Input Format (input.txt)

[REVIEWER_INFO]  
 User has written 50 reviews with mostly positive feedback.

[REVIEW_TEXT]
 This product exceeded my expectations. Highly recommended!

[PURCHASE_INFO]
 Order ID available. Purchase verified.
 

⚙️ Installation & Setup

1️⃣ Clone the Repository
    git clone https://github.com/your-username/multi-agent-review-validator.git
    cd multi-agent-review-validator

2️⃣ Create Virtual Environment (Optional)
    python -m venv venv
    source venv/bin/activate   # Windows: venv\Scripts\activate

3️⃣ Install Dependencies
    pip install -r requirements.txt

4️⃣ Set Environment Variables
    Create a .env file:
    GOOGLE_API_KEY=your_google_api_key_here

▶️ Running the Project
    python main.py
    

✅ Sample Output

{
  "final_decision": "APPROVE",
  
  "confidence": 97,
  
  "action": "Allow review, may boost ranking"
  
}


🧠 Tech Stack

Python

LangGraph

LangChain

Google Gemini (ChatGoogleGenerativeAI)

dotenv
