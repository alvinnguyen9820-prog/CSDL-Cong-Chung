# Use Case: Tìm kiếm tổ chức công chứng

## User Story
- Là Chuyên viên STP, Lãnh đạo STP, Lãnh đạo phòng HCBTTP tại STP, tôi muốn tìm kiếm theo nhiều tiêu chí, để có thể nhanh chóng tìm ra thông tin tổ chức công chứng trong danh sách quản lý thuộc Sở Tư pháp của mình
- Là Chuyên viên STP, Lãnh đạo STP, Lãnh đạo phòng HCBTTP tại STP, tôi muốn tìm kiếm theo nhiều tiêu chí, để có thể nhanh chóng tìm ra thông tin tổ chức công chứng trong danh sách quản lý toàn bộ hệ thống

## Acceptance criteria
- Hệ thống hiển thị form tìm kiếm với các tiêu chí
    - Ô điền thông tin tìm kiếm theo "Tên tổ chức công chứng"
    - Bộ lọc:
        - Trạng thái hoạt động 
        - Tỉnh/Thành phố của tổ chức hành nghề công chứng
- Hiển thị bảng danh sách tổ chức công chứng với các cột tông tin cơ bản (Tên tổ chức công chứng, Địa chỉ tổ chức công chứng, Tên trưởng văn phòng công chứng, Sở Tư pháp (hiển thị nếu người dùng thuộc bộ), Trạng thái) theo tiêu chí đã tìm kiếm.
- Nếu số lượng bản ghi vượt quá giới hạn hiển thị, hệ thống phải cung cấp phân trang (10 bản ghi 1 trang).
- Nếu có lỗi tải dữ liệu, hiển thị thông báo lỗi.
- Nếu không tìm thấy dữ liệu theo tiêu chí tìm kiếm, thông báo "Không tìm thấy dữ liệu tổ chức công chứng"
- Danh sách tổ chức công chứng hiển thị theo thứ tự thời gian cập nhật từ mới tới cũ nhất.

## Tác nhân chính
- Chuyên viên STP, Lãnh đạo STP, Lãnh đạo phòng HCBTTP tại STP, Lãnh đạo Bộ Tư pháp, Lãnh đạo Cục BTTP, Chuyên viên Cục BTTP

## Tiền điều kiện
- Người dùng đăng nhập hệ thống.
- Người dùng có quyền tìm kiếm thông tin tổ chức công chứng

## Luồng chính
1. Người dùng truy cập màn hình danh sách tổ chức công chứng (**UC_Org_List**).
2. Người dùng điền thông tin tìm kiếm (theo tên tổ chức công chứng)
3. Người dùng lọc tiêu chí tìm kiếm
4. Người dùng bấm nút "Tìm kiếm"
5. Nếu người dùng thuộc cấp Bộ, hệ thống thực hiện truy vấn trên toàn bộ danh sách tổ chức công chứng của hệ thống
6. Nếu người dùng thuộc cấp Sở, hệ thống truy vấn trên danh sách tổ chức công chứng thuộc Sở Tư pháp gắn với người dùng
7. Hệ thống truy vấn thông tin tổ chức công chứng
    - Truy vấn họ và tên tổ chức công chứng gần giống với kết quả đã điền
    - Truy vấn chính xác theo trạng thái đã chọn
    - Truy vấn chính xác theo tỉnh thành của tổ chức công chứng đã chọn
8. Hệ thống hiển thị danh sách công chứng theo kết quả đã truy vấn được
9. Hệ thống hiển thị danh sách tổ chức công chứng theo thứ tự thời gian cập nhật từ mới tới cũ nhất
10. Nếu số lượng bản ghi lớn hơn 10, hệ thống thực hiện phân trang, 10 bản ghi mỗi trang
11. Kết thúc.

## Luồng phụ / ngoại lệ
- Nếu có lỗi tìm kiếm: hiển thị thông báo "Không tải được danh sách, vui lòng thử lại".
- Nếu không tìm thấy dữ liệu: hiển thị "Không có dữ liệu tổ chức công chứng".

## Hậu điều kiện
- Nếu thành công: Người dùng tìm kiếm thành công thông tin tổ chức công chứng.
- Nếu thất bại: Không hiển thị dữ liệu, hoặc hiển thị thông báo lỗi.

## Liên kết
- Activity Diagram: [AD_Org_Search.puml]
- Form/Screen: [SCR_Org_List.md]
- Entity liên quan: ENT_ToChucCongChung
