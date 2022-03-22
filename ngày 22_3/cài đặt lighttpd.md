# Cài đặt Lighttpd trên Ubuntu 20.04

Lighttpd là một giải pháp thay thế rất phổ biến cho các máy chủ web phổ biến trên hệ điều hành họ Unix. Nhờ đó, Chúng ta có thể tìm thấy nó có sẵn thông qua các kho lưu trữ Ubuntu 20.04 chính. Do đó, để cài đặt nó trong Ubuntu 20.04, chúng ta sẽ chỉ phải mở một thiết bị đầu cuối (Ctrl + Alt + T) và thực hiện lệnh:

**sudo apt install lighttpd**

![image](https://user-images.githubusercontent.com/101611197/159440872-625d0bb0-6df6-43f6-b2a4-d90cf597b0d2.png)

Bật dịch vụ Lighttpd 

**sudo systemctl start lighttpd**

Xem trạng thái của dịch vụ

**sudo systemctl stop lighttpd**

 mở trình duyệt web và truy cập http://localhost để kiểm tra
 
 ![image](https://user-images.githubusercontent.com/101611197/159441417-2b235515-dbc6-49ee-a0e2-393ddbc4ecb9.png)

Thêm hỗ trợ PHP vào Lighttpd

chúng ta sẽ cần cài đặt PHP để các trang web động có thể được thông dịch

**sudo apt install php7.4 php7.4-fpm php7.4-mysql php7.4-cli php7.4-curl php7.4-xml**

![image](https://user-images.githubusercontent.com/101611197/159442320-43981751-7ece-4f72-bcf5-39a08ddca406.png)


Khi quá trình cài đặt PHP hoàn tất, cần thực hiện một số thay đổi nhỏ để Lighttpd có thể hoạt động với PHP và thông dịch các trang web. Điều đầu tiên sẽ là mở một trong những tệp cấu hình với trình soạn thảo

**sudo nano /etc/php/7.4/fpm/pool.d/www.conf**

Y bên trong tệp thay đổi giá trị của 'Listen' a: **listen = 127.0.0.1:9000**

![image](https://user-images.githubusercontent.com/101611197/159443177-972a169d-d889-4917-87c6-66a758d6032e.png)

Thực hiện thay đổi với những tệp cấu hình khác:

**sudo nano /etc/lighttpd/conf-available/15-fastcgi-php.conf**

Và bên trong chúng ta sẽ thay đổi những dòng sau:

**"bin-path" => "/usr/bin/php-cgi",**

**"socket" => "/var/run/lighttpd/php.socket",**



