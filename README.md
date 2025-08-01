# Bema Integrated Services - Developer Skills Test Submission

## 📘 Overview

This project is a comprehensive submission for the **Software Developer Skills Test**. It features a **Next.js** frontend application connected to a **headless WordPress** backend.

The application showcases proficiency in:
- Consuming data via both **GraphQL** and **REST API**
- Handling **internal** and **external** data sources
- Creating **custom WordPress API endpoints**

This README outlines the project structure, setup instructions, and key technical insights discovered during development.

---

## 🚀 Key Features & Skills Demonstrated

- **Headless WordPress Setup**  
  Configured using *Local by Flywheel* to serve as the CMS.

- **GraphQL API Consumption**  
  Utilized `graphql-request` to fetch site settings and blog posts from WPGraphQL.

- **Next.js Development**  
  Demonstrated both server-side (`getStaticProps`) and client-side (`useEffect`) data fetching in functional React components.

- **External REST API Integration**  
  Integrated a 3rd-party exchange rate API with dynamic error handling and API key management.

- **Internal REST API Consumption**  
  Built a custom form component interacting with WordPress REST endpoints.

- **Custom WordPress Endpoint**  
  Created a REST endpoint via `register_rest_route` to handle `POST` and `GET` requests.

- **Problem-Solving & Adaptability**  
  Debugged and resolved issues related to deprecated/non-functional endpoints, showcasing resilience and adaptability.

---

## 🛠 Technology Stack

- **Frontend**: Next.js, React  
- **Backend**: WordPress (Headless CMS)  
- **APIs**: WPGraphQL, REST API  
- **Environment**: Local by Flywheel  
- **Styling**: CSS Modules (`globals.css`)

---

## ⚙️ Setup Instructions

### 1️⃣ Backend (WordPress)

- Set up a local WordPress site using **Local by Flywheel** (e.g., `wp-headless-test`)
- Install and activate:
  - `WPGraphQL`
  - `Easy Digital Downloads`
- Go to **Settings > Permalinks** and select **"Post name"** to ensure proper REST API functionality.
- Add the following snippets to your active theme’s `functions.php`:

**Custom REST Endpoint for Name Form**
```php
// Add your custom REST logic here

2️⃣ Frontend (Next.js)
Clone/download this repo and open the wp-next-test folder
Install dependencies:
npm install

Create a .env.local file in the root and add:
# Your local WordPress site URL
WORDPRESS_GRAPHQL_ENDPOINT=http://wp-headless-test.local/graphql
NEXT_PUBLIC_WORDPRESS_API_URL=http://wp-headless-test.local/wp-json

# API key from exchangerate-api.com
NEXT_PUBLIC_EXCHANGE_RATE_API_KEY=YOUR_API_KEY_HERE

3️⃣ Running the App
Start the development server:
npm run dev

Open http://localhost:3000 in your browser.
Run the standalone exchange rate script:
node exchange-rate.js
Note: Ensure you set the API_ACCESS_KEY inside exchange-rate.js.

🧪 Technical Notes & Findings
1. ⚠️ External Exchange Rate API
Issue: https://api.exchangerate.host/... was non-functional and returned 404.

Action: Switched to https://www.exchangerate-api.com with a free API key.

Outcome: Feature works and showcases adaptability to real-world API shifts.

2. ⚠️ Internal EDD REST API Endpoint (/edd/v1/settings)
Issue: The endpoint /wp-json/edd/v1/settings was not available.

Investigation:

Possible deprecation or plugin version change

Conditional route registration (e.g., only after setup wizard)

Outcome: The feature could not be implemented. The logic remains in the codebase for review. The API index at /wp-json/ can be shown during evaluation to confirm its absence.

✅ Conclusion
This project not only fulfills the technical requirements but also highlights the ability to adapt to unforeseen issues, debug effectively, and implement real-world solutions.

Feel free to explore the code and reach out with any questions or review requests.


Paste this directly into your project as `README.md`. Let me know if you also need a sample project folder structure or want the PHP snippets for the WordPress side.



