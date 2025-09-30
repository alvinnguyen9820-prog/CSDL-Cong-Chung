# Màn hình: Tra cứu tổ chức công chứng
Màn hình tra cứu tổ chức công chứng

## Điều kiện tiên quyết
- Người dùng đã đăng nhập và có quyền tra cứu tổ chức công chứng.

## Nguyên mẫu
[https://www.figma.com/design/STv6BI8XR469xhObHjgCHs/Test-Puml?node-id=61-27996&t=D6KMt6aiRNAU7m7V-1]

## Thành phần

### Bảng kết quả tra cứu

<div style="overflow-x:auto">

| Trường thông tin       | Control | Field              | Max length | Bắt buộc (Y/N) | Giá trị mặc định | Cho phép sửa (Y/N) | Mô tả                                                                             |
|:-----------------------|:--------|:-------------------|:-----------|:---------------|:-----------------|:-------------------|:----------------------------------------------------------------------------------|
| Tên tổ chức công chứng | text    | tenToChucCongChung | 255        | Y              |                  | N                  | Tên của tổ chức hành nghề công chứng                                              |
| Sở Tư pháp quản lý     | text    | soTuPhap           | 255        | Y              |                  | N                  | Tên Sở Tư pháp quản lý (Chỉ hiển thị cột này cho người dùng cấp bộ)               |
| Trưởng văn phòng       | number  | truongVanPhongId   | -          | N              |                  | N                  | ID tổ chức công chứng là trưởng văn phòng công chứng                              |
| Địa chỉ trụ sở         | text    | diaChi             | 500        | Y              |                  | N                  | Địa chỉ trụ sở chính                                                              |
| Trạng thái hoạt động   | text    | trangThai          | -          | Y              |                  | N                  | Trạng thái: Đang hoạt động, Chờ thành lập, Giải thể, … (theo enum)                |
| Chức năng              | icon    | -                  | -          | -              |                  | -                  | Hiển thị danh sách nút: Xem chi tiết, sửa, xóa, xem lịch sử (tùy theo phân quyền) |

</div>

### Khác
- Phân trang 10 bản ghi/trang.  
- Sắp xếp theo thứ tự thời gian cập nhật từ mới tới cũ nhất.  
- Nếu không có dữ liệu, hiển thị: **"Không tìm thấy thông tin tổ chức công chứng"**.  
- Nếu có lỗi tải dữ liệu, hiển thị: **"Không tải được thông tin, vui lòng thử lại"**.  

### Menu
| Tên                        | Loại   | Mô tả                                                           |
|:---------------------------|:-------|:----------------------------------------------------------------|
| Tra cứu tổ chức công chứng | Button | Chỉ hiển thị khi người dùng có quyền tra cứu tổ chức công chứng |

### Chức năng

<div style="overflow-x:auto">

| Tên                           | Loại     | Mô tả                                                                                               |
|:------------------------------|:---------|:----------------------------------------------------------------------------------------------------|
| Ô tìm kiếm                    | Input    | Nhập tên tổ chức công chứng để tìm kiếm                                                            |
| Biểu tượng tìm kiếm           | Button   | Bấm vào thực hiện tra cứu theo thông tin đã nhập/chọn (**UC_Org_Lookup**)                           |
| Ô điền tên tổ chức công chứng | input    |                                                                                                     |
| Ô chọn tỉnh thành phố         | dropdown |                                                                                                     |
| Ô chọn trạng thái             | dropdown | Chọn trạng thái từ danh sách trạng thái hoạt động của tổ chức công chứng (Giống với SCR_Org_Create) |

</div>
