# 🎓 PRM323 — Lab 2: Thiết kế UI/UX có hỗ trợ AI (Google Stitch → Figma)

> **Môn học:** PRM323 — Cross-Platform Application Development  
> **Giảng viên hướng dẫn:** ThS. Lê Hoàng Phương (@Lam Phuong / PhuonglhK)  
> **Nhóm thực hiện:** PRM Nhóm 4 — Đại học FPT TP. Hồ Chí Minh  
> **Danh sách thành viên & Phân công Vai trò:**  
> 1. **Trương Chí Trung** — MSSV: **SE193059** (Trưởng nhóm / TV2: Google Stitch & AI Lead) → Branch: [`tv2`](https://github.com/chstrg2208/PRN-LAB-2-/tree/tv2)  
> 2. **Võ Quang Tâm** — MSSV: **SE192621** (TV1: UX Research, Persona & User Flow Lead) → Branch: [`tv1`](https://github.com/chstrg2208/PRN-LAB-2-/tree/tv1)  
> 3. **Nguyễn Phương Khải** — MSSV: **SE183590** (TV3: UI Design System & Screen Specifications Lead) → Branch: [`tv3`](https://github.com/chstrg2208/PRN-LAB-2-/tree/tv3)  
> 4. **Đỗ Trọng Tín** — MSSV: **SE190218** (TV4: Figma UI/UX Implementation & Flutter Handoff Lead) → Branch: [`tv4`](https://github.com/chstrg2208/PRN-LAB-2-/tree/tv4)  

---

## 👥 Bảng Phân công Thành viên & Git Branches Mới nhất

Dự án được phân chia thành 4 nhánh Git độc lập tương ứng với 4 thành viên theo đúng quy định làm việc nhóm và lưu vết đóng góp:

| Thành viên | MSSV | Vai trò bài Lab 2 | Git Branch | Trách nhiệm chính trong bài Lab |
| :--- | :--- | :---: | :---: | :--- |
| **Trương Chí Trung** | **SE193059** | **Trưởng nhóm / TV2** | [`tv2`](https://github.com/chstrg2208/PRN-LAB-2-/tree/tv2) | **AI & Prompting:** Thực thi Google Stitch, lưu trữ nguyên văn Prompts, 3 vòng lặp Before/After, phản biện 10 Heuristics & bảng lập luận. |
| **Võ Quang Tâm** | **SE192621** | **TV1** | [`tv1`](https://github.com/chstrg2208/PRN-LAB-2-/tree/tv1) | **UX & User Flow:** Persona, Problem Statement, Information Architecture 8 màn hình, 3 sơ đồ User Flow Mermaid (có luồng phục hồi lỗi). |
| **Nguyễn Phương Khải** | **SE183590** | **TV3** | [`tv3`](https://github.com/chstrg2208/PRN-LAB-2-/tree/tv3) | **Design System & Specs:** Design Tokens (Colors, Typography, 8dp Spacing), đặc tả chi tiết 8 màn hình, Top 10 quyết định thiết kế & Checklist A11y. |
| **Đỗ Trọng Tín** | **SE190218** | **TV4** | [`tv4`](https://github.com/chstrg2208/PRN-LAB-2-/tree/tv4) | **Figma UI/UX & Developer Handoff:** Thiết kế Wireframe (Page 02), hoàn thiện Final UI High-Fidelity (Page 03), dựng Interactive Prototype 4 flows & Overlay Dialogs (Page 06), xuất bộ ảnh 12 màn hình assets/figma/, và soạn thảo toàn diện đặc tả Flutter Handoff 6 mục cho 8 màn hình + 2 bảng mapping dữ liệu/widget. |

---

## 📌 1. Giới thiệu Dự án

- **Tên Ứng dụng:** **F-Alumni — FPT Alumni Mentorship & Opportunity Network**
- **Chủ đề Đề tài:** *Nền tảng kết nối mạng lưới cựu sinh viên Đại học FPT với sinh viên đang theo học, chia sẻ kinh nghiệm phỏng vấn/đồ án, cơ hội việc làm thực tập OJT và học bổng. Ứng dụng phân chia mạch lạc giữa không gian chung toàn trường và không gian chuyên sâu theo từng nhóm ngành nghề.*
- **Persona một dòng (One-Line Persona):**  
  > *"Trương Chí Trung — Sinh viên năm 3 ngành Kỹ thuật Phần mềm (SE) tại Đại học FPT cần một kênh chính thống để học hỏi kinh nghiệm từ cựu sinh viên đi trước, nộp CV xin bảo lãnh Referral việc làm OJT trong dưới 20 giây và đặt lịch tư vấn 1-1 qua Google Meet trong dưới 30 giây."*

---

## 🔗 2. Liên kết Sản phẩm & File Thiết kế Figma

| Hạng mục | Đường dẫn Liên kết Trực tiếp | Trạng thái Quyền Truy cập |
| :--- | :--- | :---: |
| **GitHub Repository Chính thức** | [https://github.com/chstrg2208/PRN-LAB-2-.git](https://github.com/chstrg2208/PRN-LAB-2-.git) | 🌐 **Public** |
| **Figma: 04 Design System & 05 Components** | [Figma: 04 Design System (node-id=1-2)](https://www.figma.com/design/PPdvsVA0O63HEHTQkxBQX0/PRM323---Lab-2---F-Alumni---Nhom-4?node-id=1-2&p=f&t=U1sXeVU5M6L3IEag-0) | 🌐 **Public View** *(Anyone with link)* |
| **Figma: 03 Final UI & 06 Prototype** | [Figma: 03 Final UI & Prototype (node-id=1-3)](https://www.figma.com/design/PPdvsVA0O63HEHTQkxBQX0/PRM323---Lab-2---F-Alumni---Nhom-4?node-id=1-3&t=00FzbJIZRL89FvX4-1) | 🌐 **Public View** *(Anyone with link)* |
| **Google Stitch (Cốt lõi 8 màn hình)** | [https://stitch.withgoogle.com/projects/1771935993966075517](https://stitch.withgoogle.com/projects/1771935993966075517) | 🌐 **Public Project** *(F-Alumni Mentorship App)* |
| **Google Stitch (Bản mở rộng)** | [https://stitch.withgoogle.com/projects/160742887452340129](https://stitch.withgoogle.com/projects/160742887452340129) | 🌐 **Public Project** *(Alumni Connect)* |
| **Design System Vector Asset** | [`assets/figma/04_design_system_and_components.svg`](assets/figma/04_design_system_and_components.svg) | 📦 **Master SVG Asset (1600x2400)** |

---

## 🤖 3. Danh sách Công cụ AI Sử dụng

Tuân thủ quy định Liêm chính Học thuật (Academic Integrity), mọi công cụ AI được sử dụng đều được khai báo rõ ràng mục đích:

1. **Google Stitch (stitch.withgoogle.com):** Sử dụng để tạo phiên bản UI ban đầu từ text prompt cho các màn hình chính (Home Feed, Post Detail, Career Board, Mentor Booking).
2. **Gemini 2.5 / Claude / Antigravity AI:** Đóng vai trò chuyên gia phản biện UX (UX Auditor) đánh giá thiết kế theo 10 Usability Heuristics của Jakob Nielsen và tiêu chuẩn tiếp cận W3C WCAG 2.1.
3. **Figma AI Assistant:** Hỗ trợ kiểm tra độ tương phản màu sắc (Contrast Ratio) và hỗ trợ Auto Layout.

---

## 🗺️ 4. Bản đồ Nơi tìm Từng Sản phẩm (Deliverables Map)

Toàn bộ tài liệu và sản phẩm của bài Lab 2 được tổ chức khoa học theo cấu trúc cây thư mục chuẩn:

```
PRN-LAB-2-/
├── README.md                      ← Bản đồ tổng quan dự án và thông tin thành viên
├── ux/
│   ├── persona.md                 ← Persona chi tiết Trương Chí Trung, bối cảnh OJT, problem statement, success metric
│   └── user-flow.md               ← Information Architecture (IA) 8 màn hình + 3 sơ đồ Mermaid + Ma trận ánh xạ
├── design/
│   ├── DESIGN.md                  ← Bản mô tả thiết kế & Design Tokens (Do TV3 Nguyễn Phương Khải biên soạn)
│   ├── screen-spec.md             ← Đặc tả chi tiết ý đồ và trạng thái 8 màn hình (Do TV3 Nguyễn Phương Khải biên soạn)
│   └── design-decisions.md        ← Top 10 quyết định thiết kế + Checklist A11y & Responsive (Do TV3 biên soạn)
├── ai/
│   └── ai-design-log.md           ← Prompt Stitch nguyên văn, 3 vòng lặp Before/After, phản biện 10 Heuristics
├── assets/
│   ├── stitch/                    ← Ảnh chụp bằng chứng kết quả Google Stitch và Before/After 3 vòng lặp
│   └── figma/                     ← Ảnh export kết quả 8 màn hình hoàn thiện từ Figma
├── handoff/
│   └── flutter-handoff.md         ← Đặc tả 6 mục cho 8 màn hình + 2 bảng mapping + Định hướng Lab 3 Firebase
└── slides/
    ├── SLIDES.md                  ← Toàn văn 12 slides thuyết trình, lời thoại chi tiết & 7 câu hỏi phản biện Q&A
    └── slides.html                ← Bộ trình chiếu Slide tương tác trực tiếp trên trình duyệt (Fullscreen, phím mũi tên)
```

| Sản phẩm Yêu cầu trong Đề bài | Vị trí File Tương ứng trong Repository | Người phụ trách chính | Điểm Trọng số Rubric |
| :--- | :--- | :---: | :---: |
| **1. Vấn đề và Persona** | [`ux/persona.md`](ux/persona.md) | TV1: Võ Quang Tâm | **5 điểm** |
| **2. Phân tích UX & Information Architecture** | [`ux/user-flow.md`](ux/user-flow.md) (Mục 1) | TV1: Võ Quang Tâm | **5 điểm** |
| **3. Ba User Flows hoàn chỉnh (có nhánh lỗi/phục hồi)** | [`ux/user-flow.md`](ux/user-flow.md) (Mục 2 & 3) | TV1: Võ Quang Tâm | **5 điểm** |
| **4. Bản mô tả thiết kế (Design Brief trước khi dùng AI)** | [`design/DESIGN.md`](design/DESIGN.md) | **TV3: Nguyễn Phương Khải** | **Cơ sở prompt** |
| **5. Prompt Google Stitch nguyên văn & Ảnh UI ban đầu** | [`ai/ai-design-log.md`](ai/ai-design-log.md) (Mục 2) | TV2: Trương Chí Trung | **10 điểm** |
| **6. Ba vòng lặp có ý nghĩa (Before / After)** | [`ai/ai-design-log.md`](ai/ai-design-log.md) (Mục 3) | TV2: Trương Chí Trung | **5 điểm** |
| **7. Bản phản biện AI theo 10 Usability Heuristics** | [`ai/ai-design-log.md`](ai/ai-design-log.md) (Mục 4) | TV2: Trương Chí Trung | **5 điểm** |
| **8. Bảng lập luận và quyết định của sinh viên (Có Reject AI)** | [`ai/ai-design-log.md`](ai/ai-design-log.md) (Mục 5) | TV2 & TV3 | **5 điểm** |
| **9. Thiết kế UI/UX cuối cùng & Đặc tả màn hình** | [Figma Page 03](https://www.figma.com/design/PPdvsVA0O63HEHTQkxBQX0/PRM323---Lab-2---F-Alumni---Nhom-4), [`assets/figma/`](assets/figma/) & [`design/screen-spec.md`](design/screen-spec.md) | **TV4: Đỗ Trọng Tín** *(Thiết kế Figma Page 02 & 03)* & **TV3: Nguyễn Phương Khải** *(screen-spec.md)* | **20 điểm** |
| **10. Design System Tokens & 9 Components đủ variants** | [Figma Page 04 & 05](https://www.figma.com/design/PPdvsVA0O63HEHTQkxBQX0/PRM323---Lab-2---F-Alumni---Nhom-4) & [`design/DESIGN.md`](design/DESIGN.md) | **TV3: Nguyễn Phương Khải** | **15 điểm** |
| **11. Interactive Prototype (3 flows, dialog overlay)** | [Figma Page 06](https://www.figma.com/design/PPdvsVA0O63HEHTQkxBQX0/PRM323---Lab-2---F-Alumni---Nhom-4) | **TV4: Đỗ Trọng Tín** *(Lead triển khai Prototype)* & Cả nhóm | **10 điểm** |
| **12. Đặc tả Flutter Handoff & 2 bảng ánh xạ** | [`handoff/flutter-handoff.md`](handoff/flutter-handoff.md) | **TV4: Đỗ Trọng Tín (SE190218)** | **10 điểm** |
| **13. Tính hoàn chỉnh của Tài liệu & Git Repository** | Toàn bộ Repository & [`README.md`](README.md) | **Cả nhóm** | **5 điểm** |
| **14. Bộ Slide Báo cáo & Lời thoại 12 Trang** | [`slides/SLIDES.md`](slides/SLIDES.md) & [`slides/slides.html`](slides/slides.html) | Cả nhóm (4 TV) | **Khung đánh giá 10 phút** |

---

## 🎨 5. Cấu trúc 6 Trang Bắt buộc trong File Figma

File Figma được thiết lập theo đúng thứ tự 6 trang theo yêu cầu của Đề bài:

- **Page 01: User Flow:** Sơ đồ luồng trực quan 3 flows (Đọc bài & Đặt lịch tư vấn, Nộp CV xin Referral, Xử lý lỗi trùng lịch/mất mạng), có liên kết trực tiếp tới các khung màn hình *(TV1: Võ Quang Tâm phụ trách)*.
- **Page 02: Wireframe:** Bản vẽ bố cục Low-Fidelity (thang xám) của toàn bộ 8 màn hình chuẩn kích thước 360 × 800 dp *(TV4: Đỗ Trọng Tín trực tiếp thiết kế)*.
- **Page 03: Final UI:** Toàn bộ 8 màn hình High-Fidelity 360 × 800 dp, đặt cạnh các biến thể trạng thái (Loading Shimmer, Empty State, Error State, Confirmation Dialog) *(TV4: Đỗ Trọng Tín trực tiếp thiết kế & export)*.
- **Page 04: Design System:** Khai báo toàn bộ Design Tokens bằng Figma Variables (Color, Typography, Spacing, Radius, Elevation). Tuyệt đối không gán cứng mã màu *(TV3: Nguyễn Phương Khải phụ trách)*.
- **Page 05: Components:** Thư viện 9 components tái sử dụng dựng bằng Auto Layout 100% và Variants đầy đủ trạng thái *(TV3: Nguyễn Phương Khải phụ trách)*.
- **Page 06: Prototype:** Kết nối tương tác hoàn chỉnh cho 3 flows chính + luồng hủy lịch, thiết lập Flow Starting Point, Overlay Modal Dialog và chuyển cảnh mượt mà *(TV4: Đỗ Trọng Tín trực tiếp thiết lập)*.

---

## ⚡ 6. Sẵn sàng cho Lab 3 (Flutter + Firebase Backend)

Kiến trúc màn hình và mô hình dữ liệu của **F-Alumni** đã được chuẩn bị sẵn sàng để cài đặt trực tiếp bằng Flutter trong bài **Lab 3**:
- **Firebase Auth:** Đăng nhập một chạm Google FPT Edu (`@fpt.edu.vn`).
- **Cloud Firestore:** Quản lý collections `posts`, `jobs`, `mentors`, `bookings`, `users`.
- **Firebase Storage:** Lưu trữ file CV PDF của sinh viên khi nộp hồ sơ xin Referral.
- **Firebase Cloud Messaging (FCM):** Đẩy thông báo khi có tin tuyển dụng/học bổng mới theo ngành và nhắc lịch hẹn tư vấn 1-1.
- **Firebase Remote Config:** Bật/tắt tính năng Referral và thông báo khẩn cấp từ xa.
- **Firebase Crashlytics:** Giám sát lỗi ứng dụng thời gian thực.
