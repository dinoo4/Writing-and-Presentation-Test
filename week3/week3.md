# Array

---

<p>Array merupakan pengorganisasian data dan tempat penyimpanan data. Array adalah tipe data list order yang dapat menyimpan tipe data apapun dialamnya seperti string, number, boolean dan lainnya</p>

```html
contoh array

let newArray = ['string', 5, true];
console.log(newArray);
```
<p>Cara mengakses array pada javascript dihitung mulai dari index ke - 0</p>

```html
let newArray = ['string', 5, true];
console.log(newArray[2]); // output = true
```

<p> Const in Array , tidak dapat update data tetapi dapat melakukan update konten nilai didalam array</p>

```html
const hewan = ['kucing', 'anjing', 'gajah'];
hewan[2] = ['burung'];

console.log(hewan)// output : ['kucing','anjing','burung']
```
<p> Array memiliki 5 properti yang sering digunakan : </p>

* constructor
* length
* index
* input
* prototype

<p>.length untuk mengembalikan nilai dari jumlah panjang data suatu array</p>

```html
let hewan = ['kucing', 'anjing', 'gajah'];
console.log(hewan.length) // output 3
```

<p>Array method atau built in methods</p>

* .push untuk menambahkan item array pada urutan terakhir

```html
let hewan = ['kucing', 'anjing', 'gajah'];
hewan.push('biawak')
console.log(hewan) // output: ['kucing', 'anjing', 'gajah', 'biawak'];
```

* .pop untuk menghapus item array index terakhir

```html
let hewan = ['kucing', 'anjing', 'gajah', 'biawak'];
hewan.pop()
console.log(hewan) // output: ['kucing', 'anjing', 'gajah'];
```

* .shift untuk menghapus item array pada index pertama

```html
let hewan = ['kucing', 'anjing', 'gajah', 'biawak'];
hewan.shift()
console.log(hewan) // output: ['anjing', 'gajah', 'biawak'];
```

* .unshift untuk menambahkan array pada index pertama
```html
let hewan = ['anjing', 'gajah', 'biawak'];
hewan.unshift('kucing)
console.log(hewan) // output: ['kucing', 'anjing', 'gajah', 'biawak'];
```

* .sort untuk mengurutkan array secara ascending atau descending

```html
const angka = [1,5,3,4,2];
angka.sort();
console.log(angka) // output : [1,2,3,4,5]
```

<p>Looping pada array. Caranya dengan menggunakan .map dan .forEach</p>

* .map = melakukan perulangan dengan membuat array baru

```html
let angka = [1,2,3,4,5];

let doubled = angka.map(num => {
    return num * 2;
});
console.log(doubled);
```

* .forEach = melakukan looping pada setiap elemen array

```html
const hewan = ['kucing', 'anjing', 'gajah'];
hewan.forEach(element => {
console.log(element);
});
```
# Multidimensional Array

<p> sepertinya bisa disebut array of array</p>

* contoh multidimensional array

```html
let pakaian = [
  ['Kaos', 5],
  ['Jaket', 3],
  ['Celana', 3],
  ['Topi', 2],
]

console.log(pakaian)
```

* mengakses multidimensional array

```html
let pakaian = [
  ['Kaos', 5],
  ['Jaket', 3],
  ['Celana', 3],
  ['Topi', 2],
]

console.log(pakaian[1][0])
```

* menggunakan built in method pada multidimensional array

```html

let pakaian = [
  ['Kaos', 5],
  ['Jaket', 3],
  ['Celana', 3],
  ['Topi', 2],
]

pakaian.push(['kalung', 2])
console.log(pakaian)
```

* menggunakan map di multidimensional array

```html
let pakaian = [
  ['Kaos', 5],
  ['Jaket', 3],
  ['Celana', 3],
  ['Topi', 2],
]

pakaian.map(dataPakaian => {
  let terjual = 50 - dataPakaian[1]
  dataPakaian[2] = terjual
})
console.table(pakaian)
```
* looping pada multidimensional array

```html
let pakaian = [
  ['Kaos', 5],
  ['Jaket', 3],
  ['Celana', 3],
  ['Topi', 2],
]

pakaian.forEach((baris) => {
  baris.forEach((column) => {
    console.table(column)
  })
})
```

# Javascript Object

<p>Object adalah sebuah tipe data pada variabel yg menyimpan properti dan fungsi (method). Properti adalah data lengkap dari sebuah object ,sedangkan Method adalah action dari sebuah object.</p>

* Contoh Object
```html
let orang = {
    name : 'Dino',
    age : 21,
    isVerified: true
}
```

* Cara mengakses object
```html
let orang = {
    name : 'Dino',
    age : 21,
    isVerified: true
}
console.log(orang)
```

* Cara mengakses properti pada object
```html
let orang = {
    name : 'Dino',
    age : 21,
    isVerified: true
}
console.log(orang.age)
```

* Mengupdate object
```html
let orang = {
    name : 'Dino',
    age : 21,
    isVerified: true
}
orang.age = 22
console.log(orang)
```

* Delete object properti
```html
let orang = {
    name : 'Dino',
    age : 21,
    isVerified: true
}
delete orang.age

console.log(orang)
```

* Method adalah tindakan yang dapat dilakukan pada objek.
* Console adalah global javascript object dan log adalah properti yang berupa function dari object console
* Pass by reference : mengubah data pada object melalui function dan memasukkan object sebagai parameter function
* Looping pada object
* Array of object 
* Nested Object

# Rekursif

<p>Rekursif adalah fungsi yang memanggil dirinya sendiri sampai suatu kondisi tertentu terpenuhi</p>

<p>Ciri dari rekursif</p>

* Fungsi recursive memiliki kondisi yang menyatakan kapan fungsi tersebut berhenti.
* fungsi recursive selalu memaanggil dirinya sendiri sambil mengurangi atau memecahkan data masukan setiap panggilannya.

<p>mencari nilai pangkat dengan rekursif </p>

```html
function pow(x,n) {
    if (n=1){
        return x;
    } else {
        return x * pow(x, n-1);
    }
}
console.log(pow(2,3)) // 8
```

# Web Storage

<p>Web storage adalah wadah untuk sebuah data yang digunakan untuk penyimpanan data yang terikat di browsernya</p>

<p>Jenis web storage yang umum digunakan</p>

* Local Storage
* Session storage
* IndexDB
* Cookies
* Cara menyimpan data pada web storage
```html
   let token = "asdfghjkl" //key
    localStorage.setItem("token", token);
```
* Cara mengambil token
```html
localstorage.getItem("token", token);
    console.log(localStorage.getItem('token");
```
* Cara menghapus data
```html
    localStorage.removeItem("token")
```


# Asynchronous

<p>Asynchronous adalah sebuah teknik yang menyelesaikan fungsi secara paralel, penggunaan asynchronous dapat dilakukan jika kita ingin mengambil data dari database.</p>
<p>Asynchronous dibutuhkan ketika ada proses yangg membutuhkan waktu lama. Jadi kita bisa mengerjakan proses yg lain secara paralel.</p>

* Contoh penggunaaan asynchronous
```html
function p1() {
  console.log('p1 selesai')
}
  function p2() {
  setTimeout(
    function() {
      console.log('p2 selesai')
    },2000
  )
}
function p3() {
console.log('p3 selesai')
}
p1()
p2()
p3()
```
* Callback adalah function yang menjadi argument untuk function lain dan akan dieksekusi pada poin tertentu.
```html
```html
const url = "https://rodtang-jt.com"

const alert = () => {
  console.log('Download complete!');
};
const download = (url, callback) => {
  console.log(`Downloading from ${url} ...`);
  callback();
};

download(url, alert);
```

* Promise adalah suatu object dan digunakan hanya untuk satu event dengan menyimpan hasil dari sebuah operasi asynchronous baik itu hasil yang diinginkan (resolved value) atau alasan kenapa operasi itu gagal (failure reason)
```html
 function GetUser(id) {
  return new Promise((resolve, reject) => {
  if (id !== "" && id !== undefined) {
    reesolve (id);
  } else {
    reject ("ID Harus di Isi");
      }
  });
  }
  
  GetUser( ) 
  .then((response) => {
  console.log(response);
   })
   .catch((error) => {
  console.log(error);
  });
```











