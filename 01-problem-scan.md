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
| 1 | VinFast | Tốn thời gian | Dự báo thiếu hụt vật tư sản xuất (MRP) để tự động kích hoạt lệnh mua hàng, giảm thời gian chết của dây chuyền. |
| 2 | Xanh SM | Pain từ người khác | Nhận diện mạng lưới trục lợi cuốc xe ảo (Fraud Detection) qua đồ thị tương tác giữa tài xế và khách hàng. |
| 3 | Vinhomes | Lặp lại | Tự động phân loại và định tuyến hàng nghìn ticket yêu cầu/phàn nàn của cư dân trên App về đúng bộ phận phụ trách. |
| 4 | Vinmec | AI có thể tốt hơn | Trích xuất thực thể (NER) và số hóa tự động các chỉ số từ phiếu xét nghiệm giấy đổ thẳng vào hệ thống hồ sơ bệnh án điện tử (HIS). |
| 5 | Vincom Retail | Lặp lại | Phân cụm hành vi chi tiêu đa kênh của khách hàng (Customer Segmentation) để cá nhân hóa hoàn toàn các voucher khuyến mãi. |
| 6 | Vinhomes | Pain từ người khác | Bảo trì dự đoán (Predictive Maintenance) cho hệ thống lõi (thang máy, trạm bơm) dựa trên dữ liệu cảm biến IoT để ngăn chặn hỏng hóc đột xuất. |
---

# 🃏 Phase 2 — QUICK-ASSESS (Cá nhân, 30 min)

Chọn **top 3 bài toán** từ danh sách trên và hoàn thiện **3 Quick Problem Cards** dưới đây (10 phút/card).

```
┌─────────────────────────────────────────────────────────────┐
│ QUICK PROBLEM CARD #1                                       │
│                                                             │
│ Bài toán (1 câu): Nhận diện mạng lưới trục lợi cuốc xe ảo   │
│ qua phân tích đồ thị tương tác tài xế - khách hàng.         │
│ Công ty thành viên: [ ] VinFast  [x] Xanh SM  [ ] Vinhomes  │
│                     [ ] Vinmec   [ ] Khác (Ghi rõ)________  │
│                                                             │
│ Ai đang đau (Actor)? Bộ phận chống gian lận (Risk) & Tài xế │
│                                                             │
│ Workflow thủ công hiện tại (3-5 bước):                      │
│   1. Nhận alert rule tĩnh ──> 2. Kéo log chuyến đi ──>      │
│   3. Kẻ bảng pivot dò trùng IP/Device ──> 4. Khóa tài khoản │
│                                                             │
│ Bước nào tốn thời gian/lỗi nhất? Bước 3 ( 45 phút/lượt)     │
│ AI có thể nhảy vào hỗ trợ ở bước nào? Dùng Graph Models quét│
│ tự động toàn bộ mạng lưới và chấm điểm rủi ro real-time.    │
│                                                             │
│ Đo thành công bằng gì (Metric có số)?                       │
│   "Giảm thời gian rà soát từ 45 min ──> under 5 min/case"   │
│                                                             │
│ Quick Architecture: [ ] No AI  [ ] Rule  [ ] LLM  [x] ML    │
└─────────────────────────────────────────────────────────────┘
```
┌─────────────────────────────────────────────────────────────┐
│ QUICK PROBLEM CARD #2                                       │
│                                                             │
│ Bài toán (1 câu): Dự báo nhu cầu vật tư (MRP) để tự động    │
│ kích hoạt lệnh mua hàng (PO), tránh dừng chuyền sản xuất.   │
│ Công ty thành viên: [x] VinFast  [ ] Xanh SM  [ ] Vinhomes  │
│                     [ ] Vinmec   [ ] Khác (Ghi rõ)________  │
│                                                             │
│ Ai đang đau (Actor)? Nhân viên Mua hàng & Quản lý Kho       │
│                                                             │
│ Workflow thủ công hiện tại (3-5 bước):                      │
│   1. Kéo tồn kho ERP ──> 2. Khớp lệnh sản xuất ──>          │
│   3. Tính lượng vật tư thiếu ──> 4. Lên nháp PO trình ký    │
│                                                             │
│ Bước nào tốn thời gian/lỗi nhất? Bước 2&3 ( 120 phút/lượt)  │
│ AI có thể nhảy vào hỗ trợ ở bước nào? Phân tích Time-series │
│ dự báo tồn kho tối thiểu và tự động gen nháp lệnh PO.       │
│                                                             │
│ Đo thành công bằng gì (Metric có số)?                       │
│   "Giảm tỷ lệ thiếu hụt linh kiện (Stockout) xuống dưới 1%" │
│                                                             │
│ Quick Architecture: [ ] No AI  [ ] Rule  [ ] LLM  [x] ML    │
└─────────────────────────────────────────────────────────────┘
```
┌─────────────────────────────────────────────────────────────┐
│ QUICK PROBLEM CARD #3                                       │
│                                                             │
│ Bài toán (1 câu): Bảo trì dự đoán hệ thống lõi (thang máy,  │
│ trạm bơm) dựa trên dữ liệu IoT để ngăn hỏng hóc đột xuất.   │
│ Công ty thành viên: [ ] VinFast  [ ] Xanh SM  [x] Vinhomes  │
│                     [ ] Vinmec   [ ] Khác (Ghi rõ)________  │
│                                                             │
│ Ai đang đau (Actor)? Ban quản lý tòa nhà, Kỹ sư trưởng      │
│                                                             │
│ Workflow thủ công hiện tại (3-5 bước):                      │
│   1. Cư dân báo lỗi ──> 2. Phân công thợ ──> 3. Kiểm tra    │
│   chẩn đoán tại chỗ ──> 4. Dừng hoạt động để sửa chữa       │
│                                                             │
│ Bước nào tốn thời gian/lỗi nhất? Bước 3 ( 60 phút/lượt)     │
│ AI có thể nhảy vào hỗ trợ ở bước nào? Cảnh báo bất thường   │
│ (Anomaly Detection) trước 24h dựa trên luồng data cảm biến. │
│                                                             │
│ Đo thành công bằng gì (Metric có số)?                       │
│   "Giảm downtime của thiết bị lõi từ 4h/tháng ──> <1h/tháng"│
│                                                             │
│ Quick Architecture: [ ] No AI  [ ] Rule  [ ] LLM  [x] ML    │
└─────────────────────────────────────────────────────────────┘
```

> [!TIP]
> **🤖 AI Prompts — Stress-Test thẻ bài toán:**
> Hãy dán nội dung thẻ bài toán của bạn vào LLM để nhận phản biện:
> *"Đây là một thẻ bài toán vận hành tôi đề xuất cho Vin Smart Future: [Dán nội dung]. Hãy đóng vai trò là một CFO và Trưởng phòng Vận hành cực kỳ khắt khe, chỉ ra cho tôi 3 điểm yếu về logic, metric, và giải thích vì sao rule-based code thông thường có thể giải quyết bài toán này tốt hơn là dùng AI."*

---