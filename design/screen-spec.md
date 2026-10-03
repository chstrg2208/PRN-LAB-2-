# 📱 Screen Specifications: Detailed Design Intent & Content Breakdown
**Dự án:** F-Event — FPT Campus Event Hub  
**Môn học:** PRM323 — Cross-Platform Application Development  
**Sinh viên thực hiện:** Nguyễn Minh Tú (MSSV: SE193059)  

---

## 1. Danh sách 8 Màn hình Độc lập trong Hệ thống

Hệ thống bao gồm 8 màn hình riêng biệt (không tính dialog hay các state variants), mỗi màn hình được thiết kế nhằm phục vụ một nhiệm vụ cụ thể của sinh viên và liên kết chặt chẽ vào 3 User Flows:

```
SCR_01: Authentication / Sign-in Screen (Đăng nhập FPT Edu Google OAuth)
SCR_02: Home / Discover Screen (Khám phá & Bộ lọc sự kiện)
SCR_03: Event Detail Screen (Chi tiết sự kiện, diễn giả & Sticky CTA)
SCR_04: Event Registration Screen (Form điền thông tin đăng ký vé)
SCR_05: Ticket Pass / QR Check-in Screen (Vé điện tử & Mã QR điểm danh)
SCR_06: My Schedule Screen (Quản lý lịch sự kiện cá nhân & Waitlist)
SCR_07: Notifications Screen (Thông báo nhắc lịch FCM & Mở slot)
SCR_08: Profile & PDP Tracking Screen (Hồ sơ sinh viên & Điểm rèn luyện)
```

---

## 2. Đặc tả Chi tiết Từng Màn hình

---

### 🖥️ SCR_01: Authentication / Sign-in Screen
- **Mục đích sử dụng:** Xác thực danh tính sinh viên Đại học FPT thông qua tài khoản Google Workspace giáo dục (`@fpt.edu.vn`) ngay khi mở ứng dụng lần đầu hoặc khi hết hạn phiên đăng nhập.
- **Nội dung hiển thị:**
  - Logo ứng dụng **F-Event** với biểu tượng vé sự kiện cách điệu cùng màu cam FPT.
  - Tiêu đề chào đón: *"Chào mừng bạn đến với F-Event — Không gian sự kiện FPT University"*.
  - Nút bấm chính một chạm: *"Tiếp tục với Email FPT Edu (@fpt.edu.vn)"* có logo Google chuẩn.
  - Bộ chọn phân hiệu cơ sở (Dropdown Campus): TP. Hồ Chí Minh, Hòa Lạc (Hà Nội), Đà Nẵng, Cần Thơ, Quy Nhơn.
  - Dòng cam kết bảo mật thông tin sinh viên và điều khoản sử dụng.
- **Thuộc User Flow:** Flow khởi đầu bắt buộc (Onboarding & Authentication Flow).
- **Ý đồ thiết kế (Design Intent):**
  - Giảm thiểu tối đa ma sát (Zero Friction): Sinh viên không cần đăng ký tài khoản mới, chỉ cần 1 lần bấm xác thực tài khoản Google sẵn có trên điện thoại.
  - Tự động đồng bộ hóa thông tin sinh viên (Họ tên, MSSV, Khoa) từ tài khoản trường cho các bước đăng ký vé về sau.

---

### 🖥️ SCR_02: Home / Discover Screen
- **Mục đích sử dụng:** Trung tâm khám phá sự kiện, giúp sinh viên nắm bắt tin tức nóng nhất, lọc workshop theo chuyên môn và tìm kiếm các hoạt động phù hợp với thời khóa biểu.
- **Nội dung hiển thị:**
  - Header cá nhân hóa: Lời chào *"Xin chào, Tú Nguyễn"*, phân hiệu *"Campus TP.HCM"*, và Avatar tròn có badge cam.
  - Thanh tìm kiếm tương tác (Search Bar): Kèm nút mở bộ lọc nâng cao (Filter).
  - Thanh cuộn ngang các chip danh mục (Category Chips): "Tất cả", "💻 Công nghệ / Tech", "🎵 Âm nhạc / Nghệ thuật", "⚽ Thể thao", "💼 Hội thảo Doanh nghiệp".
  - Banner Hero sự kiện nổi bật trong tuần (Featured Banner): Ảnh chất lượng cao, tên workshop "GenAI with Flutter & Dart", ngày giờ, địa điểm "Hall Alpha", badge "+5 Điểm PDP", nút "Xem vé ngay".
  - Danh mục sự kiện sắp diễn ra (Upcoming Events List): Danh sách dạng thẻ Card dọc, mỗi thẻ hiển thị ảnh bìa, danh mục, thời gian, số chỗ còn lại (ví dụ: *"Còn 18/100 slots"*), và nút "Đăng ký".
  - Thanh điều hướng đáy (Bottom Navigation Bar) gồm 4 tab cố định.
- **Thuộc User Flow:** User Flow 1 (Điểm bắt đầu Khám phá & Đăng ký sự kiện).
- **Ý đồ thiết kế (Design Intent):**
  - Tối ưu quét mắt nhanh: Áp dụng quy tắc F-pattern, sinh viên dễ dàng định vị ngay sự kiện hot nhất ở nửa trên màn hình và cuộn nhanh danh sách bên dưới bằng 1 ngón tay cái.

---

### 🖥️ SCR_03: Event Detail Screen
- **Mục đích sử dụng:** Cung cấp thông tin toàn diện, minh bạch về sự kiện, diễn giả, quyền lợi điểm rèn luyện PDP, và thúc đẩy hành động đăng ký giữ chỗ trước khi hết slot.
- **Nội dung hiển thị:**
  - Ảnh bìa Hero tỷ lệ 16:9 sắc nét, có nút Back và nút Bookmark/Lưu vé trên góc trên.
  - Tiêu đề sự kiện H1 20sp Bold, tên câu lạc bộ bảo trợ (CLB F-Code).
  - Khối thông tin nhanh (Quick Info Cards): Icon lịch ngày giờ (15/10/2026, 13:30 - 16:30), Icon địa điểm (Hội trường Alpha, Tòa nhà Innovation).
  - Badge quyền lợi điểm rèn luyện: Nổi bật với nền cam nhạt *"Được cộng +5 Điểm PDP sau khi điểm danh"*.
  - Nội dung mô tả chi tiết: Giới thiệu nội dung workshop, kiến thức thu nhận được, yêu cầu chuẩn bị laptop/công cụ.
  - Khối thông tin diễn giả (Speaker Info): Ảnh chân dung, họ tên, chức danh chuyên gia từ doanh nghiệp đối tác.
  - **Sticky Bottom Action Bar:** Luôn cố định ở chân màn hình, hiển thị số chỗ trực thời (ví dụ: *"Còn 18/100 slots"*) và nút bấm chính *"ĐĂNG KÝ THAM GIA"* (hoặc *"THAM GIA DANH SÁCH CHỜ"* nếu đã hết chỗ).
- **Thuộc User Flow:** User Flow 1 (Xem thông tin) & User Flow 3 (Điểm phát hiện Hết slot / Waitlist).
- **Ý đồ thiết kế (Design Intent):**
  - Giải quyết triệt để vấn đề Visual Hierarchy đã được khắc phục qua Vòng lặp 1: Người dùng không phải cuộn hết trang để tìm nút đăng ký. Nút CTA luôn thường trực giúp tỷ lệ chuyển đổi đạt tối đa.

---

### 🖥️ SCR_04: Event Registration / Checkout Form Screen
- **Mục đích sử dụng:** Thu thập và xác nhận thông tin sinh viên đăng ký tham gia sự kiện một cách nhanh chóng, chính xác, không sai sót.
- **Nội dung hiển thị:**
  - Top App Bar có nút Back và tiêu đề *"Xác nhận Đăng ký"*.
  - Thẻ tóm tắt sự kiện nhỏ gọn (Tên sự kiện, ngày giờ, địa điểm).
  - Các trường thông tin sinh viên tự động điền sẵn (Pre-filled): Họ và tên ("Nguyễn Minh Tú"), Mã số sinh viên ("SE193059"), Email sinh viên ("tuntse193059@fpt.edu.vn").
  - Tùy chọn hình thức tham gia (Radio Button): "Tham gia Trực tiếp tại Hội trường (Offline)" hoặc "Xem Livestream (Online)".
  - Trường văn bản mở rộng: *"Câu hỏi bạn muốn gửi trước cho diễn giả (không bắt buộc)"*.
  - Hộp kiểm điều khoản: *"Tôi cam kết tham gia đúng giờ và tuân thủ quy định hội trường"*.
  - Nút bấm CTA lớn chân trang: *"XÁC NHẬN ĐĂNG KÝ VÉ"* (có tích hợp Loading Spinner khi bấm gửi).
  - Error Banner (trạng thái ngoại lệ): Hiển thị khi mất kết nối mạng kèm nút "Thử lại (Retry)".
- **Thuộc User Flow:** User Flow 1 (Điền thông tin vé) & User Flow 3 (Phục hồi lỗi mất mạng).
- **Ý đồ thiết kế (Design Intent):**
  - Tối giản thao tác nhập liệu: Do thông tin MSSV và Email đã được hệ sinh thái FPT Edu xác thực, sinh viên chỉ mất chưa đầy 10 giây để chọn hình thức tham gia và nhấn xác nhận.

---

### 🖥️ SCR_05: Ticket Pass / Dynamic QR Check-in Screen
- **Mục đích sử dụng:** Đóng vai trò là chiếc vé vào cửa điện tử thông minh, hiển thị mã QR động phục vụ điểm danh không chạm tại sảnh hội trường và quản lý trạng thái vé.
- **Nội dung hiển thị:**
  - Thẻ vé điện tử dạng card bo góc nổi khối, có vết cắt khuyết vé đặc trưng (Ticket notch design).
  - Header vé màu cam FPT hiển thị tên sự kiện, thời gian, vị trí ghế ngồi.
  - Badge trạng thái vé rõ ràng: Có icon + text: `● VÉ HỢP LỆ` (Màu xanh lá) / `● ĐÃ ĐIỂM DANH` (Màu xanh lục đậm) / `● ĐÃ HỦY VÉ` (Màu xám).
  - **Mã QR Code động:** Nằm ở trung tâm vé, tự động tăng độ sáng màn hình lên 100% khi sinh viên mở trang để máy quét dễ nhận diện.
  - Thông tin sinh viên sở hữu vé: Họ tên, MSSV, Mã vé độc nhất (FEV-2026-SE193059-001).
  - Nút hành động chính: *"LƯU VÉ VÀO BỘ SƯU TẬP ẢNH"* (để dùng offline khi mất sóng).
  - Nút hành động phụ (Hủy vé): *"Hủy đăng ký vé"* dạng Text Link màu xám nhạt (khi bấm sẽ kích hoạt Confirmation Dialog 2 bước).
- **Thuộc User Flow:** User Flow 1 (Đích đến sau khi đăng ký), User Flow 2 (Điểm danh tại cửa), User Flow 3 (Điểm khởi tạo hủy vé nhường slot).
- **Ý đồ thiết kế (Design Intent):**
  - Thiết kế chống gian lận và tối ưu trải nghiệm check-in ngoài đời thực: Mã QR to bản, sắc nét, tương phản tối đa, giúp camera của ban tổ chức quét thành công chỉ trong 1 giây.

---

### 🖥️ SCR_06: My Schedule Screen
- **Mục đích sử dụng:** Quản lý toàn diện lịch trình các sự kiện mà sinh viên đã đăng ký, theo dõi tiến độ tham gia và quản lý trạng thái danh sách chờ.
- **Nội dung hiển thị:**
  - Header trang: *"Lịch trình Sự kiện của tôi"*.
  - Thanh chuyển đổi 3 tab con (Segmented Tab Bar):
    - Tab 1: *"Sắp tới (Upcoming)"* — Hiển thị danh sách vé hợp lệ chuẩn bị diễn ra kèm nút "Mở vé QR".
    - Tab 2: *"Chờ duyệt (Waitlist)"* — Hiển thị các sự kiện đã đăng ký xếp hàng, số thứ tự trong hàng chờ (ví dụ: *"Bạn đang ở vị trí #3"*).
    - Tab 3: *"Lịch sử (History)"* — Danh sách sự kiện đã tham gia trong quá khứ, trạng thái cộng điểm PDP.
  - Thẻ sự kiện trong lịch: Thiết kế dạng hàng ngang với vạch màu biểu thị thời gian bắt đầu còn lại (đếm ngược: 2 ngày, 3 giờ...).
  - Empty State: Hiển thị minh họa lịch học và nút *"Khám phá sự kiện ngay"* khi chưa có vé nào.
- **Thuộc User Flow:** User Flow 2 (Mở vé điểm danh) & User Flow 3 (Quản lý và hủy vé).
- **Ý đồ thiết kế (Design Intent):**
  - Giúp sinh viên kiểm soát trọn vẹn thời gian biểu cá nhân, không bị trùng lịch thi hoặc lịch học trên giảng đường FPT.

---

### 🖥️ SCR_07: Notifications Screen
- **Mục đích sử dụng:** Kênh liên lạc tức thời giữa ban tổ chức nhà trường/CLB với sinh viên qua hệ thống thông báo đẩy (Firebase Cloud Messaging).
- **Nội dung hiển thị:**
  - Top App Bar: Tiêu đề *"Thông báo"*, nút tùy chọn "Đánh dấu đã đọc tất cả".
  - Bộ lọc thông báo: "Tất cả", "Nhắc lịch", "Cập nhật slot".
  - Danh sách thẻ thông báo theo thời gian (Hôm nay, Hôm qua, Tuần trước):
    - *Thông báo Nhắc lịch (Event Reminder):* Icon đồng hồ màu cam — *"Workshop GenAI sẽ diễn ra sau 1 giờ nữa tại Hội trường Alpha. Đừng quên mang theo laptop!"*.
    - *Thông báo Mở slot Waitlist:* Icon vé chúc mừng — *"Tin vui! Bạn đã có 1 slot chính thức cho F-Acoustic Night. Bấm để nhận vé ngay trong 15 phút"*.
    - *Thông báo Đổi phòng/giờ:* Icon cảnh báo — *"Thông báo: Workshop Flutter chuyển từ phòng 204 sang Hội trường Alpha"*.
    - *Thông báo Điểm PDP:* Icon ngôi sao — *"Chúc mừng bạn đã được ghi nhận +5 điểm rèn luyện PDP"*.
  - Badge chấm tròn màu cam biểu thị thông báo mới chưa đọc.
- **Thuộc User Flow:** User Flow 2 (Chạm thông báo để mở vé) & User Flow 3 (Nhận thông báo slot trống từ Waitlist).
- **Ý đồ thiết kế (Design Intent):**
  - Đóng vai trò là cầu nối kỹ thuật quan trọng nhất với dịch vụ Firebase Cloud Messaging (FCM) trong Lab 3.

---

### 🖥️ SCR_08: Profile & PDP Tracking Screen
- **Mục đích sử dụng:** Không gian cá nhân của sinh viên, theo dõi tổng kết số điểm rèn luyện PDP đã tích lũy, quản lý sở thích sự kiện và cài đặt tài khoản.
- **Nội dung hiển thị:**
  - Thẻ thông tin sinh viên FPT (Student Profile Card): Avatar, Họ tên, Mã sinh viên (SE193059), Chuyên ngành (Kỹ thuật phần mềm), Khóa (K19).
  - **Khối Tổng kết Điểm Rèn luyện PDP (PDP Progress Dashboard):**
    - Vòng tròn tiến độ trực quan: Hiển thị 85/100 Điểm PDP đã đạt được trong kỳ.
    - Thống kê chi tiết: 12 sự kiện chuyên môn đã tham gia, 3 hoạt động phong trào CLB.
  - Danh mục Cài đặt & Tùy chọn (Settings List):
    - "Chủ đề sự kiện yêu thích" (chọn CLB và thể loại muốn nhận thông báo ưu tiên).
    - "Cài đặt thông báo đẩy" (Bật/tắt nhắc lịch trước 24h và 1h).
    - "Lịch sử tích lũy chứng nhận".
    - "Hỗ trợ & Góp ý cho Ban Tổ chức".
    - Nút "Đăng xuất tài khoản" bằng chữ màu đỏ.
- **Thuộc User Flow:** User Flow 2 (Kiểm tra cập nhật điểm PDP sau sự kiện).
- **Ý đồ thiết kế (Design Intent):**
  - Tạo động lực gamification: Hiển thị thanh tiến độ điểm rèn luyện PDP rõ ràng giúp sinh viên có động lực tích cực tham gia các hoạt động ngoại khóa để hoàn thành chỉ tiêu tốt nghiệp.
