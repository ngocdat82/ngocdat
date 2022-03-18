# Web server là gì?
**B1**: Đầu tiên chúng ta sử dụng lệnh **sudo dnf install openssh-server** để cài đặt gói gói openssh-server

Web server có nghĩa là máy chủ web, là máy tính lớn được kết nối với tập hợp mạng máy tính mở rộng. Máy chủ chứa toàn bộ dữ liệu mà nó được giao quyền quản lý. Mỗi máy chủ có một IP riêng và có thể đọc đa dạng ngôn ngữ như HTML, HTM, File,… Máy chủ có dung lượng lớn và tốc độ rất cao để có thể lưu trữ và vận hành tốt kho dữ liệu trên internet. Thông qua cổng giao tiếp riêng biệt của mỗi máy chủ mà hệ thống máy tính có khả năng hoạt động trơn tru hơn. Máy chủ phải đảm bảo hoạt động liên tục để có thể cung cấp dữ liệu cho mạng lưới máy tính của nó.

![image](https://user-images.githubusercontent.com/101611197/158929896-31e43b8c-9b79-4ae8-b138-bf64e9addd2e.png)

# Về mặt phần cứng

Web server là một máy tính lưu trữ các file thành phần tạo nên một website (ví dụ: HTML, images, CSS, và file javacript...) và truyền chúng tới người dùng cuối. 

Web server được kết nối đến internet và truy cập thông qua một domain giống như mozilla.org. 

# Về mặt phần mềm

Web server bao gồm một số phần kiểm soát người dùng web truy cập đến file host tại tối thiểu một HTTP server. Một HTTP server là một phần của phần mềm nó hiểu là URLs(web address) và HTTP (là phương thức để trình duyệt của bạn hiển thị trang web) Ở mức cơ bản nhất, bất cứ một trình duyệt nào cần một file host trên một web server, trình duyệt đó sẽ request file đó thông qua HTTP. Khi một yêu cầu được gửi đến địa chỉ web server đúng thì HTTP server gửi trở lại một yêu cầu thông qua HTTP. 

# Các đặc tính của Web Server

Web server (máy chủ web) có thể xử lý dữ liệu, cung cấp thông tin đến máy khách qua môi trường internet thông qua giao thức HTTP, giao thức được thiết kế gửi file đến trình duyệt web hay giao thức khác. Chẳng hạn: Người dùng truy cập vào website bkns.vn. Khi đó, server sẽ cung cấp tất cả dữ liệu về website đó thông qua lệnh giao tiếp.

Nếu được cài đặt một chương trình Server Software và kết nối internet thì bất cứ máy tính này cũng có thể trở thành web server. Phần mềm Server Software là phần mềm chuyên dụng để cài đặt và chạy trên bất cứ máy tính nào có thể đáp ứng đủ yêu cầu về bộ nhớ. Nhờ có nó mà người dùng có thể truy cập đến các thông tin của website từ một máy tính khác qua internet.

Người ta thường thuê các máy chủ nhỏ, máy chủ ảo VPS hay Hosting để lưu trữ dữ liệu cho website của mình.

Một server có thể cung cấp cả nội dung Static và Dynamic. Static có nghĩa là nội dung nguyên vẹn và dễ dàng để thiết lập. Dynamic là nội dung đã được sever xử lý hoặc tạo mới với dữ liệu từ Database, định dạng, đẩy vào trong HTTP Template rồi gửi kết quả đến người dùng.

# Các bước lấy dữ liệu của một website

**Bước 1**: Web server lưu trữ các file của website – Hosting file

Web server lưu trữ các file của website (bao gồm các tài liệu HTML, ảnh file CSS, fonts, video, file JavaScript). Người dùng hoàn toàn có thể lưu trữ chúng trên máy tính của mình nhưng khi lưu trên máy chủ web sẽ có những lợi ích sau:

- Luôn sẵn sàng – up and running

- Luôn kết nối tới mạng internet

- Địa chỉ IP cố định

- Được bảo dưỡng và bảo vệ bởi nhà cung cấp

**Bước 2**:  Giao tiếp qua HTTP
Web server sẽ hỗ trợ giao thức truyền phát siêu văn bản – HTTP. HTTP là tập hợp các quy tắc kết nối giữa hai máy tính bao gồm Textual và Stateless.

Textual: Mọi lệnh đều là văn bản thuần túy và người dùng có thể đọc được nó.

Stateless: Khi cả người dùng và máy chủ không nhớ kết nối trước đó.

HTTP có quy tắc rõ ràng về giao tiếp giữa client và server như sau:

Duy nhất client có thể tạo ra yêu cầu HTTP đến server. Các server chỉ có thể đáp trả yêu cầu HTTP của client.

Client phải cung cấp URL của file khi yêu cầu file đó thông qua HTTP.

Tất cả yêu cầu HTTP sẽ được web server trả lời.

HTTP có trách nhiệm xử lý và trả lời các yêu cầu đến qua các bước:

Khi nhận được một yêu cầu, HTTP sẽ kiểm tra URL được yêu cầu có khớp với file hiện có không?

Nếu trùng khớp, máy chủ web sẽ gửi nội dung file trả lại trình duyệt. Trường hợp không trùng khớp, một Application server sẽ tạo ra file được yêu cầu.

Web server sẽ gửi trả lại một thông điệp lỗi cho trình duyệt (phổ biến nhất là 404 Not Found) nếu nó không thể xử lý được.

# Các loại Web server phổ biến hiện nay

### Web server Apache

- Web server Apache được phát triển bởi Quỹ Phần mềm Apache và là một trong những web server nổi tiếng trên thế giới. Đây là phần mềm mã nguồn mở, hỗ trợ hầu hết các hệ điều hành như Unix, Linux, Windows, Mac OS X, FreeBSD,… Theo thống kê, khoảng 60% máy tính chạy trên web server Apache.

- Web server Apache có các tùy biến được thực hiện dễ dàng bởi nó có cấu trúc dạng Module. Bạn có thể thêm hay sửa đổi các Module vào server theo ý muốn nếu cảm thấy phù hợp. So với bất cứ máy chủ web nào thì Apache cũng ổn định và dễ dàng xử lý khi có vấn đề xảy ra. Các phiên bản mới của web server Apache có khả năng xử lý được nhiều yêu cầu hơn so với phiên bản tiền nhiệm.

![image](https://user-images.githubusercontent.com/101611197/158931897-660eaa26-b709-442c-9f71-66a86ad2e1f2.png)

### Web server IIS

Web server IIS là sản phẩm của Microsoft, nó có rất nhiều tính năng giống như Apache. Tuy nhiên, đây không phải là mã nguồn mở và việc thêm, chỉnh sửa các Module theo ý muốn không hề dễ dàng. Web server IIS có khả năng chạy trên tất cả nền tảng của hệ điều hành của Windows.

![image](https://user-images.githubusercontent.com/101611197/158932170-c95d6db9-fe02-43cf-8016-c18a8f7fbb17.png)

### Web server Nginx

Web server Nginx là một máy chủ mã nguồn mở miễn phí. Nginx bao gồm máy chủ POP3 và IMAP. Web server Nginx có ưu điểm là ổn định, hiệu suất cao, cấu hình đơn giản và sử dụng tài nguyên thấp. Nginx không dùng các chuỗi (thread) để xử lý các yêu cầu mà sử dụng kiến trúc lập trình theo sự kiện (có khả năng mở rộng). Kiến trúc lập trình này dùng bộ nhớ khi tải nhỏ và dự đoán được. Nginx hiện đang lưu trữ khoảng 7.5 % các tên miền trên toàn thế giới. Trong những năm trở lại đây, phần đông công ty web hosting sử dụng Nginx.

![image](https://user-images.githubusercontent.com/101611197/158932277-86a53ed8-8c66-4b87-bf1a-098eb26bc9d2.png)

# Một số lưu ý khi sử dụng Web server

**Thứ nhất**, web server là một ứng dụng giúp người dùng có thể tìm kiếm thông tin liên quan đến website của mình. Do đó, bạn cần có một máy tính cấu hình cao, lưu trữ được dung lượng lớn dữ liệu và đáp ứng được số lượng lớn người dùng truy cập.  

**Thứ hai**, web server cần đảm bảo hoạt động liên tục 24/24 để cung cấp thông tin trực tuyến cho người dùng. Việc lựa chọn máy chủ web đóng vai trò quan trọng trong trong việc lưu chuyển thông tin từ server đến máy tính truy cập. Dịch vụ cho thuê web server ngày càng mở rộng và phát triển không ngừng, nó cho phép tạo ra nhiều gói dịch vụ để doanh nghiệp có thể đưa ra lựa chọn tối ưu nhất. Giữa trăm ngàn lựa chọn nhà cung cấp dịch vụ máy chủ web, bạn cần hiểu biết và tỉnh táo để lựa chọn được địa chỉ uy tín cung cấp sản phẩm chất lượng.

“Công ty TNHH phần mềm  Nhân Hòa” là lựa chọn đúng đắn nhất nếu bạn muốn thuê dịch vụ công nghệ thông tin và giải pháp mạng hoàn hảo về chất lượng với mức giá vô cùng hợp lý.

Như vậy, web server là thuật ngữ dùng để chỉ phần mềm hoặc phần cứng với nhiệm vụ xử lý các yêu cầu từ người dùng thông qua giao thức HTTP và một giao thức khác. Máy chủ web là máy tính có dung lượng lớn, tốc độ cao để lưu trữ và vận hành kho dữ liệu trên internet. Các web server phải đảm bảo tính liên tục để cung cấp dữ liệu cần thiết cho mạng lưới máy tính của người dùng.
