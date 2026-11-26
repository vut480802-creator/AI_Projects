# Credit Default Dataset

## Tổng quan

Bộ dữ liệu chứa thông tin về khách hàng thẻ tín dụng tại Đài Loan, dùng cho bài toán phân loại nhị phân: dự đoán khách hàng có vỡ nợ trong kỳ tiếp theo hay không.

- Số dòng: 30.000
- Số đặc trưng: 23
- Ngoài các đặc trưng, file có cột `ID` và cột mục tiêu.
- Định dạng file gốc: Excel `.xls`

## File trong thư mục

- `raw/default of credit card clients.xls`: dữ liệu gốc tải từ UCI.
- `processed/`: nơi lưu dữ liệu đã qua xử lý nếu project tạo ra. Dữ liệu gốc trong `raw/` nên được giữ nguyên.

## Nguồn dữ liệu

- Tên bộ dữ liệu: **Default of Credit Card Clients**
- Nguồn: [UCI Machine Learning Repository](https://archive.ics.uci.edu/dataset/350/default%2Bof%2Bcredit%2Bcard%2Bclients%2Bdataset)
- Trích dẫn: Yeh, I. (2009). *Default of Credit Card Clients* [Dataset]. UCI Machine Learning Repository. https://doi.org/10.24432/C55S3H

## Cột mục tiêu

Tên cột trong file gốc là `default payment next month`. Sau khi chuẩn hóa tên cột trong notebook, tên được dùng là `default_payment_next_month`.

- `1`: khách hàng vỡ nợ trong kỳ tiếp theo.
- `0`: khách hàng không vỡ nợ trong kỳ tiếp theo.

## Mô tả các cột

| Cột | Mô tả |
|---|---|
| `ID` | Mã định danh khách hàng; không dùng làm đặc trưng dự đoán. |
| `LIMIT_BAL` | Hạn mức tín dụng được cấp, tính bằng Đô la Đài Loan (NT dollar). |
| `SEX` | Mã giới tính: `1` = nam, `2` = nữ. |
| `EDUCATION` | Mã học vấn: `1` = sau đại học, `2` = đại học, `3` = trung học phổ thông, `4` = nhóm khác. |
| `MARRIAGE` | Mã tình trạng hôn nhân: `1` = đã kết hôn, `2` = độc thân, `3` = nhóm khác. |
| `AGE` | Tuổi khách hàng, tính bằng năm. |
| `PAY_0`, `PAY_2`–`PAY_6` | Mã trạng thái thanh toán trong các kỳ từ tháng 9 đến tháng 4 năm 2005. `PAY_0` tương ứng tháng 9; `PAY_2` tháng 8; tiếp tục theo thứ tự đến `PAY_6` tháng 4. Theo mô tả UCI, `-1` là thanh toán đúng hạn; `1`–`9` biểu thị số tháng chậm thanh toán. |
| `BILL_AMT1`–`BILL_AMT6` | Số tiền trên sao kê hóa đơn theo các kỳ từ tháng 9 đến tháng 4 năm 2005, tính bằng NT dollar. |
| `PAY_AMT1`–`PAY_AMT6` | Số tiền thanh toán trước đó theo các kỳ từ tháng 9 đến tháng 4 năm 2005, tính bằng NT dollar. |
| `default payment next month` | Biến mục tiêu trong file gốc; `1` = có vỡ nợ, `0` = không vỡ nợ. |

## Lưu ý khi phân tích

- `ID` là mã định danh, không phải đặc trưng có ý nghĩa dự đoán.
- `SEX`, `EDUCATION`, `MARRIAGE` và các cột `PAY_*` chứa mã rời rạc; không nên diễn giải chúng như các đại lượng liên tục thông thường.
- Bản dữ liệu có các mã `EDUCATION` ngoài `1`–`4` và `MARRIAGE` ngoài `1`–`3`. Cần kiểm tra data dictionary trước khi gán ý nghĩa hoặc gộp các mã này.
- Notebook chuẩn hóa tên cột thành chữ thường và dùng dấu gạch dưới; ví dụ `LIMIT_BAL` thành `limit_bal`.
- Trong bản dữ liệu đã kiểm tra bằng EDA, không phát hiện giá trị thiếu, dòng trùng hoàn toàn hoặc ID trùng.