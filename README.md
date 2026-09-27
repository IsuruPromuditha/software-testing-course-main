# 🛒 TechMart API Automation Suite (Playwright + KaneAI)

![Playwright](https://img.shields.io/badge/Playwright-1.x-brightgreen?logo=playwright)
![Node.js](https://img.shields.io/badge/Node.js-%3E%3D18.x-green?logo=nodedotjs)
![KaneAI](https://img.shields.io/badge/QA%20Engine-KaneAI-blue)
![License](https://img.shields.io/badge/License-MIT-yellow)

An end-to-end REST API automated testing framework for the **TechMart** web application built with **Playwright Test APIRequestContext** and powered by **KaneAI** for intelligent test generation, execution, and reporting.

---

## 📌 Project Overview

This test suite validates core backend features of the **TechMart REST API**, ensuring high reliability, precise HTTP status code compliance, data model integrity, and proper error handling.

By utilizing Playwright's native API execution engine alongside KaneAI's agentic testing capability, this project achieves:
- **Fast Execution**: Pure HTTP request testing without web browser overhead.
- **Isolated State**: Automated dynamic test data generation and state cleanups.
- **Robust Assertions**: Comprehensive validations on HTTP headers, status codes, payload structures, and response bodies.

---

## 📑 Test Coverage Matrix

| Module | Endpoint | Method | Test Scenarios |
| :--- | :--- | :--- | :--- |
| **Products** | `/api/products` | `GET` | Get all products, category filtering, search keyword query |
| **Products** | `/api/products/:id` | `GET` | Fetch product by ID, handle non-existent ID (404) |
| **Cart** | `/api/cart` | `GET` | Fetch empty/populated cart |
| **Cart** | `/api/cart` | `POST` | Add item, validate invalid product handling |
| **Cart** | `/api/cart/:productId` | `PUT` | Update product quantity |
| **Cart** | `/api/cart/:productId` | `DELETE` | Remove single item from cart |
| **Cart** | `/api/cart` | `DELETE` | Clear entire cart (Used in `beforeEach` hooks) |
| **Auth** | `/api/login` | `POST` | Valid login, invalid credentials (401), missing payload (400) |
| **Auth** | `/api/register` | `POST` | Create new user with dynamic email generation |
| **Health** | `/api/health` | `GET` | System operational health & timestamp verification |

---

## 🛠️ Tech Stack & Key Tools

- **Automation Engine**: [Playwright Test](https://playwright.dev/) (`@playwright/test`)
- **AI Agent Execution**: [KaneAI](https://www.testmuai.com/kane-ai/)
- **Type Checking**: JSDoc with JSHint `@ts-check` for static type enforcement
- **Language**: JavaScript (Node.js ES6+)

---

## 📂 Project Directory Structure

```text
.
├── tests/
│   └── api.spec.js          # Core REST API test specs
├── playwright.config.js     # Global Playwright configuration
├── package.json             # NPM dependencies and scripts
└── README.md                # Project documentation
