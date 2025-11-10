# TypeScript Node.js Template

A minimal TypeScript Node.js project template with Express.js, featuring hot-reload development and path aliases.

## Features

- ✨ TypeScript for type safety
- 🚀 Express.js v5 web framework
- 🔥 Hot reload with Nodemon
- 📁 Path aliases (`@/` for `src/`)
- 🎨 Prettier for code formatting
- 🔐 Environment variable support with dotenv

## Prerequisites

Before you begin, ensure you have the following installed:

- [Node.js](https://nodejs.org/) (v18 or higher recommended)
- [npm](https://www.npmjs.com/) (comes with Node.js)

## Getting Started

### 1. Clone the Repository

```bash
git clone <repository-url>
cd ts-node-template
```

### 2. Install Dependencies

```bash
npm install
```

### 3. Environment Configuration

Create a `.env` file in the root directory (if not already present):

```bash
cp .env.example .env
```

Or create it manually with:

```env
PORT=3000
```

### 4. Run the Development Server

Start the development server with hot reload:

```bash
npm run dev
```

The server will start at `http://localhost:3000` (or the port specified in your `.env` file).

### 5. Build for Production

Compile TypeScript to JavaScript:

```bash
npm run build
```

This will generate compiled JavaScript files in the `dist/` directory.

### 6. Run Production Build

After building, run the production server:

```bash
npm start
```

## Available Scripts

| Script          | Description                              |
| --------------- | ---------------------------------------- |
| `npm run dev`   | Start development server with hot reload |
| `npm run build` | Compile TypeScript to JavaScript         |
| `npm start`     | Run the production build                 |

## Project Structure

```
ts-node-template/
├── src/
│   ├── config/
│   │   └── index.ts        # Configuration management
│   └── server.ts           # Express server entry point
├── dist/                   # Compiled JavaScript (generated)
├── node_modules/           # Dependencies
├── .env                    # Environment variables (not tracked)
├── .gitignore             # Git ignore rules
├── .prettierrc            # Prettier configuration
├── .prettierignore        # Prettier ignore rules
├── nodemon.json           # Nodemon configuration
├── package.json           # Project metadata and dependencies
├── tsconfig.json          # TypeScript configuration
└── README.md              # This file
```

## Path Aliases

This template uses path aliases for cleaner imports:

```typescript
// Instead of relative paths
import config from '../../../config';

// Use path aliases
import config from '@/config';
```

The `@/` alias maps to the `src/` directory.

## Adding New Routes

Create route files in `src/routes/`:

```typescript
// src/routes/users.ts
import { Router } from 'express';

const router = Router();

router.get('/', (req, res) => {
  res.json({ message: 'Users route' });
});

export default router;
```

Then import in `server.ts`:

```typescript
import userRoutes from '@/routes/users';

app.use('/users', userRoutes);
```

## Code Formatting

Format your code with Prettier:

```bash
npx prettier --write .
```

## License

This project is licensed under the Apache-2.0 License.

## Author

Matthew Roxas

## Support

For issues and questions, please open an issue in the GitHub repository.
