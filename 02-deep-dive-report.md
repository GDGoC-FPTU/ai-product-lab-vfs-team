# Intro
Group Name: VFS team
Members:
- Hồ Tất Bảo Hoàng - 2A202600699
- Nguyễn Phương Nam - 2A202600962
- Đào Tất Thắng - 2A202600540
- Bùi Văn Tuân - 2A202601006

---
# 🏗️ Phase 3 — DEEP-DIVE (Nhóm, 85 min)

## 3.1. Current-State Workflow Mapping (25 min)

**Vẽ quy trình hiện tại lên bảng/giấy A3.** Sử dụng các ký hiệu:

* 🔴 **Bottleneck:** Bước gây tắc nghẽn, tốn thời gian, hoặc sai sót nhiều nhất.
* 🔄 **Handoff:** Điểm chuyển giao thông tin giữa người và hệ thống, hoặc giữa các bộ phận.
* Ghi rõ thời gian vận hành trung bình: **Tổng cộng = 13 phút/lượt**.

**Quy trình hiện tại (Manual Workflow):**

1. Cư dân gửi khiếu nại qua App Vinhomes Resident ➡️ Hệ thống ghi nhận ticket.
2. 🔴 **Bottleneck:** Nhân viên CSKH (Tier 1) mở từng ticket, đọc và phân tích ý định (Intent) của cư dân (Mất ~4 phút).
3. 🔄 **Handoff:** CSKH chuyển tab sang phần mềm quản lý để tra cứu lịch sử căn hộ, xem đã có sự cố tương tự chưa (Mất ~3 phút).
4. 🔴 **Bottleneck:** CSKH copy/paste câu trả lời mẫu, sửa lại tên/mã căn hộ và nhấn gửi. Đồng thời, thủ công gán nhãn chuyển ticket cho đội Kỹ thuật/BQL (Mất ~5 phút). Dễ xảy ra chuyển nhầm phòng ban do đọc vội.
5. Đội ngũ chuyên môn tiếp nhận và xử lý thực địa (Mất ~1 phút để nhận lệnh).

## 3.2. Problem Statement (6-field) & Metrics (15 min)

Điền đầy đủ 6 trường thông tin của bài toán:

| Field | Nội dung chi tiết |
| --- | --- |
| **1. Actor / Operator** | Nhân viên Chăm sóc khách hàng (Tier 1) tại Vinhomes. |
| **2. Current Workflow** | Cư dân báo lỗi qua App. CSKH phải tự đọc từng ticket, phân tích vấn đề, tra cứu lịch sử, soạn phản hồi thủ công và tự quyết định định tuyến (route) cho bộ phận nào (BQL, Kỹ thuật, An ninh). |
| **3. Bottleneck** | Khâu đọc hiểu ngữ nghĩa, đánh giá mức độ khẩn cấp và định tuyến thủ công. Nhân viên dễ bị quá tải, phản hồi rập khuôn gây bức xúc, hoặc chuyển nhầm phòng ban làm kéo dài thời gian xử lý. |
| **4. Business Impact** | Vi phạm SLA về thời gian phản hồi (chờ quá lâu). Cư dân đánh giá 1-star, phàn nàn trên mạng xã hội gây ảnh hưởng uy tín thương hiệu. Lãng phí nhân sự vào các tác vụ phân loại lặp lại. |
| **5. Success Metric** | 1. **Routing Accuracy:** > 95% ticket được định tuyến đúng phòng ban.<br>

<br>2. **First Response Time:** Giảm từ 13 phút xuống < 1 phút (thời gian gen ra câu trả lời nháp để duyệt). |
| **6. Operational Boundary** | **Được làm:** AI tự động gắn tag (phân loại), chấm điểm khẩn cấp, và soạn SẴN bản nháp phản hồi.<br>

<br>**TUYỆT ĐỐI không:** Không được tự động gửi tin nhắn phản hồi cho cư dân khi chưa có người duyệt (trừ ca khẩn cấp sinh tử). KHÔNG được tự bịa ra các phòng ban ngoài danh mục có sẵn.<br>

<br>**Điểm duyệt:** Nhân viên CSKH bắt buộc phải click "Duyệt & Gửi" (HITL). |

## 3.3. Future-State Flow & AI Fit (25 min)

* **Xác định mức AI Fit (AI-Fit Matrix):** Giải pháp thuộc nhóm nào? [ ] Rule / State-Machine [x] LLM Feature [ ] Agentic Loop.
* **Vẽ Future-State Flow:** Đánh dấu rõ:
* 🔵 **AI Step:** Tác vụ LLM xử lý: Nhận raw text -> Phân tích Intent -> Chấm điểm Urgency -> Trích xuất Entity (Mã căn/Tòa) -> Soạn Draft phản hồi.
* 🟢 **Human Step (HITL):** Bước con người phê duyệt/review: CSKH đọc bản nháp của AI trên màn hình, chỉnh sửa (nếu cần) và bấm "Gửi". Hệ thống tự động chuyển ticket về đúng phòng ban theo tag AI đã gắn.
* ↩️ **Fallback:** Kế hoạch dự phòng khi LLM trả về kết quả lỗi hoặc không tự tin: Nếu Confidence Score của AI < 70% hoặc gặp ticket có ngôn từ quá phức tạp/đe dọa, hệ thống đẩy thẳng ticket vào hàng đợi "Manual Review" để CSKH xử lý thủ công 100% như quy trình cũ.



---

# 🏁 Phase 5 — EVALUATE (Nhóm, 20 min)

### AI Readiness Checklist:

1. [x] Chúng tôi có sẵn dữ liệu mẫu/logs sạch để test? *(Có, kho dữ liệu ticket khiếu nại khổng lồ trên hệ thống Vinhomes Resident).*
2. [x] Rủi ro khi AI sai có nằm trong tầm kiểm soát (qua HITL hoặc Fallback)? *(Có, AI chỉ làm Draft và gắn nhãn, quyền quyết định cuối cùng vẫn nằm ở nút "Duyệt" của con người).*
3. [x] Stakeholders sẵn sàng thay đổi quy trình làm việc cũ? *(Có, đội ngũ CSKH đang quá tải và rất cần công cụ giảm tải tác vụ lặp lại).*

### Quyết định cuối cùng của Ban Giám Đốc Vin Smart Future:

[x] **GO (Bắt đầu xây dựng Prototype):** Bắt đầu phát triển với scope hẹp.
[ ] **NOT YET (Cần tích lũy thêm dữ liệu/xác lập baseline):** Trì hoãn để chuẩn bị thêm.
[ ] **NO-GO (Không khả thi / Rule-based tốt hơn):** Hủy bỏ dự án AI này.

**Justification (Lý giải quyết định dựa trên bằng chứng kỹ thuật và chi phí):**

> Dự án đạt mức độ khả thi cao vì giải quyết trực tiếp một "nút thắt cổ chai" rõ ràng: Việc xử lý ngôn ngữ tự nhiên (NLP) ở khối lượng lớn. Tác vụ đọc hiểu phàn nàn và trích xuất thông tin là thế mạnh cốt lõi của LLM. Mô hình Human-in-the-loop (CSKH duyệt nháp) đảm bảo rủi ro rò rỉ thông tin sai lệch ra phía cư dân gần như bằng không. Hơn nữa, việc tích hợp LLM vào luồng phân loại ticket (Routing) có thể triển khai nhanh chóng thông qua API mà không đòi hỏi đập bỏ hạ tầng phần mềm quản lý hiện tại, mang lại ROI tức thì bằng việc tiết kiệm hàng nghìn giờ công/tháng và cải thiện trực tiếp chỉ số CSAT (Sự hài lòng của khách hàng).
