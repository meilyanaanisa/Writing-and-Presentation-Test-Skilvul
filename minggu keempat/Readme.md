# Rangkuman Minggu Keempat Skilvul
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

