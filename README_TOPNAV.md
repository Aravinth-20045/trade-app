Migration: Replace existing header(s) with the single `TopNav` component

1. Remove duplicate header components

- Search the project for any existing header or navbar components (e.g., `Navbar`, `Header`, `TopHeader`, `IQOptionLayout`) and remove or comment-out their render calls so only one top nav remains.

2. Import and use `TopNav`

- Add the import in your app entry (e.g., `src/App.jsx`):

```js
import TopNav from './components/TopNav';
```

- Add the component near the top of your app layout, inside the centered `container-lg`:

```jsx
<TopNav
  activeView={view}
  setActiveView={setView}
  isConnected={isConnected}
  balance={{ cash: cashBalance, equity: equity }}
  onOpenSettings={() => setShowSettings(true)}
  onToggleTheme={() => toggleTheme()}
  hideTopNav={false}
/>
```

3. Use `container-lg` to center content

- Wrap the main grid in a `container-lg` and use Bootstrap `row` / `col` classes for the 3-column layout:

```jsx
<div className="container-lg">
  <div className="row gx-3">
    <div className="col-auto" style={{width:280}}>{/* Assets */}</div>
    <div className="col">{/* Chart */}</div>
    <div className="col-auto" style={{width:320}}>{/* Ancillary */}</div>
  </div>
</div>
```

Notes
- `TopNav` uses CSS variables for colors; keep your theme injector to set `--bg-secondary`, `--accent`, `--text-primary`, etc.
- If embedding inside another app set `hideTopNav={true}` to avoid duplicates.
