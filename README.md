# UseFirst – Working Web App (case-study edition)

A working prototype of **UseFirst: A Smart Household Consumption Prioritization and Replenishment System**
from the Software Engineering Case Study (Review 1). Everything is in one file, `index.html`.
Nothing to install or build.

## How it follows the case study deck
| Deck item | In the app |
|---|---|
| Slide 1 wireframe: Dashboard, Inventory, Alerts, Shopping | Same four sections. The Dashboard shows the four wireframe panels: **Use-First List**, **Expiry Alerts** ("Milk in 2d"), **Smart Shopping List**, **Consumption Chart** |
| FR1-FR12 | All covered. See the "Requirements coverage" table on the Household page |
| Slide 12 usage scenario, steps 1-10 | Scan or enter an item, alert, Use-First list, recipe, consume, stock update, auto-add to list, **manager approves the list** |
| Slide 12 alternative paths | **Mark resolved** on an alert; **Save it before it goes** tips and **Share** when no recipe fits |
| Slide 13 actors | **Home Manager**, **Household Member**, **System Administrator** (Admin console: users, roles, data sources, system logs). Viewer role from FR2. Retail Partner is marked future in the deck and is not built |
| Slide 8 stakeholders | Flatmates: assign items and split expenses. Elderly users: large text mode. Working professionals: quick check line. Home managers: budget and money at risk |
| Slide 10 quality targets | NFR1 timing, NFR4 alert accuracy and NFR8 data integrity are measured in **Admin > System health** |
| Slide 5 modularity | Code is split into Inventory, Alerts, Shopping, Analytics and a separate UI layer (see the comment at the top of the script) |

## Try it
1. Create the first account. **The first account created in a browser becomes the System Administrator.**
2. Create a household, then press **Load sample data**.
3. Sample barcodes: `8900000000011` (Milk), `8900000000059` (Eggs), `8900000000103` (Tomato).
4. To see other roles, create more accounts and join with the household code, then change roles in
   **Household** (Home Manager) or **Admin** (System Administrator).

## Publish on GitHub Pages
Upload `index.html` (and this README) to the top level of your repository, then
Settings > Pages > Deploy from a branch > `main` / `(root)` > Save.
To update an existing site: **Add file > Upload files**, upload the new `index.html` (it replaces the old one), then Commit.

## Honest limits of a browser-only prototype
- Data is saved in the browser (localStorage), private to each browser and device. Use Backup and restore on the Household page.
- Passwords use salted PBKDF2 hashing, but the stored data itself is not encrypted (NFR2).
- NFR5 scalability, NFR6 availability and NFR8 atomic database operations need a real server and database.
- Barcode lookup uses a small sample catalog plus whatever the System Administrator adds.
- Camera barcode scanning works in Chrome on Android. Typing the code or a USB scanner works everywhere.
- Shelf-life suggestions are rough estimates. Always check the date on the pack.
