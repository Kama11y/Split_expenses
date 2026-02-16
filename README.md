# Split_expenses

A simple command-line based expense splitting system built using Python.  
This project tracks shared expenses, calculates net balances, and generates settlement transactions between users.

---

## Features

- Add shared expenses
- Equal or custom weighted splits
- Track net balances
- Automatically generate settlement transactions
- Simple and beginner-friendly implementation

---

## How It Works

The system maintains:

### `user_dict`
A dictionary storing each user's net balance.

- Positive value → User should receive money
- Negative value → User owes money

Example:
{'alice': 500.0, 'bob': -100.0, 'carol': -400.0}


The total of all balances should always equal **zero**.

---

### `expense_list`
Stores all recorded expenses in the format:

[name, amount, paid_by, users, split_type, description]


---

## 🔧 Functions

### `add_expense(name, amount, paid_by, *users, split="Equal", desc="")`

Adds a new expense and updates balances.

#### Equal Split
- Total amount is divided equally among users.
- The payer receives the share owed by others.

#### Custom Split
- User enters weights separated by spaces.
- Each user’s share = weight × total amount.

---

### `net_balances()`

Displays each user's current balance.

Output format:
- `Should Receive` → User is owed money
- `Owes` → User needs to pay money

---

### `settle_expenses()`

Generates transactions to clear all balances.

Logic:
- Separates creditors and debtors.
- Uses a greedy approach to settle payments.
- Prints transactions like:

