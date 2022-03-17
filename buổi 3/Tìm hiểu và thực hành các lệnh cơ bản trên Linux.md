# Tìm hiểu và thực hành các lệnh cơ bản của Linux

**1**. Lệnh **PWD**: Lệnh này được dùng để tìm đường dẫn của thư mục hiện tại (folder) mà chúng ta đang ở trong đó. Yêu cầu này sẽ trả về đường dẫn hoàn chỉnh, bắt đầu bằng dấu gạch chéo (/).

![image](https://user-images.githubusercontent.com/101611197/158766776-00f60af1-eae7-43b8-a5f7-7d547898324d.png)

Ở đây mình thực hiện command này ở Desktop nên đường dẫn được trả về là **/home/ngocdat/Desktop.**

**2**. Lệnh **cd**: Đây là lệnh chuyển hướng trong hệ thống tập tin của Linux. Nó sẽ cần nhập đường dẫn đầy đủ hoặc tên thư mục bạn muốn chuyển tới.

![image](https://user-images.githubusercontent.com/101611197/158768433-c648900e-b186-4cd3-872b-1677799dfb19.png)

Ví dụ như trường hợp này. Mình đang ở thư mục Desktop. Sau đó mình di chuyển vào thư mục ngocdat và ngược lại.

**3**. Lệnh **ls**: Lệnh này sẽ hiển thị danh sách file trong thư mục hiện tại.

Có nhiều phiên bản để dùng với lệnh ls như sau:

- **ls -R** liệt kê các file bao gồm cả các thư mục phụ bên trong

- **ls -a** liệt kê những file ẩn

- **ls -al** liệt kê tất cả file và thư mục với thông tin chi tiết như phân quyền, kích thước, chủ sở hữu, vân vân.

![image](https://user-images.githubusercontent.com/101611197/158771432-360f0f2f-07b9-4928-8817-84eb658c135b.png)

Ví dụ ở đây: Mình có 1 thư mục tên là folder1 bao gồm bên trong có 2 thư mục phụ (1 cái đã bị ẩn đi), và 2 file .txt. Bây giờ chúng ta sẽ thực hiền lần lượt các lệnh trên.

![image](https://user-images.githubusercontent.com/101611197/158772850-f196e14b-43af-4d02-ac84-0bc951a3841a.png)

**4**. Lệnh **cp**: Đây là lệnh để sao chép files từ thư mục hiện tại

Hình ảnh folder1 và folder2 ban đầu

![image](https://user-images.githubusercontent.com/101611197/158774501-c3951937-f6b6-43ca-9047-b30dccb3fdb3.png)

Hình ảnh folder1 và folder2 sau khi dùng lệnh cp để coppy file **vanban1.txt** từ folder1 sang folder2

![image](https://user-images.githubusercontent.com/101611197/158775069-37e9c1bc-ee1a-419c-a777-0a49aca3b39b.png)

**5**. Lệnh **mv**: Đây là lệnh để di chuyển file. Ngoài ra nó cũng có thể được dùng để đổi tên file.

Hình ảnh folder1 và folder2 ban đầu

![image](https://user-images.githubusercontent.com/101611197/158775681-94edd108-509b-4b22-be67-5e76c6a2401f.png)

Hình ảnh folder1 và folder2 sau khi di chuyển file vanban2.txt từ folder1 sang folder2

![image](https://user-images.githubusercontent.com/101611197/158775949-bea22e7c-6411-40eb-99f1-dc447e5be657.png)

Hình ảnh sau khi đổi tên file vanban2.txt thành text.txt

![image](https://user-images.githubusercontent.com/101611197/158776280-eee88753-04e1-40b2-a421-84b48f2631c5.png)

**6**. Lệnh **mkdir**: Đây là lệnh được dùng để tạo thư mục mới

![image](https://user-images.githubusercontent.com/101611197/158776994-7f8c376c-f234-4d76-8dff-78c90651c341.png)

Hình ảnh mình vừa tạo thư mục folder1

![image](https://user-images.githubusercontent.com/101611197/158777511-87023319-63af-4270-8d9d-8f47073502df.png)

Chúng ta có thể tạo thêm 2 thư mục con ở trong thư mục folder1 bằng cú pháp như trên

**7**. Lệnh **rmdir**: Lệnh này được sử dụng để xóa cá thư mục trống

![image](https://user-images.githubusercontent.com/101611197/158778462-5cd7938b-5e37-411b-bb20-aecac7b1bb4a.png)

Ở đây. Thư mục TMG vì không phải là thư mục trống nên không thể xóa được. Còn thư mục folder12 thì ngược lại, vì là thư mục trống nên đã bị xóa đi.

**8**. Lệnh **rm**: Lệnh này được sử dụng để xóa tệp. Trường hợp bạn muốn dùng lệnh này để xóa thư mục thì bạn sẽ phải sử dụng cú pháp rm -r (và cú pháp này sẽ xóa cả nội dung bên trong)

![image](https://user-images.githubusercontent.com/101611197/158779922-756a435c-86de-46c3-8314-e7111bda3946.png)

**9**. Lệnh **touch**: Lệnh này được sử dụng để tạo file mới

![image](https://user-images.githubusercontent.com/101611197/158780695-f724d579-a286-43d5-af71-bd1edd57d305.png)

**10**. Lệnh **Sudo**: Lệnh này cho phép chúng ta thực hiện các tác vụ với quyền quản trị hoặc root. Tuy nhiên chúng ta k nên lạm dụng lệnh này bởi vì sẽ rất dễ bị lỗi nếu như làm sai.

**11**. Lệnh **head**: Lệnh này được sử dụng để xem dòng đầu tiên của bất kỳ văn bản nào. Theo mặc định, nó sẽ hiển thị 10 dòng đầu tiên, nhưng chúng ta có thể thay đổi số này theo ý mình

![image](https://user-images.githubusercontent.com/101611197/158783149-45633cbd-27bf-4e01-b4a3-9f6e4cdc3fe4.png)

**12**. Lệnh **tail**: Trái ngược với lệnh head, lệnh này được sử dụng để xem dòng cuối cùng của văn bản. Theo mặc định, nó sẽ hiển thị 10 dòng cuối cùng, nhưng chúng ta cũng có thể thay đổi được số dòng theo ý mình, tương tự như head

![image](https://user-images.githubusercontent.com/101611197/158783725-a1b3c34c-a638-486d-97da-648da2650ba9.png)

**13**. Lệnh **diff**: Lệnh này được sử dụng để so sánh nội dung từng dòng 1 của 2 file và sẽ hiển thị đoạn nội dung k giống nhau lên màn hình Terminal

![image](https://user-images.githubusercontent.com/101611197/158784933-3caf2c55-09d2-4e1a-a1ad-d3d01cd35334.png)

Ở đây mình đã thêm 2 đoạn bất kỳ vào 1 trong 2 file. Và đây là kết quả sau khi sử dụng lệnh **diff**


