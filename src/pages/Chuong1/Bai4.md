---
title: Orverview
---

# Chạy thử nghiệm & giới thiệu cây thư mục

## 1. Tạo mới dự án

Khởi tạo dự án bằng câu lệnh `aiken new {tên tổ chức/tên dự án}`.

Cây thư mục khi mới khởi tạo gồm có:

- Một file `readme.md`, file này có thể dùng để mô tả dự án.
- Một file `aiken.toml`, đây là một file tệp cấu hình chính cho dự án Aiken, có
  một số vai trò như: Quản lý các phần phụ thuộc của dự án, là các thư viện
  ngoài aiken, cấu hình các tùy chọn của trình biên dịch hay xác định các thông
  tin chung về dự án như tên, mô tả và tác giả của dự án.
- Có một thư mục lib, trong thư mục này sẽ có một thư mục con nữa với tên trùng
  với tên dự án các bạn vừa khởi tạo, ở trong này, các bạn có thể viết nhiều thư
  viện con chứa các hàm, các kiểu dữ liệu tự định nghĩa, các bạn có thể gọi các
  thư viện đó ra trong file hợp đồng thông minh và sử dụng.
- Một thư mục `validators` chứa file hợp đồng thông minh, các bạn sẽ viết
  validator trong file này, và sau đó biên dịch ra thành file `plutus.json`, lưu
  ý rằng các bạn phải đặt tên của file hợp đồng thông minh trùng với tên của dự
  án, nếu không các bạn sẽ không thể nào biên dịch được ra mã cbor trong file
  `plutus.json`.
- Sau khi biên dịch sẽ sinh ra một file `Plutus.json`, đây chính là khung hợp
  đồng, nó là một loại tài liệu có thể tương tác tóm tắt dự án. Mỗi validator
  các bạn viết ra đều sẽ chứa một mã bytecode và một mã hash tương ứng, đó chính
  là địa chỉ của hợp đồng.

## 2. Biên soạn một dự án

Các bạn có thể sử dụng `aiken build` để biên dịch file hợp đồng thông minh mà
các bạn đã viết trong thư mục `validators`, tức là có thể biên dịch toàn bộ dự
án Aiken, chuyển mã nguồn thành các tập lệnh thực thi hoặc thư viện có thể sử
dụng được thành mã CBOR để có thể giao tiếp với onchain. Ngoài ra, để kiểm tra
xem các lệnh mà bạn viết có đúng nguyên tắc hay không có thể sử dụng aiken
check, lệnh này cũng có thể giúp các bạn kiểm tra các hàm test mà các bạn có thử
nghiệm trong file hợp đồng, các bạn có thể dùng các hàm test này để kiểm tra xem
các hàm hay những đoạn logic nhỏ các bạn có viết đúng hay không, đồng thời câu
lệnh này thì cũng có thể nhắc nhở các bạn những biến nào không được dùng hay
những hàm nào khai báo vào hợp đồng nhưng không sử dụng đến, mục đích là để
tránh lãng phí tài nguyên và tiết kiệm chi phí cho từng kb tập lệnh.

Ngoài ra, các bạn có thể sử dụng aiken docs để tạo tài liệu HTML cho dự án aiken
dựa trên các kiểu dữ liệu, chú thích và nhận xét trên mã nguồn, các bạn có thể
vào đây và đọc các thư viện có trong aiken, trong này họ có giải thích rất rõ về
từng kiểu dữ liệu và các hàm có trong aiken.

Về lệnh aiken blueprint (nhóm lệnh): có 3 nhóm lệnh sau

- `aiken blueprint generate-addresses`: Lệnh này có thể áp dụng để tạo địa chỉ
  cho các hợp đồng thông minh
- `aiken blueprint apply-parameters`: Áp dụng các tham số cụ thể cho blueprint
- `aiken blueprint convert`: Chuyển đổi đầu ra bản dựng (`plutus.json`) sang các
  định dạng khác nhau.

## 3. Các thư viện chính thức do TxPipe phát hành

Ở đây sẽ có 2 loại thư viện

- Với các kiểu dữ liệu và các hàm nền tảng của ngôn ngữ lập trình aiken, bao gồm
  cả các kiểu dữ liệu nguyên thủy, các bạn có thể truy cập vào
  [Thư viện Aiken nền tảng](https://aiken-lang.github.io/prelude/aiken.html) để
  đọc và hiểu rõ hơn.
- Những hàm và kiểu dữ liệu liên quan đến các giao dịch để phục vụ cho việc viết
  hợp đồng thông minh sẽ ở thư viện [Thư viện Aiken được xây dựng sẵn](https://aiken-lang.github.io/stdlib/), các
  bạn có thể đọc tại trang này hoặc có thể đọc trực tiếp trong thư viện aiken có
  trong project khi các bạn thực hiện aiken build hoặc aiken check lần đầu tiên.

Hãy cùng nhau học và phát triển kỹ năng lập trình của bạn!

Chúc các bạn thành công và không ngừng nâng cao trình độ của mình!
