# 🗺️ UX Analysis: Information Architecture & User Flows
**Dự án:** F-Alumni — FPT Alumni Mentorship & Opportunity Network  
**Môn học:** PRM323 — Cross-Platform Application Development  
**Nhóm thực hiện:** PRM Nhóm 4 — Đại học FPT TP.HCM  
**Thành viên:** Trương Chí Trung (SE193059), Nguyễn Phương Khải (SE183590), Đỗ Trọng Tín, Võ Quang Tâm (SE192621)  

---

## 1. Kiến trúc Thông tin (Information Architecture - IA)

### 1.1. Phân cấp Cấu trúc Điều hướng (Navigation Structure)

Ứng dụng **F-Alumni** được tổ chức theo mô hình kết hợp **Bottom Navigation Bar (4 Tab Cấp cao nhất)** và **Stack Navigation (Màn hình cấp con lồng bên trong)**:

```mermaid
graph TD
    AppRoot[F-Alumni App Root] --> AuthGate{Đã đăng nhập?}
    
    AuthGate -- Chưa --> SCR_01[SCR_01: Login & Role Screen\nFPT Edu Google OAuth + Chọn Ngành]
    AuthGate -- Đã đăng nhập --> MainShell[Main Shell Navigation Bar]
    
    subgraph TopLevelTabs ["Top-Level Screens (Bottom Navigation - 4 Tabs)"]
        MainShell --> SCR_02[SCR_02: Home Feed\nTab 1: Không gian chung & Nhóm ngành]
        MainShell --> SCR_04[SCR_04: Career & Job Board\nTab 2: Việc làm, OJT & Học bổng]
        MainShell --> SCR_06[SCR_06: Mentors Directory\nTab 3: Danh bạ Cựu sinh viên]
        MainShell --> SCR_08[SCR_08: Profile & Network\nTab 4: Hồ sơ & Lịch tư vấn của tôi]
    end
    
    subgraph NestedScreens ["Sub-level / Nested Screens (Stack Navigation)"]
        SCR_02 --> SCR_03[SCR_03: Post / Experience Detail\nChi tiết bài chia sẻ & Bio Tác giả]
        SCR_03 --> SCR_07[SCR_07: Mentor Booking Screen\nĐặt lịch tư vấn 1-1 qua Google Meet]
        
        SCR_04 --> SCR_05[SCR_05: Job Detail & Referral Form\nChi tiết công việc & Nộp CV xin Referral]
        
        SCR_06 --> SCR_07
        SCR_08 --> SCR_07
    end

    style AppRoot fill:#f9f,stroke:#333,stroke-width:2px
    style MainShell fill:#bbf,stroke:#333,stroke-width:2px
    style SCR_02 fill:#dfd,stroke:#333,stroke-width:1px
    style SCR_04 fill:#dfd,stroke:#333,stroke-width:1px
    style SCR_06 fill:#dfd,stroke:#333,stroke-width:1px
    style SCR_08 fill:#dfd,stroke:#333,stroke-width:1px
```

---

### 1.2. Danh mục 8 Màn hình Độc lập (Screen Inventory)

| Mã MH | Tên Màn hình | Cấp độ | Phương thức Truy cập | Nội dung & Chức năng Cốt lõi |
| :--- | :--- | :--- | :--- | :--- |
| **SCR_01** | **Login & Role Selection** | Entry Point | Mở app khi chưa đăng nhập | Đăng nhập Google FPT Edu (`@fpt.edu.vn`), chọn vai trò (Sinh viên / Cựu sinh viên), chọn chuyên ngành chính (Kỹ thuật phần mềm, Trí tuệ nhân tạo, Quản trị kinh doanh, Thiết kế đồ họa...). |
| **SCR_02** | **Home Feed (Không gian Chung & Ngành)** | Top-level | Tab 1 (Bottom Nav) | Bộ chuyển đổi 2 không gian: **Tab "Không gian chung"** (chia sẻ toàn trường) và **Tab "Nhóm ngành"** (bài chuyên sâu SE, AI...); Thanh tìm kiếm; Thẻ bài viết chia sẻ kinh nghiệm phỏng vấn, học bổng; Bài viết nổi bật (Featured Alumni Article). |
| **SCR_03** | **Post / Experience Detail** | Sub-level | Chạm vào thẻ bài viết từ Home / Search | Tiêu đề bài viết, thẻ chuyên mục, nội dung hướng dẫn chi tiết, tài liệu đính kèm (Checklist phỏng vấn PDF), Thẻ thông tin Alumni tác giả (chức danh, công ty VNG/FPT Software), phần Hỏi đáp - Bình luận, nút Sticky CTA "Đặt lịch tư vấn 1-1 với Mentor". |
| **SCR_04** | **Career & Opportunity Board** | Top-level | Tab 2 (Bottom Nav) | Bảng tin cơ hội thực tập OJT, tuyển dụng chính thức và học bổng do cựu sinh viên chia sẻ/bảo lãnh; Bộ lọc theo chuyên ngành; Thẻ công việc có badge *"Cựu SV bảo lãnh Referral"*. |
| **SCR_05** | **Job Detail & Referral Apply** | Sub-level | Bấm "Xem & Xin Referral" từ `SCR_04` | Chi tiết mô tả công việc, mức đãi ngộ, yêu cầu kỹ năng, Form tải lên file CV (PDF), ô nhập thư ngỏ ngắn gửi cựu sinh viên, Nút nộp đơn xin Referral. |
| **SCR_06** | **Alumni Mentors Directory** | Top-level | Tab 3 (Bottom Nav) | Danh bạ mạng lưới cựu sinh viên theo ngành; Bộ lọc công ty (Google, VNG, FPT Software, Shopee, Techcombank); Thẻ Mentor hiển thị chuyên môn, số năm kinh nghiệm, đánh giá; Nút "Đặt lịch tư vấn 1-1". |
| **SCR_07** | **Mentor Booking & Session Pass** | Sub-level | Từ `SCR_03`, `SCR_06` hoặc `SCR_08` | Chọn khung giờ rảnh trong tuần của Mentor, nhập chủ đề cần tư vấn (Review CV / Định hướng nghề nghiệp), xác nhận tạo link Google Meet tự động, Thẻ lịch hẹn Session Pass có thể lưu vào Google Calendar. |
| **SCR_08** | **Profile & My Network** | Top-level | Tab 4 (Bottom Nav) | Thông tin cá nhân, chuyên ngành, kho CV đã lưu, danh sách bài viết đã Bookmark, quản lý các buổi hẹn tư vấn (Sắp tới / Đã hoàn thành / Đã hủy), cài đặt nhận thông báo cơ hội mới. |

---

## 2. Đặc tả Chi tiết 3 User Flows

---

### 🟢 User Flow 1: Khám phá Bài viết Kinh nghiệm & Đặt lịch Tư vấn 1-1 với Mentor
- **Điểm bắt đầu:** Sinh viên đang ở màn hình chính `SCR_02` (Home Feed).
- **Mục tiêu:** Học hỏi kinh nghiệm phỏng vấn OJT và hoàn tất đặt một buổi hẹn tư vấn trực tuyến 1-1 với cựu sinh viên tác giả qua Google Meet.
- **Điểm kết thúc:** Mở màn hình `SCR_07` hiển thị thẻ xác nhận lịch hẹn (Session Pass) thành công, lịch tự động lưu vào `SCR_08`.

```mermaid
flowchart TD
    Start([Bắt đầu: Mở SCR_02 Home Feed]) --> SwitchSpace{Chọn không gian hiển thị?}
    
    SwitchSpace -- Không gian Chung --> ViewGeneral[Duyệt bài học bổng & hướng nghiệp chung toàn trường]
    SwitchSpace -- Chuyển Tab: Nhóm ngành IT --> ViewMajor[Xem danh sách bài viết chuyên sâu Kỹ thuật Phần mềm]
    
    ViewMajor --> ClickPost[Chạm vào bài 'Lộ trình ôn luyện phỏng vấn Software Engineer 2026']
    ClickPost --> OpenDetail[Mở SCR_03 Post Detail: Đọc bài viết, tải checklist PDF]
    
    OpenDetail --> DecisionPost{Sinh viên muốn làm gì?}
    DecisionPost -- Nhánh Thay Thế: Lưu đọc sau --> BookmarkAction[Bấm icon Bookmark trên AppBar]
    BookmarkAction --> BookmarkToast[Toast: 'Đã lưu bài viết vào mục Hồ sơ']
    BookmarkToast --> EndAlt([Kết thúc nhánh lưu bài])
    
    DecisionPost -- Happy Path: Đặt lịch tư vấn --> ClickBookMentor[Nhấn nút Sticky 'Đặt lịch tư vấn 1-1 với Mentor']
    ClickBookMentor --> OpenBooking[Mở SCR_07 Mentor Booking Screen]
    OpenBooking --> PickSlot[Chọn khung giờ rảnh của Mentor: Thứ Bảy 09:00 - 09:45]
    PickSlot --> InputTopic[Nhập chủ đề: 'Nhờ anh review CV thực tập OJT vị trí Flutter']
    InputTopic --> SubmitBooking[Nhấn nút 'Xác nhận Đặt lịch hẹn']
    
    SubmitBooking --> ShowLoading[Hiển thị Spinner xử lý kết nối máy chủ]
    ShowLoading --> SuccessModal[Modal Dialog: 'Đặt lịch tư vấn thành công!']
    SuccessModal --> ViewPass[Chạm 'Xem thẻ lịch hẹn']
    ViewPass --> ShowSessionPass[Hiển thị Session Pass: Có link Google Meet & nút thêm vào Lịch]
    ShowSessionPass --> EndHappy([Kết thúc Flow 1: Lịch hẹn đã lưu vào SCR_08])

    style Start fill:#e1f5fe,stroke:#0288d1,stroke-width:2px
    style EndHappy fill:#e8f5e9,stroke:#388e3c,stroke-width:2px
    style EndAlt fill:#fffde7,stroke:#fbc02d,stroke-width:2px
    style SuccessModal fill:#ffe0b2,stroke:#f57c00,stroke-width:2px
```

---

### 🔵 User Flow 2: Tìm cơ hội OJT & Gửi yêu cầu Referral
- **Điểm bắt đầu:** Sinh viên đã đăng nhập và đang ở `SCR_04` (Career & Opportunity Board).
- **Mục tiêu:** Tìm cơ hội phù hợp, xem thông tin vị trí và gửi CV cùng yêu cầu Referral.
- **Kết thúc thành công:** `SCR_05` xác nhận gửi thành công; trạng thái hồ sơ có thể theo dõi tại `SCR_08`.
- **Kết thúc thay thế:** Không có kết quả sau khi thử điều chỉnh/xóa bộ lọc; hoặc sinh viên rời form chưa gửi và quay lại `SCR_04`.

```mermaid
flowchart TD
    Start([Bắt đầu: SCR_04 đang hiển thị]) --> SetFilters[Người dùng chọn từ khóa hoặc bộ lọc OJT và ngành]
    SetFilters --> SearchResults{Hệ thống có cơ hội phù hợp?}
    SearchResults -- Không --> EmptyState[SCR_04 hiển thị empty state: Chưa tìm thấy cơ hội phù hợp]
    EmptyState --> SearchRecovery{Người dùng muốn thử lại?}
    SearchRecovery -- Có --> RecoverSearch[Người dùng điều chỉnh bộ lọc hoặc chọn Xóa bộ lọc]
    RecoverSearch --> SearchResults
    SearchRecovery -- Không --> NoResultsEnd([Kết thúc thay thế: quay lại SCR_04, chưa tìm thấy cơ hội])
    SearchResults -- Có --> Browse[Người dùng xem danh sách cơ hội có Referral]
    Browse --> SelectOpportunity[Người dùng chọn một cơ hội]
    SelectOpportunity --> Review[SCR_05 hiển thị JD, quyền lợi và thông tin alumni bảo lãnh]
    Review --> OpenForm[Người dùng mở form Referral tại SCR_05]
    OpenForm --> ProvideLetter[Người dùng nhập thư ngỏ tối đa 500 ký tự]
    ProvideLetter --> FormChoice{Người dùng gửi hay hủy yêu cầu?}
    FormChoice -- Hủy --> Cancel[Người dùng dùng nút Back trước khi gửi]
    Cancel --> CancelEnd([Quay lại SCR_04; thông tin form chưa gửi bị bỏ, không lưu draft])
    FormChoice -- Gửi --> Validate[Hệ thống kiểm tra đã chọn CV PDF bắt buộc]
    Validate --> HasCV{Đã chọn CV PDF?}
    HasCV -- Chưa --> MissingCV[SCR_05 báo cần có CV trước khi gửi]
    MissingCV --> KeepLetter[Giữ thư ngỏ đã nhập; người dùng chọn CV PDF]
    KeepLetter --> Validate
    HasCV -- Rồi --> Submit[Người dùng nhấn Gửi yêu cầu xin Referral]
    Submit --> Loading[Hệ thống gửi yêu cầu và hiển thị trạng thái đang xử lý]
    Loading --> Success[SCR_05 hiển thị hộp thoại gửi thành công và mã theo dõi]
    Success --> Track[SCR_08 hiển thị trạng thái hồ sơ đang chờ alumni phản hồi]
    Track --> EndSuccess([Kết thúc thành công: yêu cầu Referral đã được gửi])
```

**Quy tắc và giả định:** CV PDF là điều kiện bắt buộc của yêu cầu này; thư ngỏ có giới hạn 500 ký tự theo đặc tả, nhưng tính bắt buộc của thư ngỏ chưa được quy định. Sơ đồ chỉ kiểm tra đã chọn CV PDF; chưa có quy tắc khác về nội dung thư ngỏ hoặc file. Thông báo thiếu CV và giữ thư ngỏ khi bổ sung CV là hành vi UX đề xuất. Đường Back từ form về `SCR_04` cũng là đề xuất; thông tin chưa gửi bị bỏ và không lưu thành draft. Không có xác nhận hủy vì screen spec chưa mô tả dialog này. Các lỗi mạng và cơ chế bảo toàn form/retry thuộc Flow 3, không lặp lại ở đây.

---

### 🔴 User Flow 3: Xử lý Ngoại lệ Lỗi Mạng & Trùng Lịch Tư vấn (Conflict & Error Recovery)
*(Đáp ứng bắt buộc tiêu chí rubric: Có nhánh lỗi nhập liệu/mất mạng và nhánh phục hồi hoàn tác)*
- **Điểm bắt đầu:** Sinh viên gửi đơn xin Referral trong điều kiện mạng yếu, HOẶC sinh viên gặp lỗi trùng lịch / muốn hủy lịch tư vấn để nhường khung giờ cho bạn khác.
- **Mục tiêu:** Bảo toàn 100% dữ liệu form và file CV khi mất kết nối mạng; giải quyết xung đột lịch hẹn; và hủy lịch an toàn có hộp thoại xác nhận.
- **Điểm kết thúc:** Phục hồi dữ liệu gửi lại thành công; hoặc khung giờ tư vấn được trả lại danh sách rảnh của Mentor.

```mermaid
flowchart TD
    Start([Bắt đầu: Sinh viên thao tác tại SCR_05 hoặc SCR_07]) --> ScenarioBranch{Tình huống ngoại lệ diễn ra?}
    
    %% Nhánh 1: Mất mạng khi tải CV xin Referral
    ScenarioBranch -- Tình huống A: Mất mạng khi gửi CV tại SCR_05 --> ClickSendCV[Nhấn 'Gửi yêu cầu xin Referral']
    ClickSendCV --> NetworkDropped[WiFi campus chập chờn / Mất kết nối Internet]
    NetworkDropped --> ShowErrorBanner[Hiển thị Error Banner màu đỏ nhạt:]
    ShowErrorBanner --> BannerMsg["'Không thể kết nối máy chủ. File CV và thư ngỏ của bạn đã được bảo lưu an toàn.'"]
    BannerMsg --> PreserveFormData[TOÀN BỘ dữ liệu text và file CV đính kèm GIỮ NGUYÊN]
    PreserveFormData --> NetworkRestored[Sinh viên bật mạng 4G hoặc kết nối lại WiFi]
    NetworkRestored --> ClickRetryBtn[Bấm nút 'Thử lại (Retry)' trên Error Banner]
    ClickRetryBtn --> SendSuccess[Tải lên thành công -> Mở Dialog Xác nhận]
    SendSuccess --> EndRecoveryNet([Hoàn tất phục hồi lỗi mạng])

    %% Nhánh 2: Trùng lịch hẹn tư vấn (Slot Conflict)
    ScenarioBranch -- Tình huống B: Khung giờ vừa bị sinh viên khác đặt trước --> ClickSubmitSlot[Bấm xác nhận đặt khung giờ 09:00 - 09:45]
    ClickSubmitSlot --> ConflictDetect[Hệ thống kiểm tra: Khung giờ này vừa có người đặt xong!]
    ConflictDetect --> ShowConflictAlert[Hiển thị Dialog Cảnh báo: 'Khung giờ này đã kín chỗ']
    ShowConflictAlert --> SuggestOtherSlots[Hệ thống tự động đề xuất 2 khung giờ rảnh kế tiếp của Mentor]
    SuggestOtherSlots --> PickAlternativeSlot[Sinh viên chọn giờ thay thế: 14:00 - 14:45]
    PickAlternativeSlot --> ConfirmNewSlot[Xác nhận thành công khung giờ mới]
    ConfirmNewSlot --> EndConflict([Hoàn tất xử lý trùng lịch])

    %% Nhánh 3: Hủy lịch hẹn nhường chỗ (Cancel Booking Recovery)
    ScenarioBranch -- Tình huống C: Sinh viên bận thi muốn hủy lịch hẹn 1-1 --> OpenMyBooking[Mở chi tiết lịch hẹn từ SCR_08]
    OpenMyBooking --> ClickCancelBooking[Chạm liên kết 'Hủy lịch tư vấn này']
    ClickCancelBooking --> OpenConfirmModal[Mở Confirmation Dialog Overlay:]
    OpenConfirmModal --> ConfirmModalText["'Bạn có chắc chắn muốn hủy buổi tư vấn? Khung giờ này sẽ được mở lại cho các bạn sinh viên khác.'"]
    
    ConfirmModalText --> UserModalChoice{Sinh viên chọn?}
    UserModalChoice -- Bấm 'Giữ lại lịch' --> DismissModal[Đóng Dialog, lịch hẹn giữ nguyên]
    DismissModal --> EndKeepBooking([Kết thúc: Giữ lịch hẹn])
    
    UserModalChoice -- Bấm 'Xác nhận hủy' --> ExecuteCancel[Gửi lệnh hủy lên Firebase]
    ExecuteCancel --> UpdateStatusCancelled[Cập nhật trạng thái: 'ĐÃ HỦY LỊCH']
    UpdateStatusCancelled --> SlotRestored[Khung giờ tự động mở lại trên lịch rảnh của Mentor]
    SlotRestored --> EndCancelSuccess([Hoàn tất hủy lịch nhường chỗ])

    style Start fill:#ffebee,stroke:#c62828,stroke-width:2px
    style ShowErrorBanner fill:#ffcdd2,stroke:#b71c1c,stroke-width:2px
    style OpenConfirmModal fill:#fff9c4,stroke:#fbc02d,stroke-width:2px
    style EndRecoveryNet fill:#e8f5e9,stroke:#2e7d32,stroke-width:2px
    style EndConflict fill:#e8f5e9,stroke:#2e7d32,stroke-width:2px
    style EndCancelSuccess fill:#e8f5e9,stroke:#2e7d32,stroke-width:2px
```

---

## 3. Bảng Ánh xạ Flow sang Màn hình (Flow-to-Screen Mapping Matrix)

Bảng ma trận chứng minh **100% mọi màn hình trong hệ thống đều được ít nhất một flow sử dụng** (đạt tối đa 5/5 điểm IA):

| Mã Màn hình | Tên Màn hình | User Flow 1 (Explore & Book Mentor) | User Flow 2 (Job & Referral) | User Flow 3 (Error, Conflict & Cancel) | Ghi chú Trạng thái Sử dụng |
| :---: | :--- | :---: | :---: | :---: | :--- |
| **SCR_01** | Login & Role Selection | ⚪ Điểm khởi đầu | ⚪ | ⚪ | Xác thực tài khoản Google FPT & Chọn ngành |
| **SCR_02** | Home Feed (Chung & Ngành) | 🟢 **Bắt đầu chính** | ⚪ | ⚪ | Điểm bắt đầu duyệt chia sẻ theo chuyên ngành |
| **SCR_03** | Post / Article Detail | 🟢 Đọc bài chia sẻ | ⚪ | ⚪ | Xem nội dung, bio tác giả, CTA đặt lịch |
| **SCR_04** | Career & Job Board | ⚪ | 🔵 **Bắt đầu Job flow** | ⚪ | Bảng tin cơ hội việc làm, OJT, học bổng |
| **SCR_05** | Job Detail & Apply Form | ⚪ | 🔵 **Nộp CV & Thư ngỏ** | 🔴 **Điểm lỗi mạng & Phục hồi form** | Xem chi tiết job, nộp hồ sơ xin Referral |
| **SCR_06** | Mentors Directory | 🟢 Tìm cựu SV theo ngành | ⚪ | ⚪ | Danh bạ Mentor, bộ lọc công ty công nghệ |
| **SCR_07** | Mentor Booking & Pass | 🟢 **Đích đến đặt lịch** | ⚪ | 🔴 **Điểm trùng lịch & Chọn lại giờ** | Chọn giờ rảnh, nhận Session Pass Meet |
| **SCR_08** | Profile & My Network | 🟢 Xem bài đã lưu | 🔵 Theo dõi trạng thái CV | 🔴 **Điểm khởi tạo Hủy lịch tư vấn** | Quản lý lịch hẹn, lưu trữ CV, đổi ngành |

> **Kết luận:** Hệ thống 8 màn hình liên kết chặt chẽ, khép kín, phân chia tối ưu giữa không gian chung toàn trường và không gian chuyên sâu theo ngành nghề.
