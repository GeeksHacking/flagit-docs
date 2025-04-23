# 📘 Flagit Documentation

Welcome to the **Flagit** docs! Check out the Table of Contents to navigate to other pages or scroll down to see an overview of the technical architecture.

## 📚 Table of Contents

- [Rationale](./rationale.md)
- [Technical Decisions](./technical-decisions.md)

---

## 🏗️ Overview of Technical Architecture

Flagit is comprised of a few key components:

### 1. Dashboard

A **NextJS web app** serving as the main user interface for viewing data collected by Flagit.

### 2. Query API

An **API wrapper around Firebase**, enabling access to the database by both the Dashboard and the Bot.

### 3. Bot

A set of **Bot implementations** that convert received messages into anonymous, cacheable data.
There is one implementation for each communication platform we support.

### 🔄 Data Flow

Flagit follows a **uni-directional data flow** model:
**Bot → Query API → Dashboard**

You can view the data flow chart here:
🔗 [Flagit Data Flow (Lucidchart)](https://lucid.app/lucidchart/74546a77-8398-4c58-9c8e-2d86b31f1028/edit?viewport_loc=60%2C185%2C1579%2C873%2C0_0&invitationId=inv_30aee402-57e0-4c57-9679-9da9734cc769)

#### Key Flows:

- **Authentication Flow**
- **Chat Group Linking Flow**

After setup, user actions are minimal:

- ✅ A **Community Admin** can **flag a message**
- 📊 **User engagement metrics** are collected **automatically**

In both cases, data flows automatically from **Bot → Query API → Dashboard**, where it can be queried as needed.

---

## 🧾 Nomenclature

| Term | Description |
|------|-------------|
| **Flagit User** | A Community Manager with a Flagit Account |
| **Flagit User ID** | An identifier for a Flagit Account (email) |
| **Flagit Community** | A Community with one or more Managers and zero or more Groups |
| **Flagit Community ID** | A UUID identifying a Community |
| **Group** | A platform-specific group (e.g., Telegram Group, Discord Server) |
| **Group ID** | A UUID identifying a Group |
| **Group Admin ID** | A Platform User ID identifying a Group Administrator |
| **Platform** | A social messaging platform (e.g., Telegram, Discord) |
| **Platform Type** | Name of the platform as a string (e.g., "Telegram") |
| **Platform User ID** | Platform-specific user identifier (e.g., UUID for Telegram) |

⚠️ In practice, we will refer to specific platforms directly, like:
`Telegram`, `Telegram User ID`, `Telegram Channel`, `Telegram Group`, etc. as opposed to `Platform`, `Platform User ID`
