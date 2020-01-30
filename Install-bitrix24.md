# Hướng dẫn cài đặt Bitrix24

## Môi trường làm việc  
- Cài đặt VMWARE, Navicat, PHPStorm, ssh client  
- Cài đặt centos 7 & Bitrix  

## Các bước cài đặt Bitrix24  

### Bước 1: Download file image  

Vào [link](https://www.bitrix24.com/self-hosted/installation.php) để tải file cài đặt.    

<img src="https://i.imgur.com/ZOi1XN5.png">

Sau khi tải gói cài về, bạn tiến hành giải nén.

### Bước 2: Cài đặt máy ảo trên VMWare Workstation  
- Mở VMWare và click vào `Open`. Bạn chọn đường dẫn thư mục chứa gói vừa giải nén. Sau đó thiết lập lại chế độ card mạng (NAT) cho VMBitrix

<img src="https://i.imgur.com/bG9CvUp.png">

- Khởi động máy ảo. Đợi một lúc VMBitrix sẽ hiển thị giao diện đăng nhập. Bạn login bằng user `root` và password `bitrix`  

<img src="https://i.imgur.com/O6AJ7u6.png">  

- Thay đổi mật khẩu đăng nhập cho user root   
- Tạo pool cho server  
Nhập 1 để tạo pool 

<img src="https://i.imgur.com/CZpDoGe.png">  

- Đặt tên cho server. Ví dụ `demo`  

<img src="https://i.imgur.com/2oTBjmC.png">  

- Tiếp theo ấn Enter để chuyển đến các bước cài đặt kế tiếp  

<img src="https://i.imgur.com/IuCkZI8.png">  

- Chọn `6` để quản lý site. Tiếp tục chọn `1` để tạo site mới.  

<img src="https://i.imgur.com/8QEdzZU.png">  

<img src="https://i.imgur.com/ntmb9IV.png">

Bạn thêm thông tin tên site và type. Sau đó chọn `0` để thoát, quay trở về giao diện ban đầu   

## Bước 3: Cấu hình IP tĩnh cho VMBitrix  

- Kiểm tra IP và card mạng  
```
ip a
```
- Kiểm tra thông tin devices  
```
nmcli dev
```
- Cấu hình IP tĩnh  
```
nmcli c modify "Wired connection 1" connection.id ens33
nmcli con modify ens7 ipv4.addresses 192.168.152.20/24
nmcli con modify ens7 ipv4.method manual
nmcli con modify ens7 connection.autoconnect yes
```
Lưu ý: Bạn set IP nằm trong dải mạng được cấp phát trong VMWare của bạn.
- Chạy lệnh khởi động lại network  
```
systemctl restart network
```

### Bước 4: Khai báo IP trong file hosts trên Windows  
Mở thư mục `hosts` trong `C:\Windows\System32\drivers\etc` và khai báo IP kèm dns  
```
192.168.152.20      demo
```

### Bước 4: Download và cài đặt Bitrix24  
-	Trên trình duyệt, vào http://demo , download và cài đặt bitrix package 

<img src="https://i.imgur.com/s5Gx9xo.png">  

- Qua một vài bước cài đặt bạn sẽ nhận được giao diện dành cho người dùng như sau  

<img src="https://i.imgur.com/KBMW00m.png">  

Bạn chọn `CONFIRM` để xác nhận và tiếp tục sử dụng.  

- Để thao tác với Bitrix24 Backend, trên url bạn gõ `http://demo/bitrix/admin/` sẽ nhận được giao diện quản lý như bên dưới:  

<img src="https://i.imgur.com/JW2goTz.png">  

### Bước 5: Cài đặt samba 

Để có thể truy cập vào dữ liệu máy ảo từ bên ngoài ta tiến hành cài đặt `samba` trên VMBitrix  
Có thể tham khảo tại [link](https://www.tecmint.com/install-samba4-on-centos-7-for-file-sharing-on-windows/)  
- Chạy lệnh cài samba  
```
yum install samba samba-client samba-common
```
- Tạo smb user
```
smbpasswd -a bitrix
```
- Set quyền sở hữu cho user
```
chown bitrix:bitrix -R demo
```
- Bổ sung thêm nội dung sau vào file `/ect/samba/smb.conf`
```
[bitrix]
	comment = bitrix
	path = /home/bitrix
	browsable =yes
	writable = yes
	guest ok = yes
	read only = no
```
- Cho phép samba chạy trên firewall
```
# firewall-cmd --permanent --zone=public --add-service=samba
# firewall-cmd --reload
```
- Khởi động dịch vụ
```
# systemctl enable smb.service
# systemctl enable nmb.service
# systemctl restart smb.service
# systemctl restart nmb.service
```
=> Như vậy từ môi trường máy thật có thể connect vào thư mục `demo`  

- Tạo user cho database 
```
create user 'nga'@'%' identified by '123456';
grant all privileges on *.* to 'nga'@'%';
flush privileges;
```

- SSH đến server Bitrix  
```
ssh root@demo
```


