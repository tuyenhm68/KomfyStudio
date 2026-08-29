# 🎨 KomfyStudio

![KomfyStudio](assets/images/banner/komfy-studio.png)

**Ứng dụng tạo ảnh & video AI được hỗ trợ bởi ComfyUI**

<a href="https://github.com/tuyenhm68/KomfyStudio/releases" target="_blank"><img src="https://img.shields.io/github/v/release/tuyenhm68/KomfyStudio" alt="Phiên bản"></a>
<a href="https://github.com/tuyenhm68/KomfyStudio/releases" target="_blank"><img src="https://img.shields.io/github/downloads/tuyenhm68/KomfyStudio/total" alt="Tải xuống"></a>

🇻🇳 Tiếng Việt | <a href="./README.md" target="_blank">🇬🇧 English</a>

---

## 📥 Tải Xuống

**<a href="https://github.com/tuyenhm68/KomfyStudio/releases/latest" target="_blank">⬇️ Tải phiên bản mới nhất</a>**

**<a href="https://drive.google.com/file/d/1e105-dN0neUjymGfpqS5wf3Om-yFASy5/view?usp=sharing" target="_blank">⬇️ Comfy Portable dành cho KomfyStudio</a>**

**<a href="https://modal.com/notebooks/tuyenhm68/main/nb-DbCzbt5HUwPCz49YjN1W94" target="_blank">⬇️ Comfy Modal Notebook dành cho KomfyStudio</a>**

**<a href="https://colab.research.google.com/drive/1qkMhPoRUL9zsoj-ogX-gx6Hw-9zi2Hgx?usp=sharing" target="_blank">⬇️ Comfy Colab Notebook dành cho KomfyStudio</a>**

**<a href="https://console.runpod.io/deploy?template=c2clojkox5&ref=rpuub8vb" target="_blank">⬇️ Comfy Runpod serverless template dành cho KomfyStudio</a>**

### Yêu Cầu Hệ Thống

- **Hệ điều hành**: Windows 10/11
- **RAM**: Tối thiểu 12GB (Khuyến nghị 32GB+)
- **GPU**: NVIDIA GPU với CUDA support từ 12GB VRAM trở lên (Khuyến nghị 24GB+ VRAM)
  > ⚠️ **Lưu ý:** GPU NVIDIA chỉ yêu cầu khi sử dụng backend **ComfyUI** (Local/VPS/Serverless). Nếu bạn chỉ sử dụng **Workflow Builder** để tạo ảnh/video thông qua **Google Gemini API** hoặc **Google Flows** thì **không cần GPU NVIDIA** — có thể chạy trên mọi máy tính.
- **Dung lượng ổ cứng**: 
  - 200MB dung lượng trống để cài app
  - 100GB+ dung lượng trống để cài ComfyUI (Khuyến nghị ổ SSD 500GB trở lên) — *chỉ cần khi sử dụng backend ComfyUI*

### Hướng Dẫn
**<a href="https://www.youtube.com/playlist?list=PL9QrPbhu7dy_iW_QMaWAlyWKEoXncJnYp" target="_blank">Video Hướng dẫn cài đặt và sử dụng</a>**
---

## ✨ Tính Năng Chính

### 🖼️ Tạo Ảnh AI

- **Text-to-Image (T2I)**: Tạo ảnh từ mô tả văn bản
- **Image-to-Image (I2I)**: Chỉnh sửa và biến đổi ảnh
- **Photo Restore**: Phục hồi và nâng cao chất lượng ảnh cũ
- **Clothes Transfer**: Chuyển quần áo giữa các ảnh
  - Trích xuất quần áo từ ảnh tham chiếu
  - Chuyển quần áo sang nhân vật khác
  - Hỗ trợ 2 chế độ: Extract + Transfer hoặc Transfer trực tiếp
- **Multi-Angle Camera**: Tạo ảnh từ nhiều góc nhìn 3D
  - Điều khiển góc camera bằng giao diện 3D trực quan
  - Xem trước góc nhìn real-time với mô hình 3D
  - Tự động tạo prompt dựa trên góc camera
  - Hỗ trợ model Flux2-Klein 9B
- **Style Changing**: Chuyển đổi phong cách ảnh
  - Nhiều preset phong cách: Anime, Sketch, Lego, Ghibli, v.v.
  - Tùy chỉnh prompt để tạo phong cách riêng
- Hỗ trợ nhiều định dạng: Landscape, Square, Portrait

### 🎬 Tạo Video AI

- **Text-to-Video (T2V)**: Tạo video từ mô tả văn bản
- **Image-to-Video (I2V)**: Chuyển ảnh tĩnh thành video động
- **MiniMax H3** ⭐ — Tạo video AI All-in-One chạy 100% local (GPU ≥ 24GB VRAM)
  - **T2V**: Text to Video (kèm âm thanh native)
  - **I2V**: Image to Video — animate từ ảnh đầu/cuối
  - **R2V**: Reference to Video — ảnh = identity, video = motion, audio = soundtrack
  - **Audio Drive**: Lip-sync tự động từ audio
  - **Keyframes**: Chuyển cảnh giữa các khung hình chỉ định
  - **Extend**: Kéo dài video thêm vài giây
  - **Chain**: Ghép nhiều clip liên tục giữ motion continuity
  - **Music**: Tạo nhạc AI từ caption/lyrics (MiniMax Music 3)
  - **Upscale**: Nâng cấp độ phân giải video
- Hỗ trợ nhiều tỷ lệ khung hình

**<a href="./docs/user-guide/minimax-h3-guide.md" target="_blank">📖 Xem hướng dẫn chi tiết MiniMax H3</a>**

### 💬 Chat

- **Mô tả là chạy**: Gõ thứ bạn muốn tạo — không cần mở app, không cần dựng workflow
- **Tự nhận diện đầu vào**: File đính kèm quyết định chế độ (1 ảnh → I2V, 1 audio → Audio Drive, 1 video → Extend)
- **Đổi model tại chỗ**: MiniMax H3, LTX 2.5, WAN 2.2 cho video, MiniMax Music 3 cho nhạc, cùng các workflow ảnh đã cài
- **Xem trước kế hoạch**: Một dòng tóm tắt nói đúng thứ sắp chạy trước khi bạn gửi
- **Thư viện dự án**: Mọi kết quả từ Chat và từ app nằm chung một chỗ, nhóm theo ngày, lọc được
- **Dùng lại kết quả**: Đưa kết quả cũ làm đầu vào cho lượt sau, hoặc chạy lại prompt đó thành biến thể
- **Job chạy nền**: Đổi hội thoại không làm huỷ lượt đang chạy

**<a href="./docs/user-guide/chat-guide.md" target="_blank">📖 Xem hướng dẫn Chat chi tiết</a>**

### 🧩 Skill

- **Gõ `/` ở bất kỳ đâu**: Skill dùng được trong mọi ô prompt của mọi app, không riêng gì Chat
- **Ba loại**: Template (chạy offline), LLM (viết prompt giúp bạn), Nhiều bước (hỏi, sinh ảnh, chờ duyệt rồi sinh video)
- **Tìm không dấu**: Gõ `giay` vẫn ra `giấy`
- **Không mất khi tắt app**: Lượt skill đang chờ bạn trả lời được khôi phục nguyên vẹn
- **Skill Hub**: Cài từ kho cộng đồng, hoặc đăng skill của bạn lên
- **Nhập / xuất**: Đóng gói skill thành file để chia sẻ hoặc sao lưu

**<a href="./docs/user-guide/skill-guide.md" target="_blank">📖 Xem hướng dẫn Skill chi tiết</a>**

### 🎵 Tạo Âm Thanh AI

- **Text-to-Audio**: Tạo âm thanh và nhạc từ mô tả
- **Text-to-Music**: Tạo nhạc từ mô tả

### 🏪 App Store

- **Kho ứng dụng cộng đồng**: Tải và cài đặt apps do cộng đồng chia sẻ
- **Cài đặt một chạm**: Tự động tải và cài đặt models, custom nodes
- **Quản lý phiên bản**: Kiểm tra và cập nhật apps đã cài đặt
- **Đánh giá và nhận xét**: Xem đánh giá từ người dùng khác
- **Tìm kiếm và lọc**: Dễ dàng tìm apps theo danh mục, tác giả
- **Chi tiết đầy đủ**: Xem thông tin models, nodes, dependencies trước khi cài

**<a href="./docs/user-guide/app-store-guide.md" target="_blank">📖 Xem hướng dẫn chi tiết App Store</a>**

### 🛠️ App Builder

- **Tạo app không cần code**: Chuyển ComfyUI workflow thành app hoàn chỉnh
- **Wizard 5 bước**: Hướng dẫn từng bước tạo app
  1. Upload workflow JSON
  2. Cấu hình metadata (tên, mô tả, icon, category)
  3. Thiết kế giao diện với drag-and-drop
  4. Liên kết controls với workflow parameters
  5. Xem trước và xuất bản
- **Tự động phát hiện**: Phân tích workflow, tìm models và custom nodes cần thiết
- **Thiết kế UI linh hoạt**: Kéo thả controls, tùy chỉnh layout
- **Chia sẻ lên Store**: Xuất bản app để cộng đồng sử dụng
- **Quản lý phiên bản**: Cập nhật và duy trì apps của bạn

**<a href="./docs/user-guide/app-builder-guide.md" target="_blank">📖 Xem hướng dẫn chi tiết App Builder</a>**

### 🔗 Workflow Builder

- **Trình tạo workflow trực quan**: Xây dựng pipeline AI bằng kéo thả node
- **Hỗ trợ đa dạng node**: Text, Image, Video, Audio Input/Output & AI Model nodes
- **Kết nối thông minh**: Chỉ cho phép kết nối các cổng dữ liệu tương thích
- **Mẫu có sẵn**: Bắt đầu nhanh với các template workflow phổ biến
- **Mẫu cộng đồng**: Khám phá và sử dụng workflow được chia sẻ bởi cộng đồng
  - Mở workflow cộng đồng ở chế độ **Chỉ xem (Read-Only)**
  - Nhấn **Tạo bản sao** để tạo phiên bản có thể chỉnh sửa
- **Xuất bản và chia sẻ**: Xuất bản workflow lên cộng đồng
  - Cập nhật workflow đã xuất bản
  - Ngừng xuất bản khi cần
- **Quản lý tài sản**: Upload và quản lý hình ảnh, tệp tin sử dụng trong workflow
- **Chạy trực tiếp**: Thực thi workflow ngay trên ứng dụng với Google Gemini API
- **Theo dõi chi phí**: Hiển thị chi phí phiên làm việc realtime

### 🔧 Quản Lý Backend

- **Local Backend**: Chạy ComfyUI trên máy tính của bạn
  - Nút Start/Stop backend tiện lợi
  - Cấu hình đường dẫn tùy chỉnh
- **VPS Backend**: Kết nối đến server từ xa sử dụng: VPS, Colab, Runpod
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
- Hỗ trợ Tiếng Việt, English
- Preview real-time khi tạo
- Zoom và pan ảnh trong modal preview

### 🔄 Tự Động Cập Nhật

- Kiểm tra cập nhật tự động
- Tải và cài đặt phiên bản mới
- Thông báo khi có bản cập nhật

---

## 🔌 Komfy Bridge — Chrome Extension

> Extension kết nối Komfy Studio với **Google Flow**, cho phép tạo video AI bằng mô hình **Veo 3.1** của Google trực tiếp trong Workflow Builder — không cần API key.

### Cài đặt

Extension được cài **tự động** từ phiên bản v0.1.39 trở lên:

1. Mở **Settings** → tab **Extension** → nhấn **Install Now** (hoặc tự cài khi khởi động)
2. Copy đường dẫn extension hiển thị
3. Mở Chrome → `chrome://extensions` → bật **Developer mode** → **Load unpacked** → dán đường dẫn

### Cách dùng

1. Mở **Komfy Studio** (chạy trước) + mở Chrome → vào <a href="https://labs.google/fx/tools/flow" target="_blank">Google Flow</a> → đăng nhập
2. Trạng thái **Connected** xuất hiện trong Settings → Extension
3. Trong Workflow Builder, thêm node **Veo 3.1** → bật **"Use Google Flow"** → nhấn Run

**<a href="./docs/user-guide/chrome-extension-guide.md" target="_blank">📖 Xem hướng dẫn đầy đủ</a>** | **<a href="https://github.com/tuyenhm68/komfy-extension/releases" target="_blank">📦 GitHub Releases</a>**


---

## 🚀 Cài Đặt

### Bước 1: Tải Installer

1. Vào <a href="https://github.com/tuyenhm68/KomfyStudio/releases/latest" target="_blank">Releases</a>, tải file `KomfyStudio-Setup-x.x.x.exe`
2. Tải ComfyUI Portable <a href="https://bit.ly/4rdBPOM" target="_blank">(Theo link)</a>

### Bước 2: Cài Đặt

1. Chạy file installer đã tải
2. Làm theo hướng dẫn trên màn hình
3. Hoàn tất cài đặt

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

### Chuyển Quần Áo (Clothes Transfer)

**Chế độ 1: Trích xuất + Chuyển (Extract + Transfer)**

1. Chọn tab **Apps** → **Image**
2. Chọn app **Clothes Transfer**
3. Upload **ảnh nhân vật chính** (Input 1) - người sẽ mặc quần áo mới
4. Upload **ảnh tham chiếu** (Input 2) - người đang mặc quần áo bạn muốn
5. Click **Generate**
6. Hệ thống sẽ tự động:
   - Trích xuất quần áo từ ảnh tham chiếu
   - Chuyển quần áo sang nhân vật chính
7. Xem kết quả trong panel **Preview**

**Chế độ 2: Chuyển trực tiếp (Direct Transfer)**

1. Chọn tab **Apps** → **Image**
2. Chọn app **Clothes Transfer**
3. Upload **ảnh nhân vật chính** (Input 1)
4. Upload **ảnh quần áo đã trích xuất** (Input 3) - chỉ có quần áo, không có người
5. Click **Generate**
6. Xem kết quả trong panel **Preview**

**💡 Lưu ý:**
- Input 2 (ảnh tham chiếu) và Input 3 (quần áo đã trích xuất) **loại trừ lẫn nhau**
- Chỉ upload 1 trong 2: hoặc Input 2 hoặc Input 3
- Kết quả tự động lưu vào dự án đang active
- App tự động lưu cache để bạn có thể quay lại tiếp tục
- Hỗ trợ định dạng: PNG, JPG, WebP

### Tạo Ảnh Đa Góc Nhìn (Multi-Angle Camera)

1. Chọn tab **Apps** → **Image**
2. Chọn app **Multi-Angle Camera**
3. Upload **ảnh nhân vật** - ảnh gốc bạn muốn tạo lại từ góc khác
4. Sử dụng **giao diện 3D** để điều chỉnh góc camera:
   - **Kéo chuột trái**: Xoay camera quanh đối tượng
   - **Cuộn chuột**: Zoom in/out
   - **Nút Reset**: Đặt lại góc camera về mặc định
5. Xem **thông tin góc camera** real-time:
   - Azimuth (góc ngang): -180° đến 180°
   - Polar (góc dọc): 0° đến 180°
   - Zoom: Khoảng cách camera
6. Prompt sẽ **tự động cập nhật** dựa trên góc camera bạn chọn
7. Click **Generate** để tạo ảnh
8. Xem kết quả trong panel **Preview**

**💡 Lưu ý:**
- Model Flux2-Klein 9B cần ~12GB VRAM
- Góc camera càng khác biệt, kết quả càng sáng tạo
- Có thể chỉnh sửa prompt tự động để tinh chỉnh kết quả
- Kết quả tự động lưu vào dự án đang active

### Sử Dụng Workflow Builder

#### Tạo Workflow Mới

1. Chọn tab **Workflows** trên thanh điều hướng chính
2. Click **+ New Workflow** để tạo workflow mới
3. Sử dụng **Side Toolbar** bên trái hoặc nhấn **Tab** để mở bảng chọn node
4. Kéo thả các node vào canvas:
   - **Input nodes**: Text Input, Image Upload, Audio Input
   - **AI Model nodes**: Gemini Nano Banana (ảnh), Veo 3.1 (video)
   - **Output nodes**: Text Output, Image Output, Video Output
5. Kết nối các node bằng cách kéo từ cổng output sang cổng input
6. Click **Run** để thực thi workflow

#### Sử Dụng Mẫu Cộng Đồng

1. Vào tab **Workflows** → chọn tab **Mẫu cộng đồng**
2. Duyệt danh sách workflow được chia sẻ
3. Click vào workflow để mở ở chế độ **Chỉ xem (Read-Only)**
4. Xem cấu trúc node và kết nối
5. Click **Tạo bản sao** (nút xanh lá trên thanh công cụ) để tạo phiên bản chỉnh sửa được
6. Chỉnh sửa và lưu bản sao theo ý muốn

#### Xuất Bản Workflow

1. Mở workflow đã lưu
2. Click nút **Publish** (hoặc **Update** nếu đã xuất bản)
3. Điền thông tin: tên, mô tả, danh mục, ảnh bìa
4. Click **Xuất bản**
5. Để ngừng xuất bản: click menu **⋯** → **Ngừng xuất bản**

**💡 Lưu ý:**
- Workflow cộng đồng mở ở chế độ chỉ xem, không thể chỉnh sửa trực tiếp
- Cần tạo bản sao trước khi chỉnh sửa hoặc chạy workflow cộng đồng
- Chi phí API được hiển thị realtime trên thanh công cụ
- Workflow được lưu tự động vào cơ sở dữ liệu local

### Quản Lý Dự Án

1. Chọn tab **Projects**
2. Click **New Project** để tạo dự án mới
3. Tất cả outputs sẽ được lưu vào dự án đang active
4. Click vào dự án để xem tất cả outputs
5. Sử dụng tìm kiếm để lọc outputs

---

## 🔧 Cài Đặt Nâng Cao

### Cấu Hình API Keys

1. Mở **Settings** → **General**
2. Nhập Hugging Face token để phục vụ tải các models có giới hạn truy cập

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
1. Vào <a href="https://github.com/tuyenhm68/KomfyStudio/releases/latest" target="_blank">Releases</a>
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

## 📄 Giấy Phép

Copyright © 2026 Hà Mạnh Tuyến

---

## 🔗 Liên Kết
- **YouTube**: <a href="https://www.youtube.com/channel/UCd3BHy2KUjBl1Z2cnrdLNFg" target="_blank">Kênh YouTube</a>
---