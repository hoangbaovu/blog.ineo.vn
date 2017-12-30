---
layout: post
title: Tự động tạo Virtual Host LAMP trên Ubuntu
comments: true
excerpt_separator:  <!--more-->
category: Ubuntu
---

Đối với các bạn chuyên làm web thì chắc hẳn ai cũng hiểu cảm giác nhàm chán vì mỗi dự án lại phải tạo virtual host cho dự án mới. Đầu tiên là cấu hình virtual host trong file vhost, tiếp đến vào file hosts để thêm domain ảo, cuối cùng restart lại apache. Cho dù làm trên môi trường nào, bạn đều phải trải qua những thao tác này.

Hôm nay mình sẽ hướng dẫn các bạn cách tạo virtual host một cách tự động chỉ với một dòng lệnh duy nhất, nhằm rút ngắn thời gian cho những thao tác lặp đi lặp lại.

### # Cài đặt

Lần lượt nhập lệnh phía dưới vào terminal

```
cd /usr/local/bin
sudo wget -O virtualhost https://raw.githubusercontent.com/RoverWire/virtualhost/master/virtualhost.sh
sudo chmod +x virtualhost
```

### # Cách sử dụng

Cú pháp dòng lệnh cơ bản

```
sudo virtualhost [create | delete] [domain] [optional host_dir]
```

### # Ví dụ

Tạo một virtual host mới

```
sudo virtualhost create mysite.dev
```

![Ví dụ tạo virtual host](/assets/images/2017/12/31/virtual-host-1.jpg "ubuntu")

Thay vì tạo virtual host với đường dẫn mặc định là `/var/www/` thì bạn có thể tạo thư mục tùy chỉnh

```
sudo virtualhost create mysite.dev my_dir
```
![Ví dụ tạo virtual host đường dẫn tùy chỉnh](/assets/images/2017/12/31/virtual-host-2.jpg "ubuntu")

Sau khi tạo xong thì bạn cần phân quyền cho thư mục vừa tạo

```
sudo chmod -R 777 /home/hoangbaovu/mysite
```

Xóa virtual host

```
sudo virtualhost delete mysite.dev
```

---
Thử truy cập địa chỉ web vừa tạo

![Ví dụ tạo virtual host](/assets/images/2017/12/31/virtual-host-3.jpg "ubuntu")

Chúc các bạn thành công!!!