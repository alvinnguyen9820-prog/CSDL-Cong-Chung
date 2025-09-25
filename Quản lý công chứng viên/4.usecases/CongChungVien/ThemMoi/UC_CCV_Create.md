# Use Case: UC_CCV_Create (Thêm mới công chứng viên)

## User Story
- Với vai trò là **Chuyên viên STP**, tôi muốn có thể thêm mới công chứng viên vào hệ thống, để đảm bảo dữ liệu công chứng viên luôn đầy đủ.

## Acceptance Criteria
- Hệ thống hiển thị form thêm mới công chứng viên.
- Hệ thống kiểm tra dữ liệu hợp lệ trước khi lưu thông tin công chứng viên.
- Nếu dữ liệu hợp lệ, hệ thống lưu công chứng viên mới vào danh sách và hiển thị thông báo thành công.
- Nếu dữ liệu không hợp lệ, hiển thị thông báo lỗi cụ thể (VD: "Số thẻ đã tồn tại").
- Người dùng có thể hủy thao tác thêm mới.

## Tác nhân chính
- Chuyên viên STP

## Tiền điều kiện
- Người dùng đã đăng nhập.
- Người dùng có quyền "Thêm mới công chứng viên".

## Luồng chính
1. Người dùng chọn chức năng **Thêm mới công chứng viên** từ danh sách (**UC_CCV_List**).
2. Hệ thống hiển thị form thêm mới (**SCR_CCV_Create**).
3. Người dùng nhập các thông tin cần thiết.
4. Người dùng bấm nút **Lưu**.
5. Hệ thống kiểm tra tính hợp lệ của dữ liệu:
   - Nếu hợp lệ: Lưu dữ liệu vào bảng **CongChungVien** và **Nguoi**.
   - Thông báo "Thêm mới công chứng viên thành công".
   - Quay lại danh sách công chứng viên (**UC_CCV_List**).
6. Kết thúc use case.

## Luồng phụ / Ngoại lệ
- Người dùng chọn **Hủy**: Form đóng, không lưu dữ liệu.
- Lỗi hệ thống: Hiển thị thông báo lỗi, không lưu dữ liệu.
- Lỗi dữ liệu: Hiển thị thông báo lỗi (**UC_CCV_CheckData**)

## Hậu điều kiện
- Nếu thành công: Công chứng viên mới được thêm vào hệ thống.
- Nếu thất bại: Không có dữ liệu mới nào được thêm.

## Liên kết
- Activity Diagram: [AD_CCV_Create.puml]
- Form liên quan: [SCR_CCV_Create.md]
- Entity liên quan: ENT_CongChungVien, ENT_Nguoi
