                                                                #**COMPILER VÀ MACRO**#

**I. COMPILER**

- Các ngôn ngữ lập trình hiện đại bao gồm cả C/C++ là những ngôn ngữ bậc cao (high-level programming language). Trong khi máy tính chỉ hiểu và xử lý thông tin dưới dạng các số nhị phân 0, 1 gọi là ngôn ngữ máy (machine code).

-> Quá trình biên dịch từ **ngôn ngữ ngữ bậc cao sang ngôn ngữ máy** để máy tính có thể hiểu và thực thi theo yêu cầu gọi cụ thể nào đó gọi là trình biên dịch (Compiler). Trong trình biên dịch GCC để biên dịch ngôn ngữ C và G++ để biên dịch ngôn ngữ C++ sẽ bao gồm các quá trình:

**1. Tiền xử lý (Pre-processor):** Quá trình này sẽ thay thế toàn bộ nội dụng file sau chỉ thị **include**, xóa tất cả các comment, thay thế các giá trị của **define**,...

-> Kết quả tạo ra file có dạng file.i

Câu lệnh:

                                                  `gcc -E filename.c -o fileName.i`

**2. Biên dịch (Compiler):** Chuyển nội dung trong file.i sang dạng hợp ngữ (Assembly) tạo ra file.s

Câu lệnh:

                                                  `gcc -S fileName.i -o fileName.s`

**3. Hợp dịch (Assembler):** Chuyển nội dung trong file.s sang mã máy (machine code) tạo ra file.o

Câu lệnh:

                                                  `gcc -c fileName.s -o fileName.o`


**4. Liên kết (Linker):** Trình liên kết sẽ liên kết tất cả các file.o được sử dụng và tạo ra file thực thi cuối cùng có dạng file.exe

Câu lệnh:

                                                  `gcc fileName.o -o fileName.exe`

