# Online-Payments-Fraud-Detection-using-ML
GuardAI: Online Payment Fraud Detection & AI Assistant

GuardAI is a hybrid financial security platform that integrates traditional Machine Learning for accurate fraud detection with Generative AI for intelligent user assistance.

By leveraging the CatBoost algorithm and a custom RAG (Retrieval-Augmented Generation) pipeline, GuardAI ensures both strong security and clear explainability for modern digital transactions.

🚀 Key Features
Real-time Fraud Detection: Instantly analyzes transactions using a CatBoost model optimized for high precision (Precision ≈ 1.00).
Advanced Feature Engineering: Computes “Balance Inaccuracy” (differences between transaction amounts and balance updates) to detect suspicious patterns.
Smart AI Assistant: A built-in chatbot powered by Google Gemini 2.0 Flash and Agno (Phidata), capable of answering user queries related to transaction fields and security alerts.
Vector-Based Knowledge Retrieval: Utilizes PostgreSQL with pgvector to store and fetch application-related documentation efficiently.
Modern User Interface: A clean and responsive dashboard developed using Flask and Bootstrap 5.
📂 Project Structure
├── app.py                      # Main Flask backend and routes
├── agent.py                    # AI agent and RAG pipeline setup
├── data_cleaning_training.py   # Model training and threshold tuning
├── knowledgebase.txt           # Knowledge base for the AI assistant
├── perfect_fraud_model.cbm     # Pre-trained CatBoost model
├── best_threshold.txt          # Optimal decision threshold
├── templates/                  # Frontend HTML files
│   ├── home.html
│   ├── predict.html
│   └── submit.html
└── requirements.txt            # Project dependencies
🛠️ Technical Stack
Backend: Python (Flask)
Machine Learning: CatBoost, Scikit-learn, Pandas, NumPy
Generative AI: Google Gemini 2.0 Flash, Agno Framework (Phidata)
Database: PostgreSQL with pgvector (Vector Database)
Frontend: Bootstrap 5, Animate.css
📊 Dataset

The model is trained on the Online Payments Fraud Detection Dataset from Kaggle.

Source: Kaggle Dataset Link
Size: ~6.3 million rows
(Note: dataset.csv is not included in this repository due to its size. Please download it manually for training.)
⚙️ Installation & Setup
1. Clone the Repository
git clone https://github.com/bhagwatankita/GuardAI-OnlinePaymentFraud-Detection.git
cd GuardAI-OnlinePaymentFraud-Detection
2. Create a Virtual Environment (Recommended)
python -m venv venv

# Windows
venv\Scripts\activate

# Mac/Linux
source venv/bin/activate
3. Install Dependencies
pip install -r requirements.txt
4. Database Configuration

Make sure PostgreSQL is installed with the pgvector extension enabled.

Create a database named: OnlinePaymentFraudAgentDB
Update the database URL in agent.py:
db_url = "postgresql+psycopg://user:password@localhost:5432/OnlinePaymentFraudAgentDB"
5. Set Environment Variables

You will need a Google AI API key for the chatbot functionality.

os.environ["GOOGLE_API_KEY"] = "YOUR_API_KEY_HERE"
🚀 Running the Application
Train the Model (Optional)
python data_cleaning_training.py
Start the Application
python app.py

Then open your browser and go to:

👉 http://127.0.0.1:5000/
