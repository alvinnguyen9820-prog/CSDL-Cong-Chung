# Use Case: UC_Org_Create (Thêm mới tổ chức công chứng)

## User Story
- Với vai trò là **Chuyên viên STP**, tôi muốn có thể thêm mới tổ chức công chứng thuộc Sở Tư pháp của tôi vào hệ thống, để đảm bảo dữ liệu tổ chức công chứng luôn đầy đủ.

## Acceptance Criteria
- Hệ thống hiển thị form thêm mới tổ chức công chứng.
- Hệ thống kiểm tra dữ liệu hợp lệ trước khi lưu thông tin tổ chức công chứng.
- Nếu dữ liệu hợp lệ, hệ thống lưu tổ chức công chứng mới vào danh sách quản lý và hiển thị thông báo thành công.
- Nếu dữ liệu không hợp lệ, hiển thị thông báo lỗi cụ thể.
- Người dùng có thể hủy thao tác thêm mới.

## Tác nhân chính
- Chuyên viên STP

## Tiền điều kiện
- Người dùng đã đăng nhập.
- Người dùng có quyền "Thêm mới tổ chức công chứng".

## Luồng chính
1. Người dùng chọn chức năng **Thêm mới tổ chức công chứng** từ danh sách (**UC_Org_List**).
2. Hệ thống hiển thị form thêm mới (**SCR_Org_Create**).
3. Người dùng nhập các thông tin cần thiết.
4. Người dùng bấm nút **Lưu**.
5. Hệ thống kiểm tra tính hợp lệ của dữ liệu:
   - Nếu hợp lệ: Lưu dữ liệu vào **ENT_ToChucCongChung**.
   - Thông báo "Thêm mới tổ chức công chứng thành công".
   - Quay lại danh sách tổ chức công chứng (**UC_Org_List**).
6. Kết thúc use case.

## Luồng phụ / Ngoại lệ
- Người dùng chọn **Hủy**: Form đóng, không lưu dữ liệu.
- Lỗi hệ thống: Hiển thị thông báo lỗi, không lưu dữ liệu.
- Lỗi dữ liệu: Hiển thị thông báo lỗi (**UC_Org_CheckData**)

## Hậu điều kiện
- Nếu thành công: tổ chức công chứng mới được thêm vào hệ thống.
- Nếu thất bại: Không có dữ liệu mới nào được thêm.

## Liên kết
- Activity Diagram: [AD_Org_Create.puml]
- Form liên quan: [SCR_Org_Create.md]
- Entity liên quan: ENT_ToChucCongChung
