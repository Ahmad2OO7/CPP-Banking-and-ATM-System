# C++ Banking and ATM System

This repository contains four standalone console programs for client records, transactions, user permissions, and ATM operations. Each program is in its own folder and reads and writes the text files in that folder.

## Project structure

```text
01-Basic-CRUD/
├── Bank 1.cpp
└── Clients.txt
02-Transactions/
├── Bank 2.cpp
└── Clients.txt
03-Users-and-Permissions/
├── Bank 3.cpp
├── Clients.txt
└── Users.txt
04-ATM-System/
├── ATM System.cpp
└── Clients.txt
```

Each folder contains its own C++ source file and `Clients.txt`. Phase 3 also contains `Users.txt`.

## Versions

- **01 - Basic CRUD:** List, add, find, update, and delete client records.
- **02 - Transactions:** Adds deposits, withdrawals, and a total balance view.
- **03 - Users and Permissions:** Adds user login, permission checks for menu actions, and user management.
- **04 - ATM System:** Signs in with a client account number and PIN; offers quick withdrawal, normal withdrawal, deposit, and balance display.

## Data files

Client records use one line per client and this field order:

```text
AccountNumber#//#PinCode#//#Name#//#Phone#//#AccountBalance
```

The fields are separated by the literal delimiter `#//#`. Phase 3 stores user records in this format:

```text
Username#//#Password#//#Permissions
```

Phase 3 permission values are bit flags: `1` list clients, `2` add clients, `4` delete clients, `8` update clients, `16` find clients, `32` use transactions, and `64` manage users. `-1` grants all permissions.

The included records and credentials are fictional examples for local testing. Credentials and account PINs are stored as plain text; do not use real personal or account information.

### Phase 3 sample login

| Username | Password | Permissions |
| --- | --- | --- |
| `Admin` | `demo-admin` | `-1` (all) |
| `DemoManager` | `demo-manager` | `63` (client actions and transactions; no user management) |
| `DemoTeller` | `demo-teller` | `49` (list, find, and transactions) |

The sample ATM account `DEMO001` uses PIN `0001`.

## Build and run

Use a Windows console and a C++11-compatible MinGW-w64 GCC installation. The programs call the Windows console commands `cls` and `pause`. Compile and run each source file from its own folder so the program can find the matching text data files.

Clone the repository and enter its folder:

```powershell
git clone https://github.com/Ahmad2OO7/CPP-Banking-and-ATM-System.git
Set-Location .\CPP-Banking-and-ATM-System
```

Run one of these sections from the repository root. Each section compiles one program; the data file in that folder is updated when records or balances change.

### Phase 1

```powershell
Set-Location .\01-Basic-CRUD
g++ -std=c++11 "Bank 1.cpp" -o Bank1.exe
.\Bank1.exe
```

### Phase 2

```powershell
Set-Location .\02-Transactions
g++ -std=c++11 "Bank 2.cpp" -o Bank2.exe
.\Bank2.exe
```

### Phase 3

```powershell
Set-Location .\03-Users-and-Permissions
g++ -std=c++11 "Bank 3.cpp" -o Bank3.exe
.\Bank3.exe
```

### ATM

```powershell
Set-Location .\04-ATM-System
g++ -std=c++11 "ATM System.cpp" -o ATMSystem.exe
.\ATMSystem.exe
```

After closing one program, return to the repository root with `Set-Location ..` before running another phase. There is no shared build target; compile the version you want to run.
