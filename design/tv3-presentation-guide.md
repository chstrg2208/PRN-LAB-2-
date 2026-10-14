# 🎤 Cẩm Nang Thuyết Trình & Vấn Đáp Dành Cho TV3 (Nguyễn Phương Khải)

> **Môn học:** PRM323 — Cross-Platform Application Development  
> **Người thực hiện:** **Nguyễn Phương Khải** — MSSV: **SE183590**  
> **Vai trò trong nhóm:** **TV3 — UI Design System & Screen Specifications Lead**  
> **Các tài liệu phụ trách chính:** [`design/DESIGN.md`](DESIGN.md), [`design/screen-spec.md`](screen-spec.md), [`design/design-decisions.md`](design-decisions.md)  
> **Các trang Figma đại diện:** **Page 02 (Wireframe)**, **Page 03 (Final UI)**, **Page 04 (Design System)**, **Page 05 (Components)**  

---

## 🕒 PHẦN 1: KỊCH BẢN THUYẾT TRÌNH (3 PHÚT TRONG TỔNG 10 PHÚT)

*Khi đến lượt TV3 trình bày, bạn sẽ chịu trách nhiệm chính từ **Slide 08 đến Slide 10**:*

---

### 📌 Slide 08: Wireframes & Final UI (Thời gian: ~1 phút)
* **Câu mở đầu:**  
  > *"Kính thưa thầy/cô và các bạn, em là Nguyễn Phương Khải, đảm nhận vai trò TV3 phụ trách UI Design System và Đặc tả màn hình của dự án F-Alumni. Ở slide 08, em xin trình bày quá trình chuyển dịch từ Wireframe Low-Fidelity sang Final UI High-Fidelity."*
* **Các luận điểm cốt lõi cần nói:**
  1. **Khung chuẩn thiết bị:** Toàn bộ 8 màn hình được nhóm dựng chuẩn xác trên kích thước logic di động **360 × 800 dp** (dựa trên thiết bị của persona Trương Chí Trung là Samsung Galaxy A54).
  2. **Phân cấp thị giác (Visual Hierarchy):** Giao diện chia rõ 2 tầng: App Bar và Header mang sắc xanh Navy đại diện cho sự uy tín học thuật; trong khi các nút kêu gọi hành động (CTA) như *'Đặt lịch Mentor'* hay *'Nộp CV xin Referral'* sử dụng sắc cam FPT rực rỡ để dẫn dắt hành vi người dùng theo quy luật Fitts.
  3. **Độ phủ trạng thái toàn diện:** Tại trang Final UI (Figma Page 03), nhóm không chỉ vẽ màn hình khi có dữ liệu (Populated) mà thiết kế đầy đủ các biến thể trạng thái: **Skeleton Shimmer** khi đang tải dữ liệu, **Empty State** khi bộ lọc không có kết quả, và **Error Banner** bảo toàn form khi mất mạng.

---

### 📌 Slide 09: Design System & 9 Reusable Components (Thời gian: ~1 phút)
* **Câu chuyển ý:**  
  > *"Để đảm bảo tính nhất quán trên toàn bộ 8 màn hình và tối ưu cho việc lập trình Flutter ở Lab 3, em đã thiết lập hệ thống Design System hoàn chỉnh trên Figma Page 04 và Page 05."*
* **Các luận điểm cốt lõi cần nói:**
  1. **Khai báo Design Tokens bằng Figma Variables:** Nhóm tuyệt đối không gán cứng mã màu. Toàn bộ màu sắc (`color-primary`, `color-secondary`, `color-tertiary`), thang kiểu chữ (`Inter` và `Hanken Grotesk`), khoảng cách lề lưới 8dp (`4, 8, 12, 16, 24, 32, 48 dp`), bán kính bo góc và độ cao bóng mờ đều được quản lý bằng Variables.
  2. **Thư viện 9 nhóm Components tái sử dụng (Figma Page 05):**
     * Đủ 9 nhóm theo yêu cầu đề bài: *Button, Text Field, Card, Bottom Navigation, App Bar, Dialog, Loading (Shimmer), Empty, Error*.
     * **100% dựng bằng Auto Layout** có padding, constraints co giãn linh hoạt.
     * Thiết lập đầy đủ các **Variants**: Trạng thái *Default, Hover/Pressed, Disabled* và đặc biệt là *Loading State (Spinner)* trên các nút Submit.

---

### 📌 Slide 10: Accessibility (WCAG 2.1 AA) & Responsiveness (Thời gian: ~1 phút)
* **Các luận điểm cốt lõi cần nói:**
  1. **Tương phản màu sắc vượt trội:** Nhóm đo lường nghiêm ngặt bằng Stark và WebAIM. Chữ chính trên nền trắng đạt **13.5:1** (vượt chuẩn AAA 7:1); chữ phụ đạt **5.4:1** (vượt chuẩn AA 4.5:1); màu nút chính đạt **3.2:1**.
  2. **Vùng chạm chuẩn nhân trắc học:** Mọi nút bấm, icon button và chip chọn giờ hẹn đều đạt diện tích cảm ứng tối thiểu **48 × 48 dp** theo chuẩn **WCAG 2.5.5**, phù hợp thói quen sử dụng điện thoại bằng một ngón tay cái của sinh viên khi di chuyển.
  3. **Cỡ chữ nội dung an toàn:** Nhóm tuân thủ nghiêm ngặt quy định: Không có bất kỳ văn bản nội dung nào nhỏ hơn **14 sp**.
  4. **Khả năng đáp ứng đa kích thước (Responsive):** Sử dụng thuộc tính `Horizontal: Fill Container` trong Auto Layout. Khi màn hình co giãn từ **360 dp** lên **412 dp**, các thẻ Card và nút bấm tự động giãn ngang cân đối mà không bao giờ bị tràn lề hay vỡ chữ.

---

## 💻 PHẦN 2: KỊCH BẢN LIVE DEMO TRÊN FIGMA (BƯỚC 5 CỦA BUỔI ĐÁNH GIÁ)

*Khi đến phần Live Demo kiểm tra Components & Tokens, bạn thực hiện các thao tác sau trên màn hình máy chiếu:*

1. **Mở Figma Page 04 (Design System):**
   * Mở bảng **Figma Variables** bên tay phải, chỉ cho giảng viên thấy các bộ Variables: `Color`, `Spacing`, `Radius`, `Elevation`.
   * *Nói:* *"Thưa thầy/cô, toàn bộ màu sắc và khoảng cách đều là Token liên kết động chứ không hard-code."*
2. **Mở Figma Page 05 (Components):**
   * Bấm chọn component `Button`, mở bảng Variants bên phải, chuyển đổi qua lại giữa `State: Default` → `State: Loading` (hiện spinner) → `State: Disabled`.
   * Bấm chọn component `JobCard` và chỉ ra huy hiệu *"Cựu SV bảo lãnh Referral"* được cấu thành bằng Auto Layout có icon và nhãn chữ đi kèm (Dual-coding).
3. **Mở Figma Page 03 (Final UI) để chứng minh Responsive:**
   * Chọn một màn hình chuẩn (ví dụ `SCR_04` hoặc `SCR_02`), kéo giãn khung chiều ngang từ **360 dp** sang **412 dp**.
   * Chỉ cho giảng viên thấy: Danh sách thẻ card tự động giãn ngang lấp đầy container, khoảng cách lề hai bên cố định đúng 16dp.

---

## ❓ PHẦN 3: BỘ CÂU HỎI VẤN ĐÁP TRỌNG TÂM CỦA GIẢNG VIÊN DÀNH CHO TV3

---

### ❓ Câu 1: "Nếu bây giờ em đổi mã màu chính (color-primary) hoặc khoảng cách margin, những màn hình nào sẽ tự động thay đổi?"
* **Câu trả lời chuẩn mực của Khải:**  
  > *"Dạ thưa thầy/cô, do 100% 8 màn hình ở Page 03 đều sử dụng Figma Variables liên kết động:  
  > - Nếu em đổi token `color-secondary` (FPT Orange `#F27024`), toàn bộ các nút CTA chính trên 8 màn hình (như nút 'Đặt lịch Mentor' ở `SCR_03`, nút 'Nộp CV' ở `SCR_05`), tab đang chọn ở Bottom Navigation và các badge nổi bật sẽ **đồng loạt tự động đổi màu ngay lập tức**.  
  > - Tương tự, nếu em đổi token `spacing-md` từ 16dp sang 20dp, toàn bộ lề mép ngoài của cả 8 màn hình sẽ tự động cập nhật mà không cần chỉnh sửa thủ công từng frame."*

---

### ❓ Câu 2: "Tại sao nhóm em lại từ chối (REJECT) gợi ý của AI, và lý do học thuật là gì?" *(Câu hỏi số 3 trong Rubric)*
* **Câu trả lời chuẩn mực của Khải:**  
  > *"Dạ thưa thầy/cô, trong quá trình làm việc với AI, trợ lý AI từng đề xuất nhóm nên tích hợp một Chatbot AI tự động trả lời thay cho cựu sinh viên và tự động chấm điểm CV để tăng tốc độ phản hồi.  
  > Tuy nhiên, nhóm em đã **hoàn toàn TỪ CHỐI (REJECT)** đề xuất này vì:  
  > 1. Theo **Heuristic #2 (Match between system and real world)** và nhu cầu của Persona Trương Chí Trung: Giá trị cốt lõi nhất của F-Alumni là **sự kết nối con người chân thực (Human Connection)** giữa sinh viên và các anh chị cựu sinh viên đi trước cùng trường FPT.  
  > 2. Điều sinh viên cần nhất là **suất bảo lãnh Referral nội bộ uy tín** vào các doanh nghiệp như FPT Software hay VNG. Chatbot AI hoàn toàn không thể cấp thư bảo lãnh và làm mất đi sự tin cậy của nền tảng. Do đó, nhóm giữ vững quyết định tư vấn 1-1 trực tiếp qua Google Meet."*

---

### ❓ Câu 3: "Làm thế nào em chứng minh được layout của em không bị vỡ khi hiển thị trên màn hình rộng 412 dp?" *(Câu hỏi số 6 trong Rubric)*
* **Câu trả lời chuẩn mực của Khải:**  
  > *"Dạ thưa thầy/cô, nhóm đã kiểm tra bằng 2 cơ chế:  
  > 1. Trong Figma, toàn bộ các thẻ Card, Search Bar và Button đều được thiết lập thuộc tính Auto Layout `Horizontal Resizing: Fill Container`. Khoảng đệm lề trái và phải được neo cố định là `spacing-md` (16 dp). Khi kéo frame từ 360 dp sang 412 dp, các card tự động co giãn theo chiều ngang mà không bị tràn chữ hay bể khung.  
  > 2. Trong bản đặc tả Flutter Handoff, nhóm quy định sử dụng `Padding` bao ngoài và thẻ `Card` có chiều rộng `double.infinity`, giúp Flutter tự động render hoàn hảo trên mọi kích thước màn hình Android từ dòng máy tiêu chuẩn (360dp) đến các dòng máy cao cấp như Samsung S24 hay Google Pixel (412dp)."*

---

### ❓ Câu 4: "Em kiểm tra độ tương phản màu sắc (Contrast Ratio) như thế nào để khẳng định đạt chuẩn WCAG 2.1 AA?"
* **Câu trả lời chuẩn mực của Khải:**  
  > *"Dạ thưa thầy/cô, em đã dùng plugin Stark trên Figma và công cụ WebAIM Contrast Checker:  
  > - Chữ chính `#111827` trên nền trắng đạt **13.5:1**, vượt xa chuẩn AAA tối thiểu 7:1.  
  > - Chữ phụ `#595959` trên nền trắng đạt **5.4:1**, vượt chuẩn AA tối thiểu 4.5:1.  
  > - Nút hành động màu cam `#F27024` trên nền trắng đạt **3.2:1**, vượt mức quy định 3:1 dành cho các thành phần điều khiển giao diện (UI Controls).  
  > - Ngoài ra, nhóm luôn áp dụng nguyên tắc **Dual-coding**: Các trạng thái quan trọng như đơn ứng tuyển hay lịch hẹn luôn có cả **icon biểu tượng và nhãn văn bản đi kèm**, không bao giờ truyền đạt ý nghĩa bằng màu sắc đơn thuần."*
