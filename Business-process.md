# Business process trong Bitrix24  

1. Tìm hiểu chung  

**Business Process** (quy trình nghiệp vụ) là luồng thông tin (hoặc tài liệu) được định nghĩa trước bằng đường đi nhằm giải quyết một nhiệm vụ hoặc công việc nào đó. Mỗi giai đoạn sẽ có sự tham gia của con người để xử lý các yêu cầu trong quy trình.   

**Business process object** 
Quy trình nghiệp vụ thường chạy trên một đối tượng nào đó và thay đổi luồng thực hiện tùy thuộc vào trạng thái đối tượng.   
Một đối tượng được gọi là một tài liệu (document) có thể là một tệp (được lưu trong Thư viện Tài liệu), một phần tử khối thông tin (iblock) hoặc một mục CRM.  


Có 2 loại quy trình là: Quy trình tuần tự (**Sequential business process**) và Quy trình trạng thái (**State-driven business process**). 
- **Sequential business process**: để thực hiện một loạt các hành động liên tiếp trên một tài liệu, từ một điểm bắt đầu được xác định trước đến một điểm kết thúc được xác định trước.  

<img src="https://i.imgur.com/TmYwkUq.png">

- **State-driven business process** không có điểm bắt đầu và điểm kết thúc; thay vào đó, quy trình làm việc thay đổi trạng thái tiến trình. Các quy trình nghiệp vụ như vậy có thể kết thúc ở bất kỳ giai đoạn nào.
Một sơ đồ điển hình cho các quá trình như vậy bao gồm một số trạng thái, mỗi trạng thái bao gồm các hành động và điều kiện thay đổi trạng thái.

<img src="https://i.imgur.com/2VQeR4S.png">

**Trường hợp sử dụng**:  
- *Sequential business process*: dùng cho chuỗi hành động liên tiếp đơn giản
- *State-driven business process* : dùng cho quy trình có thể ở trạng thái khác nhau, có thể chuyển từ trạng thái này sang trạng thái khác. 

## Ví dụ tạo quy trình xin nghỉ phép.

### 1. Mô tả luồng công việc:  

<img src="https://i.imgur.com/zCMVKFT.png"> 

### 2. Thiết kế Business process trên Bitrix24  

- Vào mục **Workflow** => **Workflow in Activity Stream** => **Create new**  
- Đặt tên cho Business process và thiết lập quyền truy cập ở mục **Access** . Sau đó chọn **Save**
- Click vào Workflow vừa tạo và tiến hành cấu hình bằng cách chọn **Configure Workflows** ở mục **Action**.  

- Điền tiêu đề

<img src="https://i.imgur.com/6aD4NMn.png">

- Thiết lập các thuộc tính (Parameters)

<img src="https://i.imgur.com/YXkRHLJ.png">

- Tạo biến đầu vào (Variables)

<img src="https://i.imgur.com/zvau6fy.png">

- Thiết tập quyền truy cập ở mục Access. Ở đây ta chỉ cho quyền thực thi (Create) đối với những user có liên quan. Sau đó ấn Save để lưu.  
- Tiếp theo ta sẽ thiết kế Business process bằng công cụ hỗ trợ trong Bitrix.

<img src="https://i.imgur.com/x5jNAVk.png">  
<img src="https://i.imgur.com/bhyiUBv.png">

- Sau đó chọn Save để lưu. 

### Test kết quả:  

<img src="https://i.imgur.com/IhoF5TD.png"> 

- Nhan vien Duc Le tạo đơn nghỉ phép  

<img src="https://i.imgur.com/6VmaOzs.png"> 

- Trên Activity Stream sẽ hiển thị hoạt động xin nghỉ phép đồng thời hệ thống sẽ gửi yêu cầu đến cho quản lý trực tiếp  

<img src="https://i.imgur.com/8xNf1lm.png">  

- Quản lý trực tiếp sẽ Duyệt đồng ý hoặc từ chối.  

<img src="https://i.imgur.com/ubAlCzG.png">  

- Nếu Quản lý trực tiếp đồng ý thì tiếp tục yêu cầu được chuyển đến bộ phận Nhân sự  

<img src="https://i.imgur.com/gqPHvYn.png">  

- Sau khi bộ phận Nhân sự duyệt thì Thông báo sẽ được gửi đến người xin nghỉ phép  

<img src="https://i.imgur.com/HltoA8O.png">

- Trường hợp Xin nghỉ phép bị từ chối:  

<img src="https://i.imgur.com/FMGUvzd.png">  

Thông báo được gửi đến:  

<img src="https://i.imgur.com/SfTl2IR.png">  

Như vậy ta đã tạo thành công Quy trình Xin nghỉ phép trên Bitrix24.  

