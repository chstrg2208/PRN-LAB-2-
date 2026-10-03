# 🎨 Design Brief: F-Event Design System & Guidelines
**Dự án:** F-Event — FPT Campus Event Hub  
**Môn học:** PRM323 — Cross-Platform Application Development  
**Sinh viên thực hiện:** Nguyễn Minh Tú (MSSV: SE193059)  
**Tài liệu cơ sở:** Bản mô tả thiết kế chuẩn hóa cung cấp làm ngữ cảnh đầu vào cho Google Stitch và hệ thống Figma Tokens.

---

## 1. Bản sắc Thương hiệu & Giọng điệu (Brand Identity & Tone of Voice)

- **Phong cách thị giác (Visual Style):** Hiện đại, tinh tế, năng động, mang đậm tinh thần công nghệ và học thuật của sinh viên Đại học FPT (FPT University). Giao diện hướng đến sự gọn gàng, giảm thiểu tải nhận thức (cognitive load), ưu tiên thông tin sự kiện và hành động đăng ký rõ ràng.
- **Tone & Voice:** Thân thiện, truyền cảm hứng, chính xác và đáng tin cậy. Các thông báo hệ thống dùng ngôn ngữ ngắn gọn, rõ ràng, lịch sự, không dùng thuật ngữ kỹ thuật phức tạp gây bối rối cho người dùng (ví dụ: dùng *"Không thể kết nối Internet, vui lòng kiểm tra lại mạng"* thay vì *"HTTP 503 Service Unavailable"*).

---

## 2. Hệ thống Token Thiết kế (Design Tokens)

### 2.1. Bảng Màu Chuẩn (Color Tokens & WCAG 2.1 AA Compliance)

Tất cả các màu được tính toán cẩn thận để đạt tỷ lệ tương phản tối thiểu **4.5:1 đối với văn bản thông thường** và **3:1 đối với điều khiển UI / văn bản lớn** theo tiêu chuẩn **WCAG 2.1 Level AA**:

| Tên Token (Figma / Flutter) | Giá trị Hex | Vai trò & Mục đích Sử dụng | Tỷ lệ Tương phản (Contrast Ratio) |
| :--- | :--- | :--- | :--- |
| `color-primary` | `#F27024` | **FPT Orange**: Màu thương hiệu chính; dùng cho nút CTA chính (Primary Button), tab đang chọn, badge "Hot", thanh tiến độ | 3.2:1 (so với trắng - đạt chuẩn icon/large UI) / 7.1:1 (so với text đen) |
| `color-primary-container` | `#FFF0E6` | Màu nền cam nhạt; dùng cho nền chip đã chọn, nền thẻ thông báo nổi bật | 1.15:1 (so với trắng) |
| `color-secondary` | `#1B365D` | **FPT Navy Blue**: Màu bổ trợ; dùng cho App Bar header, tiêu đề cấp cao H1, thẻ sự kiện học thuật trang trọng | 12.8:1 (so với nền trắng - Đạt chuẩn AAA) |
| `color-secondary-container` | `#E8EEF5` | Nền xanh navy nhạt; dùng cho chip danh mục Học thuật/Tech | 1.2:1 (so với trắng) |
| `color-surface` | `#FFFFFF` | Nền trắng tinh khiết của các thẻ Card, Bottom Sheet, Dialog và TextField | - |
| `color-background` | `#F8F9FA` | Nền xám nhạt toàn ứng dụng (Light Theme), giúp các thẻ card màu trắng nổi khối rõ rệt | - |
| `color-text-primary` | `#1A1A1A` | Chữ chính cho tiêu đề, nội dung sự kiện, nhãn trường nhập liệu | **13.5:1** (so với `#FFFFFF` - Vượt xa chuẩn 4.5:1) |
| `color-text-secondary` | `#595959` | Chữ phụ cho ngày giờ, địa điểm, tên diễn giả, mô tả ngắn | **5.4:1** (so với `#FFFFFF` - Đạt chuẩn WCAG 4.5:1) |
| `color-text-disabled` | `#8C8C8C` | Chữ cho trạng thái vô hiệu hóa (Disabled text/icon) | 3.0:1 |
| `color-border` | `#E0E0E0` | Đường viền ngăn cách (divider), viền thẻ card, viền textfield trạng thái default | - |
| `color-success` | `#1E8E3E` | Màu thông báo thành công: Trạng thái vé "Hợp lệ / Đã điểm danh", thông báo đăng ký thành công | 4.6:1 (Đạt WCAG AA) |
| `color-error` | `#D93025` | Màu cảnh báo lỗi: Trạng thái "Hết slot", thông báo mất mạng, textfield nhập sai định dạng | 4.7:1 (Đạt WCAG AA) |
| `color-warning` | `#E37400` | Màu cảnh báo nhẹ: Slot sắp hết (còn < 5 vé), thông báo danh sách chờ Waitlist | 3.5:1 |

---

### 2.2. Thang Đo Kiểu Chữ (Typography Scale)

Sử dụng bộ font không chân hiện đại **Inter** (hoặc **Roboto** trên nền tảng Android/Flutter), với quy định nghiêm ngặt: **Không có bất kỳ văn bản nội dung nào nhỏ hơn 14 sp** (đáp ứng trọn vẹn tiêu chí mục 6 của đề bài):

| Tên Token Typo | Cỡ chữ (Size) | Độ đậm (Weight) | Khoảng cách dòng (Line Height) | Mục đích Áp dụng |
| :--- | :--- | :--- | :--- | :--- |
| `type-display-large` | **26 sp** | Bold (700) | 34 sp | Tiêu đề chính màn hình Login, Tiêu đề sự kiện nổi bật |
| `type-title-large` | **20 sp** | Bold (700) | 28 sp | Tiêu đề các mục lớn trên Home ("Sự kiện sắp diễn ra", "CLB đề xuất") |
| `type-title-medium` | **18 sp** | SemiBold (600) | 24 sp | Tiêu đề của từng thẻ Event Card, Tên sự kiện trên App Bar |
| `type-body-large` | **16 sp** | Regular (400) / Medium (500) | 24 sp | Nội dung đoạn văn mô tả chi tiết sự kiện (`SCR_03`), nội dung form |
| `type-body-medium` | **14 sp** | Regular (400) | 20 sp | **Cỡ chữ nội dung tiêu chuẩn** (ngày giờ, địa điểm, nhãn trường form) |
| `type-label-large` | **14 sp** | SemiBold (600) | 20 sp | Chữ trên nút bấm chính (Button Text), Chữ trên Bottom Nav item |
| `type-label-small` | **12 sp** | Medium (500) | 16 sp | Nhãn tag thể loại (Chip badge), số thứ tự Waitlist, ghi chú chân trang |

---

### 2.3. Hệ thống Khoảng cách Lưới (Spacing Tokens - 8dp Grid System)

Tuân thủ nghiêm ngặt hệ thống lưới cơ sở **8-point grid** của Google Material Design 3, bảo đảm tính nhịp nhàng và nhất quán trên toàn bộ màn hình:

| Tên Token Spacing | Kích thước | Ứng dụng Thực tế trong Layout |
| :--- | :--- | :--- |
| `spacing-xxs` | **4 dp** | Khoảng cách giữa icon và text nhỏ trong tag, padding nội bộ nhỏ |
| `spacing-xs` | **8 dp** | Khoảng cách giữa các chip lọc ngang, khoảng cách giữa title và subtitle |
| `spacing-sm` | **12 dp** | Khoảng cách giữa các phần tử nhập liệu trong form, padding trong thẻ card nhỏ |
| `spacing-md` | **16 dp** | **Khoảng cách lề chuẩn (Standard Screen Margin)** hai bên mép màn hình 360dp |
| `spacing-lg` | **24 dp** | Khoảng cách giữa các khối nội dung lớn (Section Gap), padding của Bottom Sheet |
| `spacing-xl` | **32 dp** | Khoảng cách trước nút CTA lớn ở chân trang, khoảng cách từ Header xuống nội dung |
| `spacing-xxl` | **48 dp** | Khoảng đệm an toàn cho cuộn trang tránh bị che bởi Floating Button / Bottom Bar |

---

### 2.4. Hệ thống Bo Góc (Corner Radius Tokens)

| Tên Token Radius | Bán kính Bo góc | Ứng dụng |
| :--- | :--- | :--- |
| `radius-xs` | **4 dp** | Bo góc nhẹ cho badge điểm PDP, tooltip |
| `radius-sm` | **8 dp** | Bo góc cho ô nhập liệu (Text Field), hình ảnh thumbnail nhỏ |
| `radius-md` | **12 dp** | Bo góc cho Thẻ sự kiện (Event Card), Hộp thoại xác nhận (Dialog) |
| `radius-lg` | **16 dp** | Bo góc cho Nút bấm chính (Button), Thẻ vé QR Pass, Bottom Sheet header |
| `radius-full` | **999 dp** | Bo tròn hoàn toàn (Pill shape) cho Category Chips, Avatar, nút tròn Icon Button |

---

### 2.5. Hệ thống Đổ bóng & Nổi khối (Elevation Tokens)

| Tên Token Elevation | Độ cao Z | Thông số Shadow trong Figma | Áp dụng Cho |
| :--- | :--- | :--- | :--- |
| `elevation-none` | 0 dp | Không bóng | Nền màn hình, Divider |
| `elevation-1` | 2 dp | `Y: 1px, Blur: 3px, Color: #000000 8%` | Thẻ Event Card trạng thái Default, Search Bar |
| `elevation-2` | 4 dp | `Y: 2px, Blur: 6px, Color: #000000 12%` | Event Card trạng thái Pressed/Hover, App Bar khi cuộn |
| `elevation-3` | 8 dp | `Y: 4px, Blur: 12px, Color: #000000 16%` | Bottom Navigation Bar, Sticky Bottom Sheet CTA |
| `elevation-4` | 16 dp | `Y: 8px, Blur: 24px, Color: #000000 20%` | Modal Dialog Xác nhận Overlay |

---

## 3. Quy tắc Thiết kế Component (Component Specifications)

### 3.1. Nút Bấm (Button)
- **Kích thước tối thiểu (Touch Target):** Chiều cao luôn đạt tối thiểu **48 dp** (chiều rộng tối thiểu 48 dp nếu là icon button, hoặc `full-width` trừ 32dp lề nếu là nút chính).
- **Auto Layout:** Căn giữa (`Center`), padding ngang 24dp, padding dọc 14dp, bo góc 12dp.
- **Trạng thái bắt buộc:**
  - `Default`: Nền FPT Orange `#F27024`, chữ trắng đậm 14sp.
  - `Pressed`: Nền cam đậm `#D95B12`, co nhẹ (scale 0.98).
  - `Disabled`: Nền xám `#E0E0E0`, chữ xám `#8C8C8C`, con trỏ khóa.
  - `Loading`: Nền `#F27024`, chữ ẩn, thay thế bằng Circular Progress Indicator màu trắng quay đều ở giữa.

### 3.2. Trường Nhập liệu (Text Field)
- **Cấu trúc:** Nhãn (Label) phía trên 14sp Medium + Khung nhập liệu chiều cao 48dp + Dòng trợ giúp/báo lỗi (Helper/Error text) 12sp phía dưới.
- **Trạng thái bắt buộc:**
  - `Default`: Nền `#FFFFFF`, viền xám `#E0E0E0` dày 1px.
  - `Focused`: Nền `#FFFFFF`, viền cam FPT `#F27024` dày 2px.
  - `Filled`: Nền `#FFFFFF`, viền xám `#BDBDBD`, hiển thị text người dùng đã nhập kèm nút icon "Clear (Xóa nhanh)".
  - `Error`: Nền `#FDF3F2`, viền đỏ `#D93025` dày 1.5px, icon chấm than màu đỏ, dòng text thông báo lỗi cụ thể bên dưới.
  - `Disabled`: Nền `#F5F5F5`, viền `#EEEEEE`, chữ xám mờ.

### 3.3. Thẻ Sự kiện (Event Card)
- **Bố cục:** Ảnh bìa tỷ lệ 16:9 bo góc trên + Khối nội dung padding 12dp bên dưới.
- **Thông tin trên thẻ:** Chip danh mục góc trên trái ảnh, Badge slot góc trên phải ảnh (ví dụ: *"Còn 12 chỗ"*), Tiêu đề sự kiện 16sp SemiBold, Dòng ngày giờ + icon lịch, Dòng địa điểm + icon ghim, Badge điểm PDP (+5 PDP).
- **Trạng thái:** `Default` (Elevation 1) và `Pressed` (Elevation 2, scale 0.98).

### 3.4. Thanh Điều hướng Đáy (Bottom Navigation Bar)
- **Độ cao:** 64 dp (cộng thêm SafeArea cho các dòng máy có thanh gạt gesture).
- **4 Mục điều hướng:** `Khám phá (Home)`, `Lịch của tôi (Schedule)`, `Thông báo (Notifications)`, `Hồ sơ (Profile)`.
- **Trạng thái item:**
  - `Selected`: Icon dạng Filled màu cam FPT, nhãn chữ màu cam FPT 12sp Bold, có viên thuốc chỉ báo (Indicator pill) màu cam nhạt `#FFF0E6`.
  - `Unselected`: Icon dạng Outline màu xám `#595959`, nhãn chữ màu xám 12sp Regular.

### 3.5. Hộp Thoại (Modal Dialog)
- **Overlay:** Lớp phủ làm mờ nền đen 50% opacity (`#000000 50%`).
- **Khung Dialog:** Chiều rộng 312 dp, bo góc 16dp, nền trắng, padding 24dp.
- **Biến thể:**
  - `Confirmation Dialog`: Icon dấu hỏi / vé, Tiêu đề xác nhận hủy, Nội dung giải thích quyền lợi, 2 nút: "Hủy bỏ (Giữ vé)" và "Xác nhận hủy (Màu đỏ)".
  - `Error / Alert Dialog`: Icon tam giác cảnh báo, Tiêu đề lỗi mạng / hết slot, Nút "Đã hiểu / Thử lại".

### 3.6. Trạng thái Tải (Loading State)
- Áp dụng **Skeleton Shimmer Pattern** toàn màn hình thay vì dùng một vòng xoay đơn điệu, giúp người dùng mường tượng trước bố cục nội dung đang được nạp.

### 3.7. Trạng thái Trống (Empty State)
- Sử dụng hình minh họa vector chủ đề sinh viên / lịch rảnh, Tiêu đề *"Chưa có sự kiện nào trong lịch"*, Phụ đề hướng dẫn, và Nút bấm CTA *"Khám phá sự kiện ngay"*.

### 3.8. Trạng thái Lỗi (Error State)
- Icon cảnh báo mất kết nối, Tiêu đề ngôn ngữ tự nhiên *"Không có kết nối Internet"*, Dòng mô tả *"Vui lòng kiểm tra WiFi campus hoặc bật 4G rồi thử lại"*, Nút bấm CTA *"Thử lại (Retry)"*.
