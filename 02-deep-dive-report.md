# Intro
Group Name: VFS team
Members:
- Hồ Tất Bảo Hoàng - 2A202600699
- Nguyễn Phương Nam - 2A202600962
- Đào Tất Thắng - 2A202600540
- Bùi Văn Tuân - 2A202601006

---
# Phase 3 — DEEP-DIVE (Nhóm, 85 min)

## 3.1. Current-State Workflow Mapping (25 min)
Quy trình thủ công hiện tại:
*   Bước 1: Tiếp nhận thông tin phản ánh/yêu cầu từ cư dân gửi qua ứng dụng Vinhomes Resident hoặc Zalo/SMS (Điểm chuyển giao Handoff 1 - Cư dân sang CSKH).
*   Bước 2: Nhân viên CSKH đọc nội dung tin nhắn, phân loại loại hình phản ánh (Điện, nước, an ninh, phí dịch vụ, thang máy, tiếng ồn, gửi xe...) (Điểm nghẽn Bottleneck 1 - Tốn thời gian đọc và phân loại thủ công).
*   Bước 3: Nhân viên CSKH tra cứu thủ công lịch sử căn hộ, thông tin hóa đơn và quy trình xử lý tương ứng của Ban quản lý tòa nhà (BQL) trên các phần mềm quản trị nội bộ khác nhau.
*   Bước 4: Nhân viên soạn thảo tin nhắn phản hồi cá nhân hóa gửi cho cư dân để xác nhận thông tin và đưa ra hướng xử lý tiếp theo (Điểm nghẽn Bottleneck 2 - Viết thủ công mất 5-7 phút/ticket, dễ gây lỗi trả lời khuôn mẫu thiếu thiện cảm đối với các phản ánh nhạy cảm).
*   Bước 5: Chuyển tiếp yêu cầu kỹ thuật sang bộ phận chuyên trách (Kỹ thuật/Bảo vệ/Vệ sinh) qua Zalo/phần mềm nội bộ (Điểm chuyển giao Handoff 2 - CSKH sang Bộ phận chuyên trách).

Thời gian vận hành trung bình: **Tổng cộng = 10 phút/lượt**.

## 3.2. Problem Statement (6-field) & Metrics (15 min)
Điền đầy đủ 6 trường thông tin của bài toán:

| Field | Nội dung chi tiết |
|---|---|
| **1. Actor / Operator** | Nhân viên chăm sóc khách hàng (CSKH) tại sảnh chung cư Vinhomes và điều phối viên Helpdesk của Ban quản lý tòa nhà. |
| **2. Current Workflow** | Đọc phản hồi/ticket cư dân gửi về qua App Vinhomes Resident/Zalo/SMS -> Phân loại loại hình sự cố (thang máy, nước, điện, gửi xe, tiếng ồn, an ninh, phí dịch vụ) -> Tra cứu thủ công lịch sử căn hộ và quy trình BQL -> Soạn tin nhắn phản hồi cá nhân hóa -> Chuyển thông tin cho các bộ phận chuyên trách liên quan. |
| **3. Bottleneck** | Tắc nghẽn tại bước đọc hiểu nội dung, đối chiếu lịch sử căn hộ từ các hệ thống khác nhau và tự tay soạn phản hồi. Việc phản hồi thủ công mất nhiều thời gian, dễ gây sai lệch, chậm trễ phản hồi trong giờ cao điểm hoặc đưa ra câu trả lời khuôn mẫu thiếu thiện cảm đối với các phản ánh nhạy cảm (như khiếu nại, review 1 sao). |
| **4. Business Impact** | Cư dân Vinhomes phàn nàn về tốc độ phản hồi chậm (SLA trung bình bị kéo dài từ 5 phút lên 15-20 phút trong giờ cao điểm), tình trạng chuyển lòng vòng giữa các bộ phận gây ức chế. Chi phí nhân sự CSKH tăng cao do phải tăng ca liên tục giờ cao điểm. Tỷ lệ hài lòng cư dân (CSAT) giảm sâu khi nhận phản hồi rập khuôn hoặc trả lời mẫu vô cảm. |
| **5. Success Metric** | Rút ngắn thời gian xử lý và soạn phản hồi cá nhân hóa trung bình từ 10 phút xuống dưới 2 phút mỗi ticket. Tỷ lệ tự động phân loại và định tuyến (routing) đúng bộ phận đạt trên 95%. Tỷ lệ phản hồi đúng SLA trong vòng 2 phút đạt trên 90%. |
| **6. Operational Boundary** | AI được phép: Đọc nội dung ticket, tự động xác định ý định (intent) và mức độ khẩn cấp, tra cứu lịch sử căn hộ qua API đã tích hợp, tự động soạn thảo bản nháp phản hồi cá nhân hóa bằng tiếng Việt, và đề xuất bộ phận tiếp nhận (BQL, Kỹ thuật, Bảo vệ, Vệ sinh). AI TUYỆT ĐỐI không được phép: Tự động gửi tin nhắn trực tiếp cho cư dân mà không có sự kiểm duyệt của nhân viên CSKH (Human-in-the-loop); không được tự động ra quyết định miễn giảm phí dịch vụ hoặc cam kết bồi thường tài chính. |

## 3.3. Future-State Flow & AI Fit (25 min)
*   **Xác định mức AI Fit (AI-Fit Matrix):** Giải pháp thuộc nhóm nào? [ ] Rule / State-Machine [ ] LLM Feature [x] Agentic Loop.
*   **Vẽ Future-State Flow:** Đánh dấu rõ:
    *   Tác vụ AI Step:
        *   AI Step 1: Nhận ticket đầu vào và tiến hành đọc, phân tích ngữ nghĩa để xác định ý định (intent) và mức độ khẩn cấp của yêu cầu.
        *   AI Step 2: Tự động gọi API truy vấn lịch sử căn hộ và các quy định xử lý sự cố tương ứng của tòa nhà từ cơ sở dữ liệu.
        *   AI Step 3: Tự động soạn thảo bản nháp phản hồi cá nhân hóa bằng tiếng Việt và đề xuất luồng định tuyến (Kỹ thuật/Bảo vệ/Vệ sinh).
    *   Bước con người phê duyệt/review (Human-in-the-loop - HITL Step):
        *   HITL Step: Nhân viên CSKH xem xét bản nháp phản hồi và luồng định tuyến đề xuất:
            *   Nếu bản nháp chính xác: Nhân viên bấm duyệt -> Hệ thống tự động gửi tin nhắn cho cư dân và chuyển ticket cho bộ phận chuyên trách.
            *   Nếu bản nháp chưa chính xác: Nhân viên chỉnh sửa trực tiếp nội dung tin nhắn hoặc thay đổi bộ phận định tuyến trước khi bấm gửi.
    *   Kế hoạch dự phòng (Fallback):
        *   Fallback: Nếu AI trả về kết quả có độ tự tin thấp (dưới 80%) hoặc gặp lỗi kết nối hệ thống API: Hệ thống tự động chuyển ticket sang quy trình xử lý thủ công truyền thống và thông báo cho nhân viên CSKH xử lý ngay lập tức để đảm bảo SLA của cư dân.

---

# Phase 5 — EVALUATE (Nhóm, 20 min)

### AI Readiness Checklist:
1. [x] Chúng tôi có sẵn dữ liệu mẫu/logs sạch để test?
2. [x] Rủi ro khi AI sai có nằm trong tầm kiểm soát (qua HITL hoặc Fallback)?
3. [x] Stakeholders sẵn sàng thay đổi quy trình làm việc cũ?

### Quyết định cuối cùng của Ban Giám Đốc Vin Smart Future:
[x] **GO (Bắt đầu xây dựng Prototype):** Bắt đầu phát triển với scope hẹp.
[ ] **NOT YET (Cần tích lũy thêm dữ liệu/xác lập baseline):** Trì hoãn để chuẩn bị thêm.
[ ] **NO-GO (Không khả thi / Rule-based tốt hơn):** Hủy bỏ dự án AI này.

**Justification (Lý giải quyết định dựa trên bằng chứng kỹ thuật và chi phí):**
> Dự án có tính khả thi cực kỳ cao vì dữ liệu lịch sử ticket văn bản của Vinhomes rất phong phú và đã được số hóa sẵn trên hệ thống quản trị hiện tại. Việc áp dụng mô hình ngôn ngữ lớn (LLM) để phân loại intent và sinh văn bản nháp giúp xử lý triệt để bài toán lặp đi lặp lại của bộ phận CSKH, mang lại hiệu quả kinh tế rõ rệt thông qua giảm 80% thời gian xử lý thủ công (từ 10 phút xuống dưới 2 phút/ticket) và nâng cao chỉ số hài lòng của cư dân (CSAT). Rủi ro vận hành được kiểm soát tuyệt đối bằng cơ chế Human-in-the-loop (nhân viên luôn kiểm duyệt bản nháp trước khi gửi) và quy trình dự phòng Fallback tự động khi mô hình không tự tin. Chi phí triển khai thấp nhờ tận dụng hạ tầng API sẵn có của Vinhomes.
