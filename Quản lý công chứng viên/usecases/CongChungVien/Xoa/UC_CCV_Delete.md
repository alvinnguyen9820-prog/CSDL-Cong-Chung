# Use Case: Xem danh sách công chứng viên

## User Story
- Là Chuyên viên STP, tôi muốn xóa được một hoặc nhiều công chứng viên, để có thể loại bỏ những bản ghi đã bị tạo nhầm.

## Acceptance criteria
- Khi người dùng chọn Xóa công chứng viên, hệ thống phải hiển thị hộp thoại xác nhận với nội dung: “Bạn có chắc chắn muốn xóa công chứng viên này không?”.
- Hệ thống phải cung cấp hai lựa chọn: Đồng ý/Xóa và Hủy.
- Nếu người dùng chọn Hủy, hệ thống đóng hộp thoại và công chứng viên không bị xóa.
- Nếu người dùng chọn Đồng ý/Xóa, hệ thống phải kiểm tra điều kiện trước khi xóa:
- Nếu vi phạm điều kiện, hệ thống phải hiển thị thông báo lỗi rõ ràng, ví dụ: “Không thể xóa công chứng viên vì còn học viên đang theo học.”, “Không thể xóa công chứng viên đang diễn ra.”
- Nếu không còn ràng buộc dữ liệu, hệ thống xóa thành công và hiển thị thông báo "Xóa thành công".
- Hệ thống phải ghi nhận thông tin xóa công chứng viên vào nhật ký hệ thống bao gồm: người thao tác, thời gian, mã công chứng viên bị xóa. 
- Hệ thống phải cập nhật danh sách công chứng viên hiển thị trên **SCR_CCV_List**

## Tác nhân chính
- Chuyên viên STP

## Tiền điều kiện
- Người dùng đăng nhập hệ thống.
- Người dùng có quyền xóa công chứng viên

## Luồng chính
1. Người dùng truy cập màn hình danh sách công chứng viên **SCR_CCV_List**.  
2. Người dùng nhấn nút "Xóa" trên bản ghi công chứng viên.  
3. Hệ thống hiển thị popup xác nhận xóa.  
4. Người dùng nhấn nút "Xác nhận".  
5. Hệ thống kiểm tra:  
   - Nếu công chứng viên còn hồ sơ công chứng đang hiệu lực → Chặn thao tác và hiển thị cảnh báo lỗi.  
   - Nếu không có ràng buộc → Xóa dữ liệu công chứng viên trong **ENT_CongChungVien** và cập nhật cơ sở dữ liệu.  
6. Hệ thống hiển thị thông báo kết quả.  
7. Use case kết thúc. 

## Luồng phụ / ngoại lệ
- Người dùng nhấn **Hủy** trong popup → Use case kết thúc, không có thay đổi.  
- Lỗi hệ thống → Hiển thị thông báo lỗi chung, không xóa dữ liệu.  

## Hậu điều kiện
- Nếu thành công: Công chứng viên bị xóa và không còn trong danh sách.  
- Nếu thất bại hoặc hủy: Không có thay đổi nào trong hệ thống.

## Liên kết
- Activity Diagram: [AD_CCV_Delete.puml]
- Form/Screen: [SCR_CCV_List.md], [SCR_CCV_Delete.md]
- Entity liên quan: ENT_CongChungVien
