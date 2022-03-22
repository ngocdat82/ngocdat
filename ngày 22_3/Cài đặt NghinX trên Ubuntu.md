# Bước 1: Cài đặt Nginx

Vì Nginx có sẵn trong kho lưu trữ của Ubuntu nên ta có thể trực tiếp cài đặt Nginx bằng hệ thống cài đặt và quản lý gói apt.

Đầu tiên, tiến hành update các gói trong hệ thống :

**sudo apt install -y update**

![image](https://user-images.githubusercontent.com/101611197/159393628-3bb8f87c-fd3a-4ba5-a5d8-a59981e4b32f.png)

Cài đặt Nginx cho máy chủ Ubuntu :

**sudo apt install -y nginx**

![image](https://user-images.githubusercontent.com/101611197/159393903-d20dc0ee-2935-4e4e-b4ca-8f18fa90771f.png)

Kiểm tra phiên bản Nginx:

**sudo nginx -v**

![image](https://user-images.githubusercontent.com/101611197/159394159-ecfc7d02-5ba7-43e6-8851-458bbd8be781.png)

Cho phép Nginx khởi động cùng hệ thống :

**sudo systemctl enable nginx**

Khởi động và kiểm tra trạng thái của dịch vụ Nginx :

**systemctl start nginx **

**systemctl status nginx**

![image](https://user-images.githubusercontent.com/101611197/159394295-9fb66a58-6952-4022-8951-ff271eb4adb8.png)

# Bước 2: Cấu hình tường lửa

Sử dụng ufw để biết cách sử dụng cấu hình tường lửa cho Nginx :

**sudo ufw app list **

nó sẽ có đầu ra như sau :

![image](https://user-images.githubusercontent.com/101611197/159394550-aef1227f-585c-4126-a769-c75373008d43.png)

Ta thấy rằng đối với nginx, có 3 cấu hình có thể để cấu hình cho nginx, nhưng hiện tại mình chưa có cấu hình sử dụng SSL đối với trang web nên mình chỉ cho lưu lượng đi qua port 80.

Kích hoạt điều trên bằng cách sử dụng câu lệnh sau:

sudo ufw allow 'Nginx HTTP'

# Bước 3: Kiểm tra trang web

Để kiểm tra trang web, ta mở trình duyệt và nhập vào địa chỉ ip của máy chủ Nginx.

![image](https://user-images.githubusercontent.com/101611197/159401237-5021ef2c-3dc1-4da0-b650-c48861ba4b46.png)

