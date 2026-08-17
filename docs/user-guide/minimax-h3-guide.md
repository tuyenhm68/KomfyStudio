# 🎬 Hướng Dẫn MiniMax H3

> Tạo video AI chất lượng cao **chạy 100% trên máy tính** với MiniMax H3 — hỗ trợ video kèm âm thanh native, nhiều chế độ sáng tạo, tất cả trong một giao diện duy nhất.

## Mục Lục

- [Tổng Quan](#tổng-quan)
- [Yêu Cầu Hệ Thống](#yêu-cầu-hệ-thống)
- [Bắt Đầu Sử Dụng](#bắt-đầu-sử-dụng)
- [Các Chế Độ Tạo Video](#các-chế-độ-tạo-video)
  - [Text to Video (T2V)](#text-to-video-t2v)
  - [Image to Video (I2V)](#image-to-video-i2v)
  - [Reference to Video (R2V)](#reference-to-video-r2v)
  - [Audio Drive](#audio-drive)
  - [Keyframes](#keyframes)
  - [Extend](#extend)
  - [Chain](#chain)
  - [Music](#music)
- [Cài Đặt Nâng Cao (TUNE)](#cài-đặt-nâng-cao-tune)
- [LoRA](#lora)
- [Upscale Video](#upscale-video)
- [Xử Lý Sự Cố](#xử-lý-sự-cố)

---

## Tổng Quan

**MiniMax H3** là mô hình tạo video AI mã nguồn mở do MiniMax phát triển. KomfyStudio tích hợp MiniMax H3 với giao diện All-in-One, cho phép bạn tạo video chất lượng cao ngay trên máy tính cá nhân — không tốn chi phí API, không giới hạn số lượng.

| Chế độ | Chức năng | Input |
|--------|-----------|-------|
| **T2V** | Text to Video | Prompt văn bản |
| **I2V** | Image to Video | Ảnh đầu/cuối + prompt |
| **R2V** | Reference to Video | Ảnh tham chiếu + video tham chiếu + audio |
| **Audio Drive** | Lip-sync | Audio + ảnh người nói |
| **Keyframes** | Chuyển cảnh giữa keyframes | Ảnh tại các frame chỉ định |
| **Extend** | Kéo dài video | Video nguồn |
| **Chain** | Ghép nhiều clip liên tục | Danh sách prompt theo thứ tự |
| **Music** | Tạo nhạc AI | Caption/lyrics |

> 💡 **Đặc biệt**: Video tạo bởi MiniMax H3 **bao gồm cả âm thanh native** — không cần thêm bước tạo audio riêng.

---

## Yêu Cầu Hệ Thống

- **GPU**: NVIDIA GPU với **VRAM ≥ 24GB** (RTX 4090, RTX 3090, A5000, v.v.)
- **RAM**: Khuyến nghị 32GB+
- **Dung lượng**: ~30GB cho models (tự động tải khi chạy lần đầu)
- **Backend**: ComfyUI Local (phải cài ComfyUI Portable hoặc tương đương)

> ⚠️ **Lưu ý**: MiniMax H3 yêu cầu GPU mạnh. Nếu GPU dưới 24GB VRAM, bạn có thể sử dụng chế độ Turbo (ít steps hơn) hoặc giảm độ phân giải.

---

## Bắt Đầu Sử Dụng

### Bước 1: Mở MiniMax H3

1. Khởi động **KomfyStudio** và đảm bảo **ComfyUI backend** đang chạy
2. Chuyển sang tab **Apps** (biểu tượng lưới ở sidebar)
3. Chọn **MiniMax H3** trong danh sách apps (mục Video)

### Bước 2: Chọn chế độ

Thanh mode bar phía trên hiển thị 8 chế độ:

**T2V** · **I2V** · **R2V** · **Audio** · **Keys** · **Extend** · **Chain** · **Music**

Click vào chế độ muốn sử dụng.

### Bước 3: Nhập nội dung và Generate

1. Nhập **prompt** mô tả video (tiếng Anh cho kết quả tốt nhất)
2. Upload input files tùy chế độ (ảnh, video, audio)
3. Nhấn nút **Generate** ở thanh dưới

> 💡 **Tip**: Lần đầu chạy, KomfyStudio sẽ tự động tải các model cần thiết (~30GB). Quá trình này chỉ diễn ra một lần.

---

## Các Chế Độ Tạo Video

### Text to Video (T2V)

Tạo video hoàn toàn từ mô tả văn bản.

**Input**: Chỉ cần prompt

**Cách dùng**:
1. Chọn mode **T2V**
2. Nhập prompt mô tả cảnh video, ví dụ:
   ```
   A cat walking on the beach at sunset, waves crashing in the background, 
   cinematic lighting, 4K quality
   ```
3. Nhấn **Generate**

---

### Image to Video (I2V)

Chuyển ảnh tĩnh thành video động.

**Input**: Ảnh đầu (First Frame) và/hoặc ảnh cuối (Last Frame) + prompt

**Cách dùng**:
1. Chọn mode **I2V**
2. Upload **First Frame** (khung hình đầu tiên) — *tùy chọn*
3. Upload **Last Frame** (khung hình cuối cùng) — *tùy chọn*
4. Nhập prompt mô tả chuyển động mong muốn
5. Nhấn **Generate**

> 💡 **Tip**: Bạn có thể chỉ upload First Frame, chỉ Last Frame, hoặc cả hai. Khi upload cả hai, video sẽ morph từ ảnh đầu đến ảnh cuối.

---

### Reference to Video (R2V)

Sử dụng ảnh/video/audio tham chiếu để tạo video mới.

**Input**: Ảnh tham chiếu + Video tham chiếu + Audio tham chiếu (tất cả tùy chọn)

**Cách dùng**:
1. Chọn mode **R2V**
2. Upload **Reference Images** — ảnh nhân vật/identity
3. Upload **Reference Videos** — video motion reference
4. Upload **Reference Audios** — nhạc nền cho video
5. Nhập prompt
6. Nhấn **Generate**

**Ý nghĩa các tham chiếu**:
- **Image** = xác định nhân vật/identity
- **Video** = xác định chuyển động/motion
- **Audio** = nhạc nền cuối cùng

---

### Audio Drive

Lip-sync tự động — âm thanh điều khiển khẩu hình nhân vật.

**Input**: File audio (bắt buộc) + ảnh người nói (tùy chọn)

**Cách dùng**:
1. Chọn mode **Audio**
2. Upload **Audio Track** — file âm thanh/giọng nói *(bắt buộc)*
3. Upload **Speaker Photo** — ảnh người nói
4. Nhập prompt bổ sung (nếu cần)
5. Nhấn **Generate**

> 💡 **Tip**: Upload ảnh khuôn mặt rõ ràng để lip-sync chính xác hơn.

---

### Keyframes

Tạo video chuyển cảnh giữa các khung hình chỉ định.

**Input**: Ảnh tại các frame positions + prompt

**Cách dùng**:
1. Chọn mode **Keys**
2. Thêm keyframes bằng cách click **+ Thêm Keyframe**
3. Chỉ định **frame number** và upload **ảnh** cho mỗi keyframe
4. Nhập prompt mô tả chuyển cảnh
5. Nhấn **Generate**

Video sẽ morph qua các ảnh theo thứ tự frame đã chỉ định.

---

### Extend

Kéo dài video đã có thêm vài giây.

**Input**: Video nguồn (bắt buộc) + prompt

**Cách dùng**:
1. Chọn mode **Extend**
2. Upload **Video to Extend** — video cần kéo dài *(bắt buộc)*
3. Nhập prompt mô tả nội dung tiếp theo
4. Nhấn **Generate**

---

### Chain

Ghép nhiều clip liên tục thành video dài, giữ liên tục chuyển động.

**Input**: Danh sách prompts cho từng clip

**Cách dùng**:
1. Chọn mode **Chain**
2. Mỗi clip có một ô prompt riêng — nhập mô tả cho từng đoạn
3. Điều chỉnh **thời lượng** cho mỗi clip (tính bằng giây)
4. Thêm/xóa clips bằng nút **+** / **-**
5. Nhấn **Generate**

> 💡 **Tip**: Các clip sẽ được stitched end-to-end với motion-context continuity — chuyển cảnh mượt mà giữa các đoạn.

---

### Music

Tạo nhạc AI bằng MiniMax Music 3.

**Input**: Caption (mô tả) và/hoặc Lyrics (lời bài hát)

**Cách dùng**:
1. Chọn mode **Music**
2. Nhập **Caption** — mô tả phong cách nhạc (ví dụ: *"Upbeat electronic dance music with synth pads"*)
3. Nhập **Lyrics** — lời bài hát (nếu muốn có vocal)
4. Điều chỉnh **thời lượng** (mặc định 60 giây)
5. Nhấn **Generate**

---

## Cài Đặt Nâng Cao (TUNE)

Mở rộng phần **TUNE** để tùy chỉnh:

| Thông số | Mô tả | Mặc định |
|----------|--------|----------|
| **Resolution** | Độ phân giải video | 960×544 (0.5MP) |
| **Duration** | Thời lượng video (giây) | 5s |
| **Steps** | Số bước inference | 20 |
| **Quality** | Chế độ chất lượng (native / turbo) | native |
| **Sampler** | Thuật toán sampling | res_multistep |
| **Scheduler** | Lịch trình noise | simple |
| **Seed** | Giá trị seed (0 = random) | 0 (random) |
| **Batch** | Số video tạo cùng lúc | 1 |

**Các độ phân giải phổ biến**:
- `960×544` — 0.5MP Balanced (mặc định, nhanh)
- `1280×720` — 720p HD
- `1920×1080` — 1080p Full HD (cần nhiều VRAM hơn)

> ⚠️ **Lưu ý**: Tăng độ phân giải và steps sẽ cần nhiều VRAM và thời gian hơn.

---

## LoRA

Mở rộng phần **ADVANCED** để quản lý LoRA:

1. Click **+ Add LoRA**
2. Chọn file LoRA từ danh sách (phải đặt trong thư mục `models/loras/`)
3. Điều chỉnh **strength** (0.0 – 2.0)
4. Có thể thêm nhiều LoRA cùng lúc

Nếu dùng chế độ **Turbo**, bạn cần chọn thêm **Speed LoRA** tương ứng.

---

## Upscale Video

Sau khi tạo video xong, bạn có thể nâng cấp độ phân giải:

1. Chuyển sang mode **Upscale** (nếu có)
2. Video vừa tạo sẽ được tự động chọn làm input
3. Nhấn **Generate** để upscale

---

## Xử Lý Sự Cố

### ❌ "Out of memory" hoặc CUDA OOM

- Giảm **Resolution** xuống 960×544 hoặc thấp hơn
- Giảm **Steps** xuống 15-20
- Đóng các ứng dụng khác đang dùng GPU
- Sử dụng chế độ **Turbo** nếu có

### ❌ Model chưa tải

- Lần đầu chạy, models sẽ tự động tải (~30GB). Đảm bảo kết nối internet ổn định.
- Kiểm tra dung lượng ổ cứng còn trống

### ❌ Video tạo xong nhưng không hiển thị

- Kiểm tra console log (F12) để xem thông báo lỗi
- Đảm bảo ComfyUI backend vẫn đang chạy
- Thử tạo lại với prompt đơn giản hơn

### ❌ Chất lượng video thấp

- Tăng **Steps** lên 25-30
- Sử dụng chế độ **Native** thay vì Turbo
- Viết prompt chi tiết hơn bằng tiếng Anh

---

## Xem Thêm

- <a href="./google-flow-guide.md" target="_blank">Hướng dẫn Google Flow Mode</a>
- <a href="./app-builder-guide.md" target="_blank">Hướng dẫn App Builder</a>
- <a href="./app-store-guide.md" target="_blank">Hướng dẫn App Store</a>
