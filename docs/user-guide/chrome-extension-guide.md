# 🔌 Komfy Bridge — Chrome Extension

> Kết nối Komfy Studio với các nền tảng AI (Google Flow, v.v.) để tạo video AI trực tiếp trong Workflow Builder — không cần API key.

## Mục Lục

- [Tổng Quan](#tổng-quan)
- [Cài Đặt](#cài-đặt)
- [Cách Dùng](#cách-dùng)
- [Cập Nhật](#cập-nhật)
- [Xử Lý Sự Cố](#xử-lý-sự-cố)
- [Yêu Cầu Hệ Thống](#yêu-cầu-hệ-thống)

---

## Tổng Quan

**Komfy Bridge** là Chrome Extension cho phép Komfy Studio giao tiếp với các nền tảng AI bên ngoài. Hiện tại hỗ trợ:

| Nền tảng | Tính năng | Model |
|----------|-----------|-------|
| Google Flow | Tạo video AI | Veo 3.1 |

Extension hoạt động như cầu nối giữa Komfy Studio và trình duyệt Chrome, tự động đồng bộ session token và project ID để thực hiện các tác vụ AI trực tiếp từ Workflow Builder.

---

## Cài Đặt

Từ phiên bản v0.1.39 trở lên, extension được quản lý hoàn toàn bởi Komfy Studio:

1. Mở **Komfy Studio** → **Settings** → tab **Extension**
2. Extension sẽ tự động tải và cài đặt khi khởi động
3. Nếu chưa cài, nhấn nút **Install Now**
4. Copy đường dẫn extension hiển thị trên giao diện
5. Mở Chrome → `chrome://extensions` → bật **Developer mode** → **Load unpacked** → dán đường dẫn

> 💡 **Tip**: Extension tự động cập nhật khi Komfy Studio khởi động. Bạn chỉ cần reload extension trong Chrome sau khi có bản mới.

---

## Cách Dùng

### Kết nối Google Flow

1. Mở **Komfy Studio** (phải chạy trước)
2. Mở Chrome → vào <a href="https://labs.google/fx/tools/flow" target="_blank">Google Flow</a>
3. Đăng nhập Google account có quyền dùng Veo
4. Icon extension sáng xanh → kết nối thành công
5. Kiểm tra trong **Settings** → **Extension** → trạng thái **Connected**

### Sử dụng trong Workflow Builder

1. Mở tab **Workflows** trong Komfy Studio
2. Thêm node **Veo 3.1** vào canvas
3. Bật toggle **"Use Google Flow"** trên node
4. Kết nối input/output và nhấn **Run**
5. Extension tự động gửi request qua Google Flow và trả kết quả về

---

## Cập Nhật

Extension được cập nhật tự động bởi Komfy Studio:

- Khi khởi động, Komfy Studio tự kiểm tra phiên bản mới trên GitHub
- Nếu có bản mới → tự tải và cập nhật vào thư mục extension
- Sau khi cập nhật, vào Chrome → `chrome://extensions` → nhấn **🔄 Reload** trên extension
- Bạn cũng có thể nhấn **Reinstall** trong **Settings** → **Extension** để cài lại bất kỳ lúc nào

---

## Xử Lý Sự Cố

### Extension không kết nối?

1. Kiểm tra Komfy Studio đang chạy
2. Kiểm tra đã mở tab Google Flow và đăng nhập
3. Đợi 10-15 giây để extension đồng bộ
4. Thử reload extension trong `chrome://extensions`

### Icon extension không sáng xanh?

1. Click vào icon extension trong Chrome toolbar
2. Kiểm tra popup hiển thị trạng thái kết nối
3. Đảm bảo đang ở đúng trang Google Flow

### "Not installed" trong Settings?

1. Thử nhấn **Install Now** hoặc **Reinstall**
2. Kiểm tra kết nối internet (cần để tải từ GitHub)
3. Kiểm tra đường dẫn extension trong Settings → Extension

---

## Yêu Cầu Hệ Thống

| Yêu cầu | Chi tiết |
|----------|----------|
| Komfy Studio | v0.1.39 trở lên |
| Chrome / Chromium | v120 trở lên |
| Google Account | Có quyền truy cập Google Flow |
| OS | Windows 10/11 |
| Internet | Cần để tải extension và kết nối Google Flow |

---

## Xem Thêm

- [Hướng dẫn App Builder](./app-builder-guide.md)
- [Hướng dẫn App Store](./app-store-guide.md)
- <a href="https://github.com/tuyenhm68/komfy-extension" target="_blank">Source code Extension trên GitHub</a>
