# Sau khi tải về ISO Windows Server và cài đặt VMWare Workstation vào máy tính, chúng ta cùng bắt đầu quá trình cài đặt Windows Server 2019

**Bước 1**: Khởi động VMWare Workstation và chọn “Create a New Virtual Machine”

![image](https://user-images.githubusercontent.com/101611197/158721023-8c7f000b-f248-48d5-805f-3f099a2c4794.png)

**Bước 2**: chọn Typical rồi nhấn Next

![image](https://user-images.githubusercontent.com/101611197/158721368-5c3d5f11-a84e-46f2-91df-f8fe2d2f66a5.png)

**Bước 3**: Lựa chọn mục thứ 3 để thêm ISO sau cùng vì nếu như chúng ta thêm ISO ở bước này, hệ thống sẽ bắt chúng ta khai báo một vài thông tin về tài khoản.

![image](https://user-images.githubusercontent.com/101611197/158721508-8fcda6a1-8ad4-49bc-92bf-84223addf60c.png)

**Bước 4**: Lựa chọn hệ điều hành cài đặt 

![image](https://user-images.githubusercontent.com/101611197/158722913-407f8a9e-7d02-401b-8a11-35c5643c1469.png)

**Bước 5**: Đặt tên cho máy ảo

![image](https://user-images.githubusercontent.com/101611197/158723045-e865a1d9-2d99-400e-b270-199691749225.png)

Bước 6: Khai báo thông số dung lượng ổ đĩa trên máy ảo khi tạo ra

![image](https://user-images.githubusercontent.com/101611197/158723167-b07d51fc-6175-4708-beb6-63c138f26aac.png)

**Bước 7**: Nhấn Finish

![image](https://user-images.githubusercontent.com/101611197/158723349-a4ece1b0-4c22-45a4-94a0-9d258d379241.png)

**Bước 8**: Ở màn hình mới chọn **Edit virtual machine settings** để thêm file iso

![image](https://user-images.githubusercontent.com/101611197/158723491-f4ec2901-c75f-4f90-ad5a-a7ddd43b6bec.png)

**Bước 9**: Lựa chọn CD/DVD (SATA), phần Use ISO image file và lựa chọn nơi lưu trữ ISO Windows Server 2019, sau đó ấn OK để hoàn tất.

![image](https://user-images.githubusercontent.com/101611197/158723714-349a7cc9-cc55-4c2a-9cef-c039d09292cd.png)

**Chúng ta có thể điều chỉnh lại cấu hình của máy ảo tại đây**

![image](https://user-images.githubusercontent.com/101611197/158723852-cb8c909a-7f21-4ed2-a91a-5ee5b1c2209d.png)

**Bước 10**: Khởi chạy máy ảo để bắt đầu tiến hành cài đặt

![image](https://user-images.githubusercontent.com/101611197/158723975-82d6d99a-fdad-493a-8145-a6371ea87391.png)

**Bước 11**: Chọn ngôn ngữ, thời gian, bàn phím rồi bấm next

![image](https://user-images.githubusercontent.com/101611197/158724697-9ae6caed-2cbd-4b4b-8838-2f9d463670fa.png)

**Bước 12**: Chọn Install now

![image](https://user-images.githubusercontent.com/101611197/158724795-43e67af4-5d02-4390-9e10-e8239a86e1e2.png)

**Bước 13**: Chọn hệ điều hành rồi nhấn next

![image](https://user-images.githubusercontent.com/101611197/158724879-d8da2c21-0eb1-432c-b381-a0d3c7dd32a1.png)

**Bước 14**: Đồng ý với các điều khoản rồi next

![image](https://user-images.githubusercontent.com/101611197/158724995-b2a0f1f5-9705-4e62-8cce-c9aee1cf1a5e.png)

**Bước 15**: Lựa chọn Custom: Install Windows only (advanced)

![image](https://user-images.githubusercontent.com/101611197/158725072-545e64c2-c60c-45f7-a652-61d4dc46eb9a.png)

**Bước 16**: lựa chọn phân vùng để bung bộ cài đặt Windows Server 2019, vì ở đây có một ổ đĩa nên tôi sẽ ấn Next 

![image](https://user-images.githubusercontent.com/101611197/158725157-e9e142a7-f527-4bae-90a9-5b96e7d81a8f.png)

### Quá trình cài đặt sẽ được diễn ra

![image](https://user-images.githubusercontent.com/101611197/158725268-deb69186-3046-47a0-a2a2-cbb293a3a72a.png)

**Bước 17**: khai báo mật khẩu cho tài khoản Administrator trước khi đăng nhập vào hệ điều hành

![image](https://user-images.githubusercontent.com/101611197/158726491-e94b3074-7ceb-4abf-8902-10d4f0f235e9.png)

**Bước 18**: Ấn Finish và đăng nhập vào hệ thống, sử dụng Ctrl + Alt + Del để unlock

![image](https://user-images.githubusercontent.com/101611197/158727083-911b1470-2df3-4f84-94a5-8140bab5291a.png)

hoàn tất cài đặt Windows Server 2019 trên VMWare
