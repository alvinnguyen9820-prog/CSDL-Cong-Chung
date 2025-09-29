# Use Case: Xóa tổ chức công chứng

## User Story
- Là Chuyên viên STP, tôi muốn xóa được tổ chức công chứng thuộc Sở Tư pháp của mình, để có thể loại bỏ những bản ghi đã bị tạo nhầm.

## Acceptance criteria
- Khi người dùng chọn Xóa tổ chức công chứng, hệ thống phải hiển thị hộp thoại xác nhận với nội dung: “Bạn có chắc chắn muốn xóa tổ chức công chứng này không?”.
- Hệ thống phải cung cấp hai lựa chọn: Xác nhận và Hủy.
- Nếu người dùng chọn Hủy, hệ thống đóng hộp thoại và tổ chức công chứng không bị xóa.
- Nếu người dùng chọn Xác nhận, hệ thống phải kiểm tra điều kiện trước khi xóa
- Nếu vi phạm điều kiện, hệ thống phải hiển thị thông báo lỗi rõ ràng, ví dụ: “Không thể xóa tổ chức công chứng đang có hồ sơ công chứng còn hiệu lực”
- Nếu không còn ràng buộc dữ liệu, hệ thống xóa thành công và hiển thị thông báo "Xóa thành công thông tin tổ chức công chứng".
- Hệ thống phải ghi nhận thông tin xóa tổ chức công chứng vào nhật ký hệ thống. 
- Hệ thống phải cập nhật danh sách tổ chức công chứng hiển thị trên **SCR_Org_List** sau khi xóa thành công

## Tác nhân chính
- Chuyên viên STP

## Tiền điều kiện
- Người dùng đã đăng nhập hệ thống.
- Người dùng có quyền xóa tổ chức công chứng

## Luồng chính
1. Người dùng truy cập màn hình danh sách tổ chức công chứng **SCR_Org_List**.  
2. Nếu người dùng có quyền xóa tổ chức công chứng, hệ thống hiển thị nút xóa tổ chức công chứng trên mỗi bản ghi
3. Người dùng nhấn nút "Xóa" trên bản ghi tổ chức công chứng.  
3. Hệ thống hiển thị popup xác nhận xóa.  
4. Người dùng nhấn nút "Xác nhận".  
5. Hệ thống kiểm tra:  
   - Nếu tổ chức công chứng còn công chứng viên hoạt động → Hệ thống đóng popup → Hiển thị cảnh báo lỗi "Không thể xóa tổ chức công chứng đang còn công chứng viên hoạt động"  và không thực hiện xóa.  
   - Nếu không có ràng buộc → Xóa dữ liệu tổ chức công chứng trong **ENT_ToChucCongChung**.  
6. Hệ thống đóng popup, hiển thị thông báo kết quả "Xóa thành công thông tin tổ chức công chứng" .  
7. Use case kết thúc. 

## Luồng phụ / ngoại lệ
- Người dùng nhấn **Hủy** hoặc biểu tượng đóng popup xác nhận xóa → Hệ thống đóng popup, use case kết thúc, không có thay đổi.  
- Nếu có lỗi hệ thống → Hiển thị thông báo lỗi chung, không xóa dữ liệu.  

## Hậu điều kiện
- Nếu thành công: tổ chức công chứng bị xóa và không còn trong danh sách.  
- Nếu thất bại hoặc hủy: Không có thay đổi nào trong hệ thống.

## Liên kết
- Activity Diagram: [AD_Org_Delete.puml]
- Form/Screen: [SCR_Org_List.md], [SCR_Org_Delete.md]
- Entity liên quan: ENT_CongChungVien
