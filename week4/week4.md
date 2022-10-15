# Async Await
---
* Async Await
<p>Async/await adalah fitur yang hadir sejak ES2017. Fitur ini mempermudah kita dalam menangani proses asynchronous.Async/Await merupakan sebuah syntax khusus yang digunakan untuk menangani Promise agar penulisan code lebih efisien dan rapih.</p>

```html
async function asyncNonton() {
  try {
    let result = await nonton("jalan")
    console.log(result);
  } catch (error) {
    console.log(error)
  }
}
asyncNonton()
```
# Fetch
* Fetch
<p>merupakan cara baru dalam melakukan network request yang memanfaatkan sebuah Promise dalam penggunaanya. Karen Fetch mengembalikan sebuah Promise maka respon handling yang digunakan adalah then jika promise mengembalikan resolve dan catch jika promise mengembalikan nilai reject</p>

```html
fetch("https://digimon-api.vercel.app/api/digimon")
.then(result => result.json())
.then(result => {
  console.log(result)
})
```

# Git dan Github Lanjutan

<p>Git Commands </p>

* GIT checkout : untuk berpindah branch atau membuat branch baru
* GIT reset : untuk merubah ke commit sebelumnya
* GIT log : untuk melihat history perubahan yang telah dilakukan pada suatu project
* GIT Revert : untuk membatalkan perubahan yang terjadi di git tanpa menghapus git commit sebelumnya
* Fork yaitu sama halnya dengan clone namun langsung mengambil file dari repository
* Clone yaitu menggandakan atau mengcopy sebuah project

# Responsive web design
<p>responsive web design adalah bertujuan membuat desain website kita dapat diakses dalam device apapun</p>
<p>Chrome Dev Tools merupakan tools pada google chrome yang digunakan sebagai tools Responsive Web Design. Untuk mengakses nya dengan cara ctrl + shift + j</p>
<p>Menggunakan responsive web design , pada HTML harus ditambahkan viewport pada bagian head agar tampilan website dapat menyesuaikan untuk berbagai device</p>
<p>membuat suatu gambar pada halaman website agar menjadi responsive dapat dilakukan dengan menambahkan atribut Max - width = 100%</p>
<p>salah satu cara untuk mengatur sebuah website agar bisa terdiri dari beberapa jenis menggunakan Media Query</p>

```css
contoh media query
@media screen and (max-width: 300px)
```

<p>Cara mengkondisikan media query : Memisahkan beberapa file css sesuai dengan tampilan device yang ingin dibuat dan Menggabungkan semua styling css device menjadi satu
</p>

<p>Breakpoint yaitu istilah saat terjadi perubahan ukuran pada suatu website ketika berganti device</p>
<p>3 jenis breakpoint yaitu desktop, tablet, dan mobile phone</p>
<p>Penggunaan breakpoint pada media query dapat dilakukan dengan membuat range ukuran sesuai dengan tampilan device yang ingin dibuat

```css
@media screen and (min-width: 300px) and (max-width: 600px) {
body {
  background-color: white 
  }
 }
```
<p><b>Flexbox</b> bertujuan untuk membuat website yang lebih efisien dalam mengatur, menata dan item pada dalam sebuah wadah bahkan ketika ukurannya tidak diketahui dan/atau dinamis (dengan menggunakan kata "flex")</p>

<p>Properti flexbox :</p>

* Flex direction : menetapkan sumbu utama item, sehingga menentukan arah item fleksibel ditempatkan di wadah fleksibel. 
- Row : Kiri ke kanan
- Row-Reverse : Kanan ke kiri
- Column : Atas ke bawah
- Column-Reverse : Bawah ke atas

* Flex Wrap : Secara default, semua item pada flexbox akan mencoba berada dalam satu baris. Maka dengan flex wrap kita dapat mengubah hal tersebut.
- nowrap : semua item flex akan berada dalam satu baris
- wrap : item fkex akan membungkus ke beberapa baris, dari atas ke bawah.
- wrap-reverse :item flex akan membungkus beberapa baris dari bawah ke atas.

* Flex flow : cara singkat untuk properti flex-direction dan flex-wrap, yang bersama-sama menentukan sumbu utama dan sumbu silang container flex. Nilai default adalah baris nowrap.

* Align items
  
<p>grid adalah sistem tata letak berbasis dua dimensi</p>
<p>2 jenis grtid yaitu grid container dan grid item.</p>

# Bootstrap
<p>Bootstrap adalah framework opensource yang berfungsi membuat suatu responsive website</p>
<p>Komponen utama bootstrap adalah bootstrap.js dan bootstrap.css</p>
<p>Konfigurasi bootstrap dengan cara Membuat tag boostrap di head. Cara memanggil css bootstrap dengan menggunakan href lalu mengganti link href css lokal dengan link boostrap online.</p>
<p>contoh penggunaan content boostsrap:</p>

* JS : bootstrap.bundle.js, bootstrap.min.js, dll
* CSS : bootstrap.min.css, bootstrap-grid.css, dll

<p>Komponen Bootstrap sebagian besar dibangun dengan base-modifier nomenclature.Contohnya mengelompokkan beberapa properti kedalam kelas dasar seperti .btn, seperti .btn-primary or .btn-success.</p>

<p>Penggunaan theme color pada boostrap dapat menggunakan keyword berikut :</p>

```html
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
<p>Boostrap digunakan ketika membuat website sederhana dan tidak memerlukan load lama</p>
<p>layout pada bootstrap :</p>

* Breakpoints merupakan suatu cara yang dilakukan untuk membuat desain responsif dengan mengontrol kapan tata letak yang disesuaikan dengan ukuran perangkat tertentu.
* Breakpoints pada bootstrap ada 5 yaitu sm, md, lg, xl dan xxl.
* Setiap breakpoint dipilih untuk menampung container yang lebarnya 12 dengan sehingga tersusun rapi. Breakpoint juga mewakili subset ukuran perangkat umum dan dimensi area pandang.

<p>Container adalah blok dasar atau pembungkus boostrap yang terdiri dari contain, pad dan align yang menyelaraskan konten website dalam perangkat atau area pandang tertentu.</p>

<p>Tiga container pada bootstrap:</p>

* .container, yang menerapkan lebar maksimum pada setiap breakpoint responsif
* .container-{breakpoint}, menerapkan lebar 100% sampai dengan breakpoint yang ditentukan.
* .container-fluid, menerapkan 100% ukurannya dari breakpoints

<p>Grid System pada bootstrap yang terdiri dari 12 kolom default.</p>
<p>Grid system pada bootstrap menggunakan container,baris dan kolom untuk menata dan menyelaraskan konten,yang dibangun menggunakan flexbox dan itu sudah responsive.</p>

<p>penggunan grid system</p>

```html
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
<p>Grid system bootstrap :</p>

* .col-lg digunakan untuk mengatur grid pada ukuran monitor yang besar
* .col-md digunakan pada monitor komputer berukuran sedang
* .col-sm digunakan untuk mengatur monitor pada tablet
* .col-xs digunakan untuk mengatur monitor pada handphone
