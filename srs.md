| Actor | Vai trò |
|---|---|
| **Customer (Khách hàng)** | Người sử dụng dịch vụ đặt xe: tạo yêu cầu đặt xe, theo dõi chuyến đi, thanh toán và đánh giá tài xế. |
| **Driver (Tài xế)** | Người tiếp nhận và thực hiện chuyến xe: nhận/từ chối chuyến, cập nhật trạng thái chuyến và vị trí. |
| **Operation Staff (Nhân viên vận hành)** | Người quản lý và giám sát hoạt động vận hành: quản lý khách hàng, tài xế, phương tiện, chuyến đi và xử lý các sự cố. |
| **Admin (Quản trị viên)** | Người quản trị hệ thống: quản lý tài khoản, phân quyền và thực hiện các thao tác quản trị nhạy cảm. |

## Business Objectives

| STT | Yêu cầu / Kỳ vọng của khách hàng | Mục tiêu nghiệp vụ |
|---|---|---|
| BO1 | Khách hàng có thể đăng ký, đặt xe, theo dõi chuyến | Cung cấp quy trình đặt xe trực tuyến thuận tiện, nhanh chóng và minh bạch cho khách hàng. |
| BO2 | Hệ thống tự động tìm tài xế phù hợp, ưu tiên tài xế gần khách | Tự động hóa và tối ưu hóa việc phân công tài xế nhằm giảm thời gian chờ xe. |
| BO3 | Nếu tài xế từ chối/không phản hồi thì tìm tài xế khác | Đảm bảo yêu cầu đặt xe được xử lý liên tục và tăng tỷ lệ tìm được tài xế. |
| BO4 | Khách hàng theo dõi được trạng thái và ETA | Tăng tính minh bạch và khả năng theo dõi chuyến đi theo thời gian thực. |
| BO5 | Tính cước và hỗ trợ tiền mặt/thanh toán điện tử | Chuẩn hóa và nâng cao hiệu quả quản lý cước phí và thanh toán. |
| BO6 | Tích hợp payment provider, không lưu thông tin nhạy cảm | Giảm rủi ro bảo mật và đảm bảo an toàn cho dữ liệu thanh toán. |
| BO7 | Gửi thông báo cho khách hàng và tài xế | Đảm bảo thông tin quan trọng được truyền đạt kịp thời đến các bên liên quan. |
| BO8 | Nhân viên vận hành quản lý khách hàng, tài xế, chuyến đi | Nâng cao hiệu quả quản lý và giám sát hoạt động vận hành. |
| BO9 | Có phân quyền cho các thao tác quản trị | Kiểm soát quyền truy cập và giảm rủi ro từ các thao tác trái phép. |
| BO10 | Có báo cáo về chuyến, doanh thu, hủy, hiệu quả tài xế | Cung cấp dữ liệu và báo cáo để hỗ trợ quản lý, đánh giá và ra quyết định kinh doanh. |
| BO11 | Hệ thống phải chịu được lượng lớn người dùng và thời điểm cao điểm | Đảm bảo hệ thống có khả năng mở rộng và duy trì hoạt động ổn định khi nhu cầu tăng cao. |
| BO12 | Lỗi thanh toán/thông báo không được làm sập hệ thống | Đảm bảo tính sẵn sàng và khả năng phục hồi của nền tảng. |
| BO13 | Có thể thêm dịch vụ, payment, notification provider trong tương lai | Xây dựng nền tảng linh hoạt, dễ mở rộng và thích ứng với nhu cầu kinh doanh mới. |
| BO14 | Lưu vết các thao tác quan trọng | Đảm bảo khả năng kiểm tra, truy vết và xử lý sự cố. |
| BO15 | Chưa rõ cách tính cước, ưu tiên tài xế, hủy chuyến... | Làm rõ và chuẩn hóa các quy tắc nghiệp vụ trước khi triển khai hệ thống. |

# HỆ THỐNG CAB

```text
HỆ THỐNG CAB
│
├── 1. KHÁCH HÀNG
│   ├── Quản lý tài khoản
│   ├── Đặt xe
│   ├── Theo dõi chuyến đi
│   ├── Thanh toán
│   ├── Lịch sử chuyến đi
│   └── Đánh giá
│
├── 2. TÀI XẾ
│   ├── Tài khoản tài xế
│   ├── Quản lý phương tiện
│   ├── Trạng thái hoạt động
│   ├── Nhận chuyến
│   ├── Quản lý chuyến đi
│   └── Theo dõi vị trí
│
├── 3. VẬN HÀNH
│   ├── Quản lý khách hàng
│   ├── Quản lý tài xế
│   ├── Quản lý phương tiện
│   ├── Quản lý chuyến đi
│   ├── Quản lý giao dịch
│   ├── Xử lý sự cố
│   └── Báo cáo
│
└── 4. DỊCH VỤ HỖ TRỢ
    ├── Ghép tài xế
    ├── Cổng thanh toán
    ├── Dịch vụ bản đồ / định vị
    └── Dịch vụ thông báo

        
