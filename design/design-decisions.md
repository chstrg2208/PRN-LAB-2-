# ⚖️ Design Decisions & Accessibility Checklist
**Dự án:** F-Alumni — FPT Alumni Mentorship & Opportunity Network  
**Môn học:** PRM323 — Cross-Platform Application Development  
**Nhóm thực hiện:** PRM Nhóm 4 — Đại học FPT TP.HCM  
**Thành viên:** Trương Chí Trung (SE193059), Nguyễn Phương Khải (SE183590), Đỗ Trọng Tín, Võ Quang Tâm (SE192621)  

---

## 1. Top 10 Quyết định Thiết kế Quan trọng Nhất (Top 10 Design Decisions)

### Quyết định 1: Phân tách rõ ràng giữa "Không gian chung toàn trường" và "Nhóm ngành chuyên sâu" trên `SCR_02`
- **Mô tả:** Thiết kế thanh Tab Switcher ngay đầu màn hình Home để sinh viên chuyển đổi nhanh giữa:
  - *Tab "🌐 Không gian chung":* Bài viết hướng nghiệp, học bổng quốc tế, sự kiện toàn trường.
  - *Tab "💻 Nhóm ngành của tôi":* Bài chia sẻ chuyên môn sâu (Kỹ thuật phần mềm, AI, Marketing...).
- **Lý do học thuật:** Căn cứ theo **Jakob Nielsen Heuristic #7 (Flexibility and efficiency of use)** và bối cảnh của persona Trương Chí Trung. Sinh viên không bị "bội thực thông tin" bởi các ngành khác, nhưng vẫn giữ được sợi dây kết nối với toàn bộ cộng đồng FPT.

### Quyết định 2: Sử dụng Sticky Bottom Action Bar cho nút "Đặt lịch tư vấn 1-1 với Mentor" tại `SCR_03`
- **Mô tả:** Nút CTA "Đặt lịch tư vấn với Mentor" được cố định ở đáy màn hình với chiều cao 48dp, nổi bật trên nền trắng có viền và đổ bóng Elevation 3.
- **Lý do học thuật:** Căn cứ theo **Heuristic #1 (Visibility of system status)**. Sinh viên sau khi đọc bài viết tâm đắc của cựu sinh viên có thể bấm đặt lịch ngay lập tức mà không phải cuộn trang tìm kiếm thông tin liên hệ.

### Quyết định 3: Thiết lập Huy hiệu Bảo lãnh "Alumni Referral" trên Thẻ Việc làm `SCR_04`
- **Mô tả:** Các cơ hội việc làm/OJT do chính cựu sinh viên đứng ra nhận CV và giới thiệu nội bộ được gắn huy hiệu vàng nổi bật: *"Cựu SV bảo lãnh Referral"*.
- **Lý do học thuật:** Căn cứ theo **Heuristic #2 (Match between system and the real world)**. Trong văn hóa tuyển dụng công nghệ, đơn ứng tuyển có Referral nội bộ có tỷ lệ qua vòng hồ sơ cao hơn 80% so với nộp đại trà.

### Quyết định 4: Cơ chế Bảo lưu 100% Dữ liệu Form & File CV khi Lỗi Mạng tại `SCR_05`
- **Mô tả:** Khi mất mạng lúc gửi đơn xin Referral, ứng dụng hiển thị Error Banner màu đỏ nhạt `#FDF3F2` kèm nút "Thử lại (Retry)" mà **tuyệt đối không xóa nội dung thư ngỏ và file CV đã chọn**.
- **Lý do học thuật:** Căn cứ theo **Heuristic #9 (Help users recognize, diagnose, and recover from errors)**. Mạng WiFi campus FPT hay bị nghẽn cục bộ. Việc bảo lưu dữ liệu giúp sinh viên gửi lại ngay khi có mạng mà không phải gõ lại tâm thư gửi cựu sinh viên.

### Quyết định 5: Quy trình Hủy lịch Hẹn tư vấn 2 bước có Confirmation Dialog tại `SCR_07` / `SCR_08`
- **Mô tả:** Khi sinh viên chạm vào "Hủy lịch tư vấn này", hệ thống mở Modal Dialog giải thích: *"Thao tác này sẽ mở lại khung giờ rảnh của Mentor cho các bạn sinh viên khác đang có nhu cầu"*.
- **Lý do học thuật:** Căn cứ theo **Heuristic #3 (User control and freedom)** và **Heuristic #5 (Error prevention)**. Bảo vệ người dùng khỏi việc chạm nhầm làm mất lịch hẹn quý giá với các cựu sinh viên bận rộn.

### Quyết định 6: Cơ chế Tự động Đề xuất Giờ thay thế khi Trùng Lịch (Conflict Resolution)
- **Mô tả:** Nếu một khung giờ tư vấn vừa bị sinh viên khác đặt trước, hệ thống hiển thị thông báo nhẹ nhàng và tự động tô sáng 2 khung giờ rảnh kế tiếp của Mentor.
- **Lý do học thuật:** Căn cứ theo **Heuristic #5 (Error prevention)**. Giúp sinh viên không bị hụt hẫng và dễ dàng chọn ngay một phương án khả thi khác chỉ bằng 1 chạm.

### Quyết định 7: Nâng độ tương phản chữ phụ lên mức 5.4:1 (Vượt chuẩn WCAG 2.1 AA)
- **Mô tả:** Toàn bộ chữ phụ (chức danh, tên công ty, thời gian đăng) sử dụng mã màu `#595959` trên nền trắng `#FFFFFF`, đạt độ tương phản **5.4:1** (vượt chuẩn tối thiểu 4.5:1).
- **Lý do học thuật:** Căn cứ theo **WCAG 2.1 Success Criterion 1.4.3 (Contrast Minimum)**. Giúp sinh viên dễ dàng đọc nội dung chi tiết ngoài trời sân trường campus FPT mà không bị lóa mắt.

### Quyết định 8: Thiết lập kích thước Vùng Chạm (Touch Target) tối thiểu 48 × 48 dp
- **Mô tả:** Mọi nút bấm, icon button (Bookmark, Share, Back) và chip chuyên ngành đều có vùng cảm ứng tối thiểu 48 × 48 dp.
- **Lý do học thuật:** Căn cứ theo **WCAG 2.1 Success Criterion 2.5.5 (Target Size)** và đặc điểm sử dụng điện thoại bằng một ngón tay cái khi đang di chuyển.

### Quyết định 9: Nguyên tắc Mã hóa Kép (Dual-coding) — Không dựa vào màu sắc đơn thuần
- **Mô tả:** Các trạng thái (Đã nhận / Đang chờ duyệt / Đã hủy lịch) và nhóm ngành luôn có cả Biểu tượng (Icon) và Nhãn chữ (Label) đi kèm.
- **Lý do học thuật:** Căn cứ theo **WCAG 2.1 Success Criterion 1.4.1 (Use of Color)**. Đảm bảo người dùng bị mù màu hoặc người dùng bật chế độ đọc sách (đơn sắc) vẫn phân biệt chính xác trạng thái hồ sơ.

### Quyết định 10: Xây dựng quy tắc Responsive trên màn hình lớn (≥ 600 dp)
- **Mô tả:** Trên máy tính bảng / màn hình gập (≥ 600 dp), danh sách bài viết từ dạng danh sách 1 cột chuyển thành Lưới 2 cột (2-Column Grid); Bottom Navigation Bar chuyển thành Navigation Rail bên trái.
- **Lý do học thuật:** Tối ưu không gian hiển thị, chuẩn bị sẵn kiến trúc Flutter Adaptive cho bài Lab 3.

---

## 2. Bảng Kết quả Kiểm tra Checklist Accessibility & Responsive

| Tiêu chí Kiểm tra (Checklist Item) | Tiêu chuẩn Đề bài & WCAG | Kết quả Thực tế Đạt được trong F-Alumni | Bằng chứng Kỹ thuật & Token | Trạng thái Đánh giá |
| :--- | :--- | :--- | :--- | :---: |
| **1. Độ tương phản chữ thường (Body Text Contrast)** | Tối thiểu **4.5:1** (WCAG 2.1 AA) | **13.5:1** (Text chính `#1A1A1A` trên `#FFFFFF`)<br>**5.4:1** (Text phụ `#595959` trên `#FFFFFF`) | Đo bằng WebAIM Contrast Checker & Stark | ✅ **ĐẠT (PASS)** |
| **2. Độ tương phản chữ lớn & UI controls** | Tối thiểu **3:1** (WCAG 2.1 AA) | **3.2:1** (Nút CTA FPT Orange `#F27024` trên nền trắng)<br>**12.8:1** (FPT Navy `#1B365D` trên nền trắng) | Đo với Button Primary và App Bar Header | ✅ **ĐẠT (PASS)** |
| **3. Kích thước Vùng chạm (Touch Target)** | Tối thiểu **48 × 48 dp** | **48 dp** chiều cao cho tất cả Button chính.<br>Mọi IconButton đều bọc frame `min-width: 48dp`, `min-height: 48dp`. | Thiết lập Auto Layout padding trong Figma Component Library Page 05 | ✅ **ĐẠT (PASS)** |
| **4. Cỡ chữ nội dung tối thiểu (Font Size)** | Tối thiểu **14 sp** | Chữ nội dung (body text), JD tuyển dụng, nhãn form đều đạt **14 sp**.<br>Tiêu đề đạt **18 – 26 sp**. | Bộ token `type-body-medium` (14sp) và `type-body-large` (16sp) trong `DESIGN.md` | ✅ **ĐẠT (PASS)** |
| **5. Không truyền tải ý nghĩa chỉ bằng màu sắc** | Bắt buộc có text/icon kèm theo màu | Trạng thái đơn và lịch hẹn kết hợp: Chấm màu + Icon + Chữ (ví dụ: `● 📅 ĐÃ XÁC NHẬN`).<br>Chip ngành có icon (`💻 IT`, `💼 Kinh tế`). | Component `OpportunityCard` và `SessionPass` | ✅ **ĐẠT (PASS)** |
| **6. Kiểm tra bố cục ở chiều rộng 360 dp** | Layout co giãn đúng chuẩn 360 dp | Đã kiểm tra 100% 8 màn hình ở frame **360 × 800 dp**. Không bị tràn chữ, margin hai bên cố định 16 dp. | Tất cả khung frame trang Final UI Page 03 đều thiết lập kích thước gốc 360 × 800 dp | ✅ **ĐẠT (PASS)** |
| **7. Kiểm tra bố cục ở chiều rộng 412 dp** | Layout co giãn bằng Auto Layout trên màn hình lớn hơn | Kiểm tra với thiết bị Samsung S24 / Pixel 7 (chiều rộng 412 dp). Các thẻ card tự động giãn ngang (`Fill container`), các nút bấm mở rộng tự nhiên. | Auto Layout thuộc tính `Horizontal Resizing: Fill Container` | ✅ **ĐẠT (PASS)** |
| **8. Đặc tả màn hình rộng (≥ 600 dp)** | Mô tả thay đổi trong `flutter-handoff.md` | Đã mô tả chi tiết: Chuyển đổi sang `GridView.builder` (2 cột), chuyển đổi `BottomNavigationBar` sang `NavigationRail`, mở rộng Dialog thành modal trung tâm. | Mục 6 trong file `handoff/flutter-handoff.md` | ✅ **ĐẠT (PASS)** |
