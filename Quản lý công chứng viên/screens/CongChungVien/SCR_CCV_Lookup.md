# Màn hình: Tra cứu công chứng viên
Form cho phép người dùng nhập tiêu chí tra cứu và hiển thị danh sách công chứng viên phù hợp.

## Điều kiện tiên quyết
- Người dùng đã đăng nhập hệ thống.
- Người dùng có quyền tra cứu thông tin công chứng viên và chứng chỉ hành nghề.

## Nguyên mẫu
[https://www.figma.com/design/STv6BI8XR469xhObHjgCHs/Test-Puml?node-id=32-37062&t=qhcu7sCD1S2A6kb5-1]
[https://www.figma.com/design/STv6BI8XR469xhObHjgCHs/Test-Puml?node-id=48-23175&t=qhcu7sCD1S2A6kb5-1]

## Thành phần

### Form tra cứu

<div style="overflow-x:auto">

| Trường thông tin             | Control  | Field              | Max length | Bắt buộc (Y/N) | Mô tả                                                       |
|:-----------------------------|:---------|:-------------------|:-----------|:---------------|:------------------------------------------------------------|
| Họ và tên                    | text     | hoVaTen            | 255        | N              | Tra cứu gần đúng theo họ và tên công chứng viên             |
| Số thẻ CCV                   | text     | soThe              | 50         | N              | Tra cứu chính xác số thẻ công chứng viên                    |
| Số chứng chỉ hành nghề       | text     | soChungChi         | 50         | N              | Tra cứu chính xác số chứng chỉ hành nghề                    |
| Trạng thái                   | dropdown | trangThai          | -          | N              | Lọc theo trạng thái hành nghề (Đang hành nghề, Tạm dừng, …) |
| Tỉnh/Thành phố TCHNCC        | dropdown | tinhThanhPho       | -          | N              | Lọc theo tỉnh/thành phố của tổ chức hành nghề công chứng    |
| Tổ chức hành nghề công chứng | dropdown | tenToChucCongChung | -          | N              | Lọc theo tên tổ chức hành nghề công chứng                   |

</div>

### Bảng kết quả

<div style="overflow-x:auto">

| Trường thông tin             | Control | Field             | Max length | Bắt buộc (Y/N) | Cho phép sửa (Y/N) | Mô tả                                 |
|:-----------------------------|:--------|:------------------|:-----------|:---------------|:-------------------|:--------------------------------------|
| Họ và tên                    | text    | hoVaTen           | 255        | Y              | N                  | Họ và tên công chứng viên             |
| Số thẻ CCV                   | text    | soThe             | 50         | Y              | N                  | Số hiệu thẻ hành nghề công chứng viên |
| Số chứng chỉ hành nghề       | text    | soChungChi        | 50         | N              | N                  | Số chứng chỉ hành nghề                |
| Tổ chức công chứng hành nghề | text    | tenToChuCongChung | 255        | Y              | N                  | Tổ chức công chứng đang hành nghề     |
| Trạng thái hoạt động         | text    | trangThai         | 50         | Y              | N                  | Trạng thái công chứng viên            |

</div>

### Popup chi tiết chứng chỉ hành nghề

<div style="overflow-x:auto">

| Trường thông tin | Control  | Field       | Max length | Bắt buộc (Y/N) | Mô tả                       |
|:-----------------|:---------|:------------|:-----------|:---------------|:----------------------------|
| Số chứng chỉ     | text     | soChungChi  | 50         | Y              | Mã số chứng chỉ hành nghề   |
| Ngày cấp         | datetime | ngayCap     | -          | Y              | Ngày cấp chứng chỉ          |
| Nơi cấp          | text     | noiCap      | 255        | N              | Nơi cấp chứng chỉ           |
| Ngày hiệu lực    | datetime | ngayHieuLuc | -          | Y              | Ngày bắt đầu có hiệu lực    |
| Ngày hết hạn     | datetime | ngayHetHan  | -          | N              | Ngày chứng chỉ hết hiệu lực |
| Đơn vị cấp       | text     | donVi       | 255        | N              | Cơ quan cấp chứng chỉ       |
| Trạng thái       | text     | trangThai   | 50         | Y              | Trạng thái chứng chỉ        |

</div>

## Chức năng

<div style="overflow-x:auto">

| Tên          | Loại    | Mô tả                                                                 |
| :----------- | :------ | :-------------------------------------------------------------------- |
| Tra cứu      | Button  | Thực hiện tra cứu theo tiêu chí đã nhập                               |
| Phân trang   | Control | Hiển thị danh sách theo trang (10 bản ghi/trang)                      |
| Đóng popup   | Button  | Đóng popup chi tiết chứng chỉ hành nghề, quay lại màn hình tra cứu     |

</div>
