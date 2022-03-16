# I. Mô hình OSI là gì?
Mô hình kết nối các hệ thống mở OSI là mô hình căn bản về các tiến trình truyền thông, thiết lập các tiêu chuẩn kiến trúc mạng ở mức Quốc tế, là cơ sở chung để các hệ thống khác nhau có thể liên kết và truyền thông được với nhau. Mô hình OSI tổ chức các giao thức truyền thông thành 7 tầng, mỗi một tầng giải quyết một phần hẹp của tiến trình truyền thông, chia tiến trình truyền thông thành nhiều tầng và trong mỗi tầng có thể có nhiều giao thức khác nhau thực hiện các nhu cầu truyền thông cụ thể

![image](https://user-images.githubusercontent.com/101611197/158511637-bb6e048a-e1e1-4e0c-b672-a2e0a93b8468.png)

Mô hình OSI tuân theo các nguyên tắc phân tầng như sau:

Mô hình gồm 7 tầng. OSI là hệ thống mở, phải có khả năng kết nối với các hệ thống khác nhau, tương thích với các chuẩn OSI.

Quá trình xử lý các ứng dụng được thực hiện trong các hệ thống mở, trong khi vẫn duy trì được các hoạt động kết nối giữa các hệ thống.

Thiết lập kênh logic nhằm mục đích thực hiện việc trao đổi thông tin giữa các thực thể.

# Các giao thức trong mô hình OSI
Trong mô hình OSI có hai loại giao thức được sử dụng: giao thức hướng liên kết (Connection – Oriented) và giao thức không liên kết (Connectionless).

## Giao thức hướng liên kết
Trước khi truyền dữ liệu, các thực thể đồng tầng trong hai hệ thống cần phải thiết lập một liên kết logic. Chúng thương lượng với nhau về tập các tham số sẽ sử dụng trong giai đoạn truyền dữ liệu, cắt/hợp dữ liệu, liên kết sẽ được hủy bỏ. Thiết lập liên kết logic sẽ nâng cao độ tin cậy và an toàn trong quá trình trao đổi dữ liệu.

## Giao thức không liên kết
Dữ liệu được truyền độc lập trên các tuyến khác nhau. Với các giao thức không liên kết chỉ có giai đoạn duy nhất truyền dữ liệu.

# Vai trò và chức năng chủ yếu các tầng.
## Vai trò và chức năng tầng ứng dụng (Application Layer)
Nhiệm vụ của tầng này là xác định giao diện giữa người sử dụng và môi trường OSI. Bao gồm nhiều giao thức ứng dụng cung cấp các phương diện cho người sử dụng truy cập vào môi trường mạng và cung cấp các dịch vụ phân tán. Khi các thực thể ứng dụng AE (Application Entity) được thiết lập, nó sẽ gọi đến các phần tử dịch vụ ứng dụng ASE (Application Service Element). Mỗi thực thể ứng dụng có thể gồm một hoặc nhiều các phần tử dịch vụ ứng dụng. Các phần tử dịch vụ ứng dụng được phối hợp trong môi trường của thực thể ứng dụng thông qua các liên kết gọi là đối tượng liên kết đơn SAO (Single Association Object). SAO điều khiển việc truyền thông và cho phép tuần tự hóa các sự kiện truyền thông.

## Vai trò và chức năng tầng trình bày (Presentation Layer)
Tầng trình bày giải quyết các vấn đề liên quan đến các cú pháp và ngữ nghĩa của thông tin được truyền. Biểu diễn thông tin người sử dụng phù hợp với thông tin làm việc của mạng và ngược lại. Thông thường biểu diễn thông tin các ứng dụng nguồn và ứng dụng đích có thể khác nhau bởi các ứng dụng được chạy trên các hệ thống có thể khác nhau. Tầng trình bày phải chịu trách nhiệm chuyển đổi dữ liệu gửi đi trên mạng từ một loại biểu diễn này sang một loại biểu diễn khác. Để đạt được điều đó nó cung cấp một dạng biểu diễn truyền thông chung cho phép chuyển đổi từ dạng biểu diễn cục bộ sang biểu diễn chung và ngược lại

## Vai trò và chức năng tầng phiên (Session Layer)
Tầng phiên cho phép người sử dụng trên các máy khác nhau thiết lập, duy trì và đồng bộ phiên truyền thông giữa họ với nhau. Nói cách khác tầng phiên thiết lập “các giao dịch” giữa các thực thể đầu cuối.

Dịch vụ phiên cung cấp một liên kết giữa 2 đầu cuối sử dụng dịch vụ phiên sao cho trao đổi dữ liệu một cách đồng bộ và khi kết thúc thì giải phóng liên kết. Sử dụng thẻ bài (Token) để thực hiện truyền dữ liệu, đồng bộ hóa và hủy bỏ liên kết trong các phương thức truyền đồng thời hay luân phiên. Thiết lập các điểm đồng bộ hóa trong hội thoại. Khi xảy ra sự cố có thể khôi phục hội thoại bắt đầu từ một điểm đồng bộ hóa đã thỏa thuận.

## Vai trò và chức năng tầng vận chuyển (Transport Layer)
Là tầng cao nhất liên có liên quan đến các giao thức trao đổi dữ liệu giữa các hệ thống mở, kiểm soát việc truyền dữ liệu từ nút tới nút (End-to-End). Thủ tục trong 3 tầng dưới (vật lý, liên kết dữ liệu và mạng) chỉ phục vụ việc truyền dữ liệu giữa các tầng kề nhau trong từng hệ thống. Các thực thể đồng tầng hội thoại, thương lượng với nhau trong quá trình truyền dữ liệu.

Tầng vận chuyển thực hiện việc chia các gói tin lớn thành các gói tin nhỏ hơn trước khi gửi đi và đánh số các gói tin và đảm bảo chúng chuyển theo đúng thứ tự. Là tầng cuối cùng chịu trách nhiệm về mức độ an toàn trong truyền dữ liệu nên giao thức tầng vận chuyển phụ thuộc nhiều vào bản chất của tầng mạng. Tầng vận chuyển có thể thực hiện việc ghép kênh (multiplex) một vài liên kết vào cùng một liên kết nối để giảm giá thành.

## Vai trò và chức năng tầng mạng (Network Layer)
Tầng mạng thực hiện các chức năng chọn đường đi (routing) cho các gói tin nguồn tới đích có thể trong cùng một mạng hoặc khác mạng nhau. Đường có thể được cố định, cũng có thể được định nghĩa khi bắt đầu hội thoại và có thể đường đi là động (Dynamic) có thể thay đổi với từng gói tin tùy theo trạng thái tải tức thời của mạng. Trong mạng kiểu quảng bá (Broadcast) routing rất đơn giản.

Một chức năng quan trọng khác của tầng mạng là chức năng điều khiển tắc nghẽn (Congestion Control). Nếu có quá nhiều gói tin cùng lưu chuyển trên cùng một đường thì có thể xảy ra tình trạng tắc nghẽn. Thực hiện chức năng giao tiếp giữa các mạng khi các gói tin đi từ mạng này sang mạng khác để tới đích

## Vai trò và chức năng tầng liên kết dữ liệu (Data Link Layer)
Chức năng chủ yếu của tầng liên kết dữ liệu là thực hiện thiết lập các liên kết, duy trì và hủy bỏ các liên kết dữ liệu. Kiểm soát lỗi và kiểm soát lưu lượng.

Chia thông tin thành các khung thông tin (Frame), truyền các khung tuần tự và xử lý các thông điệp xác nhận (Acknowledgement Frame) từ bên máy thu gửi về. Tháo gỡ các khung thành chuỗi bit không cấu trúc chuyển xuống tầng vật lý. Tầng 2 bên thu, tái tạo chuỗi bit thành các khung thông tin. Đường truyền vật lý có thể gây ra lỗi, nên tầng liên kết dữ liệu phải giải quyết vấn đề kiểm soát lỗi, kiểm soát luồng, kiểm soát lưu lượng, ngăn không để nút nguồn gây “ngập lụt” dữ liệu cho ben thu có tốc độ thấp hơn. Trong các mạng quảng bá, tầng con MAC (Medium Access Sublayer) điều khiển việc duy trì nhập đường truyền.

## Vai trò và chức năng tầng vật lý (Physical Layer)
Tầng vật lý là tầng thấp nhất trong mô hình 7 lớp OSI. Các thực thể tầng giao tiếp với nhau qua một đường truyền vật lý. Tầng vật lý xác định các chức năng, thủ tục về điện, cơ, quang để kích hoạt, duy trì và giải phóng các kết nối vật lý giữa các hệ thống mạng. Cung cấp các cơ chế về điện, hàm, thủ tục, … nhằm thực hiện việc kết nối các phần tử của mạng thành một hệ thống bằng các phương pháp vật lý. Đảm bảo cho các yêu cầu về chuyển mạch hoạt động nhằm tạo ra các đường truyền thực cho các chuỗi bit thông tin. Các chuẩn trong tầng vật lý là các chuẩn xác định giao diện người sử dụng và môi trường mạng. Các giao thức tầng vật lý có hai loại: truyền dị bộ (Asynchronous) và truyền đồng bộ (Synchronous).

# Tóm tắt chức năng các tầng giao thức trong OSI

|Tầng|Chức năng chủ  yếu|Giao thức|
|------------------------|-----------------|----------------|
|7 - Application|Giao tiếp người và môi trường mạng|Ứng dụng|
|6 – Presentation|Chuyển đổi cú pháp dữ liệu để đáp ứng yêu cầu truyền thông của các ứng dụng|Giao thức Biến đổi mã|
|5 - Session|Quản lý các cuộc liên lạc giữa các thực thể bằng cách thiết lập, duy trì, đồng bộ hóa và hủy bỏ các phiên truyền thông giữa các ứng dụng|Giao thức phiên|
|4 – Transpost|Vận chuyển thông tin giữa các máy chủ (End to End). Kiểm soát lỗi và luồng dữ liệu|Giao thức Giao vận|
|3 – Network|Thực hiện chọn đường và đảm bảo trao đổi thông tin trong liên mạng với công nghệ chuyển mạch thích hợp.|Giao thức mạng|
|2 – Data Link|Tạo/gỡ bỏ khung thông tin (Frames), kiểm soát luồng và kiểm soát lỗi.|Thủ tục kiểm soát|
|1 - Physical|Đảm bảo các yêu cầu truyền/nhận các chuỗi bit qua các phương tiện vật lý.|Giao diện DTE - DCE|

## Ưu điểm của OSI:

OSI phân thành nhiều tầng nhỏ và đơn giản hơn.

OSI chuẩn hóa các thành phần mạng để phát triển dễ dàng hơn.

OSI chuẩn hóa giao diện giữa các tầng.

Dữ liệu được truyền nhanh chóng và dễ dàng hơn.
## Nhược điểm

Tầng phiên và tầng trình diễn thường không được sử dụng nhiều so với các tầng khác vì chức năng hạn hẹp của nó.

Không hỗ trợ các giao thức, không định nghĩa bất kì giao thức nào.

Nhiều dịch vụ trùng lặp tại các tầng, ví dụ tầng mạng và tầng liên kết dữ liệu.

Các tầng không thể hoạt động song song, tầng dưới phải chờ dữ liệu từ tầng trên.

# II. Mô hình TCP/IP là gì?
TCP/ IP (Transmission Control Protocol/ Internet Protocol - Giao thức điều khiển truyền nhận/ Giao thức liên mạng), là một bộ giao thức trao đổi thông tin được sử dụng để truyền tải và kết nối các thiết bị trong mạng Internet. TCP/IP được phát triển để mạng được tin cậy hơn cùng với khả năng phục hồi tự động.

![image](https://user-images.githubusercontent.com/101611197/158516368-ffefe739-e423-4835-b73b-887685cb1c7a.png)

## Cách thức hoạt động của mô hình TCP/IP
Phân tích từ tên gọi, TCP/IP là sự kết hợp giữa 2 giao thức. Trong đó IP (Giao thức liên mạng) cho phép các gói tin được gửi đến đích đã định sẵn, bằng cách thêm các thông tin dẫn đường vào các gói tin để các gói tin được đến đúng đích đã định sẵn ban đầu. Và giao thức TCP (Giao thức truyền vận) đóng vai trò kiểm tra và đảm bảo sự an toàn cho mỗi gói tin khi đi qua mỗi trạm. Trong quá trình này, nếu giao thức TCP nhận thấy gói tin bị lỗi, một tín hiệu sẽ được truyền đi và yêu cầu hệ thống gửi lại một gói tin khác. Quá trình hoạt động này sẽ được làm rõ hơn ở chức năng của mỗi tầng trong mô hình TCP/IP.

## Chức năng của các tầng trong mô hình TCP/IP
Một mô hình TCP/IP tiêu chuẩn bao gồm 4 lớp được chồng lên nhau, bắt đầu từ tầng thấp nhất là Tầng vật lý (Physical) → Tầng mạng (Network) → Tầng giao vận (Transport) và cuối cùng là Tầng ứng dụng (Application).

![image](https://user-images.githubusercontent.com/101611197/158516878-1f57ed15-5318-47ff-b302-5e2dcc1d40bd.png)

**Tầng 4 - Tầng Ứng dụng (Application)**

Đây là lớp giao tiếp trên cùng của mô hình. Đúng với tên gọi, tầng Ứng dụng đảm nhận vai trò giao tiếp dữ liệu giữa 2 máy khác nhau thông qua các dịch vụ mạng khác nhau (duyệt web, chat, gửi email, một số giao thức trao đổi dữ liệu: SMTP, SSH, FTP,...). Dữ liệu khi đến đây sẽ được định dạng theo kiểu Byte nối Byte, cùng với đó là các thông tin định tuyến giúp xác định đường đi đúng của một gói tin

![image](https://user-images.githubusercontent.com/101611197/158517020-a42fe689-8514-44e2-b81c-d22fc43d221f.png)

**Tầng 3 - Tầng Giao vận (Transport)** 

Chức năng chính của tầng 3 là xử lý vấn đề giao tiếp giữa các máy chủ trong cùng một mạng hoặc khác mạng được kết nối với nhau thông qua bộ định tuyến. Tại đây dữ liệu sẽ được phân đoạn, mỗi đoạn sẽ không bằng nhau nhưng kích thước phải nhỏ hơn 64KB. Cấu trúc đầy đủ của một Segment lúc này là Header chứa thông tin điều khiển và sau đó là dữ liệu.

Trong tầng này còn bao gồm 2 giao thức cốt lõi là TCP và UDP. Trong đó, TCP đảm bảo chất lượng gói tin nhưng tiêu tốn thời gian khá lâu để kiểm tra đầy đủ thông tin từ thứ tự dữ liệu cho đến việc kiểm soát vấn đề tắc nghẽn lưu lượng dữ liệu. Trái với điều đó, UDP cho thấy tốc độ truyền tải nhanh hơn nhưng lại không đảm bảo được chất lượng dữ liệu được gửi đi.

![image](https://user-images.githubusercontent.com/101611197/158517072-f1beb15b-bf36-4e5d-ba63-c5a1ee8ed704.png)

**Tầng 2 - Tầng mạng (Internet)** 

Gần giống như tầng mạng của mô hình OSI. Tại đây, nó cũng được định nghĩa là một giao thức chịu trách nhiệm truyền tải dữ liệu một cách logic trong mạng. Các phân đoạn dữ liệu sẽ được đóng gói (Packets) với kích thước mỗi gói phù hợp với mạng chuyển mạch mà nó dùng để truyền dữ liệu. Lúc này, các gói tin được chèn thêm phần Header chứa thông tin của tầng mạng và tiếp tục được chuyển đến tầng tiếp theo. Các giao thức chính trong tầng là IP, ICMP và ARP.

![image](https://user-images.githubusercontent.com/101611197/158517153-975b1c9d-966f-4350-acca-419774dcee07.png)

**Tầng 1 - Tầng Vật lý (Physical)** 

Là sự kết hợp giữa tầng Vật lý và tầng liên kết dữ liệu của mô hình OSI. Chịu trách nhiệm truyền dữ liệu giữa hai thiết bị trong cùng một mạng. Tại đây, các gói dữ liệu được đóng vào khung (gọi là Frame) và được định tuyến đi đến đích đã được chỉ định ban đầu.

## Ưu điểm của TCP/IP:

Mô hình TCP/IP không chịu sự kiểm soát của tổ chức nào. Do đó, người dùng có thể tự do sử dụng.

TCP/IP có khả năng tương thích với các mạng, hệ điều hành và phần cứng máy tính.

TCP/IP có khả năng khả năng định tuyến, mở rộng và nhận định được đường dẫn tốt nhất thông qua mạng.

## Nhược điểm

Khó khăn trong việc thay thế các giao thức mới.

Một tầng có nhiều chức năng nên phức tạp hơn so với mô hình OSI.

Không có sự phân biệt dõ dàng giữa dịch vụ, giao diện và giao thức
# So sánh 2 mô hình
##  - Điểm tương đồng giữa mô hình OSI và TCP/IP
+ Chia sẻ kiến trúc chung

Cả 2 mô hình đều là mô hình logic và có kiến trúc tương tự vì cả 2 mô hình đều được xây dựng dựa trên các lớp

+ Xác định tiêu chuẩn 

Cả 2 lớp đều có các tiêu chuẩn xác định và chúng cũng cung cấp khuôn khổ được sử dụng để thực hiện các tiêu chuẩn và thiết bị

+ Quy trình khắc phục sự cố được đơn giản hóa

Cả 2 mô hình đã đơn giản hóa quá trình khắc phục sự cố bằng cách chia nhỏ chức năng phức tạp thành các thành phần đơn giản hơn

+ Các tiêu chuẩn được xác định trước

Các tiêu chuẩn và giao thức đã được xác định trước, những mô hình này không xác định lại chúng, chỉ tham khảo hoặc sử dụng lại chúng. Ví dụ, các tiêu chuẩn Ethernet đã được IEEE xác định trước khi phát triển các mô hình 

+ Cả 2 đều có chức năng tương tự của các lớp Transport và Network

Chức năng được thực hiện giữa lớp Presentation và lớp Network tương tự như chức năng được thực hiện ở lớp Transport

##  Sự khác biệt giữa mô hình OSI và TCP/IP

|Nội dung| Mô Hình OSI| Mô Hình TCP/IP|
|----------|------------|--------------|
|Độ tin cậy và phổ biến|Nhiều người cho rằng đây là mô hình cũ, chỉ để tham khảo, số người sử dụng hạn chế hơn so với TCP/IP|Được chuẩn hóa, nhiều người tin cậy và sử dụng phổ biến trên toàn cầu|
|Phương án tiếp cận|Tiếp cận theo chiều dọc|Tiếp cận theo chiều ngang|
|Sự kết hợp giữa các tầng|Mỗi tầng khác nhau sẽ thực hiện một nhiệm vụ khác nhau, không có sự kết hợp giữa bất cứ tầng nào|Trong tầng ứng dụng có tầng trình diễn và tầng phiên được kết hợp với nhau|
|Thiết kế|Phát triển mô hình trước, sau đó sẽ phát triển giao thức|Các giao thức được thiết kế trước sau đó phát triển mô hình|
|Số lớp (Tầng)|7|4
|Truyền thông|Hỗ trợ cả kết nối định tuyến và không dây|Hỗ trợ truyền thông không kết nối từ tầng mạng|
|Tính phụ thuộc|Giao thức độc lập| Phụ thuộc vào giao thức|

