# 🎬 Hướng Dẫn Google Flow Mode

> Sử dụng **Komfy Bridge Extension** để tạo video AI (Veo 3.1) và ảnh AI (Nano Banana) trực tiếp qua Google Flow — miễn phí, không cần API key.

## Mục Lục

- [Tổng Quan](#tổng-quan)
- [Thiết Lập Ban Đầu](#thiết-lập-ban-đầu)
- [Sử Dụng Node Veo 3.1](#sử-dụng-node-veo-31)
  - [Chế Độ Ingredients](#chế-độ-ingredients-ảnh-tham-chiếu)
  - [Cài Đặt Nâng Cao](#cài-đặt-nâng-cao)
- [Sử Dụng Node Nano Banana](#sử-dụng-node-nano-banana)
- [Kiểm Tra Trạng Thái Kết Nối](#kiểm-tra-trạng-thái-kết-nối)
- [Xử Lý Sự Cố](#xử-lý-sự-cố)

---

## Tổng Quan

**Google Flow Mode** cho phép Komfy Studio điều khiển Google Flow thông qua Komfy Bridge Extension. Thay vì gọi API trực tiếp (cần API key và tốn credit), hệ thống sẽ:

1. Tự động mở/điều hướng tab Google Flow trong Chrome
2. Nhập prompt và ảnh tham chiếu tự động
3. Kích hoạt tạo video/ảnh
4. Tải kết quả về và hiển thị trong node

| Node | Chức năng | Yêu cầu |
|------|-----------|---------|
| **Veo 3.1** | Tạo video AI (Text-to-Video, Image-to-Video) | Google account có quyền Veo |
| **Nano Banana 2** | Tạo ảnh AI | Google account có quyền Flow |
| **Nano Banana Pro** | Tạo ảnh chất lượng cao | Google account có quyền Flow |

---

## Thiết Lập Ban Đầu

### Bước 1: Cài Komfy Bridge Extension

1. Mở **Komfy Studio** → **Settings** → tab **Extension**
2. Nhấn **Install Now** nếu chưa cài
3. Copy đường dẫn extension hiển thị
4. Mở Chrome → `chrome://extensions` → bật **Developer mode** → **Load unpacked** → dán đường dẫn
5. Extension **Komfy Bridge** xuất hiện trong Chrome toolbar

### Bước 2: Kết Nối Google Flow

1. Đảm bảo **Komfy Studio đang chạy**
2. Trong Chrome, mở <a href="https://labs.google/fx/tools/flow" target="_blank">labs.google/fx/tools/flow</a>
3. Đăng nhập Google account có quyền dùng Veo / Flow
4. Đợi **10–15 giây** để extension đồng bộ

### Bước 3: Kiểm Tra Kết Nối

Click vào icon **Komfy Bridge** trong Chrome toolbar — popup hiển thị:

```
Komfy Studio    ● Connected
Google Session  ● Active
Project         af9ec403-aa36-...
Last sync       2s ago
```

Nếu thấy **Connected** + **Active** → sẵn sàng sử dụng ✅

---

## Sử Dụng Node Veo 3.1

### Bật Google Flow Mode

1. Mở **Workflows** → kéo node **Veo 3.1** vào canvas
2. Click icon ⚙️ (Settings) trên node
3. Bật toggle **Use Google Flow** → icon 🔌 xuất hiện trên header node
4. Kết nối **Prompt** từ Text node

> ⚠️ **Lưu ý:** Khi bật Google Flow, các setting **Resolution** và **Duration** ẩn đi (chỉ dùng cho API mode). Thay vào đó xuất hiện **Video Type** và **Orientation**.

### Chế Độ Ingredients (Ảnh Tham Chiếu)

Chế độ mặc định — phù hợp để tạo video với phong cách/đối tượng từ ảnh tham chiếu.

**Cách dùng:**

```
[Text Node]  ──────────►  Prompt *
[Image Node] ──────────►  Image 1
[Image Node] ──────────►  Connect for more slots (up to 4)
                                ↓
                          [Veo 3.1 Node]  ──►  Video
```

- **Image 1**: Ảnh tham chiếu đầu tiên (phong cách, nhân vật, ...)
- **Image 2–4**: Có thể kết nối thêm tối đa 4 ảnh tham chiếu
- Slot trống mới tự động hiện ra khi bạn kết nối slot trước

**Ví dụ workflow:**

```
Text (prompt) ──► Veo 3.1 (Ingredients) ──► Video Output
Image (product)──►
Image (style)──►
```

### Cài Đặt Nâng Cao

Mở Settings (⚙️) trên node Veo 3.1:

| Setting | Giá trị | Mô tả |
|---------|---------|--------|
| **Use Google Flow** | On/Off | Bật/tắt Flow mode |
| **Veo Model** | Veo 3.1 - Fast / Quality | Fast = nhanh hơn, Quality = chất lượng cao hơn |
| **Video Type** | Ingredients | Chế độ ảnh tham chiếu (hiện tại) |
| **Orientation** | Landscape / Portrait | Tỉ lệ khung hình 16:9 / 9:16 |

---

## Sử Dụng Node Nano Banana

### Nano Banana 2 / Nano Banana Pro

Tương tự Veo 3.1 nhưng tạo **ảnh** thay vì video.

**Setup:**

1. Kéo node **Nano Banana 2** hoặc **Nano Banana Pro** vào canvas
2. Click ⚙️ → bật **Use Google Flow**
3. Kết nối Prompt và (tùy chọn) ảnh tham chiếu

**Cấu trúc input:**

```
[Text Node]  ──────────►  Prompt *
[Image Node] ──────────►  Image 1     (tùy chọn)
[Image Node] ──────────►  Image 2     (tùy chọn)
                                ↓
                     [Nano Banana] ──►  Image Output
```

**Settings:**

| Setting | Giá trị | Mô tả |
|---------|---------|--------|
| **Use Google Flow** | On/Off | Bật Flow mode |
| **Orientation** | Landscape / Portrait | Tỉ lệ ảnh |

---

## Kiểm Tra Trạng Thái Kết Nối

### Trên Node

Khi **Use Google Flow = On**, header node hiển thị icon 🔌 màu xanh lá. Hover vào icon để xem chi tiết:

```
🔌 Google Flow active
Model: Veo 3.1 - Fast
Type: Ingredients
Orientation: Landscape
```

### Trong Extension Popup

Click icon Komfy Bridge trong Chrome toolbar:

| Trạng thái | Ý nghĩa |
|-----------|---------|
| `● Connected` | Komfy Studio đang kết nối với extension |
| `● Active` | Google session đang hoạt động (có token) |
| `Project: xxx` | ID project đang sử dụng trên Google Flow |
| `Last sync: Xs ago` | Thời gian đồng bộ gần nhất |

### Trong Settings Komfy Studio

**Settings** → **Extension** → xem trạng thái chi tiết của từng profile Chrome đang kết nối.

---

## Xử Lý Sự Cố

### ❌ "Komfy Bridge extension is not connected"

Node báo lỗi này khi extension chưa kết nối hoặc mới bị ngắt.

**Giải pháp:**
1. Mở Chrome và đảm bảo tab Google Flow đang mở
2. Đợi 10–30 giây (extension tự động kết nối lại)
3. Nhấn **Sync** trong popup extension
4. Nếu vẫn lỗi: reload extension trong `chrome://extensions`

> 💡 Lỗi này thường xảy ra khi Chrome không hoạt động trong một thời gian. Chỉ cần chạy lại node là đủ vì hệ thống tự động chờ extension kết nối lại (tối đa 16 giây).

### ❌ Extension tạo project mới thay vì dùng project cũ

Extension tự động tạo project **"komfy-studio"** trên Google Flow nếu chưa tìm thấy. Nếu thấy project mới được tạo mỗi lần:

1. Xóa project cũ bị lỗi trên Google Flow
2. Reload extension → chạy lại node
3. Extension sẽ tìm project "komfy-studio" hiện có hoặc tạo mới đúng 1 lần

### ❌ Video/ảnh của node này hiển thị kết quả của node khác

Hiện tượng này đã được fix trong **v2.0.79+** bằng session token isolation.

Nếu vẫn gặp:
1. Chạy từng node một thay vì song song
2. Đảm bảo đang dùng extension **v2.0.79** trở lên (xem trong popup)

### ❌ Kết quả trả về chậm hoặc không có

Google Flow có thể mất **1–5 phút** để tạo video tùy độ phức tạp:

- **Ingredients + không có ảnh**: ~1–2 phút
- **Ingredients + có ảnh tham chiếu**: ~2–4 phút
- **Veo 3.1 Quality**: ~3–5 phút

Theo dõi thanh tiến trình trên node để biết trạng thái.

---

## Xem Thêm

- [Hướng dẫn Komfy Bridge Extension](./chrome-extension-guide.md)
- [Hướng dẫn App Builder](./app-builder-guide.md)
- <a href="https://labs.google/fx/tools/flow" target="_blank">Google Flow (labs.google)</a>
