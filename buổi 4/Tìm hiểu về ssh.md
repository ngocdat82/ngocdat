# 1. Khái niệm về SSH

![image](https://user-images.githubusercontent.com/101611197/158933064-256e7180-5ad6-4a56-ae8a-bc3fdba17228.png)

**SSH** ( tên tiếng anh là Secure Shell) được hiểu là giao thức kết nối giữa máy khách và máy chủ điều khiển từ xa cho phép người sử dụng chỉnh sửa và kiểm soát server từ xa nhưng vẫn đảm bảo được an toàn. Server sẽ không bao giờ bị đánh cắp thông tin được truyền đi giữa máy chủ và máy tính nếu sử dụng SSH để kết nối vps. Giao thức SSL và SSH đều mã hoá đường truyền dữ liệu. Người dùng có khả năng sử dụng để chuyển tập tin, chạy chương trình, chuyển tiếp khác kết nối TCP / IP bằng đường truyền đã được bảo mật. 

# 2. So sánh giữa SSL/TLS và SSH

![image](https://user-images.githubusercontent.com/101611197/158933994-1ab37098-d234-40ef-84b7-83dd1d125363.png)

SSL/TLS và SSH đều đảm bảo bảo mật dữ liệu giao tiếp trong vận chuyển dữ liệu và xác thực    các bên

**Giống nhau**: Đều đảm bảo bảo mật dữ liệu giao tiếp trong vận chuyển dữ liệu và xác thực các bên.

**Khác nhau**:

Các **giao thức SSH** dựa vào một mã nhị phân đơn giản, dùng như một lớp an toàn cho SCP và SFTP chuyển tập tin, truy cập trong môi trường bảo mật, và chuyển tiếp các kết nối cho những ứng dụng khác.

**SSH** được coi như một phiên bản đơn giản của TLS: Do độc lập có chủ ý từ chứng chỉ X.509 (Được hiểu là tiêu chí giao tiếp chuẩn bảo đảm bảo mật giữa máy chủ, máy khách và đường truyền), SSH phát triển độc lập qua chứng chỉ X.509, vì vậy SSH có thể kết nối máy khách và máy trạm một cách đáng tin cậy, nơi mà giao thức TLS kém bảo mật hơn. 

**SSL/TLS** có xu hướng dùng giấy chức nhận X.509 dựa trên bảng mã ASN.1, và được sử dụng một lớp bảo mật cho SMTP. HTTP và truyền tải tập tin qua FTP.

# 3. Độ an toàn bảo mật của SSH

SSH hoạt động bởi 3 bước cơ bản là: **định danh host, mã hoá** và cuối cùng là **chứng thực**.

**Bước 1**: Định danh host được hiểu là máy khách-máy tính điều khiển: Xác minh định danh của hệ thống tham gia làm việc SSH

Quá trình trao đổi khoá được thực hiện qua việc định danh host. Từng máy điều khiển SSH có duy nhất một khoá định danh. Có 2 phần ở khoá là **khoá công cộng** (public) và **khoá riêng tư**. Khoá public được dùng bằng khoá công khai và chỉ có thể giải mã bằng khoá riêng. Nếu ở máy chủ có bất cứ thay đổi nào như: thay đổi của chương trình SSH, hệ điều hành thay đổi, thay đổi ở khoá định danh. Để đăng nhập vào máy chủ, người dùng sử dụng SSH, máy chủ cũng được thông báo về sự thay đổi này. Máy chủ sẽ gửi khoá công cộng của máy chủ khi một phiên làm việc SSH của hai hệ thống được bắt đầu. Mã hoá khoá và một khoá phiên ngẫu nhiên được tạo ra từ máy khách bằng khoá công cộng của máy chủ sau đấy gửi cho máy chủ. Bằng khoá riêng của mình máy chủ sẽ giải mã và sau đó nhận được khoá phiên. Khoá phiên này cũng đồng thời là khoá sử dụng với mục đích trao đổi dữ liệu giữa hai máy. Toàn bộ quá trình này cũng được coi như là các bước nhận diện máy khách và máy chủ. Kiểu mã hoá an toàn tập tim trên đường truyền này của SSH cũng giống với cơ chế của SSL.

**Bước 2**: Mã hoá dữ liệu: Thiết lập kênh làm việc mã hoá

Quá trình trao đổi dữ liệu hoạt động thông qua giải mã/mã hoá làm bước trung gian. Đây đồng nghĩa với việc dự liệu nhận và gửi trên đường truyền đều được giải mã và mã hoá theo thoả thuận trước đây giữa khách và máy chủ. Máy khách sẽ thường được quyết định lựa chọn các cơ chế mã hoá. Ba cơ chế mã hoá thông dụng là: Blowfish, IDEA và 3DES. Máy khách và máy chủ trao đổi mã hoá cho nhau khi chọn cơ chế mã hoá. Việc trao đổi khoá mã hoá đó luôn được bảo mật thông qua định danh kín của các máy. Thông tin trên đường truyền trao đổi khó có thể bị giải mã và đánh cắp bởi vì những kẻ tấn công sẽ không biết khoá mã hoá. Sau đây là các thuật toán mã hoá:

**Blowfish**: Bảo mật và tốc độ nhanh, các phương pháp mã hoá còn hạn chế nhưng vẫn đang được cải tiến

**Arcfour**: nhanh, có xảy ra vấn đề bảo mật

**3DES**: được mặc định là phương pháp mã hoá cho SSH

**IDEA**:  phương pháp này nhanh hơn 3DES, nhưng lại hoạt động chậm hơn Blowfih và Arcfour

**Bước 3**: Giải mã và chứng thực: xác minh quyền đăng nhập hệ thống của người dùng

Ở 3 bước hoạt động của SSH thì đây là bước kết thúc. Tại đây, kênh trao đổi đã được bảo mật. Từng lượt truy cập và định danh của người dùng được cung cấp theo nhiều cách đa dạng khác khau. Ví dụ như kiểu chứng thực rhosts được dùng nhưng không phải có sẵn, chỉ có mục đích kiểm tra định danh của máy khách được liệt kê theo địa chỉ IP và DNS (file rhost). Định danh người dùng qua việc xác thực mật khẩu là cách được nhiều người dùng, bên cạnh đó cũng có cách khác như xác thực RSA, dùng ssh-agent và ssh-keygen để xác thực những cặp khoá. 

