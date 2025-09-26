# Use Case: UC_Sign_Create (Chỉnh sửa thông tin đăng ký)

## User Story
- Với vai trò là **Công chứng viên / Nhân viên TCHNCC**, tôi muốn có thể Chỉnh sửa thông tin đăng ký chữ ký số.

## Acceptance Criteria
- Hệ thống hiển thị form Chỉnh sửa thông tin đăng ký chữ ký số.
- Người dùng cập nhật thông tin: 
   - Công chứng viên
   - Gói đăng ký
   - Nhà cung cấp
   - Mã chứng thư
   - Ngày hiệu lực
   - Ngày hết hạn 
   - File đính kèm
- Hệ thống kiểm tra dữ liệu hợp lệ (thời gian hiệu lực/hết hạn, file đúng định dạng).
- Nếu hợp lệ: lưu hồ sơ đăng ký ở trạng thái **"Mới tạo"** hoặc **"Chờ duyệt"**.
- Người dùng có thể hủy thao tác chỉnh sửa.

## Tác nhân chính
- Công chứng viên  
- Nhân viên TCHNCC  

## Tiền điều kiện
- Người dùng đã đăng nhập và có quyền Chỉnh sửa thông tin đăng ký.

## Luồng chính
1. Người dùng chọn chức năng **Chỉnh sửa thông tin đăng ký** bằng cách bấm vào biểu tượng chỉnh sửa trên dòng thông tin đăng ký chữ ký số (**SCR_Sign_List**) hoặc nút "Chỉnh sửa" trong trang chi tiết thông tin đăng ký.
2. Hệ thống hiển thị màn hình chỉnh sửa thông tin đăng ký (**SCR_Sign_Update**).
3. Người dùng chỉnh sửa các thông tin cần thiết.
4. Người dùng bấm nút **Trình duyệt**.
5. Hệ thống kiểm tra dữ liệu:
   - Nếu hợp lệ: lưu dữ liệu vào **ENT_ChuKySo** với trạng thái = "Chờ duyệt".
   - Hiển thị thông báo "Cập nhật thông tin đăng ký chữ ký số thành công".
   - Lịch sử đăng ký thông tin chữ ký số được cập nhật
   - Quay về danh sách (**UC_Sign_List**).
6. Kết thúc use case.

## Luồng phụ / Ngoại lệ
- Người dùng chọn **Hủy**: Form đóng, không lưu dữ liệu.
- Nhập thiếu thông tin bắt buộc: Hiển thị cảnh báo lỗi.
- Ngày hết hạn < ngày hiệu lực: Hiển thị lỗi "Ngày hết hạn không hợp lệ".
- File đính kèm sai định dạng: Hiển thị lỗi "File không hợp lệ".
- Lỗi hệ thống: Hiển thị thông báo lỗi, không lưu dữ liệu.
- Người dùng chọn **Lưu nháp**: Hệ thống không thực hiện kiểm tra tính đầy đủ của dữ liệu mà chỉ kiểm tra logic, hệ thống lưu thông tin Chỉnh sửa thông tin đăng ký với trạng thái là "Mới tạo"

## Hậu điều kiện
- Nếu thành công: Hồ sơ Chỉnh sửa thông tin đăng ký được lưu trong hệ thống.
- Nếu thất bại: Không có dữ liệu nào được thêm.

## Liên kết
- Activity Diagram: [AD_Sign_Update.puml]
- Form liên quan: [SCR_Sign_Update.md]
- Entity liên quan: ChuKySo, LichSuChuKySo
