

# 🌍 Yatrai-Local-Connect

## Overview

**Yatrai-local-connect** is a full-stack web application developed to help users discover and organize travel destinations efficiently. The application provides destination information, ratings, estimated costs, and location details through an intuitive and responsive interface.

The system combines modern frontend technologies with a robust backend and database architecture to provide users with a seamless travel-planning experience.

---

# Objectives

* Help users discover tourist destinations.
* Store and retrieve travel information efficiently.
* Provide ratings and estimated travel expenses.
* Offer a responsive and user-friendly interface.
* Maintain scalable and organized code architecture.

---

# Technology Stack

| Layer            | Technology   |
| ---------------- | ------------ |
| Frontend         | React.js     |
| Language         | TypeScript   |
| Styling          | Tailwind CSS |
| Backend          | Node.js      |
| Server Framework | Express.js   |
| Database         | PostgreSQL   |
| ORM              | Drizzle ORM  |
| Validation       | Zod          |
| Deployment       | Replit       |

---

# System Architecture

```text
User
 ↓
React Frontend
 ↓
Express Server
 ↓
Drizzle ORM
 ↓
PostgreSQL Database
 ↓
JSON Response
 ↓
User Interface
```

---

# Project Structure

```text
Travel-Companion
│
├── client
│    ├── src
│    │     ├── components
│    │     ├── pages
│    │     ├── hooks
│    │     └── App.tsx
│
├── server
│    ├── index.ts
│    ├── routes.ts
│    └── db.ts
│
├── shared
│    └── schema.ts
│
├── package.json
└── tsconfig.json
```

---

# Database Schema

```typescript
import { pgTable, text, serial, real, integer } from "drizzle-orm/pg-core";

export const placesTable = pgTable("places", {
  id: serial("id").primaryKey(),
  name: text("name").notNull(),
  direction: text("direction").notNull(),
  rating: real("rating"),
  cost: integer("cost"),
});
```

## Explanation

### id

```typescript
id: serial("id").primaryKey()
```

* Unique identifier.
* Auto-incremented.

---

### name

```typescript
name: text("name").notNull()
```

Stores the name of the place.

Example:

* Goa Beach
* Ooty Hills
* Mysore Palace

---

### direction

```typescript
direction: text("direction").notNull()
```

Stores the location or address.

Example:

```text
North Goa
Mysore, Karnataka
Ooty, Tamil Nadu
```

---

### rating

```typescript
rating: real("rating")
```

Stores decimal ratings.

Example:

```text
4.3
4.7
4.9
```

---

### cost

```typescript
cost: integer("cost")
```

Stores estimated expenditure.

Example:

```text
5000
8000
12000
```

---

# Backend API

Example:

```typescript
app.get("/api/places", async (req, res) => {

  const places = await db.select()
                         .from(placesTable);

  res.json(places);

});
```

## Working

1. Client sends a request.
2. Express receives the request.
3. Drizzle ORM queries PostgreSQL.
4. Data is returned as JSON.
5. React displays the results.

---

# React Component

```tsx
function PlaceCard({ place }) {

  return (

    <div className="card">

      <h2>{place.name}</h2>

      <p>{place.direction}</p>

      <p>Rating: {place.rating}</p>

      <p>Cost: ₹{place.cost}</p>

    </div>

  );

}
```

---

# Sample Output

```text
Goa Beach

Location : North Goa

Rating : 4.8

Estimated Cost : ₹5000
```

---

# Features

### ✓ Destination Search

Allows users to browse places.

### ✓ Ratings

Displays reviews and ratings.

### ✓ Budget Estimation

Provides approximate expenses.

### ✓ Responsive Design

Compatible with mobile and desktop devices.

### ✓ Database Connectivity

Uses PostgreSQL with Drizzle ORM.

### ✓ Type Safety

Implemented using TypeScript.

---

# Advantages

* Easy to use.
* Scalable architecture.
* Fast data retrieval.
* Organized code structure.
* Responsive UI.
* Secure backend communication.

---

# Future Enhancements

* User authentication.
* Google Maps integration.
* AI-based trip recommendation.
* Hotel booking system.
* Weather forecasting.
* Expense tracker.
* Personalized itineraries.
* Image galleries.
* Wishlist and favorites.
* Multi-language support.

---

# Conclusion

**Travel Companion** is a modern web application designed to simplify travel planning by providing destination information, ratings, directions, and estimated costs through an efficient full-stack architecture. By utilizing React, TypeScript, Express, PostgreSQL, and Drizzle ORM, the project demonstrates the practical implementation of contemporary web technologies while providing users with a reliable and interactive travel-planning platform.

This description is suitable for **project reports, GitHub README files, resumes, and viva examinations**.
