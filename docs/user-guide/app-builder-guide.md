# 🛠️ Hướng Dẫn Sử Dụng App Builder

**App Builder** là công cụ mạnh mẽ cho phép bạn tạo các ứng dụng AI tùy chỉnh từ workflow ComfyUI của riêng bạn, với giao diện người dùng trực quan và dễ sử dụng.

---

## 📋 Mục Lục

- [Giới Thiệu](#giới-thiệu)
- [Bắt Đầu Nhanh](#bắt-đầu-nhanh)
- [Quy Trình 5 Bước](#quy-trình-5-bước)
  - [Bước 1: Upload Workflow](#bước-1-upload-workflow)
  - [Bước 2: Thông Tin Ứng Dụng](#bước-2-thông-tin-ứng-dụng)
  - [Bước 3: Kiểm Tra Dependencies](#bước-3-kiểm-tra-dependencies)
  - [Bước 4: Thiết Kế Giao Diện](#bước-4-thiết-kế-giao-diện)
  - [Bước 5: Xem Trước & Triển Khai](#bước-5-xem-trước--triển-khai)
- [Quản Lý Ứng Dụng](#quản-lý-ứng-dụng)
- [Xuất Bản Lên App Store](#xuất-bản-lên-app-store)
- [Tips & Best Practices](#tips--best-practices)
- [Xử Lý Sự Cố](#xử-lý-sự-cố)

---

## 🎯 Giới Thiệu

App Builder cho phép bạn:

- ✅ **Tạo ứng dụng AI tùy chỉnh** từ workflow ComfyUI
- ✅ **Thiết kế giao diện** với drag-and-drop builder
- ✅ **Tự động phát hiện dependencies** (models, custom nodes)
- ✅ **Test trực tiếp** trong quá trình xây dựng
- ✅ **Lưu trữ offline** và sử dụng ngay lập tức
- ✅ **Xuất bản lên App Store** để chia sẻ với cộng đồng

---

## 🚀 Bắt Đầu Nhanh

### Truy Cập App Builder

1. Mở **Komfy Studio**
2. Click vào tab **"Apps"** trên thanh sidebar bên trái
3. Click nút **"Builder"** ở góc trên bên phải
4. Hoặc click **"Create New App"** từ My Apps dashboard

### Yêu Cầu

- ✅ Một workflow ComfyUI đã được test và hoạt động tốt (file `.json`)
- ✅ Backend đang chạy và kết nối thành công
- ✅ Các models và custom nodes cần thiết đã được cài đặt

---

## 📝 Quy Trình 5 Bước

### Bước 1: Upload Workflow

**Mục đích**: Import workflow ComfyUI của bạn vào App Builder

#### Cách Thực Hiện:

1. **Chọn nguồn workflow**:
   - **Upload File**: Click "Upload Workflow File" và chọn file `.json`
   - **Từ Thư Viện**: Chọn từ danh sách workflows đã lưu

2. **Xác nhận workflow**:
   - Hệ thống sẽ tự động phân tích workflow
   - Kiểm tra các nodes và parameters
   - Phát hiện inputs có thể tùy chỉnh

3. **Click "Next"** để tiếp tục

#### 💡 Tips:

- Đảm bảo workflow đã được test kỹ trong ComfyUI trước khi import
- Workflow nên có cấu trúc rõ ràng với các parameters dễ điều chỉnh
- Tránh workflow quá phức tạp với nhiều nhánh logic

---

### Bước 2: Thông Tin Ứng Dụng

**Mục đích**: Cung cấp metadata và thông tin mô tả cho ứng dụng

#### Các Trường Thông Tin:

##### 📌 Thông Tin Cơ Bản

- **Tên Ứng Dụng** (bắt buộc):
  - Tên hiển thị của ứng dụng
  - Nên ngắn gọn, dễ nhớ (VD: "Portrait Generator", "Style Transfer AI")
  
- **Mô Tả** (bắt buộc):
  - Mô tả chi tiết chức năng của ứng dụng
  - Giải thích input/output
  - Gợi ý cách sử dụng tối ưu

- **Icon** (khuyến nghị):
  - Click "Upload Icon" để chọn hình ảnh
  - Format: PNG, JPG, WebP
  - Kích thước khuyến nghị: 512x512px
  - Icon sẽ tự động resize và tối ưu

##### 🏷️ Phân Loại

- **Category**:
  - Image: Ứng dụng tạo/chỉnh sửa ảnh
  - Video: Ứng dụng tạo/chỉnh sửa video
  - Audio: Ứng dụng xử lý âm thanh
  - General: Các ứng dụng khác

- **Tags** (tùy chọn):
  - Thêm các từ khóa để dễ tìm kiếm
  - VD: "portrait", "anime", "realistic", "fast"

##### 📦 Thông Tin Kỹ Thuật

- **Version**:
  - Theo chuẩn Semantic Versioning (VD: 1.0.0)
  - Tăng version khi cập nhật ứng dụng

- **Author**:
  - Tên tác giả (tự động lấy từ thông tin đăng nhập)

#### 💡 Tips:

- Viết mô tả rõ ràng, dễ hiểu
- Chọn icon đẹp và liên quan đến chức năng
- Sử dụng tags phù hợp để tăng khả năng tìm kiếm

---

### Bước 3: Kiểm Tra Dependencies

**Mục đích**: Xác nhận các models và custom nodes cần thiết

#### Hệ Thống Tự Động:

App Builder sẽ tự động:
- ✅ Phân tích workflow và phát hiện dependencies
- ✅ Kiểm tra models đã cài đặt
- ✅ Kiểm tra custom nodes đã cài đặt
- ✅ Hiển thị danh sách thiếu (nếu có)

#### Trạng Thái Dependencies:

- **✅ Installed**: Đã cài đặt, sẵn sàng sử dụng
- **⚠️ Missing**: Chưa cài đặt, cần tải về
- **ℹ️ Optional**: Không bắt buộc, có thể bỏ qua

#### Xử Lý Dependencies Thiếu:

1. **Models thiếu**:
   - Click "Download" để tải model
   - Hoặc vào **Tools > Models Manager** để cài đặt thủ công

2. **Custom Nodes thiếu**:
   - Click "Install" để cài đặt node
   - Hoặc vào **Tools > Custom Nodes** để cài đặt thủ công

3. **Sau khi cài đặt**:
   - Click "Revalidate" để kiểm tra lại
   - Đảm bảo tất cả dependencies đều ✅ trước khi tiếp tục

#### 💡 Tips:

- Cài đặt đầy đủ dependencies trước khi publish
- Ghi chú rõ ràng về requirements trong mô tả app
- Test kỹ với các models khác nhau nếu app hỗ trợ nhiều models

---

### Bước 4: Thiết Kế Giao Diện

**Mục đích**: Tạo giao diện người dùng trực quan cho ứng dụng

#### 🎨 Design Canvas

Bước này cho phép bạn thiết kế layout của ứng dụng với drag-and-drop interface.

##### Các Thành Phần UI (Components):

###### 📝 Input Controls

- **Text Input**:
  - Nhập text prompt, mô tả
  - Hỗ trợ multiline, placeholder
  - Bind với node parameters

- **Number Input**:
  - Nhập số (steps, CFG, seed, etc.)
  - Hỗ trợ min/max, step increment
  - Slider hoặc input box

- **Dropdown/Select**:
  - Chọn từ danh sách (models, samplers, schedulers)
  - Single hoặc multi-select

- **Checkbox/Toggle**:
  - Bật/tắt tính năng
  - Boolean parameters

- **Image Upload**:
  - Upload ảnh input
  - Preview thumbnail
  - Drag & drop support

###### 🎛️ Advanced Controls

- **Slider**:
  - Điều chỉnh giá trị liên tục
  - Visual feedback

- **Color Picker**:
  - Chọn màu sắc
  - Hex/RGB output

- **File Upload**:
  - Upload các file khác (video, audio, etc.)

###### 📊 Display Components

- **Label/Text**:
  - Hiển thị text tĩnh
  - Hướng dẫn, ghi chú

- **Divider**:
  - Phân chia sections
  - Tổ chức layout

- **Group/Container**:
  - Nhóm các controls lại
  - Collapsible sections

##### 🔗 Parameter Binding

**Liên kết UI controls với workflow parameters**:

1. **Chọn component** trên canvas
2. **Mở Properties Panel** bên phải
3. **Chọn "Bind to Parameter"**
4. **Chọn node và parameter** từ workflow
5. **Cấu hình mapping** (nếu cần transform)

**Ví dụ**:
```
Text Input "Prompt" → KSampler.positive
Number Input "Steps" → KSampler.steps
Dropdown "Model" → CheckpointLoaderSimple.ckpt_name
```

##### 🎯 Layout Organization

- **Drag & Drop**: Kéo thả components vào canvas
- **Resize**: Điều chỉnh kích thước components
- **Reorder**: Sắp xếp thứ tự hiển thị
- **Group**: Nhóm các controls liên quan
- **Responsive**: Layout tự động điều chỉnh theo màn hình

#### 💡 Tips:

- Sắp xếp controls theo thứ tự logic (prompt → settings → advanced)
- Nhóm các parameters liên quan vào sections
- Sử dụng labels và tooltips để hướng dẫn người dùng
- Test layout trên các kích thước màn hình khác nhau
- Ẩn các advanced parameters vào collapsible sections

---

### Bước 5: Xem Trước & Triển Khai

**Mục đích**: Test ứng dụng và lưu vào thư viện

#### 🎬 Preview & Test

##### Test Interface:

Bước này hiển thị app trong môi trường thực tế:

- **Left Panel**: Form với các controls bạn đã thiết kế
- **Right Panel**: Preview kết quả generation

##### Test Workflow:

1. **Điền thông tin** vào form (prompt, parameters)
2. **Click "Generate"** để test
3. **Xem kết quả** ở panel bên phải
4. **Kiểm tra**:
   - ✅ Tất cả controls hoạt động đúng
   - ✅ Parameters được truyền chính xác
   - ✅ Output hiển thị đúng format
   - ✅ Không có lỗi generation

##### Debug:

Nếu có lỗi:
- Kiểm tra console logs
- Xác nhận parameter bindings
- Test lại với values khác nhau
- Quay lại Bước 4 để điều chỉnh

#### 💾 Deploy App

Khi test thành công:

1. **Click "Deploy App"** (nút xanh lá)
2. **Xác nhận thông tin**
3. **Chờ hệ thống lưu**
4. **App sẽ xuất hiện trong "My Apps"**

#### 🌐 Publish to Store (Tùy chọn)

Nếu muốn chia sẻ với cộng đồng:

1. **Click "Publish to Store"** (nút xanh dương với icon 🌐)
2. **Xác nhận**:
   - Tất cả thông tin đã đầy đủ
   - Icon đã upload
   - Dependencies đã liệt kê đầy đủ
3. **Click "Confirm"**
4. **App sẽ được đóng gói (.kapp) và upload lên App Store**

#### 💡 Tips:

- Test kỹ với nhiều input khác nhau
- Kiểm tra edge cases (empty input, extreme values)
- Đảm bảo error handling hoạt động tốt
- Viết mô tả rõ ràng trước khi publish

---

## 📱 Quản Lý Ứng Dụng

### My Apps Dashboard

Truy cập: **Apps > My Apps** hoặc click **"My Apps"** trong App Builder

#### Chức Năng:

##### 📋 Xem Danh Sách

- Hiển thị tất cả apps đã tạo
- Thông tin: Icon, tên, category, version
- Trạng thái: Local, Published

##### ✏️ Chỉnh Sửa (Edit)

1. Click **icon Edit** (✏️) trên app card
2. App Builder sẽ mở với dữ liệu đã lưu
3. Chỉnh sửa bất kỳ bước nào
4. Click **"Update App"** để lưu thay đổi

##### 🗑️ Xóa (Delete)

1. Click **icon Delete** (🗑️)
2. Xác nhận xóa
3. ⚠️ **Cảnh báo**: Không thể khôi phục sau khi xóa

##### 📤 Xuất (Export)

1. Click **icon Export** (📤)
2. Chọn vị trí lưu file `.kapp`
3. Sử dụng để:
   - Backup ứng dụng
   - Chia sẻ với người khác
   - Import vào máy khác

##### 🌐 Xuất Bản (Publish)

1. Click **icon Publish** (🌐)
2. Xem lại thông tin
3. Xác nhận publish
4. App sẽ xuất hiện trên App Store

---

## 🏪 Xuất Bản Lên App Store

### Quy Trình Publish

#### 1️⃣ Chuẩn Bị

Đảm bảo app của bạn:

- ✅ **Hoạt động ổn định**: Đã test kỹ, không lỗi
- ✅ **Thông tin đầy đủ**: Tên, mô tả, icon, category
- ✅ **Dependencies rõ ràng**: Liệt kê đầy đủ models và nodes cần thiết
- ✅ **Mô tả chi tiết**: Hướng dẫn sử dụng, requirements
- ✅ **Icon chất lượng cao**: Ảnh đẹp, rõ nét, liên quan

#### 2️⃣ Publish

**Từ App Builder** (Bước 5):
- Click **"Publish to Store"**

**Từ My Apps**:
- Click icon **Publish** (🌐) trên app card

#### 3️⃣ Xác Nhận

Hệ thống sẽ:
1. Đóng gói app thành file `.kapp`
2. Upload app và icon
3. Publish app lên App Store

#### 4️⃣ Sau Khi Publish

- App xuất hiện trên **App Store** ngay lập tức
- Người dùng khác có thể tìm, xem và cài đặt
- Bạn có thể theo dõi số lượt cài đặt (sắp có)

### Cập Nhật App Đã Publish

Khi cần cập nhật:

1. **Edit app** từ My Apps
2. **Tăng version number** (VD: 1.0.0 → 1.1.0)
3. **Chỉnh sửa** nội dung cần thiết
4. **Update App**
5. **Publish lại**

Hệ thống sẽ:
- Kiểm tra version (phải cao hơn version cũ)
- Tạo version mới trong database
- Người dùng sẽ thấy thông báo "Update Available"

### Quy Tắc & Best Practices

#### ✅ Nên:

- Viết mô tả rõ ràng, dễ hiểu
- Upload icon chất lượng cao
- Liệt kê đầy đủ requirements
- Test kỹ trước khi publish
- Cập nhật version đúng chuẩn SemVer
- Trả lời feedback từ người dùng

#### ❌ Không nên:

- Publish app chưa test kỹ
- Thiếu thông tin hoặc mô tả sơ sài
- Sử dụng icon không liên quan
- Spam nhiều versions không cần thiết
- Copy app của người khác

---

## 💡 Tips & Best Practices

### Thiết Kế Workflow

- **Đơn giản hóa**: Workflow càng đơn giản càng dễ maintain
- **Parameterize**: Expose các parameters quan trọng
- **Default values**: Đặt giá trị mặc định hợp lý
- **Error handling**: Xử lý edge cases trong workflow

### Thiết Kế UI

- **User-friendly**: Giao diện trực quan, dễ sử dụng
- **Logical flow**: Sắp xếp controls theo thứ tự logic
- **Visual hierarchy**: Nhóm và phân cấp thông tin rõ ràng
- **Responsive**: Test trên nhiều kích thước màn hình

### Metadata

- **Descriptive names**: Tên app ngắn gọn, dễ nhớ
- **Detailed description**: Giải thích rõ chức năng, cách dùng
- **Proper categorization**: Chọn category và tags phù hợp
- **Version control**: Quản lý version đúng chuẩn

### Testing

- **Comprehensive testing**: Test với nhiều inputs khác nhau
- **Edge cases**: Kiểm tra các trường hợp đặc biệt
- **Performance**: Đảm bảo app chạy mượt mà
- **User feedback**: Lắng nghe và cải thiện dựa trên feedback

---

## 🔧 Xử Lý Sự Cố

### Lỗi Upload Workflow

**Triệu chứng**: Không thể upload file workflow

**Giải pháp**:
- Kiểm tra file có đúng format `.json` không
- Mở file bằng text editor, xác nhận JSON hợp lệ
- Thử export lại workflow từ ComfyUI
- Kiểm tra kích thước file (không quá lớn)

### Dependencies Không Được Phát Hiện

**Triệu chứng**: Hệ thống không hiển thị đầy đủ models/nodes cần thiết

**Giải pháp**:
- Đảm bảo backend đang chạy và kết nối
- Refresh danh sách models/nodes trong Tools
- Kiểm tra workflow có sử dụng custom nodes không chuẩn
- Thử revalidate dependencies

### UI Controls Không Bind Được

**Triệu chứng**: Không thể liên kết control với parameter

**Giải pháp**:
- Kiểm tra workflow có node tương ứng không
- Xác nhận parameter name chính xác
- Thử xóa và tạo lại control
- Kiểm tra data type có khớp không (string, number, etc.)

### Test Generation Lỗi

**Triệu chứng**: Lỗi khi click "Generate" trong Preview

**Giải pháp**:
- Kiểm tra console logs để xem lỗi cụ thể
- Xác nhận tất cả required parameters đã được bind
- Test workflow trực tiếp trong ComfyUI
- Kiểm tra backend logs
- Verify models đã load đúng

### Publish Thất Bại

**Triệu chứng**: Không thể publish app lên Store

**Giải pháp**:
- Kiểm tra kết nối internet
- Xác nhận đã đăng nhập
- Verify tất cả required fields đã điền
- Kiểm tra version number (phải > version cũ nếu update)
- Thử lại sau vài phút

### App Không Xuất Hiện Trong My Apps

**Triệu chứng**: Sau khi deploy, app không hiển thị

**Giải pháp**:
- Refresh trang (Ctrl+R)
- Kiểm tra tab "My Apps" đã được chọn
- Xem console logs có lỗi không
- Thử tạo lại app
- Kiểm tra database connection

---

## 📞 Hỗ Trợ

Nếu gặp vấn đề không được liệt kê ở trên:

1. Kiểm tra [Common Issues](../troubleshooting/common-issues.md)
2. Xem [FAQ](../troubleshooting/faq.md)
3. Tạo issue trên GitHub
4. Liên hệ support team

---

**Cập nhật lần cuối**: 2026-02-06  
**Phiên bản**: 1.0.0
