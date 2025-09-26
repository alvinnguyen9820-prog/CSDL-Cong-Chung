# Use Case: Xem danh sách Thông tin đăng ký chữ ký số

## User Story
- Là Nhân viên TCHNCC, Công chứng viên của TCNHCC, tôi muốn xóa được Thông tin đăng ký chữ ký số, để có thể loại bỏ những bản ghi đã bị tạo nhầm.

## Acceptance criteria
- Khi người dùng chọn Xóa Thông tin đăng ký chữ ký số, hệ thống phải hiển thị hộp thoại xác nhận với nội dung: “Bạn có chắc chắn muốn xóa Thông tin đăng ký chữ ký số này không?”.
- Hệ thống phải cung cấp hai lựa chọn: Xác nhận và Hủy.
- Nếu người dùng chọn Hủy, hệ thống đóng hộp thoại và Thông tin đăng ký chữ ký số không bị xóa.
- Nếu người dùng chọn Xác nhận, hệ thống phải kiểm tra điều kiện trước khi xóa
- Nếu không còn ràng buộc dữ liệu, hệ thống xóa thành công và hiển thị thông báo "Xóa thành công thông tin Thông tin đăng ký chữ ký số".
- Hệ thống phải ghi nhận thông tin xóa Thông tin đăng ký chữ ký số vào nhật ký hệ thống. 
- Hệ thống phải cập nhật danh sách Thông tin đăng ký chữ ký số hiển thị trên **SCR_CKS_List** sau khi xóa thành công
- Nhân viên TCHNCC, công chứng viên chỉ có thể xóa đăng ký chữ ký số của tổ chức mình

## Tác nhân chính
- Nhân viên TCHNCC, Công chứng viên của TCNHCC

## Tiền điều kiện
- Người dùng đã đăng nhập hệ thống.
- Người dùng có quyền xóa Thông tin đăng ký chữ ký số

## Luồng chính
1. Người dùng truy cập màn hình danh sách Thông tin đăng ký chữ ký số **SCR_CKS_List**.  
2. Nếu người dùng có quyền xóa Thông tin đăng ký chữ ký số, hệ thống hiển thị nút xóa Thông tin đăng ký chữ ký số trên mỗi bản ghi
3. Người dùng nhấn nút "Xóa" trên bản ghi Thông tin đăng ký chữ ký số.  
3. Hệ thống hiển thị popup xác nhận xóa.  
4. Người dùng nhấn nút "Xác nhận".  
5. Hệ thống kiểm tra:  
   - Nếu Thông tin đăng ký chữ ký số còn hồ sơ công chứng đang hiệu lực → Hệ thống đóng popup → Hiển thị cảnh báo lỗi "Không thể xóa Thông tin đăng ký chữ ký số đang có hồ sơ công chứng còn hiệu lực"  và không thực hiện xóa.  
   - Nếu không có ràng buộc → Xóa dữ liệu Thông tin đăng ký chữ ký số trong **ENT_ChuKySo**.  
6. Hệ thống đóng popup, hiển thị thông báo kết quả "Xóa thành công thông tin Thông tin đăng ký chữ ký số" .  
7. Use case kết thúc. 

## Luồng phụ / ngoại lệ
- Người dùng nhấn **Hủy** hoặc biểu tượng đóng popup xác nhận xóa → Hệ thống đóng popup, use case kết thúc, không có thay đổi.  
- Nếu có lỗi hệ thống → Hiển thị thông báo lỗi chung, không xóa dữ liệu.  

## Hậu điều kiện
- Nếu thành công: Thông tin đăng ký chữ ký số bị xóa và không còn trong danh sách.  
- Nếu thất bại hoặc hủy: Không có thay đổi nào trong hệ thống.

## Liên kết
- Activity Diagram: [AD_CKS_Delete.puml]
- Form/Screen: [SCR_CKS_List.md], [SCR_CKS_Delete.md]
- Entity liên quan: ENT_ChuKySo
