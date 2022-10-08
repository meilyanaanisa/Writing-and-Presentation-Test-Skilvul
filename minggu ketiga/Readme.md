# Rangkuman Minggu Ketiga SKILVUL
## JavaScript Array
Apa itu Array, adalah cara untuk mengorganisasi data kita dan menyimpan data.

Array sendiri dapat menyimpan berbagai tipe data seperti :
- String
- Number
- Boolean
- dan lainnya

Cara menggunakan Array itu dengan kurung siku []
dan didalamnya terdapat data

contohnya
```
let contoh = ["nama",35,true];
console.log(contoh);
```

dan cara akses array berdasarkan index, dan dimulai dari 0
```
let contoh = ["nama",35,true];
console.log(contoh[1]); //hasil 35

let contoh = ["nama",35,true];
console.log(contoh[0]); //hasil nama

let contoh = ["nama",35,true];
console.log(contoh[2]); //hasil true
```

- menambahkan type data pada array
```
let contoh = ["nama",35,true];
console.log(contoh);

contoh[0] = "kucing";
console.log (contoh);
// maka data bertambah menjadi ["kucing",nama",35,true,]
```

**Const in Array**
- menggunakan let, diperbolehkan mengubah data pada array dan konten nilai pada array.
- conts, tidak di perbolehkan mengubah data hanya nilai pada data array.
- tidak bisa mengubah array dengan array baru dengan const

**Array Properties**
Constructor, Length, Index, Input dan prototype

.length mengembalikan nilai panjang data pada array
```
let contoh = ["nama",35,true];
console.log(contoh.length);  //3
```

**Array Methods**
Array biasa disebut built in method sehingga tidak perlu membuat function lagi jika method yang kita butuhkan sudah tersedia.
- menambahkan type data di awal dengan unshift
```
let contoh = ["nama",35,true];
console.log(contoh);

contoh.unshift("Angkasa");
console.log(contoh);
//output ["Angkasa","nama",35,true]
```
- menghapus type data di awal dengan shift
```
let contoh = ["nama",35,true];
console.log(contoh);

contoh.shift();
console.log(contoh);
//output [35,true]
```
- menambahkan type data di akhir dengan push
```
let contoh = ["nama",35,true];
console.log(contoh);

contoh.push("kucing");
console.log (contoh);
// maka data bertambah menjadi ["nama",35,true,"kucing"]
```
- menghapus tipe data di akhir dengan pop
```
let contoh = ["nama",35,true];
console.log(contoh);

contoh.pop();
console.log;

//output ["nama",35];
```
- mengurutkan tipe data berdasarkan Ascending atau Descending
```
let angka = [3,7,1,2];
angka.sort();

//output [1,2,3,7]
```
**Looping pada Array**
Array memiliki built in method untuk melakukan looping dengan .map() dan .forEach()

- .forEach() melakukan looping(perulangan) pada setiap element array. Dilakukan saat menampilkan data array atau menyimpan ke database.
```
const kendaraan = ["becak","mobil","sepeda"]
cars.forEach(element) => { 
    console.log(element);
});

// output ["becak","mobil,"sepeda"]
```
- .map melakukan perulangan dengan membua array baru
```
let arr = [1,2,3,4,5];

let doubled = arr.map(num => {
    return num * 2;
});
console.log(doubled);
```
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

## JavaScript Asynchronous
Proses antrian dibaca dari atas ke bawah. Sedangkan Asynchronous memblocking sebuah operasi yang sedang berjalan. Dan hal ini dapat mempermudah user dalam berinteraksi dengan website kita.  