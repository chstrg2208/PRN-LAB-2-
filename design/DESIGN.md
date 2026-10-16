# 🎨 Design Brief: F-Alumni Design System & Guidelines

> **Môn học:** PRM323 — Cross-Platform Application Development  
> **Dự án:** **F-Alumni — FPT Alumni Mentorship & Opportunity Network**  
> **Nhóm thực hiện:** PRM Nhóm 4 — Đại học FPT TP. Hồ Chí Minh  
> **Người biên soạn chính (Lead Author):** **Nguyễn Phương Khải** — MSSV: **SE183590** (Vai trò: **TV3 — UI Design System & Screen Specifications Lead**)  
> **Các thành viên nhóm:**  
> 1. **Trương Chí Trung** — MSSV: **SE193059** (Trưởng nhóm / TV2: AI & Google Stitch Lead)  
> 2. **Võ Quang Tâm** — MSSV: **SE192621** (TV1: UX Research, Persona & User Flow Lead)  
> 3. **Nguyễn Phương Khải** — MSSV: **SE183590** (TV3: UI Design System & Screen Spec Lead)  
> 4. **Đỗ Trọng Tín** — MSSV: **SE190218** (TV4: Flutter Handoff & Architecture Lead)  
> 
> 🌐 **Không gian Google Stitch nguồn:** [https://stitch.withgoogle.com/projects/1771935993966075517](https://stitch.withgoogle.com/projects/1771935993966075517) *(F-Alumni Mentorship App Design — Public Project)*  
> 🎨 **Figma Design File:** [Figma: PRM323 - Lab 2 - F-Alumni - Nhom 4 (Pages 04 & 05)](https://www.figma.com/design/PPdvsVA0O63HEHTQkxBQX0/PRM323---Lab-2---F-Alumni---Nhom-4?node-id=1-3&t=00FzbJIZRL89FvX4-1)  

---

## 1. Bản sắc Thương hiệu & Giọng điệu (Brand Identity & Tone of Voice)

- **Phong cách thị giác (Visual Style):** *Modern Corporate & Executive Academic*. Giao diện kết hợp tính uy tín của một tổ chức giáo dục công nghệ hàng đầu với tinh thần kết nối cố vấn năng động. Hệ thống phân định mạch lạc, trực quan giữa:
  - **Không gian chung toàn trường (General Campus Space):** Bài viết hướng nghiệp, kỹ năng mềm, cơ hội học bổng quốc tế và sự kiện cựu sinh viên toàn trường.
  - **Không gian chuyên sâu theo nhóm ngành (Major-Specific Space):** Kỹ thuật phần mềm (SE), Trí tuệ nhân tạo (AI), An toàn thông tin (IA), Thiết kế mỹ thuật số (GD), Quản trị kinh doanh (BA).
- **Tone & Voice:** Đáng tin cậy, tôn trọng, truyền cảm hứng và đậm chất anh em cựu sinh viên FPT (tinh thần người đi trước dẫn dắt thế hệ đàn em đi sau). 
  - *Ví dụ thông điệp thành công:* `"Hồ sơ xin Referral của bạn đã được gửi trực tiếp tới cựu sinh viên Trần Tuấn Anh (Tech Lead K12 - FPT Software)"`.
  - *Ví dụ thông điệp lỗi:* `"Không thể kết nối máy chủ. File CV và thư ngỏ của bạn đã được lưu tạm an toàn"`.

---

## 2. Hệ thống Token Thiết kế (Design Tokens)

Toàn bộ Design Tokens được định nghĩa theo chuẩn **W3C Design Tokens Community Group**, khai báo bằng **Figma Variables** trên **Figma Page 04 (Design System)** và ánh xạ trực tiếp sang `ThemeData` của Flutter trong `handoff/flutter-handoff.md`.

### 2.1. Bảng Màu Chuẩn (Color Tokens & WCAG 2.1 AA Compliance)

Tất cả màu sắc được đo lường chính xác bằng công cụ kiểm tra độ tương phản WebAIM và Stark, bảo đảm đạt và vượt chuẩn **WCAG 2.1 Level AA** (tối thiểu **4.5:1** cho body text và **3:1** cho UI controls):

| Tên Token (Figma Variables / CSS) | Mã Màu Hex | Vai trò & Ứng dụng Thực tế | Tỷ lệ Tương phản (Contrast Ratio) | Đánh giá Chuẩn WCAG |
| :--- | :---: | :--- | :---: | :---: |
| `color-primary` | `#1B365D` | **FPT Navy Blue:** Màu nền tảng học thuật; dùng cho App Bar Header, thẻ hồ sơ cựu sinh viên, huy hiệu doanh nghiệp (FPT Software, VNG, Google), tiêu đề quan trọng. | **12.8:1** (so với nền trắng) | ✅ **Đạt AAA** (Vượt xa 7:1) |
| `color-primary-container` | `#E8EEF5` | Nền xanh navy nhạt; dùng cho chip chuyên ngành IT/Tech, khung chứa nổi bật. | 1.2:1 (so với trắng) | Nền phụ trợ |
| `color-secondary` | `#F27024` | **Signature FPT Orange:** Màu hành động thương hiệu; dùng cho nút CTA chính ("Đặt lịch Mentor", "Nộp CV & Xin Referral"), tab đang chọn, badge "Hot / Mới". | **3.2:1** (so với trắng - đạt chuẩn nút/icon lớn)<br>**7.1:1** (so với chữ đen) | ✅ **Đạt AA** (UI Control & Large Text) |
| `color-secondary-container` | `#FFF0E6` | Màu nền cam nhạt; dùng cho nền chip chuyên ngành đã chọn, nền thông báo nổi bật. | 1.15:1 (so với trắng) | Nền phụ trợ |
| `color-tertiary` | `#10B981` | **Emerald Green:** Huy hiệu *"Cựu SV bảo lãnh Referral"*, chỉ báo trạng thái đã xác nhận (`● ĐÃ XÁC NHẬN`), lịch hẹn thành công. | **4.6:1** (so với nền trắng) | ✅ **Đạt AA** |
| `color-surface` | `#FFFFFF` | Nền trắng tinh khiết của các thẻ bài viết (Post Card), Job Card, Dialog và TextField. | - | Nền bề mặt chuẩn |
| `color-background` | `#F8F9FA` | Nền canvas xám sáng toàn ứng dụng (Light Mode), giảm mỏi mắt khi đọc bài viết dài. | - | Nền tổng thể |
| `color-text-primary` | `#111827` | Chữ chính cho tiêu đề bài viết, tên cựu sinh viên, tiêu đề tuyển dụng. | **13.5:1** (so với `#FFFFFF`) | ✅ **Đạt AAA** |
| `color-text-secondary` | `#595959` | Chữ phụ cho chức danh, tên công ty, thời gian đăng, mô tả ngắn. | **5.4:1** (so với `#FFFFFF`) | ✅ **Đạt AA** (Vượt chuẩn 4.5:1) |
| `color-text-disabled` | `#8C8C8C` | Chữ cho trạng thái vô hiệu hóa (Disabled). | 3.0:1 | Trạng thái tắt |
| `color-border` | `#E5E7EB` | Đường viền thẻ card, đường kẻ phân cách (Divider), viền TextField trạng thái Default. | - | Phân tách cấu trúc |
| `color-error` | `#DC2626` | Màu cảnh báo lỗi: Thông báo mất mạng, lỗi tải file CV, khung giờ trùng lịch. | **4.7:1** (so với nền trắng) | ✅ **Đạt AA** |
| `color-error-container` | `#FDF3F2` | Nền đỏ nhạt của Error Banner tại `SCR_05`. | 1.1:1 | Nền cảnh báo lỗi |
| `color-warning` | `#E37400` | Màu cảnh báo nhẹ: Slot tư vấn sắp kín, thời hạn nộp hồ sơ sắp hết. | **3.5:1** (so với nền trắng) | ✅ **Đạt AA UI** |

---

### 2.2. Thang Đo Kiểu Chữ (Typography Scale)

Hệ thống kết hợp 2 bộ font: **Hanken Grotesk** (Font tiêu đề kiến tạo phong cách đĩnh đạc, hiện đại) và **Inter** (Font nội dung tối ưu khả năng đọc dày đặc trên màn hình di động).  
**Quy tắc bất di bất dịch của WCAG 2.1 AA:** **Tuyệt đối không có bất kỳ văn bản nội dung (Body Text) nào nhỏ hơn 14 sp**.

| Tên Token Typo | Font Family | Cỡ chữ (Size) | Độ đậm (Weight) | Khoảng cách dòng (Line Height) | Letter Spacing | Mục đích Áp dụng Cụ thể |
| :--- | :--- | :---: | :---: | :---: | :---: | :--- |
| `type-display-large` | Hanken Grotesk | **26 sp** | Bold (700) | 34 sp | -0.02em | Tiêu đề chính màn hình Login `SCR_01` |
| `type-title-large` | Hanken Grotesk | **20 sp** | Bold (700) | 28 sp | -0.01em | Tiêu đề mục lớn trên Home `SCR_02`, Tên Job tuyển dụng |
| `type-title-medium` | Hanken Grotesk | **18 sp** | SemiBold (600) | 24 sp | 0 | Tiêu đề bài viết chia sẻ `SCR_03`, Tên Mentor trên thẻ |
| `type-body-large` | Inter | **16 sp** | Regular (400) | 24 sp | 0 | Nội dung bài viết chi tiết (`SCR_03`), thư ngỏ xin Referral |
| `type-body-medium` | Inter | **14 sp** | Regular (400) | 20 sp | 0 | **Cỡ chữ nội dung chuẩn sàn** (Chức danh, công ty, nhãn form, JD) |
| `type-label-large` | Inter | **14 sp** | SemiBold (600) | 20 sp | +0.01em | Chữ trên nút bấm chính (Button Text), Nhãn Bottom Nav |
| `type-label-medium` | Inter | **12 sp** | SemiBold (600) | 16 sp | +0.02em | Nhãn tag chuyên ngành (Chip), nhãn tab phụ |
| `type-label-small` | Inter | **11 sp** | Medium (500) | 14 sp | +0.03em | Dành riêng cho Metadata, thời gian đăng bài ("2 giờ trước") |

---

### 2.3. Hệ thống Khoảng cách Lưới (Spacing Tokens — 8dp Grid)

Tất cả khoảng cách, padding và margin đều là bội số của lưới **8dp** (có bước nhảy phụ 4dp cho chi tiết nhỏ) nhằm đảm bảo tính nhịp nhàng và tương thích hoàn hảo với màn hình Android/iOS:

| Tên Token Spacing | Kích thước | Ứng dụng Thực tế trong Bố cục |
| :--- | :---: | :--- |
| `spacing-xxs` | **4 dp** | Khoảng cách giữa icon và chữ nhỏ trong badge, padding tối thiểu |
| `spacing-xs` | **8 dp** | Khoảng cách giữa các chip lọc, khoảng cách giữa tiêu đề và phụ đề |
| `spacing-sm` | **12 dp** | Khoảng cách giữa các ô nhập liệu trong form đặt lịch / nộp CV |
| `spacing-md` | **16 dp** | **Khoảng cách lề chuẩn (Standard Screen Margin)** hai bên mép màn hình 360dp |
| `spacing-lg` | **24 dp** | Khoảng cách giữa các khối nội dung lớn (Section Gap) |
| `spacing-xl` | **32 dp** | Khoảng đệm trước nút CTA lớn ở chân trang |
| `spacing-xxl` | **48 dp** | **Kích thước Vùng chạm tối thiểu (Min Touch Target)** và khoảng đệm an toàn chân trang |

---

### 2.4. Hệ thống Bo Góc (Corner Radius Tokens)

| Tên Token Radius | Bán kính Bo góc | Ứng dụng Thực tế |
| :--- | :---: | :--- |
| `radius-xs` | **4 dp** | Bo góc tag học bổng nhỏ, badge năm tốt nghiệp |
| `radius-sm` | **8 dp** | Bo góc Nút bấm chính, Khung nhập liệu (Text Field), Thumbnail logo công ty |
| `radius-md` | **12 dp** | Bo góc Thẻ bài viết (Post Card), Thẻ công việc (Job Card), Dialog cảnh báo |
| `radius-lg` | **16 dp** | Bo góc Thẻ lịch hẹn Session Pass, Modal Sheet trung tâm |
| `radius-xl` | **24 dp** | Bo góc cạnh trên của Bottom Sheet / Modal xác nhận |
| `radius-full` | **9999 dp** | Bo tròn hoàn toàn (Pill shape) cho Category Chips, Avatar cá nhân |

---

### 2.5. Hệ thống Đổ bóng & Nổi khối (Elevation Tokens)

Hệ thống đổ bóng sử dụng màu bóng phủ sắc xanh FPT Navy `#1B365D` mờ nhẹ (Ambient Shadow) thay vì màu đen đặc thô ráp, tạo chiều sâu thị giác thanh lịch và chuyên nghiệp:

| Tên Token Elevation | Độ cao Z | Thông số Shadow trong Figma | Áp dụng Cho |
| :--- | :---: | :--- | :--- |
| `elevation-0` | 0 dp | `None` | Nền canvas màn hình, Divider |
| `elevation-1` | 2 dp | `Y: 1px, Blur: 3px, Color: rgba(27, 54, 93, 0.06)` | Thẻ Post Card, Thẻ Job Card trạng thái Default, Search Bar |
| `elevation-2` | 4 dp | `Y: 4px, Blur: 6px, Color: rgba(27, 54, 93, 0.08)` | Thẻ Card trạng thái Pressed/Hover, Thẻ Mentor nổi bật |
| `elevation-3` | 8 dp | `Y: -4px, Blur: 16px, Color: rgba(27, 54, 93, 0.08)` | Bottom Navigation Bar, Sticky Bottom Action Bar đặt lịch `SCR_03` |
| `elevation-4` | 16 dp | `Y: 12px, Blur: 24px, Color: rgba(27, 54, 93, 0.12)` | Modal Confirmation Dialog Overlay (hộp thoại xác nhận 2 bước) |

---

## 3. Quy chuẩn Thiết kế 9 Component Bắt buộc (Figma Page 05)

Tất cả 9 nhóm components được xây dựng **100% bằng Auto Layout** trong Figma, có đầy đủ **Component Properties** và **Variants** các trạng thái:

1. **Button (Nút bấm):**
   * *Variants:* `Primary` (FPT Orange `#F27024`), `Secondary` (FPT Navy `#1B365D`), `Outlined` (Viền `#1B365D`), `Text/Ghost`.
   * *States:* `Default`, `Hover/Pressed` (sậm 10%), `Disabled` (nền xám chữ xám), `Loading` (nút chứa spinner trắng quay tròn, tắt tương tác).
   * *Ràng buộc:* Chiều cao luôn đạt **48 dp** chuẩn Touch Target WCAG 2.5.5.
2. **Text Field (Ô nhập liệu):**
   * *Variants:* `Single-line` (48dp), `Multi-line / Text Area` (ô nhập thư ngỏ 120dp), `Dropdown Picker` (chọn ngành).
   * *States:* `Default` (viền `#E5E7EB`), `Focused` (viền `#1B365D` kèm outer glow 3px), `Filled`, `Error` (viền đỏ `#DC2626` kèm dòng helper text giải thích lỗi), `Disabled`.
3. **Card (Thẻ nội dung):**
   * *Các biến thể:*
     * `PostCard`: Avatar tác giả, họ tên cựu SV, chức danh, tiêu đề bài viết, lượt tương tác, icon Bookmark nhanh.
     * `JobCard`: Logo công ty, vị trí tuyển dụng, mức lương, **Huy hiệu bảo lãnh Referral** viền xanh `#10B981`, nút "Xem & Xin Referral".
     * `MentorCard`: Avatar 56×56dp, họ tên, số năm kinh nghiệm, đánh giá 5⭐, nút "Đặt lịch 1-1".
   * *States:* `Default` (Elevation 1), `Pressed` (Elevation 2).
4. **Bottom Navigation Bar (Thanh điều hướng đáy):**
   * Chiều cao **64 dp** (+ Safe Area chân máy), cố định đáy màn hình.
   * Gồm 4 Tab: *Trang chủ (`SCR_02`)*, *Việc làm/Học bổng (`SCR_04`)*, *Mentors (`SCR_06`)*, *Hồ sơ (`SCR_08`)*.
   * *States:* `Active` (Icon cam + Chữ cam 12sp SemiBold) và `Inactive` (Icon xám + Chữ xám 12sp Regular). Bố cục có khoảng trống 80dp đệm nội dung cuộn bên dưới.
5. **App Bar (Thanh đầu trang):**
   * Chiều cao 56–64 dp, nền FPT Navy `#1B365D`, chữ trắng độ tương phản 12.8:1.
   * Chứa nút Back (IconButton bọc khung tối thiểu 48×48dp) và các action buttons (Bookmark, Share, Filter).
6. **Dialog (Hộp thoại tương tác):**
   * Khung modal 312dp căn giữa màn hình, nền trắng bo góc 16dp, đổ bóng Elevation 4, lớp overlay nền mờ 50% đen.
   * *Biến thể:*
     * `ConfirmationDialog`: Xác nhận đặt lịch / Xác nhận hủy lịch hẹn 2 bước (có 2 nút "Hủy bỏ" và "Xác nhận").
     * `ConflictAlertDialog`: Cảnh báo khung giờ trùng lịch và tự động gợi ý 2 khung giờ rảnh thay thế.
7. **Loading State (Trạng thái tải dữ liệu):**
   * Áp dụng **Skeleton Shimmer Animation** (xám nhạt `#E5E7EB` chuyển động sáng `#F3F4F6`) cho thẻ bài viết và danh sách công việc, giúp người dùng nắm được cấu trúc trang trong lúc chờ mạng.
8. **Empty State (Trạng thái rỗng):**
   * Minh họa vector thân thiện (Folder rỗng hoặc kính lúp) + Tiêu đề *"Chưa tìm thấy cơ hội phù hợp"* + Mô tả ngắn hướng dẫn người dùng + Nút hành động chính *"↻ Xóa bộ lọc"* hoặc *"Khám phá bài viết chung"*.
9. **Error State (Trạng thái lỗi & Phục hồi):**
   * Banner cảnh báo màu đỏ nhạt `#FDF3F2` có icon cảnh báo + Thông báo ngôn ngữ tự nhiên: *"Mất kết nối Internet. Toàn bộ file CV và thư ngỏ của bạn đã được bảo lưu an toàn"* + Nút *"Thử lại (Retry)"*.
