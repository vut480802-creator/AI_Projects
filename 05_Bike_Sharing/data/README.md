# Bike Sharing — Data

## Nguồn dữ liệu

Bộ dữ liệu Bike Sharing của Capital Bikeshare, được cung cấp qua UCI Machine Learning Repository. Bộ dữ liệu ghi nhận số lượt thuê theo giờ và theo ngày trong giai đoạn 2011–2012, cùng các thông tin về thời tiết và thời gian.

- Trang dữ liệu: [UCI Bike Sharing Dataset](https://archive.ics.uci.edu/dataset/275/bike%2Bsharing%2Bdataset)
- Trích dẫn: Fanaee-T, H. (2013). *Bike Sharing* [Dataset]. UCI Machine Learning Repository. DOI: [10.24432/C5W894](https://doi.org/10.24432/C5W894).
- Giấy phép theo UCI: Creative Commons Attribution 4.0 International (CC BY 4.0). Khi chia sẻ hoặc điều chỉnh dữ liệu, cần ghi nhận nguồn.

## Các file dữ liệu
File	      Độ phân giải	      Kích thước quan sát được	         Ghi chú
hour.csv	  Theo giờ	          17.379 dòng × 17 cột gốc	         Có cột hr từ 0 đến 23
day.csv	      Theo ngày	          731 dòng × 16 cột	                 Không có cột hr

Hai file có độ phân giải khác nhau, nên được xử lý như hai chuỗi riêng. Có thể cộng cnt của hour.csv theo ngày để đối chiếu với cnt trong day.csv; không nối hai file thành một bảng theo từng dòng.

## Ý nghĩa các cột
Cột	                       Ý nghĩa
instant	                   Số thứ tự bản ghi
dteday	                   Ngày ghi nhận
season	                   Mã mùa: 1 = đông, 2 = xuân, 3 = hè, 4 = thu
yr	                       Mã năm: 0 = 2011, 1 = 2012
mnth	                   Tháng, từ 1 đến 12
hr	                       Giờ trong ngày, từ 0 đến 23; chỉ có trong hour.csv
holiday	                   Cờ ngày lễ
weekday	                   Mã thứ trong tuần: 0 = Chủ nhật đến 6 = Thứ bảy
workingday	               1 nếu là ngày làm việc; 0 nếu là cuối tuần hoặc ngày lễ
weathersit	               Mã tình trạng thời tiết, từ 1 (thuận lợi hơn) đến 4 (bất lợi hơn)
temp	                   Nhiệt độ đã chuẩn hóa
atemp	                   Nhiệt độ cảm nhận đã chuẩn hóa
hum	                       Độ ẩm đã chuẩn hóa
windspeed	               Tốc độ gió đã chuẩn hóa
casual	                   Số lượt thuê của người dùng không đăng ký
registered	               Số lượt thuê của người dùng đã đăng ký
cnt	                       Tổng lượt thuê; bằng casual + registered


Các biến thời tiết là giá trị đã chuẩn hóa, không phải đơn vị đo gốc.

## Ghi chú chất lượng dữ liệu
Trong EDA của hour.csv, không phát hiện giá trị null, dòng trùng hoàn toàn hoặc timestamp trùng. Khi tạo lịch liên tục theo giờ từ đầu đến cuối giai đoạn, có 165 giờ không có dòng ghi nhận. Tổng cnt theo giờ vẫn khớp với day.csv ở cả 731 ngày.

Trong notebook, cột timestamp được tạo bằng cách kết hợp dteday và hr; cột này không có sẵn trong file CSV gốc. Khi dựng lại lịch giờ, chỉ các cột lượt thuê (cnt, casual, registered) được điền 0 tại giờ vắng dòng. Không tự điền 0 cho các đặc trưng thời tiết.

Nếu mô hình dự đoán cnt, không dùng casual và registered làm đầu vào vì chúng cộng lại thành biến mục tiêu. instant cũng không nên dùng làm đặc trưng dự báo.