# Unix Command Line

---

<p> <strong>Shell</strong>, program yang digunakan untuk berkomunikasi atau memerintah sistem </p>
<p> <strong>CLI</strong> atau command line interface, jenis shell yang berbasis teks </p>
<p> <strong>Terminal emulator</strong>, aplikasi untuk mengakses cli </p>
<p> <strong>File system</strong>, Kegunaan nya mengatur bagaimana data disimpan didalam sebuah system </p>
<img src="file-system-structure.png">

<p> <strong>Command</strong></p>
<ol>
<li>head, tail, cat untuk isi file diawal, akhir, dan keseluruhan</li>
<li>touch untuk membuat file</li>
<li>mkdir untuk membuat directory</li>
<li>cp untuk menyalin file, cp -R untuk menyalin directory</li>
<li>mv untuk memindahkan file, mv-R untuk memindahkan directory</li>
<li>rm untuk menghapus file, rm-R atau rm-d untuk menghapus directory</li>
</ol>

# Git dan Github

---

<p> <strong>Git</strong> adalah aplikasi yang dapat melacak setiap perubahan yang terjadi pada suatu folder atau file.</p>
<p> <strong> Github </strong> merupakan manajemen project, sistem versioning code, sekaligus platform jaringan sosial bagi para developer seluruh dunia</p>
<p><strong>Kenapa wajib mengguanakan git&github</strong>, karena programmer tidak akan bekerja sendirian , pasti membutuhkan bantuan tim. hampir semua perusahaan berbasis teknologi telah menggunakan kedua platform ini untuk pekerjaan karyawannya</p>

#### Setup awal git

<p>git config --global user.name "Zuhri Agusdino"</p>
<p>git config --global user.email zuhriagusdino92@gmail.com</p>
<p>cek apakah instalasi berhasil, git --version</p>
<p>cek apakah setup berhasil, git config --list</p>
<p><strong>Repository</strong>, direktori proyek yang kita buat</p>
<p>membuat repository, git init namarepository</p>
<p>mengecek apakah ada perubahan pada git, git status</p>
<p>menghubungkan remote repository dengan project lokal yang telah dibuat direktorinya, git remote</p>
<p>menambah file baru atau menambahkan file yang telah diubah, git add</p>
<p>mengecek apakah ada perubahan pada git, git status</p>
<p>menyimpan perubahan pada git, git commit -m "commit massage"</p>
<p>mengirimkan perubahan file ke remote repository, git push -u origin master</p>
<p>membuat branch baru, git branch -b (nama branch)</p>
<p>berpindah branch, git checkout</p>
<p>menggabungkan branch cabang ke branch master, git merge atau git merge origin/(nama branch)</p>

# HTML

---

<p><strong>HTML</strong> adalah singkatan dari hypertext markup language, digunakan untuk menampilkan konten pada browser</p>
<p>Tools pendukung dalam menggunakan html adalah text editor dan browser. contoh text editor adalah visual studio code dan sublime text.</p>

### Teks HTML sederhana

```html
<!DOCTYPE html>
<html lang="en">
	<head>
		<title>Html Sederhana</title>
	</head>
	<body>
		<p>membuat teks html sederhana</p>
	</body>
</html>
```

#### Tag HTML

<p> adalah sebuah penanda awalan dari sebuah elemen di HTML. Tag dibuat dengan kurung siku (<..>) lalu didalam nya berisi nama tag dan kadang juga ditambahkan dengan atribut. Atribut adalah properti dari elemen HTML, contohnya id,class,name.</p>

- Tag <'html'> untuk memulai dokumen html
- Tag <'head'> untuk membuat bagian head
- Tag <'title'> untuk membuat judul
- Tag <'body'> untuk membuat bagian body
- Tag <'h1'> sampai <'h6'> untuk membuat heading pada artikel
- Tag <'p'> untuk membuat paragraf
- Tag <'!-- --'> untuk memberikan komentar

#### Elemen semantik HTML

<p>adalah elemen-elemen yang menyatakan makna atau tujuan dari elemen tersebut.Salah satu keuntungan menggunakan elemen semantik adalah dokumen HTML kita akan mudah dibaca</p>

#### Contoh Tag semantik HTML

- Tag <'footer'> untuk membuat elemen footer atau bagian kaki dari web
- Tag <'article'> untuk membuat elemen article
- Tag <'aside'> untuk membuat elemen bagian samping
- Tag <'header'> untuk membuat kepala kop dari web
- Tag <'main'> untuk membuat elemen utama
- Tag <'nav'> untuk membuat navigasi
- Tag <'section'> untuk membuat bagian artikel

#### Deploy HTML

<p>Deploy adalah sebuah proses untuk menyebarkan aplikasi yang sudah kita kerjakan supaya bisa digunakan oleh orang-orang. Jika aplikasi kita HTML atau Web App kita perlu mendeploy ke server. Dalam mendeploy HTML kita menggunakan tools bernama <b>Netlify</b></p>

# CSS

---

#### CSS atau Cascading stlye sheets

<p>berfungsi untuk menjelaskan dan menata tampilan elemen yang tertulis pada bahasa markup, salah satunya adalah HTML.Jadi css digunakan untuk mendesain halaman website dengan mengubah warna, menggunakan font custom, editing text format, mengatur tata letak.</p>

#### Menyisipkan CSS kedalam HTML

- Menggunakan CSS inline, CSS inline adalah sebuah kode CSS yang kita sematkan pada element apa pun di dalam body HTML, langsung menggunakan atribut style

```
<button style="color: red">Masuk</button>
<button style="color: blue; border: 2px solid green">
  Daftar
</button>
```

- Menggunakan CSS internal, CSS internal adalah CSS yang diletakkan pada bagian head suatu halaman HTML.

```
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>CSS Internal</title>

  <style>
    a {
      padding: 8px 16px;
      border-radius: 4px;
      color: white;
      background-color: #8d68e8;
      text-decoration: none;
      font-family: Arial, Helvetica, sans-serif;
    }
  </style>
</head>
<body>
  <a href="#">Beranda</a>
  <a href="#">Tentang Kami</a>
</body>
</html>
```

- Menggunakan CSS eksternal, Yang dimaksud eksternal adalah kita membuat file tersendiri yang berekstensi css. Kemudian file tersebut kita hubungkan ke dalam halaman HTML menggunakan tag link

```
Kita bisa menambahkan tag <link> pada bagian <head> yang mengarah kepada file style/app.css seperti berikut

<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>CSS Eksternal</title>

  <link rel="stylesheet" href="./style/app.css">
</head>
<body>
  <a href="#">Beranda</a>
  <a href="#">Tentang Kami</a>
</body>
</html>

Sedangkan isi file CSS

a {
  padding: 8px 16px;
  border-radius: 4px;
  color: white;
  text-decoration: none;
  font-family: Arial, Helvetica, sans-serif;
}

a:first-of-type {
  background-color: #1fc296;
}

a:last-of-type {
  background-color: #d45a5a;
}
```

#### Sintaks dasar CSS

<p>Sintaks CSS terdiri dari tiga bagian:(selector),(property),(value).Selektor biasanya adalah elemen atau tag HTML yang akan didefinisikan, properti adalah atribut yang akan diganti dengan nilai tertentu. Properti dan nilai dipisahkan dengan tanda titik dua (:) dan keduanya diapit oleh tanda kurung kurawal ({).</p>

```
Sintaks css

p{
	color: red;
}


- p adalah selector berupa elemen html yang akan diubah
- color adalah prroperti berupa bagian yang akan diubah. contoh diatas adalah kita akan mengubah warna dari teks yang ada didalam elemen p
- red adalah value atau nilai berupa warna merah
```

#### Flexbox

<p>Flexbox adalah cara untuk mengatur layout. Flexbox direkomendasikan karena penggunaannya yang mudah dan didukung oleh kebanyakan browser. Flexbox terdiri dari 1 parent atau container dan bisa beberapa child</p>
<p>Flex direction digunakan untuk mengatur letak child, sedangkan flex warp mengatur tata letak child pada 1 line</p>
<p>Flex flow yaitu digunakan sebagai shortcut untuk set up flex-direction dan flex-wrap secara bersamaan.sedangkan Order digunakan untuk ordering item yang ingin diatur posisinya</p>

- Justify - content digunakan untuk mengatur tata letak antar item child secara horizontal
- Align - content digunakan untuk mengatur tata letak antar item child secara vertikal atau cross axis
- Flex-grow digunakan untuk mengatur size suatu item child pada flexbox
- Flex-shrink digunakan untuk memperkecil size suatu item child secara relatif terhadap item child lainnya
- flex-basis digunakan untuk mengatur width setiap item child

# Algoritma

---

#### Algoritma

<p><b>Algoritma</b> adalah deskripsi berupa step-step yang dibutuhkan untuk menyelesaikan suatu masalah, untuk menyelesaikan suatu masalah, kita harus mempunyai <b>data struktur</b>. data inilah yang akan kita gunakan untuk menyelesaikan suatu masalah dengan menggunakan algoritma..</p>

#### Manfaat menggunakan algoritma

- membantu menyelesaikan suatu masalah dengan logika dan sistematis
- Mempermudah pembuatan program yang dapat menyelesaikan masalah tertentu.
- Membantu menyederhanakan suatu program yang rumit dan juga besar.

#### Kualitas wajib algoritma

- Input dan output harus didefinisikan terlebih dahulu dengan tepat
- Setiap step harus benar-benar clear dan tidak ambigu
- Algoritma seharusnya tidak mengandung suatu code pada bahasa pemograman tertentu. Algoritma harus dibuat agar dapat digunakan dalam bahasa pemograman apapun

#### Contoh Algoritma sederhana

```
input 1 = 5
input 2 = 7
output = input 1 + input 2
print ("Result", output)
```

#### Pseudocode

<p> Pseudocode adalah menuliskan algoritma sebelum kita implementasikan ke bahasa pemograman tertentu. </p>

<p> Menulis pseudocode </p>

- Huruf kapital digunakan untuk menulis perintah
- 1 statement hanya terdiri dari 1 baris
- Harus bersifat spesifik dan simple
- Menggunakan indentasi

<p> Contoh pseudocode </p>

```
STORE "width" with any number
STORE "height" with any nummber
STORE "area" without any value

CALCULATE "width" times "height"
SET "area" value with calculation result
DISPLAY "area"
```

#### Contoh pseudocode

- Procedural : cara berpikir secara runtun. Artinya serangkaian perintah yang berurutan.\
- Conditional : digunakan saat dibutuhkan percabangan kasus. Komputer akan melakukan suatu tindakan jika suatu kondisi terpenuhi.
- Looping : Jika membutuhkan perulangan dalam kasus tertentu, kita bisa menggunakan Looping.
- Recursive : pola pikir dalam algoritma yang memanggil method/function didalam sebuah function.
