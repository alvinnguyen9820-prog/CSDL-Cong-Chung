# Use Case: Tìm kiếm công chứng viên

## User Story
- Là Chuyên viên STP, Lãnh đạo STP, Lãnh đạo phòng HCBTTP tại STP, Lãnh đạo Bộ Tư pháp, Lãnh đạo Cục BTTP, Chuyên viên Cục BTTP, tôi muốn tìm kiếm theo nhiều tiêu chí, để có thể nhanh chóng tìm ra thông tin công chứng viên trong danh sách quản ly

## Acceptance criteria
- Hệ thống hiển thị form tìm kiếm với các tiêu chí
    - Ô điền thông tin tìm kiếm theo "Họ và tên", "Số thẻ CCV"
    - Bộ lọc:
        - Trạng thái: Đang hành nghề, 
        - Tỉnh/Thành phố của tổ chức hành nghề công chứng
        - Tên tổ chức hành nghề công chứng
- Hiển thị bảng danh sách công chứng viên với các cột tông tin cơ bản (STT, Họ và tên, số thẻ, tổ chức công chứng đang hành nghề, trạng thái hoạt động, địa chỉ tổ chức công chứng) theo tiêu chí đã tìm kiếm.
- Nếu số lượng bản ghi vượt quá giới hạn hiển thị, hệ thống phải cung cấp phân trang (10 bản ghi 1 trang).
- Nếu có lỗi tải dữ liệu, hiển thị thông báo lỗi.
- Nếu không tìm thấy dữ liệu theo tiêu chí tìm kiếm, thông báo "Không tìm thấy dữ liệu công chứng viên"
- Danh sách công chứng viên hiển thị theo thứ tự thời gian cập nhật từ mới tới cũ nhất.

## Tác nhân chính
- Chuyên viên STP, Lãnh đạo STP, Lãnh đạo phòng HCBTTP tại STP, Lãnh đạo Bộ Tư pháp, Lãnh đạo Cục BTTP, Chuyên viên Cục BTTP

## Tiền điều kiện
- Người dùng đăng nhập hệ thống.
- Người dùng có quyền tìm kiếm thông tin công chứng viên

## Luồng chính
1. Người dùng truy cập màn hình danh sách công chứng viên (**UC_CCV_List**).
2. Người dùng điền thông tin tìm kiếm (theo họ và tên hoặc số thẻ CCV)
3. Người dùng lọc tiêu chí tìm kiếm
4. Người dùng bấm nút "Tìm kiếm"
5. Hệ thống truy vấn thông tin công chứng viên
    - Truy vấn họ và tên công chứng viên gần giống với kết quả đã điền/Trong tên có thông tin đã điền
    - Truy vấn chính xác số thẻ công chứng viên
    - Truy vấn chính xác theo trạng thái đã chọn
    - Truy vấn chính xác theo tỉnh thành của tổ chức công chứng đã chọn
    - Truy vấn chính xác theo tên tổ chức công chứng đã chọn
6. Hệ thống hiển thị danh sách công chứng theo kết quả đã truy vấn được
7. Hệ thống hiển thị danh sách công chứng viên theo thứ tự thời gian cập nhật từ mới tới cũ nhất
8. Nếu số lượng bản ghi lớn hơn 10, hệ thống thực hiện phân trang, 10 bản ghi mỗi trang
9. Nếu người dùng bấm nút "Xóa điều kiện", hệ thống xóa các tiêu chí vừa chọn, các thông tin tìm kiếm đã điền
10. Kết thúc.

## Luồng phụ / ngoại lệ
- Nếu có lỗi tìm kiếm: hiển thị thông báo "Không tải được danh sách, vui lòng thử lại".
- Nếu không tìm thấy dữ liệu: hiển thị "Không có dữ liệu công chứng viên".

## Hậu điều kiện
- Nếu thành công: Người dùng tìm kiếm thành công thông tin công chứng viên.
- Nếu thất bại: Không hiển thị dữ liệu, hoặc hiển thị thông báo lỗi.

## Liên kết
- Activity Diagram: [AD_CCV_Search.puml]
- Form/Screen: [SCR_CCV_List.md]
- Entity liên quan: ENT_CongChungVien, ENT_ToChucCongChung
