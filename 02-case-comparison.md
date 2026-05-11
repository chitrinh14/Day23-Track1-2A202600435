# Bảng So Sánh Case Thành Công / Thất Bại

## Chọn Case

| Nhóm case | Gợi ý & Lựa chọn |
| --- | --- |
| **Thành công / tín hiệu tốt** | Morgan Stanley (Ứng dụng RAG GPT-4 vào quản trị tri thức) |
| **Thất bại / cảnh báo** | IBM Watson Oncology tại MD Anderson (Dự án AI y tế) |

## Bảng Điền

| Trường | Case thành công: **Morgan Stanley** | Case thất bại/cảnh báo: **IBM Watson (MD Anderson)** |
| --- | --- | --- |
| **Case** | Trợ lý ảo (dựa trên RAG) tra cứu hơn 100.000 báo cáo nghiên cứu và tài liệu đầu tư. | Hệ thống AI Oncology nhằm tự động đưa ra phác đồ điều trị ung thư từ y văn và hồ sơ bệnh án. |
| **AI được dùng trong quy trình nào?** | Tìm kiếm, bóc tách và tổng hợp thông tin tài chính nội bộ. | Chẩn đoán y khoa và đề xuất hướng điều trị chuyên sâu. |
| **Người dùng chính là ai?** | 16.000+ Cố vấn tài chính (Financial Advisors). | Bác sĩ chuyên khoa ung bướu. |
| **Họ đo chỉ số gì?** | Tốc độ tiếp cận thông tin; Mức độ hài lòng của cố vấn tài chính. | Độ chính xác so với phác đồ chuẩn; Thời gian triển khai; Ngân sách tiêu tốn ($62 triệu USD). |
| **Chỉ số đó thuộc lớp nào?** | **Productivity** (Năng suất) & **Engagement** (Sự gắn kết). | **Quality** (Chất lượng) & **Value** (Giá trị kinh tế). |
| **Chỉ số đó chứng minh được gì?** | AI giúp cố vấn tiết kiệm hàng giờ đọc PDF, cho phép họ phản hồi khách hàng gần như ngay lập tức. | AI có khả năng quét lượng dữ liệu khổng lồ nhưng không thể thay thế tư duy lâm sàng. |
| **Chỉ số đó chưa chứng minh được gì?** | Việc thao tác nhanh hơn có trực tiếp mang lại thêm dòng tiền đầu tư (AUM) từ khách hàng hay không. | Hoàn toàn không chứng minh được tính an toàn trên bệnh nhân thực tế. |
| **Thiếu chỉ số nào?** | Tỷ lệ báo cáo lỗi hoặc số lần cố vấn phải tự đọc lại file gốc (Override Rate) chưa được công bố rõ. | Khả năng thích ứng với các ca bệnh nằm ngoài dữ liệu được huấn luyện cứng. |
| **Rủi ro lớn nhất** | **Hallucination (Ảo giác):** Trích xuất sai số liệu báo cáo tài chính gây tư vấn sai, dẫn đến rủi ro pháp lý lớn. | **Bias (Thiên kiến dữ liệu):** Đưa ra lời khuyên điều trị nguy hiểm do học từ các "ca bệnh giả định" thay vì bệnh án thực tế. |
| **Bài học cho dashboard nhóm** | Là BA/PM, cần tập trung đo lường tính **Groundedness** (Độ bám sát tài liệu nguồn). Người dùng sẽ dùng nếu họ có thể click vào để kiểm chứng nguồn gốc câu trả lời. | Không được bỏ qua chỉ số đánh giá chất lượng đầu vào (Data Quality). Nếu AI không đọc chuẩn được biểu đồ/layout phức tạp, đầu ra sẽ vô nghĩa dù thuật toán tốt đến đâu. |

---

## Câu Chốt Của Nhóm

Case thành công (Morgan Stanley) dạy nhóm tôi rằng:
Đừng tham vọng AI sẽ thay thế con người tự động làm báo cáo cuối cùng. Giá trị cốt lõi (ROI) của RAG nằm ở việc giải phóng người dùng khỏi quy trình "đọc và tìm kiếm thủ công", giúp Productivity tăng vọt.

Case thất bại/cảnh báo (IBM Watson) dạy nhóm tôi rằng:
Kỳ vọng quá mức (Overpromise) và bỏ qua rủi ro "ảo giác/thiên kiến dữ liệu" sẽ giết chết dự án. Nếu hệ thống RAG đưa ra một câu trả lời sai lệch (dù chỉ 1 lần) ở những domain cần độ chính xác tuyệt đối, toàn bộ Trust sẽ sụp đổ.

Vì vậy dashboard nhóm tôi (PapeBreak) phải tránh:
Chỉ hiển thị các chỉ số "đẹp" về số lượng (Ví dụ: số file tải lên, số câu hỏi được đặt) mà bỏ qua các chỉ số đo lường chất lượng cốt lõi như Tỷ lệ trích xuất đúng/sai biểu đồ (VQA accuracy) và Tỷ lệ người dùng bấm nút báo lỗi.

### Nguồn Trích Dẫn (References)

**1. Case Morgan Stanley (Thành công):**

* **OpenAI Customer Stories:** Báo cáo chính thức từ OpenAI về quan hệ đối tác chiến lược. (*Nguồn: [openai.com/customer-stories/morgan-stanley*]())
* **Morgan Stanley Press Release:** "Morgan Stanley Wealth Management Announces Key Milestone in Innovation Journey with OpenAI" công bố tháng 3/2023. (*Nguồn: [morganstanley.com/press-releases*]())
* **Forbes (2023):** "How Morgan Stanley Is Training GPT-4 To Be The Ultimate Financial Advisor".

**2. Case IBM Watson MD Anderson (Thất bại/Cảnh báo):**

* **IEEE Spectrum:** Bài báo phân tích hậu kỳ kinh điển "How IBM Watson Overpromised and Underdelivered on AI Health Care" xuất bản tháng 4/2019. (*Nguồn: spectrum.ieee.org*)
* **STAT News (2018):** Loạt bài điều tra nội bộ "IBM Watson recommended 'unsafe and incorrect' cancer treatments, internal documents show", chỉ ra nguyên nhân hệ thống học từ dữ liệu giả định thay vì bệnh án thật.
* **The Wall Street Journal (2017):** Báo cáo về việc MD Anderson dừng dự án hợp tác trị giá 62 triệu USD với IBM.