# Restaurant-Ordering-System-Menu-Cart-and-Orders-


### Live Preview : https://ahmedsa19980.github.io/Restaurant-Ordering-System-Menu-Cart-and-Orders-/



🧩 Project Overview
This is a single-page restaurant manager with a split layout:
🔹 Left side: tables list (select / open / close / add table / reset demo).
🔸 Right side: menu items + the current selected table order.

Each table has its own separate order stored in memory, and the system can print a full bill and close the table after printing.

🧬 Core Concepts
🔹 Table Management (Open / Close + Selection)
➡️ Each table has a status (Open / Closed).
➡️ You select one table to work on its order.
➡️ A table must be ✅ Open before you can add items to its order.

🔹 In-Memory Data Models (Simple POS Logic)
➡️ Tables are stored in an array tables[].
➡️ Menu is stored in a static array menu[].
➡️ Orders are stored in an object map ordersByTable{} where:
🔸 key = tableId
🔸 value = array of order items

🔹 Menu Rendering (Dynamic UI Cards)
➡️ Menu items are rendered into cards using JavaScript.
➡️ Each card includes name, description, price, and an “Add” button.

🔹 Order Building per Table (Separate Orders ✅)
➡️ Clicking “Add” adds the item to the selected table’s order.
➡️ If the item already exists, quantity increases instead of creating a duplicate row.

🔹 Quantity Controls (+ / −)
➡️ Each order row has buttons to increase or decrease quantity.
➡️ If quantity becomes 0, the line is removed automatically.

🔹 Totals & Subtotals Calculation
➡️ Each row calculates subtotal = price × quantity.
➡️ The total is recalculated every time the order changes.

🔹 Remove Item + Clear Order
➡️ Remove button deletes a single item line.
➡️ Clear Order removes all items of the current selected table (after confirmation).

🔹 Printing the Check (Popup + window.print)
➡️ A popup window is opened using window.open().
➡️ The bill HTML is generated dynamically and written into the popup.
➡️ When the popup loads, it calls window.print() automatically.

🔹 Close Table After Printing (Demo Workflow)
➡️ After generating the bill, the table is set to Closed.
➡️ The order for that table is cleared to prepare it for the next customer.
