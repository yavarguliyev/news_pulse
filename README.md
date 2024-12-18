# Scalable News Website with User Chat and Admin Panel

## Project Name
**News Pulse**

## Objective
Create a cost-effective, user-friendly news platform that:
- Supports high traffic of up to 1,000,000 logins per day.
- Periodically scrapes and displays news articles with pagination and search functionality.
- Provides a real-time user chat feature.
- Includes an admin dashboard for user statistics and activity monitoring.

## Key Features
1. **High Traffic Handling:** Scalable architecture to manage high user load.
2. **News Scraping System:** Fetches and updates news articles periodically.
3. **Pagination and Search:** Users can browse articles by date or keyword.
4. **Real-time User Chat:** Facilitates seamless communication among users.
5. **Admin Dashboard:** Supervisors can monitor user activities and statistics.

---

## Tech Stack

| Component          | Technology              |
|--------------------|-------------------------|
| Backend            | Node.js, Express.js     |
| Frontend           | React.js               |
| Database           | PostgreSQL             |
| News Scraping      | Puppeteer (Headless Chrome) |
| Caching            | Redis                  |
| Messaging          | WebSocket (Socket.IO)  |
| Admin Dashboard    | React.js + Chart.js    |
| Deployment         | Docker, Kubernetes, AWS|
| Load Balancing     | NGINX + AWS ALB        |
| Monitoring         | Prometheus + Grafana   |
| IP Management      | Proxy rotation via Smartproxy or similar|

---

## System Architecture

### High-Level Diagram

### Description of Components

1. **Frontend**: Built with React.js to provide an intuitive interface for users and admins.
2. **Backend API**: A Node.js/Express.js service for handling user requests, chat messages, and admin actions.
3. **News Scraper**:
   - Utilizes Puppeteer to scrape news from target websites.
   - Handles dynamic page structures and uses proxies to manage IP limits.
4. **Database**:
   - PostgreSQL for storing user data, news articles, and chat messages.
   - Redis for caching frequently accessed data (e.g., news articles).
5. **WebSockets**: Enables real-time chat functionality with low latency.
6. **Admin Dashboard**: Allows supervisors to view user activity and statistics.
7. **Load Balancer**: Distributes traffic evenly across backend servers.
8. **Monitoring Tools**: Prometheus and Grafana track system performance and logs.

---

## Component Communication

| Source Component | Target Component | Communication Interface |
|-------------------|------------------|--------------------------|
| Frontend          | Backend          | REST API (JSON over HTTP)|
| Frontend          | Backend          | WebSocket                |
| Backend           | News Scraper     | API Calls / Scheduler    |
| Backend           | Database         | PostgreSQL Driver (SQL)  |
| Backend           | Cache            | Redis                    |
| Backend           | Frontend         | JSON Responses           |
| Admin Dashboard   | Backend          | REST API (JSON over HTTP)|

---

## News Scraping System Diagram

### Components of News Scraping System
1. **Scheduler**:
   - Triggers scraping jobs periodically.
   - Uses Cron-like scheduling in Node.js.
2. **Scraper Engine**:
   - Built with Puppeteer to handle HTML page parsing.
   - Implements retries and error handling for dynamic content.
3. **Proxy Pool**:
   - Rotates IPs to prevent rate-limiting.
   - Managed using a library or paid service.
4. **Data Storage**:
   - Stores parsed articles in PostgreSQL.
   - Frequently accessed articles are cached in Redis.

---

## Folder Structure

```
news_pulse/
├── backend/
│   ├── src/
│   │   ├── controllers/
│   │   ├── services/
│   │   ├── routes/
│   │   ├── models/
│   │   └── utils/
│   └── tests/
├── frontend/
│   ├── public/
│   ├── src/
│   │   ├── components/
│   │   ├── pages/
│   │   ├── hooks/
│   │   └── utils/
├── scraper/
│   ├── engines/
│   ├── proxies/
│   └── scheduler/
├── admin-panel/
│   ├── src/
│   │   ├── components/
│   │   ├── pages/
│   │   └── utils/
└── README.md
```

---

## Roadmap

1. **Phase 1:** Backend and Frontend Setup.
   - Implement REST APIs for user authentication and news fetching.
   - Build frontend for user interaction.

2. **Phase 2:** News Scraping System.
   - Develop scraper with Puppeteer.
   - Set up IP proxy rotation.

3. **Phase 3:** Real-time Features.
   - Add WebSocket-based chat functionality.

4. **Phase 4:** Admin Panel.
   - Build React-based dashboard with user statistics.

5. **Phase 5:** Deployment and Monitoring.
   - Dockerize services and deploy to AWS.
   - Implement Prometheus and Grafana for monitoring.

---

## Cost-Effective Practices
1. **Proxies**: Use pay-as-you-go IP rotation services.
2. **Caching**: Reduce database load with Redis.
3. **Auto-scaling**: Use Kubernetes for dynamic scaling.
4. **Open Source**: Leverage free and open-source tools like Puppeteer and Grafana.

---

## Setup Instructions

1. Clone the repository:
   ```bash
   git clone git@github.com:yavarguliyev/news_pulse.git
   ```
---
