# Phase 1 — SCAN (Cá nhân, 20 min)

### List bai toan cua toi:
| # | Subsidiary (VinFast/Xanh SM...) | Lens | Mô tả ngắn bài toán |
|---|----------------------------------|------|---------------------|
| 1 | Vinhomes | Pain từ người khác (Stakeholder Pain) | CSKH cư dân: phân loại ticket & phản hồi khiếu nại. Mỗi ngày nhận ticket về thang máy, nước, điện, gửi xe, tiếng ồn, an ninh, phí dịch vụ — nhiều nội dung lặp. Nhân viên phải đọc, phân loại, tra lịch sử căn hộ, soạn phản hồi, chuyển đúng bộ phận. Cư dân phàn nàn phản hồi chậm, bị chuyển lòng vòng, trả lời mẫu; nhân viên CSKH quá tải giờ cao điểm. AI agent có thể đọc intent, xác định mức khẩn cấp, soạn phản hồi cá nhân hóa, tự route cho BQL/kỹ thuật/bảo vệ. |
| 2 | VinFast | Tốn thời gian (Time-consuming) | Chẩn đoán lỗi xe & xử lý warranty claim tại xưởng dịch vụ. Kỹ thuật viên/service advisor lặp lại các bước đọc complaint, DTC, lịch sử sửa chữa, telematics, phụ tùng đã thay, điều kiện bảo hành — mất nhiều thời gian khoanh vùng lỗi, xin phê duyệt, viết repair order. Chi phí claim EV cao hơn xe xăng 26–50%, thay pin toàn bộ tốn ~8.000–12.000 GBP/xe. Khách bực vì chờ lâu, quay lại nhiều lần. AI service copilot tóm tắt lịch sử xe, gợi ý nguyên nhân, next-best-action, tự soạn warranty claim. |
| 3 | Xanh SM | Lặp lại (Repetitive) | Hỗ trợ tài xế: payout, thưởng, phạt, chính sách, tranh chấp chuyến. Tài xế hỏi lặp lại về thưởng tuần, thu nhập, chuyến bị hủy, điểm đón, phiên sạc, vi phạm, hồ sơ. Nhân viên phải tra nhiều hệ thống: chuyến, ví, payout, chấm công, rule thưởng, biên bản vi phạm. Tài xế bức xúc nếu thưởng/thu nhập không rõ; đội vận hành bị kéo vào nhiều case nhỏ nhưng nhạy cảm. AI tự động trả lời chính sách, giải thích payout, phát hiện sai lệch, tự tạo ticket escalation có đủ bằng chứng. |
| 4 | VinFast | Lặp lại (Repetitive) | Kiểm tra chất lượng cuối dây chuyền & rework. Kiểm tra dựa vào checklist thủ công và quan sát kỹ thuật viên, dễ bỏ sót lỗi nhỏ và tạo vòng lặp rework; benchmark ngành cho thấy chi phí scrap & rework ngốn ~2,2% doanh thu/năm — hàng chục triệu USD với OEM doanh thu tỉ đô. AI thị giác máy tính và phân tích lỗi theo thời gian thực có thể phát hiện sớm và giảm rework. |
| 5 | VinFast | AI có thể tốt hơn (AI-upgrade) | CSKH tổng đài & kênh hỗ trợ. Tổng đài/chat xử lý nhiều câu hỏi lặp (tình trạng xe, lịch bảo dưỡng, lỗi app, chính sách pin) bằng script rập khuôn và tra cứu thủ công; AHT trung bình 4–7 phút/cuộc (chuẩn ~6 phút 10 giây), tỉ lệ gọi lại cùng vấn đề 10–15%, kéo chi phí nhân sự tăng và CSAT giảm. AI agent, routing thông minh và gợi ý next-best-action dựa trên ngữ cảnh có thể giảm AHT 40–60%. |
| 6 | Xanh SM | Tốn thời gian (Time-consuming) | Điều phối sạc khẩn cấp & cứu hộ xe điện (EV Emergency Dispatch) khi pin của tài xế dưới 5%. Quy trình thủ công: tài xế gọi báo hết pin, điều phối kiểm tra vị trí xe, tìm xe sạc lưu động rảnh, gọi điện xác nhận, tạo lệnh điều xe. Mất 15-20 phút phản hồi, dễ gây rò rỉ cơ hội sạc cứu hộ kịp thời, xe chết máy giữa đường gây tắc nghẽn và tốn chi phí kéo xe (~1-2 triệu VND/lượt). AI agent tự động phân tích GPS, pin từ telematics, định tuyến xe sạc di động gần nhất và tự động dispatch lệnh trong <30 giây. |
| 7 | Vinmec | Tốn thời gian (Time-consuming) | Tóm tắt bệnh án & hỗ trợ bác sĩ kê đơn thuốc (Clinical Documentation & Prescription Copilot). Bác sĩ mất trung bình 3-4 giờ/ngày để nhập liệu bệnh án điện tử (EHR) và ghi chép lâm sàng thủ công sau mỗi ca khám. Điều này làm giảm thời gian tương tác trực tiếp với bệnh nhân và tăng nguy cơ sai sót y khoa khi kê đơn thuốc chống chỉ định (tỷ lệ lỗi kê đơn nói chung khoảng 5-10%). AI copilot lắng nghe cuộc hội thoại y khoa (ambient AI), tự động cấu trúc hóa bệnh án chuẩn SOAP, và cảnh báo chống chỉ định kê đơn theo thời gian thực giúp giảm 50% thời gian giấy tờ. |
| 8 | Vinhomes | AI có thể tốt hơn (AI-upgrade) | Quản lý năng lượng & phát hiện bất thường tòa nhà (Smart Building Energy & Anomaly Detection). Hệ thống quản lý tòa nhà (chiller, điều hòa sảnh, chiếu sáng công cộng) vận hành theo lịch cứng bất kể mật độ cư dân hay thời tiết thực tế, gây lãng phí năng lượng lớn (chiếm đến 40% chi phí vận hành tòa nhà). Việc phát hiện rò rỉ nước hoặc quá tải điện cũng phụ thuộc lịch kiểm tra tuần/tháng. AI phân tích dữ liệu cảm biến IoT thời gian thực, tự động dự báo phụ tải, điều chỉnh tối ưu năng lượng và phát hiện rò rỉ/chập điện ngay lập tức, tiết kiệm 15-25% chi phí năng lượng. |
| 9 | Xanh SM | AI có thể tốt hơn (AI-upgrade) | Phân tích hành vi lái xe & dự báo rủi ro tai nạn (Driver Behavior & Risk Predictive Analytics). Đội ngũ giám sát an toàn phải rà soát thủ công hàng ngàn giờ video dashcam và dữ liệu cảm biến viễn thông (phanh gấp, tăng tốc đột ngột, lệch làn) khi có sự cố xảy ra, dẫn đến phản ứng chậm chạp và không ngăn chặn được tai nạn chủ động. Tỷ lệ va chạm xe dịch vụ cao gây tổn thất lớn về chi phí bảo hiểm và uy tín thương hiệu. AI tự động chấm điểm an toàn lái xe theo thời gian thực (telemetry and cabin video analysis), cảnh báo tài xế mất tập trung và dự báo rủi ro tai nạn chủ động để nhắc nhở, giảm 30% tỷ lệ va chạm. |
| 10 | VinFast | Tốn thời gian (Time-consuming) | Dự báo nhu cầu phụ tùng & tối ưu hóa chuỗi cung ứng linh kiện (Predictive Spare Parts Demand Forecasting). Việc lập kế hoạch phân phối phụ tùng thay thế đến các xưởng dịch vụ toàn cầu dựa trên dự báo thống kê truyền thống, dẫn đến tình trạng mất cân đối nghiêm trọng: thừa những phụ tùng ít hỏng nhưng lại thiếu các linh kiện cốt lõi khiến khách hàng phải đợi sửa chữa từ 2-4 tuần, làm giảm nghiêm trọng CSAT. AI phân tích dữ liệu telematics xe lưu thông, kết hợp lịch sử sửa chữa để dự báo chính xác nhu cầu phụ tùng tại từng khu vực, giảm 20-30% hàng tồn kho dự phòng và rút ngắn 50% thời gian chờ. |

---

# Phase 2 — QUICK-ASSESS (Cá nhân, 30 min)

```
┌─────────────────────────────────────────────────────────────┐
│ QUICK PROBLEM CARD #01                                      │
│                                                             │
│ Bài toán (1 câu): Tự động phân loại ticket phản hồi của cư  │
│ dân Vinhomes để định tuyến chính xác và soạn tin nhắn nháp  │
│ phản hồi cá nhân hóa nhanh chóng.                           │
│ Công ty thành viên: [ ] VinFast  [ ] Xanh SM  [x] Vinhomes  │
│                     [ ] Vinmec   [ ] Khác (Ghi rõ)________  │
│                                                             │
│ Ai đang đau (Actor)? Nhân viên CSKH tại sảnh chung cư       │
│ (Receptionist/Helpdesk Operator).                           │
│                                                             │
│ Workflow thủ công hiện tại (3-5 bước):                      │
│   1. Tiếp nhận phản hồi từ cư dân qua App/Zalo ──>          │
│   2. Đọc và phân loại nội dung thủ công ──>                 │
│   3. Truy cứu lịch sử căn hộ và quy trình BQL ──>           │
│   4. Soạn phản hồi mẫu ──>                                  │
│   5. Chuyển thông tin cho bộ phận kỹ thuật hoặc bảo vệ.     │
│                                                             │
│ Bước nào tốn thời gian/lỗi nhất? Bước 3 & 4 (⏱ 8-10 phút)   │
│ AI có thể nhảy vào hỗ trợ ở bước nào? Bước 2, 3 và 4        │
│ (Phân loại intent và tự động soạn tin phản hồi nháp).       │
│                                                             │
│ Đo thành công bằng gì (Metric có số)? Giảm thời gian        │
│ phản hồi từ 10 phút ──> dưới 2 phút; tăng độ chính xác      │
│ định tuyến từ 70% ──> trên 95%.                             │
│                                                             │
│ Quick Architecture: [ ] No AI  [ ] Rule  [x] LLM  [x] Agent │
└─────────────────────────────────────────────────────────────┘
```

```
┌─────────────────────────────────────────────────────────────┐
│ QUICK PROBLEM CARD #02                                      │
│                                                             │
│ Bài toán (1 câu): Hỗ trợ kỹ thuật viên tổng hợp thông số    │
│ DTC lỗi xe và telematics để tự động soạn hồ sơ yêu cầu      │
│ bảo hành (warranty claim) gửi hãng duyệt.                   │
│ Công ty thành viên: [x] VinFast  [ ] Xanh SM  [ ] Vinhomes  │
│                     [ ] Vinmec   [ ] Khác (Ghi rõ)________  │
│                                                             │
│ Ai đang đau (Actor)? Cố vấn dịch vụ (Service Advisor) và    │
│ Kỹ thuật viên xưởng dịch vụ (Workshop Technician).          │
│                                                             │
│ Workflow thủ công hiện tại (3-5 bước):                      │
│   1. Gặp khách hàng và ghi nhận complaint ──>               │
│   2. Cắm cổng OBD quét mã lỗi DTC ──>                       │
│   3. Tra cứu thủ công lịch sử sửa chữa và hệ thống bảo hành ──>│
│   4. Khoanh vùng lỗi, soạn repair order ──>                 │
│   5. Làm đơn yêu cầu warranty claim gửi lên hãng.           │
│                                                             │
│ Bước nào tốn thời gian/lỗi nhất? Bước 3 & 5 (⏱ 45-60 phút)  │
│ AI có thể nhảy vào hỗ trợ ở bước nào? Bước 3 và 5           │
│ (Đọc DTC/telematics gợi ý lỗi và tự soạn claim nháp).       │
│                                                             │
│ Đo thành công bằng gì (Metric có số)? Giảm thời gian        │
│ soạn warranty claim từ 60 phút ──> dưới 15 phút; giảm tỷ    │
│ lệ claim bị từ chối từ 15% ──> dưới 3%.                     │
│                                                             │
│ Quick Architecture: [ ] No AI  [ ] Rule  [x] LLM  [ ] Agent │
└─────────────────────────────────────────────────────────────┘
```

```
┌─────────────────────────────────────────────────────────────┐
│ QUICK PROBLEM CARD #06                                      │
│                                                             │
│ Bài toán (1 câu): Tự động phát hiện xe điện Xanh SM dưới    │
│ 5% pin qua telemetry để điều phối xe sạc pin di động        │
│ cứu hộ tức thời và tự động định tuyến hướng đi.             │
│ Công ty thành viên: [ ] VinFast  [x] Xanh SM  [ ] Vinhomes  │
│                     [ ] Vinmec   [ ] Khác (Ghi rõ)________  │
│                                                             │
│ Ai đang đau (Actor)? Nhân viên điều phối đội xe (Fleet      │
│ Dispatcher) và tài xế xe điện gặp sự cố hết pin.            │
│                                                             │
│ Workflow thủ công hiện tại (3-5 bước):                      │
│   1. Tài xế gọi tổng đài báo hết pin giữa đường ──>         │
│   2. Điều phối tìm vị trí GPS của xe trên bản đồ ──>        │
│   3. Tra cứu xe sạc lưu động đang rảnh ở gần đó ──>         │
│   4. Gọi điện cho tài xế sạc lưu động để điều xe ──>        │
│   5. Soạn tin nhắn chỉ đường gửi cho tài xế.                │
│                                                             │
│ Bước nào tốn thời gian/lỗi nhất? Bước 2, 3 và 4 (⏱ 15-20 phút)│
│ AI có thể nhảy vào hỗ trợ ở bước nào? Bước 2, 3, 4 và 5     │
│ (Tự lọc GPS/pin từ telemetry, dispatch xe cứu hộ thời       │
│ gian thực).                                                 │
│                                                             │
│ Đo thành công bằng gì (Metric có số)? Giảm thời gian        │
│ điều phối cứu hộ từ 15 phút ──> dưới 30 giây; giảm tỷ lệ    │
│ xe chết máy gây tắc nghẽn xuống 0%.                         │
│                                                             │
│ Quick Architecture: [ ] No AI  [ ] Rule  [ ] LLM  [x] Agent │
└─────────────────────────────────────────────────────────────┘
```

> [!TIP]
> **AI Prompts — Stress-Test the bai toan:**
> Hãy dán nội dung thẻ bài toán của bạn vào LLM để nhận phản biện:
> *"Đây là một thẻ bài toán vận hành tôi đề xuất cho Vin Smart Future: [Dán nội dung]. Hãy đóng vai trò là một CFO và Trưởng phòng Vận hành cực kỳ khắt khe, chỉ ra cho tôi 3 điểm yếu về logic, metric, và giải thích vì sao rule-based code thông thường có thể giải quyết bài toán này tốt hơn là dùng AI."*

---