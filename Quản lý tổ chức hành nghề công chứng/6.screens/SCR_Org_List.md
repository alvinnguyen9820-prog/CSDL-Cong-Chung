# Màn hình: Danh sách tổ chức công chứng
Nơi tập trung để xem và quản lý tổ chức công chứng trên hệ thống.

## Điều kiện tiên quyết
- Người dùng đã đăng nhập và có quyền xem danh sách tổ chức công chứng.

## Nguyên mẫu
[https://www.figma.com/design/STv6BI8XR469xhObHjgCHs/Test-Puml?node-id=61-26621&t=D6KMt6aiRNAU7m7V-1]

## Thành phần

### Bảng chính

<div style="overflow-x:auto">

| Trường thông tin       | Control | Field              | Max length | Bắt buộc (Y/N) | Giá trị mặc định | Cho phép sửa (Y/N) | Mô tả                                                                             |
|:-----------------------|:--------|:-------------------|:-----------|:---------------|:-----------------|:-------------------|:----------------------------------------------------------------------------------|
| Tên tổ chức công chứng | text    | tenToChucCongChung | -          | -              |                  | -                  | Tên của tổ chức hành nghề công chứng                                              |
| Sở Tư pháp quản lý     | text    | soTuPhap           | -          | -              |                  | -                  | Tên Sở Tư pháp quản lý (Chỉ hiển thị cột này cho người dùng cấp bộ)               |
| Trưởng văn phòng       | number  | hoVaTen            | -          | -              |                  | -                  | Tên công chứng viên lấy theo ID trưởng văn phòng công chứng                       |
| Địa chỉ trụ sở         | text    | diaChi             | -          | -              |                  | -                  | Địa chỉ trụ sở: Địa chỉ - Phường/xã - Tỉnh/Thành phố                                                             |
| Trạng thái hoạt động   | text    | trangThai          | -          | -              |                  | -                  | Hiển thị trạng thái đã lưu
| Chức năng              | icon    | -                  | -          | -              |                  | -                  | Hiển thị danh sách nút: Xem chi tiết, sửa, xóa, xem lịch sử (tùy theo phân quyền) |

</div>

### Khác
- Phân trang 10 bản ghi/trang.  
- Sắp xếp theo thứ tự thời gian cập nhật từ mới tới cũ nhất.  
- Nếu không có dữ liệu, hiển thị: **"Không có dữ liệu tổ chức công chứng"**.  
- Nếu có lỗi tải dữ liệu, hiển thị: **"Không tải được danh sách, vui lòng thử lại"**.  

### Menu
| Tên                        | Loại   | Mô tả                                                                                                                 |
|:---------------------------|:-------|:----------------------------------------------------------------------------------------------------------------------|
| Quản lý tổ chức công chứng | Button | Chỉ hiển thị khi người dùng có quyền xem danh sách tổ chức công chứng, bấm vào mở màn hình quản lý tổ chức công chứng |

### Chức năng

<div style="overflow-x:auto">

| Tên                           | Loại     | Mô tả                                                                                                                                    |
|:------------------------------|:---------|:-----------------------------------------------------------------------------------------------------------------------------------------|
| Ô tìm kiếm                    | Input    | Chỉ hiển thị khi người dùng có quyền tìm kiếm tổ chức công chứng, nhập tên tổ chức công chứng để tìm kiếm                                |
| Biểu tượng tìm kiếm           | Button   | Chỉ hiển thị khi người dùng có quyền tìm kiếm tổ chức công chứng, Bấm vào thực hiện tìm kiếm theo thông tin đã nhập/chọn (UC_Org_Search) |
| Ô điền tên tổ chức công chứng | input    |                                                                                                                                          |
| Ô điền tên trưởng văn phòng   | input    |                                                                                                                                          |
| Ô điền địa chỉ tổ chức        | input    |                                                                                                                                          |
| Ô chọn tên Sở Tư pháp         | dropdown | Chọn từ danh sách Sở Tư pháp                                                                                                             |
| Ô chọn trạng thái             | dropdown | Chọn trạng thái từ danh sách trạng thái hoạt động của tổ chức công chứng (Giống với SCR_Org_Create)                                      |
| Nút xuất danh sách            | Button   | Hiển thị nếu có quyền, click sẽ xuất danh sách theo điều kiện đã tìm (UC_Org_Export)                                                     |
| Nút thêm mới                  | Button   | Hiển thị nếu có quyền, click sẽ mở popup thêm tổ chức công chứng (UC_Org_Create)                                                         |
| Biểu tượng xem chi tiết       | Button   | Hiển thị nếu có quyền, click sẽ mở popup xem chi tiết tổ chức công chứng (UC_Org_Detail)                                                 |
| Biểu tượng sửa                | Button   | Hiển thị nếu có quyền, click sẽ mở popup chỉnh sửa tổ chức công chứng (UC_Org_Update)                                                    |
| Biểu tượng xóa                | Button   | Hiển thị nếu có quyền, click sẽ mở popup xác nhận xóa tổ chức công chứng (UC_Org_Delete)                                                 |
| Biểu tượng lịch sử cập nhật   | Button   | Hiển thị nếu có quyền, click sẽ mở popup xem lịch sử cập nhật thông tin tổ chức công chứng (UC_Org_History)                              |

</div>
