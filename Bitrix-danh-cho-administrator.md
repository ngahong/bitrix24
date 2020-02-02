# Bitrix dành cho Administrator  

## 1. Tìm hiểu về cấu trúc hệ thống  
Hệ thống được chia làm 2 phần: `frontend` và `backend`.   
`Frontend` là phần public của site, hiển thị nội dung công khai cho người dùng. Còn phía backend sẽ được quản lý bởi **Administrator**.   

<img src="https://i.imgur.com/I5nRy7T.png">  

- **File system** bao gồm các thông tin tĩnh (text, images, videos...) và mã nguồn (program code, source code) được lưu trữ trong thư mục `/bitrix`.  

- **Information blocks**: khối dữ liệu chứa thông tin có cấu trúc tương tự 
- **Infoblocks**  -  1 module trong Bitrix chịu trách nhiệm khai báo và tạo dữ liệu
- **Module**: chịu trách nhiệm xử lý dữ liệu
- **Component**:
    - Kết nối module và information block  
    - Chịu trách nhiệm về việc hiển thị dữ liệu lên site

## 2. Cơ chế hoạt động  

### 2.1 Tạo và thêm dữ liệu  
- Tạo information block (IB1), thiết lập thuộc tính và thêm dữ liệu   
- Information block lưu dữ liệu vào Database.

### 2.2. Tạo page với thông tin động
- Tạo 1 page mới  
- Trên page, ta đặt component M từ  module N.  
- Config component để lấy thông tin từ  information block (IB1).

### 2.3.	Khi người dùng truy cập vào page

- information block (IB1) gửi data đến module N.  
- module thực hiện xử lý và tính toán dữ liệu, sau đó trả kết quả về component M  
- component M hiển thị kết quả lên website.  

## 3. Bitrix với administrator  
`Administrative section`: quản lý modules, component, cấu trúc website, nội dung và thông tin người dùng.  
Các phần trong `administrative section`   
-	Administrative control panel (top menu)
-	Administrative menu (menu ngoài cùng bên trái)
-	Functions menu (menu phía trong bên trái)
-	Primary workspace  (chính giữa)

<img src="https://i.imgur.com/JW2goTz.png">  

### 3.1 Desktop   
Click vào mục `Destop` và chọn `Add new desktop`.
Bạn có thể đặt tên cho desktop và thêm nội dung hiển thị bằng cách tùy chọn các mẫu sẵn có  

<img src="https://i.imgur.com/KPPOBPb.png">  

### 3.2 Content  
Ở mục `Content` hiển thị như bảng CSDL để bạn nắm được thông tin data của từng mục  

<img src="https://i.imgur.com/V6eVXji.png">

### 3.3 Marketing  
Mục `Marketing` quản lý các sản phẩm, email, quảng cáo marketing,...   

<img src="https://i.imgur.com/hHPz6bx.png">

### 3.4 e-Store  
Mục `e-store` có chức năng như một Cửa hàng điện tử, có thể đặt hàng, thanh toán, quản lý khách hàng, lập báo cáo... 

<img src="https://i.imgur.com/2zNpeGX.png">

### 3.5 Services 

Mục `Services` quản lý tất cả các dịch vụ như: Controller (site, group, task...), Web forms, Helpdesk, Blogs, Forums...  

<img src="https://i.imgur.com/21E7MEB.png">  

### 3.6 Setting  

Ngoài ra ở mục `Setting` bạn có thể thực hiện các thao tác quản lý user (thêm, sửa, xóa), Tìm kiếm, Cấu hình HTTPS, quản lý kho lưu trữ, cài đặt hệ thống ...

<img src="https://i.imgur.com/bpcLogK.png">