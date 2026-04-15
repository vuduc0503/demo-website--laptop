# Computer Store Project (sản phẩm nhóm chưa hoàn thiện)

## Mô tả dự án

Đây là một dự án full-stack cho một cửa hàng máy tính trực tuyến, bao gồm backend API được xây dựng bằng Node.js và Express, cùng với frontend React. Dự án sử dụng Docker để dễ dàng triển khai và quản lý môi trường phát triển.

Dự án này được phát triển như một phần của việc học tập và thực hành kỹ năng lập trình web full-stack, nhằm mục đích xin thực tập tại các công ty công nghệ.

## Tính năng chính

- **Quản lý sản phẩm**: Thêm, sửa, xóa, và xem danh sách sản phẩm máy tính.
- **Quản lý đơn hàng**: Tạo đơn hàng, xem lịch sử đơn hàng.
- **Xác thực người dùng**: Đăng ký, đăng nhập, quên mật khẩu với JWT.
- **Quản lý kho**: Theo dõi số lượng tồn kho.
- **Báo cáo**: Xuất báo cáo đơn hàng và sản phẩm dưới dạng PDF/Excel.
- **Giao diện người dùng**: Frontend responsive với Ant Design.
- **API Documentation**: Swagger UI cho tài liệu API.

## Công nghệ sử dụng

### Backend
- **Node.js** với **Express.js** cho server.
- **SQLite** làm cơ sở dữ liệu.
- **JWT** cho xác thực.
- **bcryptjs** để mã hóa mật khẩu.
- **Multer** cho upload file.
- **Swagger** cho tài liệu API.
- **Nodemailer** cho gửi email.
- **PDFKit** và **ExcelJS** cho xuất báo cáo.

### Frontend
- **React** với **React Router** cho routing.
- **Ant Design** cho UI components.
- **Recharts** cho biểu đồ.
- **Swiper** cho carousel.

### DevOps
- **Docker** và **Docker Compose** cho containerization.

## Cài đặt và chạy

### Yêu cầu hệ thống
- Docker và Docker Compose được cài đặt.
- Node.js (phiên bản 14+) nếu chạy không dùng Docker.

### Chạy với Docker (Khuyến nghị)
1. Clone repository:
   ```
   git clone <repository-url>
   cd computer-store-project-master
   ```

2. Chạy Docker Compose:
   ```
   docker-compose up --build
   ```

3. Truy cập:
   - Frontend: http://localhost:3000
   - Backend API: http://localhost:5000
   - API Documentation: http://localhost:5000/api-docs

### Chạy thủ công (Không dùng Docker)
1. Backend:
   ```
   cd backend
   npm install
   npm run migrate
   npm run dev
   ```

2. Frontend:
   ```
   cd frontend
   npm install
   npm start
   ```

## Cấu trúc dự án

```
computer-store-project-master/
├── backend/
│   ├── config/          # Cấu hình database và seed data
│   ├── controllers/     # Logic xử lý API
│   ├── middleware/      # Middleware xác thực và upload
│   ├── migrations/      # Database migrations
│   ├── routes/          # Định nghĩa routes API
│   ├── services/        # Services cho email, etc.
│   ├── uploads/         # Thư mục upload files
│   ├── utils/           # Utilities
│   ├── Dockerfile
│   ├── package.json
│   └── server.js
├── frontend/
│   ├── public/          # Static files
│   ├── src/
│   │   ├── components/  # React components
│   │   ├── context/     # React context cho auth và cart
│   │   ├── pages/       # Các trang React
│   │   ├── services/    # API services
│   │   ├── styles/      # CSS files
│   │   └── utils/       # Utilities
│   ├── Dockerfile
│   └── package.json
├── docker-compose.yml
└── README.md
```

## API Endpoints chính

### Authentication
- `POST /api/auth/register` - Đăng ký
- `POST /api/auth/login` - Đăng nhập
- `POST /api/auth/forgot-password` - Quên mật khẩu

### Products
- `GET /api/products` - Lấy danh sách sản phẩm
- `POST /api/products` - Thêm sản phẩm (Admin)
- `PUT /api/products/:id` - Cập nhật sản phẩm
- `DELETE /api/products/:id` - Xóa sản phẩm

### Orders
- `GET /api/orders` - Lấy đơn hàng của user
- `POST /api/orders` - Tạo đơn hàng
- `PUT /api/orders/:id/status` - Cập nhật trạng thái đơn hàng

### Reports
- `GET /api/reports/orders` - Báo cáo đơn hàng
- `GET /api/reports/products` - Báo cáo sản phẩm

## Database Schema

Dự án sử dụng SQLite với các bảng chính:
- `users` - Thông tin người dùng
- `products` - Sản phẩm
- `orders` - Đơn hàng
- `order_items` - Chi tiết đơn hàng

Migrations được quản lý trong thư mục `backend/migrations/`.

## Đóng góp

Dự án này được phát triển bởi [Tên của bạn] như một portfolio project. Mọi đóng góp đều được chào đón!

## Liên hệ

- Email: vuduc022@gmail.com

## Giấy phép

ISC License