# Cài đặt IIS trên Windows Server 2019

### 1. Chạy Powershell với quyền admin và cài đặt IIS.**
Sử dụng 2 lệnh:

**Install-WindowsFeature Web-Server -IncludeManagementTools**

Để cài đặt IIS bằng công cụ quản trị

Và lệnh 

**Invoke-WebRequest http://localhost **

Để xác minh việc chạy để truy cập vào trang web mặc định

![image](https://user-images.githubusercontent.com/101611197/158940422-2a4c82a2-d7ad-428c-bc18-b73f3b4ee833.png)

### 2. Chạy Server Manager và nhấp vào Add roles and features.

![image](https://user-images.githubusercontent.com/101611197/158949894-e48498a5-26a0-41e6-b2d6-385f0cb639ce.png)

### 3. Nhấp vào nút Next.

![image](https://user-images.githubusercontent.com/101611197/158951435-d32cad94-3f4e-49fe-be07-632c6f86ab22.png)

### 4. Chọn Role-based or feature-based installation.

![image](https://user-images.githubusercontent.com/101611197/158952174-748f38bb-7a8d-4e1a-be2a-bbafd882d9b6.png)

### 5. Chọn host bạn muốn thêm các service.

![image](https://user-images.githubusercontent.com/101611197/158952290-c60c5a0e-6bac-4787-8d21-ba181d63a840.png)

### 6. Tích vào hộp Web Server (IIS).

![image](https://user-images.githubusercontent.com/101611197/158952407-2ae5272d-782d-467b-92bc-77651f3391d2.png)

### 8. Nhấp vào nút Next.

![image](https://user-images.githubusercontent.com/101611197/158952752-2b4c029a-2f8b-4f78-87c8-cda9c2f832cb.png)

### 9. tích chọn Restart the destination server automatically if requied -> Install

![image](https://user-images.githubusercontent.com/101611197/158953269-522700d2-6c5f-4bc6-903b-f5046476e55e.png)

### 10. Chạy trình duyệt web và truy cập vào localhost, sau đó bạn có thể xác minh IIS có đang chạy bình thường không.

![image](https://user-images.githubusercontent.com/101611197/158953492-c286d8bf-10ab-4fcc-bc7a-ee13d90cd0c5.png)

# Sử dụng IIS trên Windows Server 2019

### 1. Chạy Powershell với quyền admin và cấu hình như sau:

**- Get-Website**

**- Get-ChildItem C:\inetpub\wwwroot**

**- Invoke-WebRequest localhost**

**- Get-WebConfigurationProperty -Filter "//defaultDocument/files/add" -PSPath "IIS:\Sites\Default Web Site" -Name "value" | select value**

**- Write-Output "IIS Default Start Page" | Out-File C:\inetpub\wwwroot\Default.htm -Encoding Default**

**- curl.exe localhost**



![image](https://user-images.githubusercontent.com/101611197/158954069-d8081173-9fe0-4b8b-9233-0bb8de51178e.png)
![image](https://user-images.githubusercontent.com/101611197/158954127-06ac0310-56ba-4f77-bbdf-1b09fad96fb7.png)

### 2. Chạy Start > Server Manager và nhấp vào Tools > Internet Information Services (IIS) Manager.

![image](https://user-images.githubusercontent.com/101611197/158955432-50ba253d-e1f1-42bf-a361-c4dcb8ceb301.png)

### 3. Mở các mục ở bảng điều khiển bên trái, Default Web Site được cấu hình

![image](https://user-images.githubusercontent.com/101611197/158955593-34f37bdb-a4d3-481f-b714-abc563cff3fe.png)

### 4. Chọn Default Web Site và nhấp vào Advanced Settings..., sau đó có thể xác nhận các cài đặt như Physical Path (Document Root), v.v...

![image](https://user-images.githubusercontent.com/101611197/158955841-c2e1b0c3-24d9-4d48-a609-67f960087ccd.png)

### 5. Mở Default Document, sau đó có thể xác nhận các tài liệu mặc định.

![image](https://user-images.githubusercontent.com/101611197/158955927-a35fc615-c3eb-4a05-ac01-3d3c48134a2a.png)

### 6. Chúng ta có thể xem các tài liệu mặc định.

![image](https://user-images.githubusercontent.com/101611197/158956037-b99c76c1-5a2d-4d08-ace0-5bd07113efe8.png)

### 7. Tạo trang test trong Physical Path (Document Root) và xác minh quyền truy cập bằng trình duyệt web.

![image](https://user-images.githubusercontent.com/101611197/158956389-23f657aa-d253-4889-9e3d-d20f4a44f487.png)

![image](https://user-images.githubusercontent.com/101611197/158956483-9473be55-a441-42b9-9fe4-98c0d9f30919.png)


