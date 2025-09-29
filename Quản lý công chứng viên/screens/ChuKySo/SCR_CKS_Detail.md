# Màn hình: Chi tiết thông tin đăng ký chữ ký số
Popup hiển thị chi tiết hồ sơ đăng ký chữ ký số, trạng thái phê duyệt và thông tin liên quan.

## Điều kiện tiên quyết
- Người dùng đã đăng nhập hệ thống.
- Người dùng có quyền xem chi tiết thông tin đăng ký chữ ký số.

## Nguyên mẫu
[https://www.figma.com/design/STv6BI8XR469xhObHjgCHs/Test-Puml?node-id=32-38211&t=qhcu7sCD1S2A6kb5-1]
[https://www.figma.com/design/STv6BI8XR469xhObHjgCHs/Test-Puml?node-id=46-21585&t=qhcu7sCD1S2A6kb5-1]

## Thành phần

### Thông tin chi tiết (ENT_ChuKySo)

<div style="overflow-x:auto">

| Trường thông tin | Control   | Field            | Max length | Bắt buộc (Y/N) | Cho phép sửa (Y/N) | Mô tả                                    |
|:-----------------|:----------|:-----------------|:-----------|:---------------|:-------------------|:-----------------------------------------|
| Công chứng viên  | text      | tenCongChungVien | 255        | Y              | N                  | Tên công chứng viên liên kết             |
| Loại chữ ký số   | text      | loaiChuKy        | 100        | Y              | N                  | Thông tin loại chữ ký số                 |
| Nhà cung cấp     | text      | nhaCungCap       | 255        | Y              | N                  | Nhà cung cấp chứng thư số                |
| Số serial        | text      | soSerial         | 100        | Y              | N                  | Mã định danh chứng thư số                |
| Ngày hiệu lực    | datetime  | ngayHieuLuc      | -          | Y              | N                  | Ngày bắt đầu hiệu lực                    |
| Ngày hết hạn     | datetime  | ngayHetHan       | -          | Y              | N                  | Ngày hết hạn                             |
| File đính kèm    | file/link | fileDinhKem      | -          | N              | N                  | File chứng thư số đính kèm               |
| Trạng thái       | text      | trangThai        | 50         | Y              | N                  | Mới tạo / Chờ duyệt / Đã duyệt / Từ chối |
| Người duyệt      | text      | nguoiDuyet       | 255        | N              | N                  | Tên người phê duyệt                      |
| Thời gian duyệt  | datetime  | thoiGianDuyet    | -          | N              | N                  | Thời gian phê duyệt                      |

</div>

## Chức năng

<div style="overflow-x:auto">

| Tên         | Loại   | Mô tả                                                                                                                          |
|:------------|:-------|:-------------------------------------------------------------------------------------------------------------------------------|
| Đóng        | Button | Đóng popup, quay lại màn hình danh sách (**SCR_CKS_List**)                                                                     |
| Duyệt       | Button | Chỉ hiển thị nếu người dùng có quyền phê duyệt → Cập nhật trạng thái = "Đã duyệt" và lưu lịch sử                               |
| Từ chối     | Button | Chỉ hiển thị nếu người dùng có quyền phê duyệt → Cập nhật trạng thái = "Từ chối" và lưu lịch sử                                |
| Chỉnh sửa   | Button | Chỉ hiển thị nếu người dùng có quyền chỉnh sửa → mở popup chỉnh sửa, Chỉ hiển thị khi trạng thái là "Mới tạo" hoặc "Chờ duyệt" |
| Trình duyệt | Button | Chỉ hiển thị nếu người dùng có quyền chỉnh sửa và trạng thái là "Mới tạo" → Cập nhật trạng thái = "Chờ duyệt" và lưu lịch sử   |

</div>

## Thông báo hệ thống
- Không có dữ liệu: Hiển thị **"Không tìm thấy thông tin đăng ký chữ ký số"**.  
- Lỗi hệ thống: Hiển thị **"Không tải được thông tin, vui lòng thử lại"**.  
- Duyệt thành công: **"Đăng ký chữ ký số đã được duyệt"**.  
- Từ chối thành công: **"Đăng ký chữ ký số đã bị từ chối"**.  

## Ngoại lệ
- Người dùng không có quyền phê duyệt: Ẩn nút **Duyệt** và **Từ chối**.  
- Lỗi hệ thống khi cập nhật trạng thái: Hiển thị thông báo lỗi chung.  

## Liên kết
- Activity Diagram: [AD_CKS_Detail.puml]  
- Form/Screen: [SCR_CKS_Detail.md]  
- Entity liên quan: ENT_ChuKySo  
