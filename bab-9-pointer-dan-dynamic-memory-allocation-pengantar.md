---
description: Pointer dan Dynamic Memory Allocation (pengantar)
---

# Bab 9

## **Pointer dan Dynamic Memory Allocation (Pengantar)**

**Pointer** adalah variabel yang menyimpan alamat memori dari variabel lain. Dalam C++, pointer memungkinkan kita untuk mengakses dan memanipulasi data secara langsung melalui alamat memori. Ini memberikan fleksibilitas dan efisiensi dalam pemrograman, terutama ketika kita bekerja dengan struktur data besar atau ingin mengelola memori secara dinamis.

**Dynamic Memory Allocation** adalah teknik untuk meminta memori secara dinamis selama eksekusi program, yang memungkinkan kita untuk mengalokasikan ruang memori sesuai kebutuhan program yang berjalan, dan membebaskannya ketika tidak diperlukan lagi. Dalam C++, kita menggunakan operator `new` untuk mengalokasikan memori secara dinamis dan `delete` untuk membebaskan memori tersebut.

***

#### **1. Apa itu Pointer?**

Pointer adalah variabel yang menyimpan alamat memori dari variabel lain.

* **Operator `&`** digunakan untuk mendapatkan alamat memori dari suatu variabel (dikenal sebagai "address-of operator").
* **Operator `*`** digunakan untuk mendeklarasikan pointer dan mengakses nilai yang disimpan di alamat memori yang ditunjuk oleh pointer (dikenal sebagai "dereferencing operator").

**Sintaks Dasar Pointer:**

```cpp
int a = 10;        // Variabel biasa
int *p = &a;       // Pointer p menyimpan alamat memori dari a

cout << &a;        // Menampilkan alamat memori a
cout << *p;        // Menampilkan nilai yang disimpan pada alamat yang ditunjuk oleh p (yaitu, 10)
```

* **`&a`** memberikan alamat memori dari variabel `a`.
* **`*p`** mengakses nilai yang ada pada alamat memori yang ditunjuk oleh `p` (yaitu, nilai `a`).

***

#### **2. Penggunaan `new` dan `delete`**

*   **`new`** digunakan untuk mengalokasikan memori secara dinamis. Memori akan dialokasikan di heap, bukan di stack. Ini berguna saat kita tidak tahu seberapa besar memori yang dibutuhkan pada saat kompilasi.

    **Contoh penggunaan `new`:**

    ```cpp
    int *ptr = new int;  // Mengalokasikan memori untuk satu bilangan integer
    *ptr = 5;            // Menyimpan nilai 5 di alamat memori yang ditunjuk oleh ptr
    cout << *ptr;        // Menampilkan nilai yang disimpan di ptr (yaitu 5)
    ```
*   **`delete`** digunakan untuk membebaskan memori yang telah dialokasikan dengan `new` setelah memori tersebut tidak lagi dibutuhkan, untuk mencegah kebocoran memori (memory leak).

    **Contoh penggunaan `delete`:**

    ```cpp
    delete ptr;   // Membebaskan memori yang dialokasikan oleh new
    ```

Jika kita mengalokasikan array dengan `new[]`, maka kita harus menggunakan `delete[]` untuk membebaskannya.

**Contoh penggunaan `new[]` dan `delete[]`:**

```cpp
int *arr = new int[5];   // Mengalokasikan array berukuran 5
arr[0] = 10;
arr[1] = 20;
delete[] arr;            // Membebaskan memori yang dialokasikan untuk array
```

***

#### **3. Mengakses Data dengan Pointer**

Dengan menggunakan pointer, kita dapat mengakses data pada alamat memori yang ditunjuk. Ini memungkinkan manipulasi data lebih efisien, terutama dalam kasus-kasus seperti struktur data yang besar atau pengelolaan memori dinamis.

**Contoh mengakses data dengan pointer:**

```cpp
int a = 10;
int *p = &a;      // Pointer p menyimpan alamat memori dari a

cout << "Nilai a: " << *p;  // Mengakses nilai a melalui pointer (10)
```

**Pointer dan array:**

```cpp
int arr[3] = {10, 20, 30};
int *p = arr;   // Pointer p menunjuk ke elemen pertama array

cout << *p;      // Menampilkan nilai pertama array (10)
cout << *(p+1);  // Menampilkan nilai kedua array (20)
```

Di sini, pointer `p` dapat digunakan untuk mengakses elemen-elemen array dengan cara menggunakan aritmetika pointer, seperti `*(p+1)` yang mengakses elemen kedua dalam array.

***

#### **4. Hubungan Pointer dengan Array dan Struct**

*   **Pointer dan Array**:\
    Array sebenarnya adalah sekumpulan elemen bertipe sama yang disimpan secara berurutan di memori. Nama array itu sendiri adalah pointer yang menunjuk ke elemen pertama array.

    **Contoh hubungan pointer dengan array:**

    ```cpp
    int arr[3] = {1, 2, 3};
    int *p = arr;  // Pointer p menunjuk ke elemen pertama array

    cout << *p;     // Menampilkan nilai elemen pertama (1)
    cout << *(p+1); // Menampilkan nilai elemen kedua (2)
    ```
*   **Pointer dan `struct`**:\
    Pointer juga bisa digunakan untuk mengakses anggota dalam `struct`. Kita dapat mendeklarasikan pointer yang menunjuk ke suatu `struct` dan menggunakan operator `->` untuk mengakses anggota `struct` yang ditunjuk oleh pointer.

    **Contoh penggunaan pointer dengan `struct`:**

    ```cpp
    struct Mahasiswa {
        string nama;
        int umur;
    };

    Mahasiswa mhs = {"Andi", 20};
    Mahasiswa *ptr = &mhs;  // Pointer ptr menunjuk ke variabel mhs

    // Mengakses anggota struct menggunakan pointer
    cout << ptr->nama;  // Menampilkan nama (Andi)
    cout << ptr->umur;  // Menampilkan umur (20)
    ```

    Di sini, operator `->` digunakan untuk mengakses anggota `struct` yang ditunjuk oleh pointer.

***

#### **Ringkasan:**

* **Pointer** adalah variabel yang menyimpan alamat memori dari variabel lain.
* **`new` dan `delete`** digunakan untuk alokasi dan dealokasi memori secara dinamis di heap.
* **Pointer dan array**: Nama array adalah pointer yang menunjuk ke elemen pertama array, dan pointer dapat digunakan untuk mengakses elemen-elemen array.
* **Pointer dan `struct`**: Pointer dapat digunakan untuk mengakses anggota dalam `struct` dengan menggunakan operator `->`.

Dengan pointer, kita memiliki kontrol yang lebih besar atas memori dan lebih efisien dalam mengelola data yang besar atau dinamis.

#### **Latihan Soal : Pengenalan Pointer**

**Deskripsi:**\
Buatlah program C++ yang mendeklarasikan variabel bertipe `int` dan pointer ke `int`. Gunakan pointer untuk menyimpan alamat variabel tersebut dan tampilkan nilai variabel menggunakan pointer.

**Petunjuk:**

* Gunakan operator `&` untuk mendapatkan alamat variabel.
* Gunakan operator `*` untuk mengakses nilai yang disimpan di alamat pointer.

**Contoh Output:**

```
Nilai variabel: 25
Alamat variabel: 0x12345678
Nilai melalui pointer: 25
```
