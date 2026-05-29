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
> _"Tôi là AI Engineer tại Vin Smart Future (Vingroup). Tôi đang tìm kiếm các pain point vận hành cụ thể có thể tối ưu bằng AI cho mảng [Chọn một: VinFast / Xanh SM / Vinhomes / Vinmec]. Hãy gợi ý cho tôi 5 quy trình nghiệp vụ thủ công, tốn nhiều thời gian và gây rò rỉ hiệu suất kèm con số thống kê ước tính về tổn thất."_

### 📝 List bài toán của tôi:

| #   | Subsidiary (VinFast/Xanh SM...) | Lens               | Mô tả ngắn bài toán                                                                                                                                                                                                                                                                                   |
| --- | ------------------------------- | ------------------ | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 1   | Xanh SM                         | Lặp lại            | Điều phối viên xử lý thủ công các cuốc xe bị lỗi ghép tài xế vào giờ cao điểm: phải kiểm tra vị trí xe, pin, trạng thái tài xế và gọi xác nhận từng trường hợp. Ước tính nếu có ~300 case/ngày, mỗi case mất 4-6 phút thì rò rỉ ~20-30 giờ công/ngày và làm tăng hủy chuyến do khách chờ lâu.         |
| 2   | Xanh SM                         | Tốn thời gian      | Tổng hợp lý do khách hủy chuyến từ log app, ghi chú tài xế và cuộc gọi CSKH đang làm thủ công theo mẫu Excel. Ước tính ~1.000 hủy chuyến/ngày, lấy mẫu 20% để phân tích mất 2-3 phút/case, tương đương ~7-10 giờ công/ngày và chậm phát hiện lỗi hệ thống theo khu vực.                               |
| 3   | Xanh SM                         | AI-upgrade         | Phân loại và phản hồi khiếu nại khách hàng về tài xế, giá cước, điểm đón sai hoặc xe đến muộn còn phụ thuộc CSKH đọc nội dung tự do. Ước tính ~500 ticket/ngày, mỗi ticket mất 6-8 phút, tương đương ~50-67 giờ công/ngày; ticket nghiêm trọng bị route chậm có thể làm giảm SLA phản hồi trong ngày. |
| 4   | Xanh SM                         | Pain từ người khác | Tài xế phải tự tìm trạm sạc phù hợp khi pin thấp, trong khi dữ liệu trạm gần nhất/còn trụ trống/loại cổng sạc không được gợi ý thành hướng dẫn hành động rõ ràng. Ước tính ~80-120 tình huống pin thấp/ngày, mỗi tình huống làm xe ngưng nhận cuốc 15-25 phút, gây mất ~20-50 giờ xe khả dụng/ngày.   |
| 5   | Xanh SM                         | Tốn thời gian      | Đối soát thủ công doanh thu cuốc xe, phụ phí, mã khuyến mãi và hoàn tiền giữa hệ thống đặt xe, ví thanh toán và báo cáo tài xế. Ước tính ~200 case lệch/ngày, mỗi case mất 5-10 phút để tra cứu chéo, tương đương ~17-33 giờ công/ngày và làm chậm chốt doanh thu/tính thưởng tài xế.                 |

---

# 🃏 Phase 2 — QUICK-ASSESS (Cá nhân, 30 min)

Chọn **top 3 bài toán** từ danh sách trên và hoàn thiện **3 Quick Problem Cards** dưới đây (10 phút/card).

## Top 3 bài toán được chọn

1. **#1 - Điều phối thủ công các cuốc xe bị lỗi ghép tài xế vào giờ cao điểm**
2. **#3 - Phân loại và phản hồi khiếu nại khách hàng**
3. **#4 - Gợi ý trạm sạc phù hợp cho tài xế khi pin thấp**

```text
┌─────────────────────────────────────────────────────────────┐
│ QUICK PROBLEM CARD #1                                       │
│                                                             │
│ Bài toán (1 câu): Điều phối viên Xanh SM phải xử lý thủ     │
│ công các cuốc xe bị lỗi ghép tài xế vào giờ cao điểm, làm   │
│ khách chờ lâu và tăng nguy cơ hủy chuyến.                   │
│ Công ty thành viên: [ ] VinFast  [x] Xanh SM  [ ] Vinhomes  │
│                     [ ] Vinmec   [ ] Khác (Ghi rõ)________  │
│                                                             │
│ Ai đang đau (Actor)? Điều phối viên, tài xế và khách đang   │
│ chờ được nhận chuyến.                                       │
│                                                             │
│ Workflow thủ công hiện tại (3-5 bước):                      │
│   1. Hệ thống báo cuốc lỗi ghép tài xế                      │
│   --> 2. Điều phối viên mở bản đồ kiểm tra vị trí xe gần đó │
│   --> 3. Kiểm tra pin, trạng thái tài xế, loại xe           │
│   --> 4. Gọi/nhắn tài xế xác nhận nhận cuốc                 │
│   --> 5. Gán lại tài xế hoặc chuyển case sang CSKH          │
│                                                             │
│ Bước nào tốn thời gian/lỗi nhất? Bước 2-4 (⏱ 4-6 phút/lượt) │
│ AI có thể nhảy vào hỗ trợ ở bước nào? Bước 2-4: tự tổng hợp │
│ bối cảnh cuốc xe, xếp hạng tài xế phù hợp và tạo khuyến nghị│
│ gán lại để điều phối viên duyệt.                            │
│                                                             │
│ Đo thành công bằng gì (Metric có số)? Giảm thời gian xử lý  │
│ mỗi cuốc lỗi từ 4-6 phút xuống dưới 90 giây; giảm tỷ lệ hủy │
│ chuyến do chờ lâu ít nhất 20% trong giờ cao điểm.           │
│                                                             │
│ Quick Architecture: [ ] No AI  [ ] Rule  [ ] LLM  [x] Agent │
└─────────────────────────────────────────────────────────────┘
```

```text
┌─────────────────────────────────────────────────────────────┐
│ QUICK PROBLEM CARD #3                                       │
│                                                             │
│ Bài toán (1 câu): CSKH Xanh SM mất nhiều thời gian đọc,     │
│ phân loại và phản hồi khiếu nại tự do về tài xế, giá cước,  │
│ điểm đón sai hoặc xe đến muộn.                              │
│ Công ty thành viên: [ ] VinFast  [x] Xanh SM  [ ] Vinhomes  │
│                     [ ] Vinmec   [ ] Khác (Ghi rõ)________  │
│                                                             │
│ Ai đang đau (Actor)? Nhân viên CSKH, trưởng ca vận hành và  │
│ khách hàng đang chờ phản hồi.                               │
│                                                             │
│ Workflow thủ công hiện tại (3-5 bước):                      │
│   1. Ticket mới được tạo từ app/call center/email           │
│   --> 2. CSKH đọc nội dung tự do và tra cứu mã chuyến       │
│   --> 3. Phân loại nguyên nhân và mức độ nghiêm trọng       │
│   --> 4. Viết phản hồi nháp hoặc chuyển bộ phận liên quan   │
│   --> 5. Trưởng ca xử lý các ticket nghiêm trọng            │
│                                                             │
│ Bước nào tốn thời gian/lỗi nhất? Bước 2-4 (⏱ 6-8 phút/lượt) │
│ AI có thể nhảy vào hỗ trợ ở bước nào? Bước 2-4: tóm tắt    │
│ nội dung, gắn nhãn nguyên nhân, chấm mức độ ưu tiên và soạn │
│ phản hồi nháp theo policy để CSKH kiểm tra trước khi gửi.   │
│                                                             │
│ Đo thành công bằng gì (Metric có số)? 85% ticket được phân  │
│ loại trong dưới 15 giây; giảm thời gian xử lý trung bình từ │
│ 6-8 phút xuống dưới 2 phút/ticket; route đúng nhóm xử lý    │
│ đạt tối thiểu 90% trên tập kiểm thử nội bộ.                 │
│                                                             │
│ Quick Architecture: [ ] No AI  [ ] Rule  [x] LLM  [ ] Agent │
└─────────────────────────────────────────────────────────────┘
```

```text
┌─────────────────────────────────────────────────────────────┐
│ QUICK PROBLEM CARD #4                                       │
│                                                             │
│ Bài toán (1 câu): Tài xế Xanh SM khi pin thấp phải tự tìm   │
│ trạm sạc phù hợp, khiến xe ngưng nhận cuốc lâu và có nguy   │
│ cơ hết pin trước khi đến trạm.                              │
│ Công ty thành viên: [ ] VinFast  [x] Xanh SM  [ ] Vinhomes  │
│                     [ ] Vinmec   [ ] Khác (Ghi rõ)________  │
│                                                             │
│ Ai đang đau (Actor)? Tài xế, điều phối viên đội xe và khách │
│ bị ảnh hưởng do thiếu xe khả dụng.                          │
│                                                             │
│ Workflow thủ công hiện tại (3-5 bước):                      │
│   1. Tài xế thấy cảnh báo pin thấp                          │
│   --> 2. Tài xế tự mở bản đồ hoặc gọi điều phối             │
│   --> 3. Kiểm tra thủ công trạm gần nhất/còn trụ trống      │
│   --> 4. Quyết định dừng nhận cuốc và di chuyển đến trạm    │
│   --> 5. Nếu không đến kịp thì gọi hỗ trợ/cứu hộ            │
│                                                             │
│ Bước nào tốn thời gian/lỗi nhất? Bước 2-4 (⏱ 15-25 phút xe │
│ ngưng nhận cuốc/lượt)                                       │
│ AI có thể nhảy vào hỗ trợ ở bước nào? Bước 2-4: kết hợp vị  │
│ trí xe, phần trăm pin, loại cổng sạc, tình trạng trụ trống  │
│ và nhu cầu cuốc gần đó để đề xuất hành động an toàn.        │
│                                                             │
│ Đo thành công bằng gì (Metric có số)? Giảm thời gian xe     │
│ ngưng nhận cuốc vì tìm trạm sạc từ 15-25 phút xuống dưới    │
│ 7 phút/lượt; 95% khuyến nghị không vượt quá ngưỡng pin an   │
│ toàn theo loại xe và khoảng cách.                           │
│                                                             │
│ Quick Architecture: [ ] No AI  [x] Rule  [x] LLM  [ ] Agent │
└─────────────────────────────────────────────────────────────┘
```

> [!TIP]
> **🤖 AI Prompts — Stress-Test thẻ bài toán:**
> Hãy dán nội dung thẻ bài toán của bạn vào LLM để nhận phản biện:
> _"Đây là một thẻ bài toán vận hành tôi đề xuất cho Vin Smart Future: Tổng hợp lý do khách hủy chuyến từ log app, ghi chú tài xế và cuộc gọi CSKH đang làm thủ công theo mẫu Excel. Ước tính ~1.000 hủy chuyến/ngày, lấy mẫu 20% để phân tích mất 2-3 phút/case, tương đương ~7-10 giờ công/ngày và chậm phát hiện lỗi hệ thống theo khu vực. Hãy đóng vai trò là một CFO và Trưởng phòng Vận hành cực kỳ khắt khe, chỉ ra cho tôi 3 điểm yếu về logic, metric, và giải thích vì sao rule-based code thông thường có thể giải quyết bài toán này tốt hơn là dùng AI."_

---
