# 3. ๋ชฝ๊ณ DB ๊ธฐ๋ณธ

---

๐ ๊ฐ์: ์ธํ๋ฐ - [[NoSQL DB (๋ชฝ๊ณ DB/mongodb) ๊ธฐ๋ณธ๋ถํฐ ํ์ด์ฌ/๋ฐ์ดํฐ๋ถ์ ํ์ฉ๊น์ง!]](https://www.inflearn.com/course/nosql-%ED%8C%8C%EC%9D%B4%EC%8D%AC-%EB%AA%BD%EA%B3%A0db-%EC%9E%94%EC%9E%AC%EB%AF%B8%EC%BD%94%EB%94%A9/dashboard)

๐ ๋ฐ์ ์: ๋ธ์ฐ์ (2021.03.20)

---

# 3.1 MongoDB ๋ค๋ค๋ณด๊ธฐ - robo 3T ์ค์น

## Robomongo ์ค์น

- [https://robomongo.org/download](https://robomongo.org/download)์์ Robo 3T ๋ค์ด๋ก๋ ํ ์ค์น
- MongoDB ์คํ

```bash
# Windows
net start MongoDB
net stop MongoDB
```

- Connect

*AWS ์ฌ์ฉํ  ๊ฒฝ์ฐ์๋ ip์ฃผ์ ์๋ ฅํ์ฌ Connect

---

# 3.2 MongoDB ๋ค๋ค๋ณด๊ธฐ - Database์ Collection ๋ง๋ค๊ธฐ

## Create Database

- server name ์ฐํด๋ฆญ โ Create Database โ Database ์ด๋ฆ ์๋ ฅ

## Delete Database

- database name ์ฐํด๋ฆญ โ Drop Database

## Create Collection

- database name ์ฐํด๋ฆญ โ Create Collection โ Collection ์ด๋ฆ ์๋ ฅ

## Delete Collection

- collection name ์ฐํด๋ฆญ โ Drop Collection

## Insert Document

- collection name ์ฐํด๋ฆญ โ Insert Document โ Json ํํ์ ๋ฐ์ดํฐ ์๋ ฅ โ Save

    ![3%20%E1%84%86%E1%85%A9%E1%86%BC%E1%84%80%E1%85%A9DB%20%E1%84%80%E1%85%B5%E1%84%87%E1%85%A9%E1%86%AB%20f928bf0deac445e9888de9d29957f545/Untitled.png](https://s3.us-west-2.amazonaws.com/secure.notion-static.com/1d558495-4803-4ac6-ae99-eb0fe0f8752f/Untitled.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=AKIAT73L2G45O3KS52Y5%2F20210319%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20210319T181031Z&X-Amz-Expires=86400&X-Amz-Signature=eceace326c907f412898739aebf9cd2f41ca9be1a40c46545b5c3a2966eaa420&X-Amz-SignedHeaders=host&response-content-disposition=filename%20%3D%22Untitled.png%22)

- collection name ์ฐํด๋ฆญ โ View Documents
- ์ธ๋ฑ์ค ์๋ ์์ฑ

    ![3%20%E1%84%86%E1%85%A9%E1%86%BC%E1%84%80%E1%85%A9DB%20%E1%84%80%E1%85%B5%E1%84%87%E1%85%A9%E1%86%AB%20f928bf0deac445e9888de9d29957f545/Untitled%201.png](https://s3.us-west-2.amazonaws.com/secure.notion-static.com/6453a786-f8b8-453c-a59e-e6b9cddcd8b6/Untitled.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=AKIAT73L2G45O3KS52Y5%2F20210319%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20210319T181100Z&X-Amz-Expires=86400&X-Amz-Signature=90399c106e0f5f55d81872471aa18b1fef895417fd7db0d5c137d4e4fa3afaf0&X-Amz-SignedHeaders=host&response-content-disposition=filename%20%3D%22Untitled.png%22)

## Delete Document

- document name ์ฐํด๋ฆญ โ Delete Document
- collection name ์ฐํด๋ฆญ โ Remove All Documents

---

# 3.3 SQL๊ณผ MongoDB ๊ฐ๋จ ๋น๊ต - MongoDB shell ์ตํ๊ธฐ

- server name ์ฐํด๋ฆญ โ Open Shell

```bash
# ์ ์ฒด ๋ฐ์ดํฐ๋ฒ ์ด์ค ์ด๋
$ show dbs

# ๋ฐ์ดํฐ๋ฒ ์ด์ค ์ ํ
$ use {DB ์ด๋ฆ}
์) use mydb

# ์ ํ๋ ๋ฐ์ดํฐ๋ฒ ์ด์ค์ ์ฝ๋ ์ ์ด๋
$ show collections

# collection ๋ด ๋ฐ์ดํฐ ์ฐพ๋ ๋ช๋ น์ด
# find ์ธ์๊ฐ ์์ผ๋ฉด ์ ์ฒด document ๊ฒ์
$ db.{collection ์ด๋ฆ}.find()

# db์ ํต๊ณ ์ ๋ณด ํ์ธ (db, collections, ์ ์ฅ ๊ณต๊ฐ ๋ฑ)
$ db.stats()

# collection ์์ฑ
$ db.createCollection("{collection ์ด๋ฆ}")
# capped:true ์ต์ด ์ ํ๋ ํฌ๊ธฐ๋ก ์์ฑ๋ ๊ณต๊ฐ์์๋ง ๋ฐ์ดํฐ๋ฅผ ์ ์ฅํ๋ ์ค์  
# ๋ฃ์ ๋๋ง๋ค ์ ์ฅ ๊ณต๊ฐ ์ถ๊ฐ x ->๊ณ ์ฑ๋ฅ
# ์ผ์  ์๊ฐ ์ ์ฅํ๋ ๋ก๊ทธ์ ์ ํฉ
$ db.createCollection("{collection ์ด๋ฆ}", {capped:true, size:10000})

# capped ์ฌ๋ถ ์์๋ณด๊ธฐ
$ db.{collection ์ด๋ฆ}.isCapped()

# collection ์ญ์ 
$ db.{collection ์ด๋ฆ}.drop()

# collection์ ํต๊ฒ ์ ๋ณด ํ์ธ
$ db.{collection ์ด๋ฆ}.stats()

# collection ์ด๋ฆ ๋ณ๊ฒฝ
$ db.{collection ์ด๋ฆ}.renameCollection("{๋ณ๊ฒฝํ  collection ์ด๋ฆ}")
```

---

# 3.4 ๋ชฝ๊ณ DB ๋ฐ์ดํฐ ์๋ ฅ - SQL๊ณผ ๋น๊ต

## CRUD ๋ช๋ น

- Create (Insert)
- Read (Search)
- Update
- Delete (Drop)

## MongoDB collection ์์ฑ/๋ณ๊ฒฝ

![3%20%E1%84%86%E1%85%A9%E1%86%BC%E1%84%80%E1%85%A9DB%20%E1%84%80%E1%85%B5%E1%84%87%E1%85%A9%E1%86%AB%20f928bf0deac445e9888de9d29957f545/Untitled%202.png](https://s3.us-west-2.amazonaws.com/secure.notion-static.com/91e21471-96c3-4101-95b8-b3adb2a543de/Untitled.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=AKIAT73L2G45O3KS52Y5%2F20210319%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20210319T181128Z&X-Amz-Expires=86400&X-Amz-Signature=f3ba21404575cac82bc2c9274266e6c3b71eac0ec63e6d1ff397c36ccc3f8334&X-Amz-SignedHeaders=host&response-content-disposition=filename%20%3D%22Untitled.png%22)

- **collection ์์ฑ**
    - Schema ๋ฐ๋ก ์ค์ ํ  ํ์ x
    - PRIMARY KEY ์ค์  ํ์ x โ document๋ง๋ค id๊ฐ ์๋ ์์ฑ๋์ด PK ์ญํ ์ ํ๋ค
- **collection ๊ตฌ์กฐ ๋ณ๊ฒฝ**
    - SQL: ALTER TABLE
    - MongoDB: ๊ฐ๊ฐ์ Document๊ฐ ๊ฐ๊ฐ์ ๊ตฌ์กฐ๋ฅผ ๊ฐ๋๋ค
- **๊ธฐ์กด Document์ ์ปฌ๋ผ๊ณผ ์ปฌ๋ผ๊ฐ ์ถ๊ฐ**
    - SQL: ALTER TABLE people ADD COLUMN join_date DATETiME
    - MongoDB: db.people.updateMany({ }, { $set: {join_date: new Date() } })
- **๊ธฐ์กด Document์ ์ปฌ๋ผ๊ณผ ์ปฌ๋ผ๊ฐ ์ญ์ **
    - SQL: ALTER TABLE people DROP COLUMN join_date
    - MongoDB: db.people.updateMany({ }, { $unset: { "join_date": "" } })

## Document ์๋ ฅ

- `InsertOne`: ํ ๊ฐ์ document ์์ฑ
- `InsertMany`: list of document ์์ฑ

```bash
# document ์๋ ฅ ๋ฌธ๋ฒ
$ db.users.insertOne(
	{
		name: "sue"
		age: 26,
		status: "pending"
	}
)
$ db.articles.insertMany(
   [
     { subject: "coffee", author: "xyz", views: 50 },
     { subject: "Coffee Shopping", author: "efg", views: 5 },
     { subject: "Baking a cake", author: "abc", views: 90  },
     { subject: "baking", author: "xyz", views: 100 },
     { subject: "Cafรฉ Con Leche", author: "abc", views: 200 },
     { subject: "ะกััะฝะธะบะธ", author: "jkl", views: 80 },
     { subject: "coffee and cream", author: "efg", views: 10 },
     { subject: "Cafe con Leche", author: "xyz", views: 10 },
     { subject: "coffees", author: "xyz", views: 10 },
     { subject: "coffee1", author: "xyz", views: 10 }
   ]
)
```

![3%20%E1%84%86%E1%85%A9%E1%86%BC%E1%84%80%E1%85%A9DB%20%E1%84%80%E1%85%B5%E1%84%87%E1%85%A9%E1%86%AB%20f928bf0deac445e9888de9d29957f545/Untitled%203.png](https://s3.us-west-2.amazonaws.com/secure.notion-static.com/aecc9788-2f42-4469-a111-d24642c9e78e/Untitled.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=AKIAT73L2G45O3KS52Y5%2F20210319%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20210319T181149Z&X-Amz-Expires=86400&X-Amz-Signature=ec816c80dc538062111013bbaa586f9d2818804b4cd3f994954b6698f66634fa&X-Amz-SignedHeaders=host&response-content-disposition=filename%20%3D%22Untitled.png%22)

---

# 3.5 ๋ชฝ๊ณ DB ๋ฐ์ดํฐ ์ฝ๊ธฐ - SQL๊ณผ ๋น๊ต1

## Document ์ฝ๊ธฐ(๊ฒ์)

- `findOne`: ๋งค์นญ๋๋ ํ ๊ฐ์ document ๊ฒ์
- `find`: ๋งค์นญ๋๋ list of document ๊ฒ์

```bash
# document ์ฝ๊ธฐ(๊ฒ์) ๋ฌธ๋ฒ
$ db.users.find(
	{ age: { $gt: 18 } },
	{ name: 1, address: 1 }
).limit(5)

# SELECT * FROM people
$ db.people.find() 

# SELECT _id, user_id, status FROM people
$ db.people.find({ }, { user_id: 1, status: 1 })

# SELECT user_id, status FROM people
$ db.people.find({ },{ user_id: 1, status: 1, _id: 0 })

# SELECT * FROM people WHERE status = "A"
$ db.people.find({ status: "A" })

# SELECT * FROM people WHERE status = "A" AND age = 50
$ db.people.find({ status: "A", age: 50 })

# SELECT * FROM people WHERE status = "A" OR age = 50
$ db.people.find({ $or: [ { status: "A" } , { age: 50 } ] })
```

---

# 3.6 ๋ชฝ๊ณ DB ๋ฐ์ดํฐ ์ฝ๊ธฐ - SQL๊ณผ ๋น๊ต2

## ๋น๊ต ๋ฌธ๋ฒ

- `$eq`: =, equal to
- `$gt`: >, greater than
- `$gte`: โฅ, geater than or equal to
- `$in`: in
- `$lt`: <, less than
- `$lte`: โค, less than or equal to
- `$ne`: โ , not equal to
- `$nin`: not in

```bash
# SELECT * FROM people WHERE age > 25
$ db.people.find({ age: { $gt: 25 } })

# SELECT * FROM people WHERE age < 25
$ db.people.find({ age: { $lt: 25 } })

# SELECT * FROM people WHERE age > 25 AND age <= 50
$ db.people.find({ age: { $gt: 25, $lte: 50 } })

# SELECT * FROM people WHERE age = 5 or age = 15
$ db.people.find( { age: { $in: [ 5, 15 ] } } ))

# SELECT * FROM people WHERE user_id like "%bc%"
$ db.people.find( { user_id: /bc/ } )
$ db.people.find( { user_id: { $regex: /bc/ } } )

# SELECT * FROM people WHERE user_id like "bc%"
$ db.people.find( { user_id: /^bc/ } )
$ db.people.find( { user_id: { $regex: /^bc/ } } )

# SELECT * FROM people WHERE status = "A" ORDER BY user_id ASC                                           
$ db.people.find( { status: "A" } ).sort( { user_id: 1 } ) 

# SELECT * FROM people WHERE status = "A" ORDER BY user_id DESC
$ db.people.find( { status: "A" } ).sort( { user_id: -1 } )

# SELECT COUNT(*) FROM people
$ db.people.count()
$ db.people.find().count()
                                                 
# SELECT COUNT(user_id) FROM people
$ db.people.count( { user_id: { $exists: true } } )
$ db.people.find( { user_id: { $exists: true } } ).count()
                                                  
# SELECT COUNT(*) FROM people WHERE age > 30
$ db.people.count( { age: { $gt: 30 } } )
$ db.people.find( { age: { $gt: 30 } } ).count()
                                                  
# SELECT DISTINCT(status) FROM people
db.people.distinct( "status" )

# SELECT * FROM people LIMIT 1
db.people.findOne()
db.people.find().limit(1)
```

---

# 3.7 ๋ชฝ๊ณ DB ๋ฐ์ดํฐ ์์  - SQL๊ณผ ๋น๊ต

## Document ์์ 

- `updateOne`: ๋งค์นญ๋๋ ํ ๊ฐ์ document ์๋ฐ์ดํธ
- `updateMany`: ๋งค์นญ๋๋ list of document ์๋ฐ์ดํธ
- `$set`: field ๊ฐ ์ค์ 
- `$inc`: field ๊ฐ ์ฆ๊ฐ ๋๋ ๊ฐ์
    - ์) $inc: { age: 2 } โ age ๊ฐ ๋ณธ๋ ๊ฐ์์ 2 ์ฆ๊ฐ

```bash
# Document ์์  ๋ฌธ๋ฒ
$ db.users.updateMany(
	{ age: { $lt: 18 } },
	{ $set: { status: "reject" } }
)

# UPDATE people SET status = "C" WHERE age > 25
$ db.people.updateMany( { age: { $gt: 25 } }, { $set: { status: "C" } } )

$ db.people.updateOne( { age: { $gt: 25 } }, { $set: { status: "C" } } )

# UPDATE people SET age = age + 3 WHERE status = "A"
$ db.people.updateMany( { status: "A" } , { $inc: { age: 3 } } )
```

---

# 3.8 ๋ชฝ๊ณ DB ๋ฐ์ดํฐ ์ญ์  - SQL๊ณผ ๋น๊ต

## Document ์ญ์ 

- `removeOne`: ๋งค์นญ๋๋ ํ๊ฐ์ document ์ญ์ 
- `removeMany`: ๋งค์นญ๋๋ list of document ์ญ์ 

```bash
# Document ์ญ์  ๋ฌธ๋ฒ
$ db.users.deleteMany(
	{ status: "reject" }
)

# DELETE FROM people WHERE status = "D"
$ db.people.deleteMany( { status: "D" } )

# DELETE FROM people
$ db.people.deleteMany({})
```

---

# [์ฐธ๊ณ ] ํ์ด์ฌ ๋ผ์ด๋ธ๋ฌ๋ฆฌ ์ฌ์ฉ๋ฒ 1, 2