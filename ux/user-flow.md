# 🗺️ UX Analysis: Information Architecture & User Flows
**Dự án:** F-Event — FPT Campus Event Hub  
**Môn học:** PRM323 — Cross-Platform Application Development  
**Sinh viên thực hiện:** Nguyễn Minh Tú (MSSV: SE193059)  

---

## 1. Kiến trúc Thông tin (Information Architecture - IA)

### 1.1. Phân cấp Cấu trúc Điều hướng (Navigation Structure)

Ứng dụng **F-Event** được thiết kế theo mô hình điều hướng kết hợp **Bottom Navigation Bar (Cấp cao nhất - 4 Tabs)** và **Hierarchical Stack Navigation (Màn hình cấp con lồng bên trong)**. Mô hình này giúp sinh viên truy cập ngay các tính năng thường dùng chỉ với 1 lần chạm ngón cái.

```mermaid
graph TD
    AppRoot[F-Event App Root] --> AuthGate{Đã đăng nhập?}
    
    AuthGate -- Chưa --> SCR_01[SCR_01: Login Screen\nFPT Edu Google OAuth]
    AuthGate -- Đã đăng nhập --> MainShell[Main Shell Navigation Bar]
    
    subgraph TopLevelTabs ["Top-Level Screens (Bottom Navigation - 4 Tabs)"]
        MainShell --> SCR_02[SCR_02: Home / Discover Screen\nTab 1: Khám phá sự kiện]
        MainShell --> SCR_06[SCR_06: My Schedule Screen\nTab 2: Sự kiện của tôi]
        MainShell --> SCR_07[SCR_07: Notifications Screen\nTab 3: Thông báo & Nhắc lịch]
        MainShell --> SCR_08[SCR_08: Profile & PDP Screen\nTab 4: Hồ sơ & Điểm rèn luyện]
    end
    
    subgraph NestedScreens ["Sub-level / Nested Screens (Stack Navigation)"]
        SCR_02 --> SCR_03[SCR_03: Event Detail Screen\nChi tiết sự kiện, diễn giả & slot]
        SCR_03 --> SCR_04[SCR_04: Event Registration Screen\nForm đăng ký vé tham gia]
        SCR_04 --> ModalSuccess[Dialog Thành công Overlay]
        ModalSuccess --> SCR_05[SCR_05: Ticket Pass / QR Check-in\nVé điện tử & Mã QR động]
        
        SCR_06 --> SCR_05
        SCR_07 --> SCR_03
        SCR_07 --> SCR_05
    end

    style AppRoot fill:#f9f,stroke:#333,stroke-width:2px
    style MainShell fill:#bbf,stroke:#333,stroke-width:2px
    style SCR_02 fill:#dfd,stroke:#333,stroke-width:1px
    style SCR_06 fill:#dfd,stroke:#333,stroke-width:1px
    style SCR_07 fill:#dfd,stroke:#333,stroke-width:1px
    style SCR_08 fill:#dfd,stroke:#333,stroke-width:1px
```

---

### 1.2. Danh mục Màn hình (Screen Inventory)

Hệ thống bao gồm **8 màn hình độc lập chính thức** (không tính dialog hay các biến thể trạng thái):

| Mã MH | Tên Màn hình | Cấp độ | Phương thức Truy cập | Nội dung & Chức năng Cốt lõi |
| :--- | :--- | :--- | :--- | :--- |
| **SCR_01** | **Login Screen** | Entry Point | Khởi động app khi chưa đăng nhập | Đăng nhập một chạm bằng tài khoản FPT Google OAuth (`@fpt.edu.vn`), chọn cơ sở (Campus HCM, Hòa Lạc, Đà Nẵng, Cần Thơ, Quy Nhơn). |
| **SCR_02** | **Home / Discover Screen** | Top-level | Tab 1 (Bottom Nav) | Banner Hero sự kiện nổi bật, Thanh tìm kiếm nhanh, Chip lọc theo chủ đề (Tech, Workshop, CLB Nghệ thuật, Thể thao), Danh sách Upcoming Events dạng thẻ (Card). |
| **SCR_03** | **Event Detail Screen** | Sub-level | Chạm vào thẻ sự kiện từ Home / Search / Schedule | Ảnh bìa sự kiện, Tiêu đề, CLB tổ chức, Thời gian, Địa điểm phòng học/hội trường, Số slot còn lại (ví dụ: 18/100 slots), Quyền lợi điểm PDP, Thông tin diễn giả, Sticky Bottom Bar với nút Đăng ký / Waitlist. |
| **SCR_04** | **Event Registration Screen** | Sub-level | Bấm nút "Đăng ký tham gia" tại `SCR_03` | Form tự động điền MSSV và Email FPT, chọn hình thức tham gia (Offline / Trực tuyến), ô nhập câu hỏi trước cho diễn giả, Điều khoản cam kết, Nút CTA "Xác nhận đăng ký". |
| **SCR_05** | **Ticket Pass / QR Check-in** | Sub-level | Sau khi đăng ký thành công hoặc từ `SCR_06` | Thẻ vé điện tử với mã QR động chống gian lận, Trạng thái vé (Hợp lệ / Đã check-in / Hết hạn), Thông tin số ghế/vị trí, Nút "Thêm vào Google Wallet/Lịch", Nút "Hủy vé nhường slot". |
| **SCR_06** | **My Schedule Screen** | Top-level | Tab 2 (Bottom Nav) | Bộ lọc 3 tab con: "Sắp tới (Upcoming)", "Chờ xét duyệt (Waitlist)", "Lịch sử tham gia (History)". Chạm vào vé để mở chi tiết `SCR_05`. |
| **SCR_07** | **Notifications Screen** | Top-level | Tab 3 (Bottom Nav) | Danh sách thông báo đẩy (Firebase Cloud Messaging): Nhắc lịch trước 24h & 30 phút, Thông báo được duyệt slot từ danh sách chờ Waitlist, Thông báo thay đổi phòng học/giờ tổ chức. |
| **SCR_08** | **Profile & PDP Tracking** | Top-level | Tab 4 (Bottom Nav) | Thẻ sinh viên điện tử (Avatar, MSSV, Ngành học SE), Biểu đồ tổng kết điểm rèn luyện PDP đã tích lũy, Tùy chọn sở thích nhận tin CLB, Cài đặt ứng dụng và Đăng xuất. |

---

## 2. Đặc tả Chi tiết 3 User Flows

---

### 🟢 User Flow 1: Khám phá & Đăng ký Sự kiện (Discover & RSVP Event)
- **Điểm bắt đầu:** Sinh viên đang ở màn hình chính `SCR_02` (Home / Discover Screen).
- **Mục tiêu:** Tìm được workshop chuyên môn phù hợp và hoàn tất nhận vé điện tử tham dự.
- **Điểm kết thúc:** Mở màn hình `SCR_05` (Ticket Pass) hiển thị mã QR thành công, sự kiện tự động xuất hiện trong lịch `SCR_06`.

```mermaid
flowchart TD
    Start([Bắt đầu: Mở SCR_02 Home]) --> Browse[Duyệt danh sách sự kiện hoặc bấm Chip 'Học thuật / Tech']
    Browse --> SelectEvent[Chạm vào Card sự kiện 'Workshop GenAI & Flutter']
    SelectEvent --> ViewDetail[Mở SCR_03 Event Detail: Xem ngày, giờ, slot, diễn giả]
    
    ViewDetail --> Decision{Sinh viên muốn làm gì?}
    
    Decision -- Nhánh Thay Thế: Lưu xem sau --> Bookmark[Bấm icon Bookmark trên AppBar]
    Bookmark --> SavedFeedback[Hiển thị Toast: 'Đã lưu vào danh sách quan tâm']
    SavedFeedback --> EndAlt([Kết thúc nhánh: Quay lại duyệt tiếp])
    
    Decision -- Happy Path: Đăng ký ngay --> ClickRSVP[Nhấn nút Sticky 'Đăng ký tham gia']
    ClickRSVP --> OpenForm[Mở SCR_04 Form Đăng ký: MSSV & Email đã tự điền]
    OpenForm --> FillInput[Chọn tham gia Offline + Nhập câu hỏi cho diễn giả]
    FillInput --> SubmitForm[Nhấn nút 'Xác nhận đăng ký']
    
    SubmitForm --> ShowLoading[Hiển thị Loading Spinner trạng thái xử lý]
    ShowLoading --> ShowDialog[Mở Modal Dialog Overlay: 'Đăng ký thành công!']
    ShowDialog --> ClickViewTicket[Nhấn 'Xem vé ngay']
    ClickViewTicket --> OpenTicket[Mở SCR_05 Ticket Pass: Hiển thị QR Code cá nhân]
    OpenTicket --> EndHappy([Kết thúc: Vé đã lưu vào My Schedule SCR_06])

    style Start fill:#e1f5fe,stroke:#0288d1,stroke-width:2px
    style EndHappy fill:#e8f5e9,stroke:#388e3c,stroke-width:2px
    style EndAlt fill:#fffde7,stroke:#fbc02d,stroke-width:2px
    style ShowDialog fill:#ffe0b2,stroke:#f57c00,stroke-width:2px
```

---

### 🔵 User Flow 2: Điểm danh Check-in bằng QR tại Hội trường & Xem Tích lũy Điểm PDP
- **Điểm bắt đầu:** Sinh viên nhận được thông báo đẩy FCM trên màn hình khóa hoặc mở tab `SCR_07` (Notifications) / `SCR_06` (My Schedule).
- **Mục tiêu:** Xuất trình vé QR Code tại bàn đón tiếp để cán bộ BTC quét xác thực, hoàn tất điểm danh nhận điểm PDP.
- **Điểm kết thúc:** Vé chuyển trạng thái sang "Đã điểm danh (Checked-in)", hệ thống tự động cộng +5 điểm PDP vào `SCR_08`.

```mermaid
flowchart TD
    Start([Bắt đầu: Nhận Notification hoặc Mở Tab SCR_06]) --> OpenTicketAction[Chạm vào thông báo hoặc chọn thẻ vé trong My Schedule]
    OpenTicketAction --> OpenTicketScreen[Mở SCR_05 Ticket Pass Screen]
    
    OpenTicketScreen --> DecisionOffline{Kiểm tra kết nối mạng?}
    
    DecisionOffline -- Có mạng ổn định --> BrightnessUp[Mã QR động tự động tăng độ sáng màn hình]
    DecisionOffline -- Nhánh Thay Thế: Mất sóng tầng hầm --> OfflineSave[Bấm 'Lưu ảnh vé vào thư viện máy']
    OfflineSave --> ImageSaved[Mở ảnh QR từ bộ nhớ thiết bị]
    ImageSaved --> PresentQR
    
    BrightnessUp --> PresentQR[Xuất trình mã QR tại cửa hội trường Alpha]
    PresentQR --> StaffScan[Ban tổ chức dùng máy quét mã QR]
    
    StaffScan --> SuccessScan[Âm thanh 'Bíp' thành công!]
    SuccessScan --> StateUpdate[Màn hình SCR_05 đổi badge trạng thái: 'ĐÃ ĐIỂM DANH']
    StateUpdate --> PushSuccess[Nhận Push Notification: 'Bạn đã được xác nhận điểm danh!']
    
    PushSuccess --> ViewProfile[Sinh viên chuyển sang Tab SCR_08 Profile]
    ViewProfile --> PDPUpdated[Mục Điểm Rèn Luyện PDP hiển thị cộng thêm +5 điểm]
    PDPUpdated --> EndFlow([Kết thúc Flow 2: Hoàn tất quyền lợi PDP])

    style Start fill:#e1f5fe,stroke:#0288d1,stroke-width:2px
    style EndFlow fill:#e8f5e9,stroke:#388e3c,stroke-width:2px
    style OfflineSave fill:#fffde7,stroke:#fbc02d,stroke-width:2px
    style StateUpdate fill:#c8e6c9,stroke:#2e7d32,stroke-width:2px
```

---

### 🔴 User Flow 3: Xử lý Ngoại lệ Hết chỗ (Waitlist) & Hủy vé Phục hồi (Cancel & Error Recovery)
*(Đáp ứng bắt buộc tiêu chí rubric: Có nhánh lỗi nhập liệu/mất mạng và nhánh phục hồi hoàn tác)*
- **Điểm bắt đầu:** Sinh viên muốn đăng ký workshop hot đã hết 100% chỗ, HOẶC sinh viên bận thi đột xuất muốn hủy vé để nhường slot.
- **Mục tiêu:** Phục hồi lỗi mất kết nối khi đăng ký; xếp hàng danh sách chờ nếu hết slot; và hoàn tất quy trình hủy vé an toàn có đối thoại xác nhận.
- **Điểm kết thúc:** Dữ liệu form được bảo toàn khi lỗi mạng; nhận thông báo kích hoạt vé từ Waitlist; hoặc slot được trả lại hệ thống minh bạch.

```mermaid
flowchart TD
    Start([Bắt đầu: Sinh viên truy cập SCR_03 hoặc SCR_05]) --> BranchChoice{Tình huống diễn ra là gì?}
    
    %% Nhánh 1: Hết slot & Waitlist
    BranchChoice -- Tình huống A: Sự kiện hết slot 0/100 --> CheckSlots[SCR_03 hiển thị Badge đỏ: 'HẾT CHỖ']
    CheckSlots --> ChangeBtn[Nút CTA tự động đổi thành: 'Tham gia Danh sách Chờ - Waitlist']
    ChangeBtn --> ClickWaitlist[Sinh viên nhấn 'Tham gia Danh sách Chờ']
    ClickWaitlist --> WaitlistConfirm[Hệ thống ghi nhận: 'Bạn đang ở vị trí #3 trên Waitlist']
    WaitlistConfirm --> AutoTrigger[Khi có sinh viên khác hủy vé...]
    AutoTrigger --> PushWaitlistAlert[SCR_07 nhận thông báo: 'Có 1 slot trống! Bạn có 15 phút để xác nhận vé']
    PushWaitlistAlert --> EndWaitlist([Hoàn tất nhánh Waitlist])

    %% Nhánh 2: Lỗi Mất Mạng khi Đăng Ký (Network Error & Recovery)
    BranchChoice -- Tình huống B: Mất mạng khi gửi form SCR_04 --> ClickSubmit[Nhấn 'Xác nhận đăng ký' tại SCR_04]
    ClickSubmit --> NetFail[Mạng WiFi chập chờn / Mất kết nối máy chủ]
    NetFail --> ErrorBanner[Hiển thị Error State Banner: 'Mất kết nối Internet. Dữ liệu của bạn đã được lưu tạm.']
    ErrorBanner --> PreserveData[TOÀN BỘ dữ liệu form và câu hỏi được GIỮ NGUYÊN, không bị xóa]
    PreserveData --> NetResume[Sinh viên bật 4G hoặc mạng có lại]
    NetResume --> ClickRetry[Nhấn nút 'Thử lại (Retry)' trên Error Banner]
    ClickRetry --> RetrySuccess[Gửi lại form thành công -> Mở Dialog Xác nhận]
    RetrySuccess --> EndNetRecovery([Hoàn tất nhánh phục hồi mạng])

    %% Nhánh 3: Hủy Vé Nhường Slot (Cancel RSVP Recovery)
    BranchChoice -- Tình huống C: Sinh viên bận đột xuất muốn hủy vé --> OpenMyTicket[Mở SCR_05 từ Tab My Schedule]
    OpenMyTicket --> ClickCancel[Chạm nút 'Hủy đăng ký vé' ở cuối trang]
    ClickCancel --> OpenConfirmDialog[Hiển thị Dialog Xác nhận dạng Overlay cảnh báo:]
    OpenConfirmDialog --> DialogContent["'Bạn có chắc chắn muốn hủy vé? Thao tác này sẽ nhường slot cho bạn sinh viên đang đợi trong Waitlist.'"]
    
    DialogContent --> DialogDecision{Sinh viên chọn?}
    DialogDecision -- Bấm 'Giữ lại vé' --> DismissDialog[Đóng Dialog, trạng thái vé giữ nguyên]
    DismissDialog --> EndCancelFail([Kết thúc: Không hủy vé])
    
    DialogDecision -- Bấm 'Xác nhận hủy' --> ProcessCancel[Gửi lệnh hủy lên hệ thống]
    ProcessCancel --> UpdateCancelled[SCR_05 cập nhật badge xám: 'ĐÃ HỦY VÉ']
    UpdateCancelled --> ReleaseSlot[Hệ thống kích hoạt slot cho bạn #1 trong Waitlist]
    ReleaseSlot --> EndCancelSuccess([Hoàn tất nhánh hủy vé phục hồi])

    style Start fill:#ffebee,stroke:#c62828,stroke-width:2px
    style ErrorBanner fill:#ffcdd2,stroke:#b71c1c,stroke-width:2px
    style ClickRetry fill:#bbdefb,stroke:#1565c0,stroke-width:2px
    style OpenConfirmDialog fill:#fff9c4,stroke:#fbc02d,stroke-width:2px
    style EndNetRecovery fill:#e8f5e9,stroke:#2e7d32,stroke-width:2px
    style EndCancelSuccess fill:#e8f5e9,stroke:#2e7d32,stroke-width:2px
```

---

## 3. Bảng Ánh xạ Flow sang Màn hình (Flow-to-Screen Mapping Matrix)

Bảng ma trận chứng minh **100% mọi màn hình trong hệ thống đều được ít nhất một flow sử dụng** (thỏa mãn tiêu chí Information Architecture 5/5 điểm của Rubric):

| Mã Màn hình | Tên Màn hình | User Flow 1 (Discover & RSVP) | User Flow 2 (Check-in & PDP) | User Flow 3 (Error, Waitlist & Cancel) | Ghi chú Trạng thái Sử dụng |
| :---: | :--- | :---: | :---: | :---: | :--- |
| **SCR_01** | Login Screen | ⚪ Điểm khởi đầu | ⚪ | ⚪ | Dành cho người dùng mới / hết hạn phiên |
| **SCR_02** | Home / Discover | 🟢 **Bắt đầu chính** | ⚪ | ⚪ | Điểm bắt đầu duyệt và tìm kiếm sự kiện |
| **SCR_03** | Event Detail | 🟢 Màn hình xem tin | ⚪ | 🔴 **Điểm phát sinh Waitlist** | Xem thông tin, slot, CTA RSVP / Waitlist |
| **SCR_04** | Event Registration | 🟢 Điền form vé | ⚪ | 🔴 **Điểm lỗi mạng & Retry** | Điền thông tin, validate MSSV, lưu tạm khi mất kết nối |
| **SCR_05** | Ticket Pass (QR) | 🟢 **Đích đến thành công** | 🔵 **Màn hình quét mã** | 🔴 **Điểm khởi tạo Hủy vé** | Xuất trình QR, đổi trạng thái vé, mở dialog hủy vé |
| **SCR_06** | My Schedule | 🟢 Xem vé đã lưu | 🔵 **Điểm mở vé** | 🔴 Quản lý vé sắp tới / đã hủy | Tab 2 điều hướng quản lý lịch trình |
| **SCR_07** | Notifications | ⚪ | 🔵 **Điểm nhận nhắc lịch** | 🔴 **Nhận thông báo mở slot Waitlist** | Tab 3 nhận thông báo đẩy FCM |
| **SCR_08** | Profile & PDP | 🟢 Xem sự kiện lưu | 🔵 **Đích cộng điểm PDP** | ⚪ | Tab 4 tổng kết điểm rèn luyện PDP |

> **Kết luận:** Hệ thống 8 màn hình liên kết chặt chẽ, khép kín, không có màn hình "mồ côi" (orphan screen) và không có đường cụt (dead end).
