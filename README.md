# Phân Tích Dữ Liệu Đặt Tour Du Lịch Tại Việt Nam

## Giới thiệu

Dự án sử dụng Power BI để phân tích dữ liệu đặt tour du lịch tại Việt Nam nhằm hỗ trợ doanh nghiệp đưa ra các quyết định kinh doanh dựa trên dữ liệu.

Thông qua việc phân tích doanh thu, hành vi khách hàng và mức độ hài lòng, báo cáo giúp xác định các nhóm khách hàng tiềm năng, các loại tour mang lại hiệu quả cao và các cơ hội cải thiện chất lượng dịch vụ.

## Mục tiêu phân tích

Dự án được thực hiện nhằm trả lời các câu hỏi kinh doanh sau:

- Nhóm khách hàng nào mang lại doanh thu cao nhất?
- Loại tour nào được khách hàng lựa chọn nhiều nhất?
- Điểm đến nào tạo ra doanh thu lớn nhất?
- Mức độ hài lòng của khách hàng đối với từng loại tour ra sao?
- Tỷ lệ khách hàng quay lại là bao nhiêu?
- Doanh nghiệp nên tập trung nguồn lực vào những phân khúc nào?

Kết quả phân tích sẽ hỗ trợ doanh nghiệp trong việc xây dựng chiến lược marketing, nâng cao trải nghiệm khách hàng và tối ưu hóa doanh thu.

## Nguồn dữ liệu

- Bộ dữ liệu: Vietnam Tour Bookings
- Nguồn: Kaggle
- Liên kết: https://www.kaggle.com/datasets/ngchno/vietnam-tour-bookings
- Giấy phép: CC0 1.0 Universal (Public Domain)

Bộ dữ liệu ban đầu gồm:

- 4.418 bản ghi
- 16 thuộc tính

Các trường dữ liệu chính được sử dụng trong quá trình phân tích:

| Cột dữ liệu | Mô tả |
|------------|--------|
| booking_id | Mã giao dịch |
| booking_date | Ngày đặt tour |
| customer_id | Mã khách hàng |
| cust_segment | Nhóm khách hàng |
| tour_type | Loại tour |
| destination | Điểm đến |
| revenue_vnd | Doanh thu |
| satisfaction | Điểm hài lòng |
| is_returning | Khách hàng quay lại |

## Làm sạch và chuẩn bị dữ liệu

Quá trình làm sạch dữ liệu được thực hiện bằng Power Query với các bước sau:

### 1. Loại bỏ các cột không phục vụ phân tích

Giữ lại 9 cột:

- booking_id
- booking_date
- customer_id
- cust_segment
- tour_type
- destination
- revenue_vnd
- satisfaction
- is_returning

### 2. Chuyển đổi kiểu dữ liệu

- booking_date → Date
- revenue_vnd → Decimal Number
- satisfaction → Decimal Number
- is_returning → True/False

### 3. Xử lý dữ liệu thiếu

- Loại bỏ các bản ghi thiếu doanh thu.
- Loại bỏ các bản ghi thiếu điểm hài lòng.

### 4. Chuẩn hóa dữ liệu văn bản

- Xóa khoảng trắng thừa.
- Sửa lỗi chính tả.
- Chuẩn hóa các giá trị danh mục.

### 5. Thay thế giá trị thiếu

Thay thế các giá trị:

- Blank
- Unknown
- Null
  
thành:

- Chưa xác định
