
💰 Personal Finance Manager (CLI Based)

A Command Line Interface (CLI) based Personal Finance Tracker built using Python, SQLite, and SQLAlchemy ORM.

This application helps users manage daily expenses, track subscriptions, monitor category-wise spending, and control monthly budgets efficiently.

🚀 Features

✅ Add and manage expense categories

✅ Record daily transactions (expenses)

✅ Update existing transactions

✅ Delete incorrect or extra entries

✅ Search expenses by date

✅ View category-wise spending summary (using Raw SQL JOIN & GROUP BY)

✅ Set monthly budgets for categories

✅ Get budget alerts when spending exceeds the limit

✅ Track subscriptions (Netflix, Gym, etc.)

✅ Persistent data storage using SQLite database

🛠 Technologies Used

Python 3

SQLite Database

SQLAlchemy ORM

Raw SQL Queries

CLI (Command Line Interface)

🗄 Database Schema

The application uses four relational tables with proper foreign key relationships.

1️⃣ Categories

Stores different types of spending categories.

Fields:

id — Integer, Primary Key

name — String (e.g., Food, Travel)

Relationships:

One Category → Many Transactions

One Category → Many Budgets

2️⃣ Transactions

Stores all expense records entered by the user.

Fields:

id — Integer, Primary Key

amount — Float

description — String

date — String (YYYY-MM-DD)

category_id — Foreign Key → categories.id

Relationship:

Many Transactions → One Category

3️⃣ Budgets

Stores monthly spending limits for categories.

Fields:

id — Integer, Primary Key

category_id — Foreign Key → categories.id

month — String (YYYY-MM format)

budget_limit — Float

Purpose:

Compare actual spending vs planned budget

Used for generating budget alerts

Relationship:

Many Budgets → One Category

4️⃣ Subscriptions

Stores recurring expenses separately.

Fields:

id — Integer, Primary Key

name — String (e.g., Netflix)

amount — Float

start_date — String (YYYY-MM-DD)

end_date — String (Renewal date)

Relationship:

Standalone entity (not linked to categories)

🔄 Relationship Summary
Category → Transactions  = One-to-Many
Category → Budgets       = One-to-Many
Transactions → Category  = Many-to-One
Budgets → Category       = Many-to-One
Subscriptions            = Independent Table

⚙️ How It Works (Workflow)

User creates categories (Food, Travel, etc.)

User records transactions under categories

Data is stored using SQLAlchemy ORM

User can:

Update/Delete transactions

Search by date

View category-wise summary

User sets monthly budgets

System compares spending with budget and shows alerts

Subscriptions are tracked separately

User exits program

📊 Category Summary Logic

Uses Raw SQL JOIN between categories and transactions:

Performs JOIN

Calculates SUM(amount)

Uses GROUP BY category

Displays category-wise spending summary

🧾 Budget Alert Logic

User enters month (YYYY-MM)

System calculates total spending per category for that month

Compares spending with budget limit

Displays:

⚠️ ALERT if spending exceeds limit

✅ Within Budget otherwise

▶️ How to Run the Project
1️⃣ Clone the Repository
git clone https://github.com/your-username/personal-finance-manager.git
cd personal-finance-manager

2️⃣ Install Dependencies
pip install sqlalchemy

3️⃣ Run the Program
python finance_tracker.py

🖥 CLI Menu Options

Add Category

Add Transaction

Update Transaction

Delete Transaction

Search Transaction by Date

Category Summary

Set Budget

Budget Alert

Add Subscription

Exit

🎯 Learning Outcomes

This project demonstrates:

ORM-based database interaction

SQL JOINs and aggregation

CLI application design

Budget tracking logic

Foreign key relationships

Modular programming with Python

🔮 Future Enhancements

📤 Export reports to CSV

📊 Monthly summary report

📈 Graphical dashboard

🖥 Convert CLI to GUI (Tkinter / Web App)

🔐 User authentication system

📌 Author

Developed as a learning project for mastering:

Python

SQLAlchemy ORM

SQL concepts

Real-world database design
