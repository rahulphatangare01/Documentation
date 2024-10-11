# React Router

<details>
<summary>
1.  <b> What is React Router? Why do we need it? </b>
</summary>

React Router is a standard library for routing in React. It enables navigation between different views or components in a React application, allowing users to change the browser URL and the application view accordingly.

React Router provides a declarative way to navigate in a single-page application (SPA), helping manage URL transitions and keeping the UI in sync with the URL.

</details>

<details>
<summary>
2.  <b> What are the main components of React Router?</b>
</summary>

The main components of React Router are:

- `<BrowserRouter>`: Wraps your entire application and enables routing.
- `<Routes>`: Contains all your routes.
- `<Route>`: Defines a path and the component to render when the path matches.

- `<Link>`: Provides declarative, accessible navigation around your application.
- `<Navigate>`: Programmatic navigation for redirects.
</details>

<details>
<summary>
3.  <b>How to create a basic route in React Router? </b>
</summary>

```jsx harmony
import { BrowserRouter, Routes, Route } from "react-router-dom";
import Home from "./Home";
import About from "./About";

function App() {
  return (
    <BrowserRouter>
      <Routes>
        <Route path="/" element={<Home />} />
        <Route path="/about" element={<About />} />
      </Routes>
    </BrowserRouter>
  );
}

export default App;
```

Here, `/` will render the` Home` component, and `/about` will render the `About` component.

</details>

<details>
<summary>
4.  <b>How can you pass parameters in React Router? </b>
</summary>
You can pass parameters in the URL using dynamic routing with React Router.

```jsx harmony
import { useParams } from "react-router-dom";

function User() {
  const { userId } = useParams();
  return <h1>User ID: {userId}</h1>;
}

function App() {
  return (
    <BrowserRouter>
      <Routes>
        <Route path="/user/:userId" element={<User />} />
      </Routes>
    </BrowserRouter>
  );
}

export default App;
```

When you navigate to `/user/123`, it will display: `User ID: 123`

</details>

<details>
<summary>
5.  <b>What is the difference between `Link` and `a` Tag  in React Router?</b>
</summary>

- `<Link>`: It provides client-side navigation, meaning it doesn’t reload the page, and only the URL and view are updated.
- `<a>:` It performs a full-page reload and navigates to the linked page, which causes the React app to reset.

```jsx harmony
<Link to="/about">Go to About</Link>
```

</details>

<details>
<summary>
6.  <b> How do you handle programmatic navigation in React Router?</b>
</summary>

You can use the `useNavigate` hook for programmatic navigation.

```jsx harmony
import { useNavigate } from "react-router-dom";

function Home() {
  const navigate = useNavigate();

  const goToAbout = () => {
    navigate("/about");
  };

  return <button onClick={goToAbout}>Go to About</button>;
}

export default Home;
```

Clicking the button will programmatically navigate to the `/about` page.

</details>

<details>
<summary>
7.  <b>What is the purpose of the <Navigate> component? </b>
</summary>

The `<Navigate>` component is used to redirect from one route to another.

```jsx haromny
import { Navigate } from "react-router-dom";

function ProtectedRoute({ isAuth }) {
  if (!isAuth) {
    return <Navigate to="/login" />;
  }

  return <h1>Protected Page</h1>;
}
```

If `isAuth` is `false`, it will redirect to the `/login` route.

</details>

<details>
<summary>
8.  <b> What are Switch and Routes? How do they differ? </b>
</summary>

In earlier versions of React Router, Switch was used to group routes and render only the first match. In React Router v6, Routes has replaced Switch.

- `Switch` (React Router v5): Renders the first matching route.
- `Routes` (React Router v6): Uses child `<Route>` elements to match paths.

```jsx harmony
import { Routes, Route } from "react-router-dom";

function App() {
  return (
    <Routes>
      <Route path="/" element={<Home />} />
      <Route path="/about" element={<About />} />
    </Routes>
  );
}
```

</details>
<details>
<summary>
9.  <b>How do you handle 404 errors in React Router? </b>
</summary>

You can define a "catch-all" route using a wildcard `(*)` to handle non-existent routes (404 errors).

```jsx harmony
function NotFound() {
  return <h1>404 - Page Not Found</h1>;
}

function App() {
  return (
    <BrowserRouter>
      <Routes>
        <Route path="/" element={<Home />} />
        <Route path="/about" element={<About />} />
        <Route path="*" element={<NotFound />} />
      </Routes>
    </BrowserRouter>
  );
}

export default App;
```

If no route matches, the NotFound component will be rendered.

</details>
<details>
<summary>
10.  <b> What is lazy loading in React Router? </b>
</summary>

Lazy loading is a performance optimization technique where you load components only when they are needed. In React Router, it can be implemented using `React.lazy.`

```jsx harmony
import React, { Suspense, lazy } from "react";
import { BrowserRouter, Routes, Route } from "react-router-dom";

const Home = lazy(() => import("./Home"));
const About = lazy(() => import("./About"));

function App() {
  return (
    <BrowserRouter>
      <Suspense fallback={<div>Loading...</div>}>
        <Routes>
          <Route path="/" element={<Home />} />
          <Route path="/about" element={<About />} />
        </Routes>
      </Suspense>
    </BrowserRouter>
  );
}

export default App;
```

This will load the `Home` and `About` components only when the respective routes are visited, improving initial load time.

</details>

## Routing Advance Questions

<details>
<summary>
11.  <b> How do you implement protected routes in React Router?</b>
</summary>

A protected route restricts access to a specific part of the app unless the user is authenticated. You can implement this by creating a wrapper around the `<Route>` component and conditionally rendering the content based on authentication status.

```jsx harmony
import { Navigate } from "react-router-dom";

function ProtectedRoute({ isAuth, children }) {
  return isAuth ? children : <Navigate to="/login" />;
}

function App() {
  const isAuthenticated = true; // Replace with actual authentication logic

  return (
    <BrowserRouter>
      <Routes>
        <Route path="/login" element={<Login />} />
        <Route
          path="/dashboard"
          element={
            <ProtectedRoute isAuth={isAuthenticated}>
              <Dashboard />
            </ProtectedRoute>
          }
        />
      </Routes>
    </BrowserRouter>
  );
}

export default App;
```

If `isAuth` is `true`, the `Dashboard` component is rendered; otherwise, the user is redirected to the login page.

</details>

<details>
<summary>
12.  <b> How do you handle role-based authentication in React Router? </b>
</summary>

For role-based access control, you can enhance the protected route logic to check for specific roles, ensuring only authorized users can access certain routes.

```jsx harmony
import { Navigate } from "react-router-dom";

function RoleProtectedRoute({ isAuth, role, allowedRoles, children }) {
  if (!isAuth) {
    return <Navigate to="/login" />;
  }
  if (!allowedRoles.includes(role)) {
    return <Navigate to="/not-authorized" />;
  }
  return children;
}

function App() {
  const isAuthenticated = true;
  const userRole = "admin"; // Example role, could be dynamic

  return (
    <BrowserRouter>
      <Routes>
        <Route path="/login" element={<Login />} />
        <Route path="/not-authorized" element={<NotAuthorized />} />
        <Route
          path="/admin"
          element={
            <RoleProtectedRoute
              isAuth={isAuthenticated}
              role={userRole}
              allowedRoles={["admin"]}
            >
              <AdminDashboard />
            </RoleProtectedRoute>
          }
        />
        <Route
          path="/user"
          element={
            <RoleProtectedRoute
              isAuth={isAuthenticated}
              role={userRole}
              allowedRoles={["user", "admin"]}
            >
              <UserDashboard />
            </RoleProtectedRoute>
          }
        />
      </Routes>
    </BrowserRouter>
  );
}

export default App;
```

Here, only users with the `admin` role can access the `AdminDashboard`. Users with either the `user` or `admin` role can access the `UserDashboard`.

</details>

<details>
<summary>
13.  <b>How can you implement authentication persistence in protected routes? </b>
</summary>

To persist authentication across page reloads, you can store the authentication token in local storage or cookies. The protected route will check this stored value to determine if the user is authenticated.

```jsx harmony
import { Navigate } from "react-router-dom";

function ProtectedRoute({ children }) {
  const token = localStorage.getItem("authToken"); // Check token in local storage
  return token ? children : <Navigate to="/login" />;
}

function App() {
  return (
    <BrowserRouter>
      <Routes>
        <Route path="/login" element={<Login />} />
        <Route
          path="/dashboard"
          element={
            <ProtectedRoute>
              <Dashboard />
            </ProtectedRoute>
          }
        />
      </Routes>
    </BrowserRouter>
  );
}

export default App;
```

In this example, the `authToken` is checked in local storage. If it's missing, the user is redirected to the login page.

</details>

<details>
<summary>
14.  <b>How do you redirect users after login in React Router? </b>
</summary>

After a successful login, you can use `useNavigate` from React Router to redirect the user to a protected page.

```jsx harmony
import { useNavigate } from "react-router-dom";

function Login() {
  const navigate = useNavigate();

  const handleLogin = () => {
    // Perform authentication logic here
    localStorage.setItem("authToken", "your_token");
    navigate("/dashboard"); // Redirect to dashboard after login
  };

  return <button onClick={handleLogin}>Login</button>;
}

function App() {
  return (
    <BrowserRouter>
      <Routes>
        <Route path="/login" element={<Login />} />
        <Route
          path="/dashboard"
          element={
            <ProtectedRoute>
              <Dashboard />
            </ProtectedRoute>
          }
        />
      </Routes>
    </BrowserRouter>
  );
}

export default App;
```

After setting the `authToken`, the user is redirected to the dashboard using the `useNavigate` hook.

</details>

<details>
<summary>
15.  <b>  How can you create a loading spinner or guard before route access?</b>
</summary>

You can implement a loading state that shows a spinner while checking the user's authentication or authorization status (e.g., validating a token from an API).

```jsx harmony
import { useState, useEffect } from "react";
import { Navigate } from "react-router-dom";

function ProtectedRoute({ children }) {
  const [loading, setLoading] = useState(true);
  const [isAuth, setIsAuth] = useState(false);

  useEffect(() => {
    // Simulate async authentication check
    setTimeout(() => {
      const token = localStorage.getItem("authToken");
      setIsAuth(!!token);
      setLoading(false);
    }, 1000); // Simulating network delay
  }, []);

  if (loading) {
    return <div>Loading...</div>; // Show spinner while loading
  }

  return isAuth ? children : <Navigate to="/login" />;
}

function App() {
  return (
    <BrowserRouter>
      <Routes>
        <Route path="/login" element={<Login />} />
        <Route
          path="/dashboard"
          element={
            <ProtectedRoute>
              <Dashboard />
            </ProtectedRoute>
          }
        />
      </Routes>
    </BrowserRouter>
  );
}

export default App;
```

This example simulates an authentication check with a delay. While the app is loading, a spinner `(Loading...)` is displayed, and then it proceeds based on the authentication status.

</details>

<details>
<summary>
16.  <b>How do you handle logout and clearing the authentication state in React Router? </b>
</summary>
You can implement logout by clearing the authentication token and redirecting the user to the login page.

```jsx harmony
import { useNavigate } from "react-router-dom";

function Dashboard() {
  const navigate = useNavigate();

  const handleLogout = () => {
    localStorage.removeItem("authToken"); // Remove token
    navigate("/login"); // Redirect to login
  };

  return (
    <div>
      <h1>Welcome to the Dashboard</h1>
      <button onClick={handleLogout}>Logout</button>
    </div>
  );
}

export default Dashboard;
```

The `handleLogout` function clears the authentication token from local storage and redirects the user back to the login page using the `useNavigate` hook.

</details>

<details>
<summary>
17.  <b>How can you protect routes based on different types of authentication (OAuth, JWT, etc.) in React Router? </b>
</summary>

You can use various authentication strategies like OAuth or JWT to protect routes. For example, with JWT, you would store the token after login and check its validity in the protected route.

```jsx harmony
import { Navigate } from "react-router-dom";

function ProtectedRoute({ children }) {
  const token = localStorage.getItem("authToken");
  // Add JWT token validation here (e.g., decode and check expiration)
  const isTokenValid = token && /* token validation logic */ true;

  return isTokenValid ? children : <Navigate to="/login" />;
}

export default ProtectedRoute;
```

In this case, you would validate the JWT (checking expiration or claims) before allowing access to the route. If the token is invalid, the user is redirected to the login page.

</details>
