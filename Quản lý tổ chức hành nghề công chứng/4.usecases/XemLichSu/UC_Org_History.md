# Use Case: Xem lịch sử cập nhật tổ chức công chứng

## User Story
- Là Chuyên viên STP, Lãnh đạo STP, Lãnh đạo phòng HCBTTP tại STP, tôi muốn xem được lịch sử cập nhật thông tin tổ chức công chứng thuộc Sở Tư pháp của mình để có thể truy vết và xem các thay đổi của thông tin
- Là Lãnh đạo Bộ Tư pháp, Lãnh đạo Cục BTTP, Chuyên viên Cục BTTP, tôi muốn xem được lịch sử cập nhật thông tin của toàn bộ tổ chức công chứng để có thể truy vết và xem các thay đổi của thông tin

## Acceptance criteria
- Hệ thống hiển thị lịch sử cập nhật dưới dạng danh sách
- Các trường thông tin trong danh sách bao gồm: 
    - Thời gian
    - Người thực hiện
    - Thao tác
    - Trường thay đổi
    - Giá trị cũ
    - Giá trị mới
- Người dùng có thể quay lại trang danh sách tổ chức công chứng
- Nếu không tìm thấy dữ liệu, hệ thống hiển thị thông báo "Không tìm thấy lịch sử cập nhật tổ chức công chứng".
- Nếu có lỗi hệ thống, hiển thị thông báo lỗi.  

## Tác nhân chính
- Chuyên viên STP, Lãnh đạo STP, Lãnh đạo phòng HCBTTP tại STP, Lãnh đạo Bộ Tư pháp, Lãnh đạo Cục BTTP, Chuyên viên Cục BTTP

## Tiền điều kiện
- Người dùng đăng nhập hệ thống.
- Người dùng có quyền xem lịch sử cập nhật tổ chức công chứng

## Luồng chính
1. Người dùng truy cập thành công màn hình danh sách tổ chức công chứng (**SCR_Org_List**)
2. Người dùng truy cập trang lịch sử cập nhật tổ chức công chứng băng cách click vào biểu tượng xem lịch sử cập nhật 1 tổ chức công chứng trong danh sách
3. Hệ thống truy vấn lịch sử cập nhật tổ chức công chứng theo ID (**ENT_LichSuCapNhatTCHNCC**).
4. Hệ thống hiển thị popup lịch sử cập nhật tổ chức công chứng (**SCR_Org_History**) bao gồm các thông tin
    - Thời gian
    - Người thực hiện
    - Thao tác
    - Trường thay đổi
    - Giá trị cũ
    - Giá trị mới
5. Hệ thống hiển thị các nút chức năng.
- Biểu tượng quay lại và nút đóng => Bấm vào đóng popup, chuyển về màn hình danh sách tổ chức công chứng (**SCR_Org_List**)
6. Kết thúc Use case

## Luồng phụ / ngoại lệ
- Không có dữ liệu: Hiển thị "Không tìm thấy lịch sử cập nhật tổ chức công chứng".
- Lỗi hệ thống: Hiển thị thông báo "Không tải được thông tin, vui lòng thử lại".

## Hậu điều kiện
- Nếu thành công: Người dùng xem được lịch sử cập nhật tổ chức công chứng.
- Nếu thất bại: Không hiển thị dữ liệu, hoặc hiển thị thông báo lỗi.

## Liên kết
- Activity Diagram: [AD_Org_History.puml]
- Form/Screen: [SCR_Org_History.md]
- Entity liên quan: ENT_LichSuCapNhatTCHNCC
