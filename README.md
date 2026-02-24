# README

This repository includes:
1) A **Java Spring Boot** backend application (Gradle)  
2) A **6-Letter Word Game (Wordle-style)** frontend (HTML/CSS/JavaScript)

---

1) Backend: Java Spring Boot (Gradle)

Prerequisites
- **Java 17** (JDK 17)
- (Recommended) IntelliJ IDEA / VS Code

Check Java version:
java -version
How to Run (Java / Spring Boot)
Option 1: Run with Gradle Wrapper (Recommended)

From the project root directory:

Windows (PowerShell / CMD)

.\gradlew.bat bootRun

macOS / Linux

./gradlew bootRun

If startup is successful, you should see logs similar to:

Tomcat started on port 8080 (http)

Then open in your browser:

http://localhost:8080

Option 2: Build a JAR and Run

Windows

.\gradlew.bat clean build
java -jar build\libs\*.jar

macOS / Linux

./gradlew clean build
java -jar build/libs/*.jar

Then open:

http://localhost:8080

Stopping the Server

Press Ctrl + C in the terminal where the server is running.

API Testing (Optional)

You can test endpoints using a browser (GET), Postman, or curl.

Example:

curl http://localhost:8080
Troubleshooting

Port 8080 already in use

Stop the process using port 8080, or run on a different port (example 8081):

Windows

.\gradlew.bat bootRun --args='--server.port=8081'

macOS / Linux

./gradlew bootRun --args='--server.port=8081'

Gradle permission issue (macOS/Linux)

chmod +x gradlew
2) Frontend: 6-Letter Word Game (Wordle-style)

A lightweight Wordle-style guessing game built with vanilla HTML/CSS/JavaScript.
Guess the hidden 6-letter word within a limited number of attempts. The game supports both physical keyboard input and an on-screen keyboard, and saves progress using localStorage.

Features

Wordle-style 6-letter guessing gameplay with instant feedback:

Correct: right letter, right position

Present: letter exists, wrong position

Absent: letter not in the word

Supports physical keyboard and on-screen keyboard

Only allows submission when 6 letters are entered

Validates guesses using an online dictionary API

Automatically saves game progress via localStorage (refresh won’t lose the current game)

Tech Stack (Frontend)

HTML5

CSS3 (Flexbox)

JavaScript (Vanilla): DOM manipulation, events

Fetch API for REST requests

localStorage for persistence

API Used (Frontend Word API)

This game uses the public word API from words.trex-sandwich.com:

Random 6-letter word (target word):
https://words.trex-sandwich.com/?count=1&length=6

Validate a guessed word (example):
https://words.trex-sandwich.com/<word>

Note: An internet connection is required to fetch and validate words. If the API is unavailable, gameplay may be affected.

How to Run (Frontend Local)
Option 1: Open directly (quick start)

Download or clone this repository.

Open index.html in your browser.

✅ This works in most browsers.

Option 2: Run with a local server (recommended)

Using a local server can avoid browser restrictions in some setups.

Using VS Code Live Server

Install the Live Server extension in VS Code.

Right-click index.html → Open with Live Server.

Using Python

# from the project root directory
python -m http.server 8000

Then open http://localhost:8000 in your browser.

How to Play

Type letters on your keyboard or click the on-screen keys.

Press Enter to submit a guess (only after entering 6 letters).

Press Backspace to remove the last letter.

The board and keyboard will update colors after each guess.

Your progress is saved automatically.

Notes

The game stores progress in the browser via localStorage.

Clearing browser data will reset your game.

This project is intended for learning and portfolio demonstration.

License

This project is for educational and demonstration purposes.
