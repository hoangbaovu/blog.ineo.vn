---
layout: post
title: Hướng dẫn cài đặt LAMP trên Ubuntu
excerpt_separator:  <!--more-->
---


### Cài đặt LAMP trên Ubuntu

LAMP là một nhóm các phần mềm mã nguồn mở được cài đặt cùng nhau để xây dựng môi trường web server:

* Hệ điều hành `Linux`
* Web server `Apache`
* Hệ quản trị cơ sở dữ liệu `MySQL`
* Ngôn ngữ lập trình `PHP`

Trong bài viết này, mình sẽ hướng dẫn các bạn cách cài đặt LAMP trên hệ điều hành Ubuntu 16.04.

### # Cập nhật Package

Trước khi làm việc ở Ubuntu, bạn nên tiến hành cập nhật gói phần mềm của Ubuntu lên phiên bản mới nhất với dòng lệnh:

```
sudo apt-get update
```

### # Cài đặt Tasksel

```
sudo apt-get install tasksel
```

```
sudo tasksel install lamp-server
```

Tiếp theo màn hình sẽ hiện cài đặt MySQL password

![alt text](http://sv1.upsieutoc.com/2017/12/30/u2.jpg "mysql password")

Nhập mật khẩu MySQL (Ở đây mình nhập mật khẩu `admin`)

Nhập lại mật khẩu MySQL

Sau bước này là bạn đã hoàn thành cài đặt LAMP (LINUX, Apache, PHP, MYSQL).

Bây giờ bạn mở trình duyệt, truy cập vào [localhost](http://localhost) trên trình duyệt sẽ được trang website như hình dưới:

![alt text](http://sv1.upsieutoc.com/2017/12/30/u1.jpg "localhost")


### # Cài đặt phpMyAdmin

Bước đầu tiên, sử dụng lệnh sau để cài đặt phpMyAdmin:

```
sudo apt-get install phpmyadmin
```

Trong quá trình cài đặt, hệ thống sẽ hỏi chúng ta chọn web server nào được tự động cấu hình khi chạy phpMyAdmin.

![alt text](http://sv1.upsieutoc.com/2017/12/30/u3.jpg "Chọn apache2")

Lúc này các bạn chọn `apache2` rồi nhấn `Enter` nhé.

Sau đó, hệ thống sẽ yêu cầu tạo mật khẩu cho phpMyAdmin thì các bạn cứ dùng mật khẩu đã tạo ở bước cài đặt MySQL cho dễ nhớ.

Tiếp tục mở file `/etc/apache2/apache2.conf` với lệnh

```
sudo gedit /etc/apache2/apache2.conf
```

Thêm dòng này vào cuối file vừa mở

```
Include /etc/phpmyadmin/apache.conf
```
Sau đó lưu lại

Cuối cùng khởi động lại Apache bằng lệnh

```
sudo service apache2 restart
```

Mở trình duyệt, vào địa chỉ [localhost/phpmyadmin](http://localhost/phpmyadmin)

phpMyadmin sẽ yêu cầu nhập tài khoản và mật khẩu thì các bạn nhập `root` và mật khẩu mà bạn đã tạo ở phần cài đặt.

OK, việc cài đặt LAMP trên Ubuntu đến đây đã hoàn tất!