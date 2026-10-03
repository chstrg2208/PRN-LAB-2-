# 🎓 PRM323 — Lab 2: Thiết kế UI/UX có hỗ trợ AI (Google Stitch → Figma)

> **Môn học:** PRM323 — Cross-Platform Application Development  
> **Giảng viên hướng dẫn:** ThS. Lê Hoàng Phương (@Lam Phuong / PhuonglhK)  
> **Sinh viên thực hiện:** Nguyễn Minh Tú  
> **Mã số sinh viên (MSSV):** SE193059  
> **Nhóm thực hiện:** PRM Nhóm 4  
> **Phân hiệu:** Đại học FPT TP. Hồ Chí Minh  

---

## 📌 1. Giới thiệu Dự án

- **Tên Ứng dụng:** **F-Event — FPT Campus Event Hub**
- **Chủ đề Đề tài:** *Ứng dụng khám phá, đăng ký vé trực tuyến và điểm danh sự kiện câu lạc bộ / workshop học thuật tích hợp điểm rèn luyện PDP dành cho sinh viên Đại học FPT.*
- **Persona một dòng (One-Line Persona):**  
  > *"Nguyễn Minh Tú — Sinh viên năm 3 ngành SE tại Đại học FPT cần một kênh tập trung, trực quan để đăng ký workshop công nghệ trong dưới 25 giây và xuất trình mã QR điểm danh nhận điểm rèn luyện PDP tự động trong dưới 5 giây."*

---

## 🔗 2. Liên kết Sản phẩm & File Thiết kế Figma

| Hạng mục | Đường dẫn Liên kết Trực tiếp | Trạng thái Quyền Truy cập |
| :--- | :--- | :---: |
| **Figma Design & Prototype (Bắt buộc)** | [Figma File: PRM323 - Lab 2 - F-Event - SE193059](https://www.figma.com/files/team/1552602956705614495/recents-and-sharing/recently-viewed?fuid=1552602953945079261) | 🌐 **Public View** *(Anyone with the link can view)* |
| **Google Stitch Workspace** | [Google Stitch Project Workspace](https://stitch.withgoogle.com/?pli=1) | Đã xuất UI ban đầu |
| **GitHub Repository** | `https://github.com/<username>/prm323-lab2-se193059` | Chế độ Public |

> [!NOTE]
> Link Figma đã được kiểm tra tính khả dụng trong cửa sổ ẩn danh (Incognito/Private Window) theo đúng **Quy tắc truy cập tại Trang 12 của Đề bài**, bảo đảm người chấm không cần đăng nhập vẫn xem được toàn bộ 6 trang và chạy Prototype tương tác.

---

## 🤖 3. Danh sách Công cụ AI Đã Sử dụng

Tuân thủ quy định Liêm chính Học thuật (Academic Integrity), mọi công cụ AI được sử dụng đều được khai báo rõ ràng mục đích:

1. **Google Stitch (stitch.withgoogle.com):** Sử dụng để tạo phiên bản UI ban đầu từ text prompt cho các màn hình chính (Home, Detail, Register, Ticket Pass).
2. **Claude 3.5 Sonnet / Antigravity AI:** Đóng vai trò chuyên gia phản biện UX (UX Auditor) đánh giá thiết kế theo 10 Usability Heuristics của Jakob Nielsen và tiêu chuẩn tiếp cận W3C WCAG 2.1.
3. **Figma AI Assistant:** Hỗ trợ kiểm tra độ tương phản màu sắc (Contrast Ratio) và gợi ý cấu trúc Auto Layout.

---

## 🗺️ 4. Bản đồ Nơi tìm Từng Sản phẩm (Deliverables Map)

Toàn bộ tài liệu và sản phẩm của bài Lab 2 được tổ chức khoa học theo cấu trúc cây thư mục chuẩn:

```
prm323-lab2-se193059/
├── README.md                      ← Bản đồ tổng quan dự án và thông tin sinh viên
├── ux/
│   ├── persona.md                 ← Persona chi tiết, bối cảnh FPT, problem statement, success metric
│   └── user-flow.md               ← Information Architecture (IA) + 3 sơ đồ Mermaid + Bảng ánh xạ
├── design/
│   ├── DESIGN.md                  ← Bản mô tả thiết kế cho Stitch (Colors, Typography, Spacing, Radius)
│   ├── screen-spec.md             ← Ý đồ thiết kế và nội dung chi tiết của 8 màn hình riêng biệt
│   └── design-decisions.md        ← Top 10 quyết định thiết kế cốt lõi + Checklist Accessibility & Responsive
├── ai/
│   └── ai-design-log.md           ← Prompt Stitch nguyên văn, 3 vòng lặp có ý nghĩa, phản biện Nielsen 10 Heuristics
├── assets/
│   ├── stitch/                    ← Ảnh chụp bằng chứng kết quả Google Stitch và Before/After 3 vòng lặp
│   └── figma/                     ← Ảnh export kết quả 8 màn hình hoàn thiện từ Figma
└── handoff/
    └── flutter-handoff.md         ← Đặc tả 6 mục cho 8 màn hình + 2 bảng mapping + Định hướng Lab 3 Firebase
```

| Sản phẩm Yêu cầu trong Đề bài | Vị trí File Tương ứng trong Repository | Điểm Trọng số Rubric |
| :--- | :--- | :---: |
| **1. Vấn đề và Persona** | [`ux/persona.md`](file:///e:/FPT/Ki%208/PRM/LAB%202%20-%20PRM%20Nhom%204/ux/persona.md) | **5 điểm** |
| **2. Phân tích UX & Information Architecture** | [`ux/user-flow.md`](file:///e:/FPT/Ki%208/PRM/LAB%202%20-%20PRM%20Nhom%204/ux/user-flow.md) (Mục 1) | **5 điểm** |
| **3. Ba User Flows hoàn chỉnh (có nhánh lỗi/phục hồi)** | [`ux/user-flow.md`](file:///e:/FPT/Ki%208/PRM/LAB%202%20-%20PRM%20Nhom%204/ux/user-flow.md) (Mục 2 & 3) | **5 điểm** |
| **4. Bản mô tả thiết kế (Design Brief trước khi dùng AI)** | [`design/DESIGN.md`](file:///e:/FPT/Ki%208/PRM/LAB%202%20-%20PRM%20Nhom%204/design/DESIGN.md) | **Cơ sở prompt** |
| **5. Prompt Google Stitch nguyên văn & Ảnh UI ban đầu** | [`ai/ai-design-log.md`](file:///e:/FPT/Ki%208/PRM/LAB%202%20-%20PRM%20Nhom%204/ai/ai-design-log.md) (Mục 2) | **10 điểm** |
| **6. Ba vòng lặp có ý nghĩa (Before / After)** | [`ai/ai-design-log.md`](file:///e:/FPT/Ki%208/PRM/LAB%202%20-%20PRM%20Nhom%204/ai/ai-design-log.md) (Mục 3) | **5 điểm** |
| **7. Bản phản biện AI theo 10 Usability Heuristics** | [`ai/ai-design-log.md`](file:///e:/FPT/Ki%208/PRM/LAB%202%20-%20PRM%20Nhom%204/ai/ai-design-log.md) (Mục 4) | **5 điểm** |
| **8. Bảng lập luận và quyết định của sinh viên** | [`ai/ai-design-log.md`](file:///e:/FPT/Ki%208/PRM/LAB%202%20-%20PRM%20Nhom%204/ai/ai-design-log.md) (Mục 5) | **5 điểm** |
| **9. Thiết kế UI/UX cuối cùng & Đặc tả màn hình** | [Figma Page 03] & [`design/screen-spec.md`](file:///e:/FPT/Ki%208/PRM/LAB%202%20-%20PRM%20Nhom%204/design/screen-spec.md) | **20 điểm** |
| **10. Design System Tokens & 9 Components đủ variants** | [Figma Page 04 & 05] | **15 điểm** |
| **11. Interactive Prototype (3 flows, dialog overlay)** | [Figma Page 06] | **10 điểm** |
| **12. Đặc tả Flutter Handoff & 2 bảng ánh xạ** | [`handoff/flutter-handoff.md`](file:///e:/FPT/Ki%208/PRM/LAB%202%20-%20PRM%20Nhom%204/handoff/flutter-handoff.md) | **10 điểm** |
| **13. Tính hoàn chỉnh của Tài liệu & Git Repository** | Toàn bộ Repository & [`README.md`](file:///e:/FPT/Ki%208/PRM/LAB%202%20-%20PRM%20Nhom%204/README.md) | **5 điểm** |

---

## 🎨 5. Cấu trúc 6 Trang Bắt buộc trong File Figma

File Figma được thiết lập theo đúng thứ tự 6 trang theo yêu cầu của Đề bài:

- **Page 01: User Flow:** Sơ đồ luồng trực quan 3 flows (Đăng ký, Điểm danh QR, Hủy vé & Xử lý lỗi), có liên kết trực tiếp tới các khung màn hình.
- **Page 02: Wireframe:** Bản vẽ bố cục Low-Fidelity (thang xám) của toàn bộ 8 màn hình chuẩn kích thước 360 × 800 dp.
- **Page 03: Final UI:** Toàn bộ 8 màn hình High-Fidelity 360 × 800 dp, đặt cạnh các biến thể trạng thái (Loading Shimmer, Empty State, Error State, Confirmation Dialog).
- **Page 04: Design System:** Khai báo toàn bộ Design Tokens bằng Figma Variables (Color, Typography, Spacing, Radius, Elevation). Tuyệt đối không gán cứng mã màu.
- **Page 05: Components:** Thư viện 9 components tái sử dụng dựng bằng Auto Layout 100% và Variants đầy đủ trạng thái (Default, Pressed, Disabled, Loading/Error).
- **Page 06: Prototype:** Kết nối tương tác hoàn chỉnh cho 3 flows, thiết lập Flow Starting Point, Overlay Modal Dialog và chuyển cảnh mượt mà.

---

## ⚡ 6. Sẵn sàng cho Lab 3 (Flutter + Firebase Backend)

Kiến trúc màn hình và mô hình dữ liệu của **F-Event** đã được chuẩn bị sẵn sàng để cài đặt trực tiếp bằng Flutter trong bài **Lab 3**:
- **Firebase Auth:** Đăng nhập một chạm Google FPT Edu (`@fpt.edu.vn`).
- **Cloud Firestore:** Quản lý collections `events`, `tickets`, `users`.
- **Firebase Cloud Messaging (FCM):** Đẩy thông báo nhắc lịch và kích hoạt slot trống từ danh sách chờ Waitlist.
- **Firebase Remote Config:** Bật/tắt tính năng đăng ký sớm và thông báo khẩn cấp từ xa.
- **Firebase Crashlytics:** Giám sát lỗi ứng dụng thời gian thực.
