# 📝 Notes API

A RESTful API built using **Node.js**, **Express.js**, and **Firebase Firestore** that enables users to create, read, update, and delete notes. This project demonstrates core backend development skills, integration with cloud databases, input validation, and error handling.

---

## 🚀 Features

- ✅ Full CRUD operations for notes
- 🔐 Secure integration with Firebase Firestore
- 📦 Input validation using `express-validator`
- 🛡️ Robust error handling for API reliability
- 🧪 Tested using Postman
- 🧱 Scalable architecture suitable for deployment

---

## 🛠️ Tech Stack

- **Node.js** – JavaScript runtime
- **Express.js** – Web framework for Node.js
- **Firebase Admin SDK** – Access Firebase services securely
- **Firestore** – NoSQL cloud database
- **Express Validator** – Middleware for validating user input
- **Postman** – API testing

---

## 📦 Installation & Setup

### 1. Clone the Repository

```bash
git clone https://github.com/yourusername/notes-api.git
cd notes-api

Notes API
A RESTful API for managing notes, built with Node.js, Express.js, and Firebase Firestore. This project provides endpoints for creating, reading, updating, and deleting (CRUD) notes, stored in a Firestore database. It includes input validation, error handling, and is tested using Postman.
Table of Contents

Features
Technologies
Prerequisites
Setup
Running the API
API Endpoints
Testing with Postman
Firestore Structure
Troubleshooting
Contributing
License

Features

Create, read, update, and delete notes via RESTful endpoints.
Store notes in Firebase Firestore with automatic timestamps.
Input validation using Express Validator.
Error handling for invalid requests or server issues.
Tested with Postman for reliability and ease of use.
Scalable backend suitable for web or mobile applications.

Technologies

Node.js: JavaScript runtime for server-side development.
Express.js: Web framework for routing and middleware.
Firebase Firestore: NoSQL cloud database for note storage.
Firebase Admin SDK: Secure server-side access to Firestore.
Express Validator: Middleware for request validation.
Postman: API testing tool.
dotenv: Environment variable management.

Prerequisites

Node.js: Version 20.x (LTS recommended). Download from nodejs.org.
Firebase Account: Create a project at Firebase Console.
Postman: Install from postman.com for testing.
Git: For cloning the repository (optional).

Setup

Clone the Repository (if applicable):
git clone <repository-url>
cd notes-api


Install Dependencies:
npm install


Set Up Firebase:

Create a Firebase project (nodeapi-cb876 or your project ID).
Go to Project Settings > Service Accounts > Generate new private key.
Download the JSON file (e.g., nodeapi-cb876-firebase-adminsdk-fbsvc.json) and place it in the project root.
Enable the Cloud Firestore API at:Google Cloud Console.
Create a Firestore database in test mode:
Go to Firebase Console > Firestore Database > Create Database.
Select Start in test mode and a location (e.g., us-central).




Configure Firestore Rules:

In Firebase Console > Firestore Database > Rules, set:rules_version = '2';
service cloud.firestore {
  match /databases/{database}/documents {
    match /{document=**} {
      allow read, write: if true;
    }
  }
}




Verify server.js:

Ensure server.js references the correct JSON file:admin.initializeApp({
  credential: admin.credential.cert('./nodeapi-cb876-firebase-adminsdk-fbsvc.json'),
});





Running the API

Start the server:
npm start

Output: Server running on port 3000.

The API is accessible at http://localhost:3000.


API Endpoints
All endpoints are prefixed with /notes.



Method
Endpoint
Description
Request Body/Example



POST
/notes
Create a new note
{ "title": "My Note", "content": "Text" }


GET
/notes
Get all notes
None


GET
/notes/:id
Get a note by ID
None (ID in URL)


PUT
/notes/:id
Update a note by ID
{ "title": "Updated", "content": "New" }


DELETE
/notes/:id
Delete a note by ID
None (ID in URL)


Example Responses

POST /notes (201 Created):{
  "id": "some-unique-id",
  "title": "My Note",
  "content": "Text",
  "createdAt": "2025-06-06T18:41:00Z",
  "updatedAt": "2025-06-06T18:41:00Z"
}


GET /notes (200 OK):[
  {
    "id": "some-unique-id",
    "title": "My Note",
    "content": "Text",
    "createdAt



