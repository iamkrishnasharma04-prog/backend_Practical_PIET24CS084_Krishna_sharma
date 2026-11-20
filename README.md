# Backend Practical

**Name:** Krishna Sharma  
**Registration No.:** PIET24CS084

This folder contains two practical programs:

- `file/A1.js` – Library Book Management API
- `file/A2.js` – Student Portal with Login and Protected Routes

## Requirements

- Node.js and npm
- MongoDB (local installation or MongoDB Atlas)
- Postman for API testing

## Setup

1. Open this folder in Visual Studio Code.
2. Open **Terminal → New Terminal**.
3. Install the required packages:

   ```bash
   npm install
   ```

4. Copy `.env.example` and rename the copy to `.env`.
5. Open `.env` and add your MongoDB connection string and a private JWT secret:

   ```env
   PORT=3000
   MONGO_URI=mongodb://127.0.0.1:27017/backend_exam
   JWT_SECRET=enter_a_private_secret_here
   ```

   If you use MongoDB Atlas, replace the `MONGO_URI` value with your Atlas connection string.

## Run the programs

Run one program at a time because both use port `3000`.

**Task 1 – Library Book Management API**

```bash
npm run start:a1
```

**Task 2 – Student Portal API**

Stop the first server with `Ctrl + C`, then run:

```bash
npm run start:a2
```

The server will use `http://localhost:3000`.

## API routes

### Task 1 – Library Book Management

| Method | Route | Purpose |
|---|---|---|
| POST | `/books` | Add a book |
| GET | `/books` | View all books |
| GET | `/books/:id` | View one book |
| PUT | `/books/:id` | Update a book |
| DELETE | `/books/:id` | Delete a book |

### Task 2 – Student Portal

| Method | Route | Purpose |
|---|---|---|
| POST | `/register` | Register a student or admin |
| POST | `/login` | Log in and receive a JWT |
| GET | `/profile` | View the logged-in user's profile |
| GET | `/students` | View students (admin only) |

For `/profile` and `/students`, select **Authorization → Bearer Token** in Postman and paste the token received from `/login`.

Expected access checks:

- `/profile` without a token: `401`
- `/profile` with a valid token: `200`
- `/students` with a student token: `403`
- `/students` with an admin token: `200`

## Output folder

The `outputs` folder contains illustrative sample layouts showing the kind of API results to capture. They are not live Postman test evidence. Before submitting, run the APIs and replace these samples with your own Postman screenshots:

- `A1.png` – book API requests and responses
- `A2.png` – registration and login responses

## Project structure

```text
backend_Practical_PIET24CS084_Krishna_sharma/
├── file/
│   ├── A1.js
│   └── A2.js
├── outputs/
│   ├── A1.png
│   └── A2.png
├── .env.example
├── .gitignore
├── package.json
└── README.md
```

Do not share your `.env` file or upload it to GitHub.
