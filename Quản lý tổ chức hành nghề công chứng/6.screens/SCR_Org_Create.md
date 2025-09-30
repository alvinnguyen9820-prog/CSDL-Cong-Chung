# Màn hình: Thêm/Sửa tổ chức công chứng
Popup form cho phép thêm mới thông tin một tổ chức hành nghề công chứng.

## Điều kiện tiên quyết
- Người dùng đã đăng nhập và có quyền thêm mới tổ chức công chứng.

## Nguyên mẫu
[https://www.figma.com/design/STv6BI8XR469xhObHjgCHs/Test-Puml?node-id=61-25541&t=D6KMt6aiRNAU7m7V-1]

## Thành phần

### Form nhập liệu

<div style="overflow-x:auto">

| Trường thông tin       | Control  | Field              | Max length | Bắt buộc (Y/N) | Giá trị mặc định | Cho phép sửa (Y/N) | Mô tả                                                                                                                                                                                                           |
|:-----------------------|:---------|:-------------------|:-----------|:---------------|:-----------------|:-------------------|:----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Tên tổ chức công chứng | text     | tenToChucCongChung | -        | Y              |                  | Y                  | Điền tên của tổ chức hành nghề công chứng                                                                                                                                                                       |
| Sở Tư pháp quản lý     | text     | soTuPhap           | -        | Y              |                  | N                  | Tự động chọn Sở Tư pháp giống với người dùng. Disable, không cho phép thay đổi                                                                                                                                  |
| Địa chỉ                | text     | diaChi             | -        | Y              |                  | Y                  | Điền địa chỉ trụ sở chính                                                                                                                                                                                       |
| Tỉnh/Thành phố         | dropdown | tinhThanhPho       | -        | Y              |                  | Y                  | Chọn tỉnh/thành phố từ danh mục hành chính quốc gia, sau khi chọn sẽ cập nhật danh sách phường xã tương ứng với tỉnh thành                                                                                      |
| Phường/Xã              | dropdown | phuongXa           | -        | Y              |                  | Y                  | Chọn phường/xã từ danh mục hành chính quốc gia, danh sách hiển thị theo tỉnh thành đã chọn                                                                                                                      |
| Số điện thoại          | text     | soDienThoai        | -         | N              |                  | Y                  | Điền số điện thoại liên hệ, validate theo cấu trúc số điện thoại Việt Nam                                                                                                                                       |
| Email                  | text     | email              | -        | N              |                  | Y                  | Nhập email liên hệ, validate theo cấu trúc email                                                                                                                                                                |
| Trưởng văn phòng       | dropdown | truongVanPhongId   | -          | Y              |                  | Y                  | Click vào cho phép chọn công chứng viên từ danh sách (entity CongChungVien), cho phép điền và tìm kiếm theo số giấy tờ/tên công chứng viên, danh sách hiển thị theo cấu trúc "Số giấy tờ - Tên công chứng viên" |
| Trạng thái hoạt động   | dropdown | trangThai          | -          | Y              | Đang hoạt động   | Y                  | Chọn trạng thái hoạt động theo danh sách đã liệt kê trong entity                                                                                                                                                |

</div>

### Chức năng
<div style="overflow-x:auto">

| Tên | Loại   | Mô tả                                                                                                 |
|:----|:-------|:------------------------------------------------------------------------------------------------------|
| Lưu | Button | Lưu dữ liệu nhập vào. Nếu hợp lệ thì cập nhật dữ liệu và đóng popup. Chi tiết trong **UC_Org_Create** |
| Hủy | Button | Hủy thao tác, đóng popup mà không lưu dữ liệu                                                         |
