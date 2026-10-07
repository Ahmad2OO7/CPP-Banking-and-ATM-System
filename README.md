# Banking & ATM Management System (C++)

A comprehensive, modular console-based banking management and ATM ecosystem developed in C++. The project demonstrates core software engineering practices, low-level data structures, and flat-file data serialization built incrementally across multiple iterations.

---

## 📌 System Evolution & Architecture

The application was designed iteratively to reflect real-world modular software architecture:

### 1. Phase 1: Core CRUD Engine (`01-Basic-CRUD`)
* **Flat-File Database:** Custom delimiter-based serialization/deserialization (`#//#`) to persist records without third-party database dependencies.
* **Record Management:** Add, search, update, and soft/hard deletion of client accounts.
* **Memory & Structure:** Managed through C++ `structs` and dynamic `std::vector` containers.

### 2. Phase 2: Transaction Processing (`02-Transactions`)
* **Financial Operations:** Deposit, withdrawal, balance checking, and total institutional ledger calculation.
* **Input Validation:** Real-time overdraft prevention and parameter validation.

### 3. Phase 3: Enterprise User & Access Control (`03-Users-and-Permissions`)
* **Authentication System:** Secure multi-user login gateway.
* **Bitwise Permission Masking:** User authorizations (List, Add, Delete, Update, Find, Transactions, Manage Users) mapped using bitwise `AND`/`OR` operations for granular access management.
* **Administrative Control:** Dedicated user management sub-system.

### 4. ATM System (`04-ATM-System`)
* **Client-Facing Terminal:** Self-service portal authenticating via `AccountNumber` and `PinCode`.
* **Quick & Custom Withdrawals:** Presets (20–1000) and custom multi-5 withdrawal rules.
* **Instant Balance Synchronization:** Direct updates to the persistent flat-file data store.

---

## 🛠 Technical Highlights

* **Language:** C++ (Standard 11+)
* **Data Persistence:** Custom flat-file stream processing (`fstream`)
* **Architecture:** Modular procedural programming, structured separation of concerns (Business Logic vs. UI Screens)
* **Optimization:** Pass-by-reference (`const &`) to prevent redundant memory copying
* **Security:** Bit-level permission masks (`enum enMainMenuePermissions`)

---

## 🚀 How to Compile and Run

Clone the repository and compile any phase using a standard C++ compiler (GCC / Clang / MSVC):

```bash
# Clone the repository
git clone [https://github.com/](https://github.com/)Ahmad2OO7/Banking-and-ATM-System-Cpp.git

# Navigate to Phase 3 (Full System)
cd Banking-and-ATM-System-Cpp/03-Users-and-Permissions

# Compile with g++
g++ -std=c++11 "Bank 3.cpp" -o BankSystem

# Run the executable
./BankSystem
