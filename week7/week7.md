# Sequelize

## Build Restful API Using Sequelize

#### Get All to do

Untuk mendapatkan list todo kita bisa menggunakan method findAll().

```js
const router = require('express').Router;
const Todos = require('../models').Todo;

router.get('/', async (req, res) => {
	try {
		const todos = await Todos.findAll();
		res.send({
			status: 'success',
			msg: 'success get all to do',
			data: todos,
		});
	} catch (error) {
		res.status(500).send({ status: 'fail', msg: error.message });
	}
});

module.exports = router;
```

#### Get To do By Id

Untuk mendapatkan list todo kita bisa menggunakan method findOne().

```js
const router = require('express').Router;
const Todos = require('../models').Todo;

router.get('/:id', async (req, res) => {
	const { id } = req.params;
	try {
		const todos = await Todos.findOne({ id: Number(id) });
		res.send({
			status: 'success',
			msg: 'success get to do by id',
			data: todos,
		});
	} catch (error) {
		res.status(500).send({ status: 'fail', msg: error.message });
	}
});

module.exports = router;
```

#### Add to do

Untuk mendapatkan list todo kita bisa menggunakan method create().

```js
const router = require('express').Router;
const Todos = require('../models').Todo;

router.post('/', async (req, res) => {
	const newTodo = req.body;
	try {
		await Todos.create(newTodo);
		res.send({ status: 'success', msg: 'success create to do' });
	} catch (error) {
		res.status(500).send({ status: 'fail', msg: error.message });
	}
});

module.exports = router;
```

#### Update To do

Untuk mendapatkan list todo kita bisa menggunakan method update().

```js
const router = require('express').Router;
const Todos = require('../models').Todo;

router.put('/:id', async (req, res) => {
	const { id } = req.params;
	const newTodo = req.body;
	try {
		await Todos.update(newTodo, { where: { id } });
		res.send({ status: 'success', msg: 'success update to do' });
	} catch (error) {
		res.status(500).send({ status: 'fail', msg: error.message });
	}
});

module.exports = router;
```

#### Delete Todo

Untuk mendapatkan list todo kita bisa menggunakan method destroy().

```js
const router = require('express').Router;
const Todos = require('../models').Todo;

router.put('/:id', async (req, res) => {
	const { id } = req.params;
	try {
		await Todos.destroy({
			where: {
				id,
			},
		});
		res.send({ status: 'success', msg: 'success delete to do' });
	} catch (error) {
		res.status(500).send({ status: 'fail', msg: error.message });
	}
});

module.exports = router;
```

# MongoDB

MongoDB adalah salah satu database noSQL yang bersifat open source dan cukup populer digunakan. di monbodb , collection sebagai tabel dan dokumen sebagai record. Data yang digunakan pada mongodb memiliki format json sehingga lebih mudah dalam pengoperasiannya.

Contoh data pada mongodb

```
	{
		"_id": ObjectId("AAA"),
		"nama": "Dino",
		"email": "dino@gmail.com",
		"password": "1234"
	},
```

#### CRUD pada mongodb

- Open CMD / GitBash / Powershell
- ketik monngosh

```
mongosh
```

- pilih database , ketik show databases

```
show databases
```

- use untuk menggunakan database

```
use <nama _database>
```

- Membuat Collection dan Dokumen

```
show collection
```

- jika belum ada , bisa membuat dengan

```
db.createCollection("users")
```

- menambah data pada collection tadi

```
db.users.insertOne
(
  {
  nama: "dinoo",
  email:"dino@gmail.com",
  password: "12345"
  }
)
```

- menampilkan data

```
db.users.find()
```

- Mengubah Data

```
db.users.updateOne
(
  {
    email: "zuhriagusdino@gmail.com"
  },
  {
    $set: {password: "123123"
    }
  }
)
```

- Menghapus data

```
db.users.deleteOne
(
  {
    email: "zuhriagusidno@gmail.com"
  }
)
```

#### MongoDB relationship

- One to one
  Pada kasus one-to-one relationship biasa digunakan sistem embedding. Contohnya satu user hanya bisa memiliki 1 \_id.

- One to Many
  Pada kasus one-to-many relationship biasa digunakan sistem referencing. Contohnya jika 1 user bisa memiliki banyak pesanan.

- Many to many
  Pada kasus many-to-many relationship biasanya juga menggunakan sistem referencing. Contohnya jika seorang user bisa memiliki banyak lagu yang disukai dan sebuah lagu bisa disukai oleh banyak user.

# Mongoose

### RESTful API with mongoose

```js
const express = require('express');
const app = express();
const mongoose = require('mongoose');

app.use(express.json());

mongoose
	.connect('mongodb://localhost:27017/users')
	.then(() => console.log('database connected'))
	.catch((error) => console.log(error.message));

const Schema = mongoose.Schema;

const users = new Schema({
	name: String,
	email: String,
});

const User = mongoose.model('user', users);

app.get('/', async (req, res) => {
	try {
		const data = await User.find();
		res.send({ status: 'success', msg: 'success get all to do', data });
	} catch (error) {
		res.status(500).send({ status: 'fail', msg: error.message });
	}
});

app.get('/:id', async (req, res) => {
	const { id } = req.params;

	try {
		const data = await User.findOne({ _id: id });
		res.send({ status: 'success', msg: 'success get todo by id', data });
	} catch (error) {
		res.status(500).send({ status: 'fail', msg: error.message });
	}
});

app.post('/', async (req, res) => {
	const { name, email } = req.body;

	try {
		const user = new User({ name, email });
		const data = await user.save();
		res.status(201).send({ status: 'success', msg: 'success create user' });
	} catch (error) {
		res.status(500).send({ status: 'fail', msg: error.message });
	}
});

app.put('/:id', async (req, res) => {
	const { id } = req.params;
	try {
		await User.findOneAndUpdate({ _id: id }, { ...req.body });
		res.send({ status: 'success', msg: 'success update user' });
	} catch (error) {
		res.status(500).send({ status: 'fail', msg: error.message });
	}
});

app.delete('/:id', async (req, res) => {
	const { id } = req.params;
	try {
		await User.deleteOne({ _id: id });
		res.send({ status: 'success', msg: 'success delete user' });
	} catch (error) {
		res.status(500).send({ status: 'fail', msg: error.message });
	}
});

app.listen(3000, () => {
	console.log('server running on http://localhost:3000');
});
```

#### Membuat API Spesification

- Get All User
  - Method = GET
  - Endpoint = /
  - Respone status code = 200
  - Response :

```js
{
	"status": "string",
	"msg": "string",
	"data": [
		{
			"_id": "ObjectId",
			"name": "string",
			"email": "string"
		}
	]
}
```

- Get User By Id
  - Method = GET
  - Endpoint = /{id}
  - Respone status code = 200
  - Response :

```js
{
	"status": "string",
	"msg": "string",
	"data": {
		"_id": "ObjectId",
		"name": "string",
		"email": "string"
	}
}
```

- Add user
  - Method = POST
  - Endpoint = /
  - Body

```js
{
	"name": "string",
	"email": "string"
}
```

- Response status code : 201
- Response :

```js
{
	"status": "string",
	"msg": "string"
}
```

- Update User
  - Method = PUT
  - Endpoint = /{id}
  - Body

```js
{
	"name": "string",
	"email": "string"
}
```

- Response status code : 200
- Response :

```js
{
	"status": "string",
	"msg": "string"
}
```

- Delete user
  - Method = DELETE
  - Endpoint = /{id}
  - Response status code : 200
  - Response :

```js
{
	"status": "string",
	"msg": "string"
}
```

# Docker

#### Container

Container berfungsi sebagai tempat menyimpan seluruh dependensi yang diperlukan oleh sebuah software tertentu agar dapat berjalan. Container ini menghindarkan user dari masalah kompatibilitas yang mungkin akan terjadi pada beberapa sistem yang berbeda.

#### Cara penggunaan docker

- docker pull
  Perintah untuk download image dari docker hub

```
docker pull chuanwen/cowsay
```

- docker images
  Perintah untuk menampilkan list images yang sudah terdownload

```
docker images
```

- docker run
  Perintah untuk menjalankan container

```
docker run
```

- docker ps
  Perintah untuk menampilkan list container yang sedang berjalan

```
docker ps
```
