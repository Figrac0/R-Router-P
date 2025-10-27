# React Router Basic Example

This project is a **training setup** built to test and demonstrate the core features of **React Router (v6+)** in a minimal environment.  
It provides a simple page structure with a home view, a product list, and individual product details, showcasing navigation and routing mechanics.

## Purpose

The goal is to explore and understand how client-side routing works in React applications — including nested routes, dynamic segments, navigation hooks, and error handling.

## Key Concepts Demonstrated

- **`createBrowserRouter`** — defines the main router configuration with nested routes and error handling.  
- **`RouterProvider`** — supplies the routing context to the application.  
- **`Outlet`** — renders child route content inside a parent layout.  
- **`Link`** — declarative navigation element used to move between routes without reloading the page.  
- **`useNavigate()`** — hook that enables programmatic navigation within event handlers.  
- **`useParams()`** — retrieves dynamic route parameters from the URL (e.g., product IDs).  
- **`relative="path"`** — controls how relative navigation behaves when using `Link` or `navigate`.  
- **`errorElement`** — defines a fallback UI displayed when a route fails to load or an invalid path is accessed.  
- **`index` route** — defines a default child route rendered at the parent’s path.

## Summary

This repository serves as a **learning sandbox** for understanding and testing React Router fundamentals: route hierarchy, dynamic routing, navigation methods, and relative path handling — all within a simple, isolated setup suitable for experimentation and teaching.
