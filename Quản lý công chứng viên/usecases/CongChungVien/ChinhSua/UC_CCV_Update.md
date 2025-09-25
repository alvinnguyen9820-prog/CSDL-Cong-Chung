# Use Case: UC_CCV_Update (Chỉnh sửa công chứng viên)

## User Story
- Với vai trò là **Chuyên viên STP**, tôi muốn có thể chỉnh sửa thông tin công chứng viên đã có trong hệ thống, để đảm bảo dữ liệu luôn chính xác và cập nhật.

## Acceptance Criteria
- Hệ thống hiển thị form chỉnh sửa với dữ liệu hiện tại của công chứng viên.
- Người dùng có thể thay đổi các thông tin: Họ tên, Giới tính, Ngày sinh, Địa chỉ, Số điện thoại, Email, Số thẻ, Trạng thái, Ngày cấp thẻ.
- Hệ thống kiểm tra dữ liệu hợp lệ (không trùng số thẻ, số giấy tờ).
- Nếu hợp lệ: hệ thống lưu thông tin đã chỉnh sửa và thông báo thành công.
- Nếu không hợp lệ: hiển thị thông báo lỗi cụ thể (VD: "Số thẻ đã tồn tại").
- Người dùng có thể hủy thao tác chỉnh sửa.

## Tác nhân chính
- Chuyên viên STP

## Tiền điều kiện
- Người dùng đã đăng nhập và có quyền chỉnh sửa công chứng viên.
- Người dùng đã chọn 1 công chứng viên từ danh sách.

## Luồng chính (Happy Case)
1. Người dùng chọn chức năng **Chỉnh sửa** từ danh sách (**UC_CCV_List**).
2. Hệ thống hiển thị form chỉnh sửa (**SCR_CCV_Update**) với dữ liệu hiện tại.
3. Người dùng cập nhật thông tin cần thay đổi.
4. Người dùng bấm nút **Lưu**.
5. Hệ thống kiểm tra dữ liệu:
   - Nếu hợp lệ: cập nhật vào DB (Nguoi, CongChungVien), hiển thị thông báo "Cập nhật thành công" và quay về danh sách.
   - Nếu không hợp lệ: hiển thị lỗi, cho phép người dùng sửa lại.
6. Kết thúc use case.

## Luồng phụ / Ngoại lệ
- Người dùng chọn **Hủy**: Form đóng, không thay đổi dữ liệu.
- Nhập thiếu thông tin bắt buộc: Hiển thị cảnh báo lỗi.
- Trùng số thẻ / số giấy tờ: Hiển thị thông báo lỗi.
- Lỗi hệ thống: Hiển thị thông báo lỗi, không lưu dữ liệu.

## Hậu điều kiện
- Nếu thành công: Dữ liệu công chứng viên được cập nhật.
- Nếu thất bại: Không có thay đổi nào được lưu.

## Liên kết
- Activity Diagram: [AD_CCV_Update.puml]
- Form liên quan: [SCR_CCV_Update.md]
- Entity liên quan: CongChungVien, Nguoi
