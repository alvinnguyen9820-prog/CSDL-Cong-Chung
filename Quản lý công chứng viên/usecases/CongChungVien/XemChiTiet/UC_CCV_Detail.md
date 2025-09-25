# Use Case: Xem chi tiết thông tin công chứng viên (UC_ViewList_CCV)

## User Story
- Là Chuyên viên STP, Lãnh đạo STP, Lãnh đạo phòng HCBTTP tại STP, Lãnh đạo Bộ Tư pháp, Lãnh đạo Cục BTTP, Chuyên viên Cục BTTP, tôi muốn xem được chi tiết thông tin của công chứng viên để nắm rõ hồ sơ cá nhân, chứng chỉ hành nghề và tình trạng hoạt động của họ

## Acceptance criteria
- Hệ thống hiển thị đầy đủ thông tin chi tiết của công chứng viên được chọn từ danh sách.
- Các trường thông tin bao gồm: 
    - Họ tên 
    - Ngày sinh
    - Giới tính
    - Số giấy tờ (CMND/CCCD)
    - Thông tin giấy tờ
    - Số thẻ Công chứng viên
    - Trạng thái hoạt động
    - Email
    - Số điện thoại
    - Địa chỉ 
    - Ngày cấp thẻ
    - Tên tổ chức công chứng đang hành nghề
    - Địa chỉ tổ chức công chứng đang hành nghề
    - Danh sách chứng chỉ của công chứng viên (**UC_CHUNGCHI_List**)
    - Danh sách chữ ký số (**UC_CKS_List**)
- Người dùng có thể quay lại danh sách công chứng viên.
- Nếu không tìm thấy dữ liệu, hệ thống hiển thị thông báo "Không tìm thấy thông tin công chứng viên".
- Nếu có lỗi hệ thống, hiển thị thông báo lỗi.  

## Tác nhân chính
- Chuyên viên STP, Lãnh đạo STP, Lãnh đạo phòng HCBTTP tại STP, Lãnh đạo Bộ Tư pháp, Lãnh đạo Cục BTTP, Chuyên viên Cục BTTP

## Tiền điều kiện
- Người dùng đăng nhập hệ thống.
- Người dùng có quyền xem chi tiết thông tin công chứng viên

## Luồng chính
1. Người dùng chọn một công chứng viên từ danh sách (**UC_CCV_List**).
2. Hệ thống truy vấn thông tin chi tiết công chứng viên theo ID.
3. Hệ thống hiển thị màn hình chi tiết công chứng viên (**SCR_CCV_Detail**).
4. Người dùng có thể:
   - Xem thông tin cá nhân.
   - Xem danh sách chứng chỉ hành nghề (nếu có quyền) => chi tiết trong **UC_CHUNGCHI_List**.
   - Xem danh sách chữ ký số (nếu có quyền) => chi tiết trong **UC_CKS_Detail**.
5. Người dùng quay lại danh sách hoặc thực hiện các thao tác khác (nếu được phân quyền).

## Luồng phụ / ngoại lệ
- Không có dữ liệu: Hiển thị "Không tìm thấy thông tin công chứng viên".
- Lỗi hệ thống: Hiển thị thông báo "Không tải được thông tin, vui lòng thử lại".

## Hậu điều kiện
- Nếu thành công: Người dùng xem được thông tin chi tiết công chứng viên.
- Nếu thất bại: Không hiển thị dữ liệu, hoặc hiển thị thông báo lỗi.

## Liên kết
- Activity Diagram: [AD_CCV_Detail.puml]
- Form/Screen: [SCR_CCV_Detail.md]
- Entity liên quan: ENT_CongChungVien, ENT_ToChucCongChung, ENT_ChuKySo, ENT_ChungChiHanhNghe
