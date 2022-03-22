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

# Bước 4: Cài đặt PHP

Để cài đặt PHP và các module cần thiết cho WordPress thì chạy lênh bên dưới:

![image](https://user-images.githubusercontent.com/101611197/159445018-b84c0b00-52a1-425a-b8f4-dd35ad247d15.png)

Còn cho Laravel thì chạy lệnh bên dưới

Kiểm tra hoạt động của dịch vụ php-fpm

![image](https://user-images.githubusercontent.com/101611197/159445371-ebddf9f2-d982-495a-8e2e-6abf16e471b2.png)

# Bước 5: Cài đặt CSDL MariaDB

MariaDB là CSDL quan hệ đang được sử dụng phổ biến. Nó chạy rất ổn định và là CSDL đang được ưa chuộng

Để cài đặt MariaDB trên Ubuntu, đầu tiên chúng ta truy cập địa chỉ

**https://downloads.mariadb.org/mariadb/repositories/**

Và thực hiện các bước sau:

Chọn hệ điều hành, VD: Ubuntu

Chọn phiên bản của HDH, VD: Ubuntu 20.04 “focal”

Chọn phiên bản của MariaDB: VD: 10.5 [Stable]

Chọn nơi lưu trữ phần mềm

![image](https://user-images.githubusercontent.com/101611197/159445997-0b7e9175-a0b7-44e5-a93b-8359f9a78bae.png)

Kết quả sau khi lựu chọn, trang web sẽ hiển thị các câu lệnh giúp bạn cài đặt dễ dàng trên phiên bản HDH mà bạn đã lựu chọn

Đầu tiên chúng ta cài đặt các package cần thiết

**sudo apt-get install software-properties-common dirmngr apt-transport-https**

![image](https://user-images.githubusercontent.com/101611197/159446212-cdce62d3-bed2-438f-9db0-738e34c75796.png)

Sau đó thêm key cho MariaDB

**sudo apt-key adv --fetch-keys 'https://mariadb.org/mariadb_release_signing_key.asc'**

![image](https://user-images.githubusercontent.com/101611197/159446356-0d5eabad-ec8f-47ee-9906-03adfdf9a0f3.png)

Thêm repository vào Server

**sudo add-apt-repository 'deb [arch=amd64,arm64,ppc64el,s390x] https://mirrors.bkns.vn/mariadb/repo/10.5/ubuntu focal main'**

![image](https://user-images.githubusercontent.com/101611197/159446519-e05eedc4-42a5-436b-9f84-708087f36be0.png)

Cập nhật mới lại các package

sudo apt update

![image](https://user-images.githubusercontent.com/101611197/159446634-a903da71-769a-4cc0-83f2-f241004a8ab6.png)

Cuối cùng là cài đặt MariaDB Server

**sudo apt install mariadb-server**

![image](https://user-images.githubusercontent.com/101611197/159446761-1728bb94-1baf-47bb-9ca9-6f41dcf0f032.png)

Kiểm tra dịch vụ MariaDB đã hoạt động chưa?

**sudo systemctl status mariadb**

![image](https://user-images.githubusercontent.com/101611197/159447583-d7741c2e-f68f-4f2c-8a35-d736f2fd6dba.png)

Để đảm bảo tính bảo mật thì chúng ta nên đổi mật khẩu tài khoản root của MariaDB

Đầu tiên đăng nhập tài khoản root với mật khẩu là rỗng

![image](https://user-images.githubusercontent.com/101611197/159447692-c1a51b46-bdfe-4299-b46c-e45619be87e4.png)

Update lại mật khẩu cho user root bằng lệnh SQL dưới đây

ALTER USER 'root'@'localhost' IDENTIFIED BY 'YOUR_NEW_PASSWORD';

FLUSH PRIVILEGES;

![image](https://user-images.githubusercontent.com/101611197/159447915-16273071-cf13-4dca-9532-0ab6bec33239.png)

# Bước 6: Cài đặt Redis Cache

Để cài đặt Redis Cache chúng ta sử dụng command bên dưới

**sudo apt -y install redis-server redis-tools**

![image](https://user-images.githubusercontent.com/101611197/159448135-ce447dbe-92ed-44b4-88b9-6597ca49c507.png)

Xác nhận dịch vụ Redis đang hoạt động

**sudo systemctl status redis-server**

![image](https://user-images.githubusercontent.com/101611197/159448414-e4d93a23-dde0-44eb-8418-e51fbf8260b0.png)

Kiểm tra bằng redis-cli với lệnh ping

![image](https://user-images.githubusercontent.com/101611197/159448599-4587f087-1319-468d-813e-a4d431b3a04d.png)

# Bước 7 Tạo swap trên Ubuntu

Việc tạo swap này sẽ giúp cho Ubuntu hoạt động mượt mà với 1 số dịch vụ cần swap như MariaDB hay MySQL

**sudo fallocate -l 1G /swapfile**

**sudo chmod 600 /swapfile**

**sudo mkswap /swapfile**

**sudo swapon /swapfile**

**sudo cp /etc/fstab /etc/fstab.bak**

**echo '/swapfile none swap sw 0 0' | sudo tee -a /etc/fstab**

Sau đó sửa file /etc/sysctl.conf, thêm mấy dòng sau vào:

**vm.swappiness=10**

**vm.vfs_cache_pressure=50**

Xác nhận swap được tạo bằng lệnh “free -m”

![image](https://user-images.githubusercontent.com/101611197/159449427-7a540526-7490-4d71-b288-731d5942d9ca.png)

# Bước 8 Cấu hình Nginx chạy PHP

Sau khi đã cài đặt hết tất cả dịch vụ chúng ta thực hiện cấu hình Nginx để chạy Web Server

Sửa file: /etc/nginx/sites-available/default

1 Thêm index.php vào mục index

2 Mở comment phần location php

![image](https://user-images.githubusercontent.com/101611197/159456408-c3c648d9-9e31-436b-884a-d19bcb530bf0.png)







