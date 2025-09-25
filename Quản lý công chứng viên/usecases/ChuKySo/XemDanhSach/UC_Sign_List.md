# Use Case: UC_Sign_List (Xem danh sách đăng ký chữ ký số)

## User Story
- Với vai trò là **Công chứng viên / Nhân viên TCHNCC / Chuyên viên STP / Lãnh đạo**, tôi muốn xem danh sách các hồ sơ đăng ký chữ ký số để quản lý, theo dõi trạng thái và thực hiện các thao tác cần thiết.

## Acceptance Criteria
- Hệ thống hiển thị danh sách hồ sơ đăng ký chữ ký số với các trường: Tên công chứng viên, Nhà cung cấp, Gói đăng ký, Ngày hiệu lực, Ngày hết hạn, Trạng thái, Người gửi, Thời gian gửi.
- Hỗ trợ phân trang, sắp xếp, lọc, và xuất nhanh sang Excel.
- Từ danh sách, người dùng có thể mở chi tiết, sửa (nếu quyền), xóa (nếu quyền và trạng thái cho phép), gửi duyệt.
- Hiển thị thông báo lỗi nếu không tải được dữ liệu.

## Actors
- Công chứng viên
- Nhân viên TCHNCC
- Chuyên viên STP
- Lãnh đạo

## Pre-conditions
- Người dùng đã đăng nhập và có quyền truy cập chức năng.

## Main Flow
1. Người dùng mở menu "Quản lý chữ ký số → Danh sách".
2. Hệ thống truy vấn và hiển thị danh sách (SCR_Sign_List).
3. Người dùng có thể lọc, tìm kiếm, sắp xếp hoặc chuyển trang.
4. Người dùng chọn hành động trên một bản ghi (Xem chi tiết / Sửa / Xóa / Gửi duyệt).

## Alternative Flows
- Không có dữ liệu: Hiển thị "Không tìm thấy dữ liệu".
- Lỗi hệ thống: Hiển thị thông báo lỗi.

## Post-conditions
- Nếu thành công: danh sách được hiển thị.
- Nếu thất bại: không có dữ liệu hoặc hiển thị lỗi.

## Related
- AD_Sign_List.puml
- SCR_Sign_List.md
- ENT: ChuKySo, CongChungVien