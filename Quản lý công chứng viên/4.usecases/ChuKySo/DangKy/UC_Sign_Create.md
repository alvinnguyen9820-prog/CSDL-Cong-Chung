# Use Case: UC_Sign_Create (Đăng ký chữ ký số)

## User Story
- Với vai trò là **Công chứng viên / Nhân viên TCHNCC**, tôi muốn có thể đăng ký chữ ký số mới để phục vụ hoạt động hành nghề công chứng.

## Acceptance Criteria
- Hệ thống hiển thị form đăng ký chữ ký số.
- Người dùng nhập thông tin: 
   - Công chứng viên (Nếu loại chữ ký số là cá nhân)
   - Loại chữ ký số (Cá nhân/Tổ chức)
   - Nhà cung cấp
   - Mã chứng thư
   - Ngày hiệu lực
   - Ngày hết hạn 
   - File đính kèm
   - Ghi chú
- Hệ thống kiểm tra dữ liệu hợp lệ (thời gian hiệu lực/hết hạn, file đúng định dạng).
- Nếu hợp lệ: lưu hồ sơ đăng ký ở trạng thái **"Mới tạo"** hoặc **"Chờ duyệt"**.
- Hiển thị thông báo "Đăng ký thành công".
- Người dùng có thể hủy thao tác đăng ký.

## Tác nhân chính
- Công chứng viên  
- Nhân viên TCHNCC  

## Tiền điều kiện
- Người dùng đã đăng nhập và có quyền đăng ký chữ ký số.
- Công chứng viên đã có hồ sơ hành nghề hợp lệ trong hệ thống.

## Luồng chính
1. Người dùng chọn chức năng **Đăng ký chữ ký số** từ menu (**SCR_Sign_List**).
2. Hệ thống hiển thị form đăng ký (**SCR_Sign_Create**).
3. Người dùng nhập các thông tin cần thiết.
4. Người dùng bấm nút **Trình duyệt**.
5. Hệ thống kiểm tra dữ liệu:
   - Nếu hợp lệ: lưu dữ liệu vào **ENT_ChuKySo** với trạng thái = "Chờ duyệt".
   - Hiển thị thông báo "Đăng ký thông tin chữ ký số thành công".
   - Lịch sử đăng ký thông tin chữ ký số được cập nhật
   - Quay về danh sách (**UC_Sign_List**).
6. Kết thúc use case.

## Luồng phụ / Ngoại lệ
- Người dùng chọn **Hủy**: Form đóng, không lưu dữ liệu.
- Nhập thiếu thông tin bắt buộc: Hiển thị cảnh báo lỗi.
- Ngày hết hạn < ngày hiệu lực: Hiển thị lỗi "Ngày hết hạn không hợp lệ".
- File đính kèm sai định dạng: Hiển thị lỗi "File không hợp lệ".
- Lỗi hệ thống: Hiển thị thông báo lỗi, không lưu dữ liệu.
- Người dùng chọn **Lưu nháp**: Hệ thống không thực hiện kiểm tra tính đầy đủ của dữ liệu mà chỉ kiểm tra logic, hệ thống lưu thông tin đăng ký chữ ký số với trạng thái là "Mới tạo"

## Hậu điều kiện
- Nếu thành công: Hồ sơ đăng ký chữ ký số được lưu trong hệ thống.
- Nếu thất bại: Không có dữ liệu nào được thêm.

## Liên kết
- Activity Diagram: [AD_Sign_Create.puml]
- Form liên quan: [SCR_Sign_Create.md]
- Entity liên quan: ChuKySo, CongChungVien
