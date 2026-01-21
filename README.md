# 🎨 KomfyStudio

**Nền tảng tạo ảnh & video AI được hỗ trợ bởi ComfyUI**

[![Phiên bản](https://img.shields.io/github/v/release/tuyenhm68/KomfyStudio)](https://github.com/tuyenhm68/KomfyStudio/releases)
[![Tải xuống](https://img.shields.io/github/downloads/tuyenhm68/KomfyStudio/total)](https://github.com/tuyenhm68/KomfyStudio/releases)
[![Giấy phép](https://img.shields.io/github/license/tuyenhm68/KomfyStudio)](LICENSE)

---

## 📥 Tải Xuống

**[⬇️ Tải phiên bản mới nhất](https://github.com/tuyenhm68/KomfyStudio/releases/latest)**

### Yêu Cầu Hệ Thống

- **Hệ điều hành**: Windows 10/11 (64-bit)
- **RAM**: Tối thiểu 8GB (Khuyến nghị 16GB+)
- **GPU**: NVIDIA GPU với CUDA support (Khuyến nghị)
- **Dung lượng**: 5GB+ dung lượng trống

---

## ✨ Tính Năng Chính

### 🖼️ Tạo Ảnh AI

- **Text-to-Image (T2I)**: Tạo ảnh từ mô tả văn bản
- **Image-to-Image (I2I)**: Chỉnh sửa và biến đổi ảnh
- **Photo Restore**: Phục hồi và nâng cao chất lượng ảnh cũ
- **Inpainting**: Xóa và thay thế đối tượng trong ảnh
- Hỗ trợ nhiều định dạng: Landscape, Square, Portrait

### 🎬 Tạo Video AI

- **Text-to-Video (T2V)**: Tạo video từ mô tả văn bản
- **Image-to-Video (I2V)**: Chuyển ảnh tĩnh thành video động
- Kiểm soát thời lượng và chất lượng video
- Hỗ trợ nhiều tỷ lệ khung hình

### 🎵 Tạo Âm Thanh AI

- **Text-to-Audio**: Tạo âm thanh và nhạc từ mô tả
- Kiểm soát thời lượng và chất lượng âm thanh
- *(Sắp ra mắt)*

### 🔧 Quản Lý Backend

- **Local Backend**: Chạy ComfyUI trên máy tính của bạn
  - Nút Start/Stop backend tiện lợi
  - Tự động phát hiện cài đặt ComfyUI
  - Cấu hình đường dẫn tùy chỉnh
- **VPS Backend**: Kết nối đến server từ xa
- **Serverless Backend**: Sử dụng RunPod Serverless
- Chuyển đổi backend linh hoạt
- Kiểm tra trạng thái kết nối

### 📁 Quản Lý Dự Án

- Tổ chức outputs theo dự án
- Xem lịch sử tạo ảnh/video
- Tìm kiếm và lọc nhanh
- Xóa hàng loạt
- So sánh ảnh trước/sau (Photo Restore)

### 🎨 Giao Diện Thân Thiện

- Giao diện hiện đại, dễ sử dụng
- Hỗ trợ đa ngôn ngữ (Tiếng Việt, English)
- Dark mode mặc định
- Preview real-time khi tạo
- Zoom và pan ảnh trong modal preview

### 🔄 Tự Động Cập Nhật

- Kiểm tra cập nhật tự động
- Tải và cài đặt phiên bản mới
- Thông báo khi có bản cập nhật

---

## 🚀 Cài Đặt

### Bước 1: Tải Installer

1. Vào [Releases](https://github.com/tuyenhm68/KomfyStudio/releases/latest)
2. Tải file `KomfyStudio-Setup-x.x.x.exe`

### Bước 2: Cài Đặt

1. Chạy file installer đã tải
2. Làm theo hướng dẫn trên màn hình
3. Chọn thư mục cài đặt (mặc định: `C:\Program Files\KomfyStudio`)
4. Hoàn tất cài đặt

### Bước 3: Cấu Hình Backend (Tùy chọn)

#### Sử dụng Local Backend

1. Mở **Settings** → **Backend**
2. Chọn backend **Local**
3. Click **Browse** để chọn thư mục ComfyUI của bạn
   - Ví dụ: `E:\ComfyUI_windows_portable`
4. Click **Save**
5. Click **Start Backend** để khởi động ComfyUI
6. Đợi backend kết nối (trạng thái chuyển sang "Connected")

#### Sử dụng VPS Backend

1. Mở **Settings** → **Backend**
2. Click **Add Backend**
3. Chọn type: **VPS**
4. Nhập thông tin:
   - Name: Tên backend (ví dụ: "My VPS")
   - URL: Địa chỉ server (ví dụ: `http://192.168.1.100:8188`)
5. Click **Add**
6. Click **Test Connection** để kiểm tra

---

## 📖 Hướng Dẫn Sử Dụng

### Tạo Ảnh từ Text (T2I)

1. Chọn tab **Tools** → **Image**
2. Chọn app **Text to Image**
3. Nhập prompt mô tả ảnh bạn muốn
4. Chọn kích thước và số lượng ảnh
5. Click **Generate**
6. Xem kết quả trong panel **Preview**
7. Click **Download** để tải ảnh về

### Tạo Video từ Ảnh (I2V)

1. Chọn tab **Tools** → **Video**
2. Chọn app **Image to Video**
3. Upload ảnh nguồn
4. Nhập prompt mô tả chuyển động
5. Chọn thời lượng video
6. Click **Generate**
7. Xem video trong panel **Preview**

### Phục Hồi Ảnh Cũ (Photo Restore)

1. Chọn tab **Tools** → **Image**
2. Chọn app **Photo Restore**
3. Upload ảnh cần phục hồi
4. Nhập prompt mô tả (tùy chọn)
5. Click **Generate**
6. Xem kết quả so sánh trước/sau
7. Click **Compare** để xem chi tiết

### Quản Lý Dự Án

1. Chọn tab **Projects**
2. Click **New Project** để tạo dự án mới
3. Tất cả outputs sẽ được lưu vào dự án đang active
4. Click vào dự án để xem tất cả outputs
5. Sử dụng tìm kiếm để lọc outputs

---

## 🎯 Workflows Được Hỗ Trợ

KomfyStudio đi kèm với các workflows được tối ưu sẵn:

### Image Generation
- **FLUX.1 Dev** - Text to Image chất lượng cao
- **FLUX.1 Schnell** - Text to Image nhanh
- **Stable Diffusion XL** - Text to Image đa năng

### Video Generation
- **CogVideoX** - Text to Video & Image to Video
- **Mochi 1** - Video generation chất lượng cao

### Image Enhancement
- **Photo Restore** - Phục hồi ảnh cũ
- **Inpainting** - Chỉnh sửa ảnh thông minh

---

## 🔧 Cài Đặt Nâng Cao

### Quản Lý Models

1. Mở **Settings** → **Models Manager**
2. Xem danh sách models cần thiết cho mỗi workflow
3. Click **Install** để tải model
4. Theo dõi tiến trình tải xuống
5. Restart ComfyUI sau khi cài đặt

### Quản Lý Custom Nodes

1. Mở **Settings** → **Custom Nodes**
2. Xem danh sách custom nodes đã cài
3. Click **Install from URL** để cài node mới
4. Nhập GitHub URL hoặc ZIP URL
5. Restart ComfyUI sau khi cài đặt

### Cấu Hình API Keys

1. Mở **Settings** → **General**
2. Nhập Hugging Face token (nếu cần)
3. Token dùng để tải models có giới hạn truy cập

---

## ❓ Câu Hỏi Thường Gặp

### App không kết nối được với backend?

**Giải pháp**:
1. Kiểm tra ComfyUI đã được cài đặt chưa
2. Kiểm tra đường dẫn ComfyUI trong Settings đúng chưa
3. Click **Start Backend** để khởi động
4. Đợi 10-30 giây để backend khởi động
5. Click **Test Connection** để kiểm tra

### Tạo ảnh/video bị lỗi?

**Giải pháp**:
1. Kiểm tra backend đang kết nối (trạng thái "Connected")
2. Kiểm tra models cần thiết đã được cài đặt
3. Kiểm tra custom nodes đã được cài đặt
4. Xem logs trong console để biết lỗi cụ thể

### Làm sao để cập nhật app?

**Tự động**:
- App sẽ tự động kiểm tra cập nhật khi khởi động
- Thông báo sẽ hiện khi có phiên bản mới
- Click **Download Update** để tải và cài đặt

**Thủ công**:
1. Vào [Releases](https://github.com/tuyenhm68/KomfyStudio/releases/latest)
2. Tải installer mới nhất
3. Chạy installer để cập nhật

### Làm sao để gỡ cài đặt?

1. Vào **Settings** → **Apps & Features** (Windows)
2. Tìm "KomfyStudio"
3. Click **Uninstall**
4. Làm theo hướng dẫn

---

## 🐛 Báo Lỗi & Góp Ý

Nếu bạn gặp lỗi hoặc có góp ý:

1. Mở app → **Settings** → **Feedback**
2. Chọn loại feedback:
   - 🐛 Bug Report (Báo lỗi)
   - ✨ Feature Request (Yêu cầu tính năng)
   - 💡 Suggestion (Đề xuất)
3. Điền thông tin chi tiết
4. Đính kèm ảnh chụp màn hình (nếu có)
5. Click **Send Feedback**

---

## 📝 Ghi Chú

- **Source Code**: Mã nguồn được quản lý riêng trong private repository
- **Releases**: Chỉ phân phối compiled binaries tại đây
- **Auto-Update**: Được cấu hình để tự động cập nhật từ repo này

---

## 📄 Giấy Phép

Copyright © 2026 Hà Mạnh Tuyến

---

## 🔗 Liên Kết

- **Releases**: https://github.com/tuyenhm68/KomfyStudio/releases
- **YouTube**: [Kênh YouTube](https://youtube.com/@tuyenhm68)
- **Email**: tuyenhm68@gmail.com

---

**Phiên bản hiện tại**: 0.1.5  
**Cập nhật lần cuối**: 2026-01-21
