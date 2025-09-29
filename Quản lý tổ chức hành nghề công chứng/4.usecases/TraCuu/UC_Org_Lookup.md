# Use Case: tra cứu tổ chức công chứng

## User Story
- Là Chuyên viên STP, Lãnh đạo STP, Lãnh đạo phòng HCBTTP tại STP, Lãnh đạo Bộ Tư pháp, Lãnh đạo Cục BTTP, Chuyên viên Cục BTTP, Nhân viên TCHNCC, tổ chức công chứng TCHNCC, tôi muốn tra cứu thông tin tổ chức công chứng theo nhiều tiêu chí, để xác minh thông tin và kiểm tra tình trạng hoạt động.

## Acceptance criteria
- Hệ thống hiển thị form tra cứu với các tiêu chí
    - Ô điền thông tin tra cứu theo "Tên tổ chức công chứng"
    - Bộ lọc:
        - Trạng thái tổ chức
        - Tỉnh/Thành phố của tổ chức hành nghề công chứng
- Hiển thị bảng danh sách tổ chức công chứng với các cột thông tin cơ bản (Tên tổ chức công chứng, Địa chỉ tổ chức công chứng, Tên trưởng văn phòng công chứng, Sở Tư pháp, Trạng thái) theo tiêu chí đã tra cứu.
- Nếu số lượng bản ghi vượt quá giới hạn hiển thị, hệ thống phải cung cấp phân trang (10 bản ghi 1 trang).
- Nếu có lỗi tải dữ liệu, hiển thị thông báo lỗi.
- Nếu không tìm thấy dữ liệu theo tiêu chí tra cứu, thông báo "Không tìm thấy dữ liệu"
- Danh sách tổ chức công chứng hiển thị theo thứ tự thời gian cập nhật từ mới tới cũ nhất.

## Tác nhân chính
- Chuyên viên STP, Lãnh đạo STP, Lãnh đạo phòng HCBTTP tại STP, Lãnh đạo Bộ Tư pháp, Lãnh đạo Cục BTTP, Chuyên viên Cục BTTP, Nhân viên TCHNCC, tổ chức công chứng TCHNCC

## Tiền điều kiện
- Người dùng đăng nhập hệ thống.
- Người dùng có quyền tra cứu thông tin tổ chức công chứng và chứng chỉ hành nghề

## Luồng chính
1. Người dùng truy cập màn hình tra cứu (**UC_Org_Lookup**).
2. Người dùng điền thông tin tra cứu (Theo tên tổ chức công chứng)
3. Người dùng lọc tiêu chí tra cứu: Trạng thái tổ chức, tỉnh thành phố của TCHNCC
4. Người dùng bấm nút "tra cứu"
5. Hệ thống truy vấn thông tin tổ chức công chứng
    - Truy vấn tên tổ chức công chứng gần giống với kết quả đã điền
    - Truy vấn chính xác theo trạng thái đã chọn
    - Truy vấn chính xác theo tỉnh thành của tổ chức công chứng đã chọn
6. Hệ thống hiển thị danh sách tổ chức công chứng theo kết quả đã truy vấn được bao gồm các thông tin: (Tên tổ chức công chứng, Địa chỉ tổ chức công chứng, Tên trưởng văn phòng công chứng, Sở Tư pháp, Trạng thái)
7. Hệ thống hiển thị danh sách tổ chức công chứng theo thứ tự thời gian cập nhật từ mới tới cũ nhất
8. Nếu số lượng bản ghi lớn hơn 10, hệ thống thực hiện phân trang, 10 bản ghi mỗi trang
9. Kết thúc.

## Luồng phụ / ngoại lệ
- Nếu có lỗi tra cứu: hiển thị thông báo "Không tải được danh sách, vui lòng thử lại".
- Nếu không tìm thấy dữ liệu: hiển thị "Không có dữ liệu tổ chức công chứng".

## Hậu điều kiện
- Nếu thành công: Người dùng tra cứu thành công thông tin tổ chức công chứng.
- Nếu thất bại: Không hiển thị dữ liệu, hoặc hiển thị thông báo lỗi.

## Liên kết
- Activity Diagram: [AD_Org_Lookup.puml]
- Form/Screen: [SCR_Org_Lookup.md]
- Entity liên quan: ENT_ToChucCongChung
