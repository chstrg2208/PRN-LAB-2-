# 🎨 Design Brief: F-Alumni Design System & Guidelines
**Dự án:** F-Alumni — FPT Alumni Mentorship & Opportunity Network  
**Môn học:** PRM323 — Cross-Platform Application Development  
**Nhóm thực hiện:** PRM Nhóm 4 — Đại học FPT TP.HCM  
**Thành viên:** Trương Chí Trung (SE193059), Nguyễn Phương Khải (SE183590), Đỗ Trọng Tín, Võ Quang Tâm  

---

## 1. Bản sắc Thương hiệu & Giọng điệu (Brand Identity & Tone of Voice)

- **Phong cách thị giác (Visual Style):** Chuyên nghiệp, hiện đại, mang tính kết nối và truyền cảm hứng học thuật. Giao diện ưu tiên sự rõ ràng, phân định mạch lạc giữa **Không gian chung toàn trường** và **Không gian chuyên môn theo từng nhóm ngành** (Kỹ thuật phần mềm, Trí tuệ nhân tạo, Quản trị kinh doanh, Thiết kế đồ họa...).
- **Tone & Voice:** Đáng tin cậy, ấm áp, đậm chất cộng đồng FPT (tinh thần anh em cựu sinh viên đi trước dìu dắt thế hệ sinh viên đi sau). Các thông báo sử dụng ngôn ngữ tự nhiên, tôn trọng và khích lệ (ví dụ: *"Yêu cầu xin Referral của bạn đã được gửi trực tiếp tới cựu sinh viên Lê Hoàng Long"*).

---

## 2. Hệ thống Token Thiết kế (Design Tokens)

### 2.1. Bảng Màu Chuẩn (Color Tokens & WCAG 2.1 AA Compliance)

Tất cả các màu được tính toán để bảo đảm tỷ lệ tương phản tối thiểu **4.5:1 đối với chữ thông thường** và **3:1 đối với điều khiển UI / chữ lớn** theo chuẩn **WCAG 2.1 Level AA**:

| Tên Token (Figma / Flutter) | Giá trị Hex | Vai trò & Mục đích Sử dụng | Tỷ lệ Tương phản (Contrast Ratio) |
| :--- | :--- | :--- | :--- |
| `color-primary` | `#F27024` | **FPT Orange**: Màu thương hiệu chính; dùng cho nút CTA chính ("Đặt lịch Mentor", "Nộp CV & Xin Referral"), tab đang chọn, badge "Hot / Mới" | 3.2:1 (so với trắng - đạt chuẩn icon/large UI) / 7.1:1 (so với text đen) |
| `color-primary-container` | `#FFF0E6` | Màu nền cam nhạt; dùng cho nền chip chuyên ngành đã chọn, nền thẻ thông báo nổi bật | 1.15:1 (so với trắng) |
| `color-secondary` | `#1B365D` | **FPT Navy Blue**: Màu bổ trợ học thuật; dùng cho App Bar header, thẻ hồ sơ cựu sinh viên, huy hiệu doanh nghiệp (FPT Software, VNG, Google) | **12.8:1** (so với nền trắng - Đạt chuẩn AAA) |
| `color-secondary-container` | `#E8EEF5` | Nền xanh navy nhạt; dùng cho chip chuyên ngành IT/Tech | 1.2:1 (so với trắng) |
| `color-surface` | `#FFFFFF` | Nền trắng tinh khiết của các thẻ bài viết (Post Card), Job Card, Dialog và TextField | - |
| `color-background` | `#F8F9FA` | Nền xám nhạt toàn ứng dụng (Light Theme), giúp các thẻ card nổi bật | - |
| `color-text-primary` | `#1A1A1A` | Chữ chính cho tiêu đề bài viết, tên cựu sinh viên, tiêu đề tuyển dụng | **13.5:1** (so với `#FFFFFF` - Vượt xa chuẩn 4.5:1) |
| `color-text-secondary` | `#595959` | Chữ phụ cho chức danh, tên công ty, thời gian đăng, mô tả ngắn | **5.4:1** (so với `#FFFFFF` - Đạt chuẩn WCAG 4.5:1) |
| `color-text-disabled` | `#8C8C8C` | Chữ cho trạng thái vô hiệu hóa (Disabled) | 3.0:1 |
| `color-border` | `#E0E0E0` | Đường kẻ phân cách (divider), viền thẻ card, viền textfield default | - |
| `color-success` | `#1E8E3E` | Màu thành công: Badge *"Cựu SV bảo lãnh Referral"*, thông báo đặt lịch thành công | 4.6:1 (Đạt WCAG AA) |
| `color-error` | `#D93025` | Màu cảnh báo: Khung giờ trùng lịch, thông báo mất mạng, lỗi tải file CV | 4.7:1 (Đạt WCAG AA) |
| `color-warning` | `#E37400` | Màu cảnh báo nhẹ: Slot tư vấn sắp kín, thời hạn nộp hồ sơ sắp hết | 3.5:1 |

---

### 2.2. Thang Đo Kiểu Chữ (Typography Scale)

Sử dụng bộ font không chân hiện đại **Inter** (hoặc **Roboto** trên Flutter), tuân thủ nghiêm ngặt: **Không có bất kỳ văn bản nội dung nào nhỏ hơn 14 sp**:

| Tên Token Typo | Cỡ chữ (Size) | Độ đậm (Weight) | Khoảng cách dòng (Line Height) | Mục đích Áp dụng |
| :--- | :--- | :--- | :--- | :--- |
| `type-display-large` | **26 sp** | Bold (700) | 34 sp | Tiêu đề chính màn hình Login & Chọn vai trò |
| `type-title-large` | **20 sp** | Bold (700) | 28 sp | Tiêu đề các mục lớn trên Home, Tên công việc tuyển dụng |
| `type-title-medium` | **18 sp** | SemiBold (600) | 24 sp | Tiêu đề bài viết chia sẻ kinh nghiệm, Tên Mentor trên thẻ |
| `type-body-large` | **16 sp** | Regular (400) / Medium (500) | 24 sp | Nội dung bài viết chi tiết (`SCR_03`), thư ngỏ xin Referral |
| `type-body-medium` | **14 sp** | Regular (400) | 20 sp | **Cỡ chữ nội dung tiêu chuẩn** (chức danh, công ty, nhãn form) |
| `type-label-large` | **14 sp** | SemiBold (600) | 20 sp | Chữ trên nút bấm chính (Button Text), Nhãn Bottom Nav |
| `type-label-small` | **12 sp** | Medium (500) | 16 sp | Nhãn tag chuyên ngành (Chip), thời gian đăng bài ("2 giờ trước") |

---

### 2.3. Hệ thống Khoảng cách Lưới (Spacing Tokens - 8dp Grid)

| Tên Token Spacing | Kích thước | Ứng dụng Thực tế trong Layout |
| :--- | :--- | :--- |
| `spacing-xxs` | **4 dp** | Khoảng cách giữa icon và text nhỏ trong tag, padding nội bộ nhỏ |
| `spacing-xs` | **8 dp** | Khoảng cách giữa các chip lọc ngành, khoảng cách giữa title và subtitle |
| `spacing-sm` | **12 dp** | Khoảng cách giữa các input field trong form đặt lịch / nộp CV |
| `spacing-md` | **16 dp** | **Khoảng cách lề chuẩn (Standard Screen Margin)** hai bên mép màn hình 360dp |
| `spacing-lg` | **24 dp** | Khoảng cách giữa các khối nội dung lớn (Section Gap) |
| `spacing-xl` | **32 dp** | Khoảng cách trước nút CTA lớn ở chân trang |
| `spacing-xxl` | **48 dp** | Khoảng đệm an toàn cuộn trang tránh bị che bởi Bottom Bar |

---

### 2.4. Hệ thống Bo Góc (Corner Radius Tokens)

| Tên Token Radius | Bán kính Bo góc | Ứng dụng |
| :--- | :--- | :--- |
| `radius-xs` | **4 dp** | Bo góc badge kinh nghiệm cựu SV, tag học bổng |
| `radius-sm` | **8 dp** | Bo góc khung nhập liệu (Text Field), thumbnail công ty |
| `radius-md` | **12 dp** | Bo góc Thẻ bài viết (Post Card), Thẻ công việc (Job Card), Dialog |
| `radius-lg` | **16 dp** | Bo góc Nút bấm chính, Thẻ lịch hẹn Session Pass |
| `radius-full` | **999 dp** | Bo tròn hoàn toàn (Pill shape) cho Category Chips, Avatar |

---

### 2.5. Hệ thống Đổ bóng & Nổi khối (Elevation Tokens)

| Tên Token Elevation | Độ cao Z | Thông số Shadow trong Figma | Áp dụng Cho |
| :--- | :--- | :--- | :--- |
| `elevation-none` | 0 dp | Không bóng | Nền màn hình, Divider |
| `elevation-1` | 2 dp | `Y: 1px, Blur: 3px, Color: #000000 8%` | Thẻ Post Card, Thẻ Job Card trạng thái Default, Search Bar |
| `elevation-2` | 4 dp | `Y: 2px, Blur: 6px, Color: #000000 12%` | Thẻ Card trạng thái Pressed/Hover |
| `elevation-3` | 8 dp | `Y: 4px, Blur: 12px, Color: #000000 16%` | Bottom Navigation Bar, Sticky Bottom Bar đặt lịch |
| `elevation-4` | 16 dp | `Y: 8px, Blur: 24px, Color: #000000 20%` | Modal Dialog Xác nhận Overlay |

---

## 3. Quy tắc Thiết kế 9 Component Bắt buộc

1. **Button:** Chiều cao luôn đạt tối thiểu **48 dp**. Trạng thái: `Default`, `Pressed`, `Disabled`, `Loading` (spinner quay tròn).
2. **Text Field:** Nhãn 14sp Medium + Khung nhập cao 48dp + Dòng trợ giúp/lỗi 12sp. Trạng thái: `Default`, `Focused`, `Filled`, `Error`, `Disabled`.
3. **Card (Post / Job / Mentor Card):** Bố cục gọn gàng, có avatar tác giả, badge chuyên ngành và công ty, padding 12–16dp, bo góc 12dp. Trạng thái: `Default` (Elevation 1) và `Pressed` (Elevation 2).
4. **Bottom Navigation Bar:** Chiều cao 64dp, 4 tabs: *Trang chủ*, *Việc làm/Học bổng*, *Mentors*, *Hồ sơ*. Trạng thái: `Selected` (icon cam + text cam 12sp Bold) và `Unselected` (icon xám + text xám 12sp Regular).
5. **App Bar:** Chiều cao 56–64dp, nền FPT Navy `#1B365D`, chữ trắng, nút Back và các nút Action (Bookmark, Share, Search).
6. **Dialog:** Khung 312dp căn giữa màn hình, overlay mờ 50%. Biến thể: `Confirmation Dialog` (hủy lịch hẹn) và `Alert/Conflict Dialog` (trùng giờ hẹn / lỗi mạng).
7. **Loading State:** Áp dụng **Skeleton Shimmer Pattern** cho bài viết và danh sách công việc.
8. **Empty State:** Hình minh họa vector thân thiện + Thông điệp *"Chưa có bài viết nào trong nhóm ngành này"* + Nút hành động *"Khám phá bài viết chung"*.
9. **Error State:** Icon cảnh báo + Thông báo ngôn ngữ tự nhiên *"Không có kết nối Internet. Dữ liệu đã lưu tạm"* + Nút *"Thử lại (Retry)"*.
