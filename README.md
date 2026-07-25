# 🧠 MedScanAI

A full-stack AI healthcare assistant powered by ⚛️ React (frontend), 📓 Jupyter Notebook (ML modeling), and ☁️ AWS (Lambda, S3, Bedrock, Lex, Textract). Users can input symptoms, upload PDFs, or chat for AI-driven medical insights.

## 🚀 Features
- AI diagnosis via Claude on Bedrock
- Symptom form and chatbot (Lex)
- PDF upload + Textract OCR
- React frontend hosted on S3

## ⚙️ Setup

### 1. Clone & Install
```bash
git clone https://github.com/yourusername/medscanai.git
cd medscanai/frontend
npm install
npm run dev
```
### 2. Backend Setup

cd ../backend
```bash
python -m venv venv
source venv/bin/activate  # Windows: venv\Scripts\activate
pip install -r requirements.txt
zip -r function.zip .
aws lambda update-function-code --function-name MedScanHandler --zip-file fileb://function.zip
```

### 3. Jupyter Setup
```bash
cd ../notebooks
pip install -r requirements.txt
jupyter notebook
```

### 4. AWS Services
S3: store PDFs, trigger Lambda

Textract: extract text from uploads

Bedrock: generate diagnosis from symptoms

Lex: chatbot integrated into site

#### Sample Prompt
You are a clinical AI assistant. Given a patient case, output:
Condition: ..., Symptoms: ..., Plan: ..., Recovery: ...

### 5. Deploy Frontend to S3
npm run build
aws s3 cp dist/ s3://your-bucket-name/ --recursive


