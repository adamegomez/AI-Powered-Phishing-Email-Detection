# 🧠 AI-Powered Phishing Email Detection

This project explores how Artificial Intelligence (AI) is used to detect phishing emails, especially job scam phishing attempts. I walk through real-world phishing scenarios, explain how AI technologies like Machine Learning (ML) and Natural Language Processing (NLP) are used for detection, and demonstrate how to train a simple phishing detection model using a public dataset.

---

## 🎯 Phishing Email Focus: Job Scams

Job scam phishing emails are increasingly common. These emails often:

- Pretend to come from legitimate recruiters
- Use urgent language like "Act now!" or "Immediate hiring!"
- Ask for sensitive information (SSNs, bank accounts)
- Contain suspicious links or malware-infected attachments

📊 According to reports, ~30% of phishing emails now target job seekers.

---

## 🤖 How AI Detects Phishing Emails

AI systems use a combination of machine learning and NLP to:

- Identify red flag phrases (e.g., "verify your identity", "urgent")
- Detect poor grammar or generic greetings like "Dear user"
- Analyze URLs for spoofed domains or malicious patterns
- Make **real-time predictions** before the user even opens the email

Most importantly, AI models **learn from large datasets** and **evolve** with new threats.

---

## 🧪 Demonstration: Training an AI Model to Detect Phishing Emails

This section shows how we trained a machine learning model to detect phishing using Python and a dataset of 82,000 emails from Kaggle.

### ✅ Step 1: Download the Dataset

- Source: [Kaggle Email Dataset (CSV)](https://kaggle.com) – contains phishing and legitimate emails
- Save it as `archive(1).zip` and place it in your `Documents` folder

### ✅ Step 2: Navigate to the Dataset Location

```bash
cd Documents

```

## ✅ Step 3: Unzip the File
``` bash
Copy
Edit
unzip archive\(1\).zip
This extracts the dataset into your working directory.

```

## ✅ Step 4: Create a Python Script Using Nano

``` bash
Copy
Edit
nano phishing_script.py
Paste the following code into the file (example outline — your actual script may vary):

python
Copy
Edit
import pandas as pd
from sklearn.model_selection import train_test_split
from sklearn.feature_extraction.text import CountVectorizer
from sklearn.naive_bayes import MultinomialNB

# Load the dataset
data = pd.read_csv("phishing_emails.csv")

# Vectorize email content
vectorizer = CountVectorizer()
X = vectorizer.fit_transform(data["email_text"])
y = data["label"]

# Train/Test Split
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2)

# Train model
model = MultinomialNB()
model.fit(X_train, y_train)

# Custom email for testing
test_email = ["You've won a free car! Just send us your SSN to claim."]
test_vect = vectorizer.transform(test_email)
print("Prediction:", model.predict(test_vect))
Save and exit with CTRL+O, ENTER, then CTRL+X.

```

## ✅ Step 5: Run the Script

``` bash
Copy
Edit
python3 phishing_script.py

```
🎯 Result: The AI model correctly detects that the email is a phishing attempt.


## 🔁 Optional Step 6: Try a Normal Email
Edit the test email to something more legitimate:

``` 
python
Copy
Edit
test_email = ["Your meeting is scheduled for 3 PM today. Please confirm attendance."]
Then re-run the script:
```

``` bash
Copy
Edit
python3 phishing_script.py

``` 
## ✅ Result: The model identifies it as a non-phishing (normal) email.

## 🛡️ How to Protect Against Phishing Emails
✅ Be cautious with links & attachments

✅ Check sender addresses for slight variations

✅ Watch for red flags like urgency or typos

✅ Enable two-factor authentication (2FA)

✅ Use anti-phishing tools and email filters

✅ Educate yourself and others

✅ Report suspicious emails

## 📌 Conclusion
Phishing emails — especially job scams — continue to grow in volume and complexity. AI helps us fight back by analyzing language patterns, URLs, and behavior in real time. While technology plays a key role, user awareness and education remain essential. By combining machine intelligence with smart practices, we can greatly reduce the risk of successful phishing attacks.
