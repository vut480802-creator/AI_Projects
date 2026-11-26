# Concrete Compressive Strength Prediction

## Giới thiệu

Project xây dựng mô hình hồi quy để dự đoán cường độ chịu nén của bê tông dựa trên thành phần cấp phối và tuổi bê tông.

Bộ dữ liệu có 1.030 mẫu, gồm 8 đặc trưng định lượng và một biến mục tiêu. Đơn vị cường độ chịu nén là MPa. Nguồn dữ liệu và mô tả đầy đủ được ghi trong [UCI Machine Learning Repository](https://archive.ics.uci.edu/dataset/165/concrete-compressive-strength).

## Đặc trưng và biến mục tiêu

Các đặc trưng đầu vào:

- Cement
- Blast Furnace Slag
- Fly Ash
- Water
- Superplasticizer
- Coarse Aggregate
- Fine Aggregate
- Age

Biến mục tiêu:

- `concrete_compressive_strength`: cường độ chịu nén của bê tông, tính bằng MPa.

## Ghi chú EDA
- Bản dữ liệu được kiểm tra có 1.030 dòng, không có giá trị thiếu hoặc giá trị âm.
- Có 25 dòng trùng hoàn toàn và 34 dòng có bộ đặc trưng đã xuất hiện trước đó. Trong đó, 9 bộ đặc trưng có nhiều giá trị target; cần xác minh các trường hợp chênh lệch lớn với dữ liệu gốc trước khi quyết định xử lý.
- Các mối liên hệ được ghi nhận trong EDA chỉ mô tả dữ liệu, không khẳng định quan hệ nhân quả.
- Khi đánh giá mô hình, cần cân nhắc giữ các bản ghi cùng bộ đặc trưng trong cùng một tập dữ liệu để hạn chế rò rỉ giữa train và test.

## Đánh giá mô hình
Các chỉ số dự kiến sử dụng cho bài toán hồi quy:
- MAE
- RMSE
- R²
Kết quả mô hình sẽ được bổ sung sau khi hoàn tất huấn luyện và đánh giá.
Trích dẫn dữ liệu
Yeh, I. (1998). Concrete Compressive Strength [Dataset]. UCI Machine Learning Repository. https://doi.org/10.24432/C5PK67.
