# NGHIÊN CỨU TÍCH HỢP TRÍ TUỆ NHÂN TẠO (AI) VÀO HỆ THỐNG

**Người thực hiện:** Phạm Nam Khánh
**Giai đoạn:** Tuần 3 - Nghiên cứu sử dụng AI trong phát triển phần mềm

---

## 1. Tổng quan phương pháp tích hợp AI
Thay vì tự huấn luyện một mô hình Machine Learning từ con số không, dự án sẽ sử dụng phương pháp **Giao tiếp qua API** với các Mô hình Ngôn ngữ Lớn (LLM) đã được huấn luyện sẵn như Google Gemini hoặc OpenAI GPT. 

Hệ thống Backend sẽ đóng vai trò trung gian: nhận yêu cầu từ người dùng, đóng gói thành câu lệnh, gửi lên Server của AI qua giao thức HTTP/REST, nhận kết quả JSON trả về và hiển thị lên giao diện.

## 2. Lựa chọn mô hình AI
Sau khi khảo sát, dự án quyết định nghiên cứu sử dụng **Google Gemini API** với các ưu điểm:
*   Khả năng xử lý ngôn ngữ tự nhiên tiếng Việt xuất sắc.
*   Tốc độ phản hồi thấp, phù hợp cho các tính năng thời gian thực.
*   Hỗ trợ cấu trúc trả về định dạng JSON, giúp hệ thống dễ dàng bóc tách dữ liệu để lưu vào Database.

## 3. Kiến trúc luồng dữ liệu (Data Flow)
Ví dụ luồng xử lý cho tính năng "AI Phân rã công việc":
1. **Client:** Người dùng nhập mô tả dự án lớn $\rightarrow$ Bấm nút "AI Breakdown".
2. **Backend:** Nhận text $\rightarrow$ Gắn vào một Prompt mẫu đã thiết kế sẵn $\rightarrow$ Gọi API gửi tới Gemini/OpenAI kèm theo API Key bảo mật.
3. **AI Server:** Xử lý và trả về mảng danh sách các task nhỏ dưới dạng JSON.
4. **Backend:** Nhận JSON $\rightarrow$ Lưu các task vào Database (MySQL) $\rightarrow$ Trả dữ liệu về Client.
5. **Client:** Hiển thị danh sách task mới lên bảng Kanban.
