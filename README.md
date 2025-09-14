# Giáo trình C++ cơ bản — Đơn giản dễ hiểu

**Cách biên dịch và chạy chương trình C++ (tóm tắt):**

* Viết mã vào file có đuôi `.cpp`, ví dụ `main.cpp`.
* Dùng trình biên dịch (compiler) như `g++`:

  * Biên dịch: `g++ -std=c++14 main.cpp -o main` (đối với Terminal)
  * Chạy: `./main` (trên Windows: `main.exe`) (đối với Terminal)
  * Chạy một dòng: `g++ -std=c++14 main.cpp -o main && ./main`
  * Lưu ý: khi tham gia các cuộc thi như học sinh giỏi của bộ giáo dục, thì khi chấm bài sẽ sử dụng phần mềm Themis để chấm và phiên bản chấm là C++ 14


---

## Mục lục

1. [Cấu trúc chương trình C++]
2. [Biến và kiểu dữ liệu]
3. [Toán tử]
4. [Câu lệnh điều kiện]
5. [Vòng lặp]
6. [Hàm (Function)]
7. [Mảng (Array)]

---

## 1. Cấu trúc chương trình C++

### Giải thích đơn giản

Một chương trình C++ cơ bản có các phần sau: khai báo thư viện (includes), hàm `main` là điểm bắt đầu, các lệnh nằm trong `main` hoặc các hàm khác.

### Ví dụ

```cpp
#include <bits/stdc++.h>
using namespace std;

int main() {
    cout << "Xin chao C++!" << endl; // in ra màn hình
    return 0; // kết thúc chương trình
}
```

### Lưu ý chuyên gia (đơn giản):

* `#include <bits/stdc++.h>` cho phép dùng `cout` để in ra màn hình.
* `return 0;` nghĩa là chương trình kết thúc thành công.

### Bài tập

1. Viết chương trình in ra tên của bạn.
2. Viết chương trình in ra 2 dòng: dòng 1 "Hello", dòng 2 "World".
3. Viết chương trình nhập tên từ bàn phím rồi in ra "Xin chao, \<tên>!".

---

## 2. Biến và kiểu dữ liệu

### Giải thích đơn giản

Biến là "hộp" để chứa dữ liệu. Mỗi biến có một kiểu dữ liệu (số nguyên, số thực, ký tự, chuỗi, boolean...). Bạn phải khai báo kiểu trước khi dùng.

### Một số kiểu cơ bản

* `int` — số nguyên (ví dụ 1, -5)
* `double` — số thực (ví dụ 3.14)
* `char` — một ký tự (ví dụ 'A')
* `bool` — giá trị đúng/sai (`true`/`false`)
* `string` — chuỗi ký tự (cần `#include <string>`)

### Ví dụ

```cpp
#include <bits/stdc++.h>
#include <string>

using namespace std;

int main() {
    int tuoi = 16;
    double diem = 8.5;
    char kyTu = 'A';
    bool laHocSinh = true;
    string ten = "Lan";

    cout << ten << " - tuoi: " << tuoi << endl;
    return 0;
}
```

### Ghi chú

* Có thể khởi tạo biến khi khai báo: `int x = 5;`.
* Nếu không khởi tạo, biến chứa giá trị rác — nên luôn gán giá trị ban đầu.

### Bài tập

1. Khai báo biến để lưu tên, tuổi, và điểm trung bình. In ra dạng: "\<tên>, \<tuổi> tuổi, điểm TB = <diem>".
2. Viết chương trình nhập 2 số nguyên a và b, in tổng, hiệu, tích và thương (dạng thực) của chúng.
3. Tại sao không nên dùng `int` để lưu tiền có lẻ cent? (trả lời ngắn)

---

## 3. Toán tử

### Giải thích đơn giản

Toán tử dùng để thực hiện phép toán: cộng, trừ, nhân, chia, phép gán, và toán tử so sánh.

### Một số toán tử phổ biến

* Số học: `+`, `-`, `*`, `/`, `%` (chia lấy dư)
* So sánh: `==`, `!=`, `<`, `>`, `<=`, `>=`
* Logic: `&&` (và), `||` (hoặc), `!` (phủ định)
* Gán và tăng/giảm: `=`, `+=`, `-=`, `++`, `--`

### Ví dụ

```cpp
int a = 7;
int b = 3;
int tong = a + b; // 10
int du = a % b; // 1
bool kq = (a > b); // true
```

### Lưu ý

* Phép chia `int / int` trả về `int` (lấy phần nguyên). Nếu muốn kết quả thực, dùng `double` hoặc ép kiểu `(double)a / b`.

### Bài tập

1. Viết chương trình nhập 2 số nguyên, in phần nguyên và phần dư của phép chia.
2. Viết chương trình kiểm tra một số nguyên n có chia hết cho 3 và 5 hay không.
3. Viết chương trình nhận ba số a, b, c và in ra số lớn nhất (sử dụng toán tử so sánh và `if`).

---

## 4. Câu lệnh điều kiện

### Giải thích đơn giản

Dùng `if`, `else if`, `else` để quyết định chương trình làm gì dựa trên điều kiện. Có thể dùng `switch` cho nhiều trường hợp rẽ nhánh dựa trên giá trị nguyên hoặc ký tự.

### Ví dụ `if`

```cpp
int n;
cin >> n;
if (n > 0) {
    cout << "Duong" << endl;
} else if (n < 0) {
    cout << "Am" << endl;
} else {
    cout << "Bang 0" << endl;
}
```

### Ví dụ `switch`

```cpp
char ch;
cin >> ch;
switch (ch) {
    case 'a': cout << "La chu a"; break;
    case 'b': cout << "La chu b"; break;
    default: cout << "Khac"; break;
}
```

### Bài tập

1. Viết chương trình nhập điểm (0-100) và in học lực: A (>=85), B (70-84), C (50-69), F (<50).
2. Viết chương trình nhập một tháng (1-12) và in tên mùa (ví dụ 1,2,3 -> "Mua Dong" v.v.).
3. Viết chương trình kiểm tra năm nhuận (năm nhuận nếu chia hết cho 4 nhưng không phải 100, hoặc chia hết cho 400).

---

## 5. Vòng lặp

### Giải thích đơn giản

Vòng lặp giúp lặp lại một đoạn mã nhiều lần: `for`, `while`, `do-while`.

### Ví dụ `for`

```cpp
for (int i = 1; i <= 5; ++i) {
    cout << i << endl;
}
```

### Ví dụ `while` và `do-while`

```cpp
int i = 1;
while (i <= 5) {
    cout << i << endl;
    ++i;
}

int j = 1;
do {
    cout << j << endl;
    ++j;
} while (j <= 5);
```

### Một số lưu ý

* Dùng `break;` để thoát vòng lặp sớm.
* Dùng `continue;` để bỏ qua lần lặp hiện tại và chuyển sang lần tiếp theo.

### Bài tập

1. In tất cả số chẵn từ 2 đến 100.
2. Nhập một số n, tính tổng 1 + 2 + ... + n.
3. Viết chương trình nhập nhiều số (kết thúc khi nhập số 0) rồi in tổng và số lượng số đã nhập (không kể số 0).

---

## 6. Hàm (Function)

### Giải thích đơn giản

Hàm là một khối mã có tên thực hiện một nhiệm vụ cụ thể. Hàm giúp tách chương trình thành phần nhỏ, dễ quản lý và tái sử dụng.

### Cấu trúc hàm

```cpp
KiTuTraVe tenHam(DS_tham_so) {
    // thân hàm
}
```

### Ví dụ

```cpp
#include <bits/stdc++.h>

int tong(int a, int b) { // trong trường hợp này nếu muốn biến có thể được chỉnh sửa và trả về cho hàm main thì ghi là (int &a, int &b)
    return a + b;
}

int main() {
    int x = 3, y = 4;
    cout << "Tong: " << tong(x, y) << endl;
    return 0;
}
```

### Ghi chú

* Một hàm có thể không trả về (`void`) hoặc trả về một giá trị.
* Thông thường khai báo hàm ở trên `main` hoặc dùng prototype trước `main`.

### Bài tập

1. Viết hàm `int max(int a, int b)` trả về số lớn hơn.
2. Viết hàm `bool laSoNguyenTo(int n)` kiểm tra nguyên tố.
3. Viết hàm `int fib(int n)` trả về số Fibonacci thứ n (dùng đệ quy và không đệ quy - so sánh hiệu năng).

---

## 7. Mảng (Array)

### Giải thích đơn giản

Mảng là tập hợp nhiều biến cùng kiểu được lưu liên tiếp trong bộ nhớ. Mỗi phần tử có chỉ số (index) bắt đầu từ 0.

### Khai báo mảng

```cpp
int a[5]; // mảng 5 phần tử
int b[] = {1, 2, 3, 4};
```

### Truy cập phần tử

```cpp
a[0] = 10;
cout << a[0];
```

### Ví dụ: tính tổng mảng

```cpp
#include <bits/stdc++.h>

int main() {
    int a[] = {2, 4, 6, 8};
    int sum = 0;
    for (int i = 0; i < 4; ++i) sum += a[i];
    cout << "Tong = " << sum << endl;
}
```

### Bài tập

1. Viết chương trình nhập n (n > 0), sau đó nhập n số nguyên vào mảng và in ra phần tử lớn nhất và nhỏ nhất.
2. Viết chương trình đảo ngược mảng (ví dụ \[1,2,3] -> \[3,2,1]).
3. Viết chương trình đếm số lượng phần tử chẵn trong mảng.

---

## Phần mở rộng (tham khảo)

* Sau khi nắm vững trên, bạn có thể học: `vector`, `string` nâng cao, con trỏ, cấu trúc (struct), lớp (class) — nhưng trước hết hãy chắc các khái niệm cơ bản.

---

## Đáp án tham khảo (ngắn gọn)


* Chương 1: dùng `cout` hoặc `cin` để in/nhập.
* Chương 2 bài 2: nhập a,b; `double t = a + b; double h = a - b; double p = a*b; double q = (double)a/b;`
* Chương 4 bài 3: kiểm tra năm nhuận bằng công thức đã nêu (chia hết 4 và không chia hết 100) hoặc chia hết 400.
* Chương 6 bài 2: hàm kiểm tra chia thử từ 2..sqrt(n).
* Chương 7 bài 2: hoán đổi `a[i]` và `a[n-1-i]` trong vòng lặp đến giữa mảng.

---
