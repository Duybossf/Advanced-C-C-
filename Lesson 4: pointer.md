**POINTE**R

**I. Khái niệm**

- Con trỏ (pointer) là một biến. Khác với biến thông thường con trỏ chứa đại chỉ của một đội tượng khác như (biến, hàm, mảng,...)

- Cú pháp khai báo: ```<data_type> *pointer_name;```

- Gán giá trị cho pointer:
VD:
```c
int x = 5;
int *ptrX = &x;
```
- Truy cập giá trị(giải tham chiếu - dereference)
VD:
```c
int y = *ptrX;   // y sẽ bằng giá trị của x
ptrX = &x;
*ptrX = *(0x01) = 5
```
- Kích thước con trỏ: Khác với các biến thông thường, kích thước con trỏ phụ thuộc vào kiến trúc hệ điều hành trình biên dịch hoặc kiến trúc microprocessor

VD:
```c
int normal = 1; // biến normal có kích thước kiểu integer là 4 byte

int *ptrN;
char *ptrC;
double *ptrD;
// Tuy được khai báo ở nhiều kiểu dữ liệu khác nhau nhưng các con trỏ trên đều có chung 1 kích thước theo kiến trúc hđh mình đang dùng là 64bit = 8byte
```
![image](https://github.com/user-attachments/assets/c8dfaae0-134b-445d-ac60-ab2f049a8a3a)  ![image](https://github.com/user-attachments/assets/c084424b-95c9-4cfa-8ec3-507a21facec9)




