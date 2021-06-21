# 1. HTTP STATUS CODE
**HTTP Status Code** là mã code server trả về sau mỗi lần gửi request. Tất cả các request mà server nhận được đều sẽ được trả về 1 response với 1 mã code tương ứng.

**HTTP Status Code** là một số nguyên 3 ký tự, ký tự đầu tiên dùng để phân loại
- 1..: request đã được server tiếp nhận và quá trình xử lý request đang được tiếp tục.
- 2..: request đã được server tiếp nhận, hiểu và xử lý thành công
- 3..: client cần có thêm action để hoàn thành request
- 4..: request chứa cú pháp không chính xác hoặc không được thực hiện
- 5..: request không thể thực hiện được

# 2. ANGULAR

## Pipe
là một cách thức đơn giản để có thể chuyển value sang một định dạng mong muốn. Pipe là một cách chuyển dữ liệu có sẵn trong angular, thông thường sẽ có một số pipe như sau:
- DatePipe
- UpperCasePipe
- LowerCasePipe
- CurrencyPipe
- DecimalPipe
- PercentPipe

Có thể tạo ra một pipe riêng biệt bằng cách dùng decorator @Pipe

Ngoài cách dùng từng pipe riêng biệt, còn một cách khác đó là dùng một chuỗi các pipe nối tiếp nhau, khi đó output của pipe này sẽ là input của pipe tiếp theo

## Reactive forms
**Reactive forms** đưa ra một phương thức tiếp cận theo kiểu **model-driven approach** để xử lý từ input form, tức là tránh sử dụng directive như *ngModel* hay *required* mà sẽ dùng Model trong Component, rồi tạo ra form

Đây là cấu trúc cơ bản của **Reactive Form**
![structure of reactive form](https://images.viblo.asia/cc518795-3e98-4122-9c09-97751cef8e11.png)

**Reactive forms** sử dụng một cách tiếp cận rõ ràng hơn **Template driven form** để quản lí state của form. Mỗi lần thay đổi của form sẽ trả lại một giá trị state mới, và giá trị này giữ cho model được ổn định sau mỗi lần thay đổi.

**Reactive forms** dựa trên observable streams. Khi đó, các input values từ form đều được coi như luồng dữ liệu đầu vào (stream of input value), và từ đó sẽ được truy cập một cách tuần tự.

**Reactive forms** thường được sử dụng khi dự án hoặc ứng dụng sử dụng forms là chính vì **Reactive forms** có khả năng tái sử dụng, dễ test và dể nâng cấp.

## snapshot vs subscribe
Cả hai cách lấy dữ liệu này đều nằm trong ActivatedRoute, nhưng mỗi cái lại phục vụ cho một mục đích khác nhau.

**Snapshot**, giống như cái tên của nó, chụp ảnh lại, thì dữ liệu khi lấy được bằng snapshot sẽ không thể update lại. Lấy ví dụ, bạn đi chụp ảnh lại một khung cảnh nào đấy, thì chỗ đó có được sửa sang lại hay bị phá huỷ đi thì trong bức ảnh của bạn, nó vẫn như vậy không hề bị thay đổi gì cả.
Còn **subscribe** thì khác, nó sẽ luôn cập nhật lại trạng thái của dữ liệu. Vẫn lấy ví dụ trên, thay vì chụp ảnh, bạn sẽ *theo dõi* địa điểm đấy thường xuyên hơn, hoặc nhờ người ở khu vực đó *theo dõi* tình hình rồi cập nhật cho bạn. Khi đó mọi tình trạng của khu vực đều được cập nhật.

Từ hai ví dụ trên, có thể nhận thấy rằng **snapshot** được sử dụng khi bạn không muốn update dữ liệu khi đang ở trong cùng một component. **Snapshot** sẽ lấy thông tin một lần duy nhất, khi component chạy và khi bạn có cố gắng sửa param trong **snapshot** thì cũng không thay đổi được.
Ví dụ cho **snapshot**: [snapshot](https://stackblitz.com/edit/angular-access-url-params-snapshot)

Còn **subscribe** thì khác, nó có thể lấy và cập nhật dữ liệu nhiều lần trong cùng component
Ví dụ cho **subscribe**: [subscribe](https://stackblitz.com/edit/angular-access-url-params-subscription)

# 3. Git/GitHub

## Merge vs Rebase
Merge và Rebase đều thực hiện một nhiệm vụ như nhau là ghép/tích hợp những thay đổi từ nhánh này vào nhánh khác.
### Merge
Merge sẽ cho phép ta ghép nối những branch độc lập vào một branch duy nhất.
**lệnh** 
git checkout [branch gốc] *git checkout main*
git merge [branch cần phải ghép] *git merge fix1*

khi đó, ở bracnh main sẽ tạo ra một commit mới chứa những thay đổi được thêm vào từ fix1, lưu lại toàn bộ lịch sử commit của branch main và fix1, nhưng branch fix1 sẽ không bị thay đổi gì

### Rebase
cũng làm công việc tương tự như **merge**
**lệnh**
git checkout [branch cần phải ghép] *git checkout fix2*
git rebase [branch gốc] *git rebase main*

nhưng thay vì nối vào, **rebase** sẽ *copy* lại một bản của fix2 ghép thẳng vào main, nằm phía trên main, và tạo ra các commit mới tương ứng với những commit ban đầu của fix2.

# 4. Javascript/TypeScript

## Double Exclamation Mark (!!)
làm cho biến đứng sau !! trở thành type boolean, tương đương với cách dùng Boolean()