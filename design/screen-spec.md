# 📱 Screen Specifications: Detailed Design Intent & State Breakdown

> **Môn học:** PRM323 — Cross-Platform Application Development  
> **Dự án:** **F-Alumni — FPT Alumni Mentorship & Opportunity Network**  
> **Nhóm thực hiện:** PRM Nhóm 4 — Đại học FPT TP. Hồ Chí Minh  
> **Người biên soạn chính (Lead Author):** **Nguyễn Phương Khải** — MSSV: **SE183590** (Vai trò: **TV3 — UI Design System & Screen Specifications Lead**)  
> 
> 🌐 **Dự án Google Stitch liên kết:** [https://stitch.withgoogle.com/projects/1771935993966075517](https://stitch.withgoogle.com/projects/1771935993966075517)  
> 🎨 **Vị trí thiết kế trong Figma:** [Figma Pages: 02 Wireframe & 03 Final UI](https://www.figma.com/design/PPdvsVA0O63HEHTQkxBQX0/PRM323---Lab-2---F-Alumni---Nhom-4?node-id=1-3&t=00FzbJIZRL89FvX4-1)  

---

## 1. Danh mục 8 Màn hình Độc lập trong Hệ thống

Hệ thống bao gồm đúng **8 màn hình độc lập** (không tính dialog overlay hay các biến thể trạng thái loading/empty/error theo quy định đề bài). Mỗi màn hình được thiết kế trên khung chuẩn di động **360 × 800 dp**, sử dụng 100% Auto Layout và ánh xạ trực tiếp vào 3 User Flows:

```
SCR_01: Login & Role Selection Screen (Xác thực Google FPT & Chọn vai trò / Chuyên ngành)
SCR_02: Home Feed Screen (Không gian chung toàn trường & Nhóm ngành chuyên sâu)
SCR_03: Post / Experience Detail Screen (Chi tiết bài chia sẻ kinh nghiệm & Bio Mentor)
SCR_04: Career & Opportunity Board Screen (Bảng tin OJT, Việc làm & Học bổng cựu SV bảo lãnh)
SCR_05: Job Detail & Referral Apply Screen (Chi tiết việc làm & Form nộp CV xin Referral)
SCR_06: Alumni Mentors Directory Screen (Danh bạ Cựu sinh viên & Bộ lọc công ty công nghệ)
SCR_07: Mentor Booking & Session Pass Screen (Đặt lịch hẹn 1-1 Google Meet & Thẻ Session Pass)
SCR_08: Profile & My Network Screen (Hồ sơ cá nhân, Kho lưu trữ CV & Lịch tư vấn của tôi)
```

---

## 2. Đặc tả Chi tiết Từng Màn hình

---

### 📱 SCR_01: Login & Role Selection Screen
- **Mục đích sử dụng:** Cổng vào xác thực danh tính sinh viên / cựu sinh viên Đại học FPT thông qua tài khoản Google Workspace (`@fpt.edu.vn`) và cá nhân hóa trải nghiệm theo chuyên ngành ngay từ lần đầu mở app.
- **Nội dung & Phân rã Giao diện:**
  - Header: Logo biểu trưng chiếc mũ tốt nghiệp F-Alumni kết hợp đôi bàn tay nâng đỡ; Tiêu đề `type-display-large` 26sp Bold: *"F-Alumni — Mạng lưới Kết nối Cựu sinh viên & Sinh viên FPT"*.
  - Nút đăng nhập chính: *"Tiếp tục với Google FPT Edu (@fpt.edu.vn)"* (Nền trắng, viền `#E5E7EB`, icon Google chuẩn, cao 48dp).
  - Khối chọn vai trò (Role Picker Segmented): Tab chọn **"Sinh viên trường (Student)"** hoặc **"Cựu sinh viên (Alumni Mentor)"**.
  - Dropdown chọn chuyên ngành chính: Kỹ thuật phần mềm (SE), Trí tuệ nhân tạo (AI), An toàn thông tin (IA), Thiết kế mỹ thuật số (GD), Quản trị kinh doanh (BA).
  - Chip chọn cơ sở Campus: TP.HCM (Q9), Hà Nội (Hòa Lạc), Đà Nẵng, Cần Thơ, Quy Nhơn.
- **Thuộc User Flow:** Flow khởi đầu bắt buộc cho mọi hành trình.
- **Ý đồ Thiết kế (Design Intent):**
  - Giảm thiểu tối đa ma sát đăng nhập (Zero-friction Google OAuth). Hệ thống tự nhận diện đuôi email (ví dụ sinh viên ngành SE có mã số `SE...`) để gợi ý sẵn chuyên ngành, giúp sinh viên vào thẳng bài viết phù hợp mà không phải cấu hình rườm rà.
- **Các trạng thái giao diện (States Breakdown):**
  - *Default:* Form hiển thị sẵn, nút Google sẵn sàng.
  - *Loading:* Nút Google hiển thị spinner xử lý xác thực token OAuth.
  - *Error:* Hiển thị thông báo đỏ *"Vui lòng sử dụng tài khoản email sinh viên đuôi @fpt.edu.vn"*.
- **Ràng buộc Accessibility & Responsive:**
  - Nút đăng nhập và các chip chọn ngành đạt chiều cao tối thiểu **48 dp**.
  - Tự động co giãn theo chiều ngang khi hiển thị trên màn hình rộng 412 dp (`Horizontal: Fill container`).

---

### 📱 SCR_02: Home Feed Screen (Không gian Chung & Nhóm ngành)
- **Mục đích sử dụng:** Bảng tin trung tâm cập nhật bài viết chia sẻ kinh nghiệm phỏng vấn, kinh nghiệm làm đồ án tốt nghiệp Capstone và cơ hội học bổng.
- **Nội dung & Phân rã Giao diện:**
  - Top Bar: Lời chào cá nhân hóa *"Xin chào, Trương Chí Trung 👋"*, huy hiệu sinh viên *"SE - K19 Campus HCM"*, Avatar tròn 40dp.
  - Search Bar: Ô tìm kiếm bo góc 8dp có icon kính lúp, placeholder *"Tìm bài chia sẻ, kinh nghiệm OJT, học bổng..."*.
  - **Bộ chuyển đổi 2 không gian (Space Tab Switcher - Điểm nhấn cốt lõi đề bài):**
    - **Tab 1: "🌐 Không gian chung"** — Tin tức, bài viết định hướng chung toàn trường, học bổng trao đổi sinh viên quốc tế.
    - **Tab 2: "💻 Nhóm ngành IT / Software"** (Tự động thích ứng theo ngành người dùng) — Các bài viết kỹ thuật chuyên sâu về thuật toán, system design, roadmap phỏng vấn Backend/Mobile.
  - Category Filter Chips (cuộn ngang): "🔥 Tất cả", "💼 Cơ hội việc làm", "🎓 Học bổng", "💡 Kinh nghiệm OJT", "⭐ Lời khuyên Capstone".
  - Thẻ bài viết nổi bật (Featured Post Card):
    - Avatar tác giả, tên cựu sinh viên *"Lê Hoàng Long"*, chức danh *"Senior Mobile Engineer tại VNG Corporation"*.
    - Tiêu đề `type-title-medium` 18sp: *"Lộ trình ôn luyện phỏng vấn Software Engineer 2026 cho sinh viên FPT"*.
    - Số lượt bookmark, bình luận và icon Bookmark lưu nhanh góc thẻ.
  - Danh sách bài viết mới nhất (Infinite Scroll Feed).
  - Bottom Navigation Bar cố định 4 tab ở chân màn hình.
- **Thuộc User Flow:** **User Flow 1 (Điểm bắt đầu khám phá bài viết & đặt lịch)**.
- **Ý đồ Thiết kế (Design Intent):**
  - Giải quyết triệt để rào cản thông tin phân mảnh: Sinh viên không bị ngập trong các bài viết khác ngành, nhưng vẫn giữ được sợi dây liên kết với các sự kiện lớn của toàn thể cựu sinh viên trường.
- **Các trạng thái giao diện (States Breakdown):**
  - *Populated:* Danh sách bài viết đầy đủ dữ liệu.
  - *Loading Shimmer:* Khung xương Skeleton bài viết chuyển động mờ từ `#E5E7EB` sang `#F3F4F6`.
  - *Empty State:* Hiển thị khi một chuyên ngành mới chưa có bài viết: Minh họa vector + nút *"Khám phá Không gian chung"*.
- **Ràng buộc Accessibility & Responsive:**
  - Vùng chạm icon Bookmark trên thẻ đạt tối thiểu **48 × 48 dp**.
  - Khoảng cách lề trái/phải cố định **16 dp** chuẩn lưới 8dp.

---

### 📱 SCR_03: Post / Experience Detail Screen
- **Mục đích sử dụng:** Trình bày toàn văn nội dung bài viết chia sẻ kinh nghiệm thực chiến từ cựu sinh viên, cung cấp tài liệu đính kèm và kích hoạt chuyển đổi sang việc đặt lịch hẹn tư vấn 1-1.
- **Nội dung & Phân rã Giao diện:**
  - Header: Nút Back tròn 48dp, tiêu đề rút gọn, icon Bookmark và nút Share chia sẻ bài viết.
  - Thẻ tác giả cựu sinh viên (Alumni Author Tile):
    - Avatar 56×56dp, tên *"Lê Hoàng Long"*, badge niên khóa *"Alumni K14"*, công ty VNG Corporation.
    - Nút phụ: *"Xem hồ sơ Mentor"*.
  - Tiêu đề bài viết lớn 20sp Bold, ngày đăng, thời lượng đọc *"5 phút đọc"*.
  - Nội dung bài viết phong phú: Các giai đoạn phỏng vấn doanh nghiệp, câu hỏi kỹ thuật hóc búa, lưu ý về thái độ ứng xử.
  - Thẻ tệp đính kèm: *"Interview_Preparation_Checklist_2026.pdf (1.8 MB)"* có nút Tải về.
  - Khu vực Thảo luận & Hỏi đáp (Q&A Comments).
  - **Sticky Bottom Action Bar:** Nút CTA màu cam FPT `#F27024` cao 48dp: *"ĐẶT LỊCH TƯ VẤN 1-1 VỚI MENTOR"* ghim cố định ở đáy màn hình.
- **Thuộc User Flow:** User Flow 1 (Cầu nối giữa đọc bài và mở màn hình đặt lịch `SCR_07`).
- **Ý đồ Thiết kế (Design Intent):**
  - Tối đa hóa tỷ lệ chuyển đổi: Biến cảm hứng học hỏi khi đọc bài viết thành hành động kết nối trực tiếp với Mentor qua nút Sticky CTA tiện dụng.
- **Các trạng thái giao diện (States Breakdown):**
  - *Populated:* Đầy đủ bài viết, danh sách bình luận.
  - *Bookmark Toast Feedback:* Hiển thị thanh thông báo ngắn dưới đáy *"Đã lưu bài viết vào mục Hồ sơ"*.
- **Ràng buộc Accessibility & Responsive:**
  - Cỡ chữ nội dung bài viết đạt **16 sp** (`type-body-large`), khoảng cách dòng 24sp giúp người dùng đọc lâu không bị mỏi mắt.

---

### 📱 SCR_04: Career & Opportunity Board Screen
- **Mục đích sử dụng:** Bảng tin chuyên biệt cập nhật các vị trí thực tập doanh nghiệp (OJT), việc làm chính thức và học bổng được cựu sinh viên bảo lãnh giới thiệu (Referral).
- **Nội dung & Phân rã Giao diện:**
  - Header: Tiêu đề `type-title-large` 20sp: *"Cơ hội Việc làm & Học bổng"*.
  - Thanh tìm kiếm và bộ lọc nhanh: "Tất cả", "Thực tập OJT", "Việc làm (Job)", "Học bổng Thạc sĩ".
  - Danh sách Thẻ cơ hội tuyển dụng (Job Cards):
    - Logo công ty tuyển dụng (FPT Software, VNG, Shopee, Techcombank).
    - Tên công việc: *"Junior Flutter Developer (Referral by Alumni)"*.
    - Mức lương / Phụ cấp thực tập (ví dụ: `8 - 15 triệu VNĐ`).
    - Địa điểm làm việc: `TP.HCM (Hybrid)`.
    - **Huy hiệu vàng/xanh nổi bật:** *"Cựu SV K15 bảo lãnh Referral"*.
    - Nút bấm trên thẻ: *"Xem & Xin Referral"* (FPT Orange, cao 48dp).
- **Thuộc User Flow:** **User Flow 2 (Điểm bắt đầu nộp hồ sơ xin Referral)**.
- **Ý đồ Thiết kế (Design Intent):**
  - Mang đến lợi thế cạnh tranh vượt trội cho sinh viên FPT: Tiếp cận kênh nộp CV nội bộ (Internal Referral) thay vì nộp hồ sơ đại trà cạnh tranh khốc liệt trên mạng xã hội.
- **Các trạng thái giao diện (States Breakdown):**
  - *Populated:* Danh sách việc làm hiển thị trực quan.
  - *Empty State (`SCR_04_Empty` - Kết quả Vòng lặp AI 2):* Khi người dùng tìm kiếm từ khóa không có (ví dụ "DevOps Fresher"), hiển thị hình minh họa thư mục rỗng, thông điệp *"Chưa tìm thấy cơ hội phù hợp"* kèm nút *"↻ Xóa bộ lọc"*.
- **Ràng buộc Accessibility & Responsive:**
  - Huy hiệu Referral áp dụng nguyên tắc Dual-coding (có icon khiên bảo lãnh + chữ *"Cựu SV bảo lãnh Referral"*).

---

### 📱 SCR_05: Job Detail & Referral Apply Screen
- **Mục đích sử dụng:** Cung cấp bản mô tả công việc (JD) chi tiết và tiếp nhận hồ sơ xin bảo lãnh giới thiệu trực tiếp từ sinh viên gửi tới cựu sinh viên.
- **Nội dung & Phân rã Giao diện:**
  - Header có nút Back và nút lưu tin tuyển dụng.
  - Tóm tắt vị trí: Tên công việc, công ty, mức đãi ngộ, hạn chót nhận đơn.
  - **Khối thông điệp bảo lãnh từ cựu SV (Alumni Endorsement Card - Kết quả Vòng lặp AI 3):**
    - Trích dẫn lời nhắn từ anh Trần Tuấn Anh (Tech Lead K12): *"Mình sẽ trực tiếp duyệt CV và gửi vào hệ thống Referral nội bộ cho các bạn sinh viên FPT có nền tảng tốt về OOP và Flutter/Dart"*.
  - Mô tả công việc, trách nhiệm và quyền lợi chi tiết.
  - **Form Nộp CV & Xin Referral:**
    - Thẻ chọn file CV: Hiển thị tên file đã chọn `TruongChiTrung_SE_CV.pdf (2.4 MB)` kèm nút thay đổi file.
    - Ô nhập thư ngỏ ngắn (Cover letter 500 ký tự) có các chip gợi ý: `+ Giới thiệu Capstone`, `+ Điểm mạnh Flutter`.
    - Nút CTA lớn ở chân màn hình: *"GỬI YÊU CẦU XIN REFERRAL"*.
  - **Error Recovery Banner (User Flow 3):** Khung cảnh báo màu đỏ nhạt `#FDF3F2` xuất hiện khi mất kết nối mạng: *"Không thể kết nối máy chủ. Toàn bộ thông tin thư ngỏ và file CV đã được bảo lưu an toàn"* kèm nút *"Thử lại (Retry)"*.
- **Thuộc User Flow:** User Flow 2 (Gửi CV) và **User Flow 3 (Phục hồi lỗi mạng bảo toàn form)**.
- **Ý đồ Thiết kế (Design Intent):**
  - Biến quy trình xin việc thành trải nghiệm tôn trọng, chu đáo. Bảo toàn 100% dữ liệu form ngăn chặn ức chế cho sinh viên khi mạng WiFi campus chập chờn.
- **Các trạng thái giao diện (States Breakdown):**
  - *Form Ready:* Đã chọn file CV, sẵn sàng bấm gửi.
  - *Loading State:* Nút bấm chuyển sang xoay vòng tròn Spinner trắng, tạm thời khóa chạm.
  - *Network Error:* Hiện Error Banner trên đầu form, dữ liệu chữ và file CV giữ nguyên vẹn.
  - *Success Modal Dialog:* Hộp thoại chúc mừng gửi đơn thành công, cấp mã theo dõi hồ sơ.
- **Ràng buộc Accessibility & Responsive:**
  - Textfield nhập thư ngỏ hỗ trợ cuộn nội dung độc lập, không che khuất bàn phím ảo.

---

### 📱 SCR_06: Alumni Mentors Directory Screen
- **Mục đích sử dụng:** Danh bạ tổng hợp mạng lưới các cựu sinh viên ưu tú của Đại học FPT sẵn sàng hỗ trợ định hướng nghề nghiệp 1-1 cho đàn em.
- **Nội dung & Phân rã Giao diện:**
  - Header: *"Mạng lưới Cựu sinh viên FPT"*.
  - Bộ lọc công ty công nghệ lớn: "Tất cả", "FPT Software", "VNG", "Google", "Shopee", "Ngân hàng / Fintech".
  - Danh sách Thẻ Mentor (Mentor Cards):
    - Avatar 56×56dp có chấm xanh online `#10B981`.
    - Họ tên cựu sinh viên, niên khóa (K12, K13, K14...).
    - Vị trí hiện tại, tên công ty và số năm kinh nghiệm.
    - Lĩnh vực sẵn sàng tư vấn: `Review CV`, `Phỏng vấn Technical`, `Định hướng OJT`.
    - Đánh giá từ sinh viên khóa trước: `5.0 ⭐ (18 buổi tư vấn thành công)`.
    - Nút bấm: *"Đặt lịch tư vấn 1-1"* (Nền Navy `#1B365D`, chữ trắng, cao 48dp).
- **Thuộc User Flow:** User Flow 1 (Tìm kiếm Mentor theo doanh nghiệp mong muốn).
- **Ý đồ Thiết kế (Design Intent):**
  - Khơi dậy sự tự hào và an tâm cho sinh viên khóa dưới thông qua các tấm gương cựu sinh viên thành đạt thực tế từ chính nhà trường.
- **Các trạng thái giao diện (States Breakdown):**
  - *Populated:* Danh sách Mentor hiển thị theo thứ tự đánh giá cao nhất.
  - *Empty State:* Khi chọn bộ lọc công ty không có mentor nào phù hợp.

---

### 📱 SCR_07: Mentor Booking & Session Pass Screen
- **Mục đích sử dụng:** Lựa chọn khung giờ rảnh của cựu sinh viên để thiết lập buổi tư vấn trực tuyến và xuất vé hẹn (Session Pass) có link Google Meet.
- **Nội dung & Phân rã Giao diện:**
  - Thẻ tóm tắt thông tin Mentor được chọn.
  - Thanh chọn ngày trong tuần (Horizontal Date Strip).
  - Khung chọn giờ rảnh trong ngày (Time Slots Grid): `09:00 - 09:45`, `14:00 - 14:45`, `20:00 - 20:45`.
  - Ô nhập chủ đề trao đổi: *"Chủ đề bạn muốn nhờ Mentor tư vấn"*.
  - Nút bấm chính: *"XÁC NHẬN ĐẶT LỊCH HẸN (QUA GOOGLE MEET)"*.
  - **Hộp thoại xác nhận 2 bước (Confirmation Modal Dialog - Kết quả Vòng lặp AI 1):**
    - Hộp thoại bật lên ở tâm màn hình yêu cầu xác nhận ngày giờ và tên Mentor trước khi chốt lịch, kèm 2 nút *"Hủy bỏ"* và *"Xác nhận đặt lịch"*.
  - **Thẻ lịch hẹn Session Pass (Sau khi đặt thành công):**
    - Mã lịch hẹn duy nhất: `SES-2026-SE193059-01`.
    - Trạng thái trực quan: `● ĐÃ XÁC NHẬN` (Xanh lá).
    - Đường dẫn phòng họp Google Meet tự động tạo.
    - Nút hành động: *"Thêm vào Google Calendar"* và dòng liên kết *"Hủy lịch hẹn này"*.
- **Thuộc User Flow:** **User Flow 1 (Đích đến đặt lịch)** và **User Flow 3 (Xử lý trùng giờ & Hủy lịch)**.
- **Ý đồ Thiết kế (Design Intent):**
  - Tự động hóa và chuẩn mực hóa toàn bộ quy trình kết nối: Không mất thời gian nhắn tin thương lượng giờ giấc, hạn chế tối đa việc quên lịch nhờ tích hợp Google Calendar.
- **Các trạng thái giao diện (States Breakdown):**
  - *Booking Form:* Chọn ngày giờ và nhập chủ đề.
  - *Conflict Alert Dialog (User Flow 3):* Khi slot vừa bị người khác đặt trước, popup cảnh báo và tự động tô sáng 2 khung giờ rảnh kế tiếp.
  - *Confirmation Dialog:* Xác nhận trước khi tạo lịch hoặc xác nhận hủy lịch nhường chỗ.
  - *Session Pass Active:* Hiển thị thẻ thông tin buổi hẹn đầy đủ.
- **Ràng buộc Accessibility & Responsive:**
  - Các ô chọn giờ (Time Slot Chips) có diện tích cảm ứng tối thiểu **48 × 48 dp**.

---

### 📱 SCR_08: Profile & My Network Screen
- **Mục đích sử dụng:** Trung tâm quản lý cá nhân của sinh viên, theo dõi tiến độ các đơn xin Referral, quản lý lịch hẹn tư vấn và lưu trữ hồ sơ CV.
- **Nội dung & Phân rã Giao diện:**
  - Thẻ thông tin cá nhân: Avatar sinh viên, Họ tên (*"Trương Chí Trung"*), MSSV (*"SE193059"*), Chuyên ngành (*"Kỹ thuật phần mềm - Khóa K19"*).
  - Thanh tab chuyển đổi quản lý:
    - **Tab 1: "Lịch tư vấn của tôi":** Các buổi hẹn 1-1 sắp tới, nút mở link Google Meet, nút khởi tạo yêu cầu hủy lịch hẹn.
    - **Tab 2: "Hồ sơ xin Referral":** Danh sách các công việc đã nộp CV kèm trạng thái xử lý (*"Đang chờ cựu SV phản hồi"* / *"Đã nhận Referral"*).
    - **Tab 3: "Bài viết đã lưu":** Danh sách các bài chia sẻ kinh nghiệm đã Bookmark từ `SCR_02`.
  - Danh mục Cài đặt (Settings ListTile): Đổi chuyên ngành quan tâm, Cài đặt thông báo tin OJT mới, Đăng xuất tài khoản.
- **Thuộc User Flow:** Phục vụ cả 3 Flows (Xem bài đã lưu, Theo dõi tiến độ hồ sơ, Khởi tạo hủy lịch nhường chỗ).
- **Ý đồ Thiết kế (Design Intent):**
  - Tạo bảng điều khiển tập trung giúp sinh viên chủ động nắm bắt toàn bộ các cơ hội phát triển nghề nghiệp và các mối quan hệ với cựu sinh viên trường.
- **Các trạng thái giao diện (States Breakdown):**
  - *Populated:* Danh sách lịch hẹn và đơn ứng tuyển đang hoạt động.
  - *Empty State:* Khi chưa có đơn xin Referral nào: Gợi ý khám phá Tab Việc làm `SCR_04`.
  - *Logout Confirmation Dialog:* Hộp thoại xác nhận đăng xuất tài khoản.
