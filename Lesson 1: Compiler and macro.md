**COMPILER VÀ MACRO**

**I. COMPILER**

- Các ngôn ngữ lập trình hiện đại bao gồm cả C/C++ là những ngôn ngữ bậc cao (high-level programming language). Trong khi máy tính chỉ hiểu và xử lý thông tin dưới dạng các số nhị phân 0, 1 gọi là ngôn ngữ máy (machine code).

-> Quá trình biên dịch từ **ngôn ngữ ngữ bậc cao sang ngôn ngữ máy** để máy tính có thể hiểu và thực thi theo yêu cầu gọi cụ thể nào đó gọi là trình biên dịch (Compiler). Trong trình biên dịch GCC để biên dịch ngôn ngữ C và G++ để biên dịch ngôn ngữ C++ sẽ bao gồm các quá trình:

![image](https://github.com/user-attachments/assets/1d0649c6-c5e7-469f-abf3-422da5c75dde)


**1. Tiền xử lý (Pre-processor):** Quá trình này sẽ thay thế toàn bộ nội dụng file sau chỉ thị **include**, xóa tất cả các comment, thay thế các giá trị của **define**,...

-> Kết quả tạo ra file có dạng file.i

Câu lệnh:

`gcc -E fileName.c -o fileName.i`

**2. Biên dịch (Compiler):** Chuyển nội dung trong file.i sang dạng hợp ngữ (Assembly) tạo ra file.s

Câu lệnh:

`gcc -S fileName.i -o fileName.s`

**3. Hợp dịch (Assembler):** Chuyển nội dung trong file.s sang mã máy (machine code) tạo ra file.o

Câu lệnh:

`gcc -c fileName.s -o fileName.o`

**4. Liên kết (Linker):** Trình liên kết sẽ liên kết tất cả các file.o được sử dụng và tạo ra file thực thi cuối cùng có dạng file.exe

Câu lệnh:

`gcc fileName.o -o fileName.exe`

**II. MACRO**

- Là từ chỉ thông tin được xử lý ở quá trình tiền xử lý (Preprocessor), bao gồm 3 loại chính:

- **#include:** Chèn nội dung file vào mã nguồn, mục đích để tái sử dụng tài nguyên trong file đó và dễ quản lý mã nguồn

- **#define:** Là chỉ thị định nghĩa dùng để thay thế mã nguồn hoặc chuỗi mã nguồn bằng một mã nguồn hoặc chuỗi mã nguồn khác để tránh tình trạng lặp lại và dễ dàng bảo trì về sau.

Example 1:

![image](https://github.com/user-attachments/assets/62d34ca6-5b24-41f2-94d9-0304d0eacc87)

Example 2:

![image](https://github.com/user-attachments/assets/4620a861-c465-4b3a-9d4b-64083795f7a3) 

![image](https://github.com/user-attachments/assets/193885f5-7227-4b5d-9734-b476c137e707)

- **#undef:** Là chỉ thị định nghĩa dùng để hủy định nghĩa chỉ thị macro **#define**

Example 3:

![image](https://github.com/user-attachments/assets/b7d79c6a-c27a-4070-b211-e9f0fab7e561)

![image](https://github.com/user-attachments/assets/aa815e5e-f664-4b5b-8167-c5b9194a1b2b)


- **#if, #elif, #else, #endif:** Đây là các chỉ thị tiền xử lý được kiểm tra ở thời điểm trước khi biên dịch, có tác dụng đặt điều kiện đoạn code nào sẽ được biên dịch (ứng với điều kiện đúng)

Example 4: Chương trình chỉ biên dịch với trạng thái STATE khác với RUNNING và PENDING

![image](https://github.com/user-attachments/assets/e6ba54f7-3d33-41e3-b22e-0ed1c1d74c5f)

![image](https://github.com/user-attachments/assets/a22f2ec4-5788-404f-9c10-6504e684d738)

- **#ifdef, #ifndef:** Đây là cặp chỉ thị dùng để định nghĩa macro nếu nó chưa được định nghĩa. Thường dùng trong file header để tránh trùng lặp gây ra lỗi redefination

Example 5: 

**III. CÁC TOÁN TỬ TRONG MACRO**

1. Toán tử #: Dùng để chuẩn hóa giá trị thành chuỗi.
2. Toán tử ##: Dùng để nối 2 chuỗi lại thành 1 chuỗi liên tiếp

Example 6:

![image](https://github.com/user-attachments/assets/ca1890ba-1811-4246-a1b6-4e4fee678611)  ![image](https://github.com/user-attachments/assets/ed58e9ed-cba6-4d76-a0e5-57148cc5103b)





