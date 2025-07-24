# 📚 Java Quiz Application (Console-Based)

## 🧠 Overview
The **Quiz Application** is a Java-based console program designed to offer a complete quiz-taking and management experience for both users and administrators. The system supports registration, login, timed quizzes of various difficulty levels, and full admin-level quiz control. All data is file-based, making it easy to run without a database setup.

---

## 🎯 Features

### 👤 User Features:
- **Secure Registration** with age validation (15+).
- **Strong Password Enforcement** (8+ characters, 1 uppercase, 1 digit, 1 special character).
- **Multiple Difficulty Levels**: Easy, Medium, Hard, and Surprise.
- **Timed Quizzes** with countdown display (different times per level).
- **Personal Result History**: View your own quiz performance.

### 🛠️ Admin Features:
- **Admin Login** with credential validation.
- **Add Quizzes** by subject and difficulty.
- **Edit Quizzes** to append questions.
- **Delete Quizzes** and update the system.
- **View All Users' Results** from one file.

### 💻 Technical Features:
- **File-Based Storage** (no external database needed).
- **Input Validation** on usernames, passwords, and age.
- **Quiz Engine** with randomization support and timer functionality.

---

## 🧩 System Modules

### 1. User Authentication Module
- **Registration**: Inputs username, age, and password; checks password strength and age.
- **Login**: Authenticates users from `registrations.txt`, allows 3 attempts.

### 2. Quiz Module
- **Difficulty Selector**: Lets users pick Easy, Medium, Hard, or Surprise.
- **Question Loading**: Reads from subject/difficulty-specific files.
- **Timed Quiz**: Each level has a different time (e.g., Easy: 2.5 mins).
- **Answer Check & Score Display**: Evaluates user responses in real time.

### 3. Admin Module
- **Add Quiz**: Creates quiz and key files per difficulty level.
- **Edit Quiz**: Adds new questions to existing quiz files.
- **Delete Quiz**: Deletes quiz + key files and updates `Subjects.txt`.

### 4. Result Tracking Module
- **User Results**: Saved in `[Username].txt`.
- **Admin Results**: All attempts saved in `AllResults.txt`.

---

## 🗂️ File Structure

| File Name                        | Purpose                              | Format/Example                                      |
|----------------------------------|--------------------------------------|-----------------------------------------------------|
| `registrations.txt`              | User login info                      | `johnDoe\|Pass123!\|20`                             |
| `adminlogin.txt`                 | Admin credentials                    | `admin\|Admin@123`                                  |
| `Subjects.txt`                   | Lists subjects                       | `1: Math`                                           |
| `[Subject][Difficulty]Quiz.txt`  | Quiz questions                       | `What is 2+2?$A. 3$B. 4$C. 5$D. 6`                  |
| `[Subject][Difficulty]Key.txt`   | Answer keys                          | `B`                                                 |
| `AllResults.txt`                 | Records of all quiz attempts         | `johnDoe scored 4/5 in MathEasy`                    |
| `[Username].txt`                 | Individual user result history       | `Previous attempts by johnDoe`                      |
| `SurpriseQuiz.txt` / `SurpriseKey.txt` | Randomized questions and keys     | Same format as others                              |

---

## 🔧 Key Methods

| Method                             | Purpose                                                                 |
|-----------------------------------|-------------------------------------------------------------------------|
| `isStrong(String password)`       | Validates password complexity.                                          |
| `duplicateUsers(String userName)` | Checks if username already exists.                                      |
| `duplicateUsers(String userName, String password)` | Checks user credentials.                            |
| `registerUser()`                  | Handles registration with validation.                                   |
| `loginUser()`                     | Handles login with 3 attempts max.                                      |
| `loginAdmin()`                    | Admin login logic.                                                      |
| `difficultyLevel()`               | Lets users choose difficulty.                                           |
| `startQuiz()`                     | Manages quiz process and flow.                                          |
| `takeQuiz(...)`                   | Loads questions, runs timer, checks answers, saves results.             |
| `viewResults()`                   | Shows personal quiz results.                                            |
| `viewAllResults()`                | Admin-only method to view all user results.                             |
| `addQuiz()`                       | Creates new quiz and key files.                                         |
| `editQuiz()`                      | Appends questions to existing quizzes.                                  |
| `deleteQuiz()`                    | Deletes quiz files and updates subject list.                            |
| `lineCounter(String file)`        | Helper to count number of questions in a file.                          |
| `createFile(...)`                 | Creates quiz + key files and updates `Subjects.txt`.                    |
| `deleteFile(...)`                 | Deletes quiz + key files and updates `Subjects.txt`.                    |

---

## 📌 Requirements
- Java SE (Standard Edition)
- Any IDE: NetBeans, Eclipse, IntelliJ, or plain terminal
- No external libraries required
- Runs via console

---

## 🚀 How to Run
1. Clone or download the project files.
2. Open in your preferred IDE or compile via command line.
3. Run the main class.
4. Choose between **User** or **Admin** mode.
5. Follow the prompts for registration, login, quiz-taking, or quiz management.

---

## 📎 License
This project is open for educational use and modification.

