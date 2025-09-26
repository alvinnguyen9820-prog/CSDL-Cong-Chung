# Use Case: Xem chi tiết thông tin đăng ký chữ ký số
## User Story
- Là Chuyên viên STP, Lãnh đạo STP, Lãnh đạo phòng HCBTTP tại STP, Lãnh đạo Bộ Tư pháp, Lãnh đạo Cục BTTP, Chuyên viên Cục BTTP, Nhân viên TCHNCC, Công chứng viên TCHNCC, tôi muốn xem được chi tiết thông tin đăng ký chữ ký số để có thế kiểm tra trạng thái phê duyệt và đảm bảo thông tin chính xác

## Acceptance criteria
- Hệ thống hiển thị đầy đủ chi tiết của thông tin đăng ký chữ ký số được chọn từ danh sách.
- Các trường thông tin bao gồm: 
   - Công chứng viên
   - Gói đăng ký
   - Nhà cung cấp
   - Mã chứng thư
   - Ngày hiệu lực
   - Ngày hết hạn 
   - File đính kèm
   - Trạng thái
   - Người duyệt
   - Thời gian duyệt
- Người dùng có thể quay lại trang danh sách thông tin đăng ký chữ ký số
- Nếu không tìm thấy dữ liệu, hệ thống hiển thị thông báo "Không tìm thấy thông tin đăng ký chữ ký số".
- Nếu có lỗi hệ thống, hiển thị thông báo lỗi.  

## Tác nhân chính
- Chuyên viên STP, Lãnh đạo STP, Lãnh đạo phòng HCBTTP tại STP, Lãnh đạo Bộ Tư pháp, Lãnh đạo Cục BTTP, Chuyên viên Cục BTTP, Nhân viên TCHNCC, Công chứng viên TCHNCC

## Tiền điều kiện
- Người dùng đăng nhập hệ thống.
- Người dùng có quyền xem chi tiết thông tin đăng ký chữ ký số

## Luồng chính
1. Người dùng truy cập thành công màn hình danh sách thông tin đăng ký chữ ký số (**SCR_CKS_List**)
2. Người dùng truy cập trang chi tiết thông tin đăng ký chữ ký số băng cách click vào biểu tượng xem chi tiết 1 thông tin đăng ký chữ ký số trong danh sách
3. Nếu người dùng có quyền xem thông tin đăng ký chữ ký số, Hệ thống truy vấn thông tin đăng ký chữ ký số theo ID (**ENT_ChuKySo**).
4. Hệ thống hiển thị popup chi tiết thông tin đăng ký chữ ký số (**SCR_CKS_Detail**) bao gồm các thông tin
    - Công chứng viên
   - Gói đăng ký
   - Nhà cung cấp
   - Mã chứng thư
   - Ngày hiệu lực
   - Ngày hết hạn 
   - File đính kèm
   - Trạng thái
   - Người duyệt
   - Thời gian duyệt
5. Hệ thống hiển thị các nút chức năng.
- Biểu tượng quay lại và nút đóng => Bấm vào chuyển về màn hình danh sách thông tin đăng ký chữ ký số (**SCR_CKS_List**)
- Các nút chức năng: Duyệt, Từ chối => Mô tả trong (**SCR_CKS_Detail**)
6. Người dùng có quyền phê duyệt thông tin đăng ký click vào nút Duyệt, hệ thống đổi trạng thái đăng ký chữ ký số thành "Đã duyệt". Hệ thống cập nhật vào lịch sử
7. Kết thúc Use case

## Luồng phụ / ngoại lệ
- Không có dữ liệu: Hiển thị "Không tìm thấy thông tin đăng ký chữ ký số".
- Lỗi hệ thống: Hiển thị thông báo "Không tải được thông tin, vui lòng thử lại".
- Người dùng có quyền phê duyệt thông tin đăng ký click vào nút Từ chối, hệ thống đổi trạng thái đăng ký chữ ký số thành "Từ chối". Hệ thống cập nhật vào lịch sử

## Hậu điều kiện
- Nếu thành công: Người dùng xem được chi tiết thông tin đăng ký chữ ký số.
- Nếu thất bại: Không hiển thị dữ liệu, hoặc hiển thị thông báo lỗi.

## Liên kết
- Activity Diagram: [AD_CKS_Detail.puml]
- Form/Screen: [SCR_CKS_Detail.md]
- Entity liên quan: ENT_ChuKySo
