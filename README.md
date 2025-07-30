# React Router v7 Framework Snippets

This comprehensive snippet collection makes it easy to develop with React Router v7 / Remix v3. Including useful `action` / `loader` on both client and server side, plus snippets for resource/UI routes, error boundaries, and framework features.

## Features

![snippet preview](assets/demo.gif)

---

# Snippets

|      Prefix | Description                                                                      |
| ----------: | -------------------------------------------------------------------------------- |
|     `rrrr→` | **R**eact **R**outer **r**esource **r**oute with action and loader              |
|     `rrur→` | **R**eact **R**outer **U**I **r**oute with loader, action, and component        |
|      `rrl→` | **R**eact **R**outer server **l**oader function                                 |
|      `rra→` | **R**eact **R**outer server **a**ction function                                 |
|     `rrcl→` | **R**eact **R**outer **c**lient **l**oader function                             |
|     `rrca→` | **R**eact **R**outer **c**lient **a**ction function                             |
|   `rrcomp→` | **R**eact **R**outer default **comp**onent with typed props                     |
|     `rreb→` | **R**eact **R**outer **e**rror **b**oundary component                           |
|     `rrhf→` | **R**eact **R**outer **h**ydrate **f**allback component                         |
|   `rrmeta→` | **R**eact **R**outer **meta** function for SEO                                  |
|  `rrlinks→` | **R**eact **R**outer **links** function for head links                          |
| `rrheaders→` | **R**eact **R**outer **headers** function for HTTP headers                      |
| `rrshouldrevalidate→` | **R**eact **R**outer **should revalidate** function for controlling revalidation |
|    `rrfull→` | **R**eact **R**outer **full** route module with all features                    |

## What's New in v2.0.0

- 🎯 **Enhanced Core Snippets** - Improved resource and UI route snippets with better defaults
- 🔧 **Framework Features** - Added meta, links, headers, and shouldRevalidate functions
- 🚨 **Error Handling** - Error boundary and hydrate fallback components
- 📝 **Better TypeScript** - Proper typing with `Route.ComponentProps`, `Route.LoaderArgs`, etc.
- 🔄 **Client/Server Support** - Dedicated snippets for both client and server-side functions
- 📦 **Complete Route Module** - Full-featured route template with all React Router v7 features

## Usage Examples

### Resource Route (`rrrr`)
```typescript
import type { Route } from "../+types/root";

export async function action({ request, params }: Route.ActionArgs) {
  const formData = await request.formData();
  // Your action logic here
  return { success: true };
}

export async function loader({ request, params }: Route.LoaderArgs) {
  // Your loader logic here
  return {};
}
```

### UI Route (`rrur`)
```typescript
import type { Route } from "../+types/root";

export async function action({ request, params }: Route.ActionArgs) {
  const formData = await request.formData();
  // Your action logic here
  return { success: true };
}

export async function loader({ request, params }: Route.LoaderArgs) {
  // Your loader logic here
  return {};
}

export default function MyRoute({
  loaderData,
  actionData,
  params,
}: Route.ComponentProps) {
  return (
    <div>
      <h1>New Route</h1>
      {/* Add your UI here */}
    </div>
  );
}
```

### Client Loader with Hydration (`rrcl`)
```typescript
export async function clientLoader({
  request,
  params,
  serverLoader,
}: Route.ClientLoaderArgs) {
  // Optional: call server loader
  // const serverData = await serverLoader();
  // Your client-side logic here
  return {};
}

// Optional: Force client loader to run during hydration
// clientLoader.hydrate = true as const;
```

## Requirements

- React Router v7 or Remix v3
- TypeScript (recommended for full type safety)
- VS Code

## Installation

### Option 1: VS Code Marketplace
Search for "React Router v7 Snippets" in the VS Code Extensions marketplace.

### Option 2: Manual Installation
1. Copy the snippets JSON
2. Open VS Code → Preferences → Configure User Snippets
3. Select "typescriptreact" 
4. Paste the snippets and save

## Contributing

Found a bug or want to add more snippets? Feel free to open an issue or submit a pull request!

## License

MIT

---