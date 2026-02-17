# Borrowdung Documentation

Dokumentasi lengkap untuk Sistem Peminjaman Ruangan Kampus (Borrowdung).

## Daftar Isi

- [Overview](#overview)
- [Architecture](#architecture)
- [API Documentation](#api-documentation)
- [User Guide](#user-guide)
- [Developer Guide](#developer-guide)

## Overview

Borrowdung adalah sistem peminjaman ruangan kampus berbasis web yang memungkinkan mahasiswa dan staf untuk:
- Melihat ketersediaan ruangan
- Mengajukan peminjaman ruangan
- Melacak status approval peminjaman
- Melihat riwayat peminjaman

## Architecture

### System Architecture

```
┌─────────────┐      API       ┌─────────────┐      ┌──────────────┐
│   Frontend  │ ◄─────────────► │   Backend   │ ◄───►│   Database   │
│ (React+TS)  │   REST/JSON    │  (ASP.NET)  │      │   (SQLite)   │
└─────────────┘                └─────────────┘      └──────────────┘
```

### Tech Stack

**Backend:**
- ASP.NET Core 8.0
- Entity Framework Core
- SQLite Database

**Frontend:**
- React 18
- TypeScript
- Tailwind CSS
- Vite

**Mobile:** (Planned)
- TBD

**Infrastructure:**
- TBD

## API Documentation

API documentation tersedia di:
- Swagger UI: http://localhost:5240/swagger
- Repository: [2026-borrowdung-backend](https://github.com/diwanparker/2026-borrowdung-backend)

### Main Endpoints

**Room Management:**
- `GET /api/Room` - List rooms
- `POST /api/Room` - Create room
- `PUT /api/Room/{id}` - Update room
- `DELETE /api/Room/{id}` - Delete room

**Booking Management:**
- `GET /api/Booking` - List bookings
- `POST /api/Booking` - Create booking
- `PUT /api/Booking/{id}/status` - Approve/Reject
- `DELETE /api/Booking/{id}` - Delete booking

## User Guide

### Untuk Admin

1. **Mengelola Ruangan**
   - Masuk ke halaman Rooms
   - Klik "Add Room" untuk menambah ruangan baru
   - Isi form dengan detail ruangan
   - Klik "Save"

2. **Mengelola Peminjaman**
   - Masuk ke halaman Bookings
   - Lihat daftar peminjaman yang masuk
   - Klik "Approve" untuk menyetujui
   - Klik "Reject" untuk menolak (sertakan alasan)

### Untuk User

1. **Melihat Ruangan Tersedia**
   - Buka halaman Rooms
   - Gunakan filter untuk mencari ruangan
   - Klik detail untuk melihat jadwal

2. **Mengajukan Peminjaman**
   - Klik "Create Booking"
   - Pilih ruangan
   - Isi detail peminjaman
   - Submit untuk approval

## Developer Guide

### Setup Development Environment

1. **Clone semua repositories:**
   ```bash
   git clone https://github.com/diwanparker/2026-borrowdung-backend.git
   git clone https://github.com/diwanparker/2026-borrowdung-frontend.git
   git clone https://github.com/diwanparker/2026-borrowdung-mobile.git
   git clone https://github.com/diwanparker/2026-borrowdung-infrastructure.git
   git clone https://github.com/diwanparker/2026-borrowdung-docs.git
   ```

2. **Backend Setup:**
   ```bash
   cd 2026-borrowdung-backend/BorrowdungAPI
   dotnet restore
   dotnet ef database update
   dotnet run
   ```

3. **Frontend Setup:**
   ```bash
   cd 2026-borrowdung-frontend
   npm install
   npm run dev
   ```

### Git Workflow

Branch Strategy:
- `main` - Production-ready code
- `develop` - Integration branch
- `feature/*` - New features
- `bugfix/*` - Bug fixes

Commit Convention:
- `feat:` - New feature
- `fix:` - Bug fix
- `docs:` - Documentation
- `chore:` - Maintenance

### Testing

**Backend:**
```bash
dotnet test
```

**Frontend:**
```bash
npm test
```

## Contributing

1. Fork repository
2. Create feature branch from `develop`
3. Commit menggunakan Conventional Commits
4. Push ke branch Anda
5. Buat Pull Request ke `develop`

## License

MIT License

## Credits

Developed by **PENS Students** untuk Project-Based Learning (PdBL) 2026.

---

**Last Updated:** 2026-02-17
