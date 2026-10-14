# 📱 Screen Specifications: Detailed Design Intent & Content Breakdown
**Dự án:** F-Alumni — FPT Alumni Mentorship & Opportunity Network  
**Môn học:** PRM323 — Cross-Platform Application Development  
**Nhóm thực hiện:** PRM Nhóm 4 — Đại học FPT TP.HCM  
**Thành viên:** Trương Chí Trung (SE193059), Nguyễn Phương Khải (SE183590), Đỗ Trọng Tín, Võ Quang Tâm  

---

## 1. Danh sách 8 Màn hình Độc lập trong Hệ thống

Hệ thống bao gồm 8 màn hình riêng biệt (không tính dialog hay các state variants), mỗi màn hình được thiết kế nhằm phục vụ một nhiệm vụ cụ thể và liên kết chặt chẽ vào 3 User Flows:

```
SCR_01: Login & Role Selection Screen (Xác thực Google FPT & Chọn vai trò/ngành)
SCR_02: Home Feed Screen (Không gian chung toàn trường & Nhóm ngành chuyên sâu)
SCR_03: Post / Experience Detail Screen (Chi tiết bài chia sẻ kinh nghiệm & Bio Mentor)
SCR_04: Career & Opportunity Board Screen (Bảng tin OJT, Việc làm & Học bổng)
SCR_05: Job Detail & Referral Apply Screen (Chi tiết công việc & Nộp CV xin Referral)
SCR_06: Alumni Mentors Directory Screen (Danh bạ Cựu sinh viên & Bộ lọc công ty)
SCR_07: Mentor Booking & Session Pass Screen (Đặt lịch hẹn 1-1 Google Meet & Vé hẹn)
SCR_08: Profile & My Network Screen (Hồ sơ cá nhân, kho CV & Lịch tư vấn đã đặt)
```

---

## 2. Đặc tả Chi tiết Từng Màn hình

---

### 🖥️ SCR_01: Login & Role Selection Screen
- **Mục đích sử dụng:** Xác thực danh tính sinh viên / cựu sinh viên Đại học FPT qua tài khoản Google Workspace (`@fpt.edu.vn`) và thiết lập hồ sơ ban đầu.
- **Nội dung hiển thị:**
  - Logo ứng dụng **F-Alumni** với biểu tượng chiếc mũ tốt nghiệp kết hợp đôi bàn tay nâng đỡ.
  - Tiêu đề: *"F-Alumni — Mạng lưới Kết nối Cựu sinh viên & Sinh viên Đại học FPT"*.
  - Nút bấm đăng nhập một chạm: *"Đăng nhập với Google FPT Edu (@fpt.edu.vn)"*.
  - Chọn vai trò (Role Picker): **"Sinh viên trường (Student)"** hoặc **"Cựu sinh viên (Alumni Mentor)"**.
  - Chọn chuyên ngành chính: Kỹ thuật phần mềm (SE), Trí tuệ nhân tạo (AI), An toàn thông tin (IA), Quản trị kinh doanh (BA), Marketing số, Thiết kế mỹ thuật số (GD), Ngôn ngữ Anh/Nhật/Hàn.
  - Chọn cơ sở: TP.HCM, Hòa Lạc, Đà Nẵng, Cần Thơ, Quy Nhơn.
- **Thuộc User Flow:** Flow khởi đầu bắt buộc.
- **Ý đồ thiết kế (Design Intent):**
  - Giảm thiểu ma sát đăng ký tài khoản, đồng thời cá nhân hóa ngay giao diện cho sinh viên dựa trên chuyên ngành đã chọn khi bước vào `SCR_02`.

---

### 🖥️ SCR_02: Home Feed Screen (Không gian Chung & Nhóm ngành)
- **Mục đích sử dụng:** Trung tâm cập nhật tin tức và bài viết chia sẻ kinh nghiệm thực chiến từ cựu sinh viên.
- **Nội dung hiển thị:**
  - Header: Lời chào *"Xin chào, Trương Chí Trung"*, nhãn chuyên ngành *"Kỹ thuật phần mềm (SE)"*, avatar cá nhân.
  - Thanh tìm kiếm: *"Tìm bài chia sẻ, học bổng, việc làm..."*.
  - **Bộ chuyển đổi không gian (Space Tab Switcher):**
    - **Tab 1: "🌐 Không gian chung"** — Hiển thị bài viết kỹ năng mềm, cơ hội học bổng quốc tế, ngày hội cựu sinh viên toàn trường.
    - **Tab 2: "💻 Nhóm ngành IT / Software"** (tự động theo ngành của user) — Hiển thị bài chia sẻ chuyên sâu về code, roadmap, phỏng vấn technical.
  - Chip phân loại con: "🔥 Nổi bật", "💼 Cơ hội việc làm", "🎓 Học bổng", "💡 Kinh nghiệm OJT".
  - Thẻ bài viết nổi bật (Featured Post Card): Ảnh tác giả, họ tên cựu sinh viên, chức danh *"Senior Mobile Engineer tại VNG"*, tiêu đề bài viết *"Lộ trình ôn luyện phỏng vấn Software Engineer 2026"*, số lượt thích, bình luận, nút Bookmark.
  - Danh sách bài viết mới nhất dạng Card dọc.
  - Thanh điều hướng đáy (Bottom Navigation Bar) gồm 4 tab.
- **Thuộc User Flow:** User Flow 1 (Điểm bắt đầu Khám phá bài viết).
- **Ý đồ thiết kế (Design Intent):**
  - Giải quyết trực tiếp nhu cầu đề bài: Vừa có không gian chia sẻ chung cho toàn trường, vừa có không gian chuyên sâu riêng theo ngành giúp sinh viên tiếp cận đúng thông tin chuyên môn cần thiết.

---

### 🖥️ SCR_03: Post / Experience Detail Screen
- **Mục đích sử dụng:** Trình bày chi tiết bài viết chia sẻ kinh nghiệm, tài liệu hướng dẫn và tạo cầu nối trực tiếp để sinh viên đặt lịch hẹn với tác giả.
- **Nội dung hiển thị:**
  - Header có nút Back, nút Chia sẻ và nút Bookmark lưu bài.
  - Tiêu đề bài viết H1 20sp Bold, ngày đăng, thời lượng đọc ("5 phút đọc").
  - Thẻ thông tin cựu sinh viên tác giả (Author Tile): Avatar, họ tên *"Lê Hoàng Long"*, khóa K14, chức danh hiện tại, công ty (logo VNG), số năm kinh nghiệm, nút "Xem hồ sơ Mentor".
  - Thân bài viết: Các giai đoạn phỏng vấn, câu hỏi phỏng vấn thường gặp, lời khuyên thực tế khi làm bài test kỹ thuật.
  - Thẻ tệp đính kèm: *"Interview_Preparation_Checklist_2026.pdf"* kèm nút tải về.
  - Khu vực Hỏi đáp - Bình luận (Q&A): Sinh viên đặt câu hỏi công khai, cựu sinh viên phản hồi.
  - **Sticky Bottom Action Bar:** Nút bấm nổi bật *"Đặt lịch tư vấn 1-1 với Mentor"* (chiều cao 48dp) luôn ghim cố định ở chân màn hình.
- **Thuộc User Flow:** User Flow 1 (Xem bài & Chuyển tiếp sang đặt lịch tư vấn).
- **Ý đồ thiết kế (Design Intent):**
  - Tối ưu tỷ lệ chuyển đổi từ việc đọc thụ động sang hành động chủ động kết nối trực tiếp với Mentor.

---

### 🖥️ SCR_04: Career & Opportunity Board Screen
- **Mục đích sử dụng:** Bảng tin việc làm, cơ hội thực tập OJT và học bổng được cựu sinh viên trực tiếp đăng tải hoặc sẵn sàng đứng ra bảo lãnh giới thiệu (Referral).
- **Nội dung hiển thị:**
  - Header: Tiêu đề *"Cơ hội Việc làm & Học bổng"*, nút lọc nâng cao.
  - Bộ lọc danh mục ngang: "Tất cả", "Thực tập OJT", "Việc làm (Full-time)", "Học bổng Thạc sĩ".
  - Danh sách thẻ cơ hội (Job Cards):
    - Logo công ty (FPT Software, VNG, Shopee, Viettel).
    - Tên vị trí: *"Junior Flutter Developer (Hỗ trợ sinh viên FPT)"*.
    - Mức lương / phụ cấp thực tập, địa điểm làm việc.
    - **Huy hiệu vàng:** *"Cựu SV K15 bảo lãnh Referral"*.
    - Hạn chót nộp hồ sơ, số lượt đã ứng tuyển.
    - Nút bấm trên thẻ: *"Xem & Xin Referral"*.
- **Thuộc User Flow:** User Flow 2 (Điểm bắt đầu tìm kiếm việc làm OJT).
- **Ý đồ thiết kế (Design Intent):**
  - Tạo sự khác biệt hoàn toàn với các trang tuyển dụng đại trà: Mọi cơ hội ở đây đều có sự kết nối và bảo trợ uy tín từ cựu sinh viên trường FPT.

---

### 🖥️ SCR_05: Job Detail & Referral Apply Screen
- **Mục đích sử dụng:** Cung cấp mô tả công việc chi tiết và tiếp nhận hồ sơ xin Referral của sinh viên.
- **Nội dung hiển thị:**
  - Header có nút Back và nút lưu công việc.
  - Tóm tắt công việc: Vị trí, công ty, mức đãi ngộ, chế độ làm việc (Hybrid / Onsite).
  - Khối thông tin cựu sinh viên bảo lãnh: Tên cựu SV, bộ phận làm việc, ghi chú từ cựu SV (*"Mình đang cần 2 bạn thực tập sinh Flutter cho dự án team, ưu tiên các bạn nắm vững Dart & Bloc"*).
  - Mô tả công việc (JD), yêu cầu kỹ thuật và quyền lợi.
  - **Form ứng tuyển & xin Referral:**
    - Khu vực tải lên CV (Upload PDF, tự động lấy CV từ hồ sơ nếu đã có).
    - Ô nhập thư ngỏ ngắn (Cover letter note): Lý do muốn xin Referral, điểm mạnh bản thân.
    - Nút CTA chân trang: *"GỬI YÊU CẦU XIN REFERRAL"* (có loading spinner khi gửi).
  - Error Banner: Hiển thị khi mất kết nối mạng và bảo lưu toàn bộ file CV cùng nội dung thư ngỏ.
- **Thuộc User Flow:** User Flow 2 (Nộp CV) & User Flow 3 (Phục hồi lỗi mạng).
- **Ý đồ thiết kế (Design Intent):**
  - Tối giản hóa quy trình xin việc, biến việc xin Referral từ cựu sinh viên thành một trải nghiệm trang trọng, lịch sự và nhanh chóng.

---

### 🖥️ SCR_06: Alumni Mentors Directory Screen
- **Mục đích sử dụng:** Danh bạ tổng hợp mạng lưới cựu sinh viên trường sẵn sàng hỗ trợ đàn em khóa dưới.
- **Nội dung hiển thị:**
  - Header: *"Mạng lưới Cựu sinh viên FPT"*.
  - Bộ lọc công ty công nghệ lớn: "Tất cả", "FPT Software", "VNG", "Google", "Shopee", "Ngân hàng/Fintech".
  - Thẻ thông tin Mentor (Mentor Cards):
    - Avatar, tên cựu sinh viên, niên khóa (K12, K13, K14...).
    - Vị trí hiện tại, công ty đang công tác.
    - Lĩnh vực sẵn sàng tư vấn: "Review CV", "Phỏng vấn kỹ thuật", "Lộ trình OJT", "Học bổng du học".
    - Đánh giá từ sinh viên khóa trước: 5.0 ⭐ (18 buổi tư vấn thành công).
    - Nút CTA: *"Đặt lịch tư vấn 1-1"*.
- **Thuộc User Flow:** User Flow 1 (Duyệt danh sách cựu sinh viên theo công ty mong muốn).
- **Ý đồ thiết kế (Design Intent):**
  - Xây dựng niềm tin và sự tự hào cho sinh viên thông qua các tấm gương cựu sinh viên thành đạt từ chính ngôi trường của mình.

---

### 🖥️ SCR_07: Mentor Booking & Session Pass Screen
- **Mục đích sử dụng:** Chọn khung giờ rảnh của Mentor để lên lịch hẹn tư vấn trực tuyến và xuất thẻ lịch hẹn (Session Pass).
- **Nội dung hiển thị:**
  - Thẻ tóm tắt thông tin Mentor được chọn.
  - Lịch chọn ngày trong tuần (Calendar Strip).
  - Khung chọn giờ rảnh trong ngày (Time Slots Grid): ví dụ: `09:00 - 09:45`, `14:00 - 14:45`, `20:00 - 20:45`.
  - Ô nhập chủ đề thảo luận: *"Chủ đề bạn muốn hỏi Mentor"*.
  - Nút bấm: *"XÁC NHẬN ĐẶT LỊCH HẸN (QUA GOOGLE MEET)"*.
  - **Thẻ lịch hẹn Session Pass (sau khi đặt thành công):**
    - Mã lịch hẹn: `SES-2026-SE193059-01`.
    - Trạng thái: `● ĐÃ XÁC NHẬN` (Màu xanh lá).
    - Link phòng họp Google Meet tự động tạo.
    - Nút: *"Thêm vào Google Calendar"* và text link *"Hủy lịch hẹn"*.
- **Thuộc User Flow:** User Flow 1 (Đích đến đặt lịch) & User Flow 3 (Trùng lịch / Hủy lịch nhường chỗ).
- **Ý đồ thiết kế (Design Intent):**
  - Tự động hóa hoàn toàn quy trình hẹn lịch, loại bỏ việc nhắn tin trao đổi giờ giấc thủ công dễ gây nhầm lẫn.

---

### 🖥️ SCR_08: Profile & My Network Screen
- **Mục đích sử dụng:** Không gian cá nhân của sinh viên để quản lý hồ sơ, kho CV, bài viết đã lưu và theo dõi trạng thái các buổi tư vấn/hồ sơ xin Referral.
- **Nội dung hiển thị:**
  - Thẻ hồ sơ sinh viên: Avatar, Họ tên (*"Trương Chí Trung"*), MSSV (*"SE193059"*), Ngành (*"Kỹ thuật phần mềm - Khóa K19"*).
  - Thanh chuyển đổi tab quản lý:
    - **Tab "Lịch tư vấn của tôi":** Các buổi hẹn 1-1 sắp tới, lịch sử các buổi đã hoàn thành.
    - **Tab "Hồ sơ xin Referral":** Danh sách các công việc đã nộp CV kèm trạng thái (Đang chờ cựu SV duyệt / Đã nhận Referral).
    - **Tab "Bài viết đã lưu":** Danh sách các bài chia sẻ kinh nghiệm đã Bookmark.
  - Kho quản lý tệp CV đính kèm.
  - Danh mục Cài đặt: Tùy chỉnh thông báo việc làm mới, đổi chuyên ngành quan tâm, Hỗ trợ và Đăng xuất.
- **Thuộc User Flow:** User Flow 1 (Xem bài đã lưu), Flow 2 (Theo dõi hồ sơ), Flow 3 (Khởi tạo hủy lịch hẹn).
- **Ý đồ thiết kế (Design Intent):**
  - Đóng vai trò là trung tâm quản lý toàn bộ hành trình phát triển nghề nghiệp và các mối quan hệ kết nối của sinh viên.
