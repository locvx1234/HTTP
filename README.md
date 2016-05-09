# HTTP
ghi chép về HTTP

## 1. Tổng quan 
**HTTP** (hypertext transfer protocol) là giao thức tầng ứng dụng cho Web.

Sử dụng mô hình Client-Server :

- **Client** : trình duyệt yêu cầu, nhận và hiển thị các đối tượng Web
- **Server** : Web server gửi các đối tượng web trong các đáp ứng yêu cầu 

## 2. Kết nối HTTP
Có 2 loại : Kết nối liên tục và kết nối không liên tục 

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
- **HTTP version not supported**: Phiên bản HTTP không hỗ trợ

## 5. Cookies
Cookie là một bản ghi được tạo ra và lưu trên trình duyệt. 

<img src="http://i.imgur.com/VzeiuAo.png">

Khi người dùng truy cập vào một website, server tạo một ID cookie cho người dùng. Cookie sẽ ghi nhớ những thông tin như username, password, các lựa chọn của người dùng. Client sẽ sử dụng cookie được cấp để sử dụng những thông tin trong những lần truy cập tiếp theo.

## 6. Web caches (proxy server)
Web caches được sử dụng để đáp ứng yêu cầu cho client mà không cần server gốc làm việc.

Trình duyệt gửi HTTP request tới web cache. Nếu đối tượng ở trong cache, cache sẽ gửi đối tượng cho trình duyệt. Ngược lại cache gửi yêu cầu tới server gốc, nhận trả lời rồi gửi đối tượng cho client đồng thời lưu vào cache.

<img src="http://i.imgur.com/vHaejwa.png">

#### Lợi ích của việc sử dụng cache:
- Giảm thời gian đáp ứng yêu cầu của client
- Giảm lưu lượng trên các liên kết
- Giảm tải cho server
- Internet với nhiều cache cho phép các ISP truyền tải nội dung hiệu quả

## 7. Web server
Web server là máy chủ có dung lượng lớn, tốc độ cao, có chức năng gửi các trang Web đến máy khách qua giao thức HTTP.
Để thực hiện được chức năng này, máy chủ cần cài đặt phần mềm phục vụ web. 

Tất cả các web server đểu hiểu file .htm và .html. Tuy nhiên mỗi web server software lại phục vụ một số kiểu file chuyên biệt như IIS dành cho .asp, .aspx,...; Apache dành cho .php,...; Sun Java system dành cho .jsp...

Bài viết [sau](https://github.com/locvx1234/HTTP/blob/master/Apache2.md) sẽ hướng dẫn về việc cài đặt và cấu hình Apache trên máy chủ Ubuntu.

## 8. Tham khảo 
Book : Computer Networking A Top-Down Approach 6th-edition - Kurose Ross.

http://servergiarenhat.com/web-server-la-gi-tong-quan-ve-web-server/