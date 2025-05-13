---
description: Input dan Output
---

# Bab 3

## **Input dan Output dalam C++**

Dalam C++, untuk berinteraksi dengan pengguna, kita menggunakan mekanisme **input** dan **output**. **Input** digunakan untuk menerima data dari pengguna, sedangkan **Output** digunakan untuk menampilkan data ke layar.

latihan soal : Buatlah sebuah program C++ yang meminta pengguna untuk memasukkan **nama** dan **umur**

#### 1. **Fungsi `cin` dan `cout`**

**`cin`** dan **`cout`** adalah dua objek utama yang digunakan untuk **input** dan **output** di C++.

* **`cin`** (character input) digunakan untuk menerima input dari pengguna.
* **`cout`** (character output) digunakan untuk menampilkan output ke layar.

**Sintaks dasar:**

```cpp
#cin >> variabel;    // Input
cout << variabel;   // Output
```

***

**Contoh Penggunaan `cin` dan `cout`:**

```cpp
#include <iostream>
using namespace std;

int main() {
    int age;
    cout << "Masukkan umur Anda: ";  // Menampilkan pesan
    cin >> age;  // Menerima input dari pengguna dan menyimpannya ke variabel 'age'
    
    cout << "Umur Anda adalah: " << age << " tahun." << endl;  // Menampilkan hasil output
    
    return 0;
}
```

**Penjelasan:**

* Program meminta pengguna untuk memasukkan nilai untuk `age` menggunakan `cin`.
* Setelah itu, program menampilkan nilai `age` ke layar menggunakan `cout`.

**Output:**

```
Masukkan umur Anda: 25
Umur Anda adalah: 25 tahun.
```

Latihan Soal : Buat program C++ yang menerima dua angka **integer** dari pengguna dan menampilkan hasil perhitungan **penjumlahan** dan **perkalian** kedua angka tersebut.

#### 2. **Format Input/Output**

Di C++, kita dapat menggunakan berbagai cara untuk **memformat output** agar lebih rapi dan mudah dibaca. Beberapa fitur format input/output yang umum digunakan antara lain:

* **Manipulasi format angka** menggunakan `setw()`, `setprecision()`, dan lainnya.
* **Menambahkan baris baru** dengan `endl` atau .
* **Memformat angka desimal** menggunakan `fixed` dan `setprecision()`.

**Contoh Format Output:**

1. **`setw()` (Set Width)**: Mengatur lebar kolom dalam output.
2. **`setprecision()`**: Mengatur jumlah angka desimal yang ditampilkan.
3. **`fixed` dan `scientific`**: Mengatur format tampilan angka desimal.

```cpp
#include <iostream>
#include <iomanip>  // Untuk manipulasi input/output
using namespace std;

int main() {
    double pi = 3.14159265358979;

    // Menampilkan angka dengan presisi 2 desimal
    cout << "Pi dengan 2 desimal: " << fixed << setprecision(2) << pi << endl;

    // Menampilkan angka dalam format ilmiah
    cout << "Pi dalam format ilmiah: " << scientific << setprecision(4) << pi << endl;

    // Menampilkan angka dengan lebar kolom 10 dan rata kanan
    cout << "Pi dengan lebar 10: |" << setw(10) << pi << "|" << endl;

    // Menampilkan beberapa nilai dalam format tabel
    cout << setw(10) << "Nama" << setw(10) << "Umur" << endl;
    cout << setw(10) << "Ali" << setw(10) << 25 << endl;
    cout << setw(10) << "Budi" << setw(10) << 30 << endl;

    return 0;
}
```

**Penjelasan:**

* `setprecision(2)` mengatur agar hanya 2 angka setelah titik desimal yang ditampilkan.
* `setw(10)` memberikan lebar kolom 10 karakter pada output.
* `fixed` menampilkan angka dalam format desimal tetap.
* `scientific` menampilkan angka dalam format ilmiah.

**Output:**

```
Pi dengan 2 desimal: 3.14
Pi dalam format ilmiah: 3.1416e+00
Pi dengan lebar 10: |      3.14159|
Nama      Umur     
Ali       25       
Budi      30       
```

Latihan Soal : Buatlah sebuah program C++ untuk menampilkan **nilai pi** dengan format berikut:

* Tampilkan nilai **pi** dengan presisi **3 angka desimal**.
* Tampilkan nilai **pi** dalam format ilmiah (scientific notation) dengan presisi **4 angka desimal**.
* Tampilkan nilai **pi** dengan lebar kolom **15 karakter**.
