# UX Analysis: Persona & Problem Statement

**Dự án:** F-Alumni — FPT Alumni Mentorship & Opportunity Network  
**Môn học:** PRM323 — Cross-Platform Application Development  
**Nhóm thực hiện:** PRM Nhóm 4 — Đại học FPT TP.HCM

## 1. Primary Persona — Sinh viên FPT

| Thuộc tính | Mô tả |
| --- | --- |
| **Họ và tên** | Trương Chí Trung |
| **Độ tuổi** | 20–22 tuổi *(khoảng tuổi persona đề xuất; tuổi cụ thể chưa được xác minh)* |
| **Vai trò** | Sinh viên năm 3 ngành Kỹ thuật Phần mềm (SE), khóa K19, Đại học FPT TP.HCM; đang chuẩn bị cho kỳ thực tập doanh nghiệp OJT. |
| **Bối cảnh học tập** | Học tại cơ sở Đại học FPT ở Khu Công nghệ cao, TP. Thủ Đức. |
| **Thiết bị chính** | Smartphone Android; hồ sơ hiện tại dùng Samsung Galaxy A54, Android 14, khung tham chiếu 360 × 800 dp. |

### Bối cảnh và hoạt động thường ngày

Trung học các môn chuyên ngành SE, làm bài tập và dự án nhóm, đồng thời chuẩn bị CV và tìm vị trí OJT. Trong giờ nghỉ hoặc khi di chuyển đến trường, Trung thường tranh thủ đọc nội dung nghề nghiệp trên điện thoại. Bạn có nền tảng lập trình nhưng còn thiếu kinh nghiệm phỏng vấn, chuẩn bị CV theo vị trí và lựa chọn hướng phát triển nghề nghiệp. Trung muốn học từ alumni FPT đã trải qua chương trình học tương tự và hiện làm trong ngành.

### Mục tiêu

- Tìm bài chia sẻ kinh nghiệm phỏng vấn, kỹ thuật và OJT phù hợp với ngành SE.
- Khám phá cơ hội OJT, việc làm và học bổng do alumni chia sẻ.
- Gửi CV và yêu cầu referral cho vị trí phù hợp.
- Tìm mentor alumni, đặt lịch tư vấn 1-1 để được review CV hoặc định hướng nghề nghiệp.
- Theo dõi lịch tư vấn và trạng thái hồ sơ đã gửi trong hồ sơ cá nhân.

### Nỗi đau và rào cản

- Khó tìm đúng alumni để hỏi; liên hệ qua mạng xã hội cá nhân có thể bị trôi tin nhắn hoặc khiến Trung ngại làm phiền.
- Bài viết và cơ hội trên các kênh chung lẫn nhiều ngành, khiến việc tìm thông tin phù hợp mất thời gian.
- Nộp hồ sơ đại trà không tạo được kết nối trực tiếp với alumni có thể giới thiệu nội bộ.
- Việc nhắn tin qua lại để thống nhất giờ tư vấn dễ kéo dài hoặc trùng lịch học.
- Wi-Fi ở trường đôi khi chập chờn, có thể làm gián đoạn việc gửi CV hoặc yêu cầu.

### Thói quen sử dụng thiết bị

- Chủ yếu dùng smartphone Android; thường thao tác bằng một tay khi nghỉ giữa giờ hoặc đang di chuyển.
- Đọc bài trong lớp, thư viện hoặc khu vực ngoài trời trong khuôn viên trường.
- Có thể chuyển từ Wi-Fi trường sang mạng di động nếu kết nối không ổn định.

### Nhu cầu tiếp cận

- Nội dung dài cần dễ đọc trên màn hình điện thoại: cỡ chữ nội dung tối thiểu 14 sp và độ tương phản phù hợp.
- Nút hành động, bộ lọc và lựa chọn khung giờ cần vùng chạm đủ lớn (mục tiêu thiết kế 48 × 48 dp).
- Không dùng màu sắc làm dấu hiệu duy nhất; trạng thái cần có nhãn chữ và/hoặc biểu tượng đi kèm.

## 2. Supporting Persona — Cựu sinh viên FPT

> **Persona hỗ trợ, không phải primary persona.** Mô tả dưới đây là giả định thiết kế dựa trên phạm vi tính năng F-Alumni; chưa được xác minh bằng phỏng vấn hoặc nghiên cứu người dùng.

**Vai trò và bối cảnh:** Cựu sinh viên FPT đang làm việc trong ngành chuyên môn của mình, có kinh nghiệm thực tế và có thể chia sẻ bài viết, đăng cơ hội nghề nghiệp, nhận yêu cầu referral hoặc tư vấn sinh viên qua lịch hẹn.

**Mục tiêu và động lực:** Chia sẻ kinh nghiệm cho sinh viên FPT; hỗ trợ người học chuẩn bị nghề nghiệp; duy trì kết nối với cộng đồng trường; giới thiệu ứng viên phù hợp khi có cơ hội.

**Nỗi đau chính:** Thời gian hạn chế; khó tiếp nhận nhiều yêu cầu không phù hợp; trao đổi lịch qua tin nhắn mất công; cần biết rõ chuyên ngành, mục tiêu và thông tin cơ bản của sinh viên trước khi nhận tư vấn hoặc referral.

**Bối cảnh dùng điện thoại:** Có thể xem bài viết, yêu cầu tư vấn và cơ hội nghề nghiệp trên smartphone trong thời gian nghỉ hoặc ngoài giờ làm; cần thao tác ngắn gọn để xem yêu cầu và phản hồi khi thuận tiện. Đây là giả định cần kiểm chứng.

## 3. Problem Statement

Sinh viên năm 3 ngành Kỹ thuật Phần mềm tại Đại học FPT TP.HCM đang chuẩn bị OJT cần một cách đáng tin cậy để tìm kinh nghiệm và cơ hội phù hợp, kết nối với alumni để xin referral hoặc tư vấn, vì thông tin phân tán và việc liên hệ, thống nhất lịch qua các kênh cá nhân làm chậm quá trình chuẩn bị nghề nghiệp.

## 4. Tiêu chí thành công đề xuất

Các ngưỡng dưới đây là **mục tiêu UX đề xuất**, chưa phải kết quả đo từ usability test. Đánh giá trên người tham gia thuộc nhóm sinh viên FPT mục tiêu; ghi nhận thời gian từ lúc màn hình bắt đầu hiển thị đến khi xuất hiện trạng thái hoàn tất được nêu. Tỷ lệ thành công là số người hoàn tất đúng nhiệm vụ chia cho tổng số người bắt đầu nhiệm vụ.

| Nhiệm vụ | Bắt đầu đo | Hoàn tất thành công khi | Cách đo và mục tiêu đề xuất |
| --- | --- | --- | --- |
| **Đặt lịch với mentor từ bài chia sẻ** | Người tham gia đã đăng nhập và `SCR_02` Home Feed hiển thị. | Người tham gia chọn bài phù hợp, mở `SCR_03`, hoàn tất đặt lịch tại `SCR_07` và thấy Session Pass xác nhận; lịch được ghi nhận trong `SCR_08`. | Đo từ lúc `SCR_02` hiển thị đến khi Session Pass xuất hiện; mục tiêu **tỷ lệ hoàn thành độc lập ít nhất 80%** và **trung vị thời gian của các lượt hoàn thành không quá 120 giây**. |
| **Gửi yêu cầu referral cho cơ hội OJT** | Người tham gia đã đăng nhập và `SCR_04` Career & Opportunity Board hiển thị; tệp CV mẫu đã có sẵn trên thiết bị để không tính thời gian chuẩn bị tệp. | Người tham gia mở cơ hội, điền form tại `SCR_05`, gửi yêu cầu và thấy xác nhận thành công/trạng thái hồ sơ. | Đo từ lúc `SCR_04` hiển thị đến xác nhận gửi thành công; mục tiêu **tỷ lệ hoàn thành độc lập ít nhất 80%** và **trung vị thời gian của các lượt hoàn thành không quá 120 giây**. |

## 5. Cơ sở và giới hạn

Persona chính kế thừa bối cảnh sinh viên SE năm 3 chuẩn bị OJT, nhu cầu học từ alumni, referral, mentoring, thiết bị Android và các nhu cầu tiếp cận đã có trong tài liệu dự án. Tuổi 20–22 và persona alumni là giả định biên tập để mô tả nhóm mục tiêu; chưa được kiểm chứng bằng nghiên cứu. Các tiêu chí thành công là ngưỡng đề xuất để kiểm thử, không phải bằng chứng rằng người dùng hiện đã đạt các ngưỡng đó.
