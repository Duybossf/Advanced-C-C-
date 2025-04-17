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
**II. Ví dụ STDARG**

1. Biết trước số lượng tham số truyền vào

![image](https://github.com/user-attachments/assets/7075e333-2e5b-42af-be3b-1d9ebf227a3a)  ![image](https://github.com/user-attachments/assets/68fa9636-ec1d-47a3-a878-a4b772603c4a)

2. Không biết trước số lượng tham số truyền vào

3. Dùng Struct

**III. Thư viện ASSERT**

1. Định nghĩa:

- Thư viện này cung cấp macro ASSERT để kiểm tra điều kiện code.
    + Nếu điều kiện đúng -> không có gì và chương trình tiếp tục được compile
    + Nếu điều kiện sai -> Lập tức dừng chương trình và thông báo 1 message assert

- Cú pháp: ```assert(<condition> && <message>);```

- Dùng trong debug ```#define LOG(condition, message) assert(condition && #message)```

2. Ví dụ

![image](https://github.com/user-attachments/assets/fbe92caa-d25c-453f-af48-843777a1c30c)     ![image](https://github.com/user-attachments/assets/efcd0ca9-3d87-47d3-a668-c934f27abf45)

