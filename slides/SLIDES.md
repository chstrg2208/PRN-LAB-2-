# 🎯 PRM323 — Laboratory 2: Presentation Slides & Speaker Script
## Đề tài: F-Alumni — FPT Alumni Mentorship & Opportunity Network
> **Môn học:** PRM323 — Cross-Platform Application Development  
> **Giảng viên hướng dẫn:** ThS. Lê Hoàng Phương (@Lam Phuong / PhuonglhK)  
> **Nhóm thực hiện:** PRM Nhóm 4 — Đại học FPT TP. Hồ Chí Minh  
> **Thời lượng phiên đánh giá:** 10 phút thuyết trình (12 slides) + 5 phút Live Demo Figma + 5 phút Q&A  
> **Phân công thuyết trình 4 thành viên:**  
> - **Slide 01 – 04:** **Võ Quang Tâm** (TV1 — MSSV: **SE192621**) | UX Research, Persona, IA & 3 User Flows  
> - **Slide 05 – 07:** **Trương Chí Trung** (Trưởng nhóm / TV2 — MSSV: **SE193059**) | AI UI Generation, 3 Iterations & Design Decisions  
> - **Slide 08 – 10:** **Nguyễn Phương Khải** (TV3 — MSSV: **SE183590**) | Wireframes, Final UI, Design System & Accessibility  
> - **Slide 11 – 12:** **Đỗ Trọng Tín** (TV4 — MSSV: **SE190218**) | Interactive Prototype, Flutter Handoff & Lab 3 Firebase  

---

## 📑 Mục lục 12 Slides Chuẩn Rubric

| Slide | Tên Slide | Người trình bày | Thời lượng | Tài liệu đối chiếu |
| :---: | :--- | :---: | :---: | :--- |
| **01** | **Project Overview: F-Alumni Network** | TV1: Võ Quang Tâm | 45s | `README.md` |
| **02** | **Problem Statement & Target Persona** | TV1: Võ Quang Tâm | 50s | `ux/persona.md` |
| **03** | **Information Architecture (8 Screens)** | TV1: Võ Quang Tâm | 55s | `ux/user-flow.md` |
| **04** | **Three User Flows & Error Recovery** | TV1: Võ Quang Tâm | 60s | `ux/user-flow.md` |
| **05** | **AI UI Generation with Google Stitch** | **TV2: Trương Chí Trung** | **55s** | `ai/ai-design-log.md` |
| **06** | **AI Iterations & UX Critique (10 Heuristics)** | **TV2: Trương Chí Trung** | **60s** | `ai/ai-design-log.md` |
| **07** | **Design Decisions & Student Rationale** | **TV2: Trương Chí Trung** | **50s** | `ai/ai-design-log.md` |
| **08** | **Wireframes vs. Final UI (8 Screens)** | TV3: Nguyễn Phương Khải | 55s | `design/screen-spec.md` |
| **09** | **Design System Tokens & 9 Components** | TV3: Nguyễn Phương Khải | 55s | `design/DESIGN.md` |
| **10** | **Accessibility & Responsive (360dp & 412dp)** | TV3: Nguyễn Phương Khải | 45s | `design/design-decisions.md` |
| **11** | **Interactive Prototype Demonstration** | TV4: Đỗ Trọng Tín | 60s | Figma Page 06 |
| **12** | **Flutter Handoff & Lab 3 Firebase Readiness** | TV4: Đỗ Trọng Tín | 50s | `handoff/flutter-handoff.md` |

---

## 🖥️ Chi tiết Nội dung & Lời thoại Từng Slide

---

### 🌟 SLIDE 01: Project Overview — F-Alumni Network
- **Người thuyết trình:** **Võ Quang Tâm** (TV1 — MSSV: SE192621)  
- **Thời lượng dự kiến:** 45 giây  
- **Bố cục hiển thị trên Slide:**
  - **Tiêu đề lớn:** `F-Alumni — FPT Alumni Mentorship & Opportunity Network`
  - **Sub-headline:** Nền tảng kết nối mạng lưới cựu sinh viên Đại học FPT với sinh viên đang theo học.
  - **3 Thẻ thông tin cốt lõi (Cards):**
    - 🎓 *Không gian chung & Ngành riêng:* Tách biệt giữa kinh nghiệm toàn trường và chuyên sâu (SE, AI, BA, GD...).
    - 💼 *Cơ hội OJT & Referral:* Cựu sinh viên trực tiếp đăng tin và bảo lãnh hồ sơ thực tập.
    - 🤝 *Tư vấn 1-1 Google Meet:* Đặt lịch hẹn cố vấn định hướng nghề nghiệp và review CV.
  - **Liên kết minh chứng trực tiếp:**
    - GitHub: `https://github.com/chstrg2208/PRN-LAB-2-.git`
    - Figma: `Public View (6 Pages)`
    - Google Stitch: `https://stitch.withgoogle.com/projects/1771935993966075517`

> 🎙️ **Lời thoại thuyết trình (Speaker Script):**
> *"Kính chào Thầy và các bạn! Hôm nay PRM Nhóm 4 xin phép được báo cáo bài Lab 2: Thiết kế UI/UX có hỗ trợ AI với đề tài: **F-Alumni — FPT Alumni Mentorship & Opportunity Network**.*  
> *Xuất phát từ thực tế sinh viên FPT bước vào giai đoạn OJT thường gặp khó khăn vì thông tin tuyển dụng, kinh nghiệm phỏng vấn nằm rải rác trên rất nhiều group Facebook, Zalo không chính thống; đồng thời các anh chị cựu sinh viên đi trước rất muốn hỗ trợ đàn em nhưng thiếu một kênh kết nối tin cậy. Nhóm em xây dựng F-Alumni với 3 trụ cột: Chia sẻ kinh nghiệm theo từng nhóm ngành, bảo lãnh Referral việc làm OJT, và đặt lịch tư vấn 1-1 qua Google Meet. Toàn bộ quy trình thiết kế từ Phân tích UX, sinh UI bằng Google Stitch, phản biện 10 Heuristics, dựng Figma đến Flutter Handoff đều đã được đẩy đầy đủ lên GitHub và Figma public của nhóm."*

---

### 👤 SLIDE 02: Problem Statement & Target Persona
- **Người thuyết trình:** **Võ Quang Tâm** (TV1 — MSSV: SE192621)  
- **Thời lượng dự kiến:** 50 giây  
- **Bố cục hiển thị trên Slide:**
  - **Cột trái — Primary Persona Profile:**
    - Họ tên: **Trương Chí Trung** | 20 tuổi | Sinh viên năm 3 K19 ngành Kỹ thuật Phần mềm (SE) Đại học FPT TP.HCM.
    - Thiết bị: Samsung Galaxy A54 (Android 14, độ phân giải chuẩn **360 × 800 dp**, 120Hz).
    - Thói quen: Sử dụng điện thoại một tay bằng ngón cái (`Thumb Zone`), thường xuyên di chuyển giữa các phòng học.
  - **Cột phải — Problem & Measurable Success Criterion:**
    - ⚠️ **Pain Point:** Mất quá nhiều thời gian sàng lọc bài viết trôi nổi, ngần ngại khi nhắn tin xin Referral cựu sinh viên vì không có quy trình chuẩn.
    - 🎯 **Problem Statement (1 câu duy nhất):**  
      > *"Sinh viên năm 3 ngành SE tại Đại học FPT cần một kênh chính thống để học hỏi kinh nghiệm, nộp CV xin bảo lãnh Referral OJT trong dưới 20 giây và đặt lịch tư vấn 1-1 với cựu sinh viên trong dưới 30 giây."*
    - ⏱️ **Tiêu chí thành công đo được (Measurable Success Metrics):**
      - Nộp CV xin Referral thành công: **≤ 20 giây** (ít hơn 3 bước chạm).
      - Đặt lịch tư vấn Google Meet thành công: **≤ 30 giây**.

> 🎙️ **Lời thoại thuyết trình (Speaker Script):**
> *"Để thiết kế bám sát người dùng thực tế, nhóm em xây dựng chân dung người dùng mục tiêu đại diện là bạn Trương Chí Trung, sinh viên K19 chuyên ngành Software Engineering. Trung đang chuẩn bị bước vào kỳ thực tập OJT, sử dụng điện thoại Android Samsung A54 với chuẩn màn hình 360 × 800 dp.*  
> *Nỗi đau lớn nhất của Trung là việc nộp CV và liên hệ mentor hiện nay qua Facebook/Zalo mất từ 2 đến 3 ngày chờ đợi và rất dễ bị trôi tin nhắn. Vì vậy, nhóm em đặt ra bài toán đo lường rõ ràng: F-Alumni phải giúp sinh viên tìm được tin việc làm và nộp CV xin Referral chỉ trong dưới 20 giây, cũng như chọn giờ rảnh của Mentor để chốt lịch Google Meet trong dưới 30 giây mà không cần nhắn tin qua lại."*

---

### 🗺️ SLIDE 03: Information Architecture (8 Screens)
- **Người thuyết trình:** **Võ Quang Tâm** (TV1 — MSSV: SE192621)  
- **Thời lượng dự kiến:** 55 giây  
- **Bố cục hiển thị trên Slide:**
  - **Sơ đồ phân cấp điều hướng (IA Tree Diagram):**
    - Cổng vào: `SCR_01: Login & Role Selection` (Google FPT Edu OAuth).
    - **4 Top-Level Tabs (Bottom Navigation Bar):**
      1. `SCR_02: Home Feed` (Tab Không gian chung toàn trường & Tab Nhóm ngành chuyên sâu).
      2. `SCR_04: Career & Opportunity Board` (Việc làm, OJT & Học bổng cựu SV bảo lãnh).
      3. `SCR_06: Alumni Mentors Directory` (Danh bạ cựu sinh viên & bộ lọc công ty công nghệ).
      4. `SCR_08: Profile & My Network` (Hồ sơ cá nhân, kho CV PDF & lịch tư vấn của tôi).
    - **Các Nested Screens (Màn hình cấp con):**
      - `SCR_03: Post / Experience Detail` (mở từ `SCR_02`).
      - `SCR_05: Job Detail & Referral Apply` (mở từ `SCR_04`).
      - `SCR_07: Mentor Booking & Session Pass` (mở từ `SCR_03`, `SCR_06`, `SCR_08`).
  - **Cam kết số lượng:** Đúng **8 màn hình độc lập** theo yêu cầu của Đề bài, không tính dialog overlay.

> 🎙️ **Lời thoại thuyết trình (Speaker Script):**
> *"Về Kiến trúc thông tin (Information Architecture), F-Alumni được tổ chức theo cấu trúc kết hợp giữa Bottom Navigation Bar 4 tabs cấp cao và Stack Navigation cho các màn hình chi tiết. Hệ thống gồm đúng 8 màn hình độc lập từ SCR_01 đến SCR_08:*  
> *Sau khi đăng nhập một chạm qua Google Edu ở SCR_01, sinh viên truy cập vào Main Shell gồm: Home Feed SCR_02 — nơi có nút chuyển đổi độc đáo giữa không gian chung toàn trường và không gian chuyên ngành SE; Tab 2 là Career Board SCR_04 lọc các tin tuyển dụng OJT; Tab 3 là Danh bạ Mentor SCR_06; và Tab 4 là Profile cá nhân SCR_08. Mọi màn hình con như Chi tiết bài viết SCR_03, Chi tiết nộp CV SCR_05 hay Đặt lịch hẹn SCR_07 đều được liên kết mạch lạc, không tồn tại bất kỳ màn hình mồ côi hay ngõ cụt nào."*

---

### 🔄 SLIDE 04: Three User Flows & Error Recovery
- **Người thuyết trình:** **Võ Quang Tâm** (TV1 — MSSV: SE192621)  
- **Thời lượng dự kiến:** 60 giây  
- **Bố cục hiển thị trên Slide:**
  - **Flow 1: Khám phá kinh nghiệm & Đặt lịch tư vấn 1-1 (Happy Path):**  
    `SCR_01 (Login) → SCR_02 (Home Feed) → SCR_03 (Post Detail) → SCR_07 (Booking) → Nhận thẻ Session Pass`
  - **Flow 2: Tìm kiếm việc làm & Nộp CV xin Referral (Happy Path):**  
    `SCR_04 (Career Board) → Lọc tin OJT → SCR_05 (Job Detail) → Upload file CV PDF → Gửi yêu cầu → SCR_08 (Theo dõi trạng thái)`
  - **Flow 3: Xử lý lỗi trùng lịch hẹn & Phục hồi mất kết nối mạng (Error / Recovery Path):**  
    `SCR_07 → Chọn khung giờ → Hệ thống phát hiện Slot đã có người đặt trước (Conflict 409) → Hiển thị Banner cảnh báo màu vàng + Gợi ý 3 khung giờ thay thế gần nhất → Hoặc khi mất kết nối mạng (No Internet) → Hiển thị SnackBar nút "Thử lại (Retry)" → Giữ nguyên toàn bộ dữ liệu đã điền mà không bắt nhập lại`
  - **Bảng đối chiếu Ma trận ánh xạ (Flow-to-Screen Mapping):** 100% 8 màn hình đều xuất hiện trong ít nhất một User Flow.

> 🎙️ **Lời thoại thuyết trình (Speaker Script):**
> *"Tuân thủ nghiêm ngặt tiêu chí 2.1.3 của Rubric, nhóm em thiết kế 3 User Flows khép kín. Điểm đặc biệt của nhóm là ở Flow số 3: Luồng xử lý lỗi và phục hồi dữ liệu.*  
> *Khi sinh viên đặt lịch ở màn hình SCR_07, nếu khung giờ đó vừa được một bạn khác đặt trước, hệ thống không báo lỗi cứng ngắc mà sẽ kích hoạt cơ chế Smart Recovery: hiển thị banner cảnh báo và tự động đề xuất 3 khung giờ trống gần nhất của Mentor. Tương tự, nếu sinh viên đang nộp CV mà gặp sự cố mạng chập chờn, dữ liệu đã điền sẽ được lưu tạm trong Local State, màn hình hiện nút Retry một chạm mà không bao giờ làm mất file CV hay thư ngỏ sinh viên vừa gõ. Toàn bộ 8 màn hình đều được phủ kín 100% qua ma trận ánh xạ."*

---

### 🤖 SLIDE 05: AI UI Generation with Google Stitch
- **Người thuyết trình:** **Trương Chí Trung** (Trưởng nhóm / TV2 — MSSV: SE193059)  
- **Thời lượng dự kiến:** 55 giây  
- **Bố cục hiển thị trên Slide:**
  - **Toàn văn Prompt Khởi tạo nguyên văn (Verbatim Prompt):**
    - Trích dẫn chính xác prompt đã soạn thảo từ `design/DESIGN.md`:
      > *"Design a clean, modern mobile app interface for F-Alumni... Platform & Constraints: Mobile screen resolution: 360 x 800 dp, Brand Colors: FPT Orange (#F27024), Deep Navy Blue (#1B365D), Background #F8F9FA, Touch target ≥ 48dp, Contrast ≥ 4.5:1 (WCAG 2.1 AA)..."*
  - **Hình ảnh kết quả UI ban đầu xuất từ Google Stitch (4 Screenshots):**
    - `v0_home.png` (Màn hình Home Feed)
    - `v0_detail.png` (Màn hình Chi tiết bài viết)
    - `v0_jobs.png` (Màn hình Cơ hội việc làm & Học bổng)
    - `v0_booking.png` (Màn hình Đặt lịch hẹn Mentor)
  - **Đánh giá ban đầu:** Stitch dựng bố cục tổng thể rất nhanh và nhận diện đúng tông màu FPT, nhưng vẫn tồn tại nhiều lỗi UX thực tế (thiếu confirmation, thiếu empty state, dãn cuộn trang tự động).

> 🎙️ **Lời thoại thuyết trình (Speaker Script):**
> *"Tiếp theo, em là Trương Chí Trung — phụ trách mảng AI Prompting và Google Stitch xin trình bày về giai đoạn tạo UI bằng AI.*  
> *Đúng theo quy trình bắt buộc của đề bài: trước khi mở Google Stitch, nhóm em đã hoàn thiện tài liệu DESIGN.md để làm cơ sở prompt. Prompt của em được soạn thảo nguyên văn với đầy đủ 5 thành tố: Persona người dùng, Nhiệm vụ, Nền tảng Android, Ràng buộc kỹ thuật 360 × 800 dp, touch target 48dp, độ tương phản WCAG 4.5:1 và màu thương hiệu FPT Orange #F27024.*  
> *Bốn ảnh chụp trên slide là kết quả sinh ban đầu từ link dự án Google Stitch thực tế của em. Công cụ AI đã tạo ra khung sườn rất tốt cho 4 màn hình cốt lõi. Tuy nhiên, theo nguyên tắc 'AI generates, Human decides', giao diện này còn nhiều điểm sơ hở về mặt trải nghiệm người dùng, mở đường cho 3 vòng lặp tối ưu hóa tiếp theo."*

---

### 🔄 SLIDE 06: AI Iterations & UX Critique (10 Heuristics)
- **Người thuyết trình:** **Trương Chí Trung** (Trưởng nhóm / TV2 — MSSV: SE193059)  
- **Thời lượng dự kiến:** 60 giây  
- **Bố cục hiển thị trên Slide:**
  - **3 Vòng lặp cải tiến có ý nghĩa (Before / After Evidence):**
    1. **Iteration 1 — Missing Booking Confirmation Modal Dialog:**
       - *Before (`iter1_before.png`):* Bấm đặt lịch nhảy thẳng sang Session Pass, người dùng không kịp kiểm tra lại giờ hẹn.
       - *After (`iter1_after.png`):* Bổ sung Modal Dialog đè mờ (Overlay) tóm tắt: Tên Mentor, Ngày giờ, Link Meet, nút xác nhận cam kết.
    2. **Iteration 2 — Search Empty State on Career Board:**
       - *Before (`iter2_before.png`):* Khi tìm từ khóa không khớp, màn hình trắng trơn gây hoang mang cho sinh viên.
       - *After (`iter2_after.png`):* Thiết kế Empty State thân thiện gồm minh họa kính lúp, dòng chữ hướng dẫn và nút *"Đặt lại bộ lọc tìm kiếm"*.
    3. **Iteration 3 — Job Detail & Referral Apply Flow with CV Upload:**
       - *Before (`iter3_before.png`):* Chỉ có thẻ xem việc làm chung chung, không có nơi nộp hồ sơ.
       - *After (`iter3_after.png` & `iter3_after_part2.png`):* Thêm khối tải file CV PDF, ô nhập thư ngỏ gửi Alumni và nút nộp bảo lãnh.
  - **Phản biện UX theo 10 Usability Heuristics của Jakob Nielsen:**
    - #1 Visibility of system status, #3 User control and freedom, #5 Error prevention, #9 Help users recognize & recover from errors.

> 🎙️ **Lời thoại thuyết trình (Speaker Script):**
> *"Ở giai đoạn vòng lặp và phản biện, em đã không dùng câu lệnh chung chung như 'make it nicer' mà nhắm thẳng vào 3 bài toán UX cụ thể, có bằng chứng Before/After rõ ràng:*  
> *Vòng 1 giải quyết vi phạm Heuristic số 5 (Ngăn ngừa lỗi): Bổ sung Modal Dialog xác nhận trước khi chốt lịch Google Meet để sinh viên không bấm nhầm.*  
> *Vòng 2 giải quyết Heuristic số 9 (Giúp người dùng nhận biết và phục hồi lỗi): Xây dựng màn hình Empty State khi tìm kiếm không có kết quả, có nút xóa bộ lọc thay vì để màn hình trắng xóa.*  
> *Vòng 3 hoàn thiện toàn bộ luồng nộp hồ sơ OJT với form đính kèm CV và thư ngỏ.*  
> *Bản phản biện UX được đối chiếu trực tiếp qua 10 Heuristics của Jakob Nielsen và bộ tiêu chuẩn tiếp cận W3C WCAG 2.1."*

---

### ⚖️ SLIDE 07: Design Decisions & Student Rationale (Reject AI)
- **Người thuyết trình:** **Trương Chí Trung** (Trưởng nhóm / TV2 — MSSV: SE193059)  
- **Thời lượng dự kiến:** 50 giây  
- **Bố cục hiển thị trên Slide:**
  - **Bảng lập luận và quyết định của sinh viên (Accept / Modify / Reject):**
    - ✅ **Quyết định 1 (Accept):** Chấp nhận gợi ý của AI về việc dùng Tab Switcher kép trên Home Feed để sinh viên chuyển đổi nhanh giữa *Không gian chung toàn trường* và *Nhóm ngành SE*.
    - ✏️ **Quyết định 2 (Modify):** Chỉnh sửa đề xuất của AI về việc hiển thị toàn bộ 7 ngày trong tuần dạng lưới dày đặc. Sinh viên sửa thành Horizontal Date Carousel trượt ngang, hiển thị tối đa 3 ngày để bảo đảm touch target 48dp không bị bấm nhầm.
    - ❌ **Quyết định 3 (REJECT AI — Điểm nhấn Rubric):** **Từ chối đề xuất của AI về việc nhúng khung Chatbot AI tự động trả lời thay cho Mentor.**
      - *Lý do từ chối (Justification):* Persona của dự án là sinh viên năm 3 cần sự kết nối thật (Human-to-Human Mentorship) từ cựu sinh viên đang làm việc tại VNG, FPT Software. Chatbot tự động trả lời sẽ làm mất đi giá trị cốt lõi của mạng lưới Alumni và gây giảm sút lòng tin của sinh viên.
  - **Minh chứng:** Toàn bộ quyết định đã được áp dụng trực tiếp vào file Figma và screen specifications.

> 🎙️ **Lời thoại thuyết trình (Speaker Script):**
> *"Tiêu chí quan trọng nhất trong phần AI của Thầy Phương là sinh viên phải chứng minh được năng lực phản biện, biết tiếp thu có chọn lọc chứ không nghe theo AI mù quáng.*  
> *Trên slide là 3 ví dụ điển hình trong Bảng quyết định thiết kế của nhóm em. Chúng em Chấp nhận tab chuyển đổi ngành, Chỉnh sửa thanh chọn ngày thành Carousel trượt ngang để tránh chạm nhầm.*  
> *Đặc biệt, nhóm em đã dứt khoát TỪ CHỐI đề xuất của AI khi nó gợi ý nhúng một chatbot trả lời tự động thay cho Mentor. Nhóm lập luận rằng: Giá trị lớn nhất của F-Alumni là sự kết nối chân thực giữa người với người (Human-to-Human). Sinh viên cần cựu sinh viên thật bảo lãnh Referral và chia sẻ trải nghiệm thực tế; việc nhúng bot AI chung chung sẽ phá vỡ hoàn toàn định vị và niềm tin của người dùng vào sản phẩm!"*

---

### 📐 SLIDE 08: Wireframes vs. Final UI (8 Screens)
- **Người thuyết trình:** **Nguyễn Phương Khải** (TV3 — MSSV: SE183590)  
- **Thời lượng dự kiến:** 55 giây  
- **Bố cục hiển thị trên Slide:**
  - **Cột trái — Low-Fidelity Wireframes (Figma Page 02):**
    - Trình bày 8 màn hình thang xám (Grayscale), tập trung 100% vào phân bố cấu trúc thông tin, phân cấp thị giác (Visual Hierarchy) và luồng đọc từ trên xuống dưới (`F-Pattern`).
  - **Cột phải — High-Fidelity Final UI (Figma Page 03):**
    - 8 màn hình hoàn thiện kích thước chuẩn **360 × 800 dp**, phủ đầy đủ màu sắc thương hiệu, hình ảnh, typography và badge trạng thái.
  - **Bổ sung trạng thái giao diện (UI States Breakdown):**
    - *Loading State:* Shimmer Effect dạng xương (Skeleton Loading) cho danh sách tin việc làm.
    - *Empty State:* Minh họa trực quan khi chưa lưu bài viết nào.
    - *Error State:* Banner cảnh báo màu đỏ với mã màu `#DC2626` khi mất kết nối.
    - *Dialog Overlay:* Modal xác nhận lịch hẹn đè mờ 40% nền đen (`rgba(0,0,0,0.4)`).

> 🎙️ **Lời thoại thuyết trình (Speaker Script):**
> *"Em là Nguyễn Phương Khải, phụ trách UI Design System và Screen Spec xin tiếp nối phần trình bày về Wireframe và Final UI.*  
> *Trên Page 02 của Figma, nhóm em xây dựng bộ khung Low-Fidelity bằng thang xám để thẩm định cấu trúc trước khi lên màu. Đến Page 03 Final UI, toàn bộ 8 màn hình đều được đưa lên kích thước chuẩn di động 360 × 800 dp, áp dụng 100% Auto Layout.*  
> *Để đảm bảo tính Usability theo mục 2.4 của Rubric, nhóm em không chỉ vẽ màn hình tĩnh (Happy Path) mà thiết kế đầy đủ 4 trạng thái giao diện: Shimmer Loading khi chờ tải dữ liệu, Empty State thân thiện, Error State có hướng dẫn phục hồi và Dialog Overlay xác nhận đặt lịch."*

---

### 🎨 SLIDE 09: Design System Tokens & 9 Components
- **Người thuyết trình:** **Nguyễn Phương Khải** (TV3 — MSSV: SE183590)  
- **Thời lượng dự kiến:** 55 giây  
- **Bố cục hiển thị trên Slide:**
  - **Hệ thống Design Tokens (Khai báo bằng Figma Variables / Styles):**
    - *Color Tokens:* `color-primary` (`#F27024` - FPT Orange), `color-secondary` (`#1B365D` - Navy Blue), `color-background` (`#F8F9FA`), `color-surface` (`#FFFFFF`), `color-error` (`#DC2626`), `color-success` (`#16A34A`).
    - *Typography Tokens:* Scale từ 12sp đến 26sp, chữ thân bài (Body) tối thiểu 14sp đảm bảo khả năng đọc.
    - *Spacing Tokens:* Hệ số lưới 8dp chuẩn Material Design (`4dp`, `8dp`, `16dp`, `24dp`, `32dp`).
    - *Radius Tokens:* `radius-sm` (4dp), `radius-md` (8dp), `radius-pill` (999dp).
  - **Thư viện 9 Reusable Components (Đủ 9 danh mục bắt buộc theo Rubric):**
    1. *Button:* Filled, Outlined, Text, Disabled (đầy đủ hover/pressed).
    2. *Text Field:* Default, Focused, Filled, Error (kèm supporting text).
    3. *Card:* Alumni Post Card, Job Referral Card, Mentor Card (Auto Layout).
    4. *Navigation:* Top AppBar (56dp) & Bottom Navigation Bar (4 items, 56dp).
    5. *App Bar:* Back navigation, Share, Bookmark actions.
    6. *Dialog:* Confirmation Modal Overlay bo góc 16dp.
    7. *Loading:* Skeleton Shimmer Card & Circular Progress Indicator.
    8. *Empty:* Empty State Card với Icon minh họa và CTA Action.
    9. *Error:* Error Banner với Icon cảnh báo và nút Retry.
  - **Cam kết kỹ thuật:** 100% màn hình sử dụng Component Instance, tuyệt đối không rã component (`No Detach`).

> 🎙️ **Lời thoại thuyết trình (Speaker Script):**
> *"Ở Page 04 và 05 của Figma, nhóm em thiết lập hệ thống Design System chuẩn mực. Mọi giá trị màu sắc, cỡ chữ, khoảng cách đệm đều được quản lý bằng Figma Variables; tuyệt đối không gán cứng mã màu.*  
> *Về mặt linh kiện, nhóm em hoàn thiện đầy đủ 9 nhóm component bắt buộc theo chuẩn đề bài: từ Button, TextField, Card, Navigation, AppBar, Dialog, Loading, Empty đến Error Component. Toàn bộ component đều được đóng gói bằng Auto Layout và Variants với đầy đủ các trạng thái tương tác như Default, Focused, Error, Disabled. Khi thay đổi mã màu Primary trên Design Token, toàn bộ 8 màn hình trong Figma sẽ tự động cập nhật ngay lập tức."*

---

### ♿ SLIDE 10: Accessibility & Responsiveness (360dp & 412dp)
- **Người thuyết trình:** **Nguyễn Phương Khải** (TV3 — MSSV: SE183590)  
- **Thời lượng dự kiến:** 45 giây  
- **Bố cục hiển thị trên Slide:**
  - **Checklist Tiếp cận WCAG 2.1 AA:**
    - 👁️ *Tỉ lệ tương phản (Contrast Ratio):* Chữ chính trên nền đạt **12.6:1** (vượt xa chuẩn 4.5:1); Chữ phụ đạt **7.1:1**; Nút bấm Primary FPT Orange trên nền trắng đạt **3.2:1** với văn bản Bold lớn.
    - 👆 *Vùng chạm cảm ứng (Touch Target):* Mọi nút bấm, Tab, Chip, ListTile đều đạt kích thước tối thiểu **48 × 48 dp**.
    - 🔤 *Cỡ chữ (Type Size):* Cỡ chữ nhỏ nhất hiển thị nội dung là **14 sp**, nhãn phụ tối thiểu **12 sp**.
    - 🚫 *Không dùng màu đơn độc (Non-color reliant):* Mọi thông báo lỗi và thành công đều đi kèm Icon trực quan (dấu gạch chéo đỏ, dấu tích xanh).
  - **Kiểm tra tương thích Responsive:**
    - Test trực tiếp trên màn hình tiêu chuẩn **360 dp** (Samsung A54, Pixel 7) và màn hình rộng **412 dp** (Galaxy S24 Ultra). Nhờ Auto Layout dạng `Fill Container`, nội dung tự động dãn cách mượt mà, không bị vỡ khung hay tràn chữ.

> 🎙️ **Lời thoại thuyết trình (Speaker Script):**
> *"Về tiêu chuẩn tiếp cận và khả năng co giãn màn hình, nhóm em bám sát checklist WCAG 2.1 tiêu chuẩn AA. Tất cả độ tương phản màu sắc đều được kiểm định bằng Figma Contrast Checker, đạt từ 7.1:1 đến 12.6:1. Vùng chạm trên mọi nút và icon đều có padding bảo đảm tối thiểu 48 × 48 dp, phục vụ tốt cho người dùng thao tác một tay.*  
> *Đồng thời, nhóm em đã kiểm thử giao diện ở cả 2 kích thước 360 dp và 412 dp. Cấu trúc Auto Layout thông minh giúp các thẻ Card tự động co giãn theo chiều ngang mà vẫn giữ nguyên tỷ lệ đệm lề 16dp chuẩn mực."*

---

### 📱 SLIDE 11: Interactive Prototype Demonstration
- **Người thuyết trình:** **Đỗ Trọng Tín** (TV4 — MSSV: SE190218)  
- **Thời lượng dự kiến:** 60 giây  
- **Bố cục hiển thị trên Slide:**
  - **Kịch bản Demo trực tiếp trên Figma Page 06 (Live Demo Roadmap):**
    - **Flow 1:** Từ Home Feed `SCR_02` → Chạm vào bài viết chia sẻ kinh nghiệm phỏng vấn VNG → Xem chi tiết `SCR_03` → Bấm nút Sticky CTA dưới đáy → Mở màn hình Đặt lịch `SCR_07` → Chọn khung giờ → Bấm Xác nhận → **Hiển thị Modal Dialog Overlay** → Chốt lịch → Chuyển cảnh mượt mà đến Thẻ Session Pass Google Meet.
    - **Flow 2:** Chuyển sang Tab Việc làm `SCR_04` → Lọc tin OJT → Mở Job Detail `SCR_05` → Mô phỏng chọn file CV PDF → Bấm Gửi yêu cầu → Hiển thị thông báo thành công và chuyển về Profile `SCR_08` để theo dõi tiến độ duyệt.
    - **Flow 3:** Thử nghiệm chọn trùng giờ hẹn đã có người đặt trước → Hiển thị cảnh báo và chuyển đổi giờ linh hoạt.
  - **Tính năng tương tác hoàn chỉnh:**
    - Có thiết lập **Flow Starting Point** rõ ràng.
    - Hành vi nút **Back vật lý / Back trên AppBar** hoạt động chính xác 100%, không bị văng app.
    - Tuyệt đối **không có ngõ cụt (No Dead Ends)** trong toàn bộ bản vẽ.

> 🎙️ **Lời thoại thuyết trình (Speaker Script):**
> *"Em là Đỗ Trọng Tín — phụ trách phần Prototype và Flutter Developer Handoff. Sau đây em xin phép được tóm lược kịch bản tương tác trên Page 06 của Figma trước khi bước vào 5 phút Live Demo trực tiếp.*  
> *Nhóm em đã kết nối hoàn chỉnh 3 luồng tương tác với các hiệu ứng chuyển cảnh Smart Animate mượt mà. Trong quá trình demo, Thầy sẽ thấy rõ: hiệu ứng Modal Dialog Overlay đè mờ nền khi chốt lịch tư vấn, quá trình chuyển đổi từ Skeleton Shimmer sang dữ liệu thực, và hành vi nút Back luôn đưa người dùng quay lại đúng màn hình trước đó mà không bao giờ rơi vào ngõ cụt."*

---

### 💻 SLIDE 12: Flutter Handoff & Lab 3 Firebase Readiness
- **Người thuyết trình:** **Đỗ Trọng Tín** (TV4 — MSSV: SE190218)  
- **Thời lượng dự kiến:** 50 giây  
- **Bố cục hiển thị trên Slide:**
  - **Hồ sơ Flutter Developer Handoff (`handoff/flutter-handoff.md`):**
    - Cung cấp đầy đủ **6 mục đặc tả kỹ thuật** cho từng màn hình: (1) Cấu trúc cây Widget Layout, (2) Thành phần Component, (3) Quản lý trạng thái State, (4) Thao tác người dùng Interaction, (5) Điều hướng Navigation với GoRouter, (6) Ràng buộc kỹ thuật UI Constraints.
    - **2 Bảng ánh xạ toàn cục:**
      - *Token → Flutter:* Ánh xạ mã màu sang `ColorScheme`, kiểu chữ sang `TextTheme`.
      - *Component → Widget:* Nút sang `FilledButton`, Ô nhập sang `TextFormField`, Thẻ sang `Card`.
  - **Kiến trúc sẵn sàng cho Lab 3 (Flutter + Firebase Backend):**
    - *Firebase Auth:* Đăng nhập một chạm Google Workspace `@fpt.edu.vn`.
    - *Cloud Firestore:* 5 Collections hoàn chỉnh (`posts`, `jobs`, `mentors`, `bookings`, `users`).
    - *Firebase Storage:* Lưu trữ tệp CV PDF của sinh viên nộp Referral.
    - *FCM:* Đẩy thông báo tuyển dụng và nhắc lịch hẹn trước 15 phút.

> 🎙️ **Lời thoại thuyết trình (Speaker Script):**
> *"Khép lại bài báo cáo, nhóm em khẳng định sản phẩm Lab 2 không chỉ dừng lại ở bản vẽ đồ họa mà đã sẵn sàng 100% để đội ngũ lập trình viên cài đặt trực tiếp bằng Flutter trong bài Lab 3 sắp tới.*  
> *Trong file flutter-handoff.md trên GitHub, em đã đặc tả chi tiết cây Widget từ Scaffold, AppBar, ListView đến 2 bảng ánh xạ Token sang ColorScheme và Component sang Flutter Widget chuẩn. Đồng thời, mô hình dữ liệu Cloud Firestore, Firebase Storage lưu file CV và cơ chế Google OAuth @fpt.edu.vn đều đã được thiết kế kiến trúc hoàn thiện.*  
> *Nhóm 4 chúng em xin chân thành cảm ơn Thầy Lê Hoàng Phương đã lắng nghe. Sau đây, nhóm em xin phép được mở Figma để tiến hành phần Live Demo trực tiếp!"*

---

## ❓ 7 Câu Hỏi Giảng Viên Hay Hỏi (Q&A Defense Guide)

Dưới đây là 7 câu hỏi điển hình mà Thầy Lê Hoàng Phương thường hỏi trong 5 phút Q&A và câu trả lời chuẩn giúp nhóm ăn trọn điểm:

### 1. Persona của các em có bối cảnh gì đặc biệt biện minh cho cấu trúc điều hướng này?
> **Trả lời:** *"Dạ thưa Thầy, persona Trương Chí Trung là sinh viên năm 3 đang chịu áp lực chuẩn bị kỳ OJT. Trung cần tiếp cận thông tin tuyển dụng và kinh nghiệm cực kỳ nhanh, thường thao tác bằng một tay trên điện thoại. Do đó nhóm em ưu tiên đưa 2 tab quan trọng nhất là Home Feed và Career Board vào ngay thanh Bottom Navigation Bar ở vùng ngón cái dễ với tới (Thumb Zone), giúp bạn tìm kiếm việc làm chỉ trong dưới 2 bước chạm."*

### 2. Trong 3 User Flows, luồng nào có khả năng phát sinh lỗi cao nhất và hệ thống phục hồi như thế nào?
> **Trả lời:** *"Dạ luồng Đặt lịch tư vấn SCR_07 là dễ phát sinh lỗi nhất do tình trạng xung đột giờ hẹn (2 sinh viên cùng chọn 1 khung giờ trống của Mentor). Hệ thống của tụi em phục hồi bằng cách trả về mã cảnh báo, lập tức khóa slot đó lại và tự động hiển thị gợi ý 3 khung giờ rảnh kế tiếp của Mentor để sinh viên chọn ngay mà không phải quay lại từ đầu."*

### 3. Đâu là đề xuất của AI mà các em đã TỪ CHỐI (Reject), và lý do là gì?
> **Trả lời:** *"Dạ nhóm em đã dứt khoát từ chối đề xuất của AI về việc nhúng Chatbot AI tự động trả lời bài viết. Lý do vì giá trị cốt lõi của F-Alumni là sự kết nối chân thực giữa người với người (Human-to-Human Mentorship); sinh viên cần sự bảo lãnh và kinh nghiệm thực chiến từ cựu sinh viên VNG, FPT Software chứ không muốn đọc câu trả lời chung chung từ máy."*

### 4. Ba vòng lặp (Iterations) của các em đã giải quyết 3 bài toán UX khác nhau như thế nào?
> **Trả lời:** *"Dạ 3 vòng lặp nhắm vào 3 vấn đề có tên riêng biệt: Vòng 1 giải quyết lỗi thiếu hộp thoại xác nhận trước khi chốt lịch (Heuristic #5 Ngăn ngừa lỗi); Vòng 2 giải quyết lỗi màn hình trống khi tìm kiếm thất bại (Heuristic #9 Hướng dẫn phục hồi lỗi); và Vòng 3 giải quyết bài toán thiếu quy trình nộp hồ sơ bằng cách bổ sung form đính kèm file CV PDF và thư ngỏ."*

### 5. Những màn hình nào sẽ tự động thay đổi nếu em đổi một Design Token (ví dụ màu Primary hoặc Spacing)?
> **Trả lời:** *"Dạ thưa Thầy, do 100% 8 màn hình đều dùng Figma Variables và Color Styles liên kết, nên khi em đổi giá trị của token `color-primary` từ cam FPT sang màu khác, toàn bộ nút bấm chính, badge chuyên mục và icon active trên cả 8 màn hình sẽ tự động đổi màu đồng loạt trong 1 giây mà không cần sửa tay từng màn hình."*

### 6. Các em kiểm tra độ tương thích bố cục ở chiều rộng 360 dp và 412 dp như thế nào?
> **Trả lời:** *"Dạ nhóm em thiết lập các thành phần bằng Auto Layout với thuộc tính `Horizontal: Fill container` và lề hai bên cố định 16 dp (`spacing-md`). Khi kéo dãn frame từ 360 dp sang 412 dp của Galaxy S24 Ultra, các thẻ bài viết tự động dãn rộng tương ứng, giữ nguyên cỡ chữ 14sp và không bao giờ bị tràn lề hay gãy dòng chữ."*

### 7. Một lập trình viên Flutter hoàn toàn mới khi nhìn vào Handoff của các em làm sao để dựng được màn hình?
> **Trả lời:** *"Dạ trong file `flutter-handoff.md`, nhóm em đã chia sẵn cấu trúc 6 mục rõ ràng: lập trình viên chỉ cần nhìn vào mục 1 để biết cây Widget Scaffold/Column, nhìn vào mục 2 để lấy đúng Widget trong bảng mapping (ví dụ `FilledButton`), mục 3 để xử lý các khối `isLoading` hay `hasError`, và mục 5 để copy đường dẫn route GoRouter."*
