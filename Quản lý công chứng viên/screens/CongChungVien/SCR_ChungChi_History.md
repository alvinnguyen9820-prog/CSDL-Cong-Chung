# Màn hình: Lịch sử cập nhật chứng chỉ hành nghề của công chứng viên
Popup hiển thị lịch sử cập nhật thông tin chứng chỉ hành nghề của công chứng viên.

## Điều kiện tiên quyết
- Người dùng đã đăng nhập hệ thống.
- Người dùng có quyền xem lịch sử cập nhật chứng chỉ hành nghề.

## Nguyên mẫu
[https://www.figma.com/design/STv6BI8XR469xhObHjgCHs/Test-Puml?node-id=44-15333&t=qhcu7sCD1S2A6kb5-1]

## Thành phần

### Bảng lịch sử (ENT_LichSuCapNhatChugnChi)

<div style="overflow-x:auto">

| Trường thông tin | Control  | Field                 | Max length | Bắt buộc (Y/N) | Cho phép sửa (Y/N) | Mô tả                      |
|:-----------------|:---------|:----------------------|:-----------|:---------------|:-------------------|:---------------------------|
| Thời gian        | datetime | updatedAt             | -          | -              | -                  | Thời điểm thay đổi         |
| Người thực hiện  | text     | updatedBy             | -          | -              | -                  | Người thực hiện thao tác   |
| Thao tác         | text     | -                     | -          | -              | -                  | Cập nhật                   |
| Trường thay đổi  | text     | truongThongtinCapNhat | -          | -              | -                  | Tên trường bị thay đổi     |
| Giá trị cũ       | text     | giaTriCu              | -          | -              | -                  | Giá trị trước khi thay đổi |
| Giá trị mới      | text     | giaTriMoi             | -          | -              | -                  | Giá trị sau khi thay đổi   |

</div>

### Thông báo hệ thống
- Nếu không có dữ liệu: Hiển thị **"Không tìm thấy lịch sử cập nhật chứng chỉ hành nghề"**.  
- Nếu lỗi hệ thống: Hiển thị **"Không tải được thông tin, vui lòng thử lại"**.  

## Chức năng

<div style="overflow-x:auto">

| Tên              | Loại    | Mô tả                                                |
| :--------------- | :------ | :--------------------------------------------------- |
| Quay lại / Đóng  | Button  | Đóng popup, trở về màn hình chi tiết công chứng viên (**SCR_CCV_Detail**) |

</div>
