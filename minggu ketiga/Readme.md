# Rangkuman Minggu Ketiga SKILVUL
## JavaScript Modules

Sebuah Js modules adalah cara untuk memaintance kode dengan file kode yang berbeda.

Keuntungan yang diperoleh dengan menggunakan modules:

- Mudah untuk mengelola kode (Maintance).
- Kode tidak berada di satu file sehingga tidak menumpuk.

Cara kerjanya itu dengan menghubungkan file source modules dua ke file utama.

dengan menggunakan deklarasi **Export**, memungkinkan value export keluar sebagai JS Modules dan 
ditangkap ke file js lain dengan menggunakan **Import** Deklarasi.

agar Export deklarasi dapat digunakan maka file harus diterjemahkan sebagai module. Menambahkan 
type="module" kedalam syntax script

**Syntax Export dan Import**

```
// Syntax pada file Export 

export let motor = ["yamaha","suzuki","honda"]

// Syntax pada file Import 
import {motor as motorJepang} from "./jepang.js"
```

splice digunakan untuk memanipulasi hapus data pada varibel.
**contoh pada array**
```
motorJepang.splice(1,1)
```


### Recusive Case

Sebuah Fungsi yang memanggil dirinya sendiri. Terdapat dua inputan yaitu Base Case atau
Recusive Case. Fungsi memanggil dirinya sendiri sampai kondisinya bertemu.

Contoh Recusive Case
```
function deretAngka(n){
// BaseCase, Fungsi akan berhenti jika kondisi sudah selesai
if (n==1){
console.log(n)
}else{
// Recursive Case
deretAngka(n-1)
}
console.log(2) // 1	
}
```