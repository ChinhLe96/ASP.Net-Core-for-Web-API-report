<h2>1.Cách sử dụng Postman: biến môi trường, biến sẵn có của postman, import, export. </h2>
POSTMAN là một App Extensions, cho phép làm việc với các API giúp ích rất nhiều cho việc testing. Hỗ trợ tất cả các phương thức HTTP (GET, POST, PUT, DELETE, OPTIONS, HEAD ...)<br>
POSTMAN cho phép lưu lại lịch sử các lần request, rất tiện cho việc sử dụng lại khi cần.<br>
<h3>Cài đặt </h3>
Để bắt đầu với POSTMAN, bạn truy cập vào trang chủ https://www.getpostman.com/ và download phiên bản phù hợp cho hệ điều hành đang sử dụng (có các phiên bản cho MAC OS, Windows 32bit, Window 64bit).<br>
    <img src="https://i.imgur.com/1DHjpTq.png"><br><br>
Sau khi tải về bạn tiến hành cài đặt bình thường và có thể sử dụng ngay.Bạn mở app lên giao diện .<br><br>
     <img src="https://i.imgur.com/6ZbkA66.png">  <br>
Như vậy là bạn có thể sử dụng POSTMAN rồi nhé. <br>
<h3>Các chức năng cơ bản</h3>
+ Cho phép gửi HTTP Request với các method GET, POST, PUT, DELETE.<br>
+ Cho phép post dữ liệu dưới dạng form (key-value), text, json<br>
+ Hiện kết quả trả về dạng text, hình ảnh, XML, JSON<br>
+ Cho phép thay đổi header của các request<br>
<h3> Sử dụng</h3>
Cách sử dụng Postman rất đơn giản, bạn chỉ việc điền Url của Api, chọn phương thức Get, Post... thêm các parameter cần thiết và ấn Send.<br>
Ví dụ ta lấy dữ liệu từ Server sử dụng method GET<br><br>
     <img src="https://i.imgur.com/i9UPvTm.png"> <br>
<h3>Biến môi trường trong Postman</h3>
Khi làm API, chúng ta thường có 3 môi trường, local, staging, production, mỗi môi trường sẽ có 1 base_url riêng nên khi test API trên cả 3 môi trường chúng ta phải tạo ra 3 request với thông số giống hệt nhau, chỉ khác mỗi base_url ==> gây một số bất tiện khi test API.<br>
Để giải quyết vấn đề trên, POSTMAN cung cấp cho chúng ta tùy chọn Environments Variable<br>
Environments variable cho phép ta cài đặt các biến môi trường, sau đó trong mỗi môi trường ta có thể lấy biến đó ra với nội dung riêng biệt.<br>
Ví dụ tạo tài khoản demo trên 2 môi trường ta có 2 url sau:<br>
+ Staging: http://lechinh.com/api/demo<br>
+ Local: http://localhost:1996/api/demo<br>
 Ta vào New chọn Environments giao diện sẽ hiện lên và ta tạo môi trường đặt tên là staging và local<br><br>
     <img src="https://i.imgur.com/6aGXjMT.png"> <br>
Bây giờ tạo 2 base_url cho 2 môi trường staging, local<br>
Staging: base_url = http://lechinh.com<br>
Local: base_url = http://localhost:1996<br><br>
  <img src="https://i.imgur.com/W6Q3ISc.png"> <br><br><br>
  <img src="https://i.imgur.com/trMM1YA.png"><br>
Sau đó, trong link gọi Web API, ta chỉ việc gọi biến base_url và đặt nó trong ngoặc nhọn {{}} là xong.<br><br>
   <img src="https://i.imgur.com/l4jQRRN.png"> <br>
Biến môi trường sẽ được sử dụng mọi nơi trong url, header, body...<br>
Bây giờ mỗi khi muốn test trên từng môi trường, bạn chỉ cẩn chuyển đổi qua lại các môi trường mà ko cần phải thay đổi đường dẫn url hoặc bất kì chỗ nào khác nếu bạn có sử dụng biến.<br>
   <img src="https://i.imgur.com/GRHSmjC.png"> <br>
<h3>Export trong Postman</h3>
`Collection:` Collection là một tập hợp của nhiều request. Những request liên quan tới nhau thì ta gom lại vào chung 1 collection để dễ quản lý hơn.<br>
Với mỗi dự án thì ta sẽ tạo 1 Collection riêng. Để share Collection với các thành viên khác trong team ta có thể với mỗi Collection ta export nó ra file json sau đấy gửi cho member khác và họ có thể import vào và dùng luôn trực tiếp được. <br>
`Các bước để thực hiện export 1 file JSON chứa các request`<br>
Bước 1.Tạo 1 collection: vào tab Collection trên Postman, sau đó click nút tạo mới 1 collection như hình vẽ<br><br>
   <img src="https://i.imgur.com/AsuN4Pi.png"> <br>
Tôi tạo 1 collection có tên Demo<br>
   <img src="https://i.imgur.com/bh2IDQf.png"> <br><br>
Bước 2.Bước tiếp theo là tạo và run 1 request, vào tab Hisroty, chọn option để Save request. Ở đây sau khi chọn Save request, ứng dụng sẽ cho phép người dùng chọn Collection muốn lưu request<br>
    <img src="https://i.imgur.com/Vz3jk8c.png"><br>
Ở đây ta Save request tại Collection Demo<br><br>
    <img src="https://i.imgur.com/pRG39AJ.png"><br>
Bước 3.Chúng ta đã có 1 set các request được chứa trong 1 Collection có tên Demo<br><br>
    <img src="https://i.imgur.com/aLt872o.png"><br>
Bước 4.Bước cuối cùng là Export ra để chia sẻ cho những người khác.<br><br>
   <img src="https://i.imgur.com/x2pQbE4.png"><br><br>
   <img src="https://i.imgur.com/PebXkan.png"><br>
- Chọn export bạn sẽ lấy được 1 file json, đó chính là Collection của bạn vừa thực hiện.<br>
<h3>Thực hiện import 1 file JSON chứa các request </h3>
Việc import vô cùng đơn giản. Trên thanh toolbar sẽ có 1 button là import, việc của bạn là ấn vào và trỏ đến file JSON vừa tạo.<br><br>
    <img src="https://i.imgur.com/wqAtc4v.png"><br><br>
    <img src="https://i.imgur.com/g98FSmm.png"><br>
Sau khi chọn xong bạn vào lại Collection và xem kết quả.<br>