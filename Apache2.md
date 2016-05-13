# Apache 
Trong bài viết này, mình sử dụng máy chủ Ubuntu 14.04 LTS để cài đặt và cấu hình Apache

## 1. Cài đặt Apache 
```
sudo apt-get update
sudo apt-get install apache2 -y
```

Sử dụng máy khác có kết nối đến server này, truy cập vào ip của nó. Một trang index của Apache hiện ra là cài đặt thành công

<img src="http://i.imgur.com/GmykRr6.png">

## 2. Cấu hình 

#### Khởi động, ngừng dịch vụ Apache :

	sudo /etc/init.d/apache2 start #start apache
	
	sudo /etc/init.d/apache2 stop #stop apache
	
	sudo /etc/init.d/apache2 restart #restart apache
	
#### Tắt khởi động cùng hệ thống : 

	sudo update-rc.d -f apache2 remove
	
Ngược lại 

	sudo update-rc.d apache2 defaults
	
#### Listen Port
Cổng dịch vụ mặc định là 80, nếu muốn thay đổi bạn sửa `Listen 80` trong **/etc/apache2/ports**

#### Document Root
Thư mục chứa trang web mặc định tại **/var/www**, bạn có thể chuyển thành một thư mục khác bằng cách sửa file **/etc/apache2/sites-enabled/000-default**

Tìm **DocumentRoot /var/www** và chuyển thành đường dẫn đến thư mục bạn muốn (VD **DocumentRoot /home/locvx**)

Và sửa file **/etc/apache2/apache2.conf** : đổi **Directory /var/www** thành **Directory /home/locvx**

Sau mỗi sự thay đổi phải restart lại dịch vụ apache2 để cập nhật thay đổi


## 3. Sử dụng Wireshark để bắt và phân tích gói tin
- IP client : 192.168.0.5
- IP server : 192.168.0.20

Sau khi chọn interface và bắt gói tin và lọc theo `http`, mình thu được các gói request và response 

#### HTTP response 

<img src="http://i.imgur.com/gHhLGqW.png">

Sử dụng phương thức GET, HTTP version 1.1 

#### HTTP request

<img src="http://i.imgur.com/QjNUMSJ.png">

Mã trả về 200 OK 
Thông tin server : Apache 2.4.7 (Ubuntu)

## 4. Sử dụng windump
Sử dụng lệnh windump -D và mình tìm được interface cần bắt là số 3 

<img src="http://i.imgur.com/ApSmpcG.png">

Bắt 100 gói tin và lưu vào file file01.pcap

<img src="http://i.imgur.com/0rVN3Gm.png">

Đọc file với IP nguồn đã biết

<img src="http://i.imgur.com/430rY5w.png">
 
## 5. Tham khảo 

http://quantrimang.com/cai-dat-va-cau-hinh-apache-trong-ubuntu-76542

https://github.com/kieulam141/HTTP/blob/master/Lythuyet.md