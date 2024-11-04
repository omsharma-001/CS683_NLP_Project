# Automated Customer Issue Categorization and Resolution System

### Overview
This project is designed to build an **Automated System** that assists customers in resolving simple, recurring issues without the need for human intervention. The system automatically categorizes customer inquiries into predefined categories and instantly provides appropriate solutions, helping customers resolve their problems independently and efficiently.

### **Problem Statement**
Customers often encounter simple, recurring issues that could be resolved without manual support. However, current processes require human intervention, leading to unnecessary delays and higher resource utilization. This project aims to automate the process of resolving common customer queries by:
- Categorizing customer issues into predefined categories
- Providing automated solutions based on the categorized issue
- Reducing dependency on human support for frequently occurring problems

### **Project Objectives**
- Develop a Natural Language Processing (NLP)-based solution that can **automatically classify customer queries** into relevant issue categories.
- Provide **instant automated responses** with solutions, based on the identified category.
- Enable **self-service** for customers, reducing the burden on customer support teams and improving response times.

### **Key Features**
- **Customer Query Categorization**: Automatically identifies the category of a customer query (e.g., account issues, transactions, loans, credit card issues).
- **Automated Response Generation**: Instantly provides customers with the right solution based on the categorized issue.
- **Support for Multiple Themes**: The system is flexible enough to handle various themes like:
  - Account Issues
  - Transactions
  - Credit/Debit Cards
  - Loans
  - Online Banking, and more.
  
### **Sample Use Case**
A customer asks: **"How do I change my address in my account?"**  
The system recognizes that this question relates to **personal information updates** and provides an automated response detailing the steps the customer needs to follow to update their address.

### **Data Collection**
To train the system, we are working with sample **FAQ data** representing common banking queries. Here are a few categories:
- **Account Issues**: Queries related to account opening, closing, or personal information updates.
- **Transactions**: Questions about transfers, withdrawals, and transaction limits.
- **Loans**: Queries on loan applications, repayments, interest rates, etc.
- **Credit/Debit Cards**: Issues related to card activation, blocking, and limits.
- **Online Banking**: Problems with online banking platforms, passwords, and login issues.

### **Data Preparation**
1. **FAQ Dataset**: A list of commonly asked questions and predefined categories. (See `data/faq_data.csv` for sample queries).
2. **Query Variations**: Each predefined question comes with multiple possible phrasings to train the model effectively.

### **Model Workflow**

#### Data Preprocessing: The input text is cleaned by removing punctuation, converting to lowercase, and eliminating numbers. This prepares the text for vectorization.
#### Text Vectorization: The text is transformed into numerical sequences using a TextVectorization layer, which converts words into integers based on a fixed vocabulary size.
#### Embedding Layer: The numerical sequences are passed through an embedding layer, which maps each integer to a dense vector representation, capturing semantic meanings.
#### LSTM Layer: The embedding output is fed into an LSTM layer, which processes the sequences to learn contextual information over time.
#### Dense Layers: The LSTM output is then passed through fully connected (Dense) layers to extract features and make predictions.
#### Output Layer: A final Dense layer with a softmax activation outputs probabilities for each category. The highest probability indicates the predicted category.
#### API Workflow: The FastAPI app processes incoming text queries, cleans them, converts them to tensors, and uses the trained model to predict the category, returning the result.

### **Contributing**
Feel free to contribute to this project by opening an issue or submitting a pull request.

