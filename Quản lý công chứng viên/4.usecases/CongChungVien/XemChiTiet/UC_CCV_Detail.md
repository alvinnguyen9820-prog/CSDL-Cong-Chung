# Use Case: Xem chi tiết thông tin công chứng viên (UC_ViewList_CCV)

## User Story
- Là Chuyên viên STP, Lãnh đạo STP, Lãnh đạo phòng HCBTTP tại STP, Lãnh đạo Bộ Tư pháp, Lãnh đạo Cục BTTP, Chuyên viên Cục BTTP, tôi muốn xem được chi tiết thông tin của công chứng viên để nắm rõ hồ sơ cá nhân, chứng chỉ hành nghề và tình trạng hoạt động của họ

## Acceptance criteria
- Hệ thống hiển thị đầy đủ thông tin chi tiết của công chứng viên được chọn từ danh sách.
- Các trường thông tin bao gồm: 
    - Họ tên 
    - Ngày sinh
    - Giới tính
    - Số điện thoại
    - Email
    - Số giấy tờ (CMND/CCCD/Hộ Chiếu)
    - Ngày cấp
    - Nơi cấp
    - Địa chỉ thường trú
    - Tỉnh/Thành phố thường trú (cũ)
    - Phường/xã thường trú (cũ)
    - Tỉnh/Thành phố thường trú (mới)
    - Phường/xã thường trú (mới)
    - Trạng thái
    - Tên tổ chức công chứng đang hành nghề
    - Địa chỉ tổ chức công chứng đang hành nghề
    - Số thẻ Công chứng viên
    - Địa chỉ 
    - Thông tin chứng chỉ của công chứng viên (Nếu có quyền xem)
- Người dùng có thể quay lại danh sách công chứng viên.
- Nếu không tìm thấy dữ liệu, hệ thống hiển thị thông báo "Không tìm thấy thông tin công chứng viên".
- Nếu có lỗi hệ thống, hiển thị thông báo lỗi.  

## Tác nhân chính
- Chuyên viên STP, Lãnh đạo STP, Lãnh đạo phòng HCBTTP tại STP, Lãnh đạo Bộ Tư pháp, Lãnh đạo Cục BTTP, Chuyên viên Cục BTTP

## Tiền điều kiện
- Người dùng đăng nhập hệ thống.
- Người dùng có quyền xem chi tiết thông tin công chứng viên

## Luồng chính
1. Người dùng truy cập thành công màn hình danh sách công chứng viên
2. Người dùng truy cập trang chi tiết thông tin công chứng viên băng cách click vào "Họ và tên" công chứng viên hoặc biểu tưởng xem chi tiết
2. Hệ thống truy vấn thông tin chi tiết công chứng viên theo ID (**ENT_CongChungVien** và **ENT_Nguoi**).
3. Nếu người dùng có quyền xem chứng chỉ hành nghề, hệ thống truy vấn danh sách chứng chỉ hành nghề công chứng viên theo congChungVienId (**ENT_ChungChiHanhNghe**)
4. Hệ thống hiển thị màn hình chi tiết công chứng viên (**SCR_CCV_Detail**) bao gồm các thông tin
    - Thông tin chung (**ENT_CongChungVien** và **ENT_Nguoi**)
        - Họ tên 
        - Ngày sinh
        - Giới tính
        - Số điện thoại
        - Email
        - Số giấy tờ (CMND/CCCD/Hộ Chiếu)
        - Ngày cấp
        - Nơi cấp
        - Địa chỉ thường trú
        - Tỉnh/Thành phố thường trú (cũ)
        - Phường/xã thường trú (cũ)
        - Tỉnh/Thành phố thường trú (mới)
        - Phường/xã thường trú (mới)
    - Thông tin tổ chức hành nghề công chứng hiện tại (**ENT_CongChungVien** và **ENT_ToChucCongChung**)
        - Tên tổ chức công chứng đang hành nghề
        - Địa chỉ tổ chức công chứng đang hành nghề
        - Số thẻ Công chứng viên
        - Trạng thái
    - Thông tin chứng chỉ hành nghề của công chứng viên (Nếu có quyền xem) (**ENT_ChungChiHanhNghe**)
        - Số chứng chỉ
        - Ngày cấp
        - Nơi cấp
        - Ngày hiệu lực
        - Ngày hết hạn
        - Đơn vị cấp
        - Trạng thái
        - File đính kèm
5. Hệ thống hiển thị các nút chức năng.
- Biểu tượng quay lại và nút đóng => Bấm vào chuyển về màn hình danh sách công chứng viên (**SCR_CCV_List**)
- Chỉnh sửa => Mô tả trong use case chỉnh sửa thông tin công chứng viên (**UC_CCV_Update**) và màn hình (**SCR_CCV_Detail**)
6. Người dùng có thể xem lịch sử cập nhật chứng chỉ hành nghề (Mô tả trong **UC_ChungChi_History**)
7. Kết thúc Use case

## Luồng phụ / ngoại lệ
- Không có dữ liệu: Hiển thị "Không tìm thấy thông tin công chứng viên".
- Lỗi hệ thống: Hiển thị thông báo "Không tải được thông tin, vui lòng thử lại".

## Hậu điều kiện
- Nếu thành công: Người dùng xem được thông tin chi tiết công chứng viên.
- Nếu thất bại: Không hiển thị dữ liệu, hoặc hiển thị thông báo lỗi.

## Liên kết
- Activity Diagram: [AD_CCV_Detail.puml]
- Form/Screen: [SCR_CCV_Detail.md]
- Entity liên quan: ENT_CongChungVien, ENT_ToChucCongChung, ENT_ChungChiHanhNghe
