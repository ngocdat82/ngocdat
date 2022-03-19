# Cài đặt Apache trên CentOS 7

## 1. Điều kiện

Trước khi bắt đầu, hãy đảm bảo rằng bạn có một VPS trắng và chưa cài đặt bất cứ dịch vụ nào.

### 2. Cài đặt Apache trên CentOS 7

#### 2.1. Bước 1: Cài đặt Apache

Apache có sẵn trong kho lưu trữ CentOS mặc định nên việc cài đặt khá đơn giản. Để cài đặt Apache hãy chạy lệnh sau:

**yum install httpd -y**

![image](https://user-images.githubusercontent.com/101611197/158959171-ca96b91c-4c5c-4281-9128-c0e13bc39381.png)

#### 2.2. Bước 2: Khởi động Apache

Khi quá trình cài đặt hoàn tất, chúng ta bật và khởi động dịch vụ Apache bằng các lệnh sau:

**systemctl enable httpd**

**systemctl start httpd**

![image](https://user-images.githubusercontent.com/101611197/158959414-a30748ff-6c69-482a-8e31-b42a1f539ecb.png)

Để kiểm tra trạng thái của Apache ta sử dụng lệnh sau:

**systemctl status httpd**

![image](https://user-images.githubusercontent.com/101611197/158959562-4c0ec879-b19b-42fb-93a1-0fca42e26700.png)

#### 2.3. Bước 3: Cấu hình Firewalld (Nếu có)

để có thể truy cập được website chúng ta sẽ cần mở port bằng các lệnh sau đây

**firewall-cmd --permanent --zone=public --add-service=http**

**firewall-cmd --permanent --zone=public --add-service=https**

**firewall-cmd --reload**

![image](https://user-images.githubusercontent.com/101611197/158959979-ccc7544c-964c-4cef-8307-693fcd6dcc57.png)

### 3. Quản lý Apache Service với systemctl

Để dừng Apache, dùng lệnh:  **systemctl stop httpd**

Để khởi động Apache dùng lệnh: **systemctl start httpd**

Lệnh khởi động lại Apache: **systemctl restart httpd**

Tải lại dịch vụ Apache mỗi khi bạn thay đổi cấu hình: **systemctl reload httpd**

Nếu không muốn Apache tự động chạy mỗi khi khởi động lại VPS sử dụng lệnh sau: **systemctl disable httpd**

Nếu muốn Apache tự động chạy mỗi khi khởi động lại VPS sử dụng lệnh sau: **systemctl enable httpd**

![image](https://user-images.githubusercontent.com/101611197/158960618-d1408e28-40a7-4f48-8260-15b63e4e77ac.png)


### 4. Các file cấu hình

- Tất cả các file cấu hình của Apache đều nằm trong thư mục **/etc/httpd.**

- File cấu hình chính của Apache là **/etc/httpd/conf/httpd.conf.**

- Tất cả các tệp cấu hình đều phải kết thúc bằng **.conf** và nằm trong thư mục **/etc/httpd/conf.d**.

- Các tệp cấu hình chịu trách nhiệm tải các modules Apache được đặt trong thư mục **/etc/httpd/conf.modules.d.**

- Để quản lý tốt hơn, nên tạo một tệp cấu hình riêng (vhost) cho mỗi tên miền.

- Các tệp vhost Apache phải kết thúc bằng **.conf** và được lưu trữ trong thư mục **/etc/httpd/conf.d.** Ví dụ: nếu tên miền của chúng ta là mydomain.com thì tệp cấu hình sẽ được đặt tên /etc/httpd/conf.d/mydomain.com.conf

- Các file log của Apache (access_log và error_log) nằm trong thư mục /var/log/httpd/. Bạn nên có file log riêng cho mỗi vhost.

### 5. Tạo Virtualhost (Vhost)
#### 5.1. Bật userdir
Mặc định thư mục chứa code sẽ nằm trong /var/www/html, với chức năng userdir cho phép di chuyển thư mục chứa code sang vị trí khác đồng thời dễ dàng quản lý vhost theo từng user.

Để bật Userdir các bạn mở file /etc/httpd/conf.d/userdir.conf.

Dùng Nano Editor để chỉnh sửa

**nano /etc/httpd/conf.d/userdir.conf**

![image](https://user-images.githubusercontent.com/101611197/158962686-7ce3a866-6908-45d2-975f-69eddfd7d91f.png)

Tại đây chúng ta cần sửa các rules sau

**UserDir disabled**

**#UserDir public_html**

Sửa lại thành như sau

**#UserDir disabled**

**UserDir public_html**

![image](https://user-images.githubusercontent.com/101611197/158963933-04836433-f802-40aa-903d-62e4138c1e10.png)

![image](https://user-images.githubusercontent.com/101611197/158964056-a5bd407e-5396-47b8-9672-7c614bd285de.png)

Tiếp theo chúng ta tìm đoạn rule sau

**<Directory "/home/*/public_html">
    AllowOverride FileInfo AuthConfig Limit Indexes
    Options MultiViews Indexes SymLinksIfOwnerMatch IncludesNoExec
    Require method GET POST OPTIONS
</Directory>**

Sửa nó lại thành như sau:

**<Directory "/home/*/public_html">
    AllowOverride All
    Options None
    Require method GET POST OPTIONS
</Directory>**

![image](https://user-images.githubusercontent.com/101611197/158965232-b8f2ad22-906f-4886-a7bb-54006f4bbfad.png)

#### 5.2. Chặn truy cập IP VPS tự động redirect về website trên VPS
Theo mặc định thì khi truy cập IP của VPS hoặc khi trỏ một tên miền về VPS mà tên miền này không được cấu hình vhost thì bạn sẽ được redirect tới một website bất kỳ trên VPS, điều này là không nên và để hạn chế điều này các bạn mở file **/etc/httpd/conf/httpd.conf**

Sử dụng lệnh:

**nano /etc/httpd/conf/httpd.conf**

Thêm phía trên dòng IncludeOptional conf.d/*.conf rules sau:

![image](https://user-images.githubusercontent.com/101611197/158966538-936b7402-066d-43a4-86b2-906426b1fed4.png)

#### 5.3. Tạo virtual host (vhost) cho website

**Virtual Host** là file cấu hình trong Apache để cho phép nhiều domain cùng chạy trên một máy chủ. Có một khái niệm khác được đề cập tới trong Nginx cũng có chức năng tương tự như Virtual Host được gọi là **Server Block.**

Tất cả các file vhost sẽ nằm trong thư mục **/etc/httpd/conf.d/**. Để tiện quản lý mỗi website nên có một vhost riêng, ví dụ: **hostvn.net.conf**

Trong ví dụ này sẽ tạo website **ngocdat.net** với vhost tương ứng là **/etc/httpd/conf.d/ngocdat.net.conf**

**nano /etc/httpd/conf.d/ngocdat.net.conf** 

Dán nội dung sau vào

<VirtualHost *:80>

	ServerName www.ngocdat.net
  
	ServerAlias hostvn.net
  
	DocumentRoot /home/ngocdat.net/public_html
  
	ErrorLog /home/ngocdat.net/logs/error_log
  
	CustomLog /home/ngocdat.net/logs/access_log combined
  
</VirtualHost>

Tiếp theo chúng ta cần tạo thư mục chứa mã nguồn website và thư mục chứa file log bằng các lệnh sau

**mkdir -p /home/ngocdat.net/public_html**

**mkdir -p /home/ngocdat.net/logs**

**chown -R apache:apache /home/ngocdat.net**

Reload lại Apache để cập nhật cấu hình

**systemctl reload httpd**

Sau khi cấu hình hoàn tất các bạn trỏ tên miền về vps sau đó tạo file /home/ngocdat.net/public_html/index.html

**nano /home/ngocdat.net/public_html/index.html**

Dán nội dung sau vào

<!DOCTYPE html>
<html lang="en">
<head>
	<meta charset="UTF-8">
	<title>hh</title>
</head>
<body>
	<p><center><?= "Hello moi nguoi" ?></center></p>
</body>
</html>


Truy cập tên miền của bạn bằng trình duyệt để kiểm tra


![image](https://user-images.githubusercontent.com/101611197/159105622-319de4c5-7afe-432e-b8f4-304199b0c900.png)
