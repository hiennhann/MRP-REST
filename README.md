# MRP-REST

Kiến trúc project dự kiến

mrp_rest/
├── backend/                 # Backend FastAPI (Thành viên A, B, C)
│   ├── webapp/
│   │   ├── api/             # Các Endpoints API
│   │   │   ├── admin.py     # Task 5: Auth, Quản lý tài khoản, Master Data
│   │   │   ├── bom.py       # Task 6: Công thức BOM, Thuật toán check kho
│   │   │   └── inventory.py # Task 7: Transaction duyệt phiếu, Xuất báo cáo
│   │   ├── core/            # Cấu hình lõi
│   │   │   ├── config.py    # Load biến môi trường
│   │   │   └── security.py  # Xử lý JWT Token
│   │   ├── crud/            # File query CSDL (Thêm, Sửa, Xóa)
│   │   ├── models/          # Class SQLAlchemy (Ánh xạ bảng PostgreSQL)
│   │   ├── schemas/         # Class Pydantic (Validate dữ liệu đầu vào/ra)
│   │   ├── database.py      # File khởi tạo kết nối PostgreSQL
│   │   └── main.py          # Cổng chạy ứng dụng FastAPI
│   ├── .env                 # Chứa biến DATABASE_URL (Không push lên Git)
│   └── requirements.txt     # Khai báo thư viện (fastapi, sqlalchemy...)
│
├── frontend/                # Frontend React (Thành viên A, D, E)
│   ├── public/
│   ├── src/
│   │   ├── assets/          # CSS toàn cục, Hình ảnh
│   │   ├── components/      # UI dùng chung (Sidebar, Table, Button)
│   │   ├── pages/           # Chứa các màn hình
│   │   │   ├── admin/       # Task 5: Login, Quản lý tài khoản, Danh mục
│   │   │   ├── manager/     # Task 8, 9: Thiết lập BOM, Duyệt phiếu, Report
│   │   │   └── staff/       # Task 10: TaskBoard (Nhận lệnh), Lập phiếu
│   │   ├── services/        # File config Axios gọi API
│   │   ├── App.jsx          # Cấu hình Router điều hướng
│   │   └── main.jsx         # Khởi chạy React
│   ├── package.json         # Danh sách thư viện (react-router, tailwind...)
│   └── tailwind.config.js   # Cấu hình CSS Responsive
│
├── database/                # Scripts CSDL (Thành viên B)
│   ├── init_db.sql          # Script tạo bảng & khóa ngoại
│   └── mock_data.sql        # Script tạo dữ liệu mẫu
│
├── docs/                    # Tài liệu (Thành viên C, D, A)
│   ├── diagrams/            # Lưu 3 sơ đồ (Chức năng, Ngữ cảnh, DFD)
│   ├── mockups/             # Lưu ảnh thiết kế giao diện UI
│   └── report_final.docx    # Báo cáo Word
│
├── .gitignore               # Chặn file rác (node_modules/, venv/, .env)
└── README.md                # Hướng dẫn setup và chạy project