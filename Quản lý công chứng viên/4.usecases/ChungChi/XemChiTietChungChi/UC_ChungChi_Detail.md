# Use Case: Xem chi tiết thông tin chứng chỉ hành nghề

## User Story
- Là Chuyên viên STP, Lãnh đạo STP, Lãnh đạo phòng HCBTTP tại STP, Lãnh đạo Bộ Tư pháp, Lãnh đạo Cục BTTP, Chuyên viên Cục BTTP, tôi muốn xem được chi tiết thông tin của chứng chỉ hành nghề để đảm bảo công chứng viên có đầy đủ thông tin

## Acceptance criteria
- Hệ thống hiển thị đầy đủ thông tin chi tiết của chứng chỉ hành nghề được chọn từ danh sách.
- Các trường thông tin bao gồm: 
    - Số chứng chỉ
    - Ngày cấp
    - Nơi cấp
    - Ngày hiệu lực
    - Ngày hết hạn
    - Đơn vị cấp
    - Trạng thái
    - File đính kèm
    - Họ và tên công chứng viên
    - Số thẻ
    - Số giấy tờ cá nhân
- Người dùng có thể quay lại trang chi tiết thông tin công chứng viên
- Nếu không tìm thấy dữ liệu, hệ thống hiển thị thông báo "Không tìm thấy thông tin chứng chỉ hành nghề".
- Nếu có lỗi hệ thống, hiển thị thông báo lỗi.  

## Tác nhân chính
- Chuyên viên STP, Lãnh đạo STP, Lãnh đạo phòng HCBTTP tại STP, Lãnh đạo Bộ Tư pháp, Lãnh đạo Cục BTTP, Chuyên viên Cục BTTP

## Tiền điều kiện
- Người dùng đăng nhập hệ thống.
- Người dùng có quyền xem chi tiết thông tin chứng chỉ hành nghề

## Luồng chính
1. Người dùng truy cập thành công màn hình chi tiết thông tin công chứng viên (**SCR_CCV_Detail**)
2. Người dùng truy cập trang chi tiết thông tin chứng chỉ hành nghề băng cách click vào biểu tượng xem chi tiết 1 chứng chỉ hành nghề trng danh sách
3. Nếu người dùng có quyền xem chứng chỉ hành nghề, Hệ thống truy vấn thông tin chi tiết chứng chỉ hành nghề theo ID (**ENT_ChungChiHanhNghe**, **ENT_CongChungVien** và **ENT_Nguoi**).
4. Hệ thống hiển thị popup chi tiết chứng chỉ hành nghề (**SCR_ChungChi_Detail**) bao gồm các thông tin
    - Số chứng chỉ
    - Ngày cấp
    - Nơi cấp
    - Ngày hiệu lực
    - Ngày hết hạn
    - Đơn vị cấp
    - Trạng thái
    - File đính kèm
5. Hệ thống hiển thị các nút chức năng.
- Biểu tượng quay lại và nút đóng => Bấm vào chuyển về màn hình danh sách chứng chỉ hành nghề (**SCR_ChungChi_List**)
6. Kết thúc Use case

## Luồng phụ / ngoại lệ
- Không có dữ liệu: Hiển thị "Không tìm thấy thông tin chứng chỉ hành nghề".
- Lỗi hệ thống: Hiển thị thông báo "Không tải được thông tin, vui lòng thử lại".
- Người dùng bấm vào file đính kèm (nếu có), hệ thống mở tab mới hiển thị file đính kèm

## Hậu điều kiện
- Nếu thành công: Người dùng xem được thông tin chi tiết chứng chỉ hành nghề.
- Nếu thất bại: Không hiển thị dữ liệu, hoặc hiển thị thông báo lỗi.

## Liên kết
- Activity Diagram: [AD_ChungChi_Detail.puml]
- Form/Screen: [SCR_ChungChi_Detail.md]
- Entity liên quan: ENT_ToChucCongChung, ENT_ChungChiHanhNghe
