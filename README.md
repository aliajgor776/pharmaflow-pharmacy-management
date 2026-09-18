# PharmaFlow — Pharmacy Operations Suite

A compact, bilingual (English/Bangla) pharmacy management system built for Namecheap shared hosting. It uses one PHP entry file, one stylesheet, and SQLite, so it requires no Composer, Node, build step, or external database.

## Features

- Admin/staff password login with role-aware product deletion.
- Dashboard with revenue, gross profit, orders, low-stock alerts, date range selection, and expense-adjusted net profit.
- Sales entry tied to the logged-in staff member, automatic stock deduction, cost/price/profit calculation, and sales ledger.
- Inventory with medicine name, generic, category, batch, expiry, stock, reorder level, unit cost, and sale price.
- Daily expenses and expense history.
- Staff performance by transactions, revenue, and profit.
- Reports with current-period / prior-period comparison and CSV export.
- Responsive mobile layout and EN / বাংলা switch.

## Upload and run

1. Upload all files to `public_html` on Namecheap: `index.php`, `style.css`, and `.htaccess`.
2. Ensure PHP 7.4+ is enabled and the SQLite3 PDO extension is available.
3. Open the domain. The app creates `pharmacy.sqlite` automatically on first run.
4. Change the demo passwords immediately after installing. The included demo users are `admin / admin123` and `staff / staff123`.
5. Keep the `.htaccess` file in place so the SQLite database and documentation cannot be downloaded directly.

## Notes

This portfolio-ready starter keeps the core workflow intentionally compact. Before production use, add regular encrypted database backups, CSRF protection, password-change screens, audit logs, and a more granular permission matrix.

## Latest corrections included

- Sales quantity above available stock now shows a stock-out alert and does not create a sale.
- Sales entries can be removed by the creating staff member or an admin; removed sales restore the medicine quantity.
- Admins can remove incorrect expense entries.
- Inventory search filters medicine name, generic name, category, and other visible row data.
- Admins can create staff accounts from the Staff page with a name, username, and password. Staff then signs in with that account and all sales are attributed to that staff ID.

## Staff access control

Admins can deactivate a staff account from the Staff page. Deactivation changes the account to inactive, preserves historical sales, and prevents future login. The same control can reactivate the account if needed.
