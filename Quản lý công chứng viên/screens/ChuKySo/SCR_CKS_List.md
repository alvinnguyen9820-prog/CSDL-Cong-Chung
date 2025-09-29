# Màn hình: Danh sách đăng ký chữ ký số
Nơi tập trung để xem và quản lý các hồ sơ đăng ký chữ ký số.

## Điều kiện tiên quyết
- Người dùng đã đăng nhập hệ thống.
- Người dùng có quyền truy cập chức năng đăng ký chữ ký số.

## Nguyên mẫu
[Link Figma - cập nhật sau]

## Thành phần

### Bảng chính (ENT_ChuKySo, ENT_CongChungVien, ENT_ToChucCongChung)

<div style="overflow-x:auto">

| Trường thông tin         | Control | Field              | Max length | Bắt buộc (Y/N) | Cho phép sửa (Y/N) | Mô tả                                                                     |
|:-------------------------|:--------|:-------------------|:-----------|:---------------|:-------------------|:--------------------------------------------------------------------------|
| Tên tổ chức công chứng   | text    | tenToChucCongChung | 255        | Y              | N                  | Chỉ hiển thị trong trường hợp người dùng là thành viên tổ chức công chứng |
| Công chứng viên (nếu có) | text    | tenCongChungVien   | 255        | N              | N                  | Tên công chứng viên liên kết với đăng ký chữ ký số                        |
| Số serial                | text    | soSerial           | 100        | Y              | N                  | Mã định danh chứng thư số                                                 |
| Nhà cung cấp dịch vụ     | text    | nhaCungCap         | 255        | Y              | N                  | Nhà cung cấp chữ ký số                                                    |
| Loại chữ ký số           | text    | loaiChuKySo        | 50         | Y              | N                  | Cá nhân / Tổ chức                                                         |
| Trạng thái               | text    | trangThai          | 50         | Y              | N                  | Mới tạo / Chờ duyệt / Đã duyệt / Từ chối                                  |
| Chức năng                | icon    | -                  | -          | -              | N                  | Xem chi tiết, Chỉnh sửa, Xóa, xem lịch sử (tuỳ quyền, tuỳ trạng thái)     |

</div>

### Khác
- Phân trang 10 bản ghi/trang.  
- Sắp xếp theo thứ tự thời gian cập nhật từ mới tới cũ nhất.  
- Nếu không có dữ liệu: hiển thị **"Không có dữ liệu đăng ký chữ ký số"**.  
- Nếu có lỗi tải dữ liệu: hiển thị **"Không tải được danh sách, vui lòng thử lại"**.  

### Chức năng

<div style="overflow-x:auto">

| Tên             | Loại    | Mô tả                                                                 |
| :-------------- | :------ | :-------------------------------------------------------------------- |
| Tìm kiếm        | Input   | Nhập tiêu chí để tra cứu hồ sơ đăng ký chữ ký số                       |
| Reset           | Button  | Xóa thông tin tìm kiếm, trả form về trạng thái mặc định                |
| Tìm kiếm        | Button  | Thực hiện tra cứu theo tiêu chí đã nhập                                |
| Export          | Button  | Xuất danh sách đăng ký chữ ký số theo điều kiện tìm kiếm (**UC_CKS_Export**) |
| Xem chi tiết    | Button  | Mở popup chi tiết thông tin đăng ký chữ ký số (**UC_CKS_Detail**)      |
| Thêm mới        | Button  | Mở popup thêm mới đăng ký chữ ký số (**UC_CKS_Create**)                 |
| Sửa             | Button  | Mở popup chỉnh sửa đăng ký chữ ký số (**UC_CKS_Update**) (tuỳ quyền)   |
| Xóa             | Button  | Mở popup xác nhận xoá (**UC_CKS_Delete**) (tuỳ quyền, tuỳ trạng thái) |
| Xem lịch sử     | Button  | Mở popup lịch sử thay đổi (**UC_CKS_History**)                        |

</div>

## Thông báo hệ thống
- **Không có dữ liệu:** "Không có dữ liệu đăng ký chữ ký số".  
- **Lỗi tải dữ liệu:** "Không tải được danh sách, vui lòng thử lại".  
- **Không có quyền truy cập:** "Không có quyền truy cập" và ẩn menu **Đăng ký chữ ký số**.  

## Liên kết
- Activity Diagram: [AD_Sign_List.puml]  
- Form/Screen: [SCR_Sign_List.md]  
- Entity liên quan: ENT_ChuKySo, ENT_CongChungVien, ENT_ToChucCongChung  
