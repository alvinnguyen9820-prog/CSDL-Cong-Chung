# Màn hình: Chỉnh sửa thông tin đăng ký chữ ký số
Form cho phép chỉnh sửa thông tin hồ sơ đăng ký chữ ký số đã có.

## Điều kiện tiên quyết
- Người dùng đã đăng nhập hệ thống.
- Người dùng có quyền chỉnh sửa thông tin đăng ký chữ ký số.

## Nguyên mẫu
[https://www.figma.com/design/STv6BI8XR469xhObHjgCHs/Test-Puml?node-id=46-19813&t=qhcu7sCD1S2A6kb5-1]

## Thành phần

### Form chỉnh sửa (ENT_ChuKySo)

<div style="overflow-x:auto">

| Trường thông tin | Control  | Field           | Max length | Bắt buộc (Y/N) | Giá trị mặc định | Cho phép sửa (Y/N) | Mô tả                                        |
|:-----------------|:---------|:----------------|:-----------|:---------------|:-----------------|:-------------------|:---------------------------------------------|
| Công chứng viên  | dropdown | congChungVienId | -          | Y              | -                | Y                  | Hiển thị nếu loại chữ ký số = Cá nhân, chọn từ danh sách công chứng viên đã tạo                                       |
| Loại chữ ký số   | dropdown | loaiChuKySo     | -          | Y              | Cá nhân          | Y                  | Cá nhân / Tổ chức                            |
| Nhà cung cấp     | dropdown | nhaCungCap      | 255        | Y              | -                | Y                  | Chọn nhà cung cấp dịch vụ từ danh sách:      |
| Số serial        | text     | soSerial        | 100        | Y              | -                | Y                  | Điền số serial                               |
| Ngày hiệu lực    | datetime | ngayHieuLuc     | -          | Y              | -                | Y                  | Ngày bắt đầu hiệu lực của chữ ký số          |
| Ngày hết hạn     | datetime | ngayHetHan      | -          | Y              | -                | Y                  | Ngày hết hạn, phải lớn hơn ngày hiệu lực     |
| File đính kèm    | button   | -               | -          | Y              | -                | Y                  | button Upload file đính kèm (định dạng PDF/PNG/JPG) |
| Ghi chú          | textarea | ghiChu          | 1000       | N              | -                | Y                  | Ghi chú dùng                                 |

</div>

### Chức năng

<div style="overflow-x:auto">

| Tên         | Loại   | Mô tả                                                                                           |
|:------------|:-------|:------------------------------------------------------------------------------------------------|
| Trình duyệt | Button | Kiểm tra hợp lệ, lưu dữ liệu vào ENT_ChuKySo với trạng thái = "Chờ duyệt"                       |
| Lưu nháp    | Button | Không kiểm tra đầy đủ, Kiểm tra hợp lệ, lưu dữ liệu vào ENT_ChuKySo với trạng thái = "Tạo mới " |
| Đóng        | Button | Đóng popup                                                                                      |
