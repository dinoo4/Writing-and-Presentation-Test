# Javascript Function

---

#### Function

<p>Fungsi di dalam Javascript adalah sebuah objek. Karena memiliki properti dan juga method.</p>

#### Cara membuat Function di Javascript

- Cara biasa

```html
function namaFungsi(){ console.log("Hello World!"); }
```

- Membuat fungsi dengan ekspresi

```html
let namaFungsi = function(){ console.log("Hello World!"); }
```

- Arrow Function

```html
var namaFungsi = () => { console.log("Hello World!"); } // atau seperti ini
(jika isi fungsi hanya satu baris): var namaFungsi = () => console.log("Hello
World!");
```

#### Data Type

<p>Dalam pemrograman, tipe data merupakan konsep penting.
Untuk dapat beroperasi pada variabel, penting untuk mengetahui sesuatu tentang tipenya.</p>

#### String

<p>Objek String digunakan untuk mewakili dan memanipulasi urutan karakter.</p>

<p>String berguna untuk menampung data yang dapat direpresentasikan dalam bentuk teks. Beberapa operasi yang paling sering digunakan pada string adalah memeriksa panjangnya, membangun dan menggabungkannya menggunakan operator string + dan +=, memeriksa keberadaan atau lokasi substring dengan metode indexOf(), atau mengekstrak substring dengan substring () metode.</p>

```html
Membuat string let text = "John Doe"
```

#### Number

<p>Number adalah objek pembungkus primitif yang digunakan untuk mewakili dan memanipulasi angka seperti 37 atau -9,25.
Konstruktor Number berisi konstanta dan metode untuk bekerja dengan angka. Nilai dari tipe lain dapat dikonversi ke angka menggunakan fungsi Number().</p>

```html
let x = 3.14; // A number with decimals let y = 3; // A number without decimals
```

#### Math

<p>Math adalah objek bawaan yang memiliki properti dan metode untuk konstanta dan fungsi matematika. Ini bukan objek fungsi.</p>

<p>8 properti objek math</p>

- Math.E // Bilangan Euler
- Math.LN2 // Log 2
- Math.LN10 // Log 10
- Math.LOG2E // Log E di Basis 2
- Math.LOG10E // Log E di Basis 10
- Math.PI // Pi
- Math.SQRT1_2 // Akar Kuadrat dari 0.5
- Math.SQRT2 // Akar Kuadrat dari 2

<p>beberapa method di objek math </p>

- Math.abs(x) // Digunakan untuk mengubah angka x yang bernilai negatif menjadi positif.
- Math.pow(x, y) // Digunakan untuk menghitung hasil dari x pangkat y.
- Math.sqrt(x) // Digunakan untuk menghitung akar kuadrat dari x.
- Math.cbrt(x) // Digunakan untuk menghitung akar pangkat 3 dari x.
- Math.round(x) // Digunakan untuk membulatkan angka desimal x menjadi bilangan bulat. Pembulatan ke atas bila angka di belakang koma lebih besar atau sama dengan 5, dan pembulatan ke bawah jika angka di belakang koma kurang dari 5.
- Math.floor(x) // Digunakan untuk membulatkan angka desimal x ke bawah.
- Math.ceil(x) // Digunakan untuk membulatkan angka desimal x ke atas.
- Math.random() // Digunakan untuk menampilkan angka secara acak antara 0 hingga 1 (0 termasuk. 1 tidak).
- Math.max(x, y, z, ..., n) // Digunakan untuk mencari angka terbesar di antara parameter x, y, z, ..., n.
- Math.min(x, y, z, ..., n) // Digunakan untuk mencari angka terkecil di antara parameter x, y, z, ..., n.

#### Type data primitive & non primitive

<p>Primitif disimpan berdasarkan nilai sedangkan Non-Primitif (Objek) disimpan berdasarkan referensi.</p>

##### Primitive

- String
- Numbers
- Boolean
- Undefined
- null

##### Non primitive

- Object
- Arrays
- Function

# Javascript DOM

<p>DOM merupakan singkatan dari Document Object Model, Artinya dokumen (HTML) yang dimodelkan dalam sebuah objek.</p>
<p>Objek dari dokumen ini menyediakan sekumpulan fungsi dan atribut/data yang bisa kita manfaatkan dalam membuat program Javascript. Inilah yang disebut API (Application Programming Interface).</p>
<p>Objek DOM di javascript bernama document. Objek ini berisi segala hal yang kita butuhkan untuk memanipulasi HTML.</p>

<p>Objek ini berisi kumpulan fungsi dan atribut berupa objek dari elemen HTML yang bisa digambarkan dalam bentuk pohon seperti ini</p>

![Struktur](D:\writing-presentation\week\week2/dom.jpg)

#### Mengakses element tertentu dengan DOM

- getElementById() fungsi untuk memilih elemen berdasarkan atribut id.
- getElementByName() fungsi untuk memilih elemen berdasarkan atribut name.
- getElementByClassName() fungsi untuk memilih elemen berdasarkan atribut class.
- getElementByTagName() fungsi untuk memilih elemen berdasarkan nama tag.
- querySelector() fungsi untuk memilih elemen berdasarkan query.
- querySelectorAll() fungsi untuk memilih elemen berdasarkan query.

#### Parent element

<p>Untuk mendapatkan parent node secara spesifik kita menggunakan property parentNode</p>

```html
let parent = node.parentNode;
```

#### Child element

<p>Untuk mendapatkan child element secara spesifik kita menggunakan property firstChild

```html
let firstChild = parentElement.firstChild;
```

jika parent element tidak memiliki child element , child element mengembalikan null.

</p>

<p>Untuk mendapatkan last child element secara spesifik kita menggunakan property lastChild

```html
let lastChild = parentElement.lastChild;
```

</p>

<p>Untuk mendapatkan live nodeList dari child element secara spesifik kita menggunakan childNodes

```html
let children = parentElement.childNodes;
```

</p>

#### Sibling

<p>Untuk mendapatkan next sibling element kita menggunakan nextElementSibling

```html
let nextSibling = currentNode.nextElementSibling;
```

</p>

<p>Untuk mendapatkan previous sibling element kita menggunakan previousElementSibling

```html
let current = document.querySelector('.current'); let prevSibling =
currentNode.previousElementSibling;
```

</p>

#### Create element

<p> createElement ini adalah sebuah fungsi dari javascript untuk membuat element HTML baru. Dan sering digunakan bersamaan dengan createTextNode.</p>

```html
syntax : document.createElement(type)
```

#### Create text node

<p>createTextNode artinya Membuat sebuah text atau kalimat</p>

```html
syntax document.createTextNode(text)
```

#### append dan appendChild

<p>Digunakan untuk menambahkan element baik berupa object node maupun DOM String, sedangkan appendChild dapat mengembalikan value berupa Node Object yang ditambahkan</p>

#### innerHTML

<p>innerHTML adalah sebuah atribut di dalam (objek) elemen HTML yang berisi string HTML.
Dengan innerHTML, kita dapat menampilkan output ke elemen yang lebih spesifik.</p>

```html
return the innerHTML property : element.innerHTML set the innerHTML property :
element.innerHTML = text
```

#### innerText

<p>innerText fungsinya adalah untuk menentukan dan mengembalikan nilai konten dari suatu element dalam bentuk text atau string</p>

```html
Return the text content of an element or node: element.innerText Set the text
content of an element or node: element.innerText = text
```

#### textContent

<p>textContent property menyetel atau mengembalikan konten teks dari node yang ditentukan, dan semua turunannya.</p>

```html
Return the text content of a node: element.textContent Set the text content of a
node: element.textContent = text
```

#### remove

<p>kegunaan nya menghapus element atau node dari dokumen</p>

```html
element.remove() atau node.remove()
```

#### attribute

<p>attribute mengembalikan collection attribute dalam suatu element</p>

```html
node.attributes
```

#### getAttribute

<p>Metode getAttribute() mengembalikan nilai atribut elemen.</p>

```html
element.getAttribute(name)
```

#### setAttribute

<p>Metode setAttribute() menetapkan nilai baru ke atribut. Jika atribut tidak ada, itu dibuat terlebih dahulu.</p>

```html
element.setAttribute(name, value)
```

#### hasAttribute

<p>Metode hasAttribute() mengembalikan nilai true jika atribut ada, jika tidak false.</p>

```html
element.hasAttribute(name)
```

#### className

<p>className Property menetapkan atau mengembalikan element class attribute.</p>

```html
Return the className property: HTMLElementObject.className Set the className
property: HTMLElementObject.className = class
```

#### classList

<p>Properti classList mengembalikan nama kelas CSS dari suatu elemen.
</p>

```html
element.classList classListAdd() const list = element.classList;
list.add("myStyle"); classListRemove() const list = element.classList;
list.remove("myStyle"); classListToggle() onst list = element.classList;
list.toggle("myStyle");
```

#### style

<p>style mengembalikan value dari element style attribute</p>

```html
Change the color of "myH1": document.getElementById("myH1").style.color = "red";
```

#### style.background

<p>style.background mengatur atau mengembalikan hingga 8 background property yang terpisah , dalam bentuk singkatan</p>

- background-color
- background-image
- background-repeat
- background-attachment
- background-position
- background-size
- background-origin
- background-clip

```html
return the backgroung property : object.style.background set the background
property: object.style.background = "color image repeat attachment position size
origin clip|initial|inherit"
```

#### style.removedProperty

<p>menghapus secara spesifik CSS Property dari CSS Declaration block</p>

```html
object.removeProperty(propertyname)
```

#### Event

<p>Event adalah kejadian yang terjadi di halaman web. Kejadian yang dimaksud di sini seperti aktivitas yang dikerjakan pada halaman web.</p>

#### Cara Handel event di javascript

- Menggunakan Attribute , HTML memiliki atribut event untuk menentukan fungsi yang akan dijalankan saat event terjadi.

```html
<button onclick="hello()">Klik</button>

onclick adalah atribut HTML untuk menentukan aksi saat event klik pada sebuah
elemen. Atribut ini bisa diisi dengan nama fungsi atau ekspresi javascript.
hello() adalah fungsi yang akan dijalankan saat terjadi event
```

- Method addEventListener(), merupakan method yang terdapat pada object DOM. Object ini mewakili sebuah elemen HTML di Javascript.

```html
button.addEventListener('click', function(e){ // kode untuk dijalankan });
button adalam dom object click adalah nama event function adalah fungsi yang
akan dijalankan ketika event terjadi
```

#### prevenDefault

<p>preventDefault adalah sebuah method yang berfungsi untuk mencegah terjadinya event bawaan dari sebuah DOM, misalnya tag "a href" jika kita klik, maka halaman browser akan melakukan reload, atau sebuah form jika kita klik tombol submit maka akan melakukan reload pula.</p>

```html
event.preventDefault()
```

#### reset

<p>Metode untuk me-reset nilai semua unsur bentuk (sesuai dengan satu kali klik efek tombol Reset).</p>

```html
formObject.reset()
```
