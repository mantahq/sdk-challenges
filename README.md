# Challenge 3 — updateRecords

Goal: Implement product editing using `manta.updateRecords()` with validation, where clause, and refetch.

## Starter repo

Branch: `challenge-3`

## Setup Instructions

### 1. Clone the starter repo

git clone https://github.com/mantahq/sdk-challenges
cd sdk-challenges
git checkout challenge-3
npm install

### 2. Add your API key

Create `.env` file:

```
VITE_MANTAHQ_API_KEY=your_key_here
```

### 3. Ensure your database table exists in MantaHQ Studio

**Table name:** `products2`

| Field       | Type   | Required |
| ----------- | ------ | -------- |
| product_id  | string | Yes      |
| name        | string | Yes      |
| category    | string | Yes      |
| price       | number | Yes      |
| stock       | number | Yes      |
| description | string | No       |
| image_url   | string | No       |

### 4. Ensure sample data exists

Your table should already have products from Challenge 2. If not, use the `products.csv` file in the repo to populate your table (20-30 products). You can either:

- Import via MantaHQ Studio
- Use the "List an item" button from Challenge 2 to add products

## Your Task

The UI is already built with the Edit button and EditProductForm modal. Your job is to implement the SDK calls in `src/components/UpdateRecords.jsx` in the `challenge-3` branch.

Look for all the `// TODO:` comments and implement them.

## SDK Documentation

Check the docs for `updateRecords()`:
[MantaHQ Docs - updateRecords()](https://mantahq-core-sdk.super.site/updating-data/updaterecords)

## What to implement

Add an "Edit product" flow (modal form already scaffolded in `src/components/EditProductForm.jsx`).

### Core features

- Implement `updateProduct(productId, formData)` using `manta.updateRecords()`
- **CRITICAL:** Always include `where: { product_id: productId }` to target specific product
- Use `options.validationRule` (singular, NOT `validationRules`!) for validation
- Validate: name minLength 3, price > 0, stock >= 0
- Show loading state while updating ("Updating..." button text)
- Close modal on success and refetch products list
- Surface helpful error messages (display network/validation errors)
- **BONUS:** implement bulk price update by category (not required)
- **BONUS:** implement `dryRun: true` preview option (not required)

### Definition of done

- ✅ updateRecords call succeeds with `status: true`
- ✅ UI indicates success and the product shows updated values (after refetch)
- ✅ Good error handling and user feedback
- ✅ The `where` clause is ALWAYS present (never updates all products by accident)
- ✅ Add test notes in your PR describing validation behavior you observed

### Test scenarios

- Edit a normal product (change name, price, stock)
- Attempt to update with invalid price (should show validation error)
- Attempt to update with empty name (should show validation error)
- Edit multiple products in succession to verify correct product is updated
- Try leaving some fields unchanged (should still update successfully)
- **BONUS:** Try `dryRun: true` (if implemented) and confirm no data is written

## Common Mistakes to Avoid

- ⚠️ **Forgetting the `where` clause** - This will update ALL products!
- ⚠️ **Using `validationRules` (plural)** - Use `validationRule` (singular)
- ⚠️ **Not refetching after update** - UI won't show changes
- ⚠️ **Not handling errors** - User won't know what went wrong

## Feedback

When done, fill out the Challenge 3 feedback form: [Challenge 3 Feedback Form](https://docs.google.com/forms/d/e/1FAIpQLSc_5paJinXTq8zLtv10lVWuEFcWdjuyF8ywrIjQKa0S3F6bEQ/viewform?usp=send_form)

## Need Help?

- Check the README in the repo
- Read the SDK docs: Pay special attention to the `where` clause examples
- Join our Discord server: [https://discord.gg/taH3JfVEMh](https://discord.gg/taH3JfVEMh)

## What's Next?

**Branch for challenge 4:** `challenge-4` (deleteRecords)

**Good luck! Take your time and explore. This is your chance to help shape the SDK.**

```
P.S. The UI styling is done with Tailwind. Focus on the SDK implementation, not styling. The edit modal is already fully styled and functional - you just need to wire up the SDK call.
```
