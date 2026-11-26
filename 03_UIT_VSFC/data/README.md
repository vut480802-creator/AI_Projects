# UIT-VSFC Data

## Tổng quan

Dữ liệu trong thư mục này thuộc UIT-VSFC (Vietnamese Students’ Feedback Corpus), bộ dữ liệu phản hồi tiếng Việt được gán nhãn cho hai tác vụ: phân loại cảm xúc và phân loại chủ đề. Nguồn tải được dùng trong project là [UIT-VSFC trên Hugging Face](https://huggingface.co/datasets/uitnlp/vietnamese_students_feedback).

Theo kết quả kiểm tra trong notebook EDA, dữ liệu có **16.175 câu**, mỗi câu gồm nội dung văn bản, nhãn cảm xúc và nhãn chủ đề.

## Các cột dữ liệu
Cột	                   Mô tả
sentence	           Câu phản hồi bằng tiếng Việt
sentiment	           Mã nhãn cảm xúc
topic	               Mã nhãn chủ đề


Mã nhãn theo schema của bộ dữ liệu:
- sentiment: 0 = Negative, 1 = Neutral, 2 = Positive
- topic: 0 = Lecturer, 1 = Training program, 2 = Facility, 3 = Others

## Kích thước các tập
Tập	             Số câu
Train	         11.426
Validation	     1.583
Test	         3.166
Tổng	         16.175

Giữ nguyên cách chia này khi huấn luyện và đánh giá mô hình.

## Ghi chú EDA
- Không phát hiện giá trị thiếu hoặc câu rỗng.
- Có một câu lặp trong tập train nhưng mang hai nhãn cảm xúc trái ngược nhau; xem chi tiết trong notebooks/03_EDA.ipynb.
- Số lượng mẫu giữa các nhãn không đồng đều, đặc biệt với nhãn Neutral và một số chủ đề.

## Nguồn 
- Dataset: uitnlp/vietnamese_students_feedback
- Bài báo giới thiệu bộ dữ liệu: UIT-VSFC: Vietnamese Students’ Feedback Corpus for Sentiment Analysis (2018).
