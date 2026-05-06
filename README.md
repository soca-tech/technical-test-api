# 🧪 Technical Test — REST API Development

> **Estimated duration:** 1 day (8 hours max)  
> **Level:** Junior / Mid  
> **Stack:** Your choice (Laravel, Node.js, Python, or any backend framework)

---

## 📌 Context

You are building the backend API for a **Task Management** application. Your job is to design and implement a clean, well-structured REST API.

This test evaluates:
- Your ability to **solve problems** and handle edge cases
- The **quality and clarity of your code**
- Your **Git discipline** (commit messages, commit structure)
- Your understanding of **REST API design principles**

---

## 🏗️ Data Model

You have 3 entities to manage:

### `User`
| Field | Type | Notes |
|---|---|---|
| `id` | integer | Primary key |
| `name` | string | Required |
| `email` | string | Unique, required |
| `password` | string | Hashed |
| `created_at` | timestamp | |

### `Category`
| Field | Type | Notes |
|---|---|---|
| `id` | integer | Primary key |
| `name` | string | Required, unique |
| `created_at` | timestamp | |

### `Task`
| Field | Type | Notes |
|---|---|---|
| `id` | integer | Primary key |
| `title` | string | Required |
| `description` | text | Optional |
| `status` | enum | `todo`, `in_progress`, `done` |
| `due_date` | date | Optional |
| `user_id` | foreign key | Owner of the task |
| `category_id` | foreign key | Optional |
| `created_at` | timestamp | |
| `updated_at` | timestamp | |

> You are free to add more models if it seems necessary.

---

## 🔌 Endpoints to Implement

### Authentication (public routes)

| Method | Endpoint | Description |
|---|---|---|
| `POST` | `/api/register` | Create a new user account |
| `POST` | `/api/login` | Login and receive a JWT token |
| `POST` | `/api/logout` | Invalidate the current token |

### Tasks (protected routes — JWT required)

| Method | Endpoint | Description |
|---|---|---|
| `GET` | `/api/tasks` | List all tasks of the authenticated user |
| `POST` | `/api/tasks` | Create a new task |
| `GET` | `/api/tasks/{id}` | Get a single task |
| `PUT` | `/api/tasks/{id}` | Update a task |
| `DELETE` | `/api/tasks/{id}` | Delete a task |

### Categories (protected routes)

| Method | Endpoint | Description |
|---|---|---|
| `GET` | `/api/categories` | List all categories |
| `POST` | `/api/categories` | Create a new category |

> You are free to add more endpoints if it seems necessary.

---

## ⚙️ Business Rules

These rules are intentional — how you handle them reveals your problem-solving ability.

1. **A task in `in_progress` status cannot be deleted.**  
2. **A user can only see and manage their own tasks.**  
3. **Status transitions must be controlled.**  
   → A task can only move forward: `todo` → `in_progress` → `done`.  
   → Going backward (e.g., `done` → `todo`) must be rejected with an error.
4. **Task list must support filtering and pagination.**  
5. **Input validation is mandatory.**  
---

## 📦 Expected Response Format

All API responses must follow a **consistent JSON structure**.

## 🚀 Getting Started

### 1. Clone this repository

### 2. Create your own private repository

### 3. Invite us as collaborator

> ⚠️ Do **not** submit a public repo. Do **not** open a Pull Request on the original repo.

### 4. Set up your project
Your project must include:
- [ ] A database (PostgreSQL, MySQL, or SQLite)
- [ ] JWT-based authentication
- [ ] Migration files to set up the schema

### 5. Seed the database
Provide a seed script or clear instructions to populate the database with:
- At least **3 categories**
- At least **2 users**
- At least **5 tasks per user** with mixed statuses

### 6. Document your project
Your `README.md` must include:
- How to install dependencies
- How to configure the `.env`
- How to run migrations and seeders
- How to start the server
- The base URL of the API
- A Postman collection or Swagger link (strongly recommended)

---

## 📋 Deliverables

Once done, send the link to your private repository to **[w.charfi@socainternational.com]**.

Your repo must contain:

- [ ] A working API covering all endpoints and business rules
- [ ] Clean Git history with meaningful commits (see below)
- [ ] A `README.md` with setup and run instructions
- [ ] A `.env.example` file

---

## ✅ Git History — Mandatory

Every completed feature must be committed **as you go**, not all at once at the end.  
We will review commit messages **and** timestamps. A single large commit or vague messages will be penalized.

### Commit format — Conventional Commits
```
<type>: <short description in English>
```

| Type | When to use |
|---|---|
| `feat` | Adding a new feature or endpoint |
| `fix` | Fixing a bug or incorrect behavior |
| `refactor` | Restructuring code without changing behavior |
| `chore` | Project setup, config files, dependencies, seeders |
| `docs` | README or documentation updates |
| `test` | Adding or updating tests |

## 📊 Evaluation Criteria

| Criterion | Weight | What we look for |
|---|---|---|
| **Problem Solving** | 30% | Business rules handled correctly, edge cases covered |
| **Code Quality** | 30% | Readable, organized, no duplication, proper structure |
| **Git History** | 20% | Clear messages, atomic commits, logical progression |
| **API Design** | 20% | Correct HTTP status codes, consistent response format |

### 🎁 Bonus points (not required)
- [ ] Unit or integration tests
- [ ] Postman collection or Swagger documentation
- [ ] Rate limiting on authentication endpoints
- [ ] A minimal frontend interface

---

## 💡 Tips

- **Commit after each feature** — we want to see your progression, not just the final result.
- **Read the business rules carefully** — they are the core of this test.
- **Keep it simple** — clean and working beats complex and broken.
- If something is ambiguous, make a decision and **document your reasoning** in your README.

---

## 📬 Submission

1. Make sure your private repo is up to date
2. Confirm **`[soca-tech]`** has been added as a collaborator
3. Send your repo link to: **[w.charfi@socainternational.com]**

**Deadline: 24 hours after receiving this test.**

Good luck! 🚀
