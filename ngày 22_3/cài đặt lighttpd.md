# Cài đặt Lighttpd trên Ubuntu 20.04

Lighttpd là một giải pháp thay thế rất phổ biến cho các máy chủ web phổ biến trên hệ điều hành họ Unix. Nhờ đó, Chúng ta có thể tìm thấy nó có sẵn thông qua các kho lưu trữ Ubuntu 20.04 chính. Do đó, để cài đặt nó trong Ubuntu 20.04, chúng ta sẽ chỉ phải mở một thiết bị đầu cuối (Ctrl + Alt + T) và thực hiện lệnh:

**sudo apt install lighttpd**

![image](https://user-images.githubusercontent.com/101611197/159652674-a894844a-301c-4e2e-8980-1b0f9aa3a0f3.png)

## Khởi động dịch vụ lighttpd

**sudo systemctl start lighttpd**

## kiểm tra trạng thái dịch vụ lighttpd

**sudo systemctl status lighttpd**

![image](https://user-images.githubusercontent.com/101611197/159653042-a27c8ace-e2aa-42ea-9050-8f289f481105.png)

## Vào trình duyệt, truy cập vào địa chỉ ip để kiểm tra 

![image](https://user-images.githubusercontent.com/101611197/159653259-ea61e862-7119-4caf-b149-bf78bf086e28.png)

# Thêm hỗ trợ PHP vào Lighttpd

## Cài đặt php 7.4

**sudo apt install php7.4 php7.4-fpm php7.4-mysql php7.4-cli php7.4-curl php7.4-xml**

![image](https://user-images.githubusercontent.com/101611197/159653414-4a40b32c-8fb3-4736-b8ad-f6a38179f7af.png)

## Mở rộng một trong những tệp cấu hình

**sudo nano /etc/php/7.4/fpm/pool.d/www.conf**

**Thay đổi giá trị listen thành 127.0.0.1:9000**

## thực hiện nhiều thay đổi hơn đối với tệp cấu hình khác

**sudo nano /etc/lighttpd/conf-available/15-fastcgi-php.conf**

Thay đổi 2 dòng:

**"bin-path" => "/usr/bin/php-cgi",**

**"socket" => "/var/run/lighttpd/php.socket",**

Thành:

**"host" => "127.0.0.1",**

**"port" => "9000",**

![image](https://user-images.githubusercontent.com/101611197/159654235-ba4d1e74-8b9a-4957-94f0-07d26b5a98af.png)

## kích hoạt các mô-đun giúp Lighttpd hoạt động với PHP:

sudo lighty-enable-mod fastcgi
 
sudo lighty-enable-mod fastcgi-php

![image](https://user-images.githubusercontent.com/101611197/159654419-85ca6e2d-2525-4334-826b-4a08f1f2ce16.png)

## khởi động lại các dịch vụ Lighttpd và php-fpm:

# Kiểm tra xem PHP đã được kích hoạt chưa

## chúng ta sẽ viết một tệp PHP trong thư mục gốc của Lighttpd, và sau đó mở nó bằng trình duyệt.

**sudo nano /var/www/html/test.php**

Bên trong tệp dán đoạn lệnh sau:

 <?php phpinfo();?>

![image](https://user-images.githubusercontent.com/101611197/159654969-83508eba-2760-45dc-933f-f1d4cab4a9de.png)

## thay đổi quyền của thư mục và đặt Lighttpd làm chủ sở hữu của nó

**sudo chown -R www-data:www-data /var/www/html/**
 
**sudo chown -R 755 /var/www/html/**

![image](https://user-images.githubusercontent.com/101611197/159655199-ddff0a85-02fe-43d6-9f0e-3dccdf9a1bfd.png)

Bây giờ chúng ta mở trình duyệt và truy cập vào đường dẫn để kiểm tra

192.168.154.137/test.php

![image](https://user-images.githubusercontent.com/101611197/159655392-8515aecc-c6c3-4a7f-9630-d71b84ca68fe.png)
