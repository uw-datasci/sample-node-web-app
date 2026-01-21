# Next.js Web App Template

A modern Next.js template with TypeScript, Tailwind CSS, and shadcn/ui components.

## 🚀 Quick Start

### Prerequisites

- Node.js 18+
- pnpm

### Setup

1. Install dependencies:

   ```bash
   pnpm install
   ```

2. Configure environment variables:

   ```bash
   cp .env.example .env
   ```

   Edit `.env` with your values:
   - `INFISICAL_CLIENT_ID`
   - `INFISICAL_CLIENT_SECRET`
   - `APP_NAME`

3. Update CI/CD configuration:

   Edit [.github/workflows/quality-gate.yml](.github/workflows/quality-gate.yml):
   - Set `INFISICAL_SECRET_PATH` to `/{APP_NAME}`

4. Start development:
   ```bash
   pnpm dev
   ```
   Open [http://localhost:3000](http://localhost:3000)

## 📁 Project Structure

```
src/
├── app/              # Next.js App Router (pages, layouts, API routes)
├── components/       # React components
│   └── ui/          # shadcn/ui components
├── hooks/           # Custom React hooks
├── lib/             # Utilities and helpers
├── server/          # Server-side code (services, repositories, config)
└── types/           # TypeScript definitions
```

See individual folders for detailed organization guidelines.

## 🏗️ Architecture

### API Architecture

The API follows a layered architecture pattern:

```
Component → API Route (app/api/) → Service (server/services/) → Repository (server/repositories/) → Database
```

- **API Routes**: Handle HTTP requests, validation, and responses
- **Services**: Contain business logic and orchestrate operations
- **Repositories**: Handle data access and database queries

This separation keeps business logic isolated from HTTP concerns and data access.

### Design System

Built with **shadcn/ui** using the New York style variant:

- **CSS Variables**: All colors and tokens defined in `globals.css` using OKLCH color space
- **Dark Mode**: Automatic support via semantic color tokens (`bg-primary`, `text-muted`, etc.)
- **Component Variants**: Built with `class-variance-authority` (cva) for consistent variants
- **Utility Function**: Use `cn()` from `@/lib/utils` to merge classNames
- **Path Aliases**: Import with `@/` (e.g., `@/components/ui/button`)

**Component Organization** follows Atomic Design principles:

- **Atoms** (`components/ui/`): Basic building blocks (Button, Input, Card)
- **Molecules** (`components/`): Simple combinations of atoms (SearchBar, FormField)
- **Organisms** (`components/`): Complex UI sections (Navigation, ProductGrid, Dashboard)

This hierarchy promotes reusability and maintainability by composing simple components into complex interfaces.

Always use semantic tokens instead of hardcoded values to maintain theme consistency.

## 🛠️ Development

Add UI components:

```bash
pnpm ui:add [component-name]
```

## 📦 Tech Stack

- Next.js 16 (App Router) • TypeScript • Tailwind CSS
- shadcn/ui • Framer Motion • Lucide Icons

## 📚 Resources

- [Next.js Docs](https://nextjs.org/docs)
- [TypeScript Docs](https://www.typescriptlang.org/docs)
- [Tailwind CSS Docs](https://tailwindcss.com/docs)
- [shadcn/ui Docs](https://ui.shadcn.com)

## 📄 License

See [LICENSE](LICENSE) for details.
