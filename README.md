# 🎟️ Tickets Service - NestJS + TypeScript (90-Minute Live Coding)

### 🎯 Goal

Build a simple **Tickets** service using **NestJS**, **TypeScript**, and **Prisma (with SQLite)**.

You will implement:

- `GET /tickets`: list tickets (with pagination)
- `POST /tickets`: create a new ticket (with validation)

We’re testing correctness, structure, and clarity - not how many features you add.

---

## 🧩 Requirements

Use the following:

- NestJS (controllers, services, modules)
- TypeScript
- Prisma + SQLite
- class-validator / class-transformer (for DTO validation)

---

## 🧱 Ticket Structure

Each ticket should have the following fields:

| Field       | Type              | Notes                      |
| ----------- | ----------------- | -------------------------- |
| id          | string            | Unique ID                  |
| title       | string            | Required, 1–200 characters |
| description | string (optional) | Optional                   |
| createdAt   | DateTime          | Set on create              |
| updatedAt   | DateTime          | Updated automatically      |

---

## 🧩 Endpoints

### 1️⃣ GET /tickets

List all tickets, newest first.

**Query params:**

- `page` (default: 1)
- `pageSize` (default: 20)

**Response:**

```json
{
  "items": [
    {
      "id": "abc123",
      "title": "Printer issue",
      "description": "It won't print",
      "createdAt": "2025-10-08T10:00:00Z",
      "updatedAt": "2025-10-08T10:00:00Z"
    }
  ],
  "page": 1,
  "pageSize": 20,
  "total": 42
}
```

### 2️⃣ POST /tickets

Create a new ticket.

**Request Body**

```json
{
  "title": "Printer issue",
  "description": "It won't print"
}
```

**Validation:**

- `title`: required, string, 1–200 chars
- `description`: optional string

**Response**

```json
{
  "id": "abc123",
  "title": "Printer issue",
  "description": "It won't print",
  "createdAt": "2025-10-08T10:00:00Z",
  "updatedAt": "2025-10-08T10:00:00Z"
}
```

---

## Setup

1. Install dependencies

```bash
npm install
```

2. Define your prisma schema for the ticket model (as above)

3. Run migration

```bash
npx prisma migreate dev --name init
```

4. Start the app

```bash
npm run start:dev
```

---

## ✅ What We’re Looking For

- Correct and working endpoints

- Proper validation and clean error handling

- Simple, readable NestJS structure (controller + service)

- Correct pagination and sorting
