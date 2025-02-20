# Python Automation CheatSheet 🚀

This cheat sheet provides a quick reference for automating tasks using Python. Covering **file handling, web scraping, system automation, and scheduling**, it serves as a go-to resource for streamlining workflows.

---

## 🔥 **1. File & Directory Handling**

### 📂 **List all files in a directory**
```python
import os
files = os.listdir("/path/to/directory")
print(files)
```

### 📝 **Read & Write files**
```python
# Read a file
with open("file.txt", "r") as f:
    content = f.read()

# Write to a file
with open("file.txt", "w") as f:
    f.write("Hello, Automation!")
```

### 🚀 **Move, Rename & Delete files**
```python
import shutil
import os

os.rename("old.txt", "new.txt")  # Rename file
shutil.move("file.txt", "new_folder/")  # Move file
os.remove("file.txt")  # Delete file
```

### 📁 **Create & Delete Directories**
```python
os.mkdir("new_folder")  # Create a new folder
shutil.rmtree("folder_to_delete")  # Delete a folder and its contents
```

---

## 🌐 **2. Web Scraping & API Automation**

### 🕷 **Scraping a webpage**
```python
import requests
from bs4 import BeautifulSoup

url = "https://example.com"
response = requests.get(url)
soup = BeautifulSoup(response.text, "html.parser")
print(soup.title.text)  # Get page title
```

### 📡 **Calling an API**
```python
import requests

url = "https://api.example.com/data"
response = requests.get(url)
print(response.json())  # Print JSON response
```

---

## 🖥 **3. System & Task Automation**

### ⏳ **Automate Tasks with Scheduling**
```python
import schedule
import time

def job():
    print("Running scheduled task!")

schedule.every(10).seconds.do(job)

while True:
    schedule.run_pending()
    time.sleep(1)
```

### 🖱 **Simulating Mouse & Keyboard Actions**
```python
import pyautogui

pyautogui.click(100, 200)  # Click at (x, y) position
pyautogui.write("Hello, World!")  # Type text
pyautogui.press("enter")  # Press Enter key
```

---

## 📧 **4. Sending Automated Emails**
```python
import smtplib
from email.mime.text import MIMEText

smtp_server = "smtp.gmail.com"
smtp_port = 587
username = "your_email@gmail.com"
password = "your_password"

def send_email(to, subject, body):
    msg = MIMEText(body)
    msg["Subject"] = subject
    msg["From"] = username
    msg["To"] = to

    with smtplib.SMTP(smtp_server, smtp_port) as server:
        server.starttls()
        server.login(username, password)
        server.sendmail(username, to, msg.as_string())

send_email("recipient@example.com", "Hello!", "This is an automated email.")
```

---

## 📝 **5. Reading & Writing Excel Files**
```python
import pandas as pd

data = pd.read_excel("data.xlsx")  # Read Excel file
data.to_csv("data.csv", index=False)  # Convert to CSV
```

---

## 🚀 **6. Running External Commands**
```python
import subprocess
subprocess.run(["echo", "Hello, World!"])
```

---

## 🎯 **Final Thoughts**
This cheat sheet covers **essential automation techniques** to help you **work smarter, not harder**! 🚀
For more, explore libraries like **Selenium, OpenCV, and Paramiko** to expand your automation toolkit!

---
**Created by:** [yung-megafone](https://github.com/yung-megafone)