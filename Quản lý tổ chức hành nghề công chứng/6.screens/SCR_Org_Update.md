# Màn hình: Chỉnh sửa tổ chức công chứng
Popup form cho phép chỉnh sửa thông tin một tổ chức hành nghề công chứng.

## Điều kiện tiên quyết
- Người dùng đã đăng nhập và có quyền chỉnh sửa tổ chức công chứng.

## Nguyên mẫu
[https://www.figma.com/design/STv6BI8XR469xhObHjgCHs/Test-Puml?node-id=61-25542&t=D6KMt6aiRNAU7m7V-1]

## Thành phần

### Form chỉnh sửa thông tin

<div style="overflow-x:auto">

| Trường thông tin       | Control  | Field              | Max length | Bắt buộc (Y/N) | Giá trị mặc định | Cho phép sửa (Y/N) | Mô tả                                                          |
|:-----------------------|:---------|:-------------------|:-----------|:---------------|:-----------------|:-------------------|:---------------------------------------------------------------|
| Tên tổ chức công chứng | text     | tenToChucCongChung | 255        | Y              | -                | Y                  | Đổ ra dữ liệu đã lưu                                           |
| Sở Tư pháp quản lý     | text     | soTuPhap           | 255        | Y              | -                | N                  | Đổ ra tên Sở Tư pháp quản lý. Disable, không cho phép thay đổi |
| Địa chỉ                | text     | diaChi             | 500        | Y              | -                | Y                  | Đổ ra dữ liệu đã lưu chính                                     |
| Tỉnh/Thành phố         | dropdown | tinhThanhPho       | 255        | Y              | -                | Y                  | Chọn tỉnh/thành phố đã lưu                                     |
| Phường/Xã              | dropdown | phuongXa           | 255        | N              | -                | Y                  | Chọn phường/xã đã lưu                                          |
| Số điện thoại          | text     | soDienThoai        | 20         | N              | -                | Y                  | Đổ ra dữ liệu đã lưu hệ                                        |
| Email                  | text     | email              | 255        | N              | -                | Y                  | Đổ ra dữ liệu đã lưu                                           |
| Trạng thái hoạt động   | dropdown | trangThai          | -          | Y              | -                | Y                  | Chọn trạng thái đã lưu…                                        |

</div>

### Chức năng
<div style="overflow-x:auto">

| Tên | Loại   | Mô tả                                                                                                 |
|:----|:-------|:------------------------------------------------------------------------------------------------------|
| Lưu | Button | Lưu dữ liệu nhập vào. Nếu hợp lệ thì cập nhật dữ liệu và đóng popup. Chi tiết trong **UC_Org_Update** |
| Hủy | Button | Hủy thao tác, đóng popup mà không lưu dữ liệu                                                         |
