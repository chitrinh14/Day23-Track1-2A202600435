# Phân tích Case - Cá nhân

## Chọn Case

| Nhóm case | Lựa chọn thực tế của nhóm |
| --- | --- |
| **Thành công / tín hiệu tốt** | Hệ thống Mentor AI của FPT Long Châu (Ứng dụng RAG vào Y tế/Bán lẻ) |
| **Thất bại / cảnh báo** | Chatbot NEO của Vietnam Airlines (Giai đoạn quy tắc cứng/NLP cũ) |

## Bảng Điền

| Trường | Case thành công (FPT Mentor AI) | Case thất bại/cảnh báo (Chatbot NEO - VNA) |
| --- | --- | --- |
| **Case** | Dùng RAG để truy xuất thông tin thuốc, phác đồ điều trị và quy trình nội bộ từ kho dữ liệu y tế. | Dùng bot tự động để trả lời câu hỏi về vé, hành lý, thủ tục bay thay cho nhân viên CSKH. |
| **AI được dùng trong quy trình nào?** | Tra cứu dược lý học, tương tác thuốc và hỗ trợ ra quyết định bán hàng tại quầy. | Trả lời nhanh, điều hướng khách hàng và cung cấp link chính sách/quy định bay. |
| **Người dùng chính là ai?** | Dược sĩ tại chuỗi nhà thuốc (đặc biệt là nhân sự mới cần onboarding). | Hành khách bay nội địa và quốc tế. |
| **Họ đo chỉ số gì?** | Tốc độ tra cứu thông tin; Thời gian đào tạo nhân viên mới (Onboarding time). | Deflection Rate (Tỷ lệ khách chat với bot mà không cần chuyển sang tổng đài viên); Số phiên chat. |
| **Chỉ số đó thuộc lớp nào?** | Productivity / Quality | Activation / Productivity (ảo) |
| **Chỉ số đó chứng minh được gì?** | Hệ thống thay thế được việc lật mở tài liệu giấy, tiết kiệm thời gian đáng kể cho dược sĩ. | Hệ thống có khả năng chặn và lọc bớt các câu hỏi lặp đi lặp lại (xin link web, hỏi số tổng đài). |
| **Chỉ số đó chưa chứng minh được gì?** | Chưa chứng minh được việc tra cứu nhanh có trực tiếp làm tăng biên lợi nhuận/doanh thu của cửa hàng hay không. | Không chứng minh được vấn đề của hành khách đã được giải quyết (khách có thể thoát chat do bực bội chứ không phải do đã xong việc). |
| **Thiếu chỉ số nào?** | Override Rate (Tỷ lệ dược sĩ bỏ qua tư vấn của AI dựa trên kinh nghiệm thực tế). | First Contact Resolution - FCR (Tỷ lệ giải quyết dứt điểm vấn đề ngay từ câu hỏi đầu tiên) / CSAT thực tế. |
| **Rủi ro lớn nhất** | **Ảo giác (Hallucination):** RAG trích xuất sai chống chỉ định thuốc gây nguy hiểm trực tiếp đến sức khỏe người bệnh. | **Mất niềm tin (Trust):** Khi hỏi quy định phức tạp, bot trả lời vòng vo hoặc quăng link PDF bắt khách tự đọc, khiến khách ức chế, tẩy chay công cụ. |
| **Bài học cho dashboard nhóm** | Trong các ngành chuyên môn sâu (y tế, tài chính, báo cáo), chỉ số Quality (độ chính xác) quyết định sinh tử, Productivity chỉ là thứ yếu. | Đừng đánh tráo khái niệm giữa "Hệ thống đã phản hồi" (Response Rate) và "Người dùng nhận được giá trị thực" (Success Rate). |