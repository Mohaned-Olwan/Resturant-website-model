# Flames App Source Code (Plug-and-Play)

This directory contains the reconstructed, plug-and-play source code for the "Flames App" web application. All necessary configuration files (`package.json`, `vite.config.js`, `tailwind.config.js`, `postcss.config.js`, and `.env`) have been created to allow for a quick setup.

The application is a **React** project built with **Vite** and styled using **Tailwind CSS**. The theme has been adjusted to a darker, more reddish-orange aesthetic.

## New Features and Fixes

*   **Data Persistence Implemented:** Order data is now saved to the browser's **Local Storage**, so it will persist even after refreshing the page or closing the browser.
*   **Order Status Change Fixed:** The functionality to change the order status is now working.
*   **Corrected Staff Permissions:** All users (**Admin** and **Staff**) can now change the status of an order, including setting it to 'Completed' or 'Canceled'.
*   **Advanced Role-Based Status Locking Implemented:**
    *   **Admin** users can now **override** the locked status of 'Completed' or 'Canceled' orders and change their state.
    *   **Staff** users can only change the status of active orders ('New Order', 'Working', 'Out for Delivery').
    *   Once an order is 'Completed' or 'Canceled', its status is locked and cannot be changed by any user.
*   **Date Format Updated:** The date and time format in the Order History and the Excel export has been updated to show the full date and time without seconds (e.g., "Nov 2, 2025, 7:50 PM").
*   **Statistics Page:** A new "Statistics" page is available for **Admin** users, providing:
    *   Total Revenue and Average Order Value from completed orders.
    *   Visualizations for the Top 5 addresses by order count and revenue (simulated data visualization).
    *   A button to download all raw order data as an Excel file.

## Project Structure

-   `index.html`: The main entry point for the application.
-   `package.json`: Contains all necessary dependencies and scripts.
-   `vite.config.js`: Vite configuration file.
-   `tailwind.config.js`: Tailwind CSS configuration file.
-   `postcss.config.js`: PostCSS configuration for Tailwind.
-   `.env`: Contains the `VITE_BACKEND_URL` used by the `Test.jsx` component.
-   `src/`: Contains the main application logic.
    -   `App.jsx`: The main application component, handling routing, state, and **Local Storage persistence**.
    -   `main.jsx`: The entry file for the React application.
    -   `Test.jsx`: A component for testing backend and database connectivity.
    -   `index.css`: The main CSS file with Tailwind directives.
    -   `components/`: Reusable React components (`LoginForm.jsx`, `Navbar.jsx`, `OrdersDashboard.jsx`, `CreateOrderForm.jsx`, `OrderHistory.jsx`, `Statistics.jsx`).
    -   `utils/`: Utility files, including `excelUtils.js` for data export.

## How to Run Locally (Plug-and-Play)

You will need **Node.js** and **pnpm** installed on your system.

1.  **Install Dependencies:**
    Navigate to the project root directory and run the install command.

    \`\`\`bash
    pnpm install
    \`\`\`

2.  **Run the Development Server:**
    Start the development server. The application will typically be available at `http://localhost:5173`.

    \`\`\`bash
    pnpm run dev
    \`\`\`

3.  **Build for Production (Optional):**
    To create a production-ready build, run:

    \`\`\`bash
    pnpm run build
    \`\`\`

**Note on Backend:**
The `Test.jsx` component attempts to connect to a backend URL specified in the `.env` file. This is for testing purposes only. The main application manages state locally and does not rely on this backend for its core order management features.
