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
| 1 | VinFast | Lặp lại (Repetitive) | Kiểm tra chất lượng cuối dây chuyền dựa vào checklist thủ công và quan sát kỹ thuật viên, dễ bỏ sót lỗi nhỏ và tạo vòng lặp rework; benchmark ngành cho thấy chi phí scrap & rework ngốn ~2,2% doanh thu/năm — hàng chục triệu USD với OEM doanh thu tỉ đô. |
| 2 | VinFast | Pain từ người khác (Stakeholder Pain) | Bảo trì nặng tính "chữa cháy" (chờ hỏng rồi sửa) gây dừng máy ngoài kế hoạch trên dây chuyền hàn-sơn-lắp ráp; downtime ngoài kế hoạch bốc hơi ~11% doanh thu/năm, chi phí trung bình 129 triệu USD/năm/nhà máy, riêng ngành ô tô mất ~2,3 triệu USD/giờ dừng sản xuất. |
| 3 | VinFast | Tốn thời gian (Time-consuming) | Xử lý claim bảo hành EV (pin, powertrain) dựa vào đọc hồ sơ và tra cứu rời rạc, vòng đời xử lý dài; chi phí claim bảo hành EV cao hơn xe xăng 26–50%, thay pin toàn bộ tốn ~8.000–12.000 GBP/xe, tỉ lệ thay pack ~1–2% nhưng tổn thất rất lớn nếu không phát hiện sớm. |
| 4 | VinFast | AI có thể tốt hơn (AI-upgrade) | Tổng đài/chat CSKH xử lý nhiều câu hỏi lặp bằng script rập khuôn và tra cứu thủ công; AHT trung bình 4–7 phút/cuộc (chuẩn ~6 phút 10 giây), tỉ lệ gọi lại cùng vấn đề 10–15%, kéo chi phí nhân sự tăng và CSAT giảm nếu không dùng AI agent & routing thông minh. |
| 5 | VinFast | Lặp lại (Repetitive) | Kiểm tra xe trước bàn giao (PDI), bảo dưỡng định kỳ và sau sửa chữa theo checklist thao tác lặp, nhập liệu rời rạc; phiên kiểm tra kéo dài 30–60 phút/xe, nghiên cứu cho thấy có thể cắt ~18 phút/xe nếu chuẩn hóa — hàng nghìn giờ công/tháng đang bị "chôn" vào thao tác mà AI/vision có thể tự động hóa. |

---

# 🃏 Phase 2 — QUICK-ASSESS (Cá nhân, 30 min)

Chọn **top 3 bài toán** từ danh sách trên và hoàn thiện **3 Quick Problem Cards** dưới đây (10 phút/card).

```
┌─────────────────────────────────────────────────────────────┐
│ QUICK PROBLEM CARD #___                                     │
│                                                             │
│ Bài toán (1 câu): ________________________________________  │
│ Công ty thành viên: [ ] VinFast  [ ] Xanh SM  [ ] Vinhomes  │
│                     [ ] Vinmec   [ ] Khác (Ghi rõ)________  │
│                                                             │
│ Ai đang đau (Actor)? ______________________________________ │
│                                                             │
│ Workflow thủ công hiện tại (3-5 bước):                      │
│   1. ___ ──> 2. ___ ──> 3. ___ ──> 4. ___                   │
│                                                             │
│ Bước nào tốn thời gian/lỗi nhất? ___ (⏱ ___ phút/lượt)      │
│ AI có thể nhảy vào hỗ trợ ở bước nào? _____________________ │
│                                                             │
│ Đo thành công bằng gì (Metric có số)? ______________________ │
│   VD: "Giảm thời gian soạn phản hồi từ 10 min ──> under 2 min"│
│                                                             │
│ Quick Architecture: [ ] No AI  [ ] Rule  [ ] LLM  [ ] Agent │
└─────────────────────────────────────────────────────────────┘
```

> [!TIP]
> **🤖 AI Prompts — Stress-Test thẻ bài toán:**
> Hãy dán nội dung thẻ bài toán của bạn vào LLM để nhận phản biện:
> *"Đây là một thẻ bài toán vận hành tôi đề xuất cho Vin Smart Future: [Dán nội dung]. Hãy đóng vai trò là một CFO và Trưởng phòng Vận hành cực kỳ khắt khe, chỉ ra cho tôi 3 điểm yếu về logic, metric, và giải thích vì sao rule-based code thông thường có thể giải quyết bài toán này tốt hơn là dùng AI."*

---