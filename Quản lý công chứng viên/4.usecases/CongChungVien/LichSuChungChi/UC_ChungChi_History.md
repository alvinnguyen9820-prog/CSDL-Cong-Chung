# Use Case: Xem lịch sử cập nhật thông tin chứng chỉ hành nghề

## User Story
- Là Chuyên viên STP, Lãnh đạo STP, Lãnh đạo phòng HCBTTP tại STP, Lãnh đạo Bộ Tư pháp, Lãnh đạo Cục BTTP, Chuyên viên Cục BTTP, tôi muốn xem được lịch sử cập nhật chứng chỉ hành nghề của công chứng viên để có thể truy vết và xem các thay đổi của thông tin

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
- Người dùng có thể quay lại trang chi tiết thông tin công chứng viên
- Nếu không tìm thấy dữ liệu, hệ thống hiển thị thông báo "Không tìm thấy lịch sử cập nhật chứng chỉ hành nghề".
- Nếu có lỗi hệ thống, hiển thị thông báo lỗi.  

## Tác nhân chính
- Chuyên viên STP, Lãnh đạo STP, Lãnh đạo phòng HCBTTP tại STP, Lãnh đạo Bộ Tư pháp, Lãnh đạo Cục BTTP, Chuyên viên Cục BTTP

## Tiền điều kiện
- Người dùng đăng nhập hệ thống.
- Người dùng có quyền xem lịch sử cập nhật thông tin chứng chỉ hành nghề

## Luồng chính
1. Người dùng truy cập thành công màn hình chi tiết thông tin công chứng viên (**SCR_CCV_Detail**)
2. Người dùng truy cập trang lịch sử cập nhật thông tin chứng chỉ hành nghề băng cách click vào biểu tượng xem lịch sử cập nhật chứng chỉ hành nghề
3. Hệ thống truy vấn thông tin lịch sử cập nhật chứng chỉ hành nghề theo ID chứng chỉ (**ENT_LichSuChungChi**).
4. Hệ thống hiển thị popup lịch sử cập nhật chứng chỉ hành nghề (**SCR_ChungChi_History**) bao gồm các thông tin
    - STT
    - ID bản ghi
    - Thời gian
    - Người thực hiện
    - Thao tác
    - Trường thay đổi
    - Giá trị cũ
    - Giá trị mới
5. Hệ thống hiển thị các nút chức năng.
- Biểu tượng quay lại và nút đóng => Bấm vào đóng popup, chuyển về màn hình chi tiết công chứng viên (**SCR_CCV_Detail**)
6. Kết thúc Use case

## Luồng phụ / ngoại lệ
- Không có dữ liệu: Hiển thị "Không tìm thấy lịch sử cập nhật chứng chỉ hành nghề".
- Lỗi hệ thống: Hiển thị thông báo "Không tải được thông tin, vui lòng thử lại".

## Hậu điều kiện
- Nếu thành công: Người dùng xem được lịch sử cập nhật chứng chỉ hành nghề.
- Nếu thất bại: Không hiển thị dữ liệu, hoặc hiển thị thông báo lỗi.

## Liên kết
- Activity Diagram: [AD_ChungChi_History.puml]
- Form/Screen: [SCR_ChungChi_History.md]
- Entity liên quan: ENT_LichSuChungChi
