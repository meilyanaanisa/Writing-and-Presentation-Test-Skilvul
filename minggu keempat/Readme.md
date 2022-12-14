# Rangkuman Minggu Keempat Skilvul

## Fetch Asynchronous 

Proses pengambilan data melalui rest-api.

Proses request
> clien server > server > database

Hasil respond
> data > server > web

Hasil data respond dalam bentuk Json (JavaScript Object Notation).
Json memiliki ciri khas di setiap properti memiliki tanda petik.

Contohnya seperti ini
![Bentuk Json!](json.png "Contoh Json")

Agar tampilan rapih seperti diatas maka harus menginstall ekstension **Json Formater** pada web browser.

- object promise yang sudah disediakan oleh javascript yaitu Fetch.

- Dua cara menangkap fetch
- .then .catch
- async await

- menangkap fetch dengan then catch
```
fetch("link") 
.then(result => {
console.log(result);
return result.json()
})
.then(result => {
console.log(result)
})
.catch(err => {
console.log(err)
})
```

- Fetch menggunakan async await
```
let getDataDigimon = async () => {
let response = await fetch("link")
let result = await respond.json ()
console.log(result);
}

getDataDigimon()
```

- harus selalu menambahkan syntax script di html
```
<script src ="script.js"  defer ></script>
```
- menampilkan data dengan DOM JavaScript.

apabila data dalam bentuk array, maka harus di looping dahulu.
```
let containerDigimon = document.getElementById("list-digimon")

let getDataDigimon = async () => {
  let response = await fetch ("link")
  let digimons = await response.json ()

  digimons.forEach (item =>{
      containerDigimon.innerHTML +=
      `
      <div>
      ${item.nama}
      </div>
      `
  })
}
```

## Responsive Web Design

Responsive web design (RWD) digunakan untuk agar website kita dapat diakses oleh banyak device tanpa mengurangi atau mengubah konten didalamya.

- Chrome Dev Tools
Menggunakan tools bawaan dari browser agar memudahkan proses development website.

- Akses Chrome Dev Tools
![Cara Akses!](inspect.avif "CLI")

- Add Viewport in HTML
```
<meta name="viewport" content="width=device-width, initial-scale=1.0">
```

- Menambahkan Max-Width
Terutama tampilan gambar agar tetep utuh dan menyesuaikan lebar device.

- Jenis Media Query

    - Min-Width, Minimum Lebar.
    - Max-Width, Maksimum Lebar.

- Dua Cara Menggunakan Media Query

    - Membuat file css yang berbeda.
    - Menggabung file css untuk setting styling berbagai device.

- Breakpoint
Perubahan yang terjadi pada tampilan saat berganti device atau ukuran width

- Contoh breakpoint dapat ditulis seperti ini
```
@media screen and (min-width: 500px) and (max-width: 700px) {
body {
  background-color: grey 
  }
 }
```
- Complex Breakpoint Media Query
Menginginkan tampilan web pada ukuran tertentu pada sebuah range ukuran device.

- Important Notes
Tidak aturan baku dalam penggunaan RWD, namun apabila melihat sebuah web tidak bisa diakses atau sulit dilihat maka sudah saatnya menggunakan media query.

## Git & Github Lanjutan
Tools yang digunakan oleh programer dan sebagai Version Control System, dimana mencatat perubahan pada file(Termasuk Code yang dibuat dan siapa yang mengubahnya).

- Kenapa harus menggunakan Git dan Github
Kita sebagai seorang programer tidak akan bisa pernah bekerja sendirian, kita pasti akan bekerja dalam tim. Tujuan besarnya yaitu kamu bisa berkolabrasi mengerjakan proyek yang sama tanpa harus repot copy paste folder aplikasi yang terupdate.
Tidak perlu menunggu rekan dalam satu tim menyelesaikan suatu program terlebih dahulu. Kita bisa mengerjakan secara bersamaan.

- Git Status
Mengetahui file yang sedang bekerja.
- Git add
Menguabh status untracked file dan unmodified menjadi modified.
- Git Commit
Melakukan save perubahan pada version control
> git commit -m "pesan"
- Git Log
melihat catatan log dari revisi - revisi sebuah visual control.
    - Melihat log dari berbagai sisi.
        
        1. Berdasarkan nomor version/commit.
        2. Melihat log file tertentu.
        3. Melihat log berdasarkan author.
- Git Checkout
Membatalkan perubahan pada file sudah staged namun belum commited.
- Git Branch
Membuat sebuah percabangan didalam repo akun github. Untuk menghindari conflict kita tidak boleh mengerjakan satu project di satu branch yang sama.
- Delete Branch
Menghapus Branch (Cabang)
- Git Merge
Menyatukan cabang fitur yang telah kita buat ke cabang master/utama.
```
# memulai perubahan baru
git checkout -b new-feature master

# edit beberapa file
git add <file>
git commit -m "start a feature"

# edit beberapa file
git add <file>
git commit -m "finish a feature"

# menggabungkan cabang new-feature
git checkout master
git merge new-feature
git branch -d new-feature
```

- Cloning, menduplikat dan menyimpan file repo ke local storage
> git clone https://github.com/meilyanaanisa/Writing-and-Presentation-Test-Skilvul.git

- Pull Request

Membuat pull requet untuk mendapatkan feedback atau perubahan yang dibuat. Pull Request di review terlebih dahulu hingga akhirnya disetujui untuk digabungkan (merge).

Apabila membuat pull request bersamaan dengan ringkasan tentang isi perubahan. Kita bisa menambahkan gambar, link dan tabel untuk membantu menyampaikan isi informasi.

## Bootstrap 5
Membuat sebuah web responsive menjadi lebih mudah dengan bootstrap.

- Penggunaan Bootstrap
Membuat file HTML dan memasukkan syntax dibawah didalam tag head. 
```
<meta name="viewport">
```
- Komponen utama bootstrap

Memasukkan Bootstrap css di dalam tag head
```
	https://cdn.jsdelivr.net/npm/bootstrap@5.2.2/dist/css/bootstrap.min.css
```
    
Memasukkan Bootstrap JavaScript di dalam tag script pada tag body
```
	https://cdn.jsdelivr.net/npm/bootstrap@5.2.2/dist/js/bootstrap.bundle.min.js
```

- Komponen bootstrap sebagian besar dibangun dengan base-modifier nomenclature. Dengan mengelompokkan beberapa properti kelas dasar seperti .btn
contoh : .btn-primary atau btn-success

- Penggunaan theme color pada bootstrap dapat menggunakan keyword sebagai berikut :
```
$theme-colors: (
"primary":    $primary,
"secondary":  $secondary,
"success":    $success,
"info":       $info,
"warning":    $warning,
"danger":     $danger,
"light":      $light,
"dark":       $dark
);
```

- Kapan kita menggunakan bootstrap
    
    - Menggunakan bootstrap sendiri saat membuat website sederhana tanpa memerluka load lama.

- Layout pada bootstrap

    - Breakpoints adalah salah satu cara dilakukan membuat design responsive dengan mengontrol tata letak disesuaikan dengan ukuran perangkat tertentu.

        - Ukuran breakpoint ada lima yaitu : sm, md, xl dan xxl.
        - Setiap breakpoint dipilih untuk menampung container yang lebarnya adalah 12 sehingga tersusun rapi. Breakpoint mewakili ukuran perangkat umum

- Container, blok dasar atau pembungkus bootstrap yang terdiri dari contain, pad dan align yang menyelaraskan konten website dalam perangkat tertentu.
Terdapat 3 container pada bootstrap :

    - .container, lebar maksimum pada setiap breakpoint responsive
    - .container-{breakpoint}, lebar 100% sampai dengan breakpoint yang ditentukan.
    - .container-fluid, menerapkan 100% ukuran dari breakpoint

- Grid System, memiliki 12 kolom default
- Grid System menggunakan container, baris dan kolom untuk menata dan menyelaraskan konten, yang dibangun menggunakan flexbox dan itu sudah responsive.

- Penggunaan grid system
```
  <div class="container text-center">
  <div class="row">
   <div class="col">
     Column
   </div>
   <div class="col">
     Column
   </div>
   <div class="col">
     Column
   </div>
  </div>
  </div>
```

- Grid system bootstrap :

    - .col-lg digunakan untuk mengatur grid pada ukuran monitor besar.
    - .col-md digunakan untuk mengatur grid pada ukuran monitor medium.
    - .col-sm digunakan untuk mengatur grid pada ukuran monitor tablet.
    - .col-xs digunakan untuk mengatur grid pada ukuran monitor handphone

