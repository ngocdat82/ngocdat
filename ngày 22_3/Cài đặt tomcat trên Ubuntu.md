# Cài đặt tomcat trên Ubuntu

## Bước 1: Cài đặt JDK

**sudo apt-get install default-jdk**

![image](https://user-images.githubusercontent.com/101611197/159604485-77c13e21-c9d1-4733-a932-b62a5021f86c.png)

## Bước 2: Kiểm tra Java đã được cài đặt hay chưa

**Java -version**

![image](https://user-images.githubusercontent.com/101611197/159604768-765d8c14-e286-4db3-aeb2-3a6cc03d0840.png)

## Bước 3: Cài đặt tomcat
### 3.1 Truy cập trang web **https://tomcat.apache.org/**

![image](https://user-images.githubusercontent.com/101611197/159605085-aa45530b-0656-4c58-af81-5b0a6ace8608.png)

Chọn Tomcat 9 => 9.0.60 

![image](https://user-images.githubusercontent.com/101611197/159605163-4bbe1d37-d209-432f-91a4-b13d415bca45.png)

Nhấn chuột phải và chọn **copy link**
### 3.2 Download gói cài đặt tomcat

![image](https://user-images.githubusercontent.com/101611197/159605805-a11746c8-8d17-41d0-88f7-7dd06ae89b21.png)

**wget https://dlcdn.apache.org/tomcat/tomcat-9/v9.0.60/bin/apache-tomcat-9.0.60.tar.gz**

### 3.3 Giải nén gói cài đặt vừa tải về

![image](https://user-images.githubusercontent.com/101611197/159606099-29daf991-a69b-4f89-a3a4-5aa289b86dc4.png)

**tar -xzf apache-tomcat-9.0.60.tar.gz**

### 3.4 Di chuyển file đã giải nén vào thư mục tùy chọn

Tạo thư mục: **sudo mkdir /opt/tomcat**

Di chuyển các mục vào thư mục vừa tạo: mv apache-tomcat-9.0.60/* /opt/tomcat/ 

![image](https://user-images.githubusercontent.com/101611197/159608272-d140753b-1360-4153-9add-502279077e47.png)

### 3.5 kiểm tra các tệp đã được chuyển đến thư mục chưa

**cd /opt/tomcat/**

**ls**

![image](https://user-images.githubusercontent.com/101611197/159608750-86b2cace-41a1-416e-92d7-e5e73a28bd89.png)

### 3.6 Tạo quản trị viên và trình quản lí:

**cd conf/**

**ls**

![image](https://user-images.githubusercontent.com/101611197/159609515-37683d20-4e1b-4635-bdfa-24a178d736c6.png)

Tạo quản trị viên và user

**sudo nano tomcat-users.xml**

Bổ sung user

![image](https://user-images.githubusercontent.com/101611197/159614275-ae32f488-7afa-4606-93dd-03924b05265a.png)

Kiểm tra xem tomcat đã được khởi động chưa

**./startup.sh**

![image](https://user-images.githubusercontent.com/101611197/159614614-301400d4-f843-4cff-a796-352beda08dd8.png)

### 3.7 Kiểm tra 

Mở trình duyệt truy cập đường dẫn: **Localhost:8080**

![image](https://user-images.githubusercontent.com/101611197/159614939-f6010fd1-1f70-4d18-ac5e-9278bb2acabe.png)

Ở đây chúng ta có thể truy cập vào trình quản lý

![image](https://user-images.githubusercontent.com/101611197/159615199-88ec2320-d1e9-443a-b1d9-6d6d7934e384.png)

![image](https://user-images.githubusercontent.com/101611197/159615246-aa4328c4-6cea-4216-8ce8-8129c6576647.png)

![image](https://user-images.githubusercontent.com/101611197/159615543-50b63c2b-5e6e-4c30-bd83-082a7df20cc7.png)

### 3.8 Tạo 1 chương trình và kiểm tra

![image](https://user-images.githubusercontent.com/101611197/159615796-1cdc4b0f-835e-4a97-883d-c2da3ac9e7f0.png)

![image](https://user-images.githubusercontent.com/101611197/159616002-6f0fadbf-2239-4c01-b629-30231ad71f62.png)

Lưu lại và vào trình duyệt chạy đường dẫn localhost:8080/test.jsp để kiểm tra













