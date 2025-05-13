---
description: Struktur (Struct)
---

# Bab 8

#### **1. Definisi `struct` dalam C++**

`struct` (struktur) adalah tipe data terstruktur yang digunakan untuk mengelompokkan beberapa variabel yang berbeda jenisnya ke dalam satu unit. Setiap variabel dalam `struct` disebut anggota atau field (field). Dengan menggunakan `struct`, kita dapat menyimpan data yang terkait dalam satu entitas yang lebih mudah dikelola.

* **Keuntungan menggunakan `struct`**:
  * Memungkinkan pengelompokan data yang berbeda menjadi satu kesatuan.
  * Mempermudah pengelolaan data yang saling berhubungan.

**Sintaks Umum untuk Mendefinisikan `struct`:**

```cpp
struct NamaStruct {
    TipeData1 namaAnggota1;
    TipeData2 namaAnggota2;
    // dan seterusnya
};
```

**Contoh:**

```cpp
struct Mahasiswa {
    string nama;
    int umur;
    float ipk;
};
```

Di atas, `Mahasiswa` adalah sebuah `struct` yang memiliki tiga anggota: `nama` bertipe `string`, `umur` bertipe `int`, dan `ipk` bertipe `float`.

***

#### **2. Membuat dan Menggunakan `struct`**

Setelah mendefinisikan sebuah `struct`, kita bisa membuat variabel bertipe `struct` dan mengakses anggotanya menggunakan operator titik (`.`).

**Langkah-langkah untuk membuat dan menggunakan `struct`:**

1. **Deklarasi struct** – mendefinisikan tipe data yang berisi beberapa anggota.
2. **Membuat variabel bertipe struct** – seperti mendeklarasikan variabel biasa.
3. **Mengakses anggota struct** – menggunakan operator titik (`.`) untuk mengakses dan memodifikasi anggota.

**Contoh Program:**

```cpp
#include <iostream>
#include <string>
using namespace std;

struct Mahasiswa {
    string nama;
    int umur;
    float ipk;
};

int main() {
    // Membuat variabel bertipe struct Mahasiswa
    Mahasiswa mhs1;

    // Mengisi nilai anggota struct
    mhs1.nama = "Andi";
    mhs1.umur = 20;
    mhs1.ipk = 3.75;

    // Menampilkan anggota struct
    cout << "Nama: " << mhs1.nama << endl;
    cout << "Umur: " << mhs1.umur << endl;
    cout << "IPK: " << mhs1.ipk << endl;

    return 0;
}
```

**Penjelasan:**

* `struct Mahasiswa` mendefinisikan tipe data `Mahasiswa` yang berisi tiga anggota: `nama`, `umur`, dan `ipk`.
* Di dalam fungsi `main`, kita mendeklarasikan variabel `mhs1` bertipe `Mahasiswa`.
* Anggota-anggota struct diakses dengan menggunakan operator titik (`.`) untuk memberi nilai dan mencetaknya.

***

#### **3. `struct` di dalam Array**

Kita juga bisa membuat array yang elemen-elemennya adalah variabel bertipe `struct`. Ini berguna ketika kita ingin menyimpan banyak data dari tipe yang sama (misalnya, data mahasiswa) dalam satu array.

**Sintaks untuk Membuat Array dari Struct:**

```cpp
struct NamaStruct {
    TipeData1 namaAnggota1;
    TipeData2 namaAnggota2;
    // dan seterusnya
};

NamaStruct arrayStruct[n];
```

**Contoh Program Array Struct:**

```cpp
#include <iostream>
#include <string>
using namespace std;

struct Mahasiswa {
    string nama;
    int umur;
    float ipk;
};

int main() {
    // Membuat array dari struct Mahasiswa
    Mahasiswa mhs[3];

    // Mengisi nilai untuk setiap elemen array
    mhs[0].nama = "Andi";
    mhs[0].umur = 20;
    mhs[0].ipk = 3.75;

    mhs[1].nama = "Budi";
    mhs[1].umur = 22;
    mhs[1].ipk = 3.85;

    mhs[2].nama = "Cici";
    mhs[2].umur = 21;
    mhs[2].ipk = 3.65;

    // Menampilkan data mahasiswa dari array
    for (int i = 0; i < 3; i++) {
        cout << "Mahasiswa " << i+1 << ":" << endl;
        cout << "Nama: " << mhs[i].nama << endl;
        cout << "Umur: " << mhs[i].umur << endl;
        cout << "IPK: " << mhs[i].ipk << endl;
        cout << endl;
    }

    return 0;
}
```

**Penjelasan:**

* Array `mhs[3]` berisi 3 elemen bertipe `Mahasiswa`.
* Setiap elemen array (`mhs[0]`, `mhs[1]`, `mhs[2]`) adalah sebuah `struct Mahasiswa`.
* Program kemudian mengisi dan menampilkan data untuk setiap mahasiswa menggunakan perulangan `for`.

***

#### **4. `struct` di dalam Fungsi**

Kita juga dapat menggunakan `struct` dalam fungsi, baik sebagai parameter input maupun output. Fungsi dapat menerima sebuah `struct` sebagai argumen atau mengembalikan `struct` sebagai nilai.

**Contoh Program: `struct` sebagai Parameter Fungsi:**

```cpp
#include <iostream>
#include <string>
using namespace std;

struct Mahasiswa {
    string nama;
    int umur;
    float ipk;
};

// Fungsi untuk menampilkan data mahasiswa
void tampilkanMahasiswa(Mahasiswa mhs) {
    cout << "Nama: " << mhs.nama << endl;
    cout << "Umur: " << mhs.umur << endl;
    cout << "IPK: " << mhs.ipk << endl;
}

int main() {
    Mahasiswa mhs1 = {"Andi", 20, 3.75};
    
    // Memanggil fungsi dan mengirim struct sebagai parameter
    tampilkanMahasiswa(mhs1);
    
    return 0;
}
```

**Penjelasan:**

* Fungsi `tampilkanMahasiswa` menerima parameter bertipe `Mahasiswa` dan menampilkan data anggotanya.
* Dalam `main`, kita membuat variabel `mhs1` bertipe `Mahasiswa` dan mengirimkannya ke fungsi `tampilkanMahasiswa`.

**Contoh Program: `struct` sebagai Return Value Fungsi:**

```cpp
#include <iostream>
#include <string>
using namespace std;

struct Mahasiswa {
    string nama;
    int umur;
    float ipk;
};

// Fungsi yang mengembalikan struct Mahasiswa
Mahasiswa buatMahasiswa(string nama, int umur, float ipk) {
    Mahasiswa mhs;
    mhs.nama = nama;
    mhs.umur = umur;
    mhs.ipk = ipk;
    return mhs;
}

int main() {
    Mahasiswa mhs1 = buatMahasiswa("Budi", 21, 3.85);
    
    // Menampilkan data mahasiswa yang dikembalikan dari fungsi
    cout << "Nama: " << mhs1.nama << endl;
    cout << "Umur: " << mhs1.umur << endl;
    cout << "IPK: " << mhs1.ipk << endl;

    return 0;
}
```

**Penjelasan:**

* Fungsi `buatMahasiswa` mengembalikan sebuah `struct Mahasiswa` yang diisi berdasarkan parameter yang diberikan.
* Di dalam `main`, kita memanggil fungsi tersebut dan menyimpan hasilnya dalam variabel `mhs1`.

***

#### **Ringkasan:**

* **`struct`** adalah tipe data terstruktur yang digunakan untuk mengelompokkan variabel-variabel yang berbeda jenis menjadi satu kesatuan.
* **Membuat dan Menggunakan `struct`** melibatkan mendeklarasikan struct, membuat variabel bertipe struct, dan mengakses anggotanya menggunakan operator titik (`.`).
* **`struct` di dalam Array** memungkinkan kita untuk menyimpan banyak data dari tipe yang sama dalam satu array.
* **`struct` di dalam Fungsi** memungkinkan kita untuk menggunakan struct sebagai parameter dan return value dalam fungsi, memudahkan pengelolaan data yang kompleks.

#### **Latihan Soal : Mendefinisikan dan Menggunakan `struct`**

**Deskripsi:**\
Buatlah program C++ yang mendefinisikan sebuah `struct` bernama `Buku`, yang memiliki anggota:

* `judul` bertipe `string`
* `penulis` bertipe `string`
* `tahunTerbit` bertipe `int`
* `harga` bertipe `float`

Kemudian, buatlah sebuah variabel bertipe `Buku` dan masukkan data buku (judul, penulis, tahun terbit, harga) melalui input pengguna. Setelah itu, tampilkan data buku tersebut.

**Petunjuk:**

* Gunakan `cin` untuk memasukkan data dan `cout` untuk menampilkannya.

**Contoh Output:**

```
Masukkan judul buku: C++ Programming
Masukkan penulis: John Doe
Masukkan tahun terbit: 2020
Masukkan harga: 150000
Data Buku:
Judul: C++ Programming
Penulis: John Doe
Tahun Terbit: 2020
Harga: 150000
```
