# Health Insurance Risk Calculator — Client Application

A static web application built for **Health Insurance, Inc.** that allows potential customers to enter their health information and receive an insurance risk assessment. This client app communicates with a separate Node.js API server to perform all calculations and data validation.

---

## Overview

This application is part of a cloud-hosted SaaS architecture. The client is deployed as an **Azure Static Web Application** and integrates with a Node.js REST API hosted on Azure. All business logic and risk calculations are handled server-side — the client is responsible only for data collection, display, and user experience.

---

## Features

- User-friendly health information form designed for non-technical customers
- Blood pressure category reference chart with selectable systolic/diastolic values
- Height (feet & inches) and weight (lbs) inputs with automatic BMI calculation via API
- Family disease history selection (diabetes, cancer, Alzheimer's)
- Displays full input summary alongside the calculated risk category
- Supports evaluating multiple customers in a single session
- Client-side validation to ensure data integrity before sending API requests
- Console logging on every API call and response

---

## Risk Categories

| Total Score | Risk Category |
|-------------|---------------|
| ≤ 20        | Low Risk      |
| ≤ 50        | Moderate Risk |
| ≤ 75        | High Risk     |
| > 75        | Uninsurable   |

---

## API Integration

This client calls the following endpoints on the Node.js API server:

| Endpoint        | Description                              |
|-----------------|------------------------------------------|
| `/ping`         | Wake-up / health check                   |
| `/bp-category`  | Returns blood pressure category          |
| `/bmi`          | Returns BMI category from height/weight  |
| `/risk-category`| Returns final risk score and category    |

> **Note:** No calculations are performed in the client code. All logic lives in the API server.

---

## Tech Stack

- HTML, CSS, JavaScript
- Hosted on **Microsoft Azure Static Web Apps**
- Source control via **GitHub** with CI/CD pipeline integration

---

## Getting Started

### Prerequisites

- [Node.js](https://nodejs.org/) (for local development tooling)
- [Git](https://git-scm.com/)
- Access to the shared GitHub organization repository
- A running instance of the Health Insurance Risk Calculator API server

### Local Development

1. Clone the repository:
   ```bash
   git clone https://github.com/<your-org>/health-risk-calculator-client.git
   cd health-risk-calculator-client
   ```

2. Configure the API base URL:
   - Open `config.js` (or the relevant config file) and set `API_BASE_URL` to your local or deployed API server address.

3. Open `index.html` in your browser, or use a local dev server:
   ```bash
   npx serve .
   ```

---

## CI/CD

Pushes to the `main` branch automatically trigger the Azure Static Web Apps deployment pipeline. All team members should verify their changes deploy correctly after merging.

---

## Team

| Role           | Name |
|----------------|------|
| Scrum Master   | Bryce     |
| Product Owner  | Ricardo   |
| Developer      | Angelo    |
| Developer      | Bobby     |

---

## Related Repository

- [Health Insurance Risk Calculator — API Server](https://health-insurance-risk-calc-s.azurewebsites.net)