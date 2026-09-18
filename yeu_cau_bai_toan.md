# ĐẶC TẢ YÊU CẦU BÀI TOÁN - HỆ THỐNG QUẢN LÝ DỰ ÁN TÍCH HỢP AI

**Người thực hiện:** Phạm Nam Khánh
**Dự án:** Quản lý dự án thông minh 

---

## 1. TỔNG QUAN HỆ THỐNG
Dự án nhằm mục đích xây dựng một ứng dụng web quản lý công việc và dự án tương tự như Jira hay Trello, nhưng được tích hợp thêm Trí tuệ nhân tạo  để tối ưu hóa năng suất làm việc của nhóm.

## 2. CÁC TÁC NHÂN (ACTORS)
Hệ thống bao gồm 3 nhóm người dùng chính:
1. **Admin (Quản trị viên):** Quản lý toàn bộ hệ thống, cấp quyền tài khoản, quản lý các gói dịch vụ.
2. **Project Manager - PM (Quản lý dự án):** Khởi tạo dự án, tạo task, phân công công việc, theo dõi tiến độ và sử dụng AI để hỗ trợ lên kế hoạch.
3. **Member (Thành viên/Lập trình viên):** Nhận task, cập nhật trạng thái làm việc (To do, In progress, Done), bình luận và báo cáo tiến độ.

## 3. CÁC MODULE CHỨC NĂNG CỐT LÕI (CORE MODULES)
* **Module Authentication:** Đăng nhập, đăng ký, khôi phục mật khẩu, phân quyền người dùng.
* **Module Workspace:** Quản lý không gian làm việc, mời thành viên vào nhóm.
* **Module Board (Kanban/Scrum):** Giao diện kéo thả trạng thái công việc trực quan. Quản lý chi tiết Task (Tiêu đề, mô tả, người phụ trách, deadline, file đính kèm).
* **Module Notification:** Thông báo thời gian thực khi có người giao task hoặc tag tên.

## 4. MODULE TÍCH HỢP AI (AI FEATURES) - Trọng tâm Tuần 3
* **AI Task Breakdown (Phân rã công việc tự động):** Khi PM nhập một yêu cầu lớn (Epic), AI sẽ tự động phân tích và đề xuất chia nhỏ thành các Sub-task chi tiết.
* **AI Time Estimation (Dự đoán thời gian):** Phân tích mô tả công việc và lịch sử làm việc để gợi ý thời gian hoàn thành (Estimate time) phù hợp nhất.
* **AI Smart Summarize (Tóm tắt tự động):** Tự động tóm tắt các đoạn thảo luận/bình luận dài trong một Task thành vài gạch đầu dòng ngắn gọn.
