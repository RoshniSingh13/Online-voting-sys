# Java Console Online Voting System

A robust, console-based voting application built with Java. This system utilizes **File Handling** to ensure data persistence, allowing users to register, securely login, and cast votes without losing data when the program closes.

---

## Table of Contents

- [Overview](#overview)
- [Key Features](#key-features)
- [Technical Architecture](#technical-architecture)
- [Prerequisites](#prerequisites)
- [Installation & Execution](#installation--execution)
- [Data Storage Structure](#data-storage-structure)
- [Usage Flow](#usage-flow)
- [Future Scope](#future-scope)

---

## Overview

This project demonstrates core Computer Science concepts including **File I/O**, **Collection Frameworks (HashMap)**, and **Object-Oriented Programming**. It simulates a real-world voting scenario where user identity verification and "one person, one vote" integrity are paramount.

---

## Key Features

- **User Registration:**
  - Securely registers new users.
  - **Duplicate Check:** Prevents multiple accounts with the same username.
- **Authentication System:**
  - Login verification using stored credentials.
  - **Vote Status Tracking:** Ensures a user can only vote exactly once.
- **Persistent Storage:**
  - All data (credentials and votes) is saved to `.txt` files.
  - Data remains available even after the program terminates.
- **Dynamic Results:**
  - Real-time vote tallying using HashMaps.
  - Handles dynamic candidate names found in the vote file.

---

## Technical Architecture

| Component | Implementation Detail |
|-----------|----------------------|
| **Language** | Java (JDK 8+) |
| **Input** | `java.util.Scanner` |
| **File I/O** | `BufferedReader`, `BufferedWriter`, `FileWriter`, `File` |
| **Collections** | `HashMap<String, Integer>` for result aggregation |
| **Logic** | Switch-Case menu driven interface |

---

## Prerequisites

- **Java Development Kit (JDK):** Version 8 or higher installed.
- **Terminal/Command Prompt:** To run the application.

---

## Installation & Execution

1. **Compile the Code**
   Open your terminal in the directory containing the file and run:
   ```bash
   javac OnlineVotingSystem.java
   ```

2. **Run the Application**
   Execute the compiled class file:
   ```bash
   java OnlineVotingSystem
   ```

3. **Interact**
   Follow the on-screen menu prompts to navigate the application.

---

## Data Storage Structure

The application automatically creates and manages two text files in the root directory.

### 1. `users.txt` (User Database)
Stores user credentials and voting status in CSV format.
**Format:** `username,password,hasVoted`

**Example:**
```text
john_doe,securePass123,true
alice_smith,myPass456,false
```
*Note: `true` indicates the user has already voted.*

### 2. `votes.txt` (Ballot Box)
Stores every vote cast as a single line entry.
**Format:** `Candidate Name`

**Example:**
```text
Candidate A
Candidate B
Candidate A
```

---

## Usage Flow

1. **Start the App:** The main menu appears.
2. **Register:** Select Option 1 to create an account.
3. **Login & Vote:** Select Option 2.
   - Enter credentials.
   - If credentials match and you haven't voted, the candidate list appears.
   - Select a candidate.
   - System updates your status to "voted" and saves the vote.
4. **View Results:** Select Option 3 to see the current tally.
5. **Exit:** Select Option 4 to close the application.

---

## Code Logic Highlights

### The "Update Status" Algorithm
To update a user's status from `false` to `true` without loading the whole file into memory:
1. The program reads `users.txt` line by line.
2. It writes every line to a `temp.txt` file.
3. When it encounters the current user's line, it modifies the data before writing.
4. Finally, it deletes the original file and renames `temp.txt` to `users.txt`.


