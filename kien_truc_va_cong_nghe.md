# KIẾN TRÚC HỆ THỐNG VÀ YÊU CẦU PHI CHỨC NĂNG

**Dự án:** Hệ thống quản lý dự án tích hợp AI
**Giai đoạn:** Tuần 2 - Xây dựng yêu cầu bài toán

---

## 1. LỰA CHỌN CÔNG NGHỆ 
Để đảm bảo hệ thống vận hành trơn tru và dễ dàng tích hợp các API của Trí tuệ nhân tạo, dự án dự kiến sẽ được phát triển dựa trên các công nghệ sau:

*   **Frontend :** Sử dụng **ReactJS** kết hợp với **Bootstrap** để xây dựng giao diện dạng Single Page Application (SPA), giúp thao tác kéo thả Task trên bảng Kanban mượt mà, không cần tải lại trang. Ngôn ngữ chính là HTML, CSS, JavaScript.
*   **Backend :** Sử dụng **PHP** (môi trường XAMPP)
*   **Database :** Hệ quản trị cơ sở dữ liệu relational **MySQL** để lưu trữ thông tin User, Project, Task và phân quyền phức tạp.
*   **AI Integration :** Dự kiến gọi API của OpenAI  hoặc Google Gemini để thực hiện xử lý ngôn ngữ tự nhiên (NLP) cho tính năng phân rã Task.

---

## 2. YÊU CẦU PHI CHỨC NĂNG 

### 2.1. Hiệu năng 
*   **Thời gian phản hồi :** Các thao tác cơ bản (thêm task, chuyển trạng thái) phải phản hồi dưới 1 giây. Riêng các thao tác gọi AI  cho phép độ trễ tối đa 3-5 giây để chờ API trả kết quả.
*   **Khả năng chịu tải:** Hệ thống đảm bảo hoạt động ổn định khi có nhiều user trong một Workspace thao tác cập nhật bảng công việc cùng lúc.

### 2.2. Bảo mật 
*   Mật khẩu người dùng phải được mã hóa trước khi lưu vào cơ sở dữ liệu MySQL 
*   Sử dụng cơ chế xác thực JWT  để bảo vệ các API endpoint, đảm bảo chỉ những user thuộc dự án mới có quyền xem và sửa Task của dự án đó.
*   Chống các lỗ hổng web cơ bản như SQL Injection hay XSS khi người dùng nhập mô tả công việc.

### 2.3. Trải nghiệm người dùng 
*   Giao diện thân thiện, tuân thủ nguyên tắc thiết kế Responsive
*   Có các thông báo rõ ràng khi người dùng thao tác thành công hoặc gặp lỗi.
