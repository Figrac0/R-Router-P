# ⚡ Advanced React Router Project

Full-featured demonstration of React Router DOM v6.17+ with backend API integration.  
Focuses on advanced routing patterns, deferred loading, async data management, and full CRUD functionality through frontend–backend interaction.

---

## 🚀 Overview

This project showcases the complete potential of React Router DOM by building a fully functional event management system.  
It includes dynamic and nested routing, deferred data loading with Suspense, and real backend communication for data persistence.

The structure combines two main layers:
- **Frontend** built with React and React Router DOM  
- **Backend** powered by Node.js and Express with a file-based data layer


---

## 📸 Project Preview

<h3 align="center">📸 Screenshots</h3>

<p align="center">
  <img src="https://raw.githubusercontent.com/Figrac0/R-Router-P/AdvRouter/frontend/src/assets/1.png" alt="Preview 1" width="450"/><br/>
</p>
<p align="center">
  <img src="https://raw.githubusercontent.com/Figrac0/R-Router-P/AdvRouter/frontend/src/assets/2.png" alt="Preview 2" height="550" width="450"/><br/>
</p>
<p align="center">
  <img src="https://raw.githubusercontent.com/Figrac0/R-Router-P/AdvRouter/frontend/src/assets/3.png" alt="Preview 3" height="550" width="450"/><br/>
</p>
<p align="center">
  <img src="https://raw.githubusercontent.com/Figrac0/R-Router-P/AdvRouter/frontend/src/assets/4.png" alt="Preview 4" height="550" width="450"/><br/>
</p>


## 🧭 Key Features

### Frontend (React Router DOM)

- **Nested Routing**  
  The routing system is organized hierarchically. Parent routes render their child routes using the `<Outlet>` component, creating a clean and scalable structure.

- **Dynamic Segments**  
  The route `/events/:eventId` dynamically renders event details based on the parameter in the URL.

- **Loaders and Actions**  
  Data fetching and data mutation are handled declaratively with React Router’s `loader()` and `action()` functions.

- **Deferred Data Loading**  
  Asynchronous loading of routes is achieved through `defer()` and `Await`, wrapped in React’s `Suspense` component, allowing multiple data sources to be fetched concurrently.

- **Optimistic Updates with useFetcher()**  
  The newsletter form uses `useFetcher()` to handle background form submissions without blocking navigation.

- **Error Handling**  
  Errors are managed at the route level with `errorElement` and `useRouteError()` providing a consistent fallback UI.

- **Navigation Feedback**  
  `useNavigation()` tracks the app’s transition state to indicate loading or submitting progress to the user.

---

### Backend (Node.js + Express)

A minimal RESTful API handles event management, including validation and error handling.  
It provides endpoints for creating, updating, fetching, and deleting events.

**Available Endpoints**
- GET `/events` — fetch all events  
- GET `/events/:id` — fetch single event  
- POST `/events` — create new event  
- PATCH `/events/:id` — update event  
- DELETE `/events/:id` — delete event  

**Validation**  
Each request validates fields such as title, description, date, and image URL using custom functions.  
Invalid input returns structured validation errors.

**Error Handling**  
All server errors are centralized and returned as JSON responses, ensuring predictable API behavior.

**Data Persistence**  
Events are stored in a simple `events.json` file managed with asynchronous file system operations.

---

## 🧩 Tech Stack

### Frontend
- React 19  
- React Router DOM 6.17+  
- CSS Modules  
- Suspense, Await, and Defer APIs  

### Backend
- Node.js 18+  
- Express 4.18+  
- body-parser  
- uuid  

---

## ⚙️ Setup Instructions

**1. Clone the Repository**  
Clone the project and open it in your local environment.

**2. Install Dependencies**  
Run npm install separately for both frontend and backend directories.

**3. Start the Application**  
- The backend runs on `http://localhost:8080`  
- The frontend runs on `http://localhost:3000`

Both layers must be running simultaneously for full functionality.

---

## 📚 Routing Architecture

The routing design includes nested routes and async data loading:
- Home page at `/`
- Events section with:
  - `/events` — displays all events with loader and defer
  - `/events/:eventId` — loads individual event data
  - `/events/:eventId/edit` — edit form for existing event
  - `/events/new` — create new event form
- Newsletter route at `/newsletter` — uses useFetcher for non-blocking form submission

---

## 🧠 Core Concepts Demonstrated

- **Data Loaders** — Prefetching data before rendering components  
- **Actions** — Handling form submissions directly in routes  
- **Nested Routes** — Compositional layout using Outlet  
- **Defer and Await** — Lazy concurrent data fetching  
- **Suspense** — Smooth async rendering for loading states  
- **useFetcher()** — Isolated background form requests  
- **Error Boundaries** — Custom route-level error handling  
- **useNavigation()** — Visual feedback during route changes  
- **Dynamic Params** — URL-driven data loading for detail views  

---



## 📦 Folder Structure

**Frontend**
- `src/components` — Reusable UI and form elements  
- `src/pages` — Route pages with loaders and actions  
- `src/assets` — Image files for preview  
- `src/index.js` — Application entry point  
- `src/App.js` — Router configuration  
- `src/index.css` — Global styling  

**Backend**
- `app.js` — Express application setup  
- `routes/events.js` — REST API routes  
- `data/event.js` — Data persistence logic  
- `util/validation.js` — Input validation utilities  
- `util/errors.js` — Custom error classes  

---

## 📜 License

This project is released under the **MIT License** and is open for educational and professional use.

---

<h3 align="center">Made with ❤️ by <a href="https://github.com/Figrac0">Figrac0</a></h3>
