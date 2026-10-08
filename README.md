# Tugas Konversi Program Java ke PHP

## Catatan

Pada tugas ini, program Java dikonversi ke bahasa PHP. Untuk menjalankan dan melihat hasil output file PHP, saya menggunakan **PHP server dan Code Runner Extension** pada Visual Studio Code.

---

# 01

## Output

### Main.php

**Foto output:**  
<img width="883" height="90" alt="main php_01" src="https://github.com/user-attachments/assets/4b0e033b-f431-4d09-8659-847724db8038" />


## Perubahan

### Main.php
- Menambahkan `Main::main([]);` agar method `main()` dapat dijalankan secara manual menggunakan PHP.
- Menambahkan `require 'iPhone.php';` supaya class `iPhone` dapat digunakan pada file `Main.php`.

### iPhone.php
- Pada Java, constructor menggunakan nama yang sama dengan nama class.
- Pada PHP, constructor ditulis menggunakan `__construct()`.

---

# 02

## Output

### Aplikasi.php

**Foto output:**  
<img width="1438" height="123" alt="aplikasi_php_02" src="https://github.com/user-attachments/assets/405a7d3c-8da2-4c86-bbc1-e20a5ddecf3b" />

## Perubahan

### Mahasiswa.php
- PHP tidak mendukung constructor overloading seperti Java.
- Beberapa constructor yang ada pada Java digabung menjadi satu `__construct()`.
- Parameter menggunakan nilai default agar object tetap dapat dibuat dengan jumlah argumen yang berbeda.

---

# 03

## Output

### App.php

**Foto output:**  
<img width="678" height="373" alt="main php_03" src="https://github.com/user-attachments/assets/962973c3-24d9-453f-b733-8cd1c3d30c17" />


### Main.php

**Foto output:**  
<img width="1889" height="114" alt="app php_03" src="https://github.com/user-attachments/assets/95ddad79-6c4b-4dec-b320-03c95488121f" />

## Perubahan

### App.php
- Constructor pada Java diubah menjadi `__construct()` di PHP.
- `super()` diganti dengan `parent::__construct()`.
- `super.tampilkanInfo()` diubah menjadi `parent::tampilkanInfo()`.
- `@Override` tidak digunakan karena PHP otomatis melakukan overriding ketika subclass memiliki method dengan nama yang sama.
- Method `main()` tetap dibuat static, tetapi pemanggilannya dilakukan secara manual menggunakan `App::main([]);` atau `Main::main([]);`.
- Penulisan return type pada PHP berada setelah nama method, contohnya `luas(): float`.

### BangunDatar.php
- Method `luas()` dan `keliling()` dibuat `public` agar dapat digunakan dari class lain dan dapat dioverride oleh subclass.

### Lingkaran.php
- `Math.PI` pada Java diganti dengan `M_PI` pada PHP.
- Pemanggilan `keliling()` pada objek `Segitiga` tetap menggunakan method dari parent apabila tidak terdapat method tersebut di subclass.
- Pada bagian pembagian bilangan integer, digunakan `intdiv()` agar hasilnya mengikuti perilaku pembagian integer pada Java.

### Mahasiswa.php
- Constructor overloading pada Java disesuaikan dengan kemampuan PHP menggunakan satu `__construct()` dengan parameter default.

### MahasiswaInternational.php
- Karena PHP tidak dapat membedakan constructor hanya berdasarkan jumlah parameter, parameter tertentu diperiksa menggunakan tipe data dan `is_string()`.
- Data milik class parent diisi melalui `parent::__construct()`.
- Properti `private` pada parent tidak diakses secara langsung oleh subclass.

---

# 04

## Output

### Main.php

**Foto output:**  
<img width="697" height="278" alt="main_04" src="https://github.com/user-attachments/assets/1327f331-fef0-421c-a970-26f72da9f282" />


## Perubahan

### Handphone.php
- Properti `protected` tetap digunakan sehingga dapat diakses oleh class turunannya.
- Constructor Java diubah menjadi `__construct()`.
- `System.out.println()` diganti menggunakan `echo` dengan `"\n"` untuk membuat baris baru.
- Return type `void` ditulis setelah tanda kurung method.

### Smartphone.php
- Menambahkan `require_once 'Handphone.php';` untuk memuat class parent.
- `super(merk, model)` diubah menjadi `parent::__construct($merk, $model)`.
- Anotasi `@Override` dihapus.
- Akses properti menggunakan `$this->merk` dan `$this->model`.

### FeaturePhone.php
- Menggunakan `require_once` untuk memuat class `Handphone`.
- Constructor parent dipanggil dengan `parent::__construct()`.
- `@Override` tidak diperlukan pada PHP.
- Properti parent diakses menggunakan `$this->`.
- Method `mainGameSnake()` tetap berada khusus pada `FeaturePhone`.

### Main.php
- Array Java `Handphone[]` diubah menjadi array PHP biasa menggunakan `[]`.
- Enhanced for-loop Java diganti menjadi `foreach`.
- `else if` dapat ditulis sebagai `elseif` pada PHP.
- Casting seperti `((Smartphone) hp)` tidak diperlukan. Setelah pengecekan `instanceof`, method dapat langsung dipanggil.
- `Main::main([]);` ditambahkan agar program dapat dijalankan melalui Code Runner.

---

# 05

## Output

### Main.php

**Foto output:**  
<img width="686" height="225" alt="05" src="https://github.com/user-attachments/assets/7e08283c-9d93-490c-99b5-4600827a1b7f" />

## Perubahan

### Pasien.php
- Constructor diubah menjadi `__construct()`.
- Tipe data `String` pada Java menjadi `string` pada PHP.
- Return type ditulis setelah nama method, misalnya `getNama(): string`.

### Dokter.php
- Menambahkan `require_once 'Pasien.php';`.
- Parameter `Pasien pasien` disesuaikan menjadi `Pasien $pasien`.
- Object `Pasien` hanya digunakan sebagai parameter dan tidak disimpan sebagai property pada `Dokter`.

### Pemain.php
- Constructor Java diganti menjadi `__construct()`.
- `String` menjadi `string`.
- Return type method diletakkan setelah tanda kurung.

### Tim.php
- `List` dari Java tidak digunakan karena PHP menyediakan tipe `array`.
- Perulangan daftar pemain menggunakan `foreach`.
- Property diakses menggunakan `$this->daftarPemain`.
- Daftar pemain dibuat dari luar lalu diberikan kepada object `Tim`.

### Bab.php
- Constructor diubah menjadi `__construct()`.
- Penulisan `String` disesuaikan menjadi `string`.
- Return type diletakkan setelah nama method.

### Buku.php
- `ArrayList` dan `List` pada Java diganti menggunakan array PHP.
- `add()` diganti dengan penambahan elemen menggunakan `$this->daftarBab[]`.
- Method `tambahBab()` dipanggil menggunakan `$this->tambahBab()`.
- Object `Bab` dibuat langsung dari dalam class `Buku`.

### Main.php
- `Arrays.asList()` diganti menjadi array biasa, misalnya `[$pemain1, $pemain2]`.
- `require_once` ditambahkan untuk setiap class yang diperlukan.
- Variabel object dapat dibuat `null` ketika sudah tidak digunakan.
- `Main::main([]);` digunakan untuk menjalankan method `main()` secara manual.

---

# 06

## Output

### Main.php

**Foto output:**  
<img width="731" height="353" alt="06" src="https://github.com/user-attachments/assets/9a4ebfb7-5e95-41f0-90c5-66a4a7b09610" />

## Perubahan

### Vehicle.php
- Constructor menggunakan `__construct()`.
- Properti diakses menggunakan `$this->`.
- `System.out.println()` diganti dengan `echo`.
- Return type `void` ditulis setelah nama method.

### Movable.php
- Method interface ditulis menggunakan `public function`.
- Karena interface hanya mendeklarasikan method, deklarasinya diakhiri dengan `;`.

### Fuelable.php
- Default method pada interface Java disesuaikan menggunakan **trait** pada PHP.
- Trait digunakan agar method `refuel()` dapat digunakan oleh class yang membutuhkannya.

### Car.php
- `Movable` tetap digunakan melalui `implements`.
- `Fuelable` digunakan dengan `use Fuelable;`.
- Method `refuel()` yang dibuat pada class `Car` akan menggunakan implementasi milik `Car` dibandingkan method dari trait.
- `require_once` digunakan untuk memuat class dan interface/trait yang diperlukan.

### Boat.php
- Menggunakan konsep yang sama dengan `Car`.
- `Movable` diimplementasikan melalui `implements`.
- `Fuelable` digunakan melalui `use Fuelable;`.
- Method `refuel()` pada class dapat menggantikan implementasi dari trait.

### Motor.php
- `Motor` tidak memiliki method `refuel()` sendiri.
- Oleh karena itu, `Motor` menggunakan implementasi `refuel()` yang berasal dari trait `Fuelable`.
- Konsep ini digunakan sebagai pengganti default method pada interface Java.

### Main.php
- `System.out.println()` yang tidak memiliki isi diganti dengan `echo "\n";`.
- Method `main()` dipanggil secara manual menggunakan `Main::main([]);`.

---

# Kesimpulan

Dari proses konversi beberapa program tersebut, terdapat beberapa perbedaan penting antara Java dan PHP, terutama pada bagian **constructor, inheritance, interface, array, method overriding, dan cara menjalankan program**.

PHP tidak memiliki entry point `main()` seperti Java, sehingga method `main()` perlu dipanggil secara manual. Selain itu, PHP tidak mendukung constructor overloading secara langsung sehingga penggunaannya disesuaikan dengan parameter default atau pengecekan tipe data.

Dengan melakukan penyesuaian tersebut, program yang sebelumnya dibuat menggunakan Java dapat dijalankan menggunakan PHP dan menghasilkan output yang sesuai dengan program aslinya.
