**THƯ VIỆN STDARG**

**I. Khái niệm**

* Thư viện STDARG ```<stdarg.h>``` trong C cung cấp cho chúng ta các maro dùng để sử dụng trong việc định nghĩa các hàm có số lượng tham số không xác định. Cú pháp dùng chung:

```c
#include <stdarg.h>

return_type function_name(fixed_arg, ...) {
    va_list args; //tạo ra biến với kiểu dữ liệu để đại diện cho danh sách các tham số

    va_start(args, fixed_arg); // Khởi tạo để lấy danh sánh tham số và báo cho chương trình biết bắt đầu từ đâu.
    // Biến fixed_arg đại diện cho số lượng tham số truyển vào
    // Khi đọc giá trị tham số chương trình sẽ bắt đầu đọc giá trị tham số ngay sau biến fixed_arg

    va_arg(args, type); // Lấy một tham số trong danh sách các tham số không xác định chuyển về data type chỉ định

    va_end(args); // Kết thúc việc sử dụng danh sách tham số không xác định

}
```
**II. Ví dụ hàm tính tổng các tham số truyển vào chưa xác định**

![image](https://github.com/user-attachments/assets/7075e333-2e5b-42af-be3b-1d9ebf227a3a)  ![image](https://github.com/user-attachments/assets/68fa9636-ec1d-47a3-a878-a4b772603c4a)

