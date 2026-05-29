# Nhật ký AI Lab 02

## AI giúp gì
Trong quá trình làm Lab 02, tôi đã dùng AI như một trợ lý tư duy và kiểm tra logic để:
- Brainstorm ý tưởng bài toán vận hành và phân loại chúng theo 4 lens: Repetitive, Time-consuming, AI-upgrade, Stakeholder Pain.
- Viết prompt để kiểm tra logic của thẻ bài toán, chỉ ra điểm yếu về metric và xác định giải pháp phù hợp giữa rule-based và AI.
- Trình bày rõ workflow thủ công, bottleneck và metric đo thành công cho các Quick Problem Cards.

AI giúp tôi:
- Tiết kiệm thời gian khi tổ chức ý tưởng, viết mô tả và định nghĩa các bước nghiệp vụ.
- Nhận diện được rằng một số bài toán nên ưu tiên giải pháp rule-based trước khi dùng AI.
- Cải thiện độ rõ ràng trong phần actor, bước xử lý và nhiệm vụ nào thực sự phù hợp với AI.

## AI sai gì
Tôi nhận thấy AI có một số điểm chưa chính xác hoặc thiếu thực tế:
- AI đề xuất dùng AI/LLM ngay cả khi bài toán tổng hợp lý do hủy chuyến có thể được xử lý hiệu quả bằng rule-based code.
- AI không phân biệt đủ rõ giữa “giảm thời gian phân tích” và “giảm tỷ lệ hủy chuyến”, dẫn đến metric dễ bị hiểu nhầm.
- AI bỏ qua thực tế rằng log app, ghi chú tài xế và cuộc gọi CSKH có thể là dữ liệu khác dạng, nên gợi ý triển khai AI trực tiếp có thể dẫn đến sai lệch và chi phí cao.

## Sửa đổi ra sao
Để khắc phục, tôi đã:
- Thêm yêu cầu trong prompt: “Hãy đánh giá bài toán này dưới góc nhìn CFO và Trưởng phòng Vận hành cực kỳ khắt khe.”
- Yêu cầu AI chỉ ra ít nhất 3 điểm yếu về logic, metric và lý do rule-based code có thể phù hợp hơn.
- Tập trung so sánh trực tiếp giữa chi phí giờ công và giá trị kinh doanh, tránh dùng metric chung chung.

Kết quả là tôi đã có được phản biện rõ ràng hơn, giúp xác định rằng bài toán này nên bắt đầu bằng giải pháp rule-based cho phần tổng hợp và phân loại, rồi mới cân nhắc AI nếu cần xử lý văn bản tự do phức tạp hơn.
