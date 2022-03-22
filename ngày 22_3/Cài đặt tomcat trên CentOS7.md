# Cài đặt và cấu hình Tomcat service

## Bước 1 – Cài đặt Java

Tomcat 9 yêu cầu Java SE 8 (hoặc cao hơn) phải được cài đặt trên CentOS. Bạn có thể cài đặt Java từ kho lưu trữ gói mặc định bằng lệnh yum  như sau:

 **yum install java-1.8.0-openjdk-devel**
 
 ![image](https://user-images.githubusercontent.com/101611197/159405111-abfb2785-c93c-4b7a-b370-f5c8d9d02e57.png)

 Sau khi quá trình cài đặt hoàn tất, bạn có thể kiểm tra lại phiên bản Java bằng lệnh bên dưới:
 
**java -version**

![image](https://user-images.githubusercontent.com/101611197/159405283-3e955fff-87a9-4bd0-b463-a82fd2232f57.png)

## Bước 2 – Tạo Tomcat System User

Vì lý do bảo mật, Tomcat nên được thực thi bởi một user được cấp quyền riêng (không phải user root). Chúng ta sẽ tạo một user  và group để thực thi Tomcat.

Đầu tiên, bạn tạo group bằng lệnh

**groupadd tomcat**

Sau đó, tạo một user tomcat (là thành viên của group tomcat) với thư mục home /opt/tomcat (thư mục cài đặt Tomcat ở bước sau) và tắt quyền truy cập vào server:
 
**useradd -M -s /bin/nologin -g tomcat -d /opt/tomcat tomcat** 
 
 Tiếp theo, bạn tiến hành giải nén file .tar.gz vào thư mục cài đăt Tomcat (/opt/tomcat) bằng lệnh sau:
 
 **tar -xzvf apache-tomcat-9.0.31.tar.gz -C /opt/tomcat --strip-components=1**
 
 ## Bước 3 – Download Tomcat
 
 Bạn có thể sử dụng lệnh wget như sau để tải về phiên bản tomcat 9 mới nhất
 
 **wget https://downloads.apache.org/tomcat/tomcat-9/v9.0.31/bin/apache-tomcat-9.0.31.tar.gz**
 
 ![image](https://user-images.githubusercontent.com/101611197/159406102-d6a53d43-7c5c-4c37-bbc7-785276a10003.png)
 
 Tiếp theo, bạn tiến hành giải nén file .tar.gz vào thư mục cài đăt Tomcat (/opt/tomcat) bằng lệnh sau:
 
 **tar -xzvf apache-tomcat-9.0.31.tar.gz -C /opt/tomcat --strip-components=1**
 
 
 
 
 
 
 
