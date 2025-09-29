# Màn hình: Xác nhận xóa Thông tin đăng ký chữ ký số
Popup xác nhận khi người dùng thực hiện thao tác xóa Thông tin đăng ký chữ ký số từ danh sách.

## Điều kiện tiên quyết
- Người dùng đã đăng nhập và có quyền xóa Thông tin đăng ký chữ ký số.
- Người dùng chỉ có thể xóa Thông tin đăng ký chữ ký số thuộc tổ chức của mình.

## Nguyên mẫu
[https://www.figma.com/design/STv6BI8XR469xhObHjgCHs/Test-Puml?node-id=32-40731&t=qhcu7sCD1S2A6kb5-1]

## Thành phần

### Popup xác nhận

<div style="overflow-x:auto">

| Thành phần      | Control | Field | Bắt buộc (Y/N) | Mô tả                                                                                     |
|:----------------|:--------|:------|:---------------|:------------------------------------------------------------------------------------------|
| Thông báo chính | label   | -     | -              | Hiển thị nội dung: **“Bạn có chắc chắn muốn xóa Thông tin đăng ký chữ ký số này không?”** |
| Nút Xác nhận    | button  | -     | -              | Khi bấm, hệ thống kiểm tra ràng buộc trước khi xóa                                        |
| Nút Hủy         | button  | -     | -              | Khi bấm, đóng popup, không thực hiện xóa                                                  |

</div>

## Chức năng

<div style="overflow-x:auto">

| Tên        | Loại   | Mô tả                                                                 |
| :--------- | :----- | :-------------------------------------------------------------------- |
| Xác nhận   | Button | Thực hiện kiểm tra điều kiện xóa và xóa thông tin đăng ký chữ ký số nếu hợp lệ |
| Hủy        | Button | Đóng popup, không thực hiện thay đổi dữ liệu                          |

</div>
