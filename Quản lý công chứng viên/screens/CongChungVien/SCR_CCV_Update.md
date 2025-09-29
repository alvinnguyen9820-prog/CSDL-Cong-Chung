# Màn hình: Chỉnh sửa công chứng viên
Form cho phép chỉnh sửa thông tin công chứng viên, hiển thị dữ liệu đã có và cho phép cập nhật.

## Điều kiện tiên quyết
- Người dùng đã đăng nhập và có quyền chỉnh sửa công chứng viên.

## Nguyên mẫu
[https://www.figma.com/design/STv6BI8XR469xhObHjgCHs/Test-Puml?node-id=44-17314&t=qhcu7sCD1S2A6kb5-1]

## Thành phần

### Thông tin cá nhân (ENT_Nguoi)

<div style="overflow-x:auto">

| Trường thông tin                | Control  | Field          | Max length | Bắt buộc (Y/N) | Giá trị mặc định | Cho phép sửa (Y/N) | Mô tả                               |
|:--------------------------------|:---------|:---------------|:-----------|:---------------|:-----------------|:-------------------|:------------------------------------|
| Họ và tên                       | text     | hoVaTen        | 255        | Y              | -                | Y                  | Họ và tên công chứng viên           |
| Ngày sinh                       | date     | ngaySinh       | -          | Y              | -                | Y                  | Ngày sinh chọn từ lịch              |
| Giới tính                       | dropdown | gioiTinh       | -          | Y              | -                | Y                  | Nam/Nữ                              |
| Quốc tịch                       | text     | quocTich       | 20         | Y              | Việt Nam         | N                  |                                     |
| Dân tộc                         | dropdown | danToc         | 20         | N              | -                | Y                  | Chọn từ danh sách dân tộc           |
| Số điện thoại                   | text     | soDienThoai    | 20         | N              | -                | Y                  |                                     |
| Email                           | text     | email          | 255        | N              | -                | Y                  |                                     |
| Số giấy tờ (CMND/CCCD/Hộ chiếu) | text     | soGiayTo       | 50         | Y              | -                | Y                  |                                     |
| Ngày cấp                        | datetime | ngayCap        | -          | Y              | -                | Y                  |                                     |
| Nơi cấp                         | text     | noiCap         | 255        | Y              | -                | Y                  |                                     |
| Địa chỉ thường trú (cũ)         | text     | diaChiCu       | 500        | N              | -                | Y                  |                                     |
| Tỉnh/Thành phố thường trú (cũ)  | dropdown | tinhThanhPhoCu | 255        | N              | -                | Y                  | Chọn từ danh mục tỉnh thành phố cũ  |
| Phường/Xã thường trú (cũ)       | dropdown | phuongXaCu     | 255        | N              | -                | Y                  | Chọn từ danh mục phường xã cũ       |
| Địa chỉ thường trú              | text     | diaChi         | 500        | Y              | -                | Y                  |                                     |
| Tỉnh/Thành phố thường trú       | dropdown | tinhThanhPho   | 255        | Y              | -                | Y                  | Chọn từ danh mục tỉnh thành phố mới |
| Phường/Xã thường trú            | dropdown | phuongXa       | 255        | Y              | -                | Y                  | Chọn từ danh mục phờng xã mới       |
| Trạng thái                      | dropdown | trangThai      | 50         | Y              | Active           | Y                  | Đăng ký tập sự, Đang tập sự, Tạm ngừng tập sự, Chấm dứt tập sự, Hoàn thành tập sự, Chờ tiếp nhận bổ nhiệm, Chờ bổ nhiệm, Đã bổ nhiệm, Đang hành nghề, Tạm đình chỉ hành nghề, Đã bổ nhiệm lại, Đã miễn nhiệm, Chờ bổ sung, Đã bổ sung, Từ chối bổ nhiệm, Đã thay đổi nơi tập sự, Chờ tiếp nhận miễn nhiệm, Chờ tiếp nhận bổ nhiệm lại, Từ chối miễn nhiệm, Chờ bổ nhiệm lại, Từ chối bổ nhiệm lại, Chờ miễn nhiệm, Thu hồi thẻ, Chờ cấp thẻ, Từ chối cấp thẻ, Đạt kết quả tập sự|

</div>

### Thông tin hành nghề (ENT_CongChungVien, ENT_ToChucCongChung)

<div style="overflow-x:auto">

| Trường thông tin           | Control  | Field                 | Max length | Bắt buộc (Y/N) | Giá trị mặc định | Cho phép sửa (Y/N) | Mô tả                        |
|:---------------------------|:---------|:----------------------|:-----------|:---------------|:-----------------|:-------------------|:-----------------------------|
| Tên tổ chức công chứng     | dropdown | tenToChucCongChung    | 255        | Y              | -                | Y                  | Chọn từ danh sách tổ chức    |
| Địa chỉ tổ chức công chứng | text     | diaChiToChucCongChung | 500        | N              | -                | N                  | Tự động điền từ tổ chức chọn |
| Số thẻ công chứng viên     | text     | soThe                 | 50         | Y              | -                | Y                  | Số hiệu thẻ hành nghề        |

</div>

## Chức năng

<div style="overflow-x:auto">

| Tên        | Loại    | Mô tả                                                                    |
| :--------- | :------ | :----------------------------------------------------------------------- |
| Lưu        | Button  | Kiểm tra hợp lệ, cập nhật dữ liệu vào ENT_CongChungVien, ENT_Nguoi       |
| Đóng        | Button  | Đóng form, không lưu dữ liệu                                             |

</div>
