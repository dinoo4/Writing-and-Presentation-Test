# WEB SERVER & RESTFUL API

#### Web server

Web server terdiri dari 2 komponen penting yaitu software dan hardware. Di sisi hardware berfungsi untuk menyimpan web server software dan komponen file website seperti HTML, CSS, dan JS. Di sisi software terdapat HTTP server yang memahami alamat website dan HTTP.

Konsep dari web server adalah apabila ada request dari sisi client atau browser, maka file atau HTTP server akan memberikan response terhadap client. Terdiri dari 2 jenis yaitu static sites dan dynamic sites, static sites hanya request navigasi halaman oleh pengguna dan dynamic sites bisa berupa request data di dalam halaman website dengan menggunakan database.

#### Restful API

Rest yang merupakan gaya arsitektur yang memudahkan sistem untuk berkomunikasi dengan yang lainya sebagai standart sistem komputer dan website. Lalu, Restfull API merupakan konsep untuk memisahkan antar server dan klien.

Di dalam konsep Rest, implementasi antar klien dan server dapat berdiri sendiri tanpa mengetahui satu sama lain. Hal ini bermaksud segala sesuatu di sisi server dapat berubah sewaktu-waktu tanpa adanya komunikasi dengan sisi klien.

Pembuatan request di Restfull API terdapat beberapa jenis, tetapi yang paling sering digunakan adalag GET untuk mendapatkan data, POST untuk mengirim data, PUT untuk mengupdate data, dan DELETE untuk menghapus data. Juga ada path sebagai endpoint alamat url yang bisa diakses.

# Node JS

#### Fundamental NodeJS

Node JS merupakan open source dan back end JavaScript runtime environment yang berjalan di V8 engine dan mengeksekusi JavaScript di luar Web Browser. Node JS sendiri berguna untuk menjalankan script server side yang membuat website menjadi dinamis.

Node JS menggunakan konsep single thread. Namun, seakan-akan Node JS seperti menggunakan konsep multiple thread dengan cara event loop yang berarti memeriksa perintah secara terus menerus apabila ada perintah baru.

#### NodeJS untuk backend

Untuk membantu Node JS dalam menjalankan sebuah Back End diberikan beberapa module populer seperti :

- console, digunakan sebagai debug
- process, digunakan untuk menampilkan dan mengontrol process di node.js
- os, digunakan untuk memberikan informasi mengenai sistem operasi komputer
- util, digunakan untuk kebutuhan API di node js
- errors, digunakan untuk mendefinisikan error
- buffer, digunakan untuk mengakses tipe data bytes dan raw
- fs, digunakan untuk berinteraksi dengan file yang ada di luar code
- timers, digunakan untuk mengatur sebuah waktu

#### Membuat program NodeJS

NodeJS dasar :

```js
const http = require('http');

const reqHandler = (req, res) => {
	res.end('Hello World!');
};

const server = http.createServer(reqHandler);

server.listen(3001, 'localhost', (err) => {
	if (err) {
		return 'Salah';
	}

	console.log('Server berjalan di port 3001');
});
```

# Express Routing & Middleware

#### Membuat routing

Routing merupakan manajemen endpoint dari sebuah aplikasi atau website untuk melakukan request dan memberikan response oleh client. Terdapat banyak sekali method untuk mengakses routing yaitu :

- GET, mendapatkan data
- POST, mengirim data
- PUT, mengupdate data
- DELETE, menghapus data

Cara routing :

```js
app.get('/', (req, res) => {
	res.send('Hello World!');
});

app.post('/', (req, res) => {
	res.send('Berhasil ditambahkan');
});

app.put('/', (req, res) => {
	res.send('Berhasil diupdate');
});

app.delete('/', (req, res) => {
	res.send('Berhasil dihapus');
});

app.get('/siswa', (req, res) => {
	res.send('Berhasil menapatkan data siswa');
});

app.get('/siswa/:id', (req, res) => {
	res.send('Berhasil menapatkan data siswa dengan id');
});
```

#### Membuat middleware

Middleware merupakan fungsi yang terdiri dari 3 parameter yaitu req (untuk mendapatkan data), res (memberikan response), dan next (untuk melanjutkan ke route lain yang berhubungan).

Bentuk middleware :

```js
// application level middleware
const middle1 = (req, res, next) => {
	console.log('middle 1');
	next();
};

app.use(middle1);

// router level middleware
const express = require('express');
const Router = express.Router();
const middle2 = (req, res, next) => {
	console.log('middle 2');
	next();
};
Router.user(middle2);

// error handling level middleware
const express = require('express');
const Router = express.Router();
const middle3 = (err, req, res, next) => {
	console.log('middle 3');
	next();
};
Router.user(middle3);
```

# Design database with MySQL

Desain basis data
adalah serangkaian kegiatan yang bertujuan untuk meningkatkan pengembangan, implementasi, dan pemeliharaan sistem manajemen data perusahaan. Tujuan utamanya adalah untuk mencerminkan garis besar sistem database ke dalam model nyata: fisik dan logis. Perancang basis data menentukan data apa yang akan disimpan di dalam basis data, dan bagaimana objek terkait satu sama lain.

Tahapan :

- Conceptual Design, pada tahapan ini desain yang dibuat masih berbentuk konsep secara keseluruhan dan umum. Tahap ini fokus pada model data yang akan digunakan tanpa memikirkan logika-logika penyimpanan database dan pertimbangan fisik database tersebut. Output dari tahapan ini biasanya first cut ERD (Entity Relationship Diagram.

- Menerjemankah Conceptual Design menjadi Logical Design. Akan ada proses validasi model data yang ada, apakah sesuai dengan logika-logika database dan sudah sesuai secara sturktural. Pada tahapan ini juga bisa dilakukan normaliasi untuk melihat kesesuaian model data yang dalam mendukung transaksi yang ada. Beberapa konsep logika database yang digunakan dalam tahapan ini adalah:

  - Strong Entitiy Types
  - Weak Entitiy Types
  - One-to-many (1:\*) Binary Relationships Types
  - One-to-one (1:1) Binary Relationships Types
  - One-to-one (1:1) Recursive Relationships
  - Superclass/ Subclass Relationships Types
  - Many-to-many (:) Binary Relationships Types
  - Complex Relationships Types
  - Multi-valued Attributes

- Database desain adalah Physical Design. Tahap ini lebih fokus pada structural database secara detail. Penyimpanan data dan hubungan pada database akan dibuat pada tahap ini. Bukan hanya structural dan hubungan data, tapi juga memperhatikan integritas data yang akan disimpan di database tersebut. Secara langsung desain yang sudah ada akan dibuat atau bisa disebut mengkonstruksi database.
