# Màn hình: Danh sách công chứng viên
Nơi tập trung để xem và quản lý công chứng viên trên hệ thống.

## Điều kiện tiên quyết
- Người dùng đã đăng nhập và có quyền xem danh sách công chứng viên.

## Nguyên mẫu
[https://www.figma.com/design/STv6BI8XR469xhObHjgCHs/Test-Puml?node-id=31-14766&t=qhcu7sCD1S2A6kb5-1]

## Thành phần

### Bảng chính

<div style="overflow-x:auto">

| Trường thông tin     | Control | Field                 | Max length | Bắt buộc (Y/N) | Giá trị mặc định | Cho phép sửa (Y/N) | Mô tả                                           |
|:---------------------|:--------|:----------------------|:-----------|:---------------|:-----------------|:-------------------|:------------------------------------------------|
| Họ và tên            | text    | hoVaTen               | -          | Y              | -                | -                  | Họ và tên công chứng viên                       |
| Số thẻ               | text    | soThe                 | -          | Y              | -                | -                  | Số hiệu thẻ hành nghề công chứng                |
| Tổ chức công chứng   | text    | tenToChucCongChung    | -          | Y              | -                | -                  | Tên tổ chức công chứng đang hành nghề           |
| Địa chỉ tổ chức      | text    | diaChiToChucCongChung | -          | Y              | -                | -                  | Địa chỉ tổ chức công chứng                      |
| Trạng thái hoạt động | text    | trangThai             | -          | Y              | -                | -                  | Trạng thái hoạt động                            |
| Hoạt động            | icon    | -                     | -          | -              | -                | -                  | Xem chi tiết, Sửa, Xóa, Xem lịch sử (tùy quyền) |

</div>

### Khác
- Phân trang 10 bản ghi/trang.  
- Sắp xếp theo thứ tự thời gian cập nhật từ mới tới cũ nhất.  
- Nếu không có dữ liệu, hiển thị: **"Không có dữ liệu công chứng viên"**.  
- Nếu có lỗi tải dữ liệu, hiển thị: **"Không tải được danh sách, vui lòng thử lại"**.  

### Menu
| Tên                       | Loại             | Mô tả                                                              |
|:--------------------------|:-----------------|:-------------------------------------------------------------------|
| Quản lý công chứng viên   | Dropdown Section | Chỉ hiển thị khi người dùng có quyền quản lý công chứng viên       |
| Danh sách công chứng viên | Button           | Chỉ hiển thị khi người dùng có quyền xem danh sách công chứng viên |

### Chức năng

<div style="overflow-x:auto">

| Tên                           | Loại     | Mô tả                                                                                                           |
|:------------------------------|:---------|:----------------------------------------------------------------------------------------------------------------|
| Ô tìm kiếm                    | Input    | Chỉ hiển thị khi người dùng có quyền tìm kiếm công chứng viên, nhập tên công chứng viên hoặc số thẻ để tìm kiếm |
| Biểu tượng tìm kiếm           | Button   | Bấm vào thực hiện tìm kiếm theo thông tin đã nhập/chọn (UC_CCV_Search)                                          |
| Ô điền tên công chứng viên    | input    |                                                                                                                 |
| Ô điền số thẻ                 | input    |                                                                                                                 |
| Ô điền tên tổ chức công chứng | input    |                                                                                                                 |
| Ô chọn trạng thái             | dropdown | Chọn trạng thái từ danh sách trạng thái hoạt động của công chứng viên (Giống với SCR_CCV_Create)                |
| Nút xuất danh sách            | Button   | Hiển thị nếu có quyền, click sẽ xuất danh sách theo điều kiện đã tìm (UC_CCV_Export)                            |
| Nút thêm mới                  | Button   | Hiển thị nếu có quyền, click sẽ mở popup thêm công chứng viên (UC_CCV_Create)                                   |
| Biểu tượng xem chi tiết       | Button   | Hiển thị nếu có quyền, click sẽ mở popup xem chi tiết công chứng viên (UC_CCV_Detail)                           |
| Biểu tượng sửa                | Button   | Hiển thị nếu có quyền, click sẽ mở popup chỉnh sửa công chứng viên (UC_CCV_Update)                              |
| Biểu tượng xóa                | Button   | Hiển thị nếu có quyền, click sẽ mở popup xác nhận xóa công chứng viên (UC_CCV_Delete)                           |
| Biểu tượng lịch sử cập nhật   | Button   | Hiển thị nếu có quyền, click sẽ mở popup xem lịch sử cập nhật thông tin công chứng viên (UC_CCV_History)        |

</div>
