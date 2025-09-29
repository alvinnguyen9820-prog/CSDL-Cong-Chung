# Use Case: UC_Sign_List (Xem danh sách đăng ký chữ ký số)

## User Story
- Với vai trò là **Công chứng viên / Nhân viên TCHNCC, Chuyên viên STP, Lãnh đạo STP, Lãnh đạo phòng HCBTTP tại STP, Lãnh đạo Bộ Tư pháp, Lãnh đạo Cục BTTP, Chuyên viên Cục BTTP**, tôi muốn xem danh sách các hồ sơ đăng ký chữ ký số để quản lý, theo dõi trạng thái và thực hiện các thao tác cần thiết.

## Acceptance Criteria
- Hệ thống hiển thị danh sách hồ sơ đăng ký chữ ký số với các trường: STT Tên tổ chức công chứng, Mã chứng thư, Nhà cung cấp dịch vụ, Trạng thái, Loại.
- Nếu số lượng bản ghi vượt quá giới hạn hiển thị, hệ thống phải cung cấp phân trang (10 bản ghi 1 trang).
- Từ danh sách, người dùng có thể mở chi tiết, sửa (nếu quyền), xóa (nếu quyền và trạng thái cho phép), gửi duyệt.
- Hiển thị thông báo lỗi nếu không tải được dữ liệu.
- Danh sách hồ sơ đăng ký chữ ký số hiển thị theo thứ tự thời gian cập nhật từ mới tới cũ nhất.
- Hỗ trợ xuất (Export) danh sách theo điều kiện đã tìm  (chi tiết trong UC_CKS_Export).
- Nếu có lỗi tải dữ liệu, hiển thị thông báo lỗi.
- Hệ thống cho phép tìm kiếm hồ sơ đăng ký chữ ký số (chi tiết trong UC_CKS_Search).    
- Nếu không có hồ sơ đăng ký nào trong hệ thống, hiển thị thông báo “Không có dữ liệu đăng ký chữ ký số”. 

## Tác nhân chính
- Công chứng viên
- Nhân viên TCHNCC
- Chuyên viên STP
- Lãnh đạo STP
- Lãnh đạo phòng HCBTTP tại STP
- Lãnh đạo Bộ Tư pháp
- Lãnh đạo Cục BTTP
- Chuyên viên Cục BTTP

## Tiền điều kiện
- Người dùng đã đăng nhập và có quyền truy cập chức năng.

## Luồng chính
1. Người dùng mở menu "Công chứng viên" > "Đăng ký Chữ ký số".
2. Hệ thống kiểm tra người dùng
3. Nếu người dùng không phải nhân viên/Công chứng viên của tổ chức hành nghề công chứng, Hệ thống tải danh sách đăng ký chữ ký số của công chứng viên (**ENT_ChuKySo**)
- Nếu người dùng thuộc tổ chức công chứng, Hệ thống chỉ hiển thị danh sách đăng ký chữ ký số theo tổ chức công chứng của người dùng
4. Hệ thống hiển thị màn hình danh sách đăng theo thứ tự thời gian cập nhật từ mới tới cũ nhất **SCR_Sign_List** (lấy dữ liệu từ **ENT_CongChungVien**, **ENT_ChuKySo** và **ENT_ToChucCongChung**).
5. Nếu số lượng bản ghi lớn hơn 10, hệ thống thực hiện phân trang, 10 bản ghi mỗi trang
6. Người dùng có thể:
   - Chọn trang tiếp theo/ trước, hệ thống sẽ hiển thị 10 bản ghi của trang tương ứng
   - Export (UC_CKS_Export)
   - Tìm kiếm (UC_CKS__Search)
   - Đăng ký (UC_CKS__Create)
   - Xem chi tiết (UC_CKS__Detail)
   - Xóa (UC_CKS__Delete)
   - Chỉnh sửa (UC_CKS__Update)
   - Xem lịch sử cập nhật thông tin (UC_CCV_History)
5. Kết thúc.

## Luồng phụ/ Ngoại lệ
- Nếu có lỗi tải danh sách: hiển thị thông báo "Không tải được danh sách, vui lòng thử lại".
- Nếu không có dữ liệu: hiển thị "Không có dữ liệu đăng ký chữ ký số của công chứng viên".
- Nếu không quyền truy cập: hiển thị "Không có quyền truy cập" và ẩn đi menu "Đăng ký chữ ký số".

## Hậu điều kiện
- Nếu thành công: Người dùng xem được danh sách đăng ký chữ ký số của công chứng viên.
- Nếu thất bại: Không hiển thị dữ liệu, hoặc hiển thị thông báo lỗi.

## Related
- AD_Sign_List.puml
- SCR_Sign_List.md
- ENT: **ENT_ChuKySo**, **ENT_CongChungVien**, **ENT_ToChucCongChun**