# MRP-REST - HỆ THỐNG QUẢN LÝ NGUYÊN VẬT LIỆU NHÀ HÀNG

##📁 CẤU TRÚC THƯ MỤC
```text
mrp_rest/
├── backend/                    # Mã nguồn Backend (NestJS)
│   ├── src/
│   │   ├── core/               # Cấu hình lõi & dependencies dùng chung
│   │   │   ├── config/         # Biến môi trường (.env validation)
│   │   │   ├── database/       # Cấu hình kết nối PostgreSQL (TypeORM/Prisma)
│   │   │   ├── exceptions/     # Global Error Filters (Bắt lỗi chuẩn hóa API)
│   │   │   └── security/       # JWT Strategy, Roles Guards (Phân quyền)
│   │   │
│   │   ├── modules/            # Các module nghiệp vụ (Modular Monolith)
│   │   │   ├── auth/           # Đăng nhập, đổi mật khẩu, refresh token (Task 5)
│   │   │   ├── users/          # Quản lý tài khoản, nhân viên (Task 6)
│   │   │   ├── catalog/        # Danh mục NVL, Đơn vị tính, NCC (Task 6)
│   │   │   ├── bom/            # Cấu trúc công thức đa tầng (Task 7, 10)
│   │   │   ├── production/     # Lệnh sản xuất, kiểm tra tồn kho (Task 7, 14)
│   │   │   ├── inventory/      # Transaction Nhập/Xuất, Back-flushing (Task 8, 12)
│   │   │   └── waste/          # Xử lý báo cáo hao hụt (Task 9, 13)
│   │   │
│   │   ├── websockets/         # Xử lý Real-time
│   │   │   └── events.gateway.ts # Bắn tín hiệu khi có phiếu duyệt/lệnh hoàn thành
│   │   │
│   │   ├── app.module.ts       # Nơi import tập trung tất cả modules
│   │   └── main.ts             # Khởi chạy NestJS (Cấu hình CORS, Swagger)
│   │
│   ├── package.json
│   └── .env.example
│
├── frontend/                   # Mã nguồn Frontend (React + Vite)
│   ├── src/
│   │   ├── core/               # Cấu hình lõi FE
│   │   │   ├── api/            # Axios instance (Tự động gắn JWT Token)
│   │   │   ├── store/          # Quản lý State toàn cục (Zustand/Redux)
│   │   │   └── websockets/     # Custom Hook kết nối Socket.io client
│   │   │
│   │   ├── features/           # Giao diện chia theo phân hệ (Khớp với BE)
│   │   │   ├── admin/          # Form tạo BOM, quản lý Danh mục
│   │   │   ├── kitchen/        # Taskboard Bếp, Báo hao hụt, Xin NVL
│   │   │   └── warehouse/      # Tab duyệt phiếu, Biểu đồ thống kê tồn kho
│   │   │
│   │   ├── components/         # UI Components dùng chung (Dumb components)
│   │   │   ├── ui/             # Buttons, Inputs, Modal, Table
│   │   │   └── layout/         # Sidebar (đổi theo Role), Header
│   │   │
│   │   ├── routes/             # Cấu hình React Router (Protected & Role Routes)
│   │   ├── App.jsx
│   │   └── main.jsx
│   │
│   ├── package.json
│   └── tailwind.config.js      # Nếu dùng TailwindCSS
│
├── db/                         # Database Scripts (Giống dự án mẫu)
│   ├── migrations/             # Chứa file tự sinh của TypeORM/Prisma
│   └── seed/                   # File SQL/TS tạo data mẫu (Tài khoản Admin, Đơn vị tính)
│
├── docs/                       # Tài liệu BA (Task 2), Thiết kế DB (Task 3)
├── docker-compose.yml          # Chạy PostgreSQL & pgAdmin
└── README.md                   # Hướng dẫn setup project
