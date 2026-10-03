# 👤 UX Analysis: Persona & Problem Statement
**Dự án:** F-Event — FPT Campus Event Hub  
**Môn học:** PRM323 — Cross-Platform Application Development  
**Sinh viên thực hiện:** Nguyễn Minh Tú (MSSV: SE193059)  

---

## 1. Primary Persona (Chân dung Người dùng Mục tiêu)

| Thuộc tính | Chi tiết |
| :--- | :--- |
| **Ảnh đại diện** | ![Nguyen Minh Tu Avatar](https://images.unsplash.com/photo-1534528741775-53994a69daeb?auto=format&fit=crop&w=250&q=80) |
| **Họ và tên** | **Nguyễn Minh Tú** |
| **Độ tuổi** | 20 tuổi (Sinh viên năm 3) |
| **Vai trò** | Sinh viên chuyên ngành Kỹ thuật Phần mềm (Software Engineering - SE), Đại học FPT; Thành viên Ban Chuyên môn Câu lạc bộ Lập trình F-Code |
| **Thiết bị sử dụng** | Samsung Galaxy A54 (Android 14, độ phân giải màn hình 360 × 800 dp logic, màn hình 120Hz) |
| **Khuôn viên học tập** | Phân hiệu Đại học FPT (Campus Quận 9, TP.HCM / Hòa Lạc, Hà Nội) |

---

### 1.1. Bối cảnh Hằng ngày (Daily Context)
- **Lịch học theo block:** Tú học các môn chuyên ngành (như PRM323, PRN231, SWD392) theo từng ca cố định kéo dài 3.5 giờ (ca sáng 07:30 – 11:45 hoặc ca chiều 12:30 – 16:45). Xen kẽ giữa các buổi học là các bài tập đồ án nhóm và tự học khóa học online trên Coursera/EdX.
- **Áp lực tích lũy điểm PDP:** Để đủ điều kiện tốt nghiệp và duy trì học bổng khuyến khích, Tú bắt buộc phải tích lũy tối thiểu 100 điểm rèn luyện PDP (Personal Development Program) thông qua các hoạt động hội thảo học thuật, workshop kỹ năng mềm và sự kiện ngoại khóa do trường hoặc các CLB tổ chức.
- **Môi trường hoạt động:** Tú thường xuyên di chuyển giữa các tòa nhà giảng đường, thư viện, sảnh Alpha và hội trường lớn. Tú tranh thủ kiểm tra thông báo và lướt điện thoại trong khoảng 15 phút giải lao giữa các tiết học hoặc khi đang chờ xe buýt/xe công nghệ.

---

### 1.2. Mục tiêu (Goals)
1. **Khám phá sự kiện nhanh chóng:** Nắm bắt tức thời các buổi Tech Talk, Workshop AI/Mobile, cuộc thi Hackathon và sự kiện giao lưu văn hóa phù hợp với thời khóa biểu và sở thích chuyên ngành.
2. **Đăng ký vé (RSVP) chỉ trong vài giây:** Giành được suất tham dự các workshop hot có giới hạn slot (thường chỉ 50 – 100 chỗ) trước khi form đóng.
3. **Check-in điểm danh tự động:** Có mã QR điện tử tiện lợi trên điện thoại để quét tại cửa hội trường trong 3 – 5 giây, bảo đảm chắc chắn được ghi nhận điểm PDP mà không cần xếp hàng ký tên giấy.
4. **Nhắc nhở lịch trình thông minh:** Nhận thông báo đẩy (push notification) nhắc hẹn trước 24 giờ và trước 30 phút để sắp xếp thời gian có mặt đúng giờ.

---

### 1.3. Nỗi đau & Rào cản (Pain Points)
- **Thông tin phân mảnh:** Sự kiện bị phân tán trên hơn 30 Fanpage câu lạc bộ, group Zalo lớp, email phòng CTSV và bảng tin trường. Rất nhiều lần Tú bỏ lỡ workshop bổ ích chỉ vì bài viết bị thuật toán mạng xã hội ẩn đi.
- **"Cháy vé" chớp nhoáng và thiếu Waitlist:** Các workshop có diễn giả nổi tiếng thường hết sạch slot chỉ sau 10 – 15 phút mở cổng. Khi sinh viên vào chậm thì form đã khóa, không có danh sách chờ (Waitlist) để nhận lại slot nếu có bạn khác hủy vé.
- **Điểm danh thủ công rườm rà & mất quyền lợi:** Tại cửa hội trường, ban tổ chức dùng bảng ký tên giấy hoặc yêu cầu quét Google Form dài dòng khiến hàng trăm sinh viên chen lấn. Từng có lần Tú tham gia đầy đủ buổi hội thảo nhưng người điểm danh ghi sót MSSV dẫn tới việc không được cập nhật điểm PDP.
- **Không có cơ chế hủy vé linh hoạt:** Khi có lịch thi bù đột xuất, Tú không thể chủ động hủy vé đã đăng ký, dẫn tới việc lãng phí slot ngồi cho các bạn sinh viên khác đang có nhu cầu thực sự.

---

### 1.4. Thói quen Sử dụng Thiết bị (Device Habits)
- **Thao tác một tay:** Sử dụng ngón tay cái bên phải để cuộn và chạm màn hình trong lúc đang đi bộ trong khuôn viên trường hoặc tay kia cầm tài liệu/balo.
- **Môi trường ánh sáng khắc nghiệt:** Sử dụng điện thoại cả dưới ánh nắng gay gắt ở sân trường (cần tương phản chữ cao, không bị lóa) lẫn trong không gian hội trường tối khi diễn giả đang trình chiếu slide chiếu bóng.
- **Kết nối mạng không ổn định:** Mạng WiFi campus (`FPT_University`) thường bị nghẽn cục bộ vào giờ tan ca hoặc khi hàng trăm người cùng truy cập tại sảnh hội trường tầng hầm.

---

### 1.5. Nhu cầu Khả năng Tiếp cận (Accessibility Needs)
- **Kích thước chữ dễ đọc (WCAG 2.1):** Cỡ chữ nội dung tối thiểu đạt **14 sp** (chuẩn Material Design & WCAG), tiêu đề chính từ **18 – 24 sp**, không dùng các font chữ cách điệu gây khó đọc khi lướt nhanh.
- **Vùng chạm tương tác lớn:** Mọi nút bấm (Button), biểu tượng (Icon Button), và thẻ bấm (Card) phải có kích thước vùng chạm tối thiểu **48 × 48 dp** theo chuẩn WCAG Success Criterion 2.5.5, giúp thao tác một tay chính xác, tránh bấm nhầm.
- **Độ tương phản màu sắc cao (Contrast Ratio):** Văn bản thông thường phải đạt độ tương phản tối thiểu **4.5:1** so với màu nền; các thành phần đồ họa và điều khiển UI đạt tối thiểu **3:1**.
- **Không phụ thuộc vào màu sắc đơn thuần:** Trạng thái sự kiện (Còn slot, Hết slot, Đã đăng ký, Đã hủy) bắt buộc phải đi kèm cả icon và nhãn chữ (Label), không truyền đạt ý nghĩa chỉ bằng màu xanh/đỏ.

---

## 2. Câu Phát biểu Vấn đề (One-Sentence Problem Statement)

> **"Sinh viên Đại học FPT thiếu một kênh tập trung, trực quan để cập nhật kịp thời các sự kiện/workshop trong trường, đăng ký nhanh chóng trước khi hết slot, và lưu trữ mã vé QR điện tử để check-in điểm danh PDP tự động mà không sợ bị bỏ lỡ hay thất lạc quyền lợi."**

---

## 3. Tiêu chí Thành công Đo được (Measurable Success Metric)

> **"Sinh viên có thể tìm kiếm, chọn và hoàn tất đăng ký 1 sự kiện bất kỳ trong vòng dưới 25 giây; và mở mã vé QR check-in trong dưới 5 giây ngay từ màn hình chính."**
