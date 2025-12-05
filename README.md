# Next.js Web App Template

A modern, well-structured Next.js template with TypeScript, Tailwind CSS, and a scalable architecture. This template provides a solid foundation for building production-ready web applications with clear organization patterns and best practices.

## 🚀 Getting Started

### Prerequisites

- Node.js 18+
- pnpm

### Installation

1. Clone this repository or use it as a template
2. Install dependencies:

```bash
pnpm install
```

3. Run the development server:

```bash
pnpm dev
```

4. Open [http://localhost:3000](http://localhost:3000) in your browser

## 📁 Project Structure

This template follows a modular, scalable architecture with clear separation of concerns:

```
src/
├── app/                    # Next.js App Router pages and layouts
│   ├── api/               # API route handlers
│   ├── layout.tsx         # Root layout
│   └── page.tsx           # Home page
├── components/            # React components
│   └── ui/               # Reusable UI components (shadcn/ui)
├── contexts/             # React Context API for global state
├── hooks/                # Custom React hooks
├── lib/                  # Shared utilities and libraries
│   ├── api/              # API client functions
│   └── utils/            # Utility functions
├── providers/            # Context providers and wrapper components
├── server/               # Server-side code
│   ├── config/           # Server configuration
│   ├── repositories/     # Data access layer
│   └── services/         # Business logic services
└── types/                # TypeScript type definitions
```

## 📋 Folder Guidelines

Each folder contains a `.gitkeep` file with detailed organization guidelines. Here's a quick overview:

### `src/app/`

Next.js App Router directory. Contains pages, layouts, and API routes.

- **`app/api/`**: API route handlers organized by endpoint
  - Create subfolders for each route: `api/users/route.ts`, `api/products/route.ts`
  - Each subfolder contains a `route.ts` file with HTTP method handlers

### `src/components/`

React components organized by feature or type.

- **`components/ui/`**: Reusable UI components (shadcn/ui components)
- Create feature-specific components in separate files or subfolders

### `src/contexts/`

React Context API contexts for global state management.

- Create separate files for each context domain: `auth-context.tsx`, `theme-context.tsx`
- Each context should export both the context and its provider

### `src/hooks/`

Custom React hooks for reusable logic.

- Use the `use-` prefix: `use-auth.ts`, `use-api.ts`
- Organize by domain: authentication, data fetching, UI interactions, etc.

### `src/providers/`

Context providers and wrapper components.

- Create separate files per provider: `theme-provider.tsx`, `auth-provider.tsx`
- Consider a root provider that combines multiple providers

### `src/types/`

TypeScript type definitions and interfaces.

- Organize by domain: `user.ts`, `product.ts`, `order.ts`
- Or by category: `models.ts`, `api.ts`, `common.ts`
- Use index files to re-export related types

### `src/lib/api/`

API client functions and HTTP request handlers.

- Organize by resource: `users.ts`, `products.ts`, `auth.ts`
- Keep API client configuration in separate files if needed

### `src/lib/utils/`

Utility functions and helper methods.

- Organize by category: `date.ts`, `string.ts`, `validation.ts`, `formatting.ts`
- Keep utilities pure and framework-agnostic when possible

### `src/server/services/`

Server-side business logic services.

- Create separate files per domain: `user-service.ts`, `order-service.ts`
- Services orchestrate between repositories and handle business rules

### `src/server/repositories/`

Data access layer for database operations.

- Create separate files per entity: `user-repository.ts`, `product-repository.ts`
- Each repository handles CRUD operations for a single entity type

### `src/server/config/`

Server configuration files.

- Common files: `database.ts`, `env.ts`, `constants.ts`
- Keep configuration files focused and single-purpose

## 🏗️ Architecture Patterns

### Layered Architecture

This template follows a layered architecture pattern:

1. **Presentation Layer** (`app/`, `components/`): UI and user interactions
2. **Application Layer** (`hooks/`, `contexts/`, `providers/`): Application logic and state
3. **Domain Layer** (`server/services/`): Business logic and rules
4. **Data Layer** (`server/repositories/`): Data access and persistence

### Data Flow

```
Component → Hook → API Client → API Route → Service → Repository → Database
```

## 🛠️ Development Guidelines

### Adding UI Components

This template includes shadcn/ui. To add new components:

```bash
pnpm ui:add [component-name]
```

### Code Organization

- **One file per entity/resource**: Keep related code together
- **Clear naming conventions**: Use descriptive, consistent names
- **Separation of concerns**: Keep business logic separate from UI
- **Type safety**: Leverage TypeScript for type safety

### Best Practices

1. **Components**: Keep components small and focused on a single responsibility
2. **Hooks**: Extract reusable logic into custom hooks
3. **Types**: Define types close to where they're used, or in `types/` for shared types
4. **Services**: Keep business logic in services, not in components or API routes
5. **Repositories**: Keep data access logic in repositories, not in services

## 📦 Tech Stack

- **Framework**: [Next.js 16](https://nextjs.org) (App Router)
- **Language**: TypeScript
- **Styling**: Tailwind CSS
- **UI Components**: shadcn/ui (Radix UI + Tailwind)
- **Animations**: Framer Motion
- **Icons**: Lucide React

## 🚢 Deployment

### Vercel (Recommended)

The easiest way to deploy is using [Vercel](https://vercel.com):

1. Push your code to GitHub
2. Import your repository in Vercel
3. Vercel will automatically detect Next.js and configure the build

### Other Platforms

This template can be deployed to any platform that supports Next.js:

- Netlify
- AWS Amplify
- Railway
- Docker containers

## 📚 Learn More

- [Next.js Documentation](https://nextjs.org/docs)
- [Next.js App Router](https://nextjs.org/docs/app)
- [TypeScript Documentation](https://www.typescriptlang.org/docs)
- [Tailwind CSS Documentation](https://tailwindcss.com/docs)
- [shadcn/ui Documentation](https://ui.shadcn.com)

## 📝 Notes

- Each folder contains a `.gitkeep` file with detailed organization guidelines
- This is a template repository - customize it to fit your project needs
- Remove `.gitkeep` files once you add actual files to the folders

## 🤝 Contributing

This is a template repository. Feel free to fork and customize it for your needs!

## 📄 License

See the [LICENSE](LICENSE) file for details.
