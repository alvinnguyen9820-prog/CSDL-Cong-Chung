# Use Case: Xem lịch sử cập nhật công chứng viên

## User Story
- Là Chuyên viên STP, Lãnh đạo STP, Lãnh đạo phòng HCBTTP tại STP, Lãnh đạo Bộ Tư pháp, Lãnh đạo Cục BTTP, Chuyên viên Cục BTTP, tôi muốn xem được lịch sử cập nhật công chứng viên để có thể truy vết và xem các thay đổi của thông tin

## Acceptance criteria
- Hệ thống hiển thị lịch sử cập nhật dưới dạng danh sách
- Các trường thông tin trong danh sách bao gồm: 
    - STT
    - ID bản ghi
    - Thời gian
    - Người thực hiện
    - Thao tác
    - Trường thay đổi
    - Giá trị cũ
    - Giá trị mới
- Người dùng có thể quay lại trang danh sách công chứng viên
- Nếu không tìm thấy dữ liệu, hệ thống hiển thị thông báo "Không tìm thấy lịch sử cập nhật công chứng viên".
- Nếu có lỗi hệ thống, hiển thị thông báo lỗi.  

## Tác nhân chính
- Chuyên viên STP, Lãnh đạo STP, Lãnh đạo phòng HCBTTP tại STP, Lãnh đạo Bộ Tư pháp, Lãnh đạo Cục BTTP, Chuyên viên Cục BTTP

## Tiền điều kiện
- Người dùng đăng nhập hệ thống.
- Người dùng có quyền xem lịch sử cập nhật công chứng viên

## Luồng chính
1. Người dùng truy cập thành công màn hình danh sách công chứng viên (**SCR_CCV_List**)
2. Người dùng truy cập trang lịch sử cập nhật công chứng viên băng cách click vào biểu tượng xem lịch sử cập nhật 1 công chứng viên trong danh sách
3. Hệ thống truy vấn lịch sử cập nhật công chứng viên theo ID (**ENT_LichSuCapNhatCCV**).
4. Hệ thống hiển thị popup lịch sử cập nhật công chứng viên (**SCR_CCV_History**) bao gồm các thông tin
    - STT
    - ID bản ghi
    - Thời gian
    - Người thực hiện
    - Thao tác
    - Trường thay đổi
    - Giá trị cũ
    - Giá trị mới
5. Hệ thống hiển thị các nút chức năng.
- Biểu tượng quay lại và nút đóng => Bấm vào đóng popup, chuyển về màn hình danh sách công chứng viên (**SCR_CCV_List**)
6. Kết thúc Use case

## Luồng phụ / ngoại lệ
- Không có dữ liệu: Hiển thị "Không tìm thấy lịch sử cập nhật công chứng viên".
- Lỗi hệ thống: Hiển thị thông báo "Không tải được thông tin, vui lòng thử lại".

## Hậu điều kiện
- Nếu thành công: Người dùng xem được lịch sử cập nhật công chứng viên.
- Nếu thất bại: Không hiển thị dữ liệu, hoặc hiển thị thông báo lỗi.

## Liên kết
- Activity Diagram: [AD_CCV_History.puml]
- Form/Screen: [SCR_CCV_History.md]
- Entity liên quan: ENT_LichSuCapNhatCCV
