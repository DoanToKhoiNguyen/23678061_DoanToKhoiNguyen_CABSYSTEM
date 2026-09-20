# Test Suite: Quy Trình Tài Xế Nhận Và Thực Hiện Chuyến (Driver Scenario)

**Test Scenario:** Tài xế nhận và thực hiện chuyến

---

| Test Case ID | Test Case | Preconditions | Test Steps | Test Data | Expected Result | Priority |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| **TC_TRIP_001** | Tài xế nhận chuyến với yêu cầu hợp lệ | Tài xế đã đăng nhập, đang AVAILABLE; có chuyến đang chờ nhận | 1. Mở danh sách yêu cầu chuyến<br>2. Chọn chuyến<br>3. Nhấn Accept | Trip ID=TRIP001; Driver=DRIVER01 | Chuyến được gán cho tài xế và trạng thái được cập nhật thành công | High |
| **TC_TRIP_002** | Tài xế từ chối chuyến | Tài xế đã đăng nhập; có chuyến đang chờ nhận | 1. Mở yêu cầu chuyến<br>2. Chọn chuyến<br>3. Nhấn Reject | Trip ID=TRIP002 | Hệ thống ghi nhận từ chối và thực hiện tìm tài xế khác | High |
| **TC_TRIP_003** | Tài xế nhận chuyến đã được tài xế khác nhận | Chuyến đã được gán cho Driver A | 1. Driver B mở yêu cầu<br>2. Nhấn Accept | Trip ID=TRIP003; Driver B=DRIVER02 | Hệ thống từ chối thao tác; chuyến vẫn thuộc Driver A | High |
| **TC_TRIP_004** | Tài xế không phản hồi trong thời gian quy định | Tài xế được gửi yêu cầu chuyến | 1. Không phản hồi<br>2. Chờ hết thời gian quy định | Trip ID=TRIP004; Response=Timeout | Hệ thống coi là quá hạn/từ chối và tìm tài xế khác | High |
| **TC_TRIP_005** | Hệ thống ưu tiên tài xế gần điểm đón | Có nhiều tài xế AVAILABLE | 1. Tạo yêu cầu chuyến<br>2. Theo dõi kết quả matching | Driver A=1km; Driver B=5km; Driver C=3km | Hệ thống ưu tiên tài xế gần điểm đón nhất theo BRULE01 | High |
| **TC_TRIP_006** | Không có tài xế sẵn sàng | Không có driver AVAILABLE phù hợp | 1. Gửi yêu cầu chuyến<br>2. Theo dõi matching | Available drivers=0 | Hệ thống thông báo rõ không tìm được tài xế | High |
| **TC_TRIP_007** | Tài xế chuyển trạng thái sang AVAILABLE | Tài xế đã đăng nhập; trạng thái hiện tại OFFLINE/UNAVAILABLE | 1. Mở trạng thái tài xế<br>2. Chọn AVAILABLE<br>3. Lưu | Driver=DRIVER01; Status=AVAILABLE | Trạng thái được cập nhật; tài xế có thể nhận chuyến | High |
| **TC_TRIP_008** | Tài xế chuyển trạng thái sang UNAVAILABLE | Tài xế đang AVAILABLE | 1. Mở trạng thái<br>2. Chọn UNAVAILABLE<br>3. Lưu | Driver=DRIVER01; Status=UNAVAILABLE | Tài xế không được chọn cho các chuyến mới | Medium |
| **TC_TRIP_009** | Tài xế xác nhận đã đến điểm đón | Tài xế đã nhận chuyến và đang di chuyển đến pickup | 1. Mở chuyến<br>2. Chọn trạng thái ARRIVED<br>3. Xác nhận | Trip ID=TRIP005; Status=ARRIVED | Trạng thái chuyến chuyển sang ARRIVED | High |
| **TC_TRIP_010** | Tài xế xác nhận đã đón khách | Tài xế đã đến điểm đón | 1. Mở chuyến<br>2. Chọn PICKED_UP<br>3. Xác nhận | Trip ID=TRIP005; Status=PICKED_UP | Trạng thái chuyến được cập nhật thành PICKED_UP | High |
| **TC_TRIP_011** | Tài xế cập nhật chuyến đang di chuyển | Tài xế đã đón khách | 1. Mở chuyến<br>2. Chọn IN_PROGRESS<br>3. Xác nhận | Trip ID=TRIP005; Status=IN_PROGRESS | Trạng thái chuyến chuyển sang IN_PROGRESS | High |
| **TC_TRIP_012** | Tài xế hoàn thành chuyến | Chuyến đang IN_PROGRESS | 1. Mở chuyến<br>2. Chọn COMPLETED<br>3. Xác nhận | Trip ID=TRIP005; Status=COMPLETED | Chuyến chỉ được hoàn thành sau khi tài xế xác nhận kết thúc | High |
| **TC_TRIP_013** | Cập nhật vị trí hợp lệ | Tài xế đang thực hiện chuyến | 1. Gửi vị trí hiện tại<br>2. Kiểm tra response | Trip ID=TRIP005; Latitude=10.8231; Longitude=106.6297 | Vị trí được lưu/cập nhật thành công | High |
| **TC_TRIP_014** | Cập nhật vị trí thiếu latitude | Tài xế đang thực hiện chuyến | 1. Gửi location request<br>2. Bỏ latitude<br>3. Submit | Trip ID=TRIP005; Longitude=106.6297 | API trả lỗi validation; vị trí không được cập nhật | High |
| **TC_TRIP_015** | Cập nhật vị trí thiếu longitude | Tài xế đang thực hiện chuyến | 1. Gửi location request<br>2. Bỏ longitude<br>3. Submit | Trip ID=TRIP005; Latitude=10.8231 | API trả lỗi validation; vị trí không được cập nhật | High |
| **TC_TRIP_016** | Tài xế không được cập nhật chuyến của tài xế khác | Driver B không sở hữu Trip A | 1. Driver B gửi request cập nhật Trip A<br>2. Submit | Trip ID=TRIP006; Driver=DRIVER02; Owner=DRIVER01 | Hệ thống từ chối truy cập/thao tác | High |
| **TC_TRIP_017** | Người chưa xác thực cập nhật trạng thái chuyến | Không có token hợp lệ | 1. Gửi request cập nhật trạng thái<br>2. Không gửi Authorization | Trip ID=TRIP005; Status=IN_PROGRESS | API trả 401 Unauthorized; trạng thái không thay đổi | High |
| **TC_TRIP_018** | Cập nhật trạng thái không hợp lệ | Tài xế có quyền; chuyến đang ở trạng thái hợp lệ | 1. Gửi trạng thái không tồn tại<br>2. Submit | Trip ID=TRIP005; Status=INVALID_STATUS | API trả lỗi validation; trạng thái không thay đổi | Medium |