# MantaHQ SDK Beta Testing

Welcome to the MantaHQ SDK beta testing program! This repository contains a progressive product catalog application that you'll build throughout the week to test all core SDK features.

## Quick Start

### Prerequisites
- Node.js 18+
- npm or yarn
- [MantaHQ Account](www.mantahq.com) and [API key](docs.mantahq.com)

### Setup

1. **Clone the repository**
```bash
git clone https://github.com/mantahq/sdk-challenges
cd sdk-challenges
```

2. **Install dependencies**
```bash
npm install
```

3. **Add your API key**
Create a `.env` file in the root:
```
VITE_MANTAHQ_API_KEY=your_api_key_here
```

4. **Checkout the branch for the challenge**
```bash
# Challenge 1
git checkout challenge-1

# Challenge 2
git checkout challenge-2

...
```

5. **Run the development server**
```bash
npm run dev
```

## Database Setup

### For All Days: `products` Table

Create this table in MantaHQ Studio:

| Field | Type | Required |
|-------|------|----------|
| product_id | string | Yes |
| name | string | Yes  |
| category | string | Yes |
| price | number | Yes  |
| stock | number | Yes |
| description | string | No | 
| image_url | string | No |


## Daily Instructions

Each branch has its own README with specific instructions:


## Resources

- **SDK Documentation:** [https://docs.mantahq.com](https://docs.mantahq.com)
- **MantaHQ Studio:** [https://app.mantahq.com](https://app.mantahq.com)
- **MantaHQ Discord Community:** [https://discord.gg/taH3JfVEMh](https://discord.gg/taH3JfVEMh)

## Feedback

Please submit feedback forms daily:
- **Daily feedback:** After completing each day's challenge
- **Final feedback:** After the beta test

Your feedback shapes the SDK.


## ❓ Troubleshooting

### Common Issues

**App won't start:**
- Check Node.js version (18+)
- Delete `node_modules` and reinstall: `npm install`
- Verify `.env` file exists with your API key
- Re-install the SDK `npm install mantahq-sdk`

**API calls failing:**
- Verify API key is correct
- Check table names match exactly (case-sensitive)
- Ensure tables are created in MantaHQ Studio

**No data showing:**
- Check browser console for errors
- Verify your tables have data in MantaHQ Studio

**Wrong branch:**
- Check current branch: `git branch`
- Switch to correct day: `git checkout challenge-X`


## Need Help?

Don't struggle alone!

- **Discord:** Ask in #feedback-and-ideas channel. Specify that it's for the Beta Test.
- **Issues:** Open an issue in this repo


## Have Fun!

This is your chance to shape a product before it launches. Be honest, be critical, and help us build something great!
