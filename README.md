# 7ContextAPILearning

A minimal React + Vite app demonstrating the Context API to share a `user` object and `setUser` across components.

Quick start

```bash
npm install
npm run dev
```

Build

```bash
npm run build
npm run preview
```

Key files

- src/main.jsx — app entry
- src/App.jsx — wraps UI with `UserContextProvider`
- src/Context/UserContext.js — `React.createContext()`
- src/Context/UserContextProvider.jsx — provides `{ user, setUser }`
- src/Components/Login.jsx — sets user via `setUser`
- src/Components/Profile.jsx — reads `user` from context

What `UserContext` and `UserContextProvider` do

- `UserContext`: the shared context object created with `React.createContext()`; used with `useContext(userContext)`.
- `UserContextProvider`: holds `user` via `useState(null)`, provides `{ user, setUser }` to descendants using `<userContext.Provider>` and wraps the app.

Usage flow

1. `Login` calls `setUser({ username, password })`.
2. `Profile` reads `user` and renders accordingly.

Notes

- Fix: in `Profile.jsx` change `if(!user) return` to `if (!user) return (<div>Please Login</div>);` to avoid an empty render.
- This example keeps passwords in memory only — use proper auth for production.

Improvements

- Persist `user` to `localStorage` and restore on load.
- Add `signOut()` helper and input validation.
- Migrate to TypeScript or add PropTypes for typing.

If you'd like, I can patch `Profile.jsx` now or add `localStorage` persistence.
