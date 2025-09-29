# Use Case: Xuất danh sách công chứng viên

## User Story
- Là Chuyên viên STP, Lãnh đạo STP, Lãnh đạo phòng HCBTTP tại STP, Lãnh đạo Bộ Tư pháp, Lãnh đạo Cục BTTP, Chuyên viên Cục BTTP, tôi muốn xuất được danh sách công chứng viên trên hệ thống theo kết quả tìm kiếm để có thể lấy được dữ liệu dưới dạng file excel

## Acceptance criteria
- Xuất thành công danh sách gồm các trường thông tin

## Tác nhân chính
- Chuyên viên STP, Lãnh đạo STP, Lãnh đạo phòng HCBTTP tại STP, Lãnh đạo Bộ Tư pháp, Lãnh đạo Cục BTTP, Chuyên viên Cục BTTP

## Tiền điều kiện
- Người dùng đã đăng nhập hệ thống.
- Người dùng có quyền xuất danh sách công chứng viên

## Luồng chính
1. Người dùng truy cập thành công màn hình danh sách công chứng viên.
2. Người dùng tìm kiếm danh sách công chứng viên cần xuất (UC_CCV_Export).
3. Người dùng bấm xuất danh sách.
4. Nếu người dùng có quyền, hệ thống xuất danh sách công chứng viên theo kết quả đã tìm kiếm
5. Kết thúc.

## Luồng phụ / ngoại lệ
- Nếu có lỗi tải danh sách: hiển thị thông báo "Không tải được danh sách, vui lòng thử lại".
- Nếu không quyền truy cập: hiển thị "Không có quyền truy cập" và ẩn đi nút "xuất danh sách".

## Hậu điều kiện
- Nếu thành công: Người dùng xuất được danh sách công chứng viên.
- Nếu thất bại: Thông báo lỗi.

## Liên kết
- Activity Diagram: [AD_CCV_Export.puml]
- Form/Screen: [SCR_CCV_List.md]
- Entity liên quan: ENT_CongChungVien, ENT_ToChucCongChung
