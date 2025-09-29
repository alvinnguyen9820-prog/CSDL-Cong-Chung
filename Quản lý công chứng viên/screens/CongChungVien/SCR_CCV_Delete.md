# Màn hình: Xác nhận xóa công chứng viên
Popup xác nhận khi người dùng thực hiện thao tác xóa công chứng viên từ màn hình danh sách.

## Điều kiện tiên quyết
- Người dùng đã đăng nhập và có quyền xóa công chứng viên.

## Nguyên mẫu
[https://www.figma.com/design/STv6BI8XR469xhObHjgCHs/Test-Puml?node-id=32-42161&t=qhcu7sCD1S2A6kb5-1]

## Thành phần

### Popup xác nhận

<div style="overflow-x:auto">

| Thành phần      | Control | Field | Bắt buộc (Y/N) | Mô tả                                                                         |
|:----------------|:--------|:------|:---------------|:------------------------------------------------------------------------------|
| Thông báo chính | text    | -     | -              | Hiển thị nội dung: **“Bạn có chắc chắn muốn xóa công chứng viên này không?”** |
| Thông báo phụ   | text    | -     | -              | Hiển thị nội dung: **“Hành động này không thể khôi phục”**                    |
| Nút Xác nhận    | button  | -     | -              | Khi bấm, hệ thống thực hiện kiểm tra ràng buộc trước khi xóa                  |
| Nút Hủy         | button  | -     | -              | Khi bấm, đóng popup, không thực hiện xóa                                      |

</div>
