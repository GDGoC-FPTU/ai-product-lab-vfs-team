# 🔍 Phase 1 — SCAN (Cá nhân, 20 min)

Hãy sử dụng **4 Lenses** dưới đây để quét qua hoạt động vận hành của các công ty thành viên Vingroup. Ghi lại **ít nhất 5 bài toán/bottleneck** thực tế.

### 4 Lenses tìm bài toán AI cho Vingroup:
1. **Lặp lại (Repetitive):** Tác vụ lặp đi lặp lại nhiều lần hằng ngày. (Ví dụ: So khớp hóa đơn sạc điện tại VinFast, route lại chuyến taxi tại Xanh SM).
2. **Tốn thời gian (Time-consuming):** Tác vụ ngốn thời gian xử lý thủ công của nhân viên. (Ví dụ: Soạn thảo phản hồi đánh giá 1-star của cư dân Vinhomes).
3. **AI có thể tốt hơn (AI-upgrade):** Dịch vụ khách hàng hiện tại còn chậm hoặc phản hồi rập khuôn. (Ví dụ: Chatbot CSKH Vinpearl hỗ trợ đặt vé vui chơi).
4. **Pain từ người khác (Stakeholder Pain):** Bottleneck khiến khách hàng hoặc nhân viên thực địa phàn nàn. (Ví dụ: Tài xế Xanh SM phàn nàn về việc hệ thống gợi ý điểm đón khách không chính xác).

> [!TIP]
> **🤖 AI Prompts — Partner brainstorm:**
> Hãy sử dụng prompt sau để brainstorm các bài toán thực tế nếu bạn chưa có ý tưởng:
> *"Tôi là AI Engineer tại Vin Smart Future (Vingroup). Tôi đang tìm kiếm các pain point vận hành cụ thể có thể tối ưu bằng AI cho mảng [Chọn một: VinFast / Xanh SM / Vinhomes / Vinmec]. Hãy gợi ý cho tôi 5 quy trình nghiệp vụ thủ công, tốn nhiều thời gian và gây rò rỉ hiệu suất kèm con số thống kê ước tính về tổn thất."*

### 📝 List bài toán của tôi:
| # | Subsidiary (VinFast/Xanh SM...) | Lens | Mô tả ngắn bài toán |
|---|----------------------------------|------|---------------------|
| 1 |
CSKH cư dân: phân loại ticket, phản hồi khiếu nại, review 1-star
Mỗi ngày nhận ticket về thang máy, nước, điện, gửi xe, tiếng ồn, an ninh, phí dịch vụ. Nhiều nội dung lặp lại.
Nhân viên phải đọc, phân loại, tra lịch sử căn hộ, soạn phản hồi, chuyển đúng bộ phận.
AI agent có thể đọc nội dung, xác định intent, mức độ khẩn cấp, soạn phản hồi cá nhân hóa, tự route cho BQL/kỹ thuật/bảo vệ.
Cư dân phàn nàn phản hồi chậm, bị chuyển lòng vòng, trả lời mẫu. Nhân viên CSKH quá tải giờ cao điểm.
| 2 |
Chẩn đoán lỗi xe và xử lý warranty claim tại xưởng dịch vụ(Vinfast)
Lặp lại các bước đọc complaint, DTC, lịch sử sửa chữa, telematics, phụ tùng đã thay, điều kiện bảo hành.
Kỹ thuật viên/service advisor mất thời gian khoanh vùng lỗi, xin phê duyệt bảo hành, viết repair order.
AI service copilot có thể tóm tắt lịch sử xe, gợi ý nguyên nhân, next-best-action, tự soạn warranty claim.
Khách bực vì phải chờ lâu, quay lại nhiều lần. Kỹ thuật viên bị thiếu thông tin hoặc phải hỏi nhiều hệ thống.
| 3 |
Hỗ trợ tài xế: payout, thưởng, phạt, chính sách, tranh chấp chuyến
Tài xế hỏi lặp lại về thưởng tuần, thu nhập, chuyến bị hủy, điểm đón, phiên sạc, vi phạm, hồ sơ.
Nhân viên phải tra nhiều hệ thống: chuyến, ví, payout, chấm công, rule thưởng, biên bản vi phạm.
AI tự động trả lời chính sách, giải thích payout, phát hiện sai lệch, tự tạo ticket escalation có đủ bằng chứng.
Tài xế bức xúc nếu thưởng/thu nhập không rõ; đội vận hành bị kéo vào nhiều case nhỏ nhưng nhạy cảm
| 4 |
Gợi ý điểm đón, matching tài xế-khách, route tới điểm đón
Mỗi chuyến đều phải map điểm đón, tìm tài xế gần nhất, tính ETA, xử lý khách đặt sai cổng/chung cư/sân bay.
Tài xế gọi khách, vòng xe, chờ sai điểm; ops phải xử lý khiếu nại hủy chuyến/đón muộn.
AI geospatial hiểu POI, cổng vào, khu đón hợp lệ; dự báo pickup friction; gợi ý text/hình ảnh điểm đón cho khách và tài xế.
Tài xế phàn nàn điểm đón không chính xác; khách hủy vì tài xế tới sai chỗ hoặc ETA thay đổi.
| 5 |
Theo dõi tiến độ công trường và nghiệm thu khối lượng
Mỗi ngày cập nhật ảnh hiện trường, nhật ký thi công, checklist an toàn, nghiệm thu hạng mục, RFI, change order.
PM/QS phải đối chiếu thủ công giữa hiện trường, bản vẽ, BOQ, BIM, báo cáo nhà thầu.
AI so sánh ảnh/drone/CCTV với BIM/schedule, phát hiện chậm tiến độ, tự tạo báo cáo nghiệm thu sơ bộ, cảnh báo sai lệch khối lượng.
Ban QLDA bị bottleneck nghiệm thu. Nhà thầu phàn nàn thanh toán chậm. Sales/bàn giao bị ảnh hưởng nếu công trường trễ.

---

# 🃏 Phase 2 — QUICK-ASSESS (Cá nhân, 30 min)

Chọn **top 3 bài toán** từ danh sách trên và hoàn thiện **3 Quick Problem Cards** dưới đây (10 phút/card).

```
┌─────────────────────────────────────────────────────────────┐
│ QUICK PROBLEM CARD #_1__                                    │
│                                                             │
│ Bài toán (1 câu): _CSKH cư dân____________________________  │
│ Công ty thành viên: [ ] VinFast  [ ] Xanh SM  [x] Vinhomes  │
│                     [ ] Vinmec   [ ] Khác (Ghi rõ)________  │
│                                                             │
│ Ai đang đau (Actor)? Cư dân phàn nàn phản hồi chậm, nhân viên CSKH quá tải_ │
│                                                             │
│ Workflow thủ công hiện tại (3-5 bước):                      │
│   1. Nhân viên phải đọc ──> 2. tra lịch sử căn hộ ──> 3. phân loại ──> 4. soạn phản hồi  ──> 5.chuyển đúng bộ phận
│                                                             │
│ Bước nào tốn thời gian/lỗi nhất? ___ (⏱ ___ phút/lượt)      │
│ AI có thể nhảy vào hỗ trợ ở bước nào? tra lịch sử căn hộ, phân loại, chuyển đúng bộ phận│
│                                                             │
│ Đo thành công bằng gì (Metric có số)? 
- Giảm thời gian xử lý ticket cấp 1 từ 8-10 phút xuống dưới 2 phút.
- Tự động phân loại đúng ≥85-90% ticket phổ biến.
- Giảm ≥30% ticket bị chuyển sai bộ phận.                      │
│                                                             │
│ Quick Architecture: [ ] No AI  [ ] Rule  [ ] LLM  [x] Agent │
└─────────────────────────────────────────────────────────────┘


┌─────────────────────────────────────────────────────────────┐
│ QUICK PROBLEM CARD #_2__                                    │
│                                                             │
│ Bài toán (1 câu): _CSKH cư dân____________________________  │
│ Công ty thành viên: [X] VinFast  [ ] Xanh SM  [] Vinhomes  │
│                     [ ] Vinmec   [ ] Khác (Ghi rõ)________  │
│                                                             │
│ Ai đang đau (Actor)? Khách hàng phàn nàn phải chờ lâu hoặc quay lại nhiều lần; kỹ thuật viên/service advisor mất thời gian tra cứu lỗi, lịch sử sửa chữa và điều kiện bảo hành.│
│                                                             │
│ Workflow thủ công hiện tại (3-5 bước):                      │
│   1. Service advisor đọc mô tả lỗi của khách hàng
     ──> 2. Kỹ thuật viên kiểm tra xe, đọc DTC/log và lịch sử sửa chữa
     ──> 3. Đối chiếu điều kiện bảo hành, phụ tùng đã thay, campaign/recall nếu có
     ──> 4. Soạn warranty claim kèm bằng chứng, ảnh, log, repair order
     ──> 5. Gửi phê duyệt và chờ phản hồi trước khi sửa/thay thế
│                                                             │
│ Bước nào tốn thời gian/lỗi nhất? Ước tính 20-45 phút/lượt claim     │
│ AI có thể nhảy vào hỗ trợ ở bước nào?
- Tóm tắt complaint của khách và lịch sử sửa chữa theo VIN.
- Đọc DTC/log/telematics và gợi ý nguyên nhân khả dĩ.
- Đề xuất checklist kiểm tra tiếp theo cho kỹ thuật viên.
- Kiểm tra điều kiện bảo hành/campaign/recall.
- Tự tạo draft warranty claim với bằng chứng cần nộp.│
│                                                             │
│ Đo thành công bằng gì (Metric có số)? 
- Giảm thời gian chuẩn bị warranty claim từ 30-45 phút xuống dưới 10 phút.
- Giảm tỷ lệ claim bị trả về do thiếu hồ sơ ≥30%.                    │
│                                                             │
│ Quick Architecture: [ ] No AI  [ ] Rule  [ ] LLM  [x] Agent │
└─────────────────────────────────────────────────────────────┘


┌─────────────────────────────────────────────────────────────┐
│ QUICK PROBLEM CARD #_3__                                    │
│                                                             │
│ Bài toán (1 câu): _CSKH cư dân____________________________  │
│ Công ty thành viên: [ ] VinFast  [x] Xanh SM  [] Vinhomes  │
│                     [ ] Vinmec   [ ] Khác (Ghi rõ)________  │
│                                                             │
│ Ai đang đau (Actor)? Cư dân phàn nàn phản hồi chậm, nhân viên CSKH quá tải_ │
│                                                             │
│ Workflow thủ công hiện tại (3-5 bước):                      │
│   1. Tài xế gửi câu hỏi/khiếu nại qua app, hotline hoặc nhóm hỗ trợ
     ──> 2. Nhân viên đọc nội dung và xác định loại vấn đề: payout, thưởng, phạt, chuyến hủy, sạc, hồ sơ
     ──> 3. Tra dữ liệu chuyến, ví tài xế, chính sách thưởng/phạt, lịch sử hỗ trợ
     ──> 4. Soạn phản hồi hoặc giải thích chi tiết cho tài xế
     ──> 5. Chuyển escalation cho bộ phận vận hành/finance/risk nếu có tranh chấp
│                                                             │
│ Bước nào tốn thời gian/lỗi nhất? 
    Bước 3-4: tra nhiều hệ thống để giải thích payout/thưởng/phạt và soạn phản hồi rõ ràng.     
    Ước tính 5-15 phút/lượt hỏi│
│ AI có thể nhảy vào hỗ trợ ở bước nào? │
│- Đọc và phân loại câu hỏi/khiếu nại của tài xế.
 - Tra lịch sử chuyến, payout, ví, bonus, penalty, phiên sạc nếu được cấp quyền.
 - Giải thích công thức tính thưởng/phạt bằng ngôn ngữ dễ hiểu.
 - Soạn phản hồi cá nhân hóa kèm bằng chứng chuyến/khung giờ/chính sách.
 - Tự tạo ticket escalation với đủ dữ liệu cho finance/ops/risk                                                │
│ Đo thành công bằng gì (Metric có số)? 
- Giảm thời gian xử lý câu hỏi tài xế từ 10-15 phút xuống dưới 3 phút.
- Tự động trả lời ≥60-70% câu hỏi phổ biến không cần agent.
- Giảm ≥30% ticket bị chuyển sai bộ phận.
- Giảm ≥20% số case tài xế hỏi lại cùng một vấn đề.                     │
│                                                             │
│ Quick Architecture: [ ] No AI  [ ] Rule  [X] LLM  [ ] Agent │
└─────────────────────────────────────────────────────────────┘
```

> [!TIP]
> **🤖 AI Prompts — Stress-Test thẻ bài toán:**
> Hãy dán nội dung thẻ bài toán của bạn vào LLM để nhận phản biện:
> *"Đây là một thẻ bài toán vận hành tôi đề xuất cho Vin Smart Future: [Dán nội dung]. Hãy đóng vai trò là một CFO và Trưởng phòng Vận hành cực kỳ khắt khe, chỉ ra cho tôi 3 điểm yếu về logic, metric, và giải thích vì sao rule-based code thông thường có thể giải quyết bài toán này tốt hơn là dùng AI."*

---