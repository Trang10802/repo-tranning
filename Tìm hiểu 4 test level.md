> # Unit testing

+ Định nghĩa: Test ở mức cơ bản, test từng module nhỏ trong hệ thống do lập trình viên (DEV) thực hiện...

+ Mục tiêu: Để xác nhận các thành phần của phần mềm phát triển đúng với thiết kế.
+ Quy trình :  
  + Bước 1: Tập hơp các input
  + Bước 2: Thực hiện đưa các input vào các function, procedure
  + Bước 3: Trả các output

+ Thời điểm thục hiện viết TestScript: trước khi thực hiện lập trình, 1 số trường hợp có thể thực hiện ở bất kỳ thời gian nào.

- Thời điểm thực thi UT: Sau khi code

- Phương pháp thực hiện: Sử dụng các kỹ thuật white box testing

- Đới tưởng sử dụng: Được thực hiện bởi các Developer

+ Giá trị mang lại: 
  + Các issues được tìm ra sớm, được fix mà không bị ảnh hưởng các phần code khác.
  + Giúp bảo trì và thay đổi code. Vì vậy code ít bị phụ thu thuộc nhau. Ut có thể thực hiện được, giảm ảnh hưởng code.
  + Bug được tìm ra sớm nên giảm chi phí fix bug so với việc bug tìm thấy trong các giai đoạn như System test,  Acceptance test.
  + Đơn giản hóa quá trình debug lỗi. Nếu 1 kiểm thử false, chúng ta chỉ cần thực hiện dubeg những thay đổi gần đây nhất.
 
> # Integration Testing

## Big Bang
- Tất cả các thành phần được tích hợp đông thời, sau đó quy trình được kiểm thử một cách tổng thể.

+ Ưu điểm
  + Các vấn đề được thực hiện và hoàn thành trước khi thực hiện Intergration test, loại hình này thích hợp cho hệ thống nhỏ.

+ Nhược điểm 
  + Tốn thời gian
  + Testing được thực hiện đồng thời 1 lúc

-Các phần được phát triển (develop) sẽ tích hợp với nhau từng phần một, testing được thực hiện sau mỗi phần tích hợp.

- Ưu điểm : Các lỗi được tìm ra sớm trong phạm vi nhỏ -> dễ dàng tìm ra nguyên nhân lỗi.

- Nhược điểm: Có thể tốn thời gian kể từ khi Stub, Driver được phát triển và được sử dụng trong ác thử nghiểm. Thực hiện Intergration Test tăng trưởng dần, phụ thuộc vào cấu trúc hệ thống.

- Thực hiện test từ trên xuống dưới theo Control Flow hoặc cấu trúc kiến trúc. Các thành phần hoặc hệ thống thay thế bằng Stub, test stubs mô phỏng các đơn vị mức dưới - những đơn vị chưa sẵn sàng trong những phases đầu tiền.

+ Ưu điểm:
  + Việc thực hiện test sản phẩm rất tốt vì IT được thực hiện ở môi trường tương tự như môi trường thật.
  + Stub được viết ít thời gian hơn, đơn giản hơn.
  + Dễ tìm được lỗi
  + Có prototype sớm
  + Các module quan trọng được ưu tiên test trước, các lỗi trong thiết kế chính được tìm thấy và fix trước.

+ Nhược điểm: Cần nhiều Stub, các module ở mức thấp chỉ được test qua loa.

## Bottom up

- Thực hiện test từ dưới lên trên của Control Flow. Các thành phần được thay thế bằng Drivers, Test Driver mô phỏng các đơn vị ở mức độ cao hơn - Không phù hợp để sử dụng cho các phase ban đầu.

* Ưu điểm: 
  * Quá trình phát triển và kiểm thử được thực hiện cùng nhau nên sản phẩm sẽ đáp ứng các đặc tả của khách hàng.
  * Các lỗi (Bugs) dễ dàng phát hiện hơn 
  * Không mất thời gian chờ đợi các module như phương pháp Big Bang

* Nhược điểm 
  * Các lỗi chính về giao diện chỉ được tìm thấy ở cuối chu kỳ
  * Chức năng quan trọng cũng được test ơt cuối và có thể phát sinh lỗi.
  
   > # System Testing
  

- Định nghĩa: System testing là việc kiểm thử một hệ thống đã được tích hợp hoàn chỉnh để xác minh khả năng đáp ứng của sản phẩm với yêu cầu ban đầu.

- Mục đích : Để đánh giá tuân thủ của hệ thống so với đặc tả yêu cầu ban đầu

- Thời gian thực hiện: ST thường được thực hiện ở cuối các giai đoạn phát triển.

- Đối tượng thực hiện: ST được thực hiện bởi các chuyên gia kiểm thử hoặc được một nhóm test thực hiện một cách độc lập với đội phát triển
- Các loại hình:
  - Functional
  - Non- functional
  
> # UAT( Alpha- Beta)
- Định nghĩa : Kiểm thử được thực hiện bởi user hoặc khách hàng để xác minh/ chấp nhận hệ thống phần mềm trước khi chuyển ứng dụng phần mềm sang môi trường production.

- Mục đích: Để dánh giá tính tuân thủ  của hệ thống đúng với đặc tả yêu cầu.

- Điều kiện tiêu đề:
  - Các nhóm phát triển đã thực hiện kiểm chứng hệ thống và sửa chữa tất cả các lỗi.
  - Bàn giao hệ thống cho user hoặc khách hàng để thực hiện Acceptance testing

+ Đối tượng thực hiện: 
  + Acceptance testing là trách nhiệm của user, khách hàng, stakeholder.
  + Các tiêu chí nghiệm thu phải được xác định khi hợp đồng được thỏa thuận.

Môi trường test: Giống Production

## Alpha test

- Đây là một dạng kiểm thử chấp nhận nội bộ được thực hiện chủ yếu bởi các QA và testing team. Alpha là thử nghiệm cuối cùng được thực hiện bởi các test teams tại development site sau acceptance test và trước khi releas để kiểm thử beta.

- Alpha test cũng có thể được thực hiện bởi người dùng tiềm năng hoặc khách hàng của ứng dụng.
## Beta test

- Đây là giai đoạn kiểm thử cuối cùng, nơi các công ty phát hành phần mềm cho vài nhóm người dùng bên ngoài khác với nhóm kiểm thử của công ty hoặc nhân viên. Phiên bản phần mềm ban đầu này được gọi là phiên bản beta. Hầu hết các công ty thu thập phản hồi của người dùng trong bản phát hành này.

- Thử nghiệm beta có thể được định nghĩa là - thử nghiệm được thực hiện bởi người dùng thực trong môi trường thực.
