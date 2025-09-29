# Use Case: tra cứu công chứng viên

## User Story
- Là Chuyên viên STP, Lãnh đạo STP, Lãnh đạo phòng HCBTTP tại STP, Lãnh đạo Bộ Tư pháp, Lãnh đạo Cục BTTP, Chuyên viên Cục BTTP, Nhân viên TCHNCC, Công chứng viên TCHNCC, tôi muốn tra cứu thông tin công chứng viên theo nhiều tiêu chí, để xác minh thông tin và kiểm tra tình trạng hoạt động.

## Acceptance criteria
- Hệ thống hiển thị form tra cứu với các tiêu chí
    - Ô điền thông tin tra cứu theo "Họ và tên", "Số thẻ CCV", "Số chứng chỉ hành nghề"
    - Bộ lọc:
        - Trạng thái: Đang hành nghề, 
        - Tỉnh/Thành phố của tổ chức hành nghề công chứng
        - Tên tổ chức hành nghề công chứng
- Hiển thị bảng danh sách công chứng viên với các cột thông tin cơ bản (STT, Họ và tên, số thẻ, số chứng chỉ hành nghề, tổ chức công chứng đang hành nghề, trạng thái hoạt động, địa chỉ tổ chức công chứng) theo tiêu chí đã tra cứu.
- Nếu số lượng bản ghi vượt quá giới hạn hiển thị, hệ thống phải cung cấp phân trang (10 bản ghi 1 trang).
- Nếu có lỗi tải dữ liệu, hiển thị thông báo lỗi.
- Nếu không tìm thấy dữ liệu theo tiêu chí tra cứu, thông báo "Không tìm thấy dữ liệu"
- Danh sách công chứng viên hiển thị theo thứ tự thời gian cập nhật từ mới tới cũ nhất.

## Tác nhân chính
- Chuyên viên STP, Lãnh đạo STP, Lãnh đạo phòng HCBTTP tại STP, Lãnh đạo Bộ Tư pháp, Lãnh đạo Cục BTTP, Chuyên viên Cục BTTP, Nhân viên TCHNCC, Công chứng viên TCHNCC

## Tiền điều kiện
- Người dùng đăng nhập hệ thống.
- Người dùng có quyền tra cứu thông tin công chứng viên và chứng chỉ hành nghề

## Luồng chính
1. Người dùng truy cập màn hình tra cứu (**UC_CCV_Lookup**).
2. Người dùng điền thông tin tra cứu (Theo họ và tên, số thẻ CCV hoặc Số chứng chỉ hành nghề)
3. Người dùng lọc tiêu chí tra cứu: Trạng thái hành nghề, tỉnh thành phố của TCHNCC đang làm việc, Tên tổ chức công chứng
4. Người dùng bấm nút "tra cứu"
5. Hệ thống truy vấn thông tin công chứng viên
    - Truy vấn họ và tên công chứng viên gần giống với kết quả đã điền
    - Truy vấn chính xác Số chứng chỉ hành nghề của công chứng viên
    - Truy vấn chính xác số thẻ công chứng viên
    - Truy vấn chính xác theo trạng thái đã chọn
    - Truy vấn chính xác theo tỉnh thành của tổ chức công chứng đã chọn
    - Truy vấn chính xác theo tên tổ chức công chứng đã chọn
6. Hệ thống hiển thị danh sách công chứng viên theo kết quả đã truy vấn được bao gồm các thông tin: (STT, Họ và tên, số thẻ, số chứng chỉ hành nghề, tổ chức công chứng đang hành nghề, trạng thái hoạt động, địa chỉ tổ chức công chứng)
7. Hệ thống hiển thị danh sách công chứng viên theo thứ tự thời gian cập nhật từ mới tới cũ nhất
8. Người dùng bấm vào xem chi tiết chứng chỉ hành nghề, hệ thống hiển thị popup chi tiết chứng chỉ hành nghề với các thông tin: 
    - Số chứng chỉ
    - Ngày cấp
    - Nơi cấp
    - Ngày hiệu lực
    - Ngày hết hạn
    - Đơn vị cấp
    - Trạng thái
8. Nếu số lượng bản ghi lớn hơn 10, hệ thống thực hiện phân trang, 10 bản ghi mỗi trang
9. Nếu người dùng bấm nút "Xóa điều kiện", hệ thống xóa các tiêu chí vừa chọn, các thông tin tra cứu đã điền
10. Kết thúc.

## Luồng phụ / ngoại lệ
- Nếu có lỗi tra cứu: hiển thị thông báo "Không tải được danh sách, vui lòng thử lại".
- Nếu không tìm thấy dữ liệu: hiển thị "Không có dữ liệu công chứng viên".
- Người dùng bấm vào nút đóng lại hoặc biểu tượng đóng popup thông tin chi tiết chứng chỉ hành nghề, hệ thống đóng popup, hiển thị màn hình tra cứu

## Hậu điều kiện
- Nếu thành công: Người dùng tra cứu thành công thông tin công chứng viên.
- Nếu thất bại: Không hiển thị dữ liệu, hoặc hiển thị thông báo lỗi.

## Liên kết
- Activity Diagram: [AD_CCV_Lookup.puml]
- Form/Screen: [SCR_CCV_Lookup.md]
- Entity liên quan: ENT_CongChungVien, ENT_ToChucCongChung
