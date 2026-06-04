# BankManagementSystem
🏦 NovaBanK — Bank Management System
A secure, console-based Java banking application with PIN authentication, fund transfers, and persistent file storage.
Built by: Ashutosh Sahani
Language: Java (JDK 11+)Type: Console Application
Features
	•	🔐 Secure PIN Authentication — salted SHA-256 hashing (no plaintext storage)
	•	👤 Account Management — create Savings or Current accounts
	•	💰 Transactions — Deposit, Withdraw, Fund Transfer
	•	📜 Transaction History — view full or limited history per account
	•	✏️ Profile Updates — change name, email, phone, or PIN
	•	🗄️ Persistent Storage — file-based (.dat), no database needed
	•	🛡️ Admin Panel — view all accounts, bank summary, deactivate accounts
	•	⚠️ Custom Exceptions — clear, typed error handling
	•	✅ Input Validation — email, phone, PIN format enforced
BankManagementSystem/
├── src/
│   ├── Main.java
│   └── bank/
│       ├── model/
│       │   ├── Account.java          # Account entity (BigDecimal balance)
│       │   └── Transaction.java      # Transaction record
│       ├── service/
│       │   └── BankService.java      # Core banking logic
│       ├── exception/
│       │   └── BankException.java    # Custom exception hierarchy
│       ├── util/
│       │   ├── AdminConfig.java      # Hashed admin password management
│       │   ├── BankUtils.java        # Hashing, validation, ID generation
│       │   └── FileStorage.java      # Serialization-based persistence
│       └── ui/
│           └── ConsoleUI.java        # All console interaction
└── data/                             # Auto-created at runtime (git-ignored)
    ├── accounts.dat
    ├── transactions.dat
    └── admin.properties              # Hashed admin password — never share
cd src
javac -d ../out bank/model/*.java bank/exception/*.java bank/util/*.java bank/service/*.java bank/ui/*.java Main.java
cd ../out
java Main
Admin Panel
	•	On first run, you’ll be prompted to create an admin password (min 6 characters)
	•	The password is stored as a salted hash in data/admin.properties — never in plaintext
	•	Access the Admin Panel from the main menu (option 3)
	•	You can change the admin password anytime from inside the panel
Admin capabilities:
	•	View all accounts
	•	Bank summary (total accounts, total deposits)
	•	Deactivate any account
	•	Change admin password
1. Select "Create New Account" → enter details → note your Account Number
2. Select "Login" → enter Account Number + PIN
3. Choose from: Deposit / Withdraw / Transfer / History
4. Logout when done
