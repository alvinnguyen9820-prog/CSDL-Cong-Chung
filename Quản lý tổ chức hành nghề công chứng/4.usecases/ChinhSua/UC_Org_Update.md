# Use Case: UC_Org_Update (Chỉnh sửa tổ chức công chứng)

## User Story
- Với vai trò là **Chuyên viên STP**, tôi muốn có thể Chỉnh sửa tổ chức công chứng vào hệ thống, để đảm bảo dữ liệu tổ chức công chứng luôn đầy đủ và chính xác.

## Acceptance Criteria
- Hệ thống hiển thị form Chỉnh sửa tổ chức công chứng và điền sẵn thông tin đã lưu.
- Hệ thống kiểm tra dữ liệu hợp lệ trước khi lưu thông tin tổ chức công chứng.
- Nếu dữ liệu hợp lệ, hệ thống lưu tổ chức công chứng mới vào danh sách và hiển thị thông báo thành công.
- Nếu dữ liệu không hợp lệ, hiển thị thông báo lỗi cụ thể.
- Người dùng có thể hủy thao tác Chỉnh sửa.

## Tác nhân chính
- Chuyên viên STP

## Tiền điều kiện
- Người dùng đã đăng nhập.
- Người dùng có quyền "Chỉnh sửa tổ chức công chứng".

## Luồng chính
1. Người dùng chọn chức năng **Chỉnh sửa tổ chức công chứng** từ danh sách (**SCR_Org_List**) hoặc màn hình chi tiết (**SCR_Org_Detail**).
2. Hệ thống hiển thị form Chỉnh sửa (**SCR_Org_Update**).
3. Người dùng nhập các thông tin cần thiết.
4. Người dùng bấm nút **Lưu**.
5. Hệ thống kiểm tra tính hợp lệ của dữ liệu:
   - Nếu hợp lệ: Cập nhật dữ liệu vào bảng **ENT_ToChucCongChung**.
   - Thông báo "Chỉnh sửa tổ chức công chứng thành công".
   - Quay lại danh sách tổ chức công chứng (**UC_Org_List**).
6. Kết thúc use case.

## Luồng phụ / Ngoại lệ 
- Người dùng chọn **Hủy**: Form đóng, không lưu dữ liệu.
- Lỗi hệ thống: Hiển thị thông báo lỗi, không lưu dữ liệu.
- Lỗi dữ liệu: Hiển thị thông báo lỗi (**UC_Org_CheckData**)

## Hậu điều kiện
- Nếu thành công: tổ chức công chứng được cập nhật thông tin.
- Nếu thất bại: Không có dữ liệu mới nào được thêm.

## Liên kết
- Activity Diagram: [AD_Org_Update.puml]
- Form liên quan: [SCR_Org_Update.md]
- Entity liên quan: ENT_ToChucCongChung
