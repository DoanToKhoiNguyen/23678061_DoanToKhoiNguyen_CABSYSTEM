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

# CAB SYSTEM

```text
                 CAB SYSTEM
                     │
       ┌─────────────┼─────────────┐
       │             │             │
       ▼             ▼             ▼
  1. ĐẶT XE     2. TÌM TÀI XẾ   3. THỰC HIỆN
       │             │             │
       │             ▼             ▼
       │        Nhận/Từ chối    Theo dõi chuyến
       │             │             │
       └─────────────┼─────────────┘
                     ▼
              4. THANH TOÁN
                     │
                     ▼
               Gửi thông báo
                     │
                     ▼
              5. VẬN HÀNH
                     │
        ┌────────────┼────────────┐
        ▼            ▼            ▼
   Quản lý       Báo cáo      Xử lý sự cố
   dữ liệu

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
```text
# Business Requirements

| ID Business Requirement | Mô tả |
| :--- | :--- |
| **BR01** | Hệ thống phải cho phép **khách hàng đăng ký và quản lý tài khoản**. |
| **BR02** | Hệ thống phải cho phép **khách hàng đăng nhập và xác thực tài khoản**. |
| **BR03** | Hệ thống phải cho phép **khách hàng đặt xe** bằng cách cung cấp điểm đón, điểm đến và loại xe. |
| **BR04** | Hệ thống phải **tìm kiếm và ghép tài xế phù hợp** với yêu cầu đặt xe của khách hàng. |
| **BR05** | Hệ thống phải cho phép **tài xế nhận hoặc từ chối chuyến xe**. |
| **BR06** | Hệ thống phải cho phép **khách hàng theo dõi trạng thái và vị trí chuyến xe**. |
| **BR07** | Hệ thống phải cho phép **tài xế cập nhật trạng thái chuyến đi** từ khi nhận chuyến đến khi hoàn thành. |
| **BR08** | Hệ thống phải hỗ trợ **tính toán và xử lý thanh toán** cho chuyến xe. |
| **BR09** | Hệ thống phải lưu trữ và cho phép **khách hàng xem lịch sử chuyến đi**. |
| **BR10** | Hệ thống phải cho phép **khách hàng đánh giá tài xế và chuyến đi**. |
| **BR11** | Hệ thống phải cho phép **nhân viên vận hành quản lý khách hàng**. |
| **BR12** | Hệ thống phải cho phép **nhân viên vận hành quản lý tài xế và phương tiện**. |
| **BR13** | Hệ thống phải cho phép **nhân viên vận hành quản lý và giám sát các chuyến xe**. |
| **BR14** | Hệ thống phải cho phép **nhân viên vận hành quản lý các giao dịch thanh toán**. |
| **BR15** | Hệ thống phải hỗ trợ **xử lý và ghi nhận các sự cố phát sinh trong quá trình vận hành**. |
| **BR16** | Hệ thống phải cung cấp **báo cáo về hoạt động đặt xe, tài xế, chuyến đi và giao dịch**. |
| **BR17** | Hệ thống phải tích hợp **dịch vụ bản đồ và định vị** để xác định vị trí khách hàng, tài xế và tuyến đường. |
| **BR18** | Hệ thống phải cung cấp **dịch vụ thông báo** cho khách hàng, tài xế và nhân viên vận hành khi có sự kiện liên quan. |

# CAB SYSTEM

```text
                         CAB SYSTEM
                             │
        ┌────────────────────┼────────────────────┐
        │                    │                    │
        ▼                    ▼                    ▼
  QUẢN LÝ TÀI KHOẢN      ĐẶT & THỰC HIỆN XE    QUẢN LÝ VẬN HÀNH
        │                    │                    │
        │                    │                    │
   ┌────┴────┐          ┌────┴─────┐        ┌────┴────────┐
   │         │          │          │        │             │
   ▼         ▼          ▼          ▼        ▼             ▼
Đăng ký   Đăng nhập   Đặt xe    Ghép tài xế  Quản lý     Quản lý
tài khoản tài khoản               │          khách hàng   tài xế
                                  │
                                  ▼
                            Nhận chuyến
                                  │
                                  ▼
                         Thực hiện chuyến
                                  │
                         ┌────────┴────────┐
                         ▼                 ▼
                    Thanh toán       Theo dõi vị trí
                         │
                         ▼
                  Hoàn thành chuyến
                         │
                    ┌────┴────┐
                    ▼         ▼
             Lịch sử chuyến  Đánh giá

CAB SYSTEM
│
├── 1. CUSTOMER
│   ├── BF01 Quản lý tài khoản
│   ├── BF02 Đặt xe
│   ├── BF06 Theo dõi chuyến đi
│   ├── BF08 Thanh toán
│   └── Đánh giá chuyến đi
│
├── 2. DRIVER
│   ├── Quản lý tài khoản tài xế
│   ├── Quản lý phương tiện
│   ├── Cập nhật trạng thái hoạt động
│   ├── BF04 Nhận chuyến
│   └── BF05 Quản lý chuyến đi
│
├── 3. OPERATION
│   ├── BF10 Quản lý khách hàng
│   ├── BF11 Quản lý tài xế
│   ├── BF12 Quản lý phương tiện
│   ├── BF13 Quản lý chuyến đi
│   ├── BF14 Quản lý giao dịch
│   ├── BF15 Phân quyền
│   ├── BF16 Báo cáo
│   ├── BF17 Xử lý sự cố
│   └── BF19 Nhật ký hoạt động
│
└── 4. SUPPORT SERVICES
    ├── BF03 Tìm kiếm tài xế
    ├── BF07 Tính cước
    ├── BF08 Thanh toán
    ├── BF09 Thông báo
    └── BF20 Dịch vụ tích hợp

# System Requirements – CAB System

| ID | System Requirement | BF |
|---|---|---|
| **SR01** | Hệ thống cho phép khách hàng đăng ký và đăng nhập tài khoản. | BF01 |
| **SR02** | Hệ thống cho phép khách hàng nhập thông tin và gửi yêu cầu đặt xe. | BF02 |
| **SR03** | Hệ thống tự động tìm và ưu tiên tài xế phù hợp ở gần khách hàng. | BF03 |
| **SR04** | Hệ thống tự động tìm tài xế khác khi tài xế từ chối hoặc không phản hồi. | BF04 |
| **SR05** | Hệ thống cho phép tài xế nhận hoặc từ chối chuyến xe. | BF04 |
| **SR06** | Hệ thống cho phép tài xế cập nhật trạng thái chuyến đi. | BF05 |
| **SR07** | Hệ thống cho phép khách hàng theo dõi vị trí, trạng thái và ETA của chuyến xe. | BF06 |
| **SR08** | Hệ thống tự động tính cước cho chuyến đi. | BF07 |
| **SR09** | Hệ thống hỗ trợ thanh toán tiền mặt và thanh toán điện tử thông qua Payment Provider. | BF08 |
| **SR10** | Hệ thống gửi thông báo về các sự kiện quan trọng của chuyến đi cho khách hàng và tài xế. | BF09 |
| **SR11** | Hệ thống cho phép nhân viên vận hành quản lý khách hàng, tài xế, phương tiện và chuyến đi. | BF10–13 |
| **SR12** | Hệ thống cho phép nhân viên vận hành quản lý và theo dõi giao dịch thanh toán. | BF14 |
| **SR13** | Hệ thống hỗ trợ phân quyền người dùng và cung cấp báo cáo vận hành. | BF15–16 |
| **SR14** | Hệ thống ghi nhận lỗi và lưu vết các thao tác quan trọng để phục vụ kiểm tra, xử lý sự cố. | BF17, BF19 |
| **SR15** | Hệ thống hỗ trợ tích hợp và mở rộng các dịch vụ như Map, Payment và Notification Provider. | BF20 |

# Quy định nghiệp vụ – CAB System

| ID | Quy định nghiệp vụ | Mô tả |
|---|---|---|
| **BRULE01** | Ưu tiên tài xế gần khách hàng | Hệ thống ưu tiên tài xế đang hoạt động và có vị trí gần điểm đón. |
| **BRULE02** | Thời gian phản hồi tài xế | Tài xế phải phản hồi yêu cầu chuyến trong thời gian quy định. |
| **BRULE03** | Tìm tài xế thay thế | Nếu tài xế từ chối hoặc không phản hồi, hệ thống tiếp tục tìm tài xế khác. |
| **BRULE04** | Tính cước | Cước chuyến xe được tính dựa trên các quy tắc giá đã được cấu hình. |
| **BRULE05** | Thanh toán | Khách hàng có thể thanh toán bằng tiền mặt hoặc phương thức điện tử được hỗ trợ. |
| **BRULE06** | Hoàn thành chuyến | Chuyến xe chỉ được chuyển sang trạng thái hoàn thành khi tài xế xác nhận kết thúc chuyến. |
| **BRULE07** | Hủy chuyến | Khách hàng hoặc tài xế có thể hủy chuyến theo điều kiện và thời điểm được quy định. |
| **BRULE08** | Theo dõi chuyến | Vị trí và trạng thái chuyến được cập nhật trong quá trình thực hiện chuyến. |
| **BRULE09** | Phân quyền | Người dùng chỉ được thực hiện các thao tác phù hợp với vai trò được cấp. |
| **BRULE10** | Ghi nhận thao tác | Các thao tác quan trọng phải được lưu vết để phục vụ kiểm tra và xử lý sự cố. |

# Ngoại lệ – CAB System

| ID | Ngoại lệ | Cách xử lý |
|---|---|---|
| **EX01** | Không tìm thấy tài xế | Thông báo cho khách hàng và cho phép gửi lại yêu cầu đặt xe. |
| **EX02** | Tài xế từ chối chuyến | Hệ thống tự động tìm tài xế tiếp theo. |
| **EX03** | Tài xế không phản hồi | Hết thời gian chờ, hệ thống chuyển yêu cầu sang tài xế khác. |
| **EX04** | Khách hàng hủy chuyến | Hệ thống kiểm tra điều kiện hủy và cập nhật trạng thái chuyến. |
| **EX05** | Tài xế hủy chuyến | Hệ thống thông báo cho khách hàng và tìm tài xế thay thế nếu phù hợp. |
| **EX06** | Thanh toán thất bại | Hệ thống thông báo lỗi và cho phép khách hàng thực hiện lại hoặc chọn phương thức khác. |
| **EX07** | Payment Provider không hoạt động | Hệ thống ghi nhận lỗi và cho phép sử dụng phương thức thanh toán khác nếu có. |
| **EX08** | Mất kết nối định vị | Hệ thống thông báo trạng thái định vị không khả dụng và tiếp tục xử lý chuyến nếu có thể. |
| **EX09** | Dịch vụ thông báo lỗi | Hệ thống ghi nhận lỗi và tiếp tục xử lý nghiệp vụ chính. |
| **EX10** | Người dùng không có quyền | Hệ thống từ chối thao tác và thông báo người dùng không có quyền thực hiện. |

# Entity Relationship Diagram – CAB System

```mermaid
erDiagram

    CUSTOMER ||--o{ BOOKING : "đặt"
    BOOKING ||--|| TRIP : "tạo"
    
    DRIVER ||--o{ TRIP : "thực hiện"
    DRIVER ||--o{ VEHICLE : "sử dụng"
    
    TRIP ||--o| PAYMENT : "có"
    TRIP ||--o| RATING : "có"
    CUSTOMER ||--o{ RATING : "đánh giá"
    
    TRIP ||--o{ LOCATION : "cập nhật"
    
    CUSTOMER ||--o{ NOTIFICATION : "nhận"
    DRIVER ||--o{ NOTIFICATION : "nhận"
    
    EMPLOYEE ||--o{ CUSTOMER : "quản lý"
    EMPLOYEE ||--o{ DRIVER : "quản lý"
    EMPLOYEE ||--o{ TRIP : "giám sát"

    CUSTOMER {
        int customer_id PK
        string name
        string email
        string phone
        string password
    }

    DRIVER {
        int driver_id PK
        string name
        string phone
        string status
        float rating
    }

    VEHICLE {
        int vehicle_id PK
        int driver_id FK
        string license_plate
        string vehicle_type
    }

    BOOKING {
        int booking_id PK
        int customer_id FK
        string pickup_location
        string destination
        datetime booking_time
        string status
    }

    TRIP {
        int trip_id PK
        int booking_id FK
        int driver_id FK
        datetime start_time
        datetime end_time
        decimal fare
        string status
    }

    PAYMENT {
        int payment_id PK
        int trip_id FK
        decimal amount
        string method
        string status
    }

    RATING {
        int rating_id PK
        int trip_id FK
        int customer_id FK
        int score
        string comment
    }

    LOCATION {
        int location_id PK
        int trip_id FK
        float latitude
        float longitude
        datetime recorded_at
    }

    NOTIFICATION {
        int notification_id PK
        string message
        string type
        datetime created_at
        string status
    }

    EMPLOYEE {
        int employee_id PK
        string name
        string email
        int role_id FK
    }

# Use Case – CAB System

| ID | Use Case | Actor chính |
|---|---|---|
| UC01 | Đăng ký tài khoản | Customer |
| UC02 | Đăng nhập | Customer, Driver, Operation Staff |
| UC03 | Đặt xe | Customer |
| UC04 | Tìm và ghép tài xế | System |
| UC05 | Nhận / Từ chối chuyến | Driver |
| UC06 | Quản lý chuyến đi | Driver |
| UC07 | Theo dõi chuyến đi | Customer |
| UC08 | Tính cước | System |
| UC09 | Thanh toán | Customer |
| UC10 | Đánh giá chuyến đi | Customer |
| UC11 | Quản lý khách hàng | Operation Staff |
| UC12 | Quản lý tài xế | Operation Staff |
| UC13 | Quản lý phương tiện | Operation Staff |
| UC14 | Quản lý chuyến đi | Operation Staff |
| UC15 | Quản lý giao dịch | Operation Staff |
| UC16 | Xem báo cáo | Operation Staff |
| UC17 | Xử lý sự cố | Operation Staff |
| UC18 | Quản lý phân quyền | Operation Staff |

# Acceptance Criteria – CAB System

| ID | Use Case | Tiêu chí chấp nhận |
|---|---|---|
| AC01 | Đăng ký tài khoản | Customer đăng ký thành công khi nhập đầy đủ thông tin hợp lệ và tài khoản được lưu vào hệ thống. |
| AC02 | Đăng nhập | Customer, Driver hoặc Operation Staff đăng nhập thành công khi thông tin xác thực chính xác. |
| AC03 | Đặt xe | Customer có thể nhập điểm đón, điểm đến và gửi yêu cầu đặt xe thành công. |
| AC04 | Tìm và ghép tài xế | Hệ thống tự động tìm tài xế phù hợp và ưu tiên tài xế ở gần Customer. |
| AC05 | Nhận / Từ chối chuyến | Driver có thể chấp nhận hoặc từ chối yêu cầu chuyến xe. |
| AC06 | Quản lý chuyến đi | Driver có thể cập nhật trạng thái chuyến: Đang đến, Đang chuyến và Hoàn thành. |
| AC07 | Theo dõi chuyến đi | Customer có thể xem trạng thái và vị trí hiện tại của Driver trong chuyến đi. |
| AC08 | Tính cước | Hệ thống tự động tính tiền dựa trên quy tắc giá cước đã được cấu hình. |
| AC09 | Thanh toán | Customer có thể thanh toán bằng tiền mặt hoặc phương thức điện tử và nhận kết quả thanh toán. |
| AC10 | Đánh giá chuyến đi | Customer có thể đánh giá chuyến đi sau khi chuyến đã hoàn thành. |
| AC11 | Quản lý khách hàng | Operation Staff có thể xem, cập nhật và quản lý thông tin Customer. |
| AC12 | Quản lý tài xế | Operation Staff có thể xem, cập nhật và quản lý thông tin Driver. |
| AC13 | Quản lý phương tiện | Operation Staff có thể thêm, cập nhật và quản lý thông tin Vehicle. |
| AC14 | Quản lý chuyến đi | Operation Staff có thể xem và giám sát trạng thái các chuyến đi. |
| AC15 | Quản lý giao dịch | Operation Staff có thể xem và kiểm tra trạng thái các giao dịch thanh toán. |
| AC16 | Xem báo cáo | Operation Staff có thể xem báo cáo về chuyến đi, doanh thu, hủy chuyến và hiệu suất Driver. |
| AC17 | Xử lý sự cố | Hệ thống ghi nhận lỗi và thông báo cho người dùng khi xảy ra sự cố trong quá trình xử lý. |
| AC18 | Quản lý phân quyền | Người dùng chỉ được thực hiện các chức năng phù hợp với Role của mình. |

# Bảng truy vết yêu cầu – CAB System

| BO | BR | FR | Acceptance Criteria | Use Case |
|---|---|---|---|---|
| BO01 | BR01 | FR01 | Customer đăng ký thành công khi thông tin hợp lệ và tài khoản được lưu. | UC01 – Đăng ký tài khoản |
| BO01 | BR02 | FR02 | Người dùng đăng nhập thành công khi thông tin xác thực hợp lệ. | UC02 – Đăng nhập |
| BO01 | BR03 | FR03 | Customer có thể nhập điểm đón, điểm đến và gửi yêu cầu đặt xe. | UC03 – Đặt xe |
| BO02 | BR04 | FR04 | Hệ thống tự động tìm và ưu tiên Driver phù hợp ở gần Customer. | UC04 – Tìm và ghép tài xế |
| BO03 | BR05 | FR05 | Driver có thể chấp nhận hoặc từ chối yêu cầu chuyến xe. | UC05 – Nhận / Từ chối chuyến |
| BO03 | BR06 | FR06 | Hệ thống tìm Driver khác khi Driver từ chối hoặc không phản hồi. | UC04 – Tìm và ghép tài xế |
| BO04 | BR07 | FR07 | Customer có thể xem trạng thái, vị trí và ETA của chuyến xe. | UC07 – Theo dõi chuyến đi |
| BO04 | BR08 | FR08 | Driver có thể cập nhật trạng thái chuyến đi theo từng giai đoạn. | UC06 – Quản lý chuyến đi |
| BO05 | BR09 | FR09 | Hệ thống tự động tính cước theo quy tắc giá đã cấu hình. | UC08 – Tính cước |
| BO05 | BR10 | FR10 | Customer có thể thanh toán bằng tiền mặt hoặc phương thức điện tử. | UC09 – Thanh toán |
| BO06 | BR10 | FR10 | Thông tin thanh toán nhạy cảm không được lưu trực tiếp trên hệ thống. | UC09 – Thanh toán |
| BO07 | BR11 | FR11 | Hệ thống gửi thông báo cho Customer và Driver khi có sự kiện quan trọng. | UC03, UC05, UC06 |
| BO08 | BR12 | FR12 | Operation Staff có thể quản lý thông tin Customer. | UC11 – Quản lý khách hàng |
| BO08 | BR13 | FR13 | Operation Staff có thể quản lý Driver và Vehicle. | UC12, UC13 |
| BO08 | BR14 | FR14 | Operation Staff có thể xem và giám sát các chuyến đi. | UC14 – Quản lý chuyến đi |
| BO08 | BR15 | FR15 | Operation Staff có thể kiểm tra trạng thái các giao dịch. | UC15 – Quản lý giao dịch |
| BO09 | BR16 | FR16 | Người dùng chỉ được thực hiện chức năng phù hợp với Role. | UC18 – Quản lý phân quyền |
| BO10 | BR17 | FR17 | Operation Staff có thể xem báo cáo về chuyến đi, doanh thu và hiệu suất Driver. | UC16 – Xem báo cáo |
| BO12 | BR18 | FR18 | Hệ thống ghi nhận lỗi và không làm gián đoạn chức năng chính khi xảy ra sự cố. | UC17 – Xử lý sự cố |
| BO14 | BR19 | FR19 | Hệ thống ghi lại các thao tác quan trọng để phục vụ truy vết. | UC17 – Xử lý sự cố |
| BO13 | BR20 | FR20 | Hệ thống có thể tích hợp và mở rộng các dịch vụ Map, Payment và Notification. | UC03, UC07, UC09 |
| BO15 | BR09 | FR09 | Quy tắc tính cước được cấu hình rõ ràng và được hệ thống áp dụng thống nhất. | UC08 – Tính cước |
