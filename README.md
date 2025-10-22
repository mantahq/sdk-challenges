# Challenge 4 — deleteRecords

**Goal:** Implement product deletion using `manta.deleteRecords()` with confirmation modal and safe deletion practices.

## Starter repo

Branch: `challenge-4`

## Setup Instructions

### 1. Clone the starter repo

```bash
git clone https://github.com/mantahq/sdk-challenges
cd sdk-challenges
git checkout challenge-4
npm install
```

### 2. Add your API key

Create `.env` file:

```
VITE_MANTAHQ_API_KEY=your_key_here
```

### 3. Create your database table in MantaHQ Studio

**Table name:** `products`

| Field       | Type   | Required |
| ----------- | ------ | -------- |
| product_id  | string | Yes      |
| name        | string | Yes      |
| category    | string | Yes      |
| price       | number | Yes      |
| stock       | number | Yes      |
| description | string | No       |
| image_url   | string | No       |

### 4. Add sample data

Use the `products.csv` file in the repo to populate your table (20-30 products). You can either:

- Import via MantaHQ Studio.

## Your Task

The UI is partially built with the delete icon on product cards. Your job is to implement the SDK calls in `src/components/DeleteRecords.jsx` in the `challenge-4` branch.

Look for all the `// TODO:` comments and implement them.

## SDK Documentation

Check the docs for `deleteRecords()`:
[MantaHQ Docs - fetchAllRecords()](https://mantahq-core-sdk.super.site/deleting-data/deleterecords)

## Definition of Done

Your app should:

- ✅ deleteRecords call succeeds with status: true
- ✅ Product disappears from UI after deletion (after refetch)
- ✅ Confirmation modal shows before deletion
- ✅ Good error handling and user feedback
- ✅ The where clause is ALWAYS present (never deletes all products by accident)
- ✅ Delete icon positioned correctly on product card (top-right corner)

## Test These Scenarios

1. Delete a normal product (should show confirmation first)
2. Click "Cancel" in confirmation modal (product should NOT be deleted)
3. Delete multiple products in succession to verify correct product is deleted
4. Attempt to delete when there's a network error (should show error message)
5. Verify deleted product is permanently removed (refresh page to confirm)
6. Click outside confirmation modal to cancel (should close modal without deleting)

## Feedback

When done, fill out the Challenge 4 feedback form: [Challenge 4 Feedback Form](https://docs.google.com/forms/d/e/1FAIpQLSc_5paJinXTq8zLtv10lVWuEFcWdjuyF8ywrIjQKa0S3F6bEQ/viewform?usp=send_form)

## Need Help?

- Check the README in the repo
- Read the SDK docs
- Join our Discord server: [https://discord.gg/taH3JfVEMh](https://discord.gg/taH3JfVEMh)

---

**Good luck! Take your time and explore. This is your chance to help shape the SDK.**

```
P.S. The UI styling is done with Tailwind. Focus on the SDK implementation, not styling.
```
