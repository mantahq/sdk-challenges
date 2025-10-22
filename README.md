# Challenge 2 — createRecords

Goal: Implement product creation using `manta.createRecords()` with validation, upsert, and refetch.

## Starter repo

Branch: `challenge-2`

## Setup Instructions

### 1. Clone the starter repo

```bash
git clone https://github.com/mantahq/sdk-challenges
cd sdk-challenges
git checkout challenge-2
npm install
```

### 2. Add your API key

Create `.env` file:

```
VITE_MANTAHQ_API_KEY=your_key_here
```

### 3. Create your database table in MantaHQ Studio (if you haven't)

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

The UI is already built. Your job is to implement the SDK calls in `src/components/CreateRecords.jsx` in the `challenge-2` branch.

Look for all the `// TODO:` comments and implement them.

## SDK Documentation

Check the docs for `createRecords()`:
[MantaHQ Docs - createRecords()](https://mantahq-core-sdk.super.site/creating-data/createrecords)

## What to implement

Add an "Add product" flow (modal form already scaffolded in `src/components/AddProductForm.jsx`).

Core features

- Implement `createProducts(formData)` using `manta.createRecords()`
- Generate a unique `product_id` per product (timestamp acceptable)
- Use `options.upsert: true` and `conflictKeys: ['product_id']`
- Validate locally before sending: name minLength 3, price > 0, stock >= 0
- Show loading state while creating
- Close modal on success and refetch products list
- Surface helpful error messages (display network/validation errors)
- **BONUS:** implement `dryRun: true` preview option (not required)

Definition of done
✅ createRecords call succeeds with `status: true`  
✅ UI indicates success and the product appears on the list (after refetch)  
✅ good error handling and user feedback  
✅ Add test notes in your PR describing upsert behavior you observed

Test scenarios

- Create a normal product
- Attempt to create with invalid price (should show validation error)
- Create duplicate `product_id` and confirm upsert behavior
- Try dryRun = true (if implemented) and confirm no data is written

## Feedback

When done, fill out the Challenge 2 feedback form: [Challenge 2 Feedback Form](https://docs.google.com/forms/d/e/1FAIpQLSc_5paJinXTq8zLtv10lVWuEFcWdjuyF8ywrIjQKa0S3F6bEQ/viewform?usp=send_form)

## Need Help?

- Check the README in the repo
- Read the SDK docs
- Join our Discord server: [https://discord.gg/taH3JfVEMh](https://discord.gg/taH3JfVEMh)

## What's Next?

**Branch for challenge 3:** `challenge-3`

**Good luck! Take your time and explore. This is your chance to help shape the SDK.**

```
P.S. The UI styling is done with Tailwind. Focus on the SDK implementation, not styling.
```
