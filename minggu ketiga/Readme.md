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
**Multidimensional Array**
Didefiniskan sebagai Array di dalam Array
```
let hewan = [
    ["kucing","kelinci","ayam"],
    ["burung","capung","kelelawar"],
    ["angsa","buaya","katak"],
];

console.log(hewan);
```
- mengakses dimensional array, didefiniskan seperti matrix (x,y). X sebagai isi data array dan Y sebagai jumlah array.
```
let hewan = [
    ["kucing","kelinci","ayam"],
    ["burung","capung","kelelawar"],
    ["angsa","buaya","katak"],
];

console.log(hewan[1][2]);
```

**Akses Multidimensional Array**
Terdapat property dan method built-in method

- menggunakan operasi .map
```
let inventory = [
    ['Kaos Polos' , 10],
    ['Jaket' , 5],
    ['Topi' , 12],
    ['Celana' , 4],
];
inventory.map(dataInventory => {
    let terjual = 100 - dataInventory[1];
    dataInventory[2] = terjual;
});
console.table(inventory);
```
- Looping Mutidimesional Array
```
let inventory = [
    ['Kaos Polos' , 10],
    ['Jaket' , 5],
    ['Topi' , 12],
    ['Celana' , 4],
];
inventory.forEach((baris) => {
    baris.forEach((column) => {
        console.table(column);
    });
});
```

## JavaScript Object
Sebuah type data yang menyimpan properti dan fungsi(method) didalam variabel.
- properti, data lengkap dari sebuah object
- method, aksi dari sebuah object

**Membuat sebuah object**
```
let hewan = {
    nama: "kucing",
    usia: 2,
};
```

**Mengakses sebuah object**
```
let hewan = {
    nama: "kucing",
    usia: 2,
};
console.log(hewan);
```
**Mengakses properti object dot notion**
```
let hewan = {
    nama: "kucing",
    usia: 2,
};
console.log(hewan.nama);
```
**Mengakses properti object bracket**
```
let hewan = {
    nama: "kucing",
    usia: 2,
};
console.log(hewan["nama"]);
```
**Update Object**

- Object dapat mengupdate value dari key yang sudah tersedia
- Object dapat menambahkan key dan value baru
```
 let hewan = {
    nama: "kucing",
    usia: 2,
};

hewan.jenis = "betina";
console.log(hewan);
```
- jangan menggunakan constant pada variabel object. kita tidak bisa mengganti seluruh data dengan object baru.
```
 let hewan = {
    nama: "kucing",
    usia: 2,
};
people = {
    fullname: "Ucilina"
}
console.log(hewan);
// output error
```
**Menghapus propertie dari object menggunakan delete operator**
```
 let hewan = {
    nama: "kucing",
    usia: 2,
};

delete hewan.usia;
console.log(hewan);
```
**Membuat custom method**
```
const greeting = {
    welcome: function (){
        return 'Halo Selamat Datang';
    },
    afterTransaction: function (){
        return 'Terima Kasih';
    },
};

console.log(greeting.welcome());
```
- Nested Object
Object kompleks yang berasal dari turunan object lainnya.
- Pass By References
Mengubah data object melalui function dan memasukkan sebagai parameter function
- Looping object
Menampilkan seluruh object properti
```
for(let key in object){

};
```
- Array of Object
menyimpan data lebih dari satu dalam bentuk array.

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