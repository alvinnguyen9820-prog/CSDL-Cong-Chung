# Use Case: UC_CCV_CheckData (Kiểm tra tính hợp lệ của dữ liệu công chứng viên khi lưu thông tin)

## User Story
- Với vai trò là **Chuyên viên STP**, tôi muốn khi lưu thông tin công chứng viên, hệ thống phải thực hiện kiểm tra tính hợp lệ của dữ liệu, để đảm bảo dữ liệu công chứng viên luôn chính xác.

## Acceptance Criteria
- Hệ thống kiểm tra dữ liệu hợp lệ trước khi lưu thông tin công chứng viên.
- Nếu dữ liệu hợp lệ, hệ thống thêm mới/cập nhật thông tin công chứng viên và tiếp tục luồng xử lý.
- Nếu dữ liệu không hợp lệ, hiển thị thông báo lỗi cụ thể (VD: "Số thẻ đã tồn tại").

## Tác nhân chính
- Chuyên viên STP

## Tiền điều kiện
- Người dùng đã đăng nhập.
- Người dùng đang thực hiện lưu thông tin công chứng viên.

## Luồng chính
1. Người dùng thực hiện lưu thông tin công chứng viên trong **UC_CCV_Create** hoặc **UC_CCV_Update**.
2. Hệ thống thực hiện kiểm tra tính hợp lệ của dữ liệu
3. Nếu thông tin đúng định dạng (mô tả trong **SCR_CCV_Create**) và các thông tin bắt buộc không bị trống, hệ thống tiếp tục kiểm tra logic. Nếu không thì hiển thị thông báo lỗi: "Thông tin không hợp lệ"
4. Nếu ngày cấp giấy tờ hoặc ngày sinh lớn hơn ngày hiện tại, hệ thống thông báo lỗi "Thông tin không hợp lệ". Nếu không tiếp tục luồng hiện tại
5. Nếu số thẻ bị trùng với công chứng viên khác trong hệ thống, hệ thống thông báo lỗi "Số thẻ đã tồn tại". Nếu không tiếp tục luồng hiện tại
6. Nếu số giấy tờ cá nhân bị trùng với công chứng viên khác trong hệ thống, hệ thống thông báo lỗi "Số CCCD/CMND/Hộ chiếu đã tồn tại". Nếu không tiếp tục luồng hiện tại
7. Nếu ngày cấp giấy tờ hoặc ngày sinh lớn hơn ngày hiện tại, hệ thống thông báo lỗi "Thông tin không hợp lệ". Nếu không tiếp tục luồng hiện tại
8. Kết thúc use case.

## Luồng phụ / Ngoại lệ
- Lỗi hệ thống: Hiển thị thông báo lỗi, không lưu dữ liệu.

## Hậu điều kiện
- Nếu thành công: Thông tin công chứng viên được cập nhật/thêm mới.
- Nếu thất bại: Không có dữ liệu mới nào được thêm/Cập nhật.

## Liên kết
- Activity Diagram: [AD_CCV_CheckData.puml]
- Entity liên quan: ENT_CongChungVien, ENT_Nguoi
