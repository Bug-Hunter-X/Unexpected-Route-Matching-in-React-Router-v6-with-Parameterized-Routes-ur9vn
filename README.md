# Unexpected Route Matching in React Router v6

This repository demonstrates a subtle bug in React Router v6 related to route matching order when using parameterized routes.  If a route with parameters (e.g., `/users/:id`) is defined before a more general route (e.g., `/`), the parameterized route will incorrectly match the general route, leading to unexpected component rendering.

## Problem Description

The provided `bug.js` file contains a simple React application using `react-router-dom` v6.  The routing configuration includes routes for `/`, `/about`, and `/users/:id`.  However, due to the order of route definitions, navigating to `/` unintentionally triggers the `/users/:id` route, causing the `User` component to render instead of the `Home` component.

## Solution

The `bugSolution.js` file demonstrates the solution: simply rearrange the route order to define the more specific routes (those with parameters) after the more general routes. By placing the route `/` before the `/users/:id`, the correct component will render for each path.

## Setup

1. Clone this repository.
2. Run `npm install` to install dependencies.
3. Run `npm start` to start the development server.