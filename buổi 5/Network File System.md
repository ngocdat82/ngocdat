# Network File System là gì?

**NFS (Network File System)** là một hệ thống giao thức chia sẻ file phát triển bởi Sun Microsystems từ năm 1984, cho phép một người dùng trên một máy tính khách truy cập tới hệ thống file chia sẻ thông qua một mạng máy tính giống như truy cập trực tiếp trên ổ cứng. Hiện tại có 3 phiên bản NFS là NFSv2, NFSv3, NFSv4.

**NFSv2** Phiên bản 2 của giao thức (được xác định trong RFC 1094 , tháng 3 năm 1989) ban đầu chỉ hoạt động trên Giao thức gói dữ liệu người dùng (UDP). Các nhà thiết kế của nó có nghĩa là giữ cho phía máy chủ không trạng thái , với việc khóa (ví dụ) được triển khai bên ngoài giao thức cốt lõi. Những người liên quan đến việc tạo ra NFS phiên bản 2 bao gồm Russel Sandberg , Bob Lyon , Bill Joy , Steve Kleiman và những người khác. [1] [4] Các hệ thống tập tin ảo giao diện cho phép thực hiện mô đun, phản ánh trong một giao thức đơn giản. Đến tháng 2 năm 1986, việc triển khai đã được chứng minh cho các hệ điều hành như System V phát hành 2, DOS và VAX / VMS sử dụng Eunice . [4] NFSv2 chỉ cho phép đọc 2 GB đầu tiên của tệp do giới hạn 32 bit .

**NFSv3** Phiên bản 3 ( RFC 1813 , tháng 6 năm 1995) đã thêm:

Hỗ trợ kích thước và độ lệch tệp 64 bit, để xử lý các tệp lớn hơn 2 gigabyte (GB);

Hỗ trợ ghi không đồng bộ trên máy chủ, để cải thiện hiệu suất ghi;

Thuộc tính tệp bổ sung trong nhiều phản hồi, để tránh phải tìm nạp lại chúng;

Một thao tác READDIRPLUS, để xử lý tệp và các thuộc tính cùng với tên tệp khi quét thư mục;

Các loại cải tiến khác.

Đề xuất NFS Phiên bản 3 đầu tiên trong Sun microsystems đã được tạo ra không lâu sau khi phát hành NFS Phiên bản 2. Động lực chính là nỗ lực giảm thiểu vấn đề hiệu năng của hoạt động ghi đồng bộ trong NFS Phiên bản 2. Đến tháng 7 năm 1992, việc thực hiện thực tế đã giải quyết được nhiều thiếu sót của NFS Phiên bản 2, chỉ thiếu hỗ trợ tệp lớn (kích thước tệp 64 bit và độ lệch) là một vấn đề cấp bách. Điều này đã trở thành một điểm đau cấp tính đối với Tập đoàn Thiết bị Kỹ thuật số với việc giới thiệu phiên bản Ultrix 64 bit để hỗ trợ bộ xử lý RISC 64 bit mới phát hành của họ , Alpha 21064 . Tại thời điểm giới thiệu Phiên bản 3, nhà cung cấp hỗ trợ cho TCP dưới dạng giao thức lớp vận chuyển bắt đầu tăng. Mặc dù một số nhà cung cấp đã thêm hỗ trợ cho NFS Phiên bản 2 với TCP làm phương tiện vận chuyển, Sun microsystems đã thêm hỗ trợ cho TCP dưới dạng vận chuyển cho NFS đồng thời bổ sung hỗ trợ cho Phiên bản 3. Sử dụng TCP làm phương tiện vận chuyển được thực hiện bằng NFS qua mạng WAN khả thi hơn và cho phép sử dụng các kích thước truyền và đọc lớn hơn vượt quá giới hạn 8 KB do Giao thức gói dữ liệu người dùng áp đặt .

**NFSv4 [ chỉnh sửa ]**

Phiên bản 4 ( RFC 3010 , tháng 12 năm 2000; được sửa đổi trong RFC 3530 , tháng 4 năm 2003 và một lần nữa trong RFC 7530 , tháng 3 năm 2015), chịu ảnh hưởng của Andrew File System (AFS) và Server Message Block (SMB, cũng được gọi là CIFS), bao gồm cải tiến hiệu suất, bắt buộc bảo mật mạnh mẽ, và giới thiệu một giao thức trạng thái . [7] Phiên bản 4 trở thành phiên bản đầu tiên được phát triển với Lực lượng đặc nhiệm kỹ thuật Internet (IETF) sau khi Sun microsystems bàn giao việc phát triển các giao thức NFS.

Phiên bản NFS 4.1 ( RFC 5661 , tháng 1 năm 2010) nhằm mục đích cung cấp hỗ trợ giao thức để tận dụng các triển khai máy chủ phân cụm bao gồm khả năng cung cấp quyền truy cập song song có thể mở rộng vào các tệp được phân phối giữa nhiều máy chủ (tiện ích mở rộng pNFS). Phiên bản 4.1 bao gồm cơ chế trung kế phiên (Còn được gọi là NFS Multipathing) và có sẵn trong một số giải pháp doanh nghiệp như VMware ESXi .

Phiên bản NFS 4.2 ( RFC 7862 ) đã được xuất bản vào tháng 11 năm 2016 [8] với các tính năng mới bao gồm: sao chép và sao chép phía máy chủ, tư vấn I / O ứng dụng, tệp thưa, đặt chỗ không gian, khối dữ liệu ứng dụng (ADB), được gắn nhãn NFS với sec_label có thể chứa bất kỳ hệ thống bảo mật MAC nào và hai hoạt động mới cho pNFS (LAYOUTERROR và LAYOUTSTATS).

Một lợi thế lớn của NFSv4 so với các phiên bản trước đó là chỉ có một cổng UDP hoặc TCP, 2049, được sử dụng để chạy dịch vụ, giúp đơn giản hóa việc sử dụng giao thức trên tường lửa.

## cài đặt và cấu hình NFS Server và NFS Client trên CentOS 7

**NFS Server IP address: 192.168.2.100**

**NFS Client IP address: 192.168.2.101**

Để cài đặt NFS Server chúng ta cài package nfs-utils

**yum install nfs-utils**

![image](https://user-images.githubusercontent.com/101611197/159113445-b80659ef-59d8-45ff-a410-e6115d4cb0a4.png)

– Tạo thư mục chia sẻ tài nguyên trên server

**mkdir /share-data**

Thay đổi permission cho thư mục

**chmod -R 755 /share-data**

**chown nfsnobody:nfsnobody /share-data**

![image](https://user-images.githubusercontent.com/101611197/159113646-3450b0fd-1a09-4766-afcd-ed7413235340.png)

Kích hoạt và chạy các dịch vụ cần thiết:

**systemctl enable rpcbind**

**systemctl enable nfs-server**

**systemctl enable nfs-lock**

**systemctl enable nfs-idmap**

**systemctl start rpcbind**

**systemctl start nfs-server**

**systemctl start nfs-lock**

**systemctl start nfs-idmap**

![image](https://user-images.githubusercontent.com/101611197/159113728-bc9d0f2c-acc0-47ee-92f7-d53ce318f14a.png)

Thiết lập quyền truy cập (client truy cập được từ một IP cụ thể của Client), cập nhật quyền này vào file /etc/exports

Ví dụ IP 192.168.154.100, 192.168.154.99 có quyền truy cập

**/share-data    192.168.154.100(rw,sync,no_root_squash,no_all_squash)**

**/share-data    192.168.1.10(rw,sync,no_root_squash,no_all_squash)**

Nếu IP thay bằng * thì mọi client có quyền truy cập.

Chạy dịch vụ NFS

**systemctl restart nfs-server**

Mở cổng cho NFS qua firewall

**firewall-cmd --permanent --zone=public --add-service=nfs**

**firewall-cmd --permanent --zone=public --add-service=mountd**

**firewall-cmd --permanent --zone=public --add-service=rpc-bind**

**firewall-cmd --reload**

![image](https://user-images.githubusercontent.com/101611197/159113958-7b08effc-3f72-4607-8aec-41d8ee50f043.png)

Cài đặt NFS Client

Cài gói nfs-utils sau cài trên máy client CentOS để có khả năng truy cập, gắn ổ đĩa NFS từ server NFS

**yum install nfs-utils**

![image](https://user-images.githubusercontent.com/101611197/159113988-581a1f3e-5ab8-47f8-9a88-3094425f959b.png)

Gán ổ đĩa NFS Server vào máy Client

Thiết lập để thư mục /share-data từ NFS Server có IP 192.168.1.3, sẽ gắn vào /mnt/nfs/share-data của máy Client

# Cấu hình trên Windows Server 2019

Mở Server manage lên và chọn Add role and features

![image](https://user-images.githubusercontent.com/101611197/159114721-6e999354-42ef-423c-b4fe-7b192b652311.png)

Chọn Next

![image](https://user-images.githubusercontent.com/101611197/159114742-7c4d3300-7c11-48c2-a117-c65f85863cc5.png)


Chọn Next

![image](https://user-images.githubusercontent.com/101611197/159114746-23ccffde-88df-4a89-84ad-e8051dc92426.png)

Chọn Next

![image](https://user-images.githubusercontent.com/101611197/159114756-a1eb1beb-d7ad-4014-9f78-de66a824cd0c.png)

Chọn Client for NFS rồi chọn Next

![image](https://user-images.githubusercontent.com/101611197/159114790-b6f862da-cf8c-4eb1-94aa-362cd062ff04.png)

Chọn Install để tiến hành cài đặt

![image](https://user-images.githubusercontent.com/101611197/159114818-54aefa75-c606-4999-94b0-475c26022799.png)

![image](https://user-images.githubusercontent.com/101611197/159114825-8881acee-a2fd-4803-88c8-9fb79c808b67.png)

Sau khi cài đặt xong chúng ta nhấn Close và mở CMD để tiến hành thiết lập

Sử dụng lệnh mount ip_máy_server:/thư_mục_share

![image](https://user-images.githubusercontent.com/101611197/159116107-c98c91d8-ff9b-4bf8-8fbc-f17a70d57e29.png)

Sau khi mount xong chúng ta vào This PC để kiểm tra. Ở đây chúng ta sẽ nhìn thấy thư mục home đã được chúng ta set làm ổ U đã hiển thị.

![image](https://user-images.githubusercontent.com/101611197/159116150-cdc832bb-abc2-4512-adc3-1356fa202d68.png)

Tương tự với thư mục nfsshare

![image](https://user-images.githubusercontent.com/101611197/159116350-7d4c797b-ac80-47d9-a663-6645311959de.png)

Thực hiện thêm thư mục test vào trong thư mục nfsshare

và kiểm tra lại ở trên máy windows server 2019

![image](https://user-images.githubusercontent.com/101611197/159116377-1234efb5-81aa-4a04-b75c-891a02c7b04c.png)

![image](https://user-images.githubusercontent.com/101611197/159116385-94fd7b99-999a-4b30-ad43-100ebcf235fa.png)

Vậy là chúng ta đã thực hiện thành công

