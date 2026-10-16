# ⚖️ Top 10 Design Decisions & Accessibility Checklist

> **Môn học:** PRM323 — Cross-Platform Application Development  
> **Dự án:** **F-Alumni — FPT Alumni Mentorship & Opportunity Network**  
> **Nhóm thực hiện:** PRM Nhóm 4 — Đại học FPT TP. Hồ Chí Minh  
> **Người biên soạn chính (Lead Author):** **Nguyễn Phương Khải** — MSSV: **SE183590** (Vai trò: **TV3 — UI Design System & Screen Specifications Lead**)  
> 
> 🌐 **Google Stitch Project:** [https://stitch.withgoogle.com/projects/1771935993966075517](https://stitch.withgoogle.com/projects/1771935993966075517)  
> 🎨 **Figma Deliverable:** [Figma: PRM323 - Lab 2 - F-Alumni (Pages 04 & 05)](https://www.figma.com/design/PRM323-F-Alumni)  

---

## 1. Top 10 Quyết định Thiết kế Cốt lõi (Top 10 Core Design Decisions)

Mọi quyết định thiết kế trong **F-Alumni** đều được xây dựng dựa trên sự kết hợp chặt chẽ giữa: **10 Usability Heuristics của Jakob Nielsen**, **Tiêu chuẩn tiếp cận W3C WCAG 2.1**, **Nhu cầu thực tế của Persona Trương Chí Trung**, và **Tư duy phản biện độc lập đối với các gợi ý của AI (Google Stitch & LLM)**:

---

### Quyết định 1: Phân tách rõ rệt giữa "Không gian chung toàn trường" và "Nhóm ngành chuyên sâu" trên `SCR_02`
- **Mô tả thiết kế:** Bố trí thanh Tab Switcher ngay đầu màn hình Home Feed để sinh viên chuyển đổi tức thời giữa:
  - *Tab "🌐 Không gian chung":* Bài viết hướng nghiệp, học bổng trao đổi quốc tế, tin tức toàn trường.
  - *Tab "💻 Nhóm ngành IT / Software":* Các bài chia sẻ chuyên môn sâu về lập trình, ôn luyện phỏng vấn kỹ thuật.
- **Lập luận học thuật:** Căn cứ theo **Jakob Nielsen Heuristic #7 (Flexibility and efficiency of use)** và bối cảnh sử dụng của Persona Trung. Sinh viên không bị "bội thực thông tin" bởi các ngành nghề khác, nhưng vẫn giữ được sợi dây kết nối văn hóa với toàn thể cộng đồng cựu sinh viên FPT.

---

### Quyết định 2: Sử dụng Sticky Bottom Action Bar cho nút "Đặt lịch tư vấn 1-1 với Mentor" tại `SCR_03`
- **Mô tả thiết kế:** Nút CTA chính "Đặt lịch tư vấn với Mentor" được cố định ở đáy màn hình với chiều cao chuẩn 48dp, nổi bật trên nền trắng có viền và đổ bóng Elevation 3.
- **Lập luận học thuật:** Căn cứ theo **Heuristic #1 (Visibility of system status)** và quy luật Fitts (Fitts's Law). Sinh viên sau khi đọc xong bài viết truyền cảm hứng của Mentor có thể bấm kết nối ngay lập tức mà không phải cuộn ngược trang tìm kiếm thông tin liên hệ.

---

### Quyết định 3: Thiết lập Huy hiệu Bảo lãnh "Alumni Referral" trên Thẻ Việc làm `SCR_04`
- **Mô tả thiết kế:** Các cơ hội việc làm/OJT do chính cựu sinh viên đứng ra nhận CV và bảo lãnh nội bộ được gắn huy hiệu xanh/vàng nổi bật: *"Cựu SV bảo lãnh Referral"*.
- **Lập luận học thuật:** Căn cứ theo **Heuristic #2 (Match between system and the real world)**. Trong văn hóa tuyển dụng công nghệ, hồ sơ có Referral nội bộ từ nhân viên chính thức có tỷ lệ được gọi phỏng vấn cao hơn 80% so với nộp đại trà qua các trang tuyển dụng bên ngoài.

---

### Quyết định 4: Cơ chế Bảo lưu 100% Dữ liệu Form & File CV khi Lỗi Mạng tại `SCR_05`
- **Mô tả thiết kế:** Khi mất mạng lúc gửi đơn xin Referral, ứng dụng hiển thị Error Banner màu đỏ nhạt `#FDF3F2` kèm nút "Thử lại (Retry)" mà **tuyệt đối không xóa nội dung thư ngỏ và file CV đã chọn**.
- **Lập luận học thuật:** Căn cứ theo **Heuristic #9 (Help users recognize, diagnose, and recover from errors)**. Mạng WiFi campus FPT hay bị nghẽn cục bộ vào giờ tan tiết. Việc bảo lưu toàn bộ dữ liệu giúp sinh viên gửi lại ngay khi có kết nối mà không phải gõ lại tâm thư gửi cựu sinh viên.

---

### Quyết định 5: Quy trình Hủy lịch Hẹn tư vấn 2 bước có Confirmation Dialog tại `SCR_07` / `SCR_08`
- **Mô tả thiết kế:** Khi sinh viên chạm vào "Hủy lịch tư vấn này", hệ thống không hủy ngay mà mở Modal Dialog giải thích: *"Thao tác này sẽ mở lại khung giờ rảnh của Mentor cho các bạn sinh viên khác đang có nhu cầu"*.
- **Lập luận học thuật:** Căn cứ theo **Heuristic #3 (User control and freedom)** và **Heuristic #5 (Error prevention)**. Bảo vệ người dùng khỏi việc chạm nhầm làm mất lịch hẹn quý giá với các cựu sinh viên bận rộn.

---

### Quyết định 6: Cơ chế Tự động Đề xuất Giờ thay thế khi Trùng Lịch (Conflict Resolution) tại `SCR_07`
- **Mô tả thiết kế:** Nếu một khung giờ tư vấn vừa bị sinh viên khác đặt trước, hệ thống hiển thị thông báo nhẹ nhàng và tự động tô sáng 2 khung giờ rảnh kế tiếp của Mentor.
- **Lập luận học thuật:** Căn cứ theo **Heuristic #5 (Error prevention)**. Giúp sinh viên không bị hụt hẫng và dễ dàng chọn ngay một phương án khả thi khác chỉ bằng 1 chạm thay vì bắt đầu lại từ đầu.

---

### Quyết định 7: ❌ TỪ CHỐI (REJECT) Gợi ý của AI về việc Tích hợp Chatbot AI Trả lời Thay Mentor
- **Mô tả gợi ý từ AI:** Trợ lý AI đề xuất *"Tích hợp Chatbot AI tự động phân tích CV và trả lời tự động câu hỏi nghề nghiệp thay cho cựu sinh viên để tăng tốc độ phản hồi"*.
- **Quyết định của nhóm:** ❌ **TỪ CHỐI HOÀN TOÀN (REJECT)**.
- **Lập luận phản biện học thuật (Critical Thinking):**
  - Căn cứ theo **Heuristic #2 (Match between system and real world)** và nhu cầu cốt lõi của **Persona Trương Chí Trung**:
  - Giá trị lớn nhất mà sinh viên tìm kiếm ở **F-Alumni** là **sự kết nối con người chân thực (Human-to-Human Connection)** — sự thấu cảm, kinh nghiệm thực chiến từ các anh chị cựu sinh viên cùng trường, và đặc biệt là sự **bảo lãnh uy tín thực tế (Referral)** vào các doanh nghiệp như FPT Software hay VNG.
  - Chatbot AI có thể tạo ra câu trả lời chung chung nhưng **hoàn toàn không thể cấp thư bảo lãnh Referral nội bộ** và làm giảm sút nghiêm trọng tính thiêng liêng, gắn kết của cộng đồng cựu sinh viên FPT. Do đó, nhóm giữ vững quyết định kết nối tư vấn 1-1 trực tiếp qua Google Meet.

---

### Quyết định 8: Nâng Độ tương phản Màu sắc đạt chuẩn WCAG 2.1 AAA cho Nội dung Chính
- **Mô tả thiết kế:** Màu chữ chính `#111827` trên nền trắng `#FFFFFF` đạt tỷ lệ **13.5:1** (chuẩn AAA tối thiểu 7:1); chữ phụ `#595959` đạt **5.4:1** (vượt chuẩn AA tối thiểu 4.5:1); màu thương hiệu Navy `#1B365D` đạt **12.8:1**.
- **Lập luận học thuật:** Căn cứ theo **WCAG 2.1 Success Criterion 1.4.3 (Contrast Minimum)**. Đảm bảo sinh viên đọc rõ từng chi tiết bài viết và tin tuyển dụng ngay cả khi đang sử dụng điện thoại ngoài trời sảnh campus FPT dưới ánh sáng mạnh.

---

### Quyết định 9: Chuẩn hóa Vùng Chạm (Touch Target) Tối thiểu 48 × 48 dp theo WCAG 2.5.5
- **Mô tả thiết kế:** Toàn bộ nút bấm chính, IconButtons (Back, Bookmark, Share), thẻ giờ hẹn và các Filter Chips đều có vùng đệm cảm ứng tối thiểu đạt **48 × 48 dp**.
- **Lập luận học thuật:** Căn cứ theo **WCAG 2.1 Success Criterion 2.5.5 (Target Size)** và đặc điểm nhân trắc học của Persona Trung khi thao tác bằng ngón tay cái bằng một tay khi đang đi lại trong trường.

---

### Quyết định 10: Nguyên tắc Mã hóa Kép (Dual-coding) — Không Dựa vào Màu sắc Đơn thuần
- **Mô tả thiết kế:** Mọi trạng thái hệ thống (Đã nhận / Đang chờ duyệt / Đã hủy lịch) và nhóm ngành đều được biểu diễn đồng thời bằng cả **Biểu tượng (Icon)** và **Nhãn văn bản (Label)** (ví dụ: `● 📅 ĐÃ XÁC NHẬN`, `● ⏳ ĐANG CHỜ DUYỆT`).
- **Lập luận học thuật:** Căn cứ theo **WCAG 2.1 Success Criterion 1.4.1 (Use of Color)**. Đảm bảo người dùng bị khiếm thị màu (Color blindness) hoặc người dùng bật chế độ màn hình đọc sách đơn sắc vẫn tiếp nhận chính xác 100% trạng thái hồ sơ.

---

## 2. Bảng Kết quả Kiểm tra Checklist Accessibility & Responsiveness

Toàn bộ các tiêu chí dưới đây đã được kiểm tra và đối soát nghiêm ngặt trên file Figma và bản đặc tả Flutter Handoff:

| Tiêu chí Kiểm tra (Checklist Item) | Tiêu chuẩn Đề bài & WCAG 2.1 | Kết quả Thực tế Đạt được trong F-Alumni | Minh chứng Kỹ thuật & Token | Đánh giá |
| :--- | :--- | :--- | :--- | :---: |
| **1. Độ tương phản chữ thường (Body Text Contrast)** | Tối thiểu **4.5:1** (WCAG 2.1 Level AA) | **13.5:1** (Text chính `#111827` trên nền `#FFFFFF`)<br>**5.4:1** (Text phụ `#595959` trên nền `#FFFFFF`) | Đo bằng Stark và WebAIM Contrast Checker | ✅ **ĐẠT (PASS)** |
| **2. Độ tương phản chữ lớn & UI Controls** | Tối thiểu **3:1** (WCAG 2.1 Level AA) | **3.2:1** (Nút CTA FPT Orange `#F27024` trên nền trắng)<br>**12.8:1** (FPT Navy `#1B365D` trên nền trắng) | Đo với Button Primary, App Bar Header và Tab Icons | ✅ **ĐẠT (PASS)** |
| **3. Kích thước Vùng chạm (Touch Target)** | Tối thiểu **48 × 48 dp** (WCAG 2.5.5) | Mọi Button, IconButton, Chip lọc và Time Slot đều bọc frame tối thiểu **48 × 48 dp**. | Cấu hình Auto Layout Padding trong Figma Component Library Page 05 | ✅ **ĐẠT (PASS)** |
| **4. Cỡ chữ nội dung tối thiểu (Font Size)** | Tối thiểu **14 sp** (Không có text nội dung nào < 14sp) | Chữ nội dung (Body text), JD tuyển dụng, nhãn form đều đạt **14 sp** (`body-md`) hoặc **16 sp** (`body-lg`). | Bộ token `type-body-medium` (14sp) và `type-body-large` (16sp) trong `DESIGN.md` | ✅ **ĐẠT (PASS)** |
| **5. Không truyền tải ý nghĩa chỉ bằng màu sắc (Dual-coding)** | Bắt buộc có Icon/Text đi kèm màu sắc (WCAG 1.4.1) | Trạng thái đơn và lịch hẹn kết hợp: Chấm màu + Biểu tượng + Nhãn chữ rõ ràng (`● 📅 ĐÃ XÁC NHẬN`). | Components `JobCard`, `SessionPass` và `FilterChip` | ✅ **ĐẠT (PASS)** |
| **6. Kiểm tra bố cục ở chiều rộng 360 dp** | Layout hiển thị chuẩn không bị tràn chữ ở 360 dp | Toàn bộ 8 màn hình được thiết kế gốc trên frame **360 × 800 dp**, khoảng lề hai bên cố định 16 dp. | Figma Page 02 (Wireframe) & Page 03 (Final UI) | ✅ **ĐẠT (PASS)** |
| **7. Kiểm tra bố cục co giãn ở chiều rộng 412 dp** | Sử dụng Auto Layout để thích ứng màn hình lớn hơn | Đã test trên thiết bị Samsung Galaxy S24 / Pixel 7 (chiều rộng 412 dp): Các card tự động giãn ngang không vỡ layout. | Thuộc tính Auto Layout `Horizontal Resizing: Fill Container` | ✅ **ĐẠT (PASS)** |
| **8. Quy chuẩn Thích ứng Màn hình Rộng (≥ 600 dp)** | Đưa ra quy tắc thích ứng cho Tablet / Desktop | Danh sách chuyển sang lưới 2 cột (`GridView.builder`); Bottom Navigation Bar chuyển thành `NavigationRail` bên trái. | Mục 6 trong file `handoff/flutter-handoff.md` | ✅ **ĐẠT (PASS)** |
