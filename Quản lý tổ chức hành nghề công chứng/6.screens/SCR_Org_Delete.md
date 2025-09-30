# Màn hình: Xác nhận xóa tổ chức công chứng
Popup xác nhận khi người dùng thực hiện thao tác xóa tổ chức công chứng từ màn hình danh sách.

## Điều kiện tiên quyết
- Người dùng đã đăng nhập và có quyền xóa tổ chức công chứng.

## Nguyên mẫu
[https://www.figma.com/design/STv6BI8XR469xhObHjgCHs/Test-Puml?node-id=61-26622&t=D6KMt6aiRNAU7m7V-1]

## Thành phần

### Popup xác nhận

<div style="overflow-x:auto">

| Thành phần            | Control | Field | Bắt buộc (Y/N) | Mô tả                                                                            |
|:----------------------|:--------|:------|:---------------|:---------------------------------------------------------------------------------|
| Thông báo chính       | text    | -     | -              | Hiển thị nội dung: **“Bạn có chắc chắn muốn xóa tổ chức công chứng này không?”** |
| Thông báo phụ         | text    | -     | -              | Hiển thị nội dung: **“Hành động này không thể khôi phục”**                       |
| Nút Xác nhận          | button  | -     | -              | Khi bấm, hệ thống thực hiện kiểm tra ràng buộc trước khi xóa (**UC_SCR_Delete**) |
| Nút Hủy               | button  | -     | -              | Khi bấm, đóng popup, không thực hiện xóa                                         |
| Biểu tượng đóng popup | button  | -     | -              | Khi bấm, đóng popup, không thực hiện xóa                                         |
</div>
