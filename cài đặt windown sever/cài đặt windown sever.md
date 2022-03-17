**Chuẩn bị công cụ**

Đầu tiên, chúng ta cần phải chuẩn bị một vài thứ để có thể cài đặt Windows Server 2019 trên VMWare bao gồm:

- Bộ [**ISO Windows Server 2019 Evaluation**](https://www.microsoft.com/en-US/evalcenter/evaluate-windows-server-2019?filetype=ISO)
- [**Công cụ VMWare Workstation PRO**](https://datnt.work/download-vmware-workstation-16-pro/) để ảo hóa phần cứng cài đặt Windows Server 2019

**Cài đặt Windows Server 2019 trên VMWare Workstation**

Sau khi tải về ISO Windows Server và cài đặt VMWare Workstation vào máy tính, chúng ta cùng bắt đầu quá trình cài đặt Windows Server 2019 với việc khởi động VMWare Workstation và chọn **“Create a New Virtual Machine”**

![cai-dat-windows-server-2019-tren-vmware-workstation-datntblog](img/Aspose.Words.39a5fca3-f852-409e-bae5-16a9455d9a7e.001.png)

Tiếp đến, nếu bạn là người mới thao tác với VMWare Workstation thì tôi khuyến nghị lựa chọn **Typical** ở cửa sổ tiếp theo

![cai-dat-windows-server-2019-tren-vmware-workstation-datntblog](img/Aspose.Words.39a5fca3-f852-409e-bae5-16a9455d9a7e.002.png)

Lựa chọn mục thứ 3 để thêm ISO sau cùng vì nếu như bạn thêm ISO ở bước này, hệ thống sẽ bắt chúng ta khai báo một vài thông tin về tài khoản.

![cai-dat-windows-server-2019-tren-vmware-workstation-datntblog](img/Aspose.Words.39a5fca3-f852-409e-bae5-16a9455d9a7e.003.png)

Lựa chọn hệ điều hành cài đặt ở bước tiếp theo, ở đây tôi sẽ chọn **Microsoft** và **Windows Server 2016** (về cơ bản 2016 và 2019 là tương tự nên không lo lắng, do tôi sử dụng version VMWare cũ nên chưa được cập nhật)

![cai-dat-windows-server-2019-tren-vmware-workstation-datntblog](img/Aspose.Words.39a5fca3-f852-409e-bae5-16a9455d9a7e.004.png)

Tiếp đến, chúng ta cần đặt tên cho máy ảo Windows Server 2019 để phân biệt với các máy ảo khác và nơi lưu trữ máy ảo

![cai-dat-windows-server-2019-tren-vmware-workstation-datntblog](img/Aspose.Words.39a5fca3-f852-409e-bae5-16a9455d9a7e.005.png)

Khai báo thông số dung lượng ổ đĩa trên máy ảo khi tạo ra (mặc định sẽ là **60GB**) và lựa chọn **“Single virtual disk as a single file”**

![cai-dat-windows-server-2019-tren-vmware-workstation-datntblog](img/Aspose.Words.39a5fca3-f852-409e-bae5-16a9455d9a7e.006.png)

Ấn **Finish** để hoàn tất

![cai-dat-windows-server-2019-tren-vmware-workstation-datntblog](img/Aspose.Words.39a5fca3-f852-409e-bae5-16a9455d9a7e.007.png)

Ở màn hình mới, lựa chọn “**Edit virtual machine settings”** để thêm ISO vào trước khi bật máy ảo

![cai-dat-windows-server-2019-tren-vmware-workstation-datntblog](img/Aspose.Words.39a5fca3-f852-409e-bae5-16a9455d9a7e.008.png)

Lựa chọn **CD/DVD (SATA)**, phần Use ISO image file và lựa chọn nơi lưu trữ ISO Windows Server 2019, sau đó ấn **OK** để hoàn tất.

![cai-dat-windows-server-2019-tren-vmware-workstation-datntblog](img/Aspose.Words.39a5fca3-f852-409e-bae5-16a9455d9a7e.009.png)

Đến bước này, khởi chạy máy ảo lên bằng việc chọn **Power on this virtual machine**

![cai-dat-windows-server-2019-tren-vmware-workstation-datntblog](img/Aspose.Words.39a5fca3-f852-409e-bae5-16a9455d9a7e.010.png)

Hệ thống được khởi động, chọn ngôn ngữ và thời gian và bàn phím sau đó ấn **Next**

![cai-dat-windows-server-2019-tren-vmware-workstation-datntblog](img/Aspose.Words.39a5fca3-f852-409e-bae5-16a9455d9a7e.011.png)

Chọn **Install now**

![cai-dat-windows-server-2019-tren-vmware-workstation-datntblog](img/Aspose.Words.39a5fca3-f852-409e-bae5-16a9455d9a7e.012.png)

Lựa chọn hệ điều hành muốn cài đặt. Vì ở đây là cài đặt để lab nên tôi sẽ lựa chọn phiên bản cao cấp nhất **(Datacenter Evaluation có giao diện)** và ấn **Next**

![cai-dat-windows-server-2019-tren-vmware-workstation-datntblog](img/Aspose.Words.39a5fca3-f852-409e-bae5-16a9455d9a7e.013.png)

đồng thời đồng ý với **các điều khoản của Mcirosoft**

![cai-dat-windows-server-2019-tren-vmware-workstation-datntblog](img/Aspose.Words.39a5fca3-f852-409e-bae5-16a9455d9a7e.014.png)

Lựa chọn **Custom: Install Windows only (advanced)**

![cai-dat-windows-server-2019-tren-vmware-workstation-datntblog](img/Aspose.Words.39a5fca3-f852-409e-bae5-16a9455d9a7e.015.png)

Tiếp đến lựa chọn phân vùng để bung bộ cài đặt Windows Server 2019, vì ở đây có một ổ đĩa nên tôi sẽ ấn **Next** 

![cai-dat-windows-server-2019-tren-vmware-workstation-datntblog](img/Aspose.Words.39a5fca3-f852-409e-bae5-16a9455d9a7e.016.png)

Quá trình cài đặt sẽ tiếp tục diễn ra, tùy thuộc vào cấu hình của máy và ổ đĩa, thời gian sẽ diễn ra khoảng 10 phút.

![cai-dat-windows-server-2019-tren-vmware-workstation-datntblog](img/Aspose.Words.39a5fca3-f852-409e-bae5-16a9455d9a7e.017.png)

Sau khi quá trình cài đặt tự động hoàn tất và khởi động lại, bạn sẽ phải khai báo mật khẩu cho tài khoản Administrator ngay trước khi đăng nhập vào hệ điều hành (khác với Windows client sẽ có lựa chọn không cần tạo mật khẩu)

![cai-dat-windows-server-2019-tren-vmware-workstation-datntblog](img/Aspose.Words.39a5fca3-f852-409e-bae5-16a9455d9a7e.018.png)

Ấn **Finish** và đăng nhập vào hệ thống, sử dụng **Ctrl + Alt + Del** để unlock. Khi bạn sử dụng VMWare thì tổ hợp phím sẽ là **Ctrl + Alt + Insert**.

![cai-dat-windows-server-2019-tren-vmware-workstation-datntblog](img/Aspose.Words.39a5fca3-f852-409e-bae5-16a9455d9a7e.019.png)

Như vậy là chúng ta đã hoàn tất cài đặt Windows Server 2019 trên VMWare để thực hành

