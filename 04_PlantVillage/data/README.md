# PlantVillage Data

## Tổng quan

Thư mục này chứa dữ liệu ảnh lá cây dùng trong project PlantVillage. Mỗi ảnh được xếp vào thư mục theo nhãn, kết hợp tên cây và tình trạng của lá.

Theo kết quả kiểm tra trong notebook EDA, bộ dữ liệu có **54.381 ảnh JPG**, được chia thành **38 lớp**, gồm **14 loại cây** và **21 tình trạng**. Ảnh có kích thước **256 × 256 pixel** và chế độ màu **RGB**.

Tên thư mục lớp thường có dạng:
<Tên cây>___<Tình trạng>
Ví dụ: Tomato___healthy, Potato___Late_blight.

## Kết quả kiểm tra dữ liệu
- Tổng số ảnh: 54.381
- Số lớp: 38
- Định dạng: JPG
- Kích thước: 256 × 256 pixel
- Chế độ màu: RGB
- Ảnh lỗi phát hiện được: 0
- File rỗng: 0
- Số ảnh mỗi lớp dao động từ 152 đến 5.507
Số lượng ảnh giữa các lớp không đồng đều. Khi chia dữ liệu và đánh giá mô hình, cần lưu ý tình trạng mất cân bằng lớp.

# Lưu ý
Không chỉnh sửa hoặc ghi đè ảnh trong raw/. Các kết quả EDA và thông tin về cách sử dụng dữ liệu được ghi trong notebook notebooks/04_EDA.ipynb.