# Use Case: Xem danh sách Thông tin đăng ký chữ ký số của công chứng viên

## User Story
- Là **Công chứng viên / Nhân viên TCHNCC, Chuyên viên STP, Lãnh đạo STP, Lãnh đạo phòng HCBTTP tại STP, Lãnh đạo Bộ Tư pháp, Lãnh đạo Cục BTTP, Chuyên viên Cục BTTP**, tôi muốn tìm kiếm theo nhiều tiêu chí, để có thể nhanh chóng tra cứu ra Thông tin đăng ký chữ ký số của công chứng viên

## Acceptance criteria
- Hệ thống hiển thị form tìm kiếm với các tiêu chí
    - Ô điền thông tin tìm kiếm theo "Họ và tên công chứng viên", "Số thẻ CCV", "Mã chứng thư"
    - Bộ lọc:
        - Trạng thái
        - Nhà cung cấp dịch vụ
        Đối với người dùng có thể xem toàn bộ danh sách
        - Tỉnh/Thành phố của tổ chức hành nghề công chứng
        - Tên tổ chức hành nghề công chứng
- Hiển thị bảng danh sách Thông tin đăng ký chữ ký số với các cột tông tin cơ bản (STT Tên tổ chức công chứng, Mã chứng thư, Nhà cung cấp dịch vụ, Trạng thái, Loại) theo tiêu chí đã tìm kiếm.
- Nếu số lượng bản ghi vượt quá giới hạn hiển thị, hệ thống phải cung cấp phân trang (10 bản ghi 1 trang).
- Nếu có lỗi tải dữ liệu, hiển thị thông báo lỗi.
- Nếu không tìm thấy dữ liệu theo tiêu chí tìm kiếm, thông báo "Không tìm thấy dữ liệu Thông tin đăng ký chữ ký số"
- Danh sách Thông tin đăng ký chữ ký số hiển thị theo thứ tự thời gian cập nhật từ mới tới cũ nhất.

## Tác nhân chính
- Công chứng viên / Nhân viên TCHNCC, Chuyên viên STP, Lãnh đạo STP, Lãnh đạo phòng HCBTTP tại STP, Lãnh đạo Bộ Tư pháp, Lãnh đạo Cục BTTP, Chuyên viên Cục BTTP

## Tiền điều kiện
- Người dùng đăng nhập hệ thống.
- Người dùng có quyền tìm kiếm thông tin Thông tin đăng ký chữ ký số

## Luồng chính
1. Người dùng truy cập màn hình danh sách Thông tin đăng ký chữ ký số (**UC_CKS_List**).
2. Người dùng điền thông tin tìm kiếm (theo "Họ và tên công chứng viên", "Số thẻ CCV", "Mã chứng thư")
3. Người dùng lọc tiêu chí tìm kiếm
4. Người dùng bấm nút "Tìm kiếm"
5. Hệ thống truy vấn thông tin Thông tin đăng ký chữ ký số
    - Truy vấn họ và tên công chứng viên gần giống với kết quả đã điền
    - Truy vấn chính xác số thẻ công chứng viên
    - Truy vấn chính xác mã chứng thư đã điền
    - Truy vấn chính xác theo trạng thái đăng ký đã chọn
    - Truy vấn chính xác theo nhà cung cấp dịch vụ đã chọn
    - Truy vấn chính xác theo tỉnh thành của tổ chức công chứng đã chọn
    - Truy vấn chính xác theo tên tổ chức công chứng đã chọn
6. Hệ thống hiển thị danh sách thông tin đăng ký chữ ký số theo kết quả đã truy vấn được
7. Hệ thống hiển thị danh sách Thông tin đăng ký chữ ký số theo thứ tự thời gian cập nhật từ mới tới cũ nhất
8. Nếu số lượng bản ghi lớn hơn 10, hệ thống thực hiện phân trang, 10 bản ghi mỗi trang
9. Nếu người dùng bấm nút "Xóa điều kiện", hệ thống xóa các tiêu chí vừa chọn, các thông tin tìm kiếm đã điền
10. Kết thúc.

## Luồng phụ / ngoại lệ
- Nếu có lỗi tìm kiếm: hiển thị thông báo "Không tải được danh sách, vui lòng thử lại".
- Nếu không tìm thấy dữ liệu: hiển thị "Không có dữ liệu Thông tin đăng ký chữ ký số".

## Hậu điều kiện
- Nếu thành công: Người dùng tìm kiếm thành công thông tin Thông tin đăng ký chữ ký số.
- Nếu thất bại: Không hiển thị dữ liệu, hoặc hiển thị thông báo lỗi.

## Liên kết
- Activity Diagram: [AD_CKS_Search.puml]
- Form/Screen: [SCR_CKS_Search.md]
- Entity liên quan: ENT_CongChungVien, ENT_ToChucCongChung, ENT_ChuKySo
