---
description: Advanced Variables, Numeric Types & Expression Optimization
icon: code
layout:
  width: wide
  title:
    visible: true
  description:
    visible: true
  tableOfContents:
    visible: true
  outline:
    visible: true
  pagination:
    visible: true
  metadata:
    visible: false
---

# WARM UP 1 - Review 22.12.25

{% hint style="success" %}
Học ngày 22/12/2025. Hãy xem record + reading + slide.
{% endhint %}

### 0. Các tài liệu <mark style="color:red;">must-read</mark>

{% embed url="https://forms.gle/eqqkodjuUQePUXAp8" fullWidth="false" %}
Link quiz
{% endembed %}

{% file src="../.gitbook/assets/Documents-2025-11-WARMUP 01 - REVIEW 01-[Reading]-WarmUp-01-Advanced-Variables-Operators.pdf" %}
File tài liệu
{% endfile %}

{% file src="../.gitbook/assets/Documents-2025-11-WARMUP 01 - REVIEW 01-[Slide]-WarmUp-01-Advanced-Variables-Operators.pdf" %}
Slide bài giảng
{% endfile %}

{% file src="../.gitbook/assets/Documents-2025-11-WARMUP 01 - REVIEW 01 - Advanced Variables, Numeric Types & Expression Optimization-[Quiz]-Advanced-Variables-Operators.pdf" %}
Quiz ôn tập cuối buổi
{% endfile %}

### **1. Python cơ bản - ôn tập**

* <mark style="background-color:blue;">**Biến (variable) là gì? Cách đặt tên biến ra sao?**</mark>
* Lưu ý: không đặt tên biến trùng keyword/hàm có sẵn Python, không đặt quá dài, và không <mark style="color:red;">BẮT ĐẦU</mark> bằng số (1, 2, 3, ...).

{% code title="variable_name" overflow="wrap" fullWidth="true" %}
```python
1a = 15 # Nên tránh đặt như thế này.

giá_trị_của_hàm_tại_x3 = 15 # Cũng không nên đặt quá dài như vậy.

value = 15 # Đây là cách đặt tên khuyến khích và hợp lệ.
```
{% endcode %}

* Lưu ý rằng việc đặt tên biến sai có thể gây ra <mark style="color:red;">LỖI SyntaxError.</mark> Cố gắng đặt tên biến <mark style="background-color:blue;">ngắn gọn, dễ hiểu và có ý nghĩa khi có thể.</mark>

{% code title="Ví dụ cho việc đặt sai tên biến" fullWidth="true" %}
```python
1a = "Hello world"
File "c:\Users\Admin\OneDrive\Tài liệu\Untitled-1.py", line 1
    1a = "Hello world"
    ^
SyntaxError: invalid decimal literal
```
{% endcode %}

* Các hàm có sẵn cơ bản trong Python: <mark style="background-color:blue;">print, type, input</mark>

{% code title="function" overflow="wrap" fullWidth="true" %}
```python
a = 5
print(a) # Gán biến và in giá trị của biến.

b = 10.2
print(type(b)) # Gán biến và in kiểu giá trị của biến.

name = input("Tên bạn là gì? ")
print("Xin chào,", name) # Gán biến, cho biến nhận giá trị từ bên ngoài và in ra giá trị đó.
 
# <class 'int'>   # int (integer - số nguyên)
# <class 'float'> # float (floating point - số thực)
# <class 'str'>   # str (string - chuỗi)
# <class 'bool'>  # bool (Boolean - đúng/sai)

```
{% endcode %}

* Ta có thể thay đổi kiểu giá trị bằng cách ép giá trị đó về kiểu <mark style="background-color:blue;">int, float, str hoặc bool</mark>

{% code title="Ví dụ về đổi kiểu" %}
```python
a = 5 
b = float(a)
print(b) # Đổi về số thực.

a = -1
c = bool(a)
print(c) # Đổi về Boolean. Lưu ý với các số khác 0 thì luôn trả giá trị True

```
{% endcode %}

### **2. Các loại toán tử trong Python (cơ bản-nâng cao)**

#### a. Giới thiệu

{% hint style="info" %}
Toán tử (operator) là ký hiệu đặc biệt, dùng để thực hiện phép tính số học hoặc logic trên các giá trị/biến.
{% endhint %}

* Loại toán tử <mark style="color:red;">cơ bản nhất</mark> mà chúng ta sẽ gặp là các phép tính cộng, trừ, nhân, chia. Chúng được gọi là <mark style="background-color:blue;">**Toán tử số học - Arithmetic Operators.**</mark>

| Arithmetic Operators |                  Meaning - ý nghĩa                 | Equivalent Assignment Operators |
| :------------------: | :--------------------------------------------------: | :-----------------------------: |
|           +          |                   Addition - Cộng                   |                +=               |
|           -          |                  Subtraction - Trừ                  |                -=               |
|          \*          |                 Multiplication - Nhân                |               \*=               |
|           /          |      Division (float) - Chia đủ có thập phân      |                /=               |
|          //          | Division (int) - Chia **chỉ lấy** giá trị nguyên |               //=               |
|           %          |         Modulo - Chia **chỉ lấy** phần dư         |                %=               |
|         \*\*         |                  Power - Luỹ thừa                  |              \*\*=              |

|    Operator type - Loại toán tử    |           Các ví dụ          |
| :-----------------------------------: | :-----------------------------: |
|        **Arithmetic Operators**       |      **+,-,\*,/,//,%,\*\***     |
|  **Relational Operators (so sánh)**  |       **<,<=,>,>=,==,!=**       |
|     **Logical Operators (logic)**     |         **and, or, not**        |
|     Bitwise Operators (nhị phân)     |         &,\|,^,\~,>>,<<         |
| **Assignment Operators (gán biến)** | **=,+=,-=,\*=,/=,//=,%=,\*\*=** |

* Relational Operators dùng để <mark style="background-color:blue;">so sánh giá trị của các biến</mark>, trả kết quả <mark style="color:red;">True hoặc False.</mark>

{% hint style="danger" %}
Chú ý: dấu `=` dùng để gán giá trị cho biến. Dấu `==` dùng để so sánh bằng.
{% endhint %}

{% code title="lỗi dùng sai dấu" %}
```
a = int(input("Enter the first number: "))
b = int(input("Enter the second number: "))
print("Two numbers are the same", a = b)
Enter the first number: 10
Enter the second number: 20
---------------------------------------------------------------------------
TypeError                                 Traceback (most recent call last)
/tmp/ipython-input-3804419606.py in <cell line: 0>()
      1 a = int(input("Enter the first number: "))
      2 b = int(input("Enter the second number: "))
-----> 3 print("Two numbers are the same", a = b)

TypeError: 'a' is an invalid keyword argument for print()
```
{% endcode %}

* Logical Operators dùng để <mark style="background-color:blue;">thực hiện các phép tính logic trong toán học</mark>, trả kết quả <mark style="color:red;">True hoặc False.</mark>
* Assignment Operators <mark style="background-color:blue;">dùng để gắn giá trị cho biến</mark>. Arithmetic và Assignment Operators có thể <mark style="color:red;">kết hợp</mark> với nhau để tinh gọn code hơn (cột 3 bảng 1 phần 2).

{% code title="operators" %}
```python
a = 10
b = 20
a += b
print(a)
a -= b
print(a)
a *= b
print(a)
a /= b
print(a) # Ví dụ của Arithmetic kết hợp với Assignment Operators

a = 10
b = 5
print(a > b)
print(a >= b)
print(a < b)
print(a <= b)
print(a == b)
print(a != b) # Ví dụ của Relational Operators

T = True
F = False
print(T and F)
print(T or F)
print(not T) # Ví dụ của Logical Operators

A = True
B = True
print(A ^ B) # Ví dụ về XOR trong Logical Operators
```
{% endcode %}

#### b. Thứ tự các loại toán tử

<table><thead><tr><th width="114" align="center">Priority- ưu tiên</th><th align="center">Toán tử</th><th align="center">Ví dụ</th></tr></thead><tbody><tr><td align="center">1</td><td align="center">Power</td><td align="center">**</td></tr><tr><td align="center">2</td><td align="center">Multiplication,<br>Division, Modulo</td><td align="center">*, /, //, %</td></tr><tr><td align="center">3</td><td align="center">Addition, Subtraction</td><td align="center">+, -</td></tr><tr><td align="center">4</td><td align="center">Comparison</td><td align="center">>, >=, &#x3C;, &#x3C;=</td></tr><tr><td align="center">5</td><td align="center">Equality comparison</td><td align="center">==, !=</td></tr><tr><td align="center">6</td><td align="center">Assignment operators</td><td align="center">=, +=, -=, *=, /=, //=, %=, **=</td></tr></tbody></table>

{% code title="ví dụ về thứ tự ưu tiên" %}
```python
print(4 + 5 * 3 ** 2 > 5 % 2 + 1)
# 4 + 5 * 9 > 5 % 2 + 1
# 4 + 45 > 1 + 1
# 49 > 2 -> True
```
{% endcode %}

### **3. Immutable và Mutable trong Python**

#### a. Immutable objects

* **Immutable objects** là đối tượng <mark style="color:red;">không thể bị sửa trực tiếp</mark> sau khi tạo.
* Ví dụ: <mark style="background-color:blue;">int, float, bool, str</mark>.
* Khi bạn viết `a = 5` rồi `a = 6`, bạn không “sửa” số 5.
* Bạn <mark style="color:red;">tạo object mới</mark> (số 6), rồi trỏ tên `a` sang object đó.

{% hint style="info" %}
`id()` cho thấy định danh (identity) của object. Với immutable, khi gán giá trị mới, `id()` thường sẽ đổi vì ta đang trỏ sang object khác.
{% endhint %}

{% code title="hàm id" %}
```python
a = 5
print(id(a))
a = 6
print(id(a))
----
11654504
11654536
```
{% endcode %}

#### b. Mutable objects

* **Mutable objects** là đối tượng <mark style="color:red;">có thể sửa nội dung</mark> sau khi tạo.
* Ví dụ: <mark style="background-color:blue;">list, dict, set</mark>.
* Bạn có thể thêm/xóa/sửa phần tử bên trong mà không cần tạo object mới.

{% hint style="info" %}
Với `list`, khi bạn `append()` thì Python sửa nội dung của chính object đó. Vì thế `id(list)` thường không đổi.
{% endhint %}

{% hint style="warning" %}
Phân biệt `list[]` và `tuple()`. Chúng đều là danh sách phần tử. `list` là **mutable**. `tuple` là **immutable**.
{% endhint %}

{% code title="ví dụ về append trong list" %}
```python
a = [1, 2, 3]
a.append(4)
print(a)
----
[1, 2, 3, 4]
```
{% endcode %}

### **4. Overflow và Underflow**

{% hint style="warning" %}
`float` trong Python thường là IEEE-754 double: **64-bit (8 byte)**. Nó có giới hạn về độ chính xác (khoảng 15-16 chữ số) và khoảng giá trị. Vì thế có thể bị sai số, overflow, hoặc underflow.
{% endhint %}

#### a. Overflow

* Overflow xảy ra khi <mark style="background-color:blue;">giá trị quá lớn</mark> và `float` không còn biểu diễn được.
* Khi đó Python trả về <mark style="color:red;">`inf`</mark> (infinity).
* `inf` vẫn là `float`. Bạn vẫn tính toán được, nhưng kết quả có thể “kỳ”.

{% code title="ví dụ" %}
```python
a = 1e400
print(a)
----
inf # Vượt giới hạn biểu diễn

a = 1e400 # 10 mũ 400
print(a) # inf
print(type(a)) # <class 'float'>
```
{% endcode %}

{% hint style="info" %}
`inf` cư xử “siêu to”: `inf + x = inf` và `inf - x = inf` (với mọi `x` hữu hạn). Nhưng `inf - inf` sẽ thành `nan`.
{% endhint %}

* Ngoài `inf`, Python cũng sẽ trả về kết quả <mark style="color:red;">`nan`</mark> <mark style="color:red;">(Not a Number)</mark> với dữ liệu thiếu, vô nghĩa. Bạn sẽ gặp nhiều trong dữ liệu thô, ví dụ như ô trống trong báo cáo.
* Một số phép tính lỗi/vô nghĩa (vd chia cho 0) hoặc trường hợp vô định (vd `inf - inf`) cũng có thể ra `nan`.
* Tuy nhiên, không phải lúc nào “vô định” cũng hiển thị `nan`.

{% code title="ví dụ" %}
```python
print(float("inf") - float("inf"))
# nan
print(float("inf") * 0)
# nan
print(float("nan") + float("inf"))
# nan

print(float('inf')*0)
print(float('inf') / float('inf'))
print(float('inf') - float('inf'))
print(pow(float('inf'), 0))
print(pow(1, float('inf')))
----
nan
nan
nan
1
1 # Trường hợp không hiển thị giá trị nan 
```
{% endcode %}

#### b. Underflow

* Underflow xảy ra khi số <mark style="background-color:blue;">quá nhỏ (rất gần 0)</mark>. `float` không còn giữ được độ chính xác. Kết quả có thể bị làm tròn về `0.0`.

{% code title="ví dụ" %}
```python
a = 1e-400
print(a)
----
0.0 # Python sẽ hiện thị 0.0 để thể hiện Underflow
```
{% endcode %}

### 5. Sai số trong số thực

* `float` lưu số theo dạng nhị phân, nên nhiều giá trị thập phân (vd `0.1`) không thể lưu chính xác.
* Vì thế, kết quả thường chỉ <mark style="background-color:blue;">xấp xỉ</mark>.
* “Nghịch lý” kinh điển:

```python
print(0.1 + 0.2 == 0.3)
# False - thật sự đấy!
```

{% hint style="info" %}
0.1 không thể biểu diễn chính xác trong hệ nhị phân. Mỗi giá trị được lưu xấp xỉ, nên khi cộng và so sánh trực tiếp sẽ có sai số nhỏ. Sai số này khiến biểu thức trả về `False`.
{% endhint %}

{% code title="ví dụ output" %}
```python
print(0.1 + 0.2)
----
0.30000000000000004
```
{% endcode %}

* Khi thực hiện nhiều phép tính với số thực, sai số do làm tròn có thể tích lũy.

{% hint style="warning" %}
Đừng so sánh `float` bằng `==` nếu bạn cần “gần bằng”. Hãy dùng `math.isclose()` hoặc so sánh theo sai số `abs(a - b) < eps`.
{% endhint %}

### 6. Bài tập (Xem trong slide phần bài tập)
