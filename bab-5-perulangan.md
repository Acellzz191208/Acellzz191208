---
description: Perulangan
---

# Bab 5

#### **Perulangan (Looping) dalam C++**

Perulangan (looping) adalah salah satu konsep penting dalam pemrograman yang memungkinkan kita untuk mengeksekusi blok kode berulang kali selama suatu kondisi tertentu terpenuhi. C++ memiliki beberapa jenis perulangan, yaitu **`for loop`**, **`while loop`**, dan **`do-while loop`**. Selain itu, ada juga **`break`** dan **`continue`** untuk mengontrol alur perulangan.

***

#### **1. `for loop`**

`for loop` digunakan ketika jumlah perulangan sudah diketahui sebelumnya atau ketika kita perlu melakukan perulangan dengan batas tertentu. Dalam `for loop`, kita mendeklarasikan variabel kontrol, kondisi perulangan, dan perubahan nilai variabel kontrol dalam satu baris.

**Sintaks Dasar:**

```cpp
for (inisialisasi; kondisi; perubahan) {
    // Blok kode yang akan dijalankan berulang kali
}
```

* **Inisialisasi**: Menentukan nilai awal variabel kontrol.
* **Kondisi**: Mengevaluasi apakah perulangan terus dilakukan (perulangan berlanjut selama kondisi bernilai true).
* **Perubahan**: Mengubah nilai variabel kontrol setelah setiap iterasi.

**Contoh `for loop`:**

```cpp
#include <iostream>
using namespace std;

int main() {
    for (int i = 1; i <= 5; i++) {
        cout << "Perulangan ke-" << i << endl;
    }
    return 0;
}
```

**Penjelasan:**

* Program akan mencetak "Perulangan ke-1", "Perulangan ke-2", hingga "Perulangan ke-5".
* Variabel `i` dimulai dari 1 dan bertambah 1 setiap iterasi hingga mencapai 5.

**Output:**

```
Perulangan ke-1
Perulangan ke-2
Perulangan ke-3
Perulangan ke-4
Perulangan ke-5
```

***

#### **2. `while loop`**

`while loop` digunakan ketika kita tidak tahu berapa kali perulangan yang akan dilakukan, tetapi kita tahu kondisi yang harus dipenuhi agar perulangan terus berlanjut. Perulangan `while` terus berlangsung selama kondisi yang diberikan bernilai true.

**Sintaks Dasar:**

```cpp
while (kondisi) {
    // Blok kode yang akan dijalankan selama kondisi bernilai true
}
```

**Contoh `while loop`:**

```cpp
#include <iostream>
using namespace std;

int main() {
    int i = 1;
    while (i <= 5) {
        cout << "Perulangan ke-" << i << endl;
        i++;
    }
    return 0;
}
```

**Penjelasan:**

* Program ini sama dengan contoh `for loop` di atas. Namun, di sini variabel `i` diinisialisasi di luar perulangan, dan kita secara eksplisit meningkatkan nilai `i` di dalam blok perulangan.

**Output:**

```
Perulangan ke-1
Perulangan ke-2
Perulangan ke-3
Perulangan ke-4
Perulangan ke-5
```

***

#### **3. `do-while loop`**

`do-while loop` mirip dengan `while loop`, tetapi perbedaannya adalah perulangan **dijalankan minimal sekali** meskipun kondisi awalnya false. Kondisi dievaluasi **setelah** blok kode dieksekusi, bukan sebelum.

**Sintaks Dasar:**

```cpp
do {
    // Blok kode yang akan dijalankan
} while (kondisi);
```

**Contoh `do-while loop`:**

```cpp
#include <iostream>
using namespace std;

int main() {
    int i = 1;
    do {
        cout << "Perulangan ke-" << i << endl;
        i++;
    } while (i <= 5);
    return 0;
}
```

**Penjelasan:**

* Program ini juga mencetak "Perulangan ke-1", "Perulangan ke-2", hingga "Perulangan ke-5".
* Walaupun kondisi `i <= 5` sudah terpenuhi, blok kode akan dijalankan terlebih dahulu sebelum mengevaluasi kondisi.

**Output:**

```
Perulangan ke-1
Perulangan ke-2
Perulangan ke-3
Perulangan ke-4
Perulangan ke-5
```

***

#### **4. Penggunaan `break` dan `continue`**

* **`break`** digunakan untuk **menghentikan** perulangan secara langsung, bahkan jika kondisi perulangan masih bernilai true. Perulangan akan berhenti segera ketika pernyataan `break` dijalankan.
* **`continue`** digunakan untuk **melewati iterasi saat ini** dan langsung melanjutkan ke iterasi berikutnya tanpa mengeksekusi kode yang ada setelahnya di dalam perulangan.

**Contoh penggunaan `break`:**

```cpp
#include <iostream>
using namespace std;

int main() {
    for (int i = 1; i <= 10; i++) {
        if (i == 6) {
            break;  // Menghentikan perulangan saat i == 6
        }
        cout << "Perulangan ke-" << i << endl;
    }
    return 0;
}
```

**Penjelasan:**

* Program ini akan mencetak "Perulangan ke-1", "Perulangan ke-2", hingga "Perulangan ke-5", kemudian berhenti ketika mencapai nilai `i == 6` karena perintah `break`.

**Output:**

```
Perulangan ke-1
Perulangan ke-2
Perulangan ke-3
Perulangan ke-4
Perulangan ke-5
```

**Contoh penggunaan `continue`:**

```cpp
#include <iostream>
using namespace std;

int main() {
    for (int i = 1; i <= 5; i++) {
        if (i == 3) {
            continue;  // Lewati iterasi ini dan lanjutkan ke iterasi berikutnya
        }
        cout << "Perulangan ke-" << i << endl;
    }
    return 0;
}
```

**Penjelasan:**

* Program ini akan mencetak "Perulangan ke-1", "Perulangan ke-2", "Perulangan ke-4", "Perulangan ke-5". Iterasi ke-3 akan dilewati karena perintah `continue`.

**Output:**

```
Perulangan ke-1
Perulangan ke-2
Perulangan ke-4
Perulangan ke-5
```

***

#### **Kesimpulan:**

* **`for loop`** digunakan ketika jumlah perulangan sudah diketahui atau ditentukan oleh suatu batas.
* **`while loop`** digunakan ketika kondisi perulangan diketahui, tetapi jumlah perulangan tidak pasti.
* **`do-while loop`** digunakan ketika perulangan harus dilakukan minimal satu kali meskipun kondisi awalnya false.
* **`break`** menghentikan perulangan lebih awal.
* **`continue`** melewati iterasi saat ini dan melanjutkan ke iterasi berikutnya.

#### **Latihan Soal : Menghitung Jumlah Angka Genap dengan `for loop`**

**Deskripsi:**\
Buatlah program C++ yang menggunakan `for loop` untuk menghitung jumlah angka genap dari 1 hingga 100.

**Petunjuk:**

* Gunakan `for loop` untuk perulangan dari 1 hingga 100.
* Cek apakah angka tersebut genap (bilangan yang habis dibagi 2) dan hitung jumlahnya.

**Contoh Output:**

```
Jumlah angka genap dari 1 hingga 100 adalah: 50
```
