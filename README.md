# Quis-Struktur-Data
# 1. Karakteristik Memori dan Proses Akses Data

Array mampu mengakses elemen dengan kompleksitas waktu `O(1)` karena data disimpan secara berurutan (kontinu) di dalam memori. Setiap elemen memiliki indeks yang dapat dihitung langsung dari alamat dasar array ditambah offset indeks tertentu. Dengan mekanisme tersebut, sistem dapat langsung menemukan lokasi data tanpa perlu memeriksa elemen lainnya.

Berbeda dengan Array, pada Singly Linked List data tidak disimpan secara berdekatan di memori. Setiap node terdiri dari data dan pointer yang menunjuk ke node selanjutnya. Untuk menemukan elemen tertentu, proses harus dilakukan dengan menelusuri node satu per satu mulai dari node pertama hingga posisi yang dicari. Oleh sebab itu, waktu akses pada Linked List menjadi `O(n)`.

---

# 2. Analisis Efisiensi Operasi Manipulasi Data

Linked List lebih efektif dibandingkan Array ketika sering dilakukan operasi penyisipan (*insertion*) dan penghapusan (*deletion*), khususnya pada bagian awal maupun tengah struktur data.

Pada Array, insertion dan deletion mengharuskan elemen lain digeser agar susunan indeks tetap teratur. Proses pergeseran tersebut membutuhkan kompleksitas waktu `O(n)`.

Sementara itu, pada Linked List, insertion dan deletion cukup dilakukan dengan mengubah hubungan pointer antar node tanpa memindahkan data lainnya. Jika posisi node telah diketahui sebelumnya, operasi tersebut dapat dilakukan dalam waktu `O(1)`.

Karena alasan tersebut, Linked List lebih sesuai digunakan untuk data yang ukurannya sering berubah secara dinamis.

---

# 3. Konsep Doubly Linked List

Pada Doubly Linked List, setiap node memiliki tiga komponen utama, yaitu:

- Data
- Pointer menuju node berikutnya (*next*)
- Pointer menuju node sebelumnya (*prev*)

Struktur ini berbeda dengan Singly Linked List yang hanya memiliki satu pointer *next*.

Adanya pointer tambahan menyebabkan penggunaan memori menjadi lebih besar karena setiap node menyimpan dua alamat pointer. Namun, kelebihannya adalah proses traversal dapat dilakukan ke dua arah, yaitu maju maupun mundur.

Selain itu, Doubly Linked List juga mempermudah proses penghapusan node karena sistem tidak perlu mencari node sebelumnya terlebih dahulu.

---

# 4. Mekanisme Circular Linked List

Circular Linked List merupakan struktur linked list yang berbentuk melingkar, di mana node terakhir tidak menunjuk ke `NULL`, tetapi kembali menunjuk ke node pertama.

Hal ini berbeda dengan Linked List biasa yang menggunakan `NULL` sebagai penanda akhir data.

Karena sifatnya yang melingkar, proses traversal dapat dilakukan terus-menerus tanpa harus kembali ke awal secara manual.

Salah satu penerapan Circular Linked List adalah pada metode *Round Robin Scheduling* dalam sistem operasi. Pada metode tersebut, setiap proses CPU dijalankan secara bergiliran dan berulang secara siklus sehingga struktur melingkar menjadi lebih efisien digunakan.

---

# 5. Array Dinamis pada Python

`Python list` menerapkan konsep *Dynamic Array*. Ketika operasi `append` dilakukan dan kapasitas array sudah penuh, Python akan membuat blok memori baru dengan ukuran yang lebih besar.

Selanjutnya, seluruh elemen dari array lama akan disalin ke lokasi memori yang baru. Setelah proses penyalinan selesai, memori lama akan dilepaskan dan sistem mulai menggunakan array baru tersebut.

Mekanisme ini memungkinkan ukuran `Python list` bertambah secara otomatis tanpa pengguna harus menentukan kapasitas awal secara manual.

Walaupun proses *resize* membutuhkan waktu `O(n)` karena adanya penyalinan data, operasi `append` secara keseluruhan tetap dianggap efisien dengan kompleksitas *amortized* `O(1)`.
