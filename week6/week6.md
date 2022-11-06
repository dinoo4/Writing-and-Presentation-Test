# MySQL

#### Database

merupakan kumpulan informasi yang disimpan di dalam komputer secara sistematik dan saling berelasi. Lalu, informasi di dalam database akan diolah yang kemudian menjadi sebuah data dan akan dikelolah oleh sistem.

#### Relasional Database

Relasi database merupakan hubungan antara beberapa tabel yang ada di dalam sebuah database. Relasi antar tabel dihubungkan antara primary key dan foreign key. Primary key merupakan atribut unik dan mewakili satu entitas, sedangkan foreign key merupakan atribut yang melengkapi relasi dan menunjukan hubungan antara tabel induk dan anak.

#### Tipe data MySQL

Tipe data string

```sql

Tipe data string

CHAR(size), karakter memiliki panjang dari 0 - 255
VARCHAR(size), karakter memiliki panjang dari 0 - 65535
TINYTEXT, karakter memiliki panjang maksimum 255
TEXT(size), karakter memiliki panjang sebesar 65,535
ENUM(val1, val2, val3, ...), bernilai pemilihan kata

Tipe data number

TINYINT(size), nilai berukuran dari 0 - 255
BOOLEAN, nilai bernilai TRUE atau FALSE
MEDIUMINT(size), nilai berukuran dari 0 - 16777215
INTEGER(size) / INT(size), nilai berukuran dari 0 - 4294967295
BIGINT(size), nilai berukuran 0 - 18446744073709551615
FLOAT(size, d), nilai memberikan nilai desimal
DOUBLE PRECISION(size, d), nilai memberikan nilai desimal

Tipe data date&time

DATE, tipe data yang berformat YYYY-MM-DD
DATETIME(fsp), tipe data yang berformat YYYY-MM-DD hh:mm:ss
TIMESTAMP(fsp), tipe data yang berformat YYYY-MM-DD hh:mm:ss
TIME(fsp), tipe data yang berformat dari -838:59:59 sampai 838:59:59
YEAR, tipe data yang berformat YYYY
```

#### Manipulasi Query

```sql

mendapatkan data
  SELECT * FROM nama_tabel;

menambahkan data
  INSERT INTO nama_tabel (nama_entitas_1, nama_entitas_2, nama_entitas_n+1) VALUES(value_1, value_2, values_n+1);

mengupdate data
  UPDATE nama_tabel SET nama_entitas1=value_1, nama_entitas_n+1=value_n+1 WHERE id_value=values_id;

menghapus data
  DELETE FROM nama_tabel WHERE id_value=values_id;
```

# MySQL Lanjutan

#### Manipulasi tipe data yang sering dilakukan

```sql
menggabungkan yang berelasi
Inner join ( Semua row akan diambil selama kolom cocok dengan kondisi yang ditentukan.)
  SELECT * FROM pengguna INNER JOIN asal ON pengguna.id_asal = asal.pengguna.id_asal

Left join ( Semua record dari tabel sisi kiri akan dipilih. Apabila kondisi tidak cocok, maka akan bernilai NULL )
  SELECT * FROM pengguna LEFT JOIN asal ON pengguna.id_asal = asal.pengguna.id_asal

Right join ( Semua record dari tabel sisi kanan akan dipilih. Apabila kondisi tidak cocok, maka akan bernilai NULL )
  SELECT * FROM pengguna RIGHT JOIN asal ON pengguna.id_asal = asal.pengguna.id_asal


fungsi aggregate

mendapatkan nilai terbesar = MAX
 SELECT MAX(id_user) FROM pengguna;

mendapatkan nilai terkecil = MIN
 SELECT MIN(id_user) FROM pengguna;

menghitung jumlah baris = COUNT
 SELECT COUNT(id_user) FROM pengguna;

menambahkan seluruh nilai = SUM
 SELECT MAX(sub_total) as total FROM pesanan;

menghitung nilai rata rata = AVG
 SELECT AVG(sub_total) as total FROM pesanan;

menggabungkan hasil dari select = UNION
 SELECT * FROM data1
 UNION
 SELECT * FROM data2

mengelompokan baris yang memiliki nilai sama ke baris ringaksan = GROUP BY
 SELECT * FROM pengguna GROUP BY id_user;

pengganti where apabilang berjalan dengan GROUP BY = HAVING
 SELECT * FROM pengguna GROUP BY id_user HAVING id_user > 10;
```

#### Relasional antar tabel

- ONE to MANY
  Relasi ini menghubungkan 1 tabel dengan banyak tabel yang akan dituju

- ONE to ONE
  Relasi ini menghubungkan 1 tabel dengan 1 tabel yang dituju.

- MANY to MANY
  Relasi ini menghubungkan banyak tabel dengan banyak tabel yang dituju.

PRIMARY KEY (Menjadi acuan utama dari setiap tabel) dan FOREIGN KEY (Merupakan PRIMARY KEY yang telah dihubungkan dengan tabel yang dituju).

```sql
menggabungkan 2 tabel di sql
   SELECT * FROM pengguna INNER JOIN asal ON pengguna.id_asal = asal.pengguna.id_asal

JOIN merupakan langkah yang digunakan untuk menghubungkan atau berelasi antar tabel.
```

# Authentication & Authorization

Perbedaan Authenticaion , Authorization , Encryption

- metode terhadap seorang pengguna mengkonfirmasi sebagai pengguna valid yang dapat mengakses sebuah akun atau informasi tertentu

- proses penentuan terhadap pengguna yang terautentikasi tersebut diizinkan atau ditolak untuk melakukan satu atau lebih akses terhadap sistem.

- proses pengubahan data menjadi format yang tidak bisa dibaca terkecuali apabila ada seseorang yang memiliki kunci untuk mengubah kembali data yang terenkripsi

#### Mencoba authentication dah authorization

materi minggu ini mencoba dengan menggunakan jsobwebtoken

```js
const express = require('express');
const app = express();

const PORT = 3000;

app.use(express.json());

const users = [
	{ id: 1, email: 'dino@gmail.com', password: 'dino' },
	{ id: 2, email: 'zuhri@gmail.com', password: 'zuhri' },
];

const KEY = 'agsdsdgsda';

// Proses autentikasi
app.get('/auth', (req, res) => {
	const { email, password } = req.body;
	const userData = users.find(
		(item) => email === item.email && password === item.password
	);
	const token = jwt.sign(
		{
			id: userData.id,
		},
		KEY
	);

	if (userData) {
		res.json({
			message: 'success login',
			token,
		});
	} else {
		res.status(401).json({
			message: 'email or password are incorrect',
		});
	}
});

// Proses autorisasi
app.get('/films/:id/subscribe', (req, res) => {
	try {
		const auth = req.headers.authorization;
		const token = auth.split(' ')[1];

		jwt.verify(token, KEY);

		res.json({
			message: 'subscribe moviess',
		});
	} catch (error) {
		res.status(500).json({
			message: error.message,
		});
	}
});

app.listen(PORT, () => {
	console.log('server running on port ', PORT);
});
```

# Sequilize

Sequelize adalah Node.js promise-based ORM untuk MySQL, PostgreSQL, SQLite, MSSQL dan database SQL lainnya. Sequelize berfungsi untuk bekerja dengan database dan relasi-relasi di dalamnya.

cara instalasi sequilize di nodejs

```cli
yarn add sequelize
```

```cli
yarn add sequelize-cli
```

```cli
npx sequelize-cli init
```
