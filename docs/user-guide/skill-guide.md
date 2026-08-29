# 🧩 Hướng Dẫn Skill

> Công thức prompt dùng lại được. Gõ một dấu `/` ở bất kỳ ô prompt nào của bất kỳ app nào là gọi ra.

## Mục Lục

- [Tổng Quan](#tổng-quan)
- [Ba Loại Skill](#ba-loại-skill)
- [Bắt Đầu Sử Dụng](#bắt-đầu-sử-dụng)
- [Skill Nhiều Bước](#skill-nhiều-bước)
- [Skill Hub](#skill-hub)
- [Quản Lý Skill Của Bạn](#quản-lý-skill-của-bạn)
- [Cấu Hình Model Ngôn Ngữ](#cấu-hình-model-ngôn-ngữ)
- [Xử Lý Sự Cố](#xử-lý-sự-cố)

---

## Tổng Quan

Viết prompt tốt là phần khó nhất khi dùng model tạo ảnh/video. **Skill** đóng gói cái khó đó lại thành một thứ gọi ra được bằng một dấu gạch chéo.

Skill dùng được ở **mọi ô prompt của mọi app**, không riêng gì Chat — app MiniMax H3, LTX, WAN, app bạn tự dựng bằng App Builder đều có.

Mỗi skill khai báo nó phục vụ app nào và chế độ nào, nên bảng chọn chỉ hiện skill hợp với chỗ bạn đang đứng — đứng ở chế độ I2V thì không thấy skill viết cho nhạc.

---

## Ba Loại Skill

| Loại | Cách hoạt động | Cần mạng | Cần API key |
|------|----------------|----------|-------------|
| **Template** | Chèn thẳng khung prompt vào ô nhập để bạn điền tiếp | Không | Không |
| **LLM** | Bạn gõ ý tưởng ngắn, model ngôn ngữ viết thành prompt hoàn chỉnh | Có | Có |
| **Nhiều bước** | Tự hỏi, tự sinh ảnh, chờ duyệt rồi sinh video | Có | Có |

> 💡 **Tip**: Skill Template chạy được ngay sau khi cài, không cần cấu hình gì. Nếu bạn chưa có API key, hãy bắt đầu từ nhóm này.

---

## Bắt Đầu Sử Dụng

### Bước 1: Mở bảng chọn skill

Có hai cách, tuỳ bạn thuận tay nào:

- **Gõ `/`** trong ô prompt — dấu `/` phải đứng riêng (ở đầu ô hoặc sau khoảng trắng)
- **Nhấn biểu tượng mảnh ghép** ở thanh công cụ dưới ô prompt

### Bước 2: Tìm skill

Bảng chọn có ô tìm kiếm và các tab phân loại:

- **All** — tất cả skill hợp với ô prompt hiện tại
- **My Skills** — skill bạn tự tạo hoặc đã cài
- **Featured** — skill nổi bật trên hub

Danh sách còn kèm cả **skill trên hub chưa cài**, xếp sau skill đã có trong máy. Chọn một cái ở nhóm đó là nó cài luôn rồi dùng ngay, không phải bỏ dở câu đang gõ.

> 💡 **Tìm không dấu**: Gõ `giay` vẫn ra skill `giấy`. Không cần bỏ dấu chính xác.

### Bước 3: Dùng skill

Tuỳ loại skill:

**Với skill Template** — khung prompt được chèn thẳng vào ô nhập. Bạn điền các chỗ trống rồi chạy như bình thường.

**Với skill LLM** — tên skill gắn thành một chip trong ô nhập. Bạn gõ ý tưởng ngắn gọn (tiếng Việt cũng được), nhấn **Viết prompt**, skill trả về prompt hoàn chỉnh.

Sau khi skill viết xong, nó hiện thêm phần **giả định** — những chi tiết skill tự điền vì bạn không nói rõ. Đọc phần này để biết nó hiểu đúng ý chưa. Không ưng thì hoàn tác và gõ lại brief cụ thể hơn.

---

## Skill Nhiều Bước

Đây là loại skill mạnh nhất, và chỉ chạy trong **Chat**.

Thay vì chỉ viết prompt rồi dừng, skill nhiều bước tự điều khiển cả quy trình:

1. Bạn mô tả ý tưởng, ví dụ *"làm video con mèo chơi trong bếp, phong cách collage giấy"*
2. Skill **hỏi lại** vài câu để chốt hướng — bao nhiêu cảnh, tỷ lệ khung hình, có nhạc nền không
3. Skill **sinh ảnh** cho từng cảnh
4. Skill **dừng chờ bạn duyệt** — ưng thì cho đi tiếp, không ưng thì cho làm lại
5. Skill **sinh video** từ những ảnh đã duyệt

Toàn bộ diễn ra trong một thẻ ngay trong hội thoại, có nút trả lời, huỷ và tiếp tục.

### Lượt chạy không mất khi tắt app

Lượt chạy sống ngoài giao diện, nên đổi hội thoại không làm mất nó.

- Lượt đang **chờ bạn trả lời** thì khôi phục trọn vẹn — mở lại app vẫn thấy câu hỏi và trả lời tiếp được
- Lượt đang **chạy dở** thì được đánh dấu gián đoạn, vì hệ thống không biết nó dừng ở giữa bước nào. Bạn cho chạy lại từ chỗ đó

Lịch sử giữ **10 lượt gần nhất trong 7 ngày**.

---

## Skill Hub

Vào **Skill** ở sidebar để mở Skill Hub. Có hai tab:

### Tab Khám phá

Kho skill chung do cộng đồng đóng góp. Lọc theo phân loại, sắp theo mức phổ biến. Nhấn vào một skill để xem mô tả đầy đủ trước khi cài.

### Tab Skill của tôi

Toàn bộ skill đang có trong máy, lọc được theo nguồn:

| Nguồn | Ý nghĩa |
|-------|---------|
| **Builtin** | Có sẵn trong app, nâng cấp app là nâng cấp luôn |
| **Store** | Cài từ Skill Hub |
| **User** | Bạn tự tạo hoặc tự nhập vào |

Khi hai skill trùng slug, thứ tự ưu tiên là **user > store > builtin** — skill của bạn luôn thắng.

### Đăng skill lên hub

Trong tab Skill của tôi, chọn skill muốn chia sẻ rồi dùng chức năng đăng lên hub. Điền mô tả, phân loại, rồi gửi. Skill của bạn sẽ xuất hiện trong tab Khám phá của người khác.

---

## Quản Lý Skill Của Bạn

- **Tắt tạm** — skill không dùng tới có thể tắt để bảng chọn gọn lại, không cần gỡ hẳn
- **Gỡ cài đặt** — với skill cài từ hub
- **Nhập / xuất** — skill đóng gói thành file, gửi cho người khác hoặc sao lưu

Slug của skill là thứ bạn gõ sau dấu `/`, nên nó phải là **chữ thường, số và gạch ngang** — ví dụ `paper-collage-explainer`.

---

## Cấu Hình Model Ngôn Ngữ

Skill loại **LLM** và **nhiều bước** cần một model ngôn ngữ để chạy. Skill Template thì không.

1. Vào **Settings**
2. Nhập **OpenAI API key**
3. Chọn model nếu muốn đổi khỏi mặc định

> ⚠️ **Lưu ý**: Phần này gọi API của bên thứ ba nên **có tính phí theo lượt dùng** và cần kết nối mạng — khác với phần tạo ảnh/video vốn chạy 100% trên máy bạn. Nếu chỉ muốn dùng offline hoàn toàn, hãy dùng skill Template.

---

## Xử Lý Sự Cố

### Gõ `/` mà không thấy bảng chọn

Dấu `/` phải **đứng riêng** — ở đầu ô, hoặc có khoảng trắng đứng trước. Gõ `abc/` thì không mở. Thử nhấn biểu tượng mảnh ghép thay thế.

### Bảng chọn trống hoặc thiếu skill quen thuộc

Skill lọc theo app và chế độ bạn đang đứng. Skill viết cho chế độ khác sẽ không hiện. Kiểm tra xem skill đó có bị tắt trong tab **Skill của tôi** không.

### Skill LLM báo lỗi thiếu key

Chưa nhập OpenAI API key trong Settings. Xem [Cấu Hình Model Ngôn Ngữ](#cấu-hình-model-ngôn-ngữ).

### Skill nhiều bước dừng giữa chừng sau khi mở lại app

Đây là hành vi cố ý. Lượt đang chạy dở không khôi phục được vì không xác định được nó dừng ở giữa lần gọi model hay giữa lần sinh video — hệ thống đánh dấu gián đoạn thay vì giả vờ chạy tiếp và cho ra kết quả sai. Cho chạy lại từ bước đó.

### Skill viết prompt không đúng ý

Đọc phần **giả định** mà skill trả về — nó liệt kê những chi tiết skill tự điền. Hoàn tác rồi viết brief cụ thể hơn ở đúng những chỗ đó.

---

## Xem Thêm

- [💬 Hướng Dẫn Chat](./chat-guide.md)
- [🏗️ Hướng Dẫn App Builder](./app-builder-guide.md)
- [🛒 Hướng Dẫn App Store](./app-store-guide.md)
