# 🗂️ File Manager Web App using Node.js, Express & EJS

A simple and intuitive file manager built with **Node.js**, **Express**, and **EJS**. It allows users to view, read, rename, and create `.txt` files through a browser interface.

---

## ✨ Features

- 📜 View all text files in a directory
- 🔍 Read contents of `.txt` files
- ✏️ Rename existing files
- 🆕 Create new `.txt` files from form input

---

## 🛠 Tech Stack

- **Backend**: Node.js, Express.js
- **Templating Engine**: EJS
- **File Handling**: Node.js `fs` module
- **Static Assets**: Express static middleware

---

## 🚀 Prerequisites

- Node.js (v14+)
- npm

---

## 🛠 Setup Instructions

### 1. Clone the Repository

```bash
git clone https://github.com/your-username/file-manager-app.git
cd file-manager-app
```

### 2. Install Dependencies

```bash
npm install
```

### 3. Create Required Directory

Create a `files/` directory to store all `.txt` files:

```bash
mkdir files
```

### 4. Run the Server

```bash
node app.js
```

Visit your app at:  
`http://localhost:3000`

---

## 📡 API Endpoints

### 1. List All Files

- **Method**: `GET`
- **Endpoint**: `/`
- **Description**: Lists all `.txt` files in the `/files` directory.

**Response Example:**

```json
{
  "files": ["todo.txt", "notes.txt", "readme.txt"]
}
```

---

### 2. Read File Content

- **Method**: `GET`
- **Endpoint**: `/file/:filename`
- **Description**: Displays the content of the selected file.

**Response Example:**

```json
{
  "filename": "todo.txt",
  "filedata": "Buy groceries\nFinish assignment"
}
```

---

### 3. Open Rename Form

- **Method**: `GET`
- **Endpoint**: `/edit/:filename`
- **Description**: Renders a form to rename a file.

**Response Example:**

```json
{
  "filename": "oldname.txt"
}
```

---

### 4. Submit File Rename

- **Method**: `POST`
- **Endpoint**: `/edit`
- **Description**: Renames the specified file.

**Request Body:**

```json
{
  "previous": "oldname.txt",
  "new": "newname.txt"
}
```

**Response**: Redirects to `/` on success.

---

### 5. Create a New File

- **Method**: `POST`
- **Endpoint**: `/create`
- **Description**: Creates a new `.txt` file using provided input.

**Request Body:**

```json
{
  "title": "DailyNotes",
  "details": "Learn Node.js basics today!"
}
```

> Resulting file: `DailyNotes.txt`

**Response**: Redirects to `/` on success.

---

## 🧪 Testing the API

You can use **Postman** or your browser for GET routes.

1. `GET /` – View all files  
2. `GET /file/:filename` – View file content  
3. `GET /edit/:filename` – Show rename form  
4. `POST /edit` – Submit rename  
5. `POST /create` – Create a new file  

> ✅ For POST: Use `x-www-form-urlencoded` or `application/json` if middleware supports it.

---

## 📁 Project Structure

```
.
├── app.js               # Main server file
├── files/               # Directory to store .txt files
├── public/              # Static files (CSS, JS, etc.)
├── views/               # EJS templates
│   ├── index.ejs
│   ├── show.ejs
│   └── edit.ejs
├── package.json
```

---

## 📌 Roadmap & Improvements

- ❌ Delete functionality
- ✍️ File content editing
- ⚠️ Error handling (e.g., file not found)
- 💅 UI upgrade with Bootstrap/Tailwind

---

## 🧡 Support This Project

If you found this helpful:

- ⭐ Star it on GitHub
- 🍴 Fork it
- 📢 Share it

---
