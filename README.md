# StarCitizen Inventory Creator

A static, backend-free inventory website for tracking in-game items and quantities. Data is stored in the browser via `localStorage`.

---

## How to use the website

- Click **Add Item** to open the search dialog
- Click into the search box to browse the first 5 items, or type to filter
- Select an item, set the quantity (mouse wheel works too), then click **Add**
- Use **Remove** to delete an item from the inventory
- Use **Export as PDF** to print the current inventory
- The name field next to "Inventory" lets you label the inventory (e.g. a player name or session)

---

## How to add new items to the list

### Option 1 — Directly on GitHub (recommended)

1. Go to [items.json](./items.json) in this repository
2. Click the **pencil icon** (Edit this file) in the top right
3. Add your items to the JSON array:
   ```json
   [
     "Existing Item",
     "Your New Item"
   ]
   ```
4. Click **Commit changes** — the workflow runs automatically and updates `index.html`

### Option 2 — Pull Request (if you don't have write access)

1. Fork this repository
2. Edit `items.json` in your fork
3. Open a Pull Request back to this repo
4. Once the owner merges it, the workflow runs automatically

---

## How the automation works

Whenever `items.json` is changed on the `main` branch, a GitHub Actions workflow runs automatically:

1. Reads the item list from `items.json`
2. Injects it into the `ITEM_LIST` array in `index.html`
3. Commits and pushes the updated `index.html`

No manual editing of `index.html` is ever needed.
