# 🚀 PPWL Modern Monorepo

[![Bun](https://img.shields.io/badge/Bun-%23000000.svg?style=for-the-badge&logo=bun&logoColor=white)](https://bun.sh)
[![ElysiaJS](https://img.shields.io/badge/ElysiaJS-%23000000.svg?style=for-the-badge&logo=elysia&logoColor=white)](https://elysiajs.com)
[![Vite](https://img.shields.io/badge/vite-%23646CFF.svg?style=for-the-badge&logo=vite&logoColor=white)](https://vitejs.dev)
[![React 19](https://img.shields.io/badge/React_19-%2320232a.svg?style=for-the-badge&logo=react&logoColor=%2361DAFB)](https://react.dev)
[![Tailwind CSS 4](https://img.shields.io/badge/Tailwind_CSS_4-%2338B2AC.svg?style=for-the-badge&logo=tailwind-css&logoColor=white)](https://tailwindcss.com)

Sebuah boilerplate monorepo modern yang dirancang untuk performa tinggi dan pengalaman pengembangan (DX) yang maksimal. Menggunakan **Bun Workspaces** untuk manajemen package yang super cepat dan berbagi tipe data (Type-Safe) antara frontend dan backend.

## 🏗️ Tech Stack

### 💻 Frontend (`apps/frontend`)

- **React 19**: Versi terbaru dengan fitur concurrent rendering.
- **Vite 8**: Build tool generasi terbaru yang sangat cepat.
- **Tailwind CSS 4**: Engine CSS tercanggih dengan performa optimal
- **Shadcn UI & Radix UI**: Komponen UI yang aksesibel dan mudah di-custom.
- **Geist Font**: Tipografi premium dari Vercel.

### ⚙️ Backend (`apps/backend`)

- **ElysiaJS**: Framework Bun-native yang diklaim sebagai salah satu yang tercepat di dunia.
- **Prisma**: ORM modern dengan dukungan penuh TypeScript (SQLite).
- **Swagger UI**: Dokumentasi API otomatis yang bisa diakses di `/swagger`.

### 📦 Shared Package (`packages/shared`)

- Berbagi **TypeScript Interfaces** dan **Dania Models** antara frontend dan backend (End-to-End Type Safety).

---

## 📂 Struktur Project

```text
.
├── apps/
│   ├── frontend/       # Vite + React 19 Project
│   └── backend/        # ElysiaJS + Prisma Project
├── packages/
│   └── shared/         # Shared Types & Logic (Internal Package)
├── mise.toml           # Tool Version Manager (Node/Bun)
├── package.json        # Monorepo Configuration (Bun Workspaces)
└── tsconfig.json       # Base TypeScript Configuration
```

---

## 🚀 Memulai Pengembangan

### Prerequisites

Pastikan kamu sudah menginstall [Bun](https://bun.sh). Jika menggunakan `mise`, jalankan:

```bash
mise trust
```

### 1. Install Dependencies

```bash
bun install
```

### 2. Setup Database

Masuk ke direktori backend dan jalankan migrasi/generate client:

```bash
cd apps/backend
bunx prisma generate
```

### 3. Jalankan Mode Development

Kamu bisa menjalankan kedua aplikasi sekaligus dari root:

```bash
bun dev
```

- **Frontend**: `http://localhost:5173`
- **Backend**: `http://localhost:3000`
- **Swagger**: `http://localhost:3000/swagger`

---

## 🛠️ Perintah Terminal (Scripts)

| Perintah               | Deskripsi                                  |
| :--------------------- | :----------------------------------------- |
| `bun dev`              | Jalankan frontend & backend secara paralel |
| `bun run dev:frontend` | Jalankan hanya aplikasi frontend           |
| `bun run dev:backend`  | Jalankan hanya aplikasi backend            |
| `bun run build`        | Build semua aplikasi untuk produksi        |

---

## 📝 Catatan Arsitektur

Project ini menggunakan **Workspace Protocol** (`workspace:*`) untuk menghubungkan package lokal. Jika kamu mengubah file di `packages/shared`, perubahan tipenya akan otomatis terdeteksi di Frontend maupun Backend tanpa perlu build ulang package shared tersebut.

---

Made by [rafli](https://github.com/iniralfi)
