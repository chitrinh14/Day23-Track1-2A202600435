# A. Thách Thức Và Phạm Vi Sản Phẩm

## A.1 Thách Thức Nhóm Chọn

| Trường | Trả lời |
| --- | --- |
| Thách thức áp dụng AI | Rút trích, tổng hợp và tra cứu thông tin chính xác từ các tài liệu phức tạp có chứa đa phương thức (văn bản dài xen lẫn biểu đồ, bảng biểu, hình ảnh). |
| Tình huống xuất phát từ ai / ở đâu? | Từ sinh viên làm nghiên cứu, chuyên viên phân tích, hoặc người dùng cần đọc hiểu báo cáo tài chính/khoa học (dạng PDF) với khối lượng lớn. |
| Dấu hiệu bị kẹt | Người dùng bị "quá tải thông tin", mất hàng giờ lướt qua hàng trăm trang tài liệu chỉ để tìm và đối chiếu một vài con số, biểu đồ cụ thể, dẫn đến sót ý hoặc sai lệch dữ liệu. |
| Vì sao thách thức này đáng giải quyết? | Nút thắt lớn nhất trong nghiên cứu là "tìm đúng chỗ" và "hiểu đúng hình". Giải quyết được việc này sẽ giúp tiết kiệm 50-70% thời gian xử lý tài liệu thô, nâng cao hiệu suất ra quyết định. |

## A.2 Sản Phẩm / Công Cụ AI

| Trường | Trả lời |
| --- | --- |
| Tên sản phẩm / công cụ AI | **PapeBreak** (Multimodal RAG Assistant) |
| Người dùng chính | Sinh viên, Thạc sĩ, Tiến sĩ |
| Bối cảnh sử dụng | Đang phân tích báo cáo thị trường, làm luận văn, hoặc cần phân tích nhiều bài báo cùng lúc để làm nghiên cứu. |
| Mục tiêu kinh doanh / học tập / vận hành | (Học tập/Vận hành): Giảm thiểu thời gian đọc tài liệu; tự động tìm kiếm và giải thích sự tương quan giữa văn bản và biểu đồ trong tích tắc. |
| Không nằm trong phạm vi | Tự động tạo ra một bài báo cáo/luận văn mới hoàn toàn từ số 0 (không thay thế tư duy tổng hợp cuối cùng của người dùng). |

## A.3 2-4 Quy Trình Chính

| # | Tên quy trình | Vai trò AI | Điểm người kiểm tra | Khi AI sai thì xử lý thế nào? |
| --- | --- | --- | --- | --- |
| 1 | Xử lý & Phân tích tài liệu đầu vào (Upload & Parse PDF) | **Classify / Summarize** (Phân loại trang chứa text/biểu đồ, bóc tách và tóm tắt sơ bộ). | Kiểm tra lướt qua danh sách các biểu đồ/hình ảnh AI nhận diện được sau khi tải lên. | Hệ thống báo lỗi/thiếu, người dùng tự khoanh vùng (crop) lại biểu đồ bị bỏ sót trên giao diện. |
| 2 | Truy vấn thông tin (Querying) | **Search** (Tìm kiếm ngữ nghĩa (semantic) trên cả text và metadata của hình ảnh). | Đọc lướt các thẻ nguồn (Source/Citations) mà AI gợi ý trước khi đọc câu trả lời. | Người dùng nhấn vào link nguồn báo sai, tự mở trang PDF tương ứng để đối chiếu thủ công. |
| 3 | Tổng hợp câu trả lời đa phương thức (Answering) | **Generate** (Tạo câu trả lời kết hợp ngôn ngữ tự nhiên và trích xuất nguyên bản hình ảnh/số liệu). | Đối chiếu chéo giữa câu trả lời bằng chữ của AI và hình ảnh biểu đồ gốc được đính kèm bên cạnh. | Nhấn nút "Regenerate" hoặc dùng tính năng "Sửa prompt" để yêu cầu AI chỉ tập trung vào một vùng dữ liệu hẹp hơn. |

## A.4 Chẩn Đoán Nhanh ADKAR

| Stage | Câu hỏi | Nhận định nhóm |
| --- | --- | --- |
| Awareness | Người dùng có biết AI này giúp gì không? | Khá. Họ quen dùng ChatGPT để tóm tắt text, nhưng có thể chưa biết AI có thể đọc hiểu được biểu đồ phức tạp. |
| Desire | Người dùng có muốn dùng không? | Tốt. Nhu cầu tiết kiệm thời gian đọc tài liệu là rất lớn. |
| Knowledge | Người dùng có biết dùng đúng không? | Kém. Họ thường đặt câu hỏi quá chung chung, khiến AI không biết nên quét biểu đồ nào. |
| Ability | Người dùng có đủ access, thời gian, kỹ năng không? | Tốt. Giao diện dạng Chatbot/Upload file rất phổ biến. |
| Reinforcement | Có cơ chế khiến họ quay lại dùng không? | Rủi ro rất cao. Nếu AI "ảo giác" (hallucinate) số liệu trong 1-2 lần đầu, họ sẽ mất niềm tin hoàn toàn và rời bỏ sản phẩm. |

**Barrier chính:**  

Reinforcement (Sự củng cố niềm tin & Gắn bó): 
Rào cản lớn nhất của RAG đa phương thức là "Trust" (Niềm tin). Nếu người dùng trải nghiệm sự sai lệch (ảo giác) giữa số liệu trên biểu đồ và câu trả lời của AI mà không có cách nào kiểm chứng nhanh chóng, họ sẽ lập tức quay lại cách đọc PDF truyền thống và không bao giờ dùng lại tool.

## A.5 3 Tactic Áp Dụng

| Tactic | Nhắm vào barrier nào? | Áp dụng cho quy trình nào? | Người phụ trách (Role) | Khi nào hoàn thành? |
| --- | --- | --- | --- | --- |
| 1. Thiết kế tính năng **"Click-to-Highlight Citations"** (Click vào nguồn, UI tự động cuộn và bôi sáng biểu đồ/text trong PDF gốc). | Reinforcement (Trust) | Quy trình 3 (Tổng hợp câu trả lời) | Product Manager / Dev | Tuần 2, Tháng 6/2026 |
| 2. Cung cấp **"Prompt Templates"** (Gợi ý sẵn các mẫu câu hỏi tối ưu cho việc truy vấn biểu đồ) ngay màn hình trống. | Knowledge | Quy trình 2 (Truy vấn) | Business Analyst | Tuần 4, Tháng 5/2026 |
| 3. Tính năng **"Báo cáo sai lệch (Thumbs up/down)"** đính kèm lý do để thu thập phản hồi, cải thiện chất lượng truy xuất. | Reinforcement (Trust) | Quy trình 3 (Tổng hợp câu trả lời) | BA / QA | Tuần 3, Tháng 6/2026 |

# B. Dashboard Đo ROI Của Sản Phẩm

## B.1 Chỉ Số Toàn Sản Phẩm (PapeBreak)

| Lớp đo | Chỉ số | Mốc hiện tại | Mục tiêu | Nguồn dữ liệu | Người phụ trách | Rủi ro từ phản biện | Sửa ở v2 |
| --- | --- | --- | --- | --- | --- | --- | --- |
| **Activation** | % người dùng mới upload thành công 1 PDF và nhận được câu trả lời đầu tiên mà không báo lỗi. | 0% | > 60% | Mixpanel: Phễu `upload_doc` -> `receive_first_answer` | Product Manager | Tính cả các PDF quá đơn giản (chỉ có text) làm số liệu đẹp ảo, bỏ qua cốt lõi Multimodal RAG. | Tách phễu đo lường riêng cho nhóm "PDF có chứa hình ảnh/biểu đồ". |
| **Retention / Value** | % người dùng quay lại sử dụng công cụ ít nhất 2 lần trong 7 ngày (W1 Retention). | 0% | > 30% | Amplitude: `active_user_weekly` event `ask_query` | Product Manager | Chu kỳ nghiên cứu/học tập có tính thời vụ (seasonality), đo theo tuần có thể người dùng drop-off tự nhiên do hết project. | Đổi thành đo Retention theo "Session/Batch tài liệu" (số lần hỏi lại trong cùng 1 bộ PDF). |
| **Trust** | Tỷ lệ phản hồi bị report sai số liệu / ảo giác (Hallucination Report Rate). | N/A | < 5% | DB Logs: Lượt bấm Thumbs down có gắn tag `Sai số liệu/nguồn`. | Business Analyst | Người dùng thấy sai nhưng lười report, chỉ lẳng lặng tắt app, khiến tỷ lệ ảo giác đo được thấp hơn thực tế. | Bổ sung framework đo lường tự động ngầm bên dưới (như RAGAS) để đối chiếu Output với PDF gốc. |

---

## B.2 Chỉ Số Theo Từng Quy Trình

### Quy trình 1 — Xử lý & Phân tích tài liệu đầu vào (Upload & Parse PDF)

| Lớp đo | Chỉ số | Mốc hiện tại | Mục tiêu | Nguồn dữ liệu | Người phụ trách | Rủi ro từ phản biện | Sửa ở v2 |
| --- | --- | --- | --- | --- | --- | --- | --- |
| **Activation** | Tỷ lệ PDF được bóc tách và phân loại thành công (không bị timeout/crash). | 0% | > 95% | Server Telemetry: `parse_status_success` | Backend Lead | Có thể bóc tách thành công nhưng layout ảnh bị nát, system vẫn báo `success`. | Đo thêm tỷ lệ độ phân giải ảnh/biểu đồ sau khi crop tự động. |
| **Productivity** | Thời gian trung bình để hệ thống xử lý xong 1 file PDF tiêu chuẩn (dưới 50 trang). | N/A | < 45 giây | APM (Datadog/New Relic) | Product Manager | User chờ 45s nhìn màn hình loading tĩnh sẽ có cảm giác rất lâu và bỏ đi. | V2 không đo tổng thời gian, mà đo "Time-to-first-page-parsed" (cho user hỏi ngay trang 1 trong lúc chờ parse trang sau). |
| **Quality** | Tỷ lệ người dùng phải kích hoạt tính năng "Chủ động khoanh vùng lại biểu đồ" (Manual Crop). | 100% (thủ công) | < 15% | Mixpanel: Event `manual_crop_triggered` | Business Analyst | Đo số lượng lượt crop chưa đủ, vì 1 file PDF lỗi layout có thể khiến user phải crop tay chục lần. | Đo "Tỷ lệ file PDF cần can thiệp thủ công" thay vì số lượt can thiệp. |
| **Value** | Tỷ lệ tài liệu sau khi tải lên bị xóa ngay trong vòng 5 phút đầu tiên. | 0% | < 5% | DB `doc_deleted_timestamp` | Business Analyst | User xóa do up nhầm file, không phải do hệ thống bóc tách kém. | Phân loại event xóa: "Xóa trước khi hỏi" (up nhầm) và "Xóa ngay sau câu hỏi đầu tiên" (bóc tách kém). |

### Quy trình 2 — Truy vấn thông tin (Querying)

| Lớp đo | Chỉ số | Mốc hiện tại | Mục tiêu | Nguồn dữ liệu | Người phụ trách | Rủi ro từ phản biện | Sửa ở v2 |
| --- | --- | --- | --- | --- | --- | --- | --- |
| **Activation** | Tỷ lệ người dùng nhấp chọn sử dụng các "Prompt Templates" được gợi ý sẵn. | 0% | > 40% | Mixpanel: `prompt_template_clicked` | UI/UX Designer | Click nhiều nhưng sinh ra câu hỏi không trúng ý, dẫn đến tỷ lệ đổi câu hỏi cao. | Đo tỷ lệ "Click template và không sửa lại nội dung prompt trước khi gửi". |
| **Engagement** | Số lượng câu hỏi trung bình được tạo ra trên mỗi tài liệu PDF tải lên. | 0 | > 4 câu/file | Database: `query_count_per_doc` | Product Manager | File ngắn thì ít câu hỏi, file dài thì nhiều, dùng trung bình chung sẽ bị lệch. | Phân khúc chỉ số này theo độ dài file (PDF < 10 trang vs PDF > 50 trang). |
| **Productivity** | Tỷ lệ truy vấn trả về kết quả rỗng ("Tôi không tìm thấy thông tin..."). | N/A | < 10% | DB Logs: `null_response_rate` | Business Analyst | Result không rỗng nhưng AI trả lời vòng vo, chung chung, user vẫn không có câu trả lời. | Áp dụng LLM-as-a-judge để chấm điểm độ chi tiết của câu trả lời. |
| **Value** | Tỷ lệ người dùng click vào thẻ Nguồn (Citation Click-through-rate). | 0% | > 35% | Mixpanel: `citation_clicked` | Business Analyst | Click vào nguồn chỉ chứng tỏ họ đang tò mò, chưa chắc là họ thấy giá trị. | Đo "Thời gian lưu lại trên cửa sổ pop-up hiển thị nguồn" (Dwell time trên citation). |

### Quy trình 3 — Tổng hợp câu trả lời đa phương thức (Answering)

| Lớp đo | Chỉ số | Mốc hiện tại | Mục tiêu | Nguồn dữ liệu | Người phụ trách | Rủi ro từ phản biện | Sửa ở v2 |
| --- | --- | --- | --- | --- | --- | --- | --- |
| **Productivity** | Thời gian xuất hiện chữ đầu tiên (Time to First Token - TTFT) kết hợp render xong hình ảnh đính kèm. | N/A | < 4 giây | System Telemetry (Frontend) | Tech Lead | Tốc độ nhanh nhưng chất lượng hình ảnh render bị mờ do nén dung lượng, ảnh hưởng trải nghiệm đọc. | Cần thêm chỉ số báo cáo lỗi mờ ảnh từ phía người dùng. |
| **Quality** | Tỷ lệ sử dụng nút "Regenerate" (Tạo lại) hoặc gửi ngay prompt đính chính phía sau. | N/A | < 20% | Mixpanel: Event `regenerate_click` & `follow_up_prompt` | Business Analyst | Tỷ lệ regenerate thấp có thể do user thất vọng và bỏ đi luôn, chứ không phải do chất lượng lần đầu tốt. | Cross-check chỉ số này với tỷ lệ Drop-off (thoát trang) ngay sau câu trả lời đầu tiên. |
| **Trust** | Tỷ lệ câu trả lời được người dùng sử dụng nút "Copy to Clipboard" hoặc "Export". | 0% | > 25% | Frontend: `copy_clicked`, `export_clicked` | Product Manager | User copy câu trả lời chứa ảo giác mang đi xài thẳng mà không đối chiếu, gây hậu quả. | Khi copy, hệ thống tự động copy kèm theo citation (nguồn trích dẫn) để hạn chế rủi ro cho người dùng cuối. |
| **Value** | Điểm CSAT (Thumbs up/down) tính riêng trên các câu trả lời có trích xuất số liệu biểu đồ. | N/A | > 85% tích cực | Database: `feedback_score_filtered` | Product Manager | Lượng user để lại feedback quá ít (dưới 5%) khiến mẫu dữ liệu không mang tính đại diện. | Tích hợp các pop-up micro-survey (VD: "Hình ảnh này có đúng biểu đồ bạn cần tìm không?") vào UI. |

# C. Dashboard Mock

```text
┌────────────────────────────────────┐ ┌────────────────────────────────────┐
│ TILE 1: PRODUCT HEALTH             │ │ TILE 2: WF1 - UPLOAD & PARSE       │
│ Metric: W1 Retention Rate (Tỷ lệ   │ │ Metric: Tỷ lệ bóc tách PDF không   │
│         user quay lại dùng)        │ │         cần user crop biểu đồ tay  │
│ Current: 15%    Target: > 30%      │ │ Current: 65%    Target: > 85%      │
│ Status: RED                        │ │ Status: AMBER                      │
│ Action if red: Phỏng vấn sâu nhóm  │ │ Action if red: Review lại module   │
│ user rời bỏ, xác định nguyên nhân  │ │ Vision nhận diện layout, thêm      │
│ do AI ảo giác hay UI/UX khó dùng.  │ │ guideline chuẩn bị file PDF.       │
└────────────────────────────────────┘ └────────────────────────────────────┘

┌────────────────────────────────────┐ ┌────────────────────────────────────┐
│ TILE 3: WF2 - QUERY & ANSWER       │ │ TILE 4: TRUST / QUALITY            │
│ Metric: Citation CTR (Tỷ lệ user   │ │ Metric: Hallucination Report Rate  │
│         click vào thẻ Nguồn/Link)  │ │         (Tỷ lệ báo cáo sai số liệu)│
│ Current: 40%    Target: > 35%      │ │ Current: 8%     Target: < 5%       │
│ Status: GREEN                      │ │ Status: AMBER                      │
│ Action if red: Tinh chỉnh UI làm   │ │ Action if red: Tạm dừng tính năng, │
│ nổi thẻ Citation, rà soát lỗi link │ │ rollback model LLM, kiểm tra lại   │
│ dẫn đến trang PDF bị trắng/hỏng.   │ │ pipeline trích xuất bảng biểu.     │
└────────────────────────────────────┘ └────────────────────────────────────┘

┌────────────────────────────────────┐ ┌────────────────────────────────────┐
│ TILE 5: VALUE / COVERAGE           │ │ TILE 6: DECISION                   │
│ Metric: Điểm CSAT cho các câu hỏi  │ │ Continue / Pivot / Kill: PIVOT     │
│         chứa số liệu từ biểu đồ    │ │ Metric mạnh nhất: Hallucination    │
│ Current: 75%    Target: > 85%      │ │                   Report Rate      │
│ Status: RED                        │ │ Before scale: Giảm ảo giác < 5%    │
│ Action if red: Bổ sung Prompt      │ │               & Tối ưu tính năng   │
│ Template hướng dẫn user cách đặt   │ │               trích xuất biểu đồ.  │
│ câu hỏi hẹp và rõ ràng hơn.        │ │ Người phụ trách: Product Manager   │
└────────────────────────────────────┘ └────────────────────────────────────┘
```

# Memo Quyết Định Cuối

Khuyến nghị: Pivot (Đổi hướng). Dừng việc dồn nguồn lực tối ưu tốc độ xử lý hàng loạt file PDF, chuyển hướng (pivot) sang tập trung hoàn thiện tính năng trích xuất biểu đồ phức tạp và cơ chế "Click-to-Highlight" nguồn để cứu vãn niềm tin người dùng. Metric mạnh nhất bảo vệ quyết định này không phải là "AI bóc tách file trong 45 giây", mà là tỷ lệ báo cáo ảo giác (Hallucination Report Rate) đang ở mức cao (8%) — minh chứng rõ nhất cho việc chúng ta phải ưu tiên tuyệt đối cho Trust và Quality thay vì Productivity.