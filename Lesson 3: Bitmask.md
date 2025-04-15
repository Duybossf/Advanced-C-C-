**BITMASK**

**I. Định nghĩa Bitmask**

- Ví dụ để quản lý các thuộc tính, quyền truy cập của đối tượng nào đó mà vẫn tối ưu hóa bộ nhớ thay vì dùng các biến có kiểu dữ liệu tốn nhiều bộ nhớ như int, double, ta chỉ cần sử dụng kiểu dữ liệu tốn ít bộ nhớ như uint8_t, hay uint_16 và **thao tác trên từng bit** của nó.

- Ta có thể kiểm tra trạng thái, đặt hoặc xóa 1 bit cụ thể. Như vậy Bitmask là kỹ thuật sử dụng các bit để thao tác và lưu trữ.

**II. BITWISE**

* NOT: kết quả cho ra là các bit đảo ngược so với ban đầu. Toán tử trong C: **~**

VD:
```c
int a = ~b; Khi b = 0b0110, kết quả là a = 0b1001
```

* OR: kết quả cho ra là các bit có giá trị theo Truth Table như sau, **với y = a OR b**. Toán tử trong C: **|**

![image](https://github.com/user-attachments/assets/067c4e07-e4cf-47d7-9111-bdeca7fde49f)


VD:
```c
int a = x | y; Với x = 0b0011 và y = 0b0101. Kết quả a = 0b0111
```

* AND: kết quả cho ra là các bit có giá trị theo Truth Table như sau, **với y = a AND b**. Toán tử trong C: **&**

![image](https://github.com/user-attachments/assets/4c0e3bfd-fee0-45ed-b13c-af7eafd24d0b)

VD:
```c
int a = x & y; Với x = 0b0011 và y = 0b0101. Kết quả a = 0b0001
```

* XOR: kết quả cho ra là các bit có giá trị theo Truth Table như sau, **với y = a XOR b**. Toán tử trong C: **^**

![image](https://github.com/user-attachments/assets/fd0bcfc6-9700-4327-a9cd-4a18f075d172)

VD:
```c
int a = x ^ y; Với x = 0b0011 và y = 0b0101. Kết quả a = 0b0111
```

**III. PHÉP DỊCH BIT (toán tử << hoặc >>)**

1. Phép dịch trái n bit: Là phép dịch toàn bộ các bit sang trái n bit, các bit tận cùng bên phải sẽ thêm n các bit có giá trị 0

VD: 
```c
int a = 0b1100 0001;
int b = a << 2; Khi đó b = 0b0000 0100
```

2. Phép dịch phải n bit: Là phép dịch toàn bộ các bit sang phải n bit, các bit tận cùng bên trái sẽ thêm n các bit có giá trị 0

VD: 
```c
int a = 0b1100 0001;
int b = a >> 2; Khi đó b = 0b0011 0000
```

