---
description: Create and understand Server Components in NextJS 15
globs: *.tsx
---
## Context

* Since React 19 and NextJS 13 Server Component can be used.
* Server Component enable use to make backend query directly on our Component
* Server Component NEVER run on the client

## Usage

Utilize React 19 with Server Components. Implement Prisma queries and backend logic inside `page` or `layout` files like this:

```tsx
// Use "async" for server components
export default async function Page() {
  // Use "await" for async operations
  const result = await prisma.user.findMany();
  return (
    <div>
      {result.map((user) => (
        <p>{user.name}</p>
      ))}
    </div>
  );
}
```

You can also implement this logic in every component that is `async`. A Server Components can do backend stuff inside is body like :

* prisma query
* fs read / write
* analytics
* third partie stuff

Some method are avaiable : 

```tsx
import { redirect } from 'next/navigation'
import { notFound } from 'next/navigation'

// Redirect to another page
redirect('/login');

// Show the `not-found.tsx` file
notFound()
```

Some rules about Server Components :

1. Server components are always `async`
2. Server components can't use hooks
3. Server Components can't use `document` or `window` because they are only run in backend