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

**IV. ỨNG DỤNG BIT WISE ĐỂ TẠO CÁC BIT MASK**

1. Dùng phép OR để set bit bất kì (không cần biết trước giá trị)

```c
void setBit(uint8_t *option, uint8_t bitNum){
  *option |= (1 << bitNum);
}
```

VD: Ta có 1 byte dữ liệu điều khiển LED, ứng với mỗi bit là số thứ tự LED ví dụ bit 0 là LED 0, bit 1 là LED 1,... . Ta muốn bật LED 5 ứng với bit 5 ta dùng Bitmask để set bit 5 lên 1 mà không quan tâm giá trị lúc đầu của nó. Trường hợp này ban đầu giá trị là 0b0000 0000 -> kết quả: 0b0010 0000

![image](https://github.com/user-attachments/assets/c771a8a8-0054-4d87-8725-3dc5d93544de)

2. Dùng phép AND và NOT để reset bit về giá trị 0

```c
void resetBit(uint8_t *option, uint8_t bitNum){
  *option &= ~(1 << bitNum);
}
```

VD: Ứng với ví dụ trên, ta tắt LED3 tức là ta reset bit số 3 về giá trị 0, trường hợp ban đầu ta có giá trị 0b0000 1000 -> kết quả: 0b0000 0000

![image](https://github.com/user-attachments/assets/fea4223b-e98a-4c46-a691-59614026db2c)  ![image](https://github.com/user-attachments/assets/b53e6cf7-757a-4998-bcff-6494fb7bcc9f)

3. Dùng phép AND để kiểm tra bit đó đang được bật hay chưa (khác 0)

```c
int isChecked(uint8_t option, uint8_t bitNum){
    return (option & (1 << bitNum)) != 0;
}
```
VD: Ứng với ví dụ trên, bit3 đang được set giá trị 1. Chúng ta kiểm tra thử xem bit3 đang có giá trị bao nhiêu

![image](https://github.com/user-attachments/assets/6de280f2-d78f-4e6e-9e81-589aec901ab4)  ![image](https://github.com/user-attachments/assets/c3cce398-e1ed-47c7-abbb-4ead0d9959df)


