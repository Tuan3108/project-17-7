# ⏰ Báo Thức Thông Minh (Smart Alarm Clock)

Một ứng dụng báo thức trực tuyến (Web App) hiện đại, trực quan và vô cùng tiện ích được xây dựng bằng công nghệ Web thuần túy (HTML, CSS và JavaScript). Ứng dụng sở hữu phong cách thiết kế Cyberpunk/Glassmorphism sang trọng với các hiệu ứng chuyển động mượt mà và âm thanh chất lượng cao được tổng hợp trực tiếp bằng Web Audio API.

## 🌟 Tính Năng Nổi Bật

- **🕰️ Đồng Hồ Thời Gian Thực Hiện Đại**: Hiển thị thời gian (Giờ:Phút:Giây) và ngày tháng tiếng Việt theo thời gian thực. Hiệu ứng nhịp đập (pulse) của vòng sáng đồng hồ đồng bộ theo từng giây.
- **🎨 Giao Diện Đậm Chất Sci-Fi (Cyberpunk)**: 
  - Phong cách Glassmorphism (kính mờ) thời thượng.
  - Các hình khối nền chuyển động lơ lửng (Floating Blobs) tạo chiều sâu.
  - Phối màu gradient hài hòa (tím, hồng, xanh lục, đỏ cảnh báo).
- **🔔 Thiết Lập Báo Thức Chi Tiết**:
  - Chọn Giờ và Phút trực quan.
  - Nhập nhãn (ghi chú) riêng cho từng báo thức (Ví dụ: *Dậy học bài*, *Họp nhóm*...).
  - Nút **Thử chuông** để nghe trước âm thanh cảnh báo (tự động tắt sau 5 giây để tránh làm phiền).
- **🎶 Bộ Tổng Hợp Âm Thanh Kỹ Thuật Số (Web Audio API)**:
  - Chuông báo thức được tổng hợp trực tiếp bằng mã nguồn (sử dụng sóng vuông `square wave` tần số 880Hz), tạo ra âm thanh bíp kép cổ điển, rõ ràng và đanh thép mà không cần tải file âm thanh ngoài (.mp3/.wav).
- **📝 Quản Lý Danh Sách Báo Thức Thông Minh**:
  - Tự động sắp xếp các báo thức theo thứ tự thời gian tăng dần.
  - Nhãn hiển thị thông minh: phân biệt báo thức sẽ reo vào **"Hôm nay"** hay **"Ngày mai"**.
  - Bật/tắt nhanh trạng thái hoạt động của báo thức thông qua nút gạt (switch) tiện lợi.
  - Xóa báo thức dễ dàng chỉ với một cú click.
  - Tự động lưu và đồng bộ danh sách báo thức vào **LocalStorage** của trình duyệt (không lo bị mất dữ liệu khi tải lại trang hoặc đóng trình duyệt).
- **🚨 Màn Hình Reo Toàn Màn Hình Ấn Tượng**:
  - Khi đến giờ báo thức, giao diện toàn màn hình sẽ xuất hiện cùng hiệu ứng nhấp nháy đỏ cảnh báo.
  - **Tắt ngay (Dismiss)**: Tắt chuông hoàn toàn và tự động vô hiệu hóa báo thức đó.
  - **Snooze (Hoãn 5 phút)**: Tạm tắt chuông và tự động hẹn giờ reo lại sau 5 phút, hỗ trợ đếm số lần hoãn (Snooze x1, x2...) ngay trên danh sách.

## 🛠️ Công Nghệ Sử Dụng

Ứng dụng được viết 100% bằng các công nghệ Web Core tiêu chuẩn, không cần qua bước biên dịch phức tạp:
1. **HTML5**: Định nghĩa cấu trúc trang web chuẩn SEO và dễ tiếp cận.
2. **Vanilla CSS3**: 
   - Biến số CSS (CSS Variables) quản lý hệ thống màu sắc thống nhất.
   - Grid & Flexbox cho bố cục responsive hoàn hảo trên mọi thiết bị di động, tablet, desktop.
   - CSS Keyframes tạo hiệu ứng chuyển động mềm mại cho các đốm sáng nền và chuông báo thức.
3. **Vanilla JavaScript (ES6)**:
   - Xử lý logic lập lịch báo thức, đồng hồ thời gian thực và quản lý trạng thái.
   - Sử dụng **Web Audio API** cho bộ phát âm thanh thời gian thực.
   - Sử dụng **LocalStorage API** để lưu trữ cấu hình báo thức của người dùng.

## 🚀 Hướng Dẫn Sử Dụng

### Cách 1: Chạy trực tiếp (Khuyên dùng cho người dùng phổ thông)
1. Tải thư mục dự án về máy tính của bạn.
2. Nhấp đúp (Double-click) vào tệp [index.html](file:///d:/T%C3%B4m/Obsidian/12-6/3.%20Resources/alarm-clock/index.html) để mở trực tiếp trên trình duyệt của bạn (Chrome, Edge, Firefox, Safari...).

### Cách 2: Chạy qua Web Server cục bộ (Dành cho nhà phát triển)
Nếu bạn muốn chạy ứng dụng qua môi trường server cục bộ (localhost):
- **Sử dụng NodeJS**:
  ```bash
  # Cài đặt công cụ serve tiện lợi
  npm install -g serve
  
  # Chạy server tại thư mục dự án
  serve .
  ```
- **Sử dụng Python**:
  ```bash
  # Python 3
  python -m http.server 8000
  ```
Sau đó truy cập địa chỉ `http://localhost:5000` (đối với Node serve) hoặc `http://localhost:8000` (đối với Python).

> [!IMPORTANT]
> **Lưu ý về quyền âm thanh (Autoplay Policy)**: Do chính sách bảo mật của các trình duyệt hiện đại, âm thanh báo thức chỉ có thể phát sau khi người dùng có ít nhất một tương tác (click, bấm nút...) trên trang. Ứng dụng đã tích hợp cơ chế tự động kích hoạt `Audio Context` ngay khi bạn click bất kỳ đâu trên màn hình.

---

*Phát triển bởi Antigravity 💜*
