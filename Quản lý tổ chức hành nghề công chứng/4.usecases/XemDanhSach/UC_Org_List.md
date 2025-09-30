# Use Case: Xem danh sách tổ chức công chứng

## User Story
- Là Chuyên viên STP, Lãnh đạo STP, Lãnh đạo phòng HCBTTP tại STP, tôi muốn xem được danh sách toàn bộ Tổ chức công chứng thuộc Sở tư pháp của mình để có thể quản lý và tra cứu thông tin
- Là Lãnh đạo Bộ Tư pháp, Lãnh đạo Cục BTTP, Chuyên viên Cục BTTP, tôi muốn xem được danh sách toàn bộ tổ chức công chứng trên hệ thống để có thể quản lý và tra cứu thông tin

## Acceptance criteria
- Hiển thị bảng danh sách tổ chức công chứng với các cột tông tin cơ bản (Tên tổ chức công chứng, Địa chỉ tổ chức công chứng, Tên trưởng văn phòng công chứng, Sở Tư pháp (hiển thị nếu người dùng thuộc bộ), Trạng thái).
- Nếu số lượng bản ghi vượt quá giới hạn hiển thị, hệ thống phải cung cấp phân trang (10 bản ghi 1 trang).
- Hỗ trợ xuất (Export) danh sách theo điều kiện đã tìm  (chi tiết trong UC_Org_Export).
- Mỗi dòng có action: Xem chi tiết, Sửa, Xóa, Xem lịch sử (tuỳ quyền).  
- Nếu có lỗi tải dữ liệu, hiển thị thông báo lỗi.
- Danh sách Tổ chức công chứng hiển thị theo thứ tự thời gian cập nhật từ mới tới cũ nhất.
- Hệ thống cho phép tìm kiếm Tổ chức công chứng (chi tiết trong UC_Org_Search).    
- Nếu không có Tổ chức công chứng nào trong hệ thống, hiển thị thông báo “Không có dữ liệu Tổ chức công chứng”.  

## Tác nhân chính
- Chuyên viên STP, Lãnh đạo STP, Lãnh đạo phòng HCBTTP tại STP, Lãnh đạo Bộ Tư pháp, Lãnh đạo Cục BTTP, Chuyên viên Cục BTTP

## Tiền điều kiện
- Người dùng đã đăng nhập hệ thống.
- Người dùng có quyền xem danh sách Tổ chức công chứng

## Luồng chính
1. Người dùng truy cập màn hình danh sách Tổ chức công chứng.
2. Nếu người dùng thuộc cấp Bộ, hệ thống tải toàn bộ danh sách Tổ chức công chứng
3. Nếu người dùng thuộc cấp Sở, hệ thống tải danh sách tổ chức công chứng thuộc Sở Tư pháp của người dùng
4. Hệ thống hiển thị màn hình danh sách Tổ chức công chứng theo thứ tự thời gian cập nhật từ mới tới cũ nhất (lấy dữ liệu từ ENT_ToChucCongChung).
5. Nếu số lượng bản ghi lớn hơn 10, hệ thống thực hiện phân trang, 10 bản ghi mỗi trang
6. Người dùng có thể:
   - Chọn trang tiếp theo/ trước, hệ thống sẽ hiển thị 10 bản ghi của trang tương ứng
   - Export (UC_Org_Export)
   - Tìm kiếm (UC_Org_Search)
   - Thêm mới (UC_Org_Create)
   - Xem chi tiết (UC_Org_Detail)
   - Xóa (UC_Org_Delete)
   - Chỉnh sửa (UC_Org_Update)
   - Xem lịch sử cập nhật thông tin (UC_Org_History)
7. Kết thúc.

## Luồng phụ / ngoại lệ
- Nếu có lỗi tải danh sách: hiển thị thông báo "Không tải được danh sách, vui lòng thử lại".
- Nếu không có dữ liệu: hiển thị "Không có dữ liệu Tổ chức công chứng".
- Nếu không quyền truy cập: hiển thị "Không có quyền truy cập" và ẩn đi menu "Quản lý tổ chức công chứng".

## Hậu điều kiện
- Nếu thành công: Người dùng xem được danh sách Tổ chức công chứng.
- Nếu thất bại: Không hiển thị dữ liệu, hoặc hiển thị thông báo lỗi.

## Liên kết
- Activity Diagram: [AD_Org_List.puml]
- Form/Screen: [SCR_Org_List.md]
- Entity liên quan: ENT_CongChungVien, ENT_ToChucCongChung
