# Use Case: UC_Sign_Detail (Xem chi tiết đăng ký chữ ký số)

## User Story
- Với vai trò là **Công chứng viên / Nhân viên TCHNCC / Chuyên viên STP / Lãnh đạo**, tôi muốn xem chi tiết một hồ sơ đăng ký chữ ký số để kiểm tra thông tin và lịch sử xử lý.

## Acceptance Criteria
- Hiển thị đầy đủ thông tin hồ sơ: Công chứng viên, Gói, Nhà cung cấp, Ngày hiệu lực, Ngày hết hạn, File đính kèm, Trạng thái, Người gửi, Thời gian gửi, Người duyệt, Thời gian duyệt, Lý do từ chối (nếu có).
- Có các hành động phù hợp theo quyền và trạng thái (Ví dụ: Export, Tải file, Gửi duyệt, Sửa nếu nháp, Hủy nếu nháp).

## Actors
- Công chứng viên
- Nhân viên TCHNCC
- Chuyên viên STP
- Lãnh đạo

## Pre-conditions
- Người dùng đã đăng nhập và chọn một bản ghi trên danh sách.

## Main Flow
1. Người dùng mở chi tiết hồ sơ (từ UC_Sign_List).
2. Hệ thống truy vấn và hiển thị thông tin chi tiết (SCR_Sign_Detail).
3. Người dùng có thể download file, xem lịch sử, hoặc thực hiện hành động tùy quyền.

## Alternatives
- Không tìm thấy hồ sơ: Hiển thị thông báo.

## Post-conditions
- Người dùng xem được thông tin chi tiết.

## Related
- AD_Sign_Detail.puml
- SCR_Sign_Detail.md
- ENT: ChuKySo