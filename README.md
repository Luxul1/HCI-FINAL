# McDo Warehouse Inventory & Order Management — Working Front-End

A database-free, browser-based prototype based on the nine uploaded wireframe screenshots. Includes all seven activity modules (Login/User Management, Dashboard, Inventory, Receiving, Orders/Picking, Stock Movement, Reports/Notifications). Reports and Notifications are separate sidebar screens, matching the references.

## Run

1. Unzip the project.
2. Open `index.html` in Chrome, Edge, or Firefox. No npm installation, build step, or server is required.
3. Log in with **admin@mcdo.com** and **admin123**. Other demo accounts: `manager@mcdo.com` / `manager123`, `clerk@mcdo.com` / `clerk123`.

## Features

- Login/logout, required fields, invalid credentials feedback, editable users and roles.
- Dashboard metrics linked to real browser-side inventory, orders, and deliveries.
- Search/filter inventory; product detail, add/edit/delete, minimum-stock alerts, locations, suppliers, and validation.
- Schedule, review, correct, cancel, and confirm deliveries; confirmed receipts increase inventory and record movement.
- Create orders; start picking; mark required products picked; block insufficient stock; move to Ready and Complete; completing releases stock.
- Record Received, Released, Transferred, or Adjusted movements, including review/confirmation, responsible user, before/after values, and searchable audit trail.
- Reports (Inventory, Low Stock, Stock Movement, Orders), searchable tables, chart, CSV export; notifications with unread status, filtering, review links, and dismiss controls.
- Feedback toasts, cancel buttons, confirmation dialogs, error prevention, consistent navigation and controls.

## Demonstration flows

1. Login → Dashboard → Receiving → Schedule Shipment or Review Delivery → Review → Confirm Receipt → verify updated inventory.
2. Dashboard → Orders & Picking → Open Order → Start Picking → mark items → Mark Ready → Complete Order → verify stock released.
3. Dashboard → click Low Stock Items or a specific alert → Inventory → Product Details → Review and optionally Adjust Stock.

## Storage and limitations

All records are stored in **localStorage** in the current browser. Login session is stored in **sessionStorage**. No database or server is used. Data persists after refresh on the same browser and origin. Clearing site data resets the demo. Passwords are stored in browser-side demo data and are **not secure**; this is a classroom UI prototype, not production authentication. No real McDonald's systems or data are connected. Product and account data are illustrative.

To reset the demo, open the browser developer console and run:

```js
localStorage.removeItem('mcdo_warehouse_demo_v1');
sessionStorage.removeItem('mcdo_session');
location.reload();
```

## Files

- `index.html` — app entry point
- `style.css` — responsive design matching the supplied wireframe's red/yellow/white aesthetic
- `app.js` — sample data, seven modules, interactions, persistence, and CSV export
- `screens/` — one renderer each for Dashboard, Inventory, Receiving, Orders, Stock Movement, Reports, Notifications, User Management, and Login
- `start.js` — starts the app after the shared logic and screen files load

## Version 2 changes
- Replaced the login emoji placeholder with the **burger photograph cropped from the supplied login wireframe** (stored locally in `assets/login-burger.png`).
- Replaced the sidebar placeholder symbols with consistent local SVG line icons and updated the login layout to follow the provided wireframe.
- Global search now runs when you press **Enter**, rather than clearing your text after the first character.
- Dashboard low-stock tile opens the filtered low-stock inventory list.
- Stock movement correction keeps the previous form values.
- Added a confirmation flow for deleting users (the signed-in account cannot be deleted).
- Improved order stock validation and error handling.

## Version 3 design alignment
- Added the exported McDonald’s wordmark and product artwork to `assets/` and used them in the app.
- Reused a transparent, tightly cropped arches mark in the sign-in header so it blends into the red background.
- Split the screen renderers into separate files under `screens/`; `app.js` retains shared state and interactions.
- Grouped the stylesheet rules by layout, screen components, responsive behavior, and sign-in styling; added section labels in `app.js`.
- Updated the dashboard to use inventory image tiles with event, appointment, low-stock, activity, and notification panels.
- Updated inventory, receiving, and order pages with persistent list-and-detail panels while preserving the existing edit, review, confirmation, and picking dialogs.
- Updated user and notification pages to use the same list-and-detail pattern.
- Added the documented Inventory Clerk and Picker roles and matching demo users.
- Used the WMS documentation as a functional reference for the role and module structure.

The design ZIP contains a composite SVG and per-screen PNG references. The product and brand images were extracted from the SVG; the application layout remains built from HTML and CSS so its controls and data stay interactive.

**Verification:** JavaScript syntax was checked. The updated screens have not been run through an automated test suite or interactive browser review.
## Publish on GitHub Pages

This is a static website with no build or package-install step. Upload the **contents of this folder** to the root of a GitHub repository so `index.html` is at the repository root. Then, in GitHub, open **Settings → Pages**, choose **Deploy from a branch**, select the `main` branch and `/ (root)`, and save. GitHub Pages will provide the published website link when deployment finishes.
