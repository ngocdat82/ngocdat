# Các lệnh căn bản về NetWork trong linux

Ubuntu và CentOS cũng như các hệ điều hành linux khác coi card mạng là một devicce và lưu cấu hình trong file text, sau đó tải lên mỗi khi khởi động máy. Mỗi máy tính cần có một card mạng Ethernet có dây hoặc không dây, được liệt kê trong thư mục /dev với tên gọi bắt đầu bằng 3 chữ cái eth, ví dụ: eth0 cho card mạng thứ nhất, eth1 cho card mạng thứ 2…

File lưu cấu hình mạng ở mỗi dòng Linux thường khác nhau, ví dụ, trong Ubuntu, file cấu hình mạng được lưu tại /etc/network/interface/ còn trong CentOS thì nó được lưu trong thư mục /etc/sysconfig/network-scripts/

## 1.1 Các câu lệnh kiểm tra thông tin mạng trong CentOS

**ifconfig**: Xem thông tin cấu hình các card mạng (MAC, địa chỉ IP, gateway..)  của tất cả các card mạng trong máy (tương tự lệnh ipconfig của Windows)

![image](https://user-images.githubusercontent.com/101611197/159113189-94f3704a-0474-4ee0-9822-03ba1d872066.png)



