# THIẾT KẾ PROMPT ENGINEERING CHO CÁC TÍNH NĂNG AI

Để AI trả về kết quả chính xác và có thể lập trình được, em đã nghiên cứu và thiết kế cấu trúc Prompt cho 3 module AI cốt lõi của hệ thống. Kỹ thuật áp dụng: **Role-playing** và **Few-shot prompting**.

---

### 1. Tính năng: AI Task Breakdown 
*   **Mục đích:** Chia một tính năng lớn thành các đầu việc nhỏ.
*   **System Prompt thiết kế:**
    ```text
    Bạn là một Project Manager chuyên nghiệp trong lĩnh vực IT. 
    Nhiệm vụ của bạn là phân tích mô tả công việc lớn sau đây và chia nhỏ nó thành các Sub-task cụ thể để team Dev có thể thực hiện.
    
    YÊU CẦU ĐẦU RA: Trả về duy nhất một mảng JSON có cấu trúc sau, không kèm text giải thích:
    [
      { "title": "Tên task ngắn gọn", "description": "Mô tả chi tiết việc cần làm" }
    ]
    
    ĐẦU VÀO EPIC: {Nội_dung_người_dùng_nhập}
    ```

### 2. Tính năng: AI Time Estimation
*   **Mục đích:** Gợi ý số giờ cần thiết để hoàn thành một task.
*   **System Prompt thiết kế:**
    ```text
    Dựa vào mô tả công việc lập trình dưới đây, hãy ước lượng thời gian hoàn thành (tính bằng giờ). 
    Hãy xem xét các yếu tố: code, viết test, và fix bug cơ bản.
    Chỉ trả về một con số nguyên duy nhất, không giải thích gì thêm.
    
    MÔ TẢ CÔNG VIỆC: {Mô_tả_task}
    ```

### 3. Tính năng: AI Smart Summarize 
*   **Mục đích:** Đọc hàng chục bình luận trao đổi của Dev và Tester trong 1 task để tóm tắt lại tình trạng hiện tại.
*   **System Prompt thiết kế:**
    ```text
    Dưới đây là lịch sử bình luận của một Task. Hãy tóm tắt lại các vấn đề chính đang gặp phải và trạng thái hiện tại trong tối đa 3 gạch đầu dòng ngắn gọn.
    
    LỊCH SỬ BÌNH LUẬN: {Mảng_các_comment}
    ```

**Kết luận:** Với các Prompt đã được định hình cấu trúc và ép định dạng JSON, hệ thống Node.js ở Tuần 4 có thể dễ dàng map dữ liệu trả về từ AI thẳng vào cơ sở dữ liệu.
