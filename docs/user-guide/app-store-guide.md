# 🏪 Hướng Dẫn Sử Dụng App Store

**App Store** là nền tảng cộng đồng cho phép bạn khám phá, cài đặt và chia sẻ các ứng dụng AI được tạo bởi cộng đồng Komfy Studio.

---

## 📋 Mục Lục

- [Giới Thiệu](#giới-thiệu)
- [Truy Cập App Store](#truy-cập-app-store)
- [Tìm Kiếm & Khám Phá](#tìm-kiếm--khám-phá)
- [Cài Đặt Ứng Dụng](#cài-đặt-ứng-dụng)
- [Cập Nhật Ứng Dụng](#cập-nhật-ứng-dụng)
- [Quản Lý Ứng Dụng Đã Cài](#quản-lý-ứng-dụng-đã-cài)
- [Xuất Bản Ứng Dụng](#xuất-bản-ứng-dụng)
- [Tips & Best Practices](#tips--best-practices)
- [Xử Lý Sự Cố](#xử-lý-sự-cố)

---

## 🎯 Giới Thiệu

App Store cung cấp:

- 🔍 **Khám phá ứng dụng**: Duyệt qua thư viện ứng dụng từ cộng đồng
- 📥 **Cài đặt một chạm**: Tải và cài đặt ứng dụng dễ dàng
- 🔄 **Tự động cập nhật**: Nhận thông báo khi có phiên bản mới
- 🏷️ **Phân loại rõ ràng**: Tìm kiếm theo category và tags
- ⭐ **Đánh giá & Reviews**: Xem đánh giá từ người dùng khác
- 📤 **Chia sẻ dễ dàng**: Publish ứng dụng của bạn lên Store

---

## 🚀 Truy Cập App Store

### Cách Mở App Store

1. Mở **Komfy Studio**
2. Click vào tab **"Store"** trên thanh sidebar bên trái (icon 🏪)
3. Hoặc từ **Apps > App Store** trong menu

### Giao Diện App Store

App Store được chia thành 3 khu vực chính:

#### 1️⃣ Sidebar Trái - Tìm Kiếm & Lọc

- **Search Bar**: Tìm kiếm ứng dụng theo tên, mô tả
- **Categories**: Lọc theo danh mục
  - 🎨 **All**: Tất cả ứng dụng
  - 🖼️ **Image**: Ứng dụng xử lý ảnh
  - 🎬 **Video**: Ứng dụng xử lý video
  - 🎵 **Audio**: Ứng dụng xử lý âm thanh

#### 2️⃣ Top Bar - Backend Status

- Hiển thị trạng thái kết nối backend
- Chọn backend đang sử dụng
- Refresh backend health

#### 3️⃣ Main Content - Danh Sách Ứng Dụng

- Grid layout hiển thị các app cards
- Mỗi card hiển thị:
  - **Icon**: Biểu tượng ứng dụng
  - **Tên**: Tên ứng dụng
  - **Tác giả**: Người tạo ứng dụng
  - **Rating**: Đánh giá trung bình (⭐)
  - **Installs**: Số lượt cài đặt
  - **Status**: Trạng thái (Installed, Update Available)
  - **Action Button**: Install/Update/Installed

---

## 🔍 Tìm Kiếm & Khám Phá

### Tìm Kiếm Theo Từ Khóa

1. **Nhập từ khóa** vào ô Search
2. Hệ thống tìm kiếm trong:
   - Tên ứng dụng
   - Mô tả
   - Tags
   - Tên tác giả
3. Kết quả hiển thị real-time

**Ví dụ từ khóa**:
- "portrait" - Tìm app tạo chân dung
- "anime" - Tìm app phong cách anime
- "fast" - Tìm app tạo nhanh
- "realistic" - Tìm app phong cách realistic

### Lọc Theo Category

Click vào category trong sidebar:

- **All**: Hiển thị tất cả ứng dụng
- **Image**: Chỉ hiển thị app xử lý ảnh
- **Video**: Chỉ hiển thị app xử lý video
- **Audio**: Chỉ hiển thị app xử lý âm thanh

### Sắp Xếp

Các tùy chọn sắp xếp (sắp có):
- **Popular**: Theo số lượt cài đặt (mặc định)
- **Newest**: Theo thời gian publish
- **Rating**: Theo đánh giá cao nhất

---

## 📥 Cài Đặt Ứng Dụng

### Quy Trình Cài Đặt

#### 1️⃣ Chọn Ứng Dụng

1. **Tìm app** bạn muốn cài đặt
2. **Xem thông tin**:
   - Đọc mô tả
   - Kiểm tra requirements
   - Xem rating và số lượt cài đặt

#### 2️⃣ Click Install

1. Click nút **"Install"** (icon 📥) trên app card
2. Hệ thống bắt đầu quá trình cài đặt

#### 3️⃣ Quá Trình Cài Đặt

Hệ thống sẽ tự động:

1. **Download .kapp file**:
   - Tải app package
   - Hiển thị progress bar

2. **Extract package**:
   - Giải nén file .kapp
   - Đọc metadata, workflow, UI layout

3. **Validate dependencies**:
   - Kiểm tra models cần thiết
   - Kiểm tra custom nodes cần thiết

4. **Install dependencies** (nếu thiếu):
   - **Models**: Tự động tải models thiếu
   - **Custom Nodes**: Tự động cài đặt nodes thiếu
   - Hiển thị progress cho từng item

5. **Save to database**:
   - Lưu app vào local database
   - Lưu icon (base64) để dùng offline

6. **Complete**:
   - Hiển thị thông báo "Installed successfully"
   - App xuất hiện trong **My Apps**
   - Nút chuyển thành **"Installed"** (✅)

#### 4️⃣ Sử Dụng App

Sau khi cài đặt:

1. Vào **Apps > My Apps**
2. Tìm app vừa cài đặt
3. Click vào app để mở và sử dụng

### Dependencies Auto-Install

**Ưu điểm của hệ thống tự động**:

- ✅ **Không cần thao tác thủ công**: Hệ thống tự động tải và cài đặt
- ✅ **Progress tracking**: Theo dõi tiến trình từng bước
- ✅ **Error handling**: Xử lý lỗi và retry tự động
- ✅ **Offline support**: Icon và metadata được lưu offline

**Lưu ý**:

- ⚠️ Quá trình cài đặt có thể mất vài phút nếu cần tải models lớn
- ⚠️ Đảm bảo có đủ dung lượng ổ cứng
- ⚠️ Kết nối internet ổn định cho việc download

---

## 🔄 Cập Nhật Ứng Dụng

### Phát Hiện Updates

Hệ thống tự động kiểm tra updates khi:

- Mở App Store
- Refresh danh sách apps
- Định kỳ (background check)

### Thông Báo Update

Khi có phiên bản mới:

- **Badge màu vàng** xuất hiện trên app card
- Text **"NEW v1.2.0"** (version mới)
- Nút chuyển thành **"Update"** (icon 🔄)

### Cài Đặt Update

1. **Click nút "Update"** trên app card
2. Hệ thống sẽ:
   - Download phiên bản mới
   - Cập nhật metadata
   - Cập nhật workflow (nếu có thay đổi)
   - Cập nhật UI layout (nếu có thay đổi)
   - Cài đặt dependencies mới (nếu có)
3. **Hoàn tất**: App được cập nhật lên version mới

### Version Management

- Hệ thống theo dõi version hiện tại và version mới nhất
- So sánh theo chuẩn **Semantic Versioning**
- Chỉ hiển thị update nếu version mới > version hiện tại

**Ví dụ**:
- Local: v1.0.0
- Store: v1.2.0
- → Hiển thị "Update Available"

---

## 📱 Quản Lý Ứng Dụng Đã Cài

### Xem Danh Sách

Vào **Apps > My Apps** để xem:

- Tất cả apps đã cài đặt
- Apps tự tạo (từ App Builder)
- Trạng thái từng app

### Phân Biệt App Types

#### Apps Từ Store:

- **Source**: "App Store"
- **Có thể update**: Khi tác giả release version mới
- **Có publish_id**: Liên kết với app trên Store

#### Apps Tự Tạo:

- **Source**: "Local"
- **Không auto-update**: Bạn tự quản lý version
- **Có thể publish**: Lên App Store để chia sẻ

### Chức Năng Quản Lý

#### ✏️ Edit

- **Apps tự tạo**: Có thể edit bất kỳ lúc nào
- **Apps từ Store**: Không thể edit (để giữ nguyên bản gốc)

#### 🗑️ Uninstall

1. Click icon **Delete** (🗑️)
2. Xác nhận xóa
3. App sẽ bị xóa khỏi local database

**Lưu ý**:
- Dependencies (models, nodes) KHÔNG bị xóa
- Có thể cài đặt lại từ Store bất kỳ lúc nào

---

## 📤 Xuất Bản Ứng Dụng

### Ai Có Thể Publish?

- Bất kỳ ai có tài khoản Komfy Studio
- Đã tạo app bằng App Builder
- App đã được test kỹ và hoạt động tốt

### Quy Trình Publish

Chi tiết xem tại [App Builder Guide - Publishing Section](app-builder-guide.md#xuất-bản-lên-app-store)

**Tóm tắt**:

1. **Tạo app** bằng App Builder
2. **Test kỹ** trong My Apps
3. **Click "Publish"** từ My Apps hoặc App Builder
4. **Xác nhận thông tin**
5. **App xuất hiện trên Store** ngay lập tức

### Quyền Lợi Khi Publish

- ✅ Chia sẻ sáng tạo với cộng đồng
- ✅ Nhận feedback từ người dùng
- ✅ Theo dõi số lượt cài đặt
- ✅ Xây dựng reputation trong cộng đồng
- ✅ Đóng góp vào hệ sinh thái Komfy Studio

### Trách Nhiệm

- ⚠️ Đảm bảo app hoạt động đúng
- ⚠️ Cung cấp thông tin đầy đủ, chính xác
- ⚠️ Liệt kê đầy đủ requirements
- ⚠️ Không publish app có nội dung không phù hợp
- ⚠️ Tôn trọng bản quyền và tác giả gốc

---

## 💡 Tips & Best Practices

### Khi Tìm Kiếm App

- ✅ Đọc kỹ mô tả trước khi cài đặt
- ✅ Kiểm tra requirements (models, nodes)
- ✅ Xem rating và số lượt cài đặt
- ✅ Ưu tiên apps có mô tả chi tiết
- ✅ Kiểm tra version và ngày cập nhật

### Khi Cài Đặt

- ✅ Đảm bảo đủ dung lượng ổ cứng
- ✅ Kết nối internet ổn định
- ✅ Đợi quá trình cài đặt hoàn tất
- ✅ Đọc hướng dẫn sử dụng (nếu có)
- ✅ Test app sau khi cài đặt

### Khi Publish

- ✅ Test kỹ trước khi publish
- ✅ Viết mô tả rõ ràng, chi tiết
- ✅ Upload icon chất lượng cao
- ✅ Liệt kê đầy đủ requirements
- ✅ Chọn category và tags phù hợp
- ✅ Cập nhật version đúng chuẩn

### Quản Lý Apps

- ✅ Thường xuyên check updates
- ✅ Uninstall apps không dùng để tiết kiệm dung lượng
- ✅ Organize apps theo category
- ✅ Đánh giá và review apps đã dùng (sắp có)

---

## 🔧 Xử Lý Sự Cố

### Không Thể Kết Nối App Store

**Triệu chứng**: Không load được danh sách apps

**Giải pháp**:
- Kiểm tra kết nối internet
- Thử refresh trang (Ctrl+R)
- Kiểm tra firewall/antivirus có chặn không
- Xem console logs để debug

### Cài Đặt Thất Bại

**Triệu chứng**: Lỗi khi cài đặt app

**Giải pháp**:

1. **Lỗi download**:
   - Kiểm tra kết nối internet
   - Thử lại sau vài phút
   - Kiểm tra dung lượng ổ cứng

2. **Lỗi dependencies**:
   - Kiểm tra backend đang chạy
   - Verify models path đúng
   - Thử cài đặt dependencies thủ công
   - Xem logs để biết dependency nào bị lỗi

3. **Lỗi database**:
   - Restart ứng dụng
   - Kiểm tra quyền ghi file
   - Xóa cache và thử lại

### App Không Xuất Hiện Sau Khi Cài

**Triệu chứng**: Cài đặt thành công nhưng không thấy app

**Giải pháp**:
- Refresh trang My Apps
- Kiểm tra tab "My Apps" đã được chọn
- Xem console logs
- Restart ứng dụng
- Kiểm tra database có lưu app không

### Update Thất Bại

**Triệu chứng**: Không thể cập nhật app

**Giải pháp**:
- Thử uninstall và install lại
- Kiểm tra version number hợp lệ
- Verify kết nối internet
- Xem logs để biết lỗi cụ thể
- Báo cáo cho tác giả app

### Icon Không Hiển Thị

**Triệu chứng**: App card hiển thị icon mặc định thay vì icon tùy chỉnh

**Giải pháp**:
- Refresh trang
- Clear cache trình duyệt
- Kiểm tra icon URL có hợp lệ không
- Thử cài đặt lại app
- Báo cáo cho tác giả app

### Publish Bị Từ Chối

**Triệu chứng**: Không thể publish app lên Store

**Giải pháp**:
- Kiểm tra đã đăng nhập chưa
- Verify tất cả required fields đã điền
- Kiểm tra version number (phải > version cũ)
- Đảm bảo icon đã upload
- Kiểm tra kết nối internet
- Xem error message cụ thể

---

## 🎯 Roadmap Features

Các tính năng sắp có:

- ⏳ **Ratings & Reviews**: Đánh giá và review apps
- ⏳ **Comments**: Bình luận và thảo luận
- ⏳ **Favorites**: Đánh dấu apps yêu thích
- ⏳ **Collections**: Tạo bộ sưu tập apps
- ⏳ **Advanced Search**: Tìm kiếm nâng cao với filters
- ⏳ **Author Profiles**: Trang cá nhân tác giả
- ⏳ **Analytics**: Thống kê cho tác giả
- ⏳ **Monetization**: Hỗ trợ apps trả phí (tùy chọn)

---

## 📞 Hỗ Trợ

### Báo Cáo Vấn Đề

Nếu gặp vấn đề với:

- **App Store platform**: Tạo issue trên GitHub
- **Specific app**: Liên hệ tác giả app
- **Installation/Update**: Xem [Troubleshooting](../troubleshooting/common-issues.md)

### Đóng Góp

Bạn có thể đóng góp bằng cách:

- 📝 Publish apps chất lượng
- ⭐ Đánh giá và review apps (sắp có)
- 🐛 Báo cáo bugs
- 💡 Đề xuất tính năng mới
- 📖 Cải thiện documentation

---

## 🔗 Liên Kết Liên Quan

- [App Builder Guide](app-builder-guide.md) - Hướng dẫn tạo app
- [Getting Started](getting-started.md) - Bắt đầu với Komfy Studio
- [Models Management](models-management.md) - Quản lý models
- [Troubleshooting](../troubleshooting/common-issues.md) - Xử lý sự cố

---

**Cập nhật lần cuối**: 2026-02-06  
**Phiên bản**: 1.0.0
