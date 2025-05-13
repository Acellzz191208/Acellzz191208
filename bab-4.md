---
description: Percabangan (Kontrol Alur)
---

# Bab 4

## **Percabangan (Kontrol Alur) dalam C++**

Percabangan (control flow) adalah bagian penting dalam pemrograman yang memungkinkan kita untuk membuat keputusan berdasarkan kondisi tertentu. Dengan menggunakan percabangan, kita dapat mengarahkan alur eksekusi program ke bagian kode yang berbeda, tergantung pada apakah kondisi yang diberikan bernilai **true** atau **false**.

Di C++, percabangan biasanya menggunakan **`if`**, **`else if`**, **`else`**, dan **`switch`** untuk menentukan alur eksekusi program.

#### 1. **Penggunaan `if`, `else if`, dan `else`**

* **`if`** digunakan untuk mengevaluasi suatu kondisi. Jika kondisi tersebut bernilai **true**, maka blok kode di dalamnya akan dieksekusi.
* **`else if`** digunakan setelah `if` untuk mengevaluasi kondisi lain jika kondisi pertama tidak terpenuhi.
* **`else`** digunakan untuk menangani kondisi ketika **semua kondisi sebelumnya gagal** (false).

**Sintaks Dasar:**

```cpp
if (kondisi) {
    // Eksekusi jika kondisi benar (true)
} else if (kondisi_lain) {
    // Eksekusi jika kondisi_lain benar
} else {
    // Eksekusi jika tidak ada kondisi yang benar
}
```

**Contoh Program dengan `if`, `else if`, dan `else`:**

```cpp
#include <iostream>
using namespace std;

int main() {
    int nilai;
    cout << "Masukkan nilai (0 - 100): ";
    cin >> nilai;
    
    // Percabangan dengan if, else if, dan else
    if (nilai >= 80) {
        cout << "Grade: A" << endl;  // Jika nilai >= 80
    } else if (nilai >= 60) {
        cout << "Grade: B" << endl;  // Jika nilai >= 60 dan < 80
    } else if (nilai >= 40) {
        cout << "Grade: C" << endl;  // Jika nilai >= 40 dan < 60
    } else {
        cout << "Grade: D" << endl;  // Jika nilai < 40
    }

    return 0;
}
```

**Penjelasan:**

* Program ini meminta input nilai dari pengguna.
* Berdasarkan nilai yang dimasukkan, program akan menampilkan grade (A, B, C, atau D) menggunakan percabangan `if`, `else if`, dan `else`.

**Output Contoh:**

```
javaSalinEditMasukkan nilai (0 - 100): 75
Grade: B
```

***

#### 2. **Penggunaan `switch` untuk Pilihan Banyak**

`switch` adalah struktur kontrol yang memungkinkan kita untuk memilih di antara beberapa opsi berdasarkan nilai suatu ekspresi. `switch` lebih efektif daripada banyak pernyataan `if`-`else if` ketika kita memiliki banyak pilihan untuk diuji.

**Sintaks Dasar:**

```cpp
switch (ekspresi) {
    case nilai_1:
        // Eksekusi jika ekspresi == nilai_1
        break;
    case nilai_2:
        // Eksekusi jika ekspresi == nilai_2
        break;
    // Tambahkan lebih banyak case jika diperlukan
    default:
        // Eksekusi jika tidak ada nilai yang cocok
}
```

* **`case`** digunakan untuk mencocokkan ekspresi dengan nilai tertentu.
* **`break`** digunakan untuk keluar dari blok `switch` setelah menemukan nilai yang cocok. Jika `break` tidak digunakan, program akan terus mengeksekusi case berikutnya (fall-through).
* **`default`** adalah blok kode yang dijalankan jika tidak ada `case` yang cocok dengan nilai ekspresi.

**Contoh Program dengan `switch`:**

```cpp
#include <iostream>
using namespace std;

int main() {
    int pilihan;
    cout << "Pilih menu:\n";
    cout << "1. Makanan\n";
    cout << "2. Minuman\n";
    cout << "3. Buah\n";
    cout << "Masukkan pilihan (1-3): ";
    cin >> pilihan;

    // Percabangan dengan switch
    switch (pilihan) {
        case 1:
            cout << "Anda memilih Makanan\n";
            break;
        case 2:
            cout << "Anda memilih Minuman\n";
            break;
        case 3:
            cout << "Anda memilih Buah\n";
            break;
        default:
            cout << "Pilihan tidak valid\n";  // Jika tidak ada case yang cocok
    }

    return 0;
}
```

**Penjelasan:**

* Program meminta pengguna untuk memilih salah satu dari tiga menu: makanan, minuman, atau buah.
* Berdasarkan pilihan yang dimasukkan, program akan menampilkan pilihan yang sesuai menggunakan `switch`.

**Output Contoh:**

```
Pilih menu:
1. Makanan
2. Minuman
3. Buah
Masukkan pilihan (1-3): 2
Anda memilih Minuman
```

***

#### **Perbedaan `if` dan `switch`**

1. **`if`** lebih fleksibel dan bisa digunakan untuk mengevaluasi kondisi yang lebih kompleks (misalnya rentang nilai atau kondisi boolean lainnya).
2. **`switch`** hanya cocok untuk memilih di antara beberapa nilai yang spesifik dan tidak bisa digunakan untuk kondisi yang lebih kompleks (misalnya rentang nilai atau ekspresi boolean).

***

#### **Contoh Kasus Pemilihan Menu dengan `switch` dan `if`**

**Soal:**

Buatlah program C++ yang meminta pengguna untuk memasukkan angka antara 1 hingga 4 yang mewakili menu pilihan:

1. Tambah
2. Kurang
3. Kali
4. Bagi

Setelah itu, program meminta dua angka dan melakukan operasi sesuai dengan menu yang dipilih. Gunakan `switch` untuk memilih menu dan `if` untuk memvalidasi apakah pembagian dengan nol dilakukan.

**Contoh Input dan Output:**

**Input:**

```
Masukkan pilihan operasi:
1. Tambah
2. Kurang
3. Kali
4. Bagi
Pilih operasi (1-4): 4
Masukkan angka pertama: 10
Masukkan angka kedua: 0
```

**Output:**

```
Pembagian dengan nol tidak diperbolehkan!
```

#### **Latihan Soal : Grade Siswa dengan `if`, `else if`, dan `else`**

**Deskripsi:**\
Buatlah program C++ yang menerima nilai ujian seorang siswa (angka antara 0 hingga 100), kemudian program akan menampilkan grade berdasarkan nilai tersebut. Berikut adalah ketentuan untuk grade:

* Nilai 80 - 100 : Grade A
* Nilai 60 - 79 : Grade B
* Nilai 40 - 59 : Grade C
* Nilai di bawah 40 : Grade D

**Petunjuk:**

* Gunakan percabangan `if`, `else if`, dan `else`.

**Contoh Input dan Output:**

**Input:**

```
Masukkan nilai ujian: 75
```

**Output:**

```
Grade: B
```
