# 🖊️ Whitewave

**Whitewave** is a real-time collaborative whiteboard application that allows multiple users to draw, sketch, and brainstorm simultaneously. It features WebSocket-powered live updates, secure user authentication, and a modern developer-friendly monorepo architecture.

---

## ✨ Features

- 🔄 **Real-time Collaboration** — Draw and update the canvas with other users instantly using WebSockets.
- 🔐 **User Authentication** — Signup/signin support with JWT-based authentication.
- 💾 **Persistent Data** — Store user and whiteboard data securely in PostgreSQL using Prisma ORM.
- ⚙️ **Scalable Architecture** — Turborepo-based monorepo with isolated frontend and backend apps.
- 🎨 **Modern UI** — Built with React, TailwindCSS, and Radix UI for a snappy user experience.
- 🔌 **REST + WebSocket APIs** — Seamless backend communication over HTTP and WebSocket protocols.

---

## 🏗️ Tech Stack

| Layer         | Tech                                                   |
|--------------|--------------------------------------------------------|
| Frontend      | Next.js 15, React 19, TailwindCSS, Radix UI           |
| Backend (HTTP)| Node.js, Express, JWT, Prisma, PostgreSQL             |
| Backend (WS)  | Node.js, ws (WebSocket server), Express               |
| Auth          | bcryptjs, jsonwebtoken                                |
| ORM           | Prisma                                                 |
| Infra         | Turborepo (monorepo), PNPM, TypeScript                |

---

## 📁 Monorepo Structure

```text
excelidraw-main/
├── apps/
│   ├── excelidraw-frontend/     # Next.js frontend app
│   ├── http-backend/            # Express backend for REST APIs
│   └── ws-backend/              # WebSocket server for real-time updates
├── packages/
│   ├── common/                  # Shared types and utilities
│   ├── db/                      # Prisma client and schema
│   ├── eslint-config/          # Shared ESLint config
│   └── typescript-config/      # Shared TS config
├── .gitignore
├── package.json
└── turbo.json
```

---

## 🚀 Getting Started

### 1. Clone the Repo

```bash
git clone https://github.com/your-username/whitewave.git
cd whitewave
```

### 2. Install Dependencies

Make sure you have Node.js ≥ 18 and [pnpm](https://pnpm.io/) installed:

```bash
npm install -g pnpm
pnpm install
```

### 3. Set up PostgreSQL

Install PostgreSQL locally or use a service like Supabase or Neon.

Update the `.env` in `packages/db/` with your DB connection:

```env
DATABASE_URL="postgresql://user:password@localhost:5432/whitewave"
JWT_SECRET="supersecretjwt"
```

### 4. Generate Prisma Client

```bash
pnpm exec prisma generate --schema=packages/db/prisma/schema.prisma
```

(Optional) Run migrations if needed:

```bash
pnpm exec prisma migrate dev --schema=packages/db/prisma/schema.prisma
```

### 5. Start the App

```bash
pnpm run dev
```

This will start:

- 🔌 HTTP API at `http://localhost:3001`
- 🌐 WebSocket server at `ws://localhost:3002`
- 🖥️ Frontend at `http://localhost:3000`

---

## 🧪 Testing the App

- Open [http://localhost:3000](http://localhost:3000)
- Signup or Signin
- Create a room and share the URL
- Join from another tab or browser to test real-time drawing

---

## 🧰 Available Scripts

Inside the monorepo root, you can run:

| Command           | Description                              |
|------------------|------------------------------------------|
| `pnpm dev`        | Runs frontend + backend + websocket apps |
| `pnpm build`      | Builds all packages                      |
| `pnpm lint`       | Lints codebase using shared config       |
| `pnpm prisma ...` | Run Prisma CLI with correct schema path  |


---

## 🤝 Contributing

Feel free to fork this repo, raise issues, and submit pull requests.

---

## 📄 License

This project is licensed under the MIT License.

---

## 💡 Inspiration

This project was built as a part of learning real-time systems, WebSocket architecture, and scalable full-stack applications using a modern monorepo setup.
