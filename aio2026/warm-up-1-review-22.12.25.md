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

### 0. Các tài liệu <mark style="color:red;">must-read</mark>:

{% embed url="https://forms.gle/eqqkodjuUQePUXAp8" fullWidth="false" %}
Link quiz&#x20;
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

* <mark style="background-color:blue;">**Biến (Variable) là gì? Cách gọi biến ra sao?**</mark>
* Lưu ý không để tên biến trùng với keyword Python <mark style="color:red;">(các hàm)</mark>, không để tên quá dài, phức tạp và <mark style="color:red;">BẮT ĐẦU</mark> bằng số 1,2,3,...

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

<pre class="language-python" data-title="function" data-overflow="wrap" data-full-width="true"><code class="lang-python">a = 5
print(a) # Gán biến và in giá trị của biến.

b = 10.2
print(type(b)) # Gán biến và in <a data-footnote-ref href="#user-content-fn-1">kiểu giá trị</a> của biến.

name = input("Tên bạn là gì? ")
print("Xin chào,", name) # Gán biến, cho biến nhận giá trị từ bên ngoài và in ra giá trị đó.
 
&#x3C;class 'int'> # Kiểu giá int (interger - số nguyên).
&#x3C;class 'float'> # Kiểu giá trị số thực (floating point - dấu phẩy động).
&#x3C;class 'str'> # Kiểu giá trị chuỗi kí tự (string).
&#x3C;class 'bool'> # Kiểu giá trị Boolean - thể hiện tính đúng/sai.

</code></pre>

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

#### a. Giới thiệu:

{% hint style="info" %}
Toán tử (operator) là các ký&#x20;hiệu đặc biệt để thực hiện các phép tính số\
học hoặc logic trên các giá trị hoặc biến.
{% endhint %}

* Loại toán tử <mark style="color:red;">cơ bản nhất</mark> mà chúng ta sẽ gặp là các phép tính cộng, trừ, nhân, chia. Chúng được gọi là <mark style="background-color:blue;">**Toán tử số học - Arithmetic Operators.**</mark>

| Arithmetic Operators |                  Meaning - ý nghĩa                 | Equivalent Assignment Operators |
| :------------------: | :--------------------------------------------------: | :-----------------------------: |
|           +          |                   Addition - Cộng                   |                +=               |
|           -          |                  Substraction - Trừ                 |                -=               |
|          \*          |                 Multiplication - Nhân                |               \*=               |
|           /          |      Division (float) - Chia đủ có thập phân      |                /=               |
|          //          | Division (Int) - Chia **chỉ lấy** giá trị nguyên |               //=               |
|           %          |         Modulo - Chia **chỉ lấy** phần dư         |                %=               |
|         \*\*         |                  Power - Luỹ thừa                  |              \*\*=              |

|    Operator type - Loại toán tử   |           Các ví dụ          |
| :----------------------------------: | :-----------------------------: |
|       **Arithmetic Operators**       |      **+,-,\*,/,//,%,\*\***     |
|  **Relational Operators( so sánh)** |       **<,<=,>,>=,==,!=**       |
|     **Logical Operators(lô gic)**    |          **AND,OR,NOT**         |
|     Bitwise Operators(nhị phân)     |         &,\|,^,\~,>>,<<         |
| **Assignment Operators(gán biến)** | **=,+=,-=,\*=,/=,//=,%=,\*\*=** |

* Relational Operators dùng để <mark style="background-color:blue;">so sánh giá trị của các biến</mark>, trả kết quả <mark style="color:red;">True hoặc False.</mark>

{% hint style="danger" %}
Chú ý về dấu = dùng để gán giá trị cho biến và dấu == để so sánh bằng.
{% endhint %}

{% code title="lỗi dùng sai dấu" %}
```python
a = int(input("Enter the first number: "))
b = int(input("Enter the second number: "))
print("Two number is the same", a = b)
Enter the first number: 10
Enter the second number: 20
---------------------------------------------------------------------------
TypeError                                 Traceback (most recent call last)
/tmp/ipython-input-3804419606.py in <cell line: 0>()
      1 a = int(input("Enter the first number: "))
      2 b = int(input("Enter the second number: "))
----> 3 print("Two number is the same", a = b)

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

#### b. Thứ tự các loại toán tử:

<table><thead><tr><th width="114" align="center">Priority- ưu tiên</th><th align="center">Toán tử</th><th align="center">Ví dụ</th></tr></thead><tbody><tr><td align="center">1</td><td align="center">Power</td><td align="center">**</td></tr><tr><td align="center">2</td><td align="center">Multiplication,<br>Division, Modulo</td><td align="center">*, /, //, %</td></tr><tr><td align="center">3</td><td align="center">Addition, Subtraction</td><td align="center">+, -</td></tr><tr><td align="center">4</td><td align="center">Comparison</td><td align="center"><p></p><p>>, >=, &#x3C;, &#x3C;=</p></td></tr><tr><td align="center">5</td><td align="center">Equality comparison</td><td align="center">==, !=</td></tr><tr><td align="center">6</td><td align="center">Assignment operators</td><td align="center">=, +=, -=, *=, /=, //=, %=, **=</td></tr></tbody></table>

{% code title="ví dụ về thứ tự ưu tiên" %}
```python
 print(4 + 5 * 3 ** 2 > 5 % 2 + 1)
# 4 + 5 * 9 > 5 % 2 + 1
# 4 + 45 > 1 + 1
# 49 > 2 -> True
```
{% endcode %}

### **3. Immutable và Mutable trong Python**

#### a. Immutable Object:&#x20;

* **Immutable objects trong Python là những đối tượng&#x20;**<mark style="color:red;">**không thể thay đổi giá trị**</mark>  \
  **sau khi khởi tạo.**
* Các ví dụ của Immutable Object là <mark style="background-color:blue;">kiểu giá trị int, float, bool, string.</mark>
* Ắt hẳn  &#x20;chúng ta sẽ thắc mắc rằng, trong quá trình lập trình, rõ ràng chúng ta vẫn có thể ‘thay đổi’ giá  &#x20;trị của các biến dữ liệu trên, nhưng tại sao chúng lại là Immutable? Thật ra, về bản chất, thứ  \
  chúng ta làm là <mark style="color:red;">tạo ra một object mới với giá trị mới</mark>, chứ không thực sự thay đổi giá trị.

{% hint style="info" %}
Sử dụng hàm id() trong Python sẽ làm rõ khái niệm tạo object mới khi chúng trả về 2 địa chỉ bộ nhớ khác nhau dù 2 biến có cùng 1 giá trị thuộc kiểu giá trị Immutable.
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

#### b. Mutable Object:

* **Mutable objects trong Python là những đối tượng&#x20;**<mark style="color:red;">**có thể thay đổi giá trị**</mark>**&#x20;sau khi đã được khởi**  \
  **tạo.**
* Ví dụ của Mutable bao gồm <mark style="background-color:blue;">set, list, dict.</mark>
* Chúng cho phép ta <mark style="color:red;">thay đổi phần tử bên trong.</mark>

{% hint style="warning" %}
Phân biệt **list\[]** và **tuple().** Chúng đều là danh sách phần tử nhưng **list** là **Mutable** còn **tuple** là **Immutable**.
{% endhint %}

{% hint style="info" %}
Khi sử dụng hàm **id** với **list,** kể cả khi ta dùng lệnh **append** để sửa đổi phần tử thì giá trị **id** vẫn giữ nguyên. Python thực sự thay đổi giá trị, phần tử trực tiếp chứ không trỏ địa chỉ bộ nhớ mới như **Immutable Object**.
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
Các số thực trong Python chỉ được lưu tối đa **8 byte**, tương đương với **64 bit** bộ nhớ. Vì vậy khi tính toán số thực, Python có thể sẽ gặp trường hợp sai số nhỏ hoặc bị hiện tượng tràn số.&#x20;
{% endhint %}

#### a. Overflow:&#x20;

* Là hiện tượng tràn số do <mark style="background-color:blue;">kết quả/giá trị số quá lớn</mark>, vượt ngoài bộ nhớ khả dụng của Python.
* Khi hiện tượng tràn số xảy ra, Python sẽ trả kết quả <mark style="color:red;">**inf (infinity)**</mark> để thể hiện rằng số đó quá lớn, không thể hiển thị thông thường do vượt giới hạn biểu diễn số.
* Python coi **inf** là kiểu giá trị số thực **(float)**, do đó ta có thể dùng các kiểu toán tử với **inf** nhưng kết quả trả về sẽ khác biệt với bình thường.

{% code title="ví dụ" %}
```python
a = 1e400
print(a)
----
inf # Vượt giới hạn biểu diễn

a = 1e400 # 10 mũ 400
print(a) # inf
print(type(a)) # <class "float">
```
{% endcode %}

{% hint style="info" %}
Do inf là một số ‘vô cùng lớn’, nên nếu lấy&#x20;inf trừ đi bất kì số nào thì giá trị trả về inf.&#x20;Tương tự, nếu ta tiếp tục cộng inf với bất&#x20;kì số nào (kể cả inf) cũng sẽ nhận được giá&#x20;trị inf.
{% endhint %}

* Ngoài **inf**, Python cũng sẽ trả về kết quả <mark style="color:red;">**nan**</mark> <mark style="color:red;">**(Not a Number)**</mark> với dữ liệu thiếu, vô nghĩa. Ta sẽ bắt gặp nhiều trong dữ liệu thô, ví dụ như thể hiện trạng thái thiếu dữ liệu trong báo cáo.
* Một số phép tính lỗi, vô nghĩa (ví dụ như chia cho 0) hay các trường hợp vô định trong toán học (vô cực - vô cực = ?) thì ta cũng sẽ nhận được giá trị **nan**.
* Tuy nhiên, không phải tất cả dạng vô định nào trong toán học cũng sẽ hiển thị **nan.**

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

#### b. Underflow:

* Ngược lại với **Overflow**, **Underflow** là hiện tượng tràn số khi <mark style="background-color:blue;">số quá thấp</mark>, vượt ngoài giá trị biểu diễn của Python.

{% code title="ví dụ" %}
```python
a = 1e-400
print(a)
----
0.0 #Python sẽ hiện thị 0.0 để thể hiện Underflow
```
{% endcode %}

### 5. Sai số trong số thực

* Như đã đề cập, Python sẽ có sai số với các số thực do cơ chế dấu phẩy động **(Floating point**) nên chỉ <mark style="background-color:blue;">lưu giá trị gần đúng</mark>. Đây là chuyện bình thương với không riêng gì Python mà đa số các ngôn ngữ lập trình phổ biến bây giờ.
* Từ đây, có 1 "**nghịch lý**" thú vị trong Python rằng:

```python
 print(0.1 + 0.2 == 0.3)
# False - false thật không đùa 
```

{% hint style="info" %}
Mặc dù biểu thức 0.1 + 0.2 về mặt toán học&#x20;đúng bằng 0.3, Python (và hầu hết các ngôn&#x20;ngữ lập trình) không thể biểu diễn chính&#x20;xác các số như 0.1 trong hệ nhị phân. Do&#x20;đó, mỗi giá trị được lưu dưới dạng một số&#x20;xấp xỉ, dẫn đến tổng của chúng cũng bị sai&#x20;số. Khi so sánh trực tiếp hai số dấu phẩy&#x20;động, sự khác biệt rất nhỏ này khiến biểu&#x20;thức trả về False.
{% endhint %}

<pre class="language-python"><code class="lang-python">print(0.1 + 0.2)
<strong>----
</strong>0.30000000000000004
</code></pre>

* Khi thực hiện nhiều phép tính với số thực, các số ngày càng được làm tròn, khiến cho kết quả  \
  sau cùng có nhiều sai lệch

### 6. Bài tập (Xem trong slide phần bài tập)

[^1]: 
