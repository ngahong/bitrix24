# Tìm hiểu về List trong Bitrix24  

**List** có thể hiểu như một dạng của *information block* được hiển thị lên site và người dùng có thể thao tác được.  
List giúp cho người dùng quản lý dễ dàng hồ sơ (record based data)  
Chức năng của List:  
- xây dựng các trường dữ liệu cho bất kỳ loại đối tượng nào, bao gồm các tệp;  
- cài đặt truy cập cho từng List;   
- tích hợp quy trình nghiệp vụ.

**Information blocks**: khối dữ liệu chứa thông tin có cấu trúc tương tự 
Infoblocks  -  1 module trong Bitrix chịu trách nhiệm khai báo và tạo dữ liệu.   
**Module**: chịu trách nhiệm xử lý dữ liệu.  

Ví dụ về List: 
- Giả sử bạn cần tạo một quy trình Phân loại Nhân viên thì bạn cần tạo 1 khối thông tin (Infomation block). Khối này sẽ có các trường (fields) như tên Họ tên, Tuổi, Địa chỉ,...Mỗi Field sẽ tương ứng với một Section. 

<img src="https://i.imgur.com/xb02kSO.png">  

- Thiết lập thuộc tính cho field  

<img src="https://i.imgur.com/p9CTBwN.png">

**Sort**: giá trị sort càng nhỏ thì mức độ ưu tiên hiển thị càng lớn.  
**Required**: xác định rằng trường này phải tồn tại khi thêm một mục List;    
**Multiple**: chỉ định nhiều giá trị cho field khi thêm hoặc chỉnh sửa một mục List;   
**Type**: xác định kiểu;  
**Defaul-value**: Giá trị mặc định   


- Tiếp theo ta cần phải nhập dữ liệu cho các trường. Mỗi Element được tạo bằng cách nhập giá trị vào các trường và click Save.  

<img src="https://i.imgur.com/80KYDXz.png">  

- Sau khi tạo các Elenment, ta sẽ nhận được một List có tên là *Nhân viên*  dưới dạng bảng sau:  

<img src="https://i.imgur.com/0aK74Si.png">  

## 1. Create new list

Chọn **New List**  

Thiết lập các thông tin cần thiết  

- **Setting**: điền tên và mô tả của List, bật chế độ quy trình nghiệp vụ.  

<img src="https://i.imgur.com/XoKUFBe.png">  

- **Titles**: được sử dụng để đặt tên cho các đối tượng của infomation block để khi ta nhìn vào sẽ dễ hiểu hơn.  
Ví dụ:  
<img src="https://i.imgur.com/8dT2fG2.png">  

- **Access**: thiết lập quyền truy cập List, có thể thêm user hoặc group user với quyền đọc/sửa/ghi...

<img src="https://i.imgur.com/vSjT9Al.png">

Trong mục **Action** của mỗi List sẽ có các tùy chọn sau:  
- **Configure list setting**: Dùng để cấu hình chung cho List như điền tên, mô tả, thiết lập quyền truy cập. Trong đó có thêm các action nhỏ như Xóa, Copy, Di chuyển sang Workflow hoặc Config list field.  

<img src="https://i.imgur.com/srU0Oae.png">  

- **Customize field**: Tùy chọn để thêm field và thiết lập các thuộc tính của field  
- **Config Workflow**: Thiết lập quy trình làm việc. 
- **Show/Hide section**: Hiển thị hoặc ẩn section  
- **Export to Microsoft Excel**: Xuất List thành bảng tính dưới dạng file excel.  
- **SharePoint**: Chia sẻ bằng cách tạo liên kết.  

## 2. Tạo quy trình công việc  

- Để cấu hình quy trình công việc, chọn *Action* => *Config workflows* 

<img src="https://i.imgur.com/NdLvi4C.png">  

- Có 2 mẫu quy trình để người dùng thao tác: 

    - **State-driven business process**: quy trình trạng thái  
    - **Sequential business process**: quy trình tuần tự

<img src="https://i.imgur.com/tJZUeG1.png">  



 
