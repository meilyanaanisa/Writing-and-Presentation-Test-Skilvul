# Rangkuman Minggu Pertama SKILVUL

## Looping (Perulangan)
Sebuah perulangan yang dikerjakan sampai kondisinya terpenuhi maka akan stop eksekusi.

- **For Loop**
perulangan yang sudah diketahui sudah tahu pasti berapa banyak nilai perulangan.

```
let nilai = 1;
for (nilai=i; i<=15; i++){
  console.log(i);
}
```
- **While Loop**
Sebuah perulangan dimana tidak diketahui jumlah pasti nilai pengulangannya.
```
let angka = 1;
while(angka<=10){
  console.log(angka);
  angka++;
}
```
- **Do WHile**
Perulangan terjadi lebih dulu sebelum mengecek kondisi
```
let keinginan = '3';
do {
  console.log('Aku Bingung');
  keinginan--;
}while(keinginan>5)
```

## FUNCTION
Sebuah blok kode yang diketikan sekali dan dapat digunakan berkali - kali.

Penulisan Function sebagai berikut
```
let hewan = function(){
  return 'Mereka adalah Hewan'
}
```

Mengetahui Parameter dan Argument pada Function

```
let persegi = function(){
  return 5*10
}
console.log (persegi(2, 7))
```
**Parameter** adalah syarat input yang harus dimasukkan ke dalam suatu fungsi
**Argument** adalah nilai yang dimasukkan kedalam fungsi, penulisan argument dituliskan bersamaan fungsi

**Default Parameter**
Memberikan nilai awal, agar saat pemanggilan function tanpa argument tidak terjadi error
```
function perkenalan(nama = 'Meilyana'){
  return `Hallo ${nama}`
}
console.log(perkenalan('Intan')) //output : 'Hallo Intan'
console.log(perkenalan()) // output : 'Hallo Meilyana'
```

**Function Helper**
Menggunakan function yang sudah dibuat pada function lain
```
function mutipleBy (number){
  return number * (9/15)
}
function getNumber (celcius){
  return mutipleBy (celcius) + 32
}
 getNumber(15) // 59
 ```

 **Arrow Function**
 Cara lain menuliskan function ini adalah fitur baru dari ES6

 contoh :
```
hello = () => {
  return "Hello World"
}
```
  
**Function Scope**
Variabel didalam function tidak bisa diakses dari luar
```
function hewan(){
  let kucing = "betina"
}
```

## DATA TYPE JavaScript
Data Type yang tersedia di javascript digunakan untuk membangun data struktur. JavaScript adalah bahasa Dynamic.

### JavaScript Type
  Primitive Data Type (Pengambilan data berdasarkan value/nilai pada data)
  ```
  let angka = 2;
  let hewan = "kucing";
  ```
  Non Primitive Data Type (Pengambilan data berdasarkan objek variabel)
  ```
  let manusia = {
    nama = "meilyana";
    kelas = 307
  };
  ```
  **JavaScript Math Object**
  Object dengan properties dan method yang melibatkan operasi matematika
  ```
  const angka = 25;
  console.log(Math.PI);
  console.log(Math.random())
  ```

  ## DOM (Document Object Model)
  Program yang dapat merubah struktur, style, dan content pada document. DOM bukan bagian dari JavaScript dan DOM adalah sebuah WEB API

  **Mencari Halaman HTML**
```
// halaman HTML
<body>
<div id="header">
</div>
<div class="container"></div>
</body>

//halaman JavaScript
let header = document.getElementById("header");
console.log(header);

let container = document.getElementByClass("container")
console.log(container));
```

**DOM EVENTS**
Interaksi yang terjadi pada website
- click = membuat element dapat di click
- submit = membuat element dapat menangkap isi data
- scroll = membuat element dapat di gulung 
```
let angka = document.getElementById("data angka")

angka.addEventListener("click", function(){
  alert(input.value)
})
```
