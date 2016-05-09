# HTTP
ghi chép về HTTP

## 1. Tổng quan 
**HTTP** (hypertext transfer protocol) là giao thức tầng ứng dụng cho Web.

Sử dụng mô hình Client-Server 
	- Client : trình duyệt yêu cầu, nhận và hiển thị các đối tượng Web
	- Server : Web server gửi các đối tượng web trong các đáp ứng yêu cầu 

## 2. Kết nối HTTP
Chia làm 2 loại : Kết nối liên tục và kết nối không liên tục 

##### Không liên tục 
Nhiều nhất một đối tượng được gửi trong một kết nối TCP 

HTTP/1.0 sử dụng kết nối không liên tục

Hệ điều hành phải làm việc và cấp phát tài nguyên cho mỗi kết nối TCP, nhưng các trình duyệt thường mở nhiều kết nối TCP song song để yêu cầu các đối tượng tham chiếu. 

##### Liên tục 
Nhiều đối tượng có thể được gửi trong một kết nối TCP

HTTP/1.1 mặc định sử dụng kết nối liên tục 

Server để các kết nối mở sau khi gửi các response, các thông báo tiếp sau được gửi qua kết nối. 

## 3. HTTP request 
Cấu trúc thông điệp HTTP request

<img src="http://i.imgur.com/rdwliuE.png">

Ví dụ :

<img src="http://i.imgur.com/Lsa8ff8.png">

#### Method 
- POST : Trang web có form nhập, dữ liệu đẩy lên server trong thân của HTTP request
- GET : Dữ liệu đẩy lên theo URL 
- HEAD : Yêu cầu server bỏ qua đối tượng được yêu cầu 
- PUT : Đẩy tệp trong thân lên thư mục được xác định bởi URL (có thêm ở HTTP/1.1)
- DELETE : Xóa tệp được xác định bởi URL (có thêm ở HTTP/1.1)

## 4. HTTP response 
Cấu trúc thông điệp HTTP response

<img src="http://i.imgur.com/VlsUNjX.png">

Ví dụ :

<img src="http://i.imgur.com/XdMvWXn.png">

#### Mã trạng thái HTTP response
- **200 OK**: Yêu cầu thành công, đối tượng được yêu cầu chứa ở phần sau của thông báo
- **301 Moved Permanently**: Đối tượng yêu cầu đã bị chuyển, thư mục mới của đối tượng được xác định ở phía sau
- **400 Bad request**: Không hiểu yêu cầu
- **404 Not found**: Không tìm thấy đối tượng được yêu cầu
- **HTTP version not supported**:
## 5. Cookies

## 6. Web caches (proxy server)

## 7. Web server

## 8. Tham khảo 
