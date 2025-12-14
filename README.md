# ⚖ Chef Court – Law App Backend API

This repository contains the backend API for *Chef Court*, a role-based law application that simulates a judicial system involving plaintiffs, defendants, judges, and jurors.

The backend is built using *Flask* and *SQLite*, handling authentication, role-based access control, case management, and jury voting logic.

## 🏛 Application Overview

- Users sign up with specific legal roles
- Plaintiffs and defendants submit cases
- Judges approve, edit, or delete cases
- Jurors vote on approved cases
- Voting results determine case outcomes

## 🛠 Tech Stack

- Python 3
- Flask
- Flask-SQLAlchemy
- SQLite
- Werkzeug Security

## ⚙ How to Run
pip install flask flask-sqlalchemy werkzeug
python app.py

Server runs at:
http://localhost:5000
🔗 Core API Endpoints
Method	Endpoint	Description
POST	/auth/signup	User signup
POST	/auth/login	User login
POST	/case/submit	Submit a case
GET	/case/all	View all cases
PATCH	/case/edit/<id>	Judge edits case
DELETE	/case/delete/<id>	Judge deletes case
POST	/case/vote/<id>	Juror votes

👥 User Roles
Role	Permissions
Plaintiff	Submit cases
Defendant	Submit cases
Judge	Approve, edit, delete cases
Juror	Vote on cases

🧮 Voting Rules
Only approved cases can be voted on
Each juror can vote only once
Votes allowed:

guilty

not_guilty

Duplicate votes are blocked

🔎 API Examples
Signup


POST /auth/signup
Content-Type: application/json

{
  "username": "alice",
  "password": "password123",
  "role": "plaintiff"
}
Login

POST /auth/login
Content-Type: application/json

{
  "username": "alice",
  "password": "password123"
}
Submit Case

POST /case/submit
Authorization: YOUR_TOKEN
Content-Type: application/json

{
  "title": "Property Dispute",
  "content": "Case details",
  "evidence": "Document reference"
}
