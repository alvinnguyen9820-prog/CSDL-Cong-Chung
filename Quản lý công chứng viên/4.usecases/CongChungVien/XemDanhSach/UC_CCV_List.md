# Use Case: Xem danh sách công chứng viên

## User Story
- Là Chuyên viên STP, Lãnh đạo STP, Lãnh đạo phòng HCBTTP tại STP, Lãnh đạo Bộ Tư pháp, Lãnh đạo Cục BTTP, Chuyên viên Cục BTTP, tôi muốn xem được danh sách toàn bộ công chứng viên trên hệ thống để có thể quản lý và tra cứu thông tin

## Acceptance criteria
- Hiển thị bảng danh sách công chứng viên với các cột tông tin cơ bản (STT, Họ và tên, số thẻ, tên tổ chức công chứng, trạng thái hoạt động, địa chỉ tổ chức công chứng).
- Nếu số lượng bản ghi vượt quá giới hạn hiển thị, hệ thống phải cung cấp phân trang (10 bản ghi 1 trang).
- Hỗ trợ xuất (Export) danh sách theo điều kiện đã tìm  (chi tiết trong UC_CCV_Export).
- Mỗi dòng có action: Xem chi tiết, Sửa, Xóa, Xem lịch sử (tuỳ quyền).  
- Nếu có lỗi tải dữ liệu, hiển thị thông báo lỗi.
- Danh sách công chứng viên hiển thị theo thứ tự thời gian cập nhật từ mới tới cũ nhất.
- Hệ thống cho phép tìm kiếm công chứng viên (chi tiết trong UC_CCV_Search).    
- Nếu không có công chứng viên nào trong hệ thống, hiển thị thông báo “Không có dữ liệu công chứng viên”.  

## Tác nhân chính
- Chuyên viên STP, Lãnh đạo STP, Lãnh đạo phòng HCBTTP tại STP, Lãnh đạo Bộ Tư pháp, Lãnh đạo Cục BTTP, Chuyên viên Cục BTTP

## Tiền điều kiện
- Người dùng đã đăng nhập hệ thống.
- Người dùng có quyền xem danh sách công chứng viên

## Luồng chính
1. Người dùng truy cập màn hình danh sách công chứng viên.
2. Hệ thống hiển thị màn hình danh sách công chứng viên theo thứ tự thời gian cập nhật từ mới tới cũ nhất (lấy dữ liệu từ ENT_CongChungVien, ENT_Nguoi và ENT_ToChucCongChung).
3. Nếu số lượng bản ghi lớn hơn 10, hệ thống thực hiện phân trang, 10 bản ghi mỗi trang
4. Người dùng có thể:
   - Chọn trang tiếp theo/ trước, hệ thống sẽ hiển thị 10 bản ghi của trang tương ứng
   - Export (UC_CCV_Export)
   - Tìm kiếm (UC_CCV_Search)
   - Thêm mới (UC_CCV_Create)
   - Xem chi tiết (UC_CCV_Detail)
   - Xóa (UC_CCV_Delete)
   - Chỉnh sửa (UC_CCV_Update)
   - Xem lịch sử cập nhật thông tin (UC_CCV_History)
5. Kết thúc.

## Luồng phụ / ngoại lệ
- Nếu có lỗi tải danh sách: hiển thị thông báo "Không tải được danh sách, vui lòng thử lại".
- Nếu không có dữ liệu: hiển thị "Không có dữ liệu công chứng viên".
- Nếu không quyền truy cập: hiển thị "Không có quyền truy cập" và ẩn đi menu "Danh sách công chứng viên".

## Hậu điều kiện
- Nếu thành công: Người dùng xem được danh sách công chứng viên.
- Nếu thất bại: Không hiển thị dữ liệu, hoặc hiển thị thông báo lỗi.

## Liên kết
- Activity Diagram: [AD_CCV_List.puml]
- Form/Screen: [SCR_CCV_List.md]
- Entity liên quan: ENT_CongChungVien, ENT_ToChucCongChung
