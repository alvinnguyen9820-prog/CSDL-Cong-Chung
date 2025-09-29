# Màn hình: Xem lịch sử cập nhật thông tin đăng ký chữ ký số
Popup hiển thị danh sách lịch sử cập nhật của một hồ sơ đăng ký chữ ký số.

## Điều kiện tiên quyết
- Người dùng đã đăng nhập hệ thống.  
- Người dùng có quyền xem lịch sử cập nhật thông tin đăng ký chữ ký số.  

## Nguyên mẫu
[https://www.figma.com/design/STv6BI8XR469xhObHjgCHs/Test-Puml?node-id=32-39612&t=qhcu7sCD1S2A6kb5-1]

## Thành phần

### Bảng lịch sử cập nhật (ENT_LichSuCapNhatChuKySo)

<div style="overflow-x:auto">

| Trường thông tin   | Control | Field                 | Bắt buộc (Y/N) | Mô tả                            |
|:-------------------|:--------|:----------------------|:---------------|:---------------------------------|
| Thời gian          | text    | updatedAt             | Y              | Thời điểm thực hiện cập nhật     |
| Người thực hiện    | text    | updatedBy             | Y              | Người thực hiện thay đổi         |
| Thao tác           | -       | -                     | -              | Cập nhật                         |
| Thông tin thay đổi | text    | truongThongtinCapNhat | Y              | Tên trường dữ liệu được thay đổi |
| Giá trị cũ         | text    | giaTriCu              | N              | Giá trị trước khi thay đổi       |
| Giá trị mới        | text    | giaTriMoi             | N              | Giá trị sau khi thay đổi         |

</div>

### Thông báo hệ thống
- Không có dữ liệu: hiển thị **"Không tìm thấy lịch sử cập nhật thông tin đăng ký chữ ký số"**.  
- Lỗi hệ thống: hiển thị **"Không tải được thông tin, vui lòng thử lại"**.  

### Chức năng

<div style="overflow-x:auto">

| Tên        | Loại   | Mô tả                                                   |
| :--------- | :----- | :------------------------------------------------------ |
| Đóng       | Button | Đóng popup, quay lại màn hình danh sách **SCR_CKS_List** |
| Quay lại   | Icon   | Chức năng tương tự nút Đóng                             |

</div>

## Ngoại lệ
- Không có dữ liệu → Hiển thị thông báo “Không tìm thấy lịch sử cập nhật thông tin đăng ký chữ ký số”.  
- Lỗi hệ thống → Hiển thị thông báo lỗi, không tải dữ liệu.  

## Liên kết
- Activity Diagram: [AD_CKS_History.puml]  
- Form/Screen: [SCR_CKS_List.md], [SCR_CKS_History.md]  
- Entity liên quan: ENT_LichSuCapNhatChuKySo  
