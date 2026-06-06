# import { prisma } from "@repo/db/prismaClient";


'use client'
import { useAuthStore } from '@repo/store'

const user = useAuthStore((s) => s.user)


Step 2 — Create a client component and use it directly
tsx// apps/user-app/app/components/Balance.tsx
'use client'

import { useAuthStore } from '@repo/store'

export default function Balance() {
  const user = useAuthStore((s) => s.user)
  
  return <div>hi there {user?.name}</div>
}


Step 3 — Use it in any page
tsx// apps/user-app/app/page.tsx
import Balance from './components/Balance'

export default function Home() {
  return <Balance />
}