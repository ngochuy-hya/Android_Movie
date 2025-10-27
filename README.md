# 🎬 RealFilm - Ứng Dụng Xem Phim Android

Dự án cuối kỳ môn Lập Trình Di Động - Thầy Trung  
**Năm học:** 2024-2025

## 👥 Sinh viên thực hiện

- **Nguyễn Ngọc Huy** - MSSV: 22110332
- **Võ Duy Khoa** - MSSV: 22110354

---

## 📋 Tổng quan dự án

**RealFilm** là một ứng dụng xem phim trực tuyến hoàn chỉnh, bao gồm:
- 📱 **Android App**: Ứng dụng di động được xây dựng bằng Java
- 🔧 **REST API Backend**: Server API được xây dựng bằng Node.js + TypeScript
- 🗄️ **MySQL Database**: Cơ sở dữ liệu lưu trữ thông tin phim, người dùng, và tương tác

---

## 🏗️ Kiến trúc hệ thống

```
Android_Movie/
├── API/                          # Backend REST API
│   ├── movies-rest-api/         # Node.js + TypeScript API
│   └── real_film.sql            # Database schema
│
└── UI/                          # Frontend Mobile App
    └── movies-android/          # Android Application (Java)
```

---

## 🚀 Tính năng chính

### 👤 Quản lý người dùng
- ✅ Đăng ký tài khoản mới
- ✅ Đăng nhập / Đăng xuất
- ✅ Quên mật khẩu với OTP
- ✅ Đổi mật khẩu
- ✅ Cập nhật thông tin cá nhân
- ✅ Xem hồ sơ người dùng

### 🎥 Quản lý phim
- ✅ Xem danh sách phim
- ✅ Tìm kiếm phim
- ✅ Xem thông tin chi tiết phim
- ✅ Xem trailer và phim đầy đủ
- ✅ Lọc phim theo thể loại
- ✅ Lọc phim theo quốc gia
- ✅ Phim đề xuất

### 👨‍💼 Quản trị viên
- ✅ Thêm phim mới
- ✅ Chỉnh sửa thông tin phim
- ✅ Xóa phim
- ✅ Quản lý danh sách phim

### 💬 Tương tác
- ✅ Bình luận phim
- ✅ Đánh giá phim (Rating)
- ✅ Yêu thích phim (Favorite)

---

## 🛠️ Công nghệ sử dụng

### Backend API (Node.js)

| Công nghệ | Phiên bản | Mục đích |
|-----------|-----------|----------|
| Node.js | - | Runtime environment |
| Express | ^4.18.2 | Web framework |
| TypeScript | ^5.1.3 | Type-safe JavaScript |
| Sequelize | ^6.32.0 | ORM cho MySQL |
| MySQL2 | ^3.3.3 | MySQL driver |
| JWT | ^9.0.0 | Authentication |
| Bcryptjs | ^2.4.3 | Password hashing |
| Multer | ^1.4.5 | File upload |
| Nodemailer | ^7.0.3 | Email service (OTP) |
| Yup | ^1.2.0 | Schema validation |

### Android App (Java)

| Công nghệ | Phiên bản | Mục đích |
|-----------|-----------|----------|
| Java | 8 | Programming language |
| Android SDK | API 21-33 | Android framework |
| Firebase | 31.0.0 | Backend services |
| - Firebase Auth | - | Authentication |
| - Firebase Firestore | - | Cloud database |
| - Firebase Storage | - | File storage |
| Retrofit | 2.4.0 | REST API client |
| Gson | 2.8.5 | JSON parsing |
| Glide | 4.8.0 | Image loading |
| ExoPlayer | 2.13.3 | Video playback |
| Material Design | - | UI components |
| OkHttp | 4.9.1 | HTTP client |

---

## 📦 Cài đặt và Chạy dự án

### 1️⃣ Backend API

#### Yêu cầu hệ thống
- Node.js (v14 trở lên)
- MySQL Server
- npm hoặc yarn

#### Các bước cài đặt

```bash
# 1. Di chuyển vào thư mục API
cd API/movies-rest-api

# 2. Cài đặt dependencies
npm install
# hoặc
yarn install

# 3. Cấu hình database
# - Import file real_film.sql vào MySQL
mysql -u root -p < ../real_film.sql

# 4. Tạo file .env và cấu hình
# Tham khảo file .env.example (nếu có)

# 5. Build TypeScript
npm run build
# hoặc
tsc

# 6. Chạy server
npm start
# hoặc
node dist/server.js
```

#### API Endpoints

Server chạy tại: `http://localhost:3000`

**Base URL:** `/api/v1`

| Method | Endpoint | Mô tả |
|--------|----------|-------|
| POST | `/users/register` | Đăng ký tài khoản |
| POST | `/users/login` | Đăng nhập |
| GET | `/users/profile` | Lấy thông tin user |
| PUT | `/users/profile` | Cập nhật thông tin |
| POST | `/users/forgot-password` | Quên mật khẩu |
| GET | `/movies` | Lấy danh sách phim |
| GET | `/movies/:id` | Lấy chi tiết phim |
| POST | `/movies` | Thêm phim mới (Admin) |
| PUT | `/movies/:id` | Cập nhật phim (Admin) |
| DELETE | `/movies/:id` | Xóa phim (Admin) |
| GET | `/genres` | Lấy danh sách thể loại |
| GET | `/countries` | Lấy danh sách quốc gia |
| POST | `/comments` | Thêm bình luận |
| GET | `/comments/:movieId` | Lấy bình luận phim |
| POST | `/ratings` | Đánh giá phim |
| GET | `/ratings/:movieId` | Lấy đánh giá phim |
| POST | `/favorites` | Thêm/xóa yêu thích |
| GET | `/favorites` | Lấy danh sách yêu thích |

### 2️⃣ Android App

#### Yêu cầu hệ thống
- Android Studio (Arctic Fox trở lên)
- JDK 8
- Android SDK (API 21-33)
- Thiết bị Android hoặc Emulator

#### Các bước cài đặt

```bash
# 1. Mở Android Studio

# 2. Import project
File -> Open -> Chọn thư mục UI/movies-android

# 3. Cấu hình Firebase
# - Đăng nhập vào Firebase Console
# - Tạo project mới hoặc sử dụng project có sẵn
# - Download file google-services.json
# - Đặt file vào thư mục app/

# 4. Cấu hình API endpoint
# Mở file: app/src/main/java/com/example/RealFilm/utils/Constants.java
# Cập nhật BASE_URL về địa chỉ server API của bạn

# 5. Sync Gradle
# Android Studio sẽ tự động download dependencies

# 6. Build và Run
# Click nút Run hoặc Shift + F10
```

#### Cấu hình API URL

Trong file `Constants.java`, cập nhật:

```java
public static final String BASE_URL = "http://YOUR_IP_ADDRESS:3000/api/v1/";
```

⚠️ **Lưu ý:** 
- Nếu chạy trên Emulator: dùng `http://10.0.2.2:3000/api/v1/`
- Nếu chạy trên thiết bị thật: dùng IP máy tính trong cùng mạng

---

## 📱 Cấu trúc Android App

### Activities
- `SplashActivity` - Màn hình khởi động
- `LoginActivity` - Đăng nhập
- `RegisterActivity` - Đăng ký
- `ForgotPasswordActivity` - Quên mật khẩu
- `OtpActivity` - Xác thực OTP
- `MainActivity` - Màn hình chính (chứa fragments)
- `MoviesActivity` - Danh sách phim
- `MoviesInformationActivity` - Chi tiết phim
- `WatchMoviesActivity` - Xem phim
- `AddMoviesActivity` - Thêm phim (Admin)
- `EditMovieActivity` - Chỉnh sửa phim (Admin)
- `ManagerMovies` - Quản lý phim (Admin)
- `ChangeInformationActivity` - Đổi thông tin
- `ChangePasswordActivity` - Đổi mật khẩu

### Fragments
- `HomeFragment` - Trang chủ
- `SearchFragment` - Tìm kiếm
- `RecommendFragment` - Đề xuất
- `UserProfileFragment` - Hồ sơ người dùng
- `SettingFragment` - Cài đặt
- `CommentsFragment` - Bình luận
- `RateStarFragment` - Đánh giá
- `ChangePasswordFragment` - Đổi mật khẩu

### Services
- `ApiService` - Retrofit API interface
- `UserService` - API calls cho User
- `MovieService` - API calls cho Movie
- `CommentService` - API calls cho Comment
- `RatingService` - API calls cho Rating
- `CommonService` - API calls chung

### Models
- `User` - Model người dùng
- `Movie` - Model phim
- `Comment` - Model bình luận
- `Rate` - Model đánh giá
- `Genre` - Model thể loại
- `Country` - Model quốc gia
- `ApiResponse` - Model response API
- `Status` - Model trạng thái

---

## 🗄️ Cơ sở dữ liệu

### Tables chính

**users**
- id, username, email, password, fullname, phone, avatar, role, created_at, updated_at

**movies**
- id, title, description, genre, director, releaseYear, duration, posterHorizontal, posterVertical, country, actors, videoURL, trailerURL

**comments**
- id, user_id, movie_id, content, created_at, updated_at

**ratings**
- id, user_id, movie_id, rating, created_at, updated_at

**favorites**
- id, user_id, movie_id, created_at, updated_at

**genres**
- id, name, created_at, updated_at

**countries**
- id, name, created_at, updated_at

---

## 🔐 Authentication

Ứng dụng sử dụng **JWT (JSON Web Token)** cho xác thực:

1. User đăng nhập với username/email và password
2. Server xác thực và trả về JWT token
3. Client lưu token và gửi kèm trong header của mỗi request
4. Server verify token trước khi xử lý request

**Header format:**
```
Authorization: Bearer <token>
```

---

## 📸 Screenshots

*(Có thể thêm screenshots của ứng dụng ở đây)*

---

## 🔄 Flow hoạt động

### User Flow
1. **Đăng ký/Đăng nhập** → Xác thực với Firebase/API
2. **Trang chủ** → Xem danh sách phim trending
3. **Tìm kiếm** → Tìm phim theo tên, thể loại, quốc gia
4. **Chi tiết phim** → Xem thông tin, trailer, rating, comments
5. **Xem phim** → Phát video với ExoPlayer
6. **Tương tác** → Like, Comment, Rate phim

### Admin Flow
1. **Đăng nhập với quyền Admin**
2. **Quản lý phim** → Thêm/Sửa/Xóa phim
3. **Upload media** → Upload poster và video lên Firebase Storage

---

## ⚙️ Cấu hình môi trường

### Backend (.env)
```env
# Database
DB_HOST=localhost
DB_USER=root
DB_PASSWORD=your_password
DB_NAME=real_film
DB_PORT=3306

# JWT
JWT_SECRET=your_jwt_secret
JWT_EXPIRES_IN=7d

# Email (cho OTP)
EMAIL_HOST=smtp.gmail.com
EMAIL_PORT=587
EMAIL_USER=your_email@gmail.com
EMAIL_PASSWORD=your_app_password

# Server
PORT=3000
```

### Android (Constants.java)
```java
public static final String BASE_URL = "http://10.0.2.2:3000/api/v1/";
public static final int TIMEOUT = 30; // seconds
```

---

## 🐛 Troubleshooting

### Lỗi kết nối API từ Android
- ✅ Kiểm tra BASE_URL trong Constants.java
- ✅ Đảm bảo server đang chạy
- ✅ Kiểm tra firewall
- ✅ Nếu dùng HTTPS, cần cấu hình Network Security Config

### Lỗi Firebase
- ✅ Kiểm tra file google-services.json
- ✅ Đảm bảo package name khớp với Firebase Console
- ✅ Kiểm tra Firebase Authentication đã enable

### Lỗi Database
- ✅ Kiểm tra MySQL đang chạy
- ✅ Import đúng file real_film.sql
- ✅ Kiểm tra thông tin kết nối trong .env

---

## 📝 Ghi chú phát triển

### Các API cần authentication
Hầu hết các endpoint đều cần JWT token, trừ:
- POST `/users/register`
- POST `/users/login`
- POST `/users/forgot-password`
- GET `/movies` (public)
- GET `/genres` (public)
- GET `/countries` (public)

### Upload file
- API sử dụng **Multer** để xử lý file upload
- Android upload lên **Firebase Storage** và gửi URL về API

---

## 📚 Tài liệu tham khảo

- [Android Developer Guide](https://developer.android.com/)
- [Firebase Documentation](https://firebase.google.com/docs)
- [Express.js Documentation](https://expressjs.com/)
- [Sequelize ORM](https://sequelize.org/)
- [Retrofit Documentation](https://square.github.io/retrofit/)
- [ExoPlayer Guide](https://exoplayer.dev/)

---

## 📄 License

Dự án này được phát triển cho mục đích học tập tại trường.  
© 2024-2025 - Nguyễn Ngọc Huy & Võ Duy Khoa

---

## 📞 Liên hệ

Nếu có thắc mắc về dự án, vui lòng liên hệ:
- **Nguyễn Ngọc Huy** - 22110332
- **Võ Duy Khoa** - 22110354

---

⭐ **Cảm ơn thầy đã hướng dẫn!** ⭐
