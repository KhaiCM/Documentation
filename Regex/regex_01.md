# Tìm hiểu về Regex

Biểu thức chính quy hữu ích trong việc trích xuất thông tin từ văn bản, log file, sheets. document.

Về cơ bản mọi thứ chúng ta viết đều là kí tự và chúng ta đang viết các mẫu để khớp với một chuỗi kí tự cụ thể. Hầu hết sử dụng mẫu ASCII, bao gồm chữ cái, chữ số, dấu chấm câu và các kí hiệu khác trên bàn phím của bạn như % # $ ! @ &, vv. Nhưng các kí tự unicode cũng có thể được sử dụng để khớp với bắt kì loại văn bản quốc tế nào.

## Cú pháp cơ bản của Regex

| Kí tự | ý nghĩa | Ví dụ | Example |
|------| -----|-----------| --------|
| **^** | Bắt đầu chuỗi nhập | ^B | B. Nhưng chỉ match nếu B là kí tự đầu tiên trong chuỗi |
| **$** | Kết thúc chuỗi nhập | B$ | B. Nhưng chỉ match nếu B là kí tự cuối cùng trong chuỗi |
| **.** | Chấp nhận bất kì kí tự nào ngoại trừ kí tự xuống dòng (**\n**) | t.thu | tathu |
| **`*`** | Kí tự trước có thể lặp lại 0 hoặc nhiều lần  | ta*thu | tathu, taathu, tthu |
| **`+`** | Kí tự trước có thể lặp lại 1 hoặc nhiều lần  | ta*thu | tathu, taathu |
| **`?`** | Kí tự trước có thể lặp lại 0 hoặc 1 lần  | ta*thu | tathu, tthu |
| **`\s`** | Bất kì kí tự khoảng trắng | \sa | [space]a, \ta, \na |
| **`\S`** | Bất kì kí tự nào không phải khoảng trắng | \Sa | aa, ba, ca |
| **`\b`** | Chấp nhận kí tự từ biên | a\b | aa, ba, va |
| **`\B`** | Chấp nhận kí tự không phải từ biên | a\B | ab, bb, vv |


Đây là cú pháp viết Regex cơ bản, nhưng tùy vào mỗi ngôn ngữ mà cách sử dụng có thể khác nhau.


| Biểu thức | ý nghĩa | ghi chú |
|------| -----|-----------|
| **`a|b`** | Khớp với a hoặc b |
| **`[0-9]`** | Khớp với một số từ 0 đến 9 |
| **`[a-z]`** | Khớp với một chữ từ a đến z |
| **`[abc]`** | Có thể khớp với a hoặc b hoặc c |
| **`[^abc]`** | Có thể khớp với bất kì kí tự nào ngoài a, b, c | Nếu **`^`** xuất hiện đầu tiên sau ngoặc vuông mang nghĩa phủ định |
| **`\d`** | Khớp với số bất kì | Thay thế cho [0-9] |
| **`\D`** | Khớp với kí tự không phải là số | Thay thế cho [^0-9] |
| **`\s`** | Kí tự khoảng trắng|
| **`\S`** | Không phải kí tự khoảng trắng | Thay thế cho [^\s] |
| **`\D`** | Không phải kí tự khoảng trắng |

## Cú pháp regex với kí tự thường


## abc

Ex:

| Task | Text |
|------| -----|
| Match | abcde |
| Match | abcdefg |
| Match | abc |

Solution: typing: `abc`


## 123

Cá kí tự thì bào gồm các chữ cái, và cả các chữ số. Trên thực tế các số 0-9 cũng là các kí tự trong bảng ASCII.

Kí tự `\d` được dùng để thay thế cho bất cứ chữ số nào từ **0-9**. Dấu gạch chéo trước phân biệt nó với kí tự **d**.

Ngược lại thì kí tự `\D` sẽ khớp với kì kí tự nào không phải chữ số.
Ex:

| Task | Text |
|------| -----|
| Match | abc123xyz |
| Match | define "123" |
| Match | var g = 123; |

Solution: typing: `123`


## . (Dấu chấm)

Có một khái niệm về kí tự đại diện được đại diện bởi **`.`**. đây là siêu kí tự có thể khớp với bất kì kí tự đơn nào (Chữ cái, chữ sô, khaongr trắng, mọi thứ). Bạn có thể nhận thấy rằng điều này
