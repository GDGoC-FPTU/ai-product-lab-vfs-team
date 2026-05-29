# Nhật ký Thảo luận và Sàng lọc Bài toán - VFS Team

Tài liệu ghi lại toàn bộ quá trình tranh luận nội bộ, sàng lọc từ danh sách 10 bài toán xuống 3 bài toán khả thi nhất và đi đến lựa chọn duy nhất làm prototype của nhóm VFS Team.

---

## 1. Phan chia vai tro thao luan nhom 4 thanh vien

Nhóm đã tổ chức họp trực tiếp để phân tích từng nghiệp vụ đặc thù tại các công ty thành viên:

*   Hồ Tất Bảo Hoàng (2A202600699) - Vai trò: Tech Lead, tập trung khảo sát các quy trình kỹ thuật và chuỗi cung ứng của VinFast.
*   Nguyễn Phương Nam (2A202600962) - Vai trò: Operations Lead, tập trung đánh giá hiệu quả vận hành đội xe và chế độ tài xế của Xanh SM.
*   Đào Tất Thắng (2A202600540) - Vai trò: Product Manager, tập trung nghiên cứu trải nghiệm cư dân và hiệu suất của Vinhomes.
*   Bùi Văn Tuân (2A202601006) - Vai trò: AI Analyst, đánh giá tính khả thi về kỹ thuật và dữ liệu của Vinmec và tổng đài.

---

## 2. Quá trình khảo sát và sàng lọc 10 bài toán từ 25 ý tưởng ban đầu

Trước khi đi đến danh sách 10 bài toán cuối cùng, từng thành viên trong nhóm đã chủ động khảo sát độc lập các nghiệp vụ vận hành trong mảng mình phụ trách và đưa ra tổng cộng 25 đề xuất bài toán thô:
*   Bảo Hoàng đề xuất 7 ý tưởng về khối nhà máy lắp ráp VinFast và chuỗi cung ứng phụ tùng.
*   Phương Nam đề xuất 6 ý tưởng về hoạt động phân bổ đội xe, chăm sóc tài xế và cứu hộ pin Xanh SM.
*   Tất Thắng đề xuất 6 ý tưởng về trải nghiệm cư dân, quản lý tiện ích và kỹ thuật tòa nhà Vinhomes.
*   Văn Tuân đề xuất 6 ý tưởng về quy trình thủ tục y khoa Vinmec và tổng đài chăm sóc khách hàng.

Cả nhóm đã tổ chức một buổi họp offline kéo dài 20 phút để phản biện nghiêm ngặt, loại bỏ và tinh gọn từ 25 ý tưởng ban đầu xuống 10 bài toán tối ưu nhất qua 3 vòng sàng lọc:

*   Vòng 1 (Kiểm chứng metrics rành mạch): Loại bỏ 8 ý tưởng khó đo lường hoặc thiếu số liệu minh chứng thực tế về tổn thất hiệu suất (ví dụ: phân bổ ca trực bảo vệ tại Vinhomes, sắp xếp lịch trực y tá tại Vinmec).
*   Vòng 2 (Áp dụng nguyên lý AI Fit): Loại bỏ 5 ý tưởng mà rule-based hoặc code logic thông thường có thể giải quyết triệt để mà không cần đến AI để tiết kiệm chi phí phát triển (ví dụ: tự động gửi thông báo đóng phí quản lý Vinhomes, kiểm tra điều kiện đăng ký giấy tờ của tài xế Xanh SM).
*   Vòng 3 (Cân đối 4 Lenses và subsidiary): Lựa chọn và tinh chỉnh 10 bài toán phù hợp nhất từ 12 ý tưởng còn lại. Nhóm đảm bảo các bài toán phải đại diện cho cả 4 công ty thành viên, phân bổ đều vào 4 Lenses (Time-consuming, Repetitive, Stakeholder Pain, AI-upgrade) để có góc nhìn toàn diện.

Kết quả là 10 bài toán vận hành tiêu biểu nhất đã được chọn lọc thành công và đồng bộ vào file 01-problem-scan.md.

---

## 3. Quá trình sàng lọc từ 10 problem scan xuống 3 ticket tiềm năng

Nhóm đã xây dựng một ma trận đánh giá dựa trên 3 tiêu chí chính với thang điểm từ 1 đến 5 (5 là tốt nhất):
*   Mức độ cấp thiết (Nêu nghẹn đầu, tổn thất hiệu suất lớn).
*   Tính sẵn có của dữ liệu (Có sẵn dữ liệu log, thông tin vận hành để làm mock/test).
*   Khả năng triển khai prototype (Khả thi để xây dựng prompt boundary và verify kết quả nhanh).

Ma trận đánh giá và cho điểm nội bộ của nhóm VFS Team:

| STT | Bài toán | Mức độ cấp thiết | Sẵn có dữ liệu | Tính khả thi | Tổng điểm | Trạng thái |
|---|---|---|---|---|---|---|
| 1 | CSKH Vinhomes | 4 | 5 | 4 | 13/15 | Được chọn (Ticket 1) |
| 2 | Service Copilot VinFast | 5 | 3 | 4 | 12/15 | Được chọn (Ticket 2) |
| 3 | Đối soát tài xế Xanh SM | 4 | 3 | 3 | 10/15 | Loại |
| 4 | Kiểm tra rework VinFast | 4 | 2 | 3 | 9/15 | Loại |
| 5 | Tổng đài hỗ trợ VinFast | 4 | 3 | 3 | 10/15 | Loại |
| 6 | Cứu hộ sạc pin Xanh SM | 5 | 4 | 5 | 14/15 | Được chọn (Ticket 6) |
| 7 | Bệnh án SOAP Vinmec | 4 | 2 | 2 | 8/15 | Loại |
| 8 | Quản lý năng lượng Vinhomes | 3 | 3 | 3 | 9/15 | Loại |
| 9 | Giám sát lái xe Xanh SM | 4 | 2 | 2 | 8/15 | Loại |
| 10 | Dự báo phụ tùng VinFast | 4 | 3 | 3 | 10/15 | Loại |

Lý do lọc ra 3 Ticket cao điểm nhất:
*   Ticket 6 (Cứu hộ sạc pin Xanh SM - 14 điểm): Cao điểm nhất nhờ tính cấp thiết về an toàn tính mạng và kỹ thuật cực kỳ rõ ràng, dữ liệu định vị vận hành dễ dàng được giả lập thời gian thực.
*   Ticket 1 (CSKH Vinhomes - 13 điểm): Dữ liệu dạng văn bản rất sẵn có và luồng vận hành của ban quản lý đã được chuẩn hóa từ trước, dễ dàng thiết lập LLM phân loại.
*   Ticket 2 (Service Copilot VinFast - 12 điểm): Mặc dù điểm dữ liệu chỉ ở mức trung bình do tính bảo mật của VinFast, nhưng đây là pain point đặc biệt nghiêm trọng của dòng xe EV nên được nhóm giữ lại để phân tích chuyên sâu.

---

## 4. Nhật ký quá trình thảo luận chọn 3 bài toán từ danh sách 10 problem scan

Từ 10 ý tưởng ban đầu trong file 01-problem-scan.md, nhóm đã tổ chức phản biện nội bộ theo các tiêu chí nghiêm ngặt: mức độ đau đớn của người vận hành, tính sẵn có của dữ liệu, và thời gian phát triển prototype.

### Ca thảo luận 1: Sàng lọc xuống 3 ứng cử viên sáng giá nhất

*   Hoàng: "Sau khi đi thực tế các xưởng dịch vụ VinFast và nhà máy sản xuất, tôi thấy bài toán số 2 (Chẩn đoán lỗi và tự động soạn warranty claim) và số 4 (Kiểm tra rework) rất đau. Tuy nhiên, hệ thống dữ liệu sản xuất và warranty rất khép kín, khó lấy dữ liệu sạch để làm prototype trong 24 giờ."
*   Tuân: "Đúng vậy, bài toán số 7 của Vinmec về ghi chép SOAP cũng gặp rào cản rất lớn về bảo mật thông tin y tế và tiêu chuẩn FDA/Bộ Y tế. Chúng ta nên ưu tiên các bài toán có luồng quy trình vận hành thủ công rõ ràng và dễ dàng tiếp cận log vận hành như Vinhomes hoặc Xanh SM."
*   Thắng: "Vậy tôi đề xuất bài toán số 1 (Phân loại ticket BQL Vinhomes). Đây là nghiệp vụ rất rõ ràng: mỗi ngày nhận hàng trăm ticket lặp về thang máy, gửi xe, nước. Log lịch sử ticket có sẵn, kiểu dữ liệu chủ yếu là văn bản, rất phù hợp cho mô hình ngôn ngữ."
*   Nam: "Tôi bổ sung thêm 2 bài toán cực kỳ cấp thiết của Xanh SM là số 3 (Hỗ trợ tài xế đối soát lương thưởng) và số 6 (Điều phối cứu hộ sạc pin khẩn cấp). Trong đó bài toán số 6 là nỗi đau lớn nhất vì ảnh hưởng trực tiếp đến an toàn và hiệu suất đội xe. Khi tài xe hết pin dưới 5% giữa đường, họ phải gọi tổng đài, điều phối viên phải làm thủ công rất lâu, gây rủi ro xe chết máy."
*   Hoàng: "Như vậy, qua khảo sát ban đầu về tính sẵn có dữ liệu và thời gian phản hồi, chúng ta thống nhất chọn ra 3 bài toán tiềm năng nhất để đưa vào stress-test nghiêm ngặt gồm:"
    1. Ticket số 1: Tự động phân loại và soạn phản hồi ticket cư dân Vinhomes (Vinhomes).
    2. Ticket số 2: AI Service Copilot hỗ trợ xưởng dịch vụ và warranty claim (VinFast).
    3. Ticket số 6: Tự động hóa điều phối cứu hộ sạc di động khi xe hết pin dưới 5% (Xanh SM).

---

## 5. Đánh giá sơ bộ 3 Ticket được chọn

### Ticket 1: Tự động phân loại ticket Vinhomes
*   Mô tả: AI đọc tin nhắn báo lỗi của cư dân, phân loại đúng BQL/Kỹ thuật/Bảo vệ và soạn tin nhắn nháp phản hồi.
*   Ưu điểm: Dữ liệu text phong phú, dễ làm prototype bằng Prompt Engineering thông thường.
*   Nhược điểm: Tác động trực tiếp đến trải nghiệm cư dân, rủi ro hallucination (ảo tưởng) của LLM khi hướng dẫn nghiệp vụ an ninh/khiếu nại rất nhạy cảm.

### Ticket 2: AI Service Copilot hỗ trợ xuyên suốt dịch vụ xe VinFast
*   Mô tả: AI đọc thông số telemetry và DTC lỗi từ xe, gợi ý nguyên nhân và tự soạn báo cáo gửi lên phòng bảo hành VinFast.
*   Ưu điểm: Mang lại hiệu quả kinh tế rất lớn, giảm thời gian chờ đợi tại workshop của khách hàng.
*   Nhược điểm: DTC code và nghiệp vụ kỹ thuật phụ tùng yêu cầu mô hình cần có tri thức đặc thù rất sâu, thời gian kiểm thử và sync dữ liệu hệ thống rất lâu.

### Ticket 6: Điều phối cứu hộ sạc di động tự động cho Xanh SM
*   Mô tả: Tự động đọc tín hiệu pin thấp từ hệ thống viễn thông, nếu dưới 5% thì ngắt quy trình tìm trạm sạc tĩnh mà ngay lập tức kích hoạt lệnh điều xe sạc pin di động cứu hộ.
*   Ưu điểm: Luồng nghiệp vụ và ranh giới an toàn cực kỳ rõ ràng (dưới 5% là phải cứu hộ di động). Giải quyết được cả rủi ro an toàn lẫn rủi ro hiệu suất.
*   Nhược điểm: Đòi hỏi bộ thông tin định vị thời gian thực.

---

## 6. Quyết định cuối cùng: Chọn Ticket 6 làm sản phẩm prototype

Nhóm đã đi đến thống nhất chọn **Ticket 6: Điều phối cứu hộ sạc di động tự động cho Xanh SM (EV Emergency Dispatch)** làm bài toán chính để phát triển prototype vì những lý do thuyết phục sau:

*   Ranh giới kỹ thuật hoàn toàn rõ ràng: Ngưỡng pin 5% là con số tuyệt đối (deterministic rule). AI có thể dễ dàng thực thi logic bằng hệ thống System Prompt mà không lo bị nhiễu bởi các yếu tố cảm xúc hay ngữ cảnh quá rộng.
*   Tính thiết thực: Giải quyết trực tiếp một điểm nghẽn chí mạng của xe điện (lo sợ hết pin - range anxiety) của cả tài xế lẫn ban vận hành Xanh SM.
*   Dễ dàng đồng bộ an toàn: Dễ dàng thiết lập cơ chế `[DRAFT_ONLY]` để bắt buộc điều phối viên phải duyệt qua tin nháp trước khi lệnh được chuyển đi, giúp đảm bảo an toàn tuyệt đối trong giai đoạn thử nghiệm mà không lo ngắt quãng nghiệp vụ hiện tại.

---

## 7. Chốt danh sách 10 bài toán problem scan của cả nhóm

Mọi thông tin về 10 bài toán phục vụ Phase 1 và làm cơ sở để chọn ra 3 ứng viên trên đã được nhóm hoàn thiện và đồng bộ hóa vào file 01-problem-scan.md của team.

Dưới đây là danh sách chi tiết 10 bài toán vận hành đã được cả nhóm VFS thống nhất ghi nhận:

| STT | Công ty thành viên | Ống kính phân tích | Mô tả ngắn bài toán vận hành và hướng giải quyết bằng AI |
|---|---|---|---|
| 1 | Vinhomes | Pain từ người khác | CSKH cư dân: phân loại ticket và phản hồi khiếu nại. Mỗi ngày nhận ticket về thang máy, nước, điện, gửi xe, tiếng ồn. AI agent tự động đọc intent, xác định mức độ khẩn cấp, tự động chuyển tiếp cho đúng bộ phận kỹ thuật/BQL và soạn sẵn tin nháp phản hồi cá nhân hóa. |
| 2 | VinFast | Tốn thời gian | Chẩn đoán lỗi xe và xử lý warranty claim tại xưởng dịch vụ. Kỹ thuật viên mất thời gian đọc complaint, DTC lỗi xe, lịch sử sửa chữa để làm claim thủ công. AI copilot tóm tắt lịch sử xe, gợi ý nguyên nhân lỗi và tự động soạn warranty claim nháp giúp giảm thời gian chờ của khách. |
| 3 | Xanh SM | Lặp lại | Hỗ trợ tài xế về payout, lương thưởng, xử phạt và tranh chấp chuyến đi. Nhân viên phải tra cứu thủ công trên nhiều hệ thống ví, chuyến đi, chấm công. AI chatbot tự động kết nối database để giải thích chính sách thu nhập và tự tạo ticket hỗ trợ cho các trường hợp sai sót phức tạp. |
| 4 | VinFast | Lặp lại | Kiểm tra chất lượng cuối dây chuyền và rework trong nhà máy sản xuất. Việc kiểm tra thủ công dễ bỏ sót lỗi nhỏ dẫn đến rework nhiều lần, gây tổn thất chi phí phế phẩm lớn. AI thị giác máy tính phát hiện sớm và phân tích lỗi lắp ráp thời gian thực để giảm thời gian rework. |
| 5 | VinFast | AI có thể tốt hơn | CSKH tổng đài hỗ trợ xe và ứng dụng. Điện thoại viên phải tra cứu thủ công về tình trạng xe, lỗi app bằng tập kịch bản cứng nhắc làm tăng thời gian đàm thoại (AHT). AI agent hỗ trợ gợi ý next-best-action thời gian thực và định tuyến thông minh để rút ngắn 40-60% thời gian cuộc gọi. |
| 6 | Xanh SM | Tốn thời gian | Điều phối cứu hộ sạc pin di động khẩn cấp (EV Emergency Dispatch) cho xe dưới 5% pin. Quy trình nhận cuộc gọi, tìm kiếm xe sạc di động rồi điều phối thủ công mất 15-20 phút dễ làm xe chết máy trên đường. AI tự động check telematics, định vị GPS và dispatch xe cứu hộ trong 30 giây. |
| 7 | Vinmec | Tốn thời gian | Tóm tắt bệnh án SOAP và hỗ trợ bác sĩ kê đơn thuốc tại bệnh viện. Bác sĩ mất 3-4 tiếng mỗi ngày nhập liệu bệnh án điện tử EHR thủ công. AI copilot lắng nghe cuộc khám bệnh (ambient AI) để tự động cấu trúc hóa hồ sơ và đưa ra cảnh báo nếu kê đơn thuốc trùng hoặc không phù hợp với bệnh lý. |
| 8 | Vinhomes | AI có thể tốt hơn | Quản lý năng lượng và phát hiện bất thường đồng bộ trong tòa nhà. Các thiết bị chiller, HVAC vận hành theo lịch cứng, gây lãng phí lớn. AI phân tích dữ liệu từ cảm biến IoT thời gian thực và thông tin thời tiết để tự động điều chỉnh năng lượng tối ưu, phát hiện sớm rò rỉ nước và chập điện. |
| 9 | Xanh SM | AI có thể tốt hơn | Giám sát hành vi tài xế và dự báo rủi ro tai nạn chủ động. Bộ phận an toàn phải check dashcam thủ công khi có sự cố. AI rà soát telemetry và video cabin để cảnh báo trực tiếp tài xế khi có biểu hiện buồn ngủ, mất tập trung và dự báo va chạm chủ động để hạn chế tai nạn. |
| 10 | VinFast | Tốn thời gian | Dự báo nhu cầu phụ tùng và tối ưu hóa chuỗi cung ứng toàn cầu. Dự báo theo thống kê cũ dẫn đến workshop thiếu linh kiện sửa chữa làm tăng thời gian chờ của khách. AI phân tích thông số lỗi và telemetry từ các xe đang lưu thông để dự báo chính xác nhu cầu linh kiện ở từng workshop. |
