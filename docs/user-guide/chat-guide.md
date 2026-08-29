# 💬 Hướng Dẫn Chat

> Mô tả thứ bạn muốn tạo, KomfyStudio tự chọn model và chế độ chạy. Không cần mở app, không cần dựng workflow.

## Mục Lục

- [Tổng Quan](#tổng-quan)
- [Yêu Cầu](#yêu-cầu)
- [Bắt Đầu Sử Dụng](#bắt-đầu-sử-dụng)
- [Bố Cục Màn Hình](#bố-cục-màn-hình)
- [Chọn Loại Đầu Ra Và Model](#chọn-loại-đầu-ra-và-model)
- [Đính Kèm File](#đính-kèm-file)
- [Dòng Tóm Tắt Kế Hoạch](#dòng-tóm-tắt-kế-hoạch)
- [Thư Viện Dự Án](#thư-viện-dự-án)
- [Hội Thoại](#hội-thoại)
- [Dùng Skill Trong Chat](#dùng-skill-trong-chat)
- [Xử Lý Sự Cố](#xử-lý-sự-cố)

---

## Tổng Quan

**Chat** là cách dùng KomfyStudio không qua app. Bạn gõ mô tả, đính kèm ảnh/video/audio nếu có, KomfyStudio đọc tổ hợp đầu vào đó và tự dựng lệnh chạy: chọn model, chọn chế độ, gán từng file vào đúng vị trí.

| Bạn làm | KomfyStudio làm |
|---------|-----------------|
| Gõ mô tả, không đính gì | Chạy Text to Video |
| Đính 1 ảnh | Chuyển sang Image to Video, ảnh thành khung đầu |
| Đính 1 audio | Chuyển sang Audio Drive (lip-sync) |
| Đính 1 video | Chuyển sang Extend Video |
| Đổi model giữa chừng | Tính lại kế hoạch, báo nếu model mới không nhận được file đang đính |

Việc định tuyến này chạy bằng **luật thuần** — cùng đầu vào luôn cho cùng kết quả, không gọi mạng, không đoán.

> 💡 **Quan trọng**: Chat **không đọc nội dung câu bạn gõ** để quyết định tạo ảnh, video hay nhạc. Loại đầu ra chọn bằng tay ở tab trong bảng model — xem [Chọn Loại Đầu Ra Và Model](#chọn-loại-đầu-ra-và-model).

---

## Yêu Cầu

- **Backend đang chạy**: ComfyUI Local hoặc backend bạn đang dùng
- **Đã cài ít nhất một model** cho loại đầu ra muốn tạo (video / ảnh / nhạc)

Chat dùng lại chính các model và workflow bạn đã cài cho các app — **không phải tải thêm gì**. Yêu cầu phần cứng phụ thuộc model bạn chọn để chạy.

> ⚠️ **Lưu ý**: Chat chạy bằng bộ tham số mặc định cân bằng riêng, **không đọc thiết lập trong app**. Bạn chỉnh gì trong app MiniMax H3 thì chat vẫn giữ mặc định của nó.

---

## Bắt Đầu Sử Dụng

### Bước 1: Mở Chat

1. Khởi động **KomfyStudio**, đảm bảo backend đang chạy
2. Chọn **Chat** ở sidebar (biểu tượng bong bóng hội thoại)

### Bước 2: Chọn loại đầu ra và model

Nhấn chip model ở đáy ô soạn (mặc định hiển thị `MiniMax H3`). Bảng hiện ra có ba tab ở trên cùng: **Video** · **Ảnh** · **Nhạc**.

1. Chọn tab đúng loại bạn muốn tạo
2. Chọn model trong danh sách bên dưới

### Bước 3: Gõ mô tả và gửi

1. Nhập mô tả vào ô soạn
2. Đính kèm file nếu cần (biểu tượng ghim giấy)
3. Kiểm tra **dòng tóm tắt** ngay trên hàng nút — nó nói đúng thứ sắp chạy
4. Nhấn nút gửi (mũi tên lên) hoặc `Enter`

> 💡 **Tip**: Dòng tóm tắt dạng `MiniMax H3 · T2V · 960×544 · 5s · native` là thứ đáng nhìn nhất trong cả màn hình. Nếu nó không nói đúng ý bạn, đừng gửi — sửa trước.

---

## Bố Cục Màn Hình

Màn Chat có hai vùng chính:

- **Cột chat** — hội thoại đang mở và ô soạn tin
- **Thư viện** — toàn bộ kết quả của dự án đang mở

Nhấn nút bố cục ở góc phải thanh lọc để đổi giữa bốn kiểu:

| Kiểu | Mô tả |
|------|-------|
| **Chat bên trái** | Mặc định — chat trái, thư viện phải |
| **Chat bên phải** | Đảo hai cột |
| **Chỉ chat** | Ẩn thư viện, chat chiếm hết bề ngang |
| **Chỉ thư viện** | Ẩn chat, xem kết quả toàn màn hình |

> 💡 **Phím tắt**: `Ctrl` + `\` đảo nhanh giữa chat trái và chat phải.

Kéo đường viền giữa hai cột để chỉnh bề rộng. Lựa chọn bố cục và bề rộng được nhớ lại cho lần sau.

---

## Chọn Loại Đầu Ra Và Model

Đây là chỗ hay nhầm nhất, nên nói kỹ.

**Loại đầu ra mặc định là Video.** Gõ "tạo một bản nhạc lofi buồn" mà không đổi tab thì KomfyStudio vẫn chạy Text to Video — vì nó định tuyến theo tab và theo file đính kèm, không theo nghĩa của câu chữ.

### Cách tạo nhạc

1. Nhấn chip model ở đáy ô soạn
2. Chọn tab **Nhạc**
3. Chọn **MiniMax Music 3**
4. Gõ mô tả thể loại/không khí rồi gửi

Dòng tóm tắt lúc này phải hiện `MiniMax Music 3 · Music · 60s`. Nếu vẫn thấy `T2V` nghĩa là tab chưa đổi.

### Thêm lời bài hát

Viết mô tả trước, rồi xuống dòng bắt đầu bằng `lyrics:` hoặc `lời:`:

```
nhạc lofi buồn, piano nhẹ, tiếng mưa nền
lyrics:
Đêm nay phố vắng
Chỉ còn mình tôi với cơn mưa
```

Phần trước `lyrics:` thành mô tả thể loại, phần sau thành lời hát. Thời lượng nhạc chỉnh được trong khoảng **10–300 giây**, mặc định 60.

### Model nhớ theo từng loại

Mỗi loại đầu ra nhớ model riêng: chọn LTX 2.5 cho video không ảnh hưởng model ảnh hay model nhạc. Lựa chọn được lưu theo backend đang dùng, vì kho model của ComfyUI local và của backend khác không giống nhau.

> ⚠️ **Lưu ý**: Loại đầu ra **không được lưu lại** giữa các lần mở app. Khởi động lại KomfyStudio thì chat quay về Video, kể cả khi lần trước bạn đang làm nhạc.

---

## Đính Kèm File

Nhấn biểu tượng **ghim giấy** ở đáy ô soạn, chọn ảnh, video hoặc audio. Có thể chọn nhiều file một lúc.

Chế độ chạy được suy ra từ **số lượng và loại file**, không phải từ câu chữ. Với MiniMax H3:

| Đính kèm | Chế độ được chọn |
|----------|------------------|
| Không có gì | **T2V** — Text to Video |
| 1 ảnh | **I2V** — Image to Video (ảnh thành khung đầu) |
| 2 ảnh | **I2V** — khung đầu + khung cuối |
| 3 ảnh trở lên | **R2V** — Reference to Video |
| 1 video | **Extend** — kéo dài video |
| 1 ảnh + 1 video | **R2V** — ảnh làm nhân vật, video làm chuyển động |
| 1 audio | **Audio Drive** — lip-sync |
| 1 audio + 1 ảnh | **Audio Drive** — audio điều khiển khẩu hình ảnh nhân vật |

Model khác có bộ chế độ khác, nên bảng này chỉ đúng với MiniMax H3. Nguyên tắc thì giống nhau: mỗi chế độ khai báo nhận được bao nhiêu ảnh/video/audio, hệ thống chọn chế độ khớp nhất với tổ hợp bạn đính vào.

Mỗi file đính kèm hiện thành một chip trong ô soạn, có nhãn cho biết nó đang đóng vai gì (`Khung đầu`, `Ảnh tham chiếu`, `Bản audio`…).

---

## Dòng Tóm Tắt Kế Hoạch

Ngay trên hàng nút có một dòng nói đúng thứ sắp chạy, ví dụ:

```
MiniMax H3 · I2V · 960×544 · 5s · native
```

### Nút Chỉnh

Nhấn **Chỉnh** để mở ba tuỳ chọn:

- **Khổ hình** — tỷ lệ khung hình
- **Mức chất lượng** — Nháp / Cân bằng / Nét
- **Thời lượng** — số giây

Các tham số còn lại do model quyết định, chat không phơi ra để giữ ô soạn gọn.

### Cảnh báo đổi model

Nếu model bạn chọn không nhận được tổ hợp file đang đính, chat **không tự đổi ngầm**. Nó dựng kế hoạch bằng model khác và hiện một dòng vàng báo rõ:

> Câu này chạy bằng *[model]* · *[chế độ]* — model bạn chọn không nhận được đầu vào đang đính kèm.

### Chip hỏi lại khi mơ hồ

Khi cùng một tổ hợp file có nhiều cách hiểu điểm sát nhau, chat hiện một hàng chip *"Các file này dùng làm:"* để bạn chốt, thay vì tự đoán.

---

## Thư Viện Dự Án

Vùng bên cạnh cột chat là **toàn bộ kết quả của dự án đang mở** — do chat tạo hay do app tạo đều nằm chung, nhóm theo ngày.

### Lọc

Thanh trên cùng lọc theo:

- **Loại** — ảnh / video / nhạc
- **Nguồn** — từ chat hay từ app
- **Model** — model đã từng tạo ra kết quả trong dự án
- **Tìm kiếm** — theo prompt hoặc tên file

### Dùng lại kết quả

Mở một kết quả ra xem toàn màn hình, bạn có ba lựa chọn:

| Hành động | Kết quả |
|-----------|---------|
| **Dùng làm đầu vào** | Đính kết quả đó vào ô soạn cho lượt tiếp theo |
| **Tạo biến thể** | Điền lại prompt cũ vào ô soạn để chạy lại với seed khác |
| **Mở trong app** | Chuyển sang app đã tạo ra nó để chỉnh sâu hơn |

### Job chạy nền

Lượt đang chạy hiện thành một ô giữ chỗ ở đầu nhóm "Hôm nay", có nút huỷ. Job sống ngoài giao diện chat, nên **đổi hội thoại hay đóng cột chat đều không huỷ nó**.

> ⚠️ **Lưu ý**: Job chỉ sống trong bộ nhớ của phiên làm việc. Tắt app khi job đang chạy thì lượt đó mất; kết quả đã xong thì vẫn còn trong thư viện.

---

## Hội Thoại

Hội thoại thuộc về **dự án**: đổi dự án thì danh sách hội thoại và thư viện đổi theo.

- Nhấn **+** ở đầu cột chat để tạo hội thoại mới
- Tiêu đề tự lấy từ câu đầu tiên bạn gõ
- Toàn bộ lịch sử lưu trên máy, mở lại app vẫn còn

Mỗi tin nhắn giữ một bản chụp lần chạy của nó — mở lại hội thoại ở phiên sau vẫn thấy đã chạy bằng model gì và ra kết quả nào.

---

## Dùng Skill Trong Chat

Gõ `/` trong ô soạn để mở bảng chọn skill, hoặc nhấn biểu tượng mảnh ghép ở đáy ô soạn. Skill sẽ viết prompt giúp bạn thay vì bạn tự nghĩ từ đầu.

Có loại skill nhiều bước: nó tự hỏi bạn vài câu, sinh ảnh, chờ bạn duyệt rồi mới sinh video.

Xem chi tiết tại [Hướng Dẫn Skill](./skill-guide.md).

---

## Xử Lý Sự Cố

### Gõ prompt tạo nhạc nhưng lại ra video

Loại đầu ra đang để Video. Chat không đọc nghĩa câu chữ. Nhấn chip model → tab **Nhạc** → chọn model nhạc. Xem [Chọn Loại Đầu Ra Và Model](#chọn-loại-đầu-ra-và-model).

### "Chưa cài model nào cho loại đầu ra này"

Loại đầu ra bạn chọn chưa có model nào. Cài model tương ứng qua **Apps** hoặc **Store**, rồi quay lại chat.

### "Không có chế độ nào nhận được tổ hợp file đang đính kèm"

Tổ hợp file vượt quá thứ model hiện tại nhận được — ví dụ đính 5 ảnh vào model chỉ nhận tối đa 4. Bớt file, hoặc đổi sang model khác.

### Nút gửi bị mờ

Nút gửi chỉ bật khi có **cả** nội dung văn bản **và** một kế hoạch chạy hợp lệ. Ô soạn trống thì không gửi được, kể cả khi đã đính file.

### Chip file hiện mờ khi mở lại hội thoại

File đính kèm từ phiên trước không lưu lại được nếu nó chỉ nằm trong bộ nhớ tạm. Chip đó được đánh dấu hết hạn — đính lại file là chạy tiếp được.

---

## Xem Thêm

- [🧩 Hướng Dẫn Skill](./skill-guide.md)
- [🎬 Hướng Dẫn MiniMax H3](./minimax-h3-guide.md)
- [🛒 Hướng Dẫn App Store](./app-store-guide.md)
