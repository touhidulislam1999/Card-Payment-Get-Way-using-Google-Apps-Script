# 💳 Google Apps Script Payment Gateway

This project implements a **simple card payment system** using **Google Apps Script**. The system performs **card validation, OTP authentication, and captcha verification** to simulate a **secure** payment process.

## 📊 Flowchart
![Flowchart](https://github.com/user-attachments/assets/53f3db85-be98-4c7d-bc6b-633dcddfb573)


---
## 🚀 Features
- **Card Validation**: Validates card details before processing the transaction.
- **OTP Authentication**: Sends a one-time password (OTP) via email.
- **Captcha Verification**: Prevents automated submissions using simple math-based captcha.
- **Google Spreadsheet Integration**: Maintains card balances.
- **Email Notifications**: Sends receipts and OTPs via email.

---
### 📂 Project Structure

```bash
📦 Google-Apps-Script-Payment-Gateway
│-- 📄 README.md  # Project documentation
│-- 📂 scripts    # Google Apps Script files
│   │-- 🏁 Starting Code.gs            # Handles the main workflow
│   │-- 🔢 Generate OTP.gs             # Generates OTP codes
│   │-- 📤 Send OTP.gs                 # Sends OTP via email
│   │-- 🔢 Generate Captcha.gs         # Creates a captcha for security
│   │-- ✅ Validate Captcha.gs         # Validates user-entered captcha
│   │-- 🔍 Verify OTP.gs               # Verifies OTP entered by the user
│   │-- 💰 Balance.gs                  # Checks and updates balance
│   │-- 💳 Card Class.gs               # Card verification class
│   │-- 📄 Receipt.gs                  # Generates and sends transaction receipts
│   │-- 📥 Input Class.gs              # Return an object containing the user's input details
│   │-- ✉️ Mail.gs                     # Uses Google Apps Script MailApp service to send an email
│   │-- 💳 Saved Cards.gs              # Create saved card users class
│   │-- 🔍 Verify Card Details.gs      # Verifies if the entered card details match any saved cards.
│-- 📂 frontend   # Frontend interface
│   │-- 🌍 Front Page.html             # Payment form (HTML & JS)
│-- 📂 assets     # Additional assets (if needed)
│-- 📂 docs       # Documentation and flowcharts (if needed)
```
---
## 📂 File Breakdown

### 🏁 `Starting Code.gs`
- Handles **HTTP GET requests** to serve the front-end.
- Calls `paynow()` to process payments.
- Verifies card details and sends OTP via `send_OTP()`.

### 🔢 `Generate OTP.gs`
- Generates a **4-digit OTP** randomly.
- Defines a `Send_Mail()` function to send the OTP via email.
- Includes `SavedCards()` to store sample card details.
- Implements `Verify_Card()` to check if card details exist.

### 📤 `Send OTP.gs`
- Calls `generate_OTP()` to create an OTP.
- Constructs an **email template** with the OTP and sends it.
- Stores the OTP in `UserProperties` for later validation.

### 🔢 `Generate Captcha.gs`
- Creates a simple **math-based captcha** (addition, subtraction, multiplication).
- Stores captcha details using `UserProperties`.

### ✅ `Validate Captcha.gs`
- Retrieves stored captcha values.
- Validates user-entered answers.

### 🔍 `Verify OTP.gs`
- Compares the **entered OTP** with the stored OTP.
- Deducts balance **only if OTP is correct**.
- Sends a **transaction confirmation email**.

### 💰 `Balance.gs`
- Maintains and verifies **account balances** using a **Google Spreadsheet**.
- Deducts the amount if sufficient balance exists.

### 💳 `Card Class.gs`
- Defines a `CardClass` that handles **card information**.
- Includes `verifyUser()` to match user details with stored data.

### 📄 `Receipt.gs`
- Generates a **transaction receipt** in **HTML format**.
- Masks card details for security.
- Sends an email notification after a successful transaction.

### 🌍 `Front Page.html`
- Implements a **responsive payment form**.
- Uses **Google Apps Script** to interact with backend functions.
- Supports **CAPTCHA and OTP validation**.
- Includes **SweetAlert2 pop-ups** for better user interaction.

---

## 🛠 How It Works
1. **User fills in card details.**
2. **Captcha verification** ensures human interaction.
3. **Card details are validated.**
4. **OTP is sent** to the registered email.
5. **User enters the OTP** for verification.
6. **Balance is checked** and the **amount is deducted**.
7. **A receipt is sent** to the user’s email.

---
## 🎥 Demo
![Initial Page](https://github.com/user-attachments/assets/ad1e7593-ab91-4477-bf98-4b2b1a71428f)
![Submiting Info](https://github.com/user-attachments/assets/9220206c-5206-48f2-86b7-d3bcef6abb24)
![Payment Button Enables after submitting Captcha](https://github.com/user-attachments/assets/1ff24708-bd72-4aeb-9e50-c9e70f577fa1)
![Verifying Card Details](https://github.com/user-attachments/assets/181f735c-d04a-45e0-90ac-62a3eda920d7)
![Popup Box](https://github.com/user-attachments/assets/77ac683f-bf76-4d31-81ca-fe0ca1a33a55)
![Invalid Captcha](https://github.com/user-attachments/assets/02065d81-4646-4e3b-9282-488151f52ec7)
![OTP Mail](https://github.com/user-attachments/assets/571e9c28-437a-49a0-9f6f-329127a9d778)
![Invalid OTP](https://github.com/user-attachments/assets/a1779e1b-9253-4470-9ec8-fbde3cf59c70)
![Resend OTP](https://github.com/user-attachments/assets/e4339391-b23b-46a5-8b64-18b3d058077c)
![New OTP Send](https://github.com/user-attachments/assets/ada84268-3e2c-4060-9fcf-098791e459a2)
![Payment Successful!](https://github.com/user-attachments/assets/8d60e93a-144b-4f75-b6c0-37b73fc948fc)
![Payment Receipt](https://github.com/user-attachments/assets/1685389d-ad41-4622-9fb9-0941464afee4)

---

## ⚡ Dependencies
- **Google Apps Script**
- **Google Sheets** (for balance storage)
- **Google MailApp** (for sending OTP and receipts)
- **SweetAlert2** (for UI pop-ups)

---

## 📌 Future Improvements
- Implement **secure encryption** for stored card details.
- Integrate **third-party payment gateways**.
- Use **Google OAuth** for better security.
- Add a **QR Code-based OTP system**.

---

## 📧 Contact
**Developer:** [Md Touhidul Islam]  
**Email:** [touhidulsislam@iut-dhaka.edu]  
**GitHub:** [https://github.com/touhidulislam1999]

---

## 🔧 Setup & Installation
### Step 1: Clone the Repository
```bash
 git clone https://github.com/touhidulislam1999/Card-Payment-Get-Way-using-Google-Apps-Script.git
```
### 🎯 **Feel free to contribute, suggest improvements, and star ⭐ this repository!**
