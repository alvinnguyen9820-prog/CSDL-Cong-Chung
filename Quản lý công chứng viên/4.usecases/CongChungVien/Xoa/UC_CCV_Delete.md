# Use Case: Xóa công chứng viên

## User Story
- Là Chuyên viên STP, tôi muốn xóa được một hoặc nhiều công chứng viên, để có thể loại bỏ những bản ghi đã bị tạo nhầm.

## Acceptance criteria
- Khi người dùng chọn Xóa công chứng viên, hệ thống phải hiển thị hộp thoại xác nhận với nội dung: “Bạn có chắc chắn muốn xóa công chứng viên này không?”.
- Hệ thống phải cung cấp hai lựa chọn: Xác nhận và Hủy.
- Nếu người dùng chọn Hủy, hệ thống đóng hộp thoại và công chứng viên không bị xóa.
- Nếu người dùng chọn Xác nhận, hệ thống phải kiểm tra điều kiện trước khi xóa
- Nếu vi phạm điều kiện, hệ thống phải hiển thị thông báo lỗi rõ ràng, ví dụ: “Không thể xóa công chứng viên đang có hồ sơ công chứng còn hiệu lực”
- Nếu không còn ràng buộc dữ liệu, hệ thống xóa thành công và hiển thị thông báo "Xóa thành công thông tin công chứng viên".
- Hệ thống phải ghi nhận thông tin xóa công chứng viên vào nhật ký hệ thống. 
- Hệ thống phải cập nhật danh sách công chứng viên hiển thị trên **SCR_CCV_List** sau khi xóa thành công

## Tác nhân chính
- Chuyên viên STP

## Tiền điều kiện
- Người dùng đã đăng nhập hệ thống.
- Người dùng có quyền xóa công chứng viên

## Luồng chính
1. Người dùng truy cập màn hình danh sách công chứng viên **SCR_CCV_List**.  
2. Nếu người dùng có quyền xóa công chứng viên, hệ thống hiển thị nút xóa công chứng viên trên mỗi bản ghi
3. Người dùng nhấn nút "Xóa" trên bản ghi công chứng viên.  
3. Hệ thống hiển thị popup xác nhận xóa.  
4. Người dùng nhấn nút "Xác nhận".  
5. Hệ thống kiểm tra:  
   - Nếu công chứng viên còn hồ sơ công chứng đang hiệu lực → Hệ thống đóng popup → Hiển thị cảnh báo lỗi "Không thể xóa công chứng viên đang có hồ sơ công chứng còn hiệu lực"  và không thực hiện xóa.  
   - Nếu không có ràng buộc → Xóa dữ liệu công chứng viên trong **ENT_CongChungVien**.  
6. Hệ thống đóng popup, hiển thị thông báo kết quả "Xóa thành công thông tin công chứng viên" .  
7. Use case kết thúc. 

## Luồng phụ / ngoại lệ
- Người dùng nhấn **Hủy** hoặc biểu tượng đóng popup xác nhận xóa → Hệ thống đóng popup, use case kết thúc, không có thay đổi.  
- Nếu có lỗi hệ thống → Hiển thị thông báo lỗi chung, không xóa dữ liệu.  

## Hậu điều kiện
- Nếu thành công: Công chứng viên bị xóa và không còn trong danh sách.  
- Nếu thất bại hoặc hủy: Không có thay đổi nào trong hệ thống.

## Liên kết
- Activity Diagram: [AD_CCV_Delete.puml]
- Form/Screen: [SCR_CCV_List.md], [SCR_CCV_Delete.md]
- Entity liên quan: ENT_CongChungVien
