---
description: Variabel dan Tipe Data
---

# Bab 2

## **Definisi Variabel**&#x20;

**Variabel** adalah tempat penyimpanan data dalam program yang dapat diubah nilainya selama eksekusi. Variabel memiliki dua komponen utama:

1. **Nama Variabel**: Identifikasi lokasi penyimpanan data (misalnya, `x`, `jumlah`, `nilai_akhir`).
2. **Tipe Data**: Menentukan jenis data yang disimpan (misalnya, `int`, `float`, `char`).

## **Deklarasi dan Inisialisasi Variabel:**

*   **Deklarasi**: Menentukan tipe dan nama variabel.

    ```cpp
    int x;  // deklarasi variabel x
    ```
*   **Inisialisasi**: Memberikan nilai pada variabel saat deklarasi.

    ```cpp
    int x = 10;  // deklarasi dan inisialisasi
    ```

#### **Contoh Penggunaan:**

```cpp
#include <iostream>
using namespace std;

int main() {
    int a = 5;       // variabel integer a
    float b = 3.14;  // variabel float b
    cout << a << " " << b;  // Menampilkan nilai a dan b
    return 0;
}
```

**Output:**

```
5 3.14
```

#### **Latihan Soal**&#x20;

**Soal:**

1. Apa itu variabel dalam C++? Jelaskan dengan singkat.
2. Sebutkan beberapa tipe data yang ada dalam C++ dan jelaskan fungsinya.
3. Tuliskan contoh program C++ yang mendeklarasikan variabel dengan tipe **int**, **float**, dan **char**.

## **Penamaan Variabel (Identifier)**

**Identifier** adalah nama yang digunakan untuk variabel, fungsi, atau elemen lainnya dalam program. Berikut aturan dan konvensinya:

#### **Aturan Penamaan:**

1. **Dimulai dengan Huruf atau Underscore**:
   * Contoh valid: `total`, `_value`, `x1`.
   * Tidak valid: `1x`, `3total`.
2. **Karakter yang Diperbolehkan**:
   * Menggunakan huruf, angka (setelah huruf pertama), dan underscore.
   * Tidak valid: `total-angka` (tanda minus).
3. **Tidak Boleh Kata Kunci**:
   * Tidak boleh menggunakan kata kunci seperti `int`, `float`, `if`, dll.
4. **Case-Sensitive**:
   * `total` dan `Total` dianggap berbeda.

#### **Konvensi Penamaan:**

1. **Camel Case**: `totalAmount`, `userName`.
2. **Snake Case**: `total_amount`, `user_name`.
3. **Nama Deskriptif**: Gunakan nama yang jelas, misalnya `studentAge` daripada `x`.

#### **Contoh:**

```cpp
int totalAmount = 100;
double total_price = 50.5;
```

#### **Kesimpulan:**

* Nama variabel harus mengikuti aturan tertentu dan tidak boleh menggunakan kata kunci.
* Pilih nama yang jelas dan sesuai konvensi agar kode mudah dibaca.

#### **Latihan Soal**&#x20;

**Soal:**

1. Apa yang dimaksud dengan identifier dalam C++? Sebutkan aturan-aturan penamaan variabel.
2. Mana yang merupakan penamaan variabel yang benar:
   * `int 1total;`
   * `int totalAmount;`
   * `int total-amount;`
3. Jelaskan perbedaan antara **camelCase** dan **snake\_case** dalam penamaan variabel.

## **Jenis Tipe Data dalam C++**

Tipe data menentukan jenis nilai yang dapat disimpan dalam variabel. Berikut penjelasan untuk tipe data yang sering digunakan dalam C++:

***

#### 1. **int** (Integer)

* **Deskripsi**: Tipe data untuk menyimpan **bilangan bulat** (tanpa angka desimal).
* **Ukuran**: Biasanya 4 byte (tergantung platform).
* **Rentang Nilai**: -2,147,483,648 sampai 2,147,483,647 (untuk `int` 32-bit).

**Contoh:**

```cpp
int age = 25;  // Menyimpan nilai bilangan bulat
```

***

#### 2. **float** (Floating Point)

* **Deskripsi**: Tipe data untuk menyimpan **bilangan desimal** (presisi lebih rendah).
* **Ukuran**: 4 byte.
* **Rentang Nilai**: Sekitar 1.5 × 10⁻⁴⁶ sampai 3.4 × 10³⁸ (dengan 6-7 angka desimal presisi).

**Contoh:**

```cpp
float price = 19.99f;  // Menyimpan nilai desimal dengan presisi lebih rendah
```

***

#### 3. **double** (Double Precision Floating Point)

* **Deskripsi**: Tipe data untuk menyimpan **bilangan desimal** (presisi lebih tinggi dibanding `float`).
* **Ukuran**: 8 byte.
* **Rentang Nilai**: Sekitar 5.0 × 10⁻³²⁴ sampai 1.7 × 10³⁰⁴ (dengan 15-16 angka desimal presisi).

**Contoh:**

```cpp
double pi = 3.141592653589793;  // Menyimpan nilai desimal dengan presisi lebih tinggi
```

***

#### 4. **char** (Character)

* **Deskripsi**: Tipe data untuk menyimpan **karakter tunggal** (seperti huruf, angka, atau simbol).
* **Ukuran**: 1 byte.
* **Rentang Nilai**: Biasanya karakter dari ASCII (0 sampai 255).

**Contoh:**

```cpp
char grade = 'A';  // Menyimpan karakter
```

***

#### 5. **bool** (Boolean)

* **Deskripsi**: Tipe data untuk menyimpan **nilai logika**: benar (`true`) atau salah (`false`).
* **Ukuran**: 1 byte (meskipun hanya membutuhkan 1 bit).
* **Rentang Nilai**: `true` atau `false`.

**Contoh:**

```cpp
bool isStudent = true;  // Menyimpan nilai logika true
```

#### **Contoh Program C++ Menggunakan Berbagai Tipe Data:**

```cpp
#include <iostream>
using namespace std;

int main() {
    int age = 30;           // tipe int
    float weight = 65.5f;   // tipe float
    double pi = 3.14159;    // tipe double
    char grade = 'A';       // tipe char
    bool isPassed = true;   // tipe bool

    cout << "Age: " << age << endl;
    cout << "Weight: " << weight << endl;
    cout << "Pi: " << pi << endl;
    cout << "Grade: " << grade << endl;
    cout << "Passed: " << isPassed << endl;

    return 0;
}
```

**Output:**

```
EditAge: 30
Weight: 65.5
Pi: 3.14159
Grade: A
Passed: 1
```

#### **Latihan Soal**&#x20;

**Soal:**

1. Apa perbedaan antara **int**, **float**, **double**, **char**, dan **bool**? Jelaskan secara singkat.
2. Tuliskan program C++ yang mendeklarasikan dan menginisialisasi variabel dengan tipe data **int**, **float**, **char**, dan **bool**, kemudian menampilkan nilainya di layar.

## **Konstanta (`const`) dalam C++**

**Konstanta** adalah nilai yang **tidak dapat diubah** selama program berjalan. Setelah sebuah nilai diberikan kepada konstanta, nilai tersebut **tidak bisa diubah**. Konstanta digunakan untuk menjaga nilai tetap stabil dan untuk mencegah perubahan yang tidak diinginkan dalam program.

***

#### **Deklarasi Konstanta dengan `const`**

Untuk mendeklarasikan konstanta, kita menggunakan kata kunci **`const`** sebelum tipe data variabel. Berikut adalah cara mendeklarasikan dan menginisialisasi konstanta:

```cpp
cppSalinEditconst tipe_data nama_konstanta = nilai;
```

Contoh:

```cpp
cppSalinEditconst int MAX_SCORE = 100;  // Mendeklarasikan konstanta MAX_SCORE dengan nilai 100
```

***

#### **Ciri-ciri Konstanta:**

1. **Tidak Bisa Diubah**: Setelah konstanta diinisialisasi dengan nilai, nilai tersebut tidak bisa diubah sepanjang program berjalan.
2. **Dapat Meningkatkan Keamanan Program**: Menggunakan konstanta dapat mencegah kesalahan yang disebabkan oleh perubahan nilai yang tidak disengaja.

***

#### **Contoh Penggunaan Konstanta:**

```cpp
cppSalinEdit#include <iostream>
using namespace std;

int main() {
    const double PI = 3.14159;  // Konstanta PI untuk nilai pi
    const int MAX_AGE = 100;    // Konstanta MAX_AGE untuk batasan usia

    cout << "Nilai PI: " << PI << endl;
    cout << "Usia maksimal: " << MAX_AGE << endl;

    // PI = 3.14;  // ERROR! Tidak bisa mengubah nilai konstanta PI
    return 0;
}
```

**Output:**

```
yamlSalinEditNilai PI: 3.14159
Usia maksimal: 100
```

Pada contoh di atas, kita mendeklarasikan dua konstanta, `PI` dan `MAX_AGE`. Jika kita mencoba mengubah nilai `PI` setelah deklarasi, program akan menghasilkan error.

***

#### **Keuntungan Menggunakan Konstanta:**

1. **Keamanan Kode**: Menghindari perubahan nilai yang tidak disengaja.
2. **Meningkatkan Keterbacaan**: Nama konstanta yang deskriptif membuat kode lebih mudah dipahami.
3. **Mempermudah Pemeliharaan**: Jika nilai konstanta harus berubah, kita hanya perlu mengubahnya di satu tempat, bukan di seluruh program.

***

#### **Konstanta dalam C++:**

* **Konstanta Literals**: Nilai tetap yang ditulis langsung dalam kode, seperti `100`, `'A'`, atau `3.14`.
* **Konstanta Global**: Konstanta yang dideklarasikan di luar fungsi `main()` dan dapat digunakan di seluruh program.
* **Konstanta dalam Fungsi**: Konstanta juga dapat dideklarasikan di dalam fungsi, dan hanya berlaku dalam fungsi tersebut.

#### **Latihan Soal**&#x20;

**Soal:**

1. Deklarasikan konstanta dengan nama `MAX_TEMP` yang menyimpan nilai **100**.
2. Deklarasikan konstanta dengan nama `PI` yang menyimpan nilai **3.14159**.
3. Tuliskan program C++ yang menampilkan nilai `MAX_TEMP` dan `PI` ke layar.

**Pertanyaan:**

* Apa yang terjadi jika kita mencoba mengubah nilai konstanta setelah dideklarasikan?

## **Operator Dasar dalam C++**

Operator adalah simbol yang digunakan untuk melakukan operasi pada variabel atau nilai. Dalam C++, ada beberapa jenis operator dasar, di antaranya adalah **operator aritmatika**, **operator perbandingan**, dan **operator logika**.

***

#### 1. \*_Operator Aritmatika (+, -, , /, %)_

Operator aritmatika digunakan untuk melakukan operasi matematis dasar seperti penjumlahan, pengurangan, perkalian, pembagian, dan modulus.

*   **`+` (Penjumlahan)**: Menjumlahkan dua nilai.

    ```cpp
    cppSalinEditint a = 5, b = 3;
    int result = a + b;  // result = 8
    ```
*   **`-` (Pengurangan)**: Mengurangi satu nilai dari nilai lainnya.

    ```cpp
    cppSalinEditint result = a - b;  // result = 2
    ```
*   **`*` (Perkalian)**: Mengalikan dua nilai.

    ```cpp
    cppSalinEditint result = a * b;  // result = 15
    ```
*   **`/` (Pembagian)**: Membagi satu nilai dengan nilai lainnya. Hasilnya adalah tipe data yang sesuai (integer atau float).

    ```cpp
    cppSalinEditint result = a / b;  // result = 1 (karena pembagian integer)
    float result = 5.0 / 3.0;  // result = 1.6667 (pembagian float)
    ```
*   **`%` (Modulus)**: Menghitung sisa pembagian antara dua angka (hanya untuk integer).

    ```cpp
    cppSalinEditint result = a % b;  // result = 2 (sisa pembagian 5 / 3)
    ```

***

#### 2. **Operator Perbandingan (==, !=, >, <, >=, <=)**

Operator perbandingan digunakan untuk membandingkan dua nilai dan menghasilkan nilai boolean (`true` atau `false`).

*   **`==` (Sama dengan)**: Memeriksa apakah dua nilai sama.

    ```cpp
    cppSalinEditint a = 5, b = 5;
    bool result = (a == b);  // result = true
    ```
*   **`!=` (Tidak sama dengan)**: Memeriksa apakah dua nilai tidak sama.

    ```cpp
    cppSalinEditint a = 5, b = 3;
    bool result = (a != b);  // result = true
    ```
*   **`>` (Lebih besar dari)**: Memeriksa apakah nilai pertama lebih besar dari nilai kedua.

    ```cpp
    cppSalinEditbool result = (a > b);  // result = true
    ```
*   **`<` (Lebih kecil dari)**: Memeriksa apakah nilai pertama lebih kecil dari nilai kedua.

    ```cpp
    cppSalinEditbool result = (a < b);  // result = false
    ```
*   **`>=` (Lebih besar atau sama dengan)**: Memeriksa apakah nilai pertama lebih besar atau sama dengan nilai kedua.

    ```cpp
    cppSalinEditbool result = (a >= b);  // result = true
    ```
*   **`<=` (Lebih kecil atau sama dengan)**: Memeriksa apakah nilai pertama lebih kecil atau sama dengan nilai kedua.

    ```cpp
    cppSalinEditbool result = (a <= b);  // result = false
    ```

***

#### 3. **Operator Logika (&&, ||, !)**

Operator logika digunakan untuk memanipulasi nilai boolean, biasanya digunakan dalam pernyataan kondisi seperti `if` atau `while`.

*   **`&&` (AND logika)**: Mengembalikan `true` hanya jika kedua operand bernilai `true`.

    ```cpp
    cppSalinEditbool result = (true && false);  // result = false
    ```
*   **`||` (OR logika)**: Mengembalikan `true` jika salah satu operand bernilai `true`.

    ```cpp
    cppSalinEditbool result = (true || false);  // result = true
    ```
*   **`!` (NOT logika)**: Mengembalikan kebalikan dari nilai boolean (membalikkan `true` menjadi `false`, dan sebaliknya).

    ```cpp
    cppSalinEditbool result = !true;  // result = false
    ```

***

#### **Contoh Program Menggunakan Operator**

```cpp
cppSalinEdit#include <iostream>
using namespace std;

int main() {
    int a = 10, b = 3;
    
    // Operator Aritmatika
    cout << "Penjumlahan: " << a + b << endl;  // 13
    cout << "Pengurangan: " << a - b << endl;  // 7
    cout << "Perkalian: " << a * b << endl;    // 30
    cout << "Pembagian: " << a / b << endl;    // 3
    cout << "Modulus: " << a % b << endl;      // 1

    // Operator Perbandingan
    cout << "a == b: " << (a == b) << endl;  // 0 (false)
    cout << "a != b: " << (a != b) << endl;  // 1 (true)
    cout << "a > b: " << (a > b) << endl;    // 1 (true)
    cout << "a < b: " << (a < b) << endl;    // 0 (false)

    // Operator Logika
    bool x = true, y = false;
    cout << "(x && y): " << (x && y) << endl;  // 0 (false)
    cout << "(x || y): " << (x || y) << endl;  // 1 (true)
    cout << "!(x): " << !x << endl;            // 0 (false)

    return 0;
}
```

**Output:**

```
yamlSalinEditPenjumlahan: 13
Pengurangan: 7
Perkalian: 30
Pembagian: 3
Modulus: 1
a == b: 0
a != b: 1
a > b: 1
a < b: 0
(x && y): 0
(x || y): 1
!(x): 0
```
