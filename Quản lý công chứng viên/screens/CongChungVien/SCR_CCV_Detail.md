# Màn hình: Chi tiết công chứng viên
Hiển thị đầy đủ hồ sơ cá nhân, tổ chức hành nghề và chứng chỉ hành nghề (nếu có quyền).

## Điều kiện tiên quyết
- Người dùng đã đăng nhập hệ thống.
- Người dùng có quyền xem chi tiết thông tin công chứng viên.

## Nguyên mẫu
[https://www.figma.com/design/STv6BI8XR469xhObHjgCHs/Test-Puml?node-id=31-34764&t=qhcu7sCD1S2A6kb5-1]
[https://www.figma.com/design/STv6BI8XR469xhObHjgCHs/Test-Puml?node-id=44-16244&t=qhcu7sCD1S2A6kb5-1]

## Thành phần

### Thông tin chung (ENT_CongChungVien, ENT_Nguoi)

<div style="overflow-x:auto">

| Trường thông tin                | Control  | Field          | Max length | Bắt buộc (Y/N) | Cho phép sửa (Y/N) | Mô tả                       |
|:--------------------------------|:---------|:---------------|:-----------|:---------------|:-------------------|:----------------------------|
| Họ và tên                       | text     | hoVaTen        | 255        | Y              | N                  | Họ tên công chứng viên      |
| Ngày sinh                       | datetime | ngaySinh       | -          | Y              | N                  | Ngày sinh                   |
| Giới tính                       | text     | gioiTinh       | -          | Y              | N                  | Giới tính                   |
| Số điện thoại                   | text     | soDienThoai    | 20         | N              | N                  | Số điện thoại liên hệ       |
| Quốc tịch                       | text     | quocTich       | 20         | N              | N                  | Quốc tịch                   |
| Dân tộc                         | text     | danToc         | 20         | N              | N                  | Dân tộc                     |
| Email                           | text     | email          | 255        | N              | N                  | Email                       |
| Số giấy tờ (CMND/CCCD/Hộ chiếu) | text     | soGiayTo       | 50         | Y              | N                  | Thông tin giấy tờ định danh |
| Ngày cấp                        | datetime | ngayCap        | -          | N              | N                  | Ngày cấp giấy tờ định danh  |
| Nơi cấp                         | text     | noiCap         | 255        | N              | N                  | Nơi cấp giấy tờ định danh   |
| Địa chỉ thường trú (cũ)         | text     | diaChiCu       | 500        | N              | N                  | Địa chỉ thường trú          |
| Tỉnh/Thành phố thường trú (cũ)  | text     | tinhThanhPhoCu | 255        | N              | N                  | Thông tin cũ                |
| Phường/Xã thường trú (cũ)       | text     | phuongXaCu     | 255        | N              | N                  | Thông tin cũ                |
| Địa chỉ thường trú              | text     | diaChiCu       | 500        | N              | N                  | Địa chỉ thường trú          |
| Tỉnh/Thành phố thường trú (mới) | text     | tinhThanhPho   | 255        | N              | N                  | Thông tin hiện tại          |
| Phường/Xã thường trú (mới)      | text     | phuongXa       | 255        | N              | N                  | Thông tin hiện tại          |

</div>

### Thông tin tổ chức hành nghề (ENT_CongChungVien, ENT_ToChucCongChung)

<div style="overflow-x:auto">

| Trường thông tin           | Control | Field                 | Max length | Bắt buộc (Y/N) | Cho phép sửa (Y/N) | Mô tả                             |
|:---------------------------|:--------|:----------------------|:-----------|:---------------|:-------------------|:----------------------------------|
| Tên tổ chức công chứng     | text    | tenToChucCongChung    | 255        | Y              | N                  | Tổ chức công chứng đang hành nghề |
| Địa chỉ tổ chức công chứng | text    | diaChiToChucCongChung | 500        | N              | N                  | Địa chỉ tổ chức công chứng        |
| Số thẻ công chứng viên     | text    | soThe                 | 50         | Y              | N                  | Số hiệu thẻ hành nghề             |
| Trạng thái                 | text    | trangThai             | 50         | Y              | N                  | Trạng thái hoạt động              |

</div>

### Thông tin chứng chỉ hành nghề (ENT_ChungChiHanhNghe) *(nếu có quyền)*

<div style="overflow-x:auto">

| Trường thông tin    | Control  | Field        | Max length | Bắt buộc (Y/N) | Cho phép sửa (Y/N) | Mô tả                              |
| :------------------ | :------- | :----------- | :--------- | :------------- | :----------------- | :--------------------------------- |
| Số chứng chỉ        | text     | licenseNo    | 50         | Y              | N                  | Hiển thị mã số chứng chỉ hành nghề           |
| Ngày cấp            | datetime | issueDate    | -          | Y              | N                  | Hiển thị ngày cấp chứng chỉ                  |
| Nơi cấp             | text     | issuePlace   | 255        | N              | N                  | Hiển thị nơi cấp chứng chỉ                   |
| Ngày hiệu lực       | datetime | effectiveDate| -          | Y              | N                  | Hiển thị ngày hiệu lực                       |
| Ngày hết hạn        | datetime | expiryDate   | -          | N              | N                  | Hiển thị ngày hết hạn                        |
| Đơn vị cấp          | text     | authority    | 255        | N              | N                  | Hiển thị cơ quan cấp chứng chỉ               |
| Trạng thái          | text     | status       | 50         | Y              | N                  | Hiển thị trạng thái chứng chỉ                 |
| File đính kèm       | file     | attachment   | -          | N              | N                  | Link file chứng chỉ, click vào mở tab mới hiển thị file           |

</div>

## Chức năng

<div style="overflow-x:auto">

| Tên                        | Loại   | Mô tả                                                                            |
|:---------------------------|:-------|:---------------------------------------------------------------------------------|
| Quay lại / Đóng            | Button | Trở về màn hình danh sách công chứng viên (**SCR_CCV_List**)                     |
| Chỉnh sửa                  | Button | Mở màn hình chỉnh sửa thông tin công chứng viên (**UC_CCV_Update**)              |
| Lịch sử cập nhật chứng chỉ | Button | Xem lịch sử cập nhật chứng chỉ (**UC_ChungChi_History**) (Hiển thị nếu có quyền) |

</div>
