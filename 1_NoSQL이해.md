# 1. NoSQL ์ดํด

---

๐ ๊ฐ์: ์ธํ๋ฐ - [[NoSQL DB (๋ชฝ๊ณ DB/mongodb) ๊ธฐ๋ณธ๋ถํฐ ํ์ด์ฌ/๋ฐ์ดํฐ๋ถ์ ํ์ฉ๊น์ง!]](https://www.inflearn.com/course/nosql-%ED%8C%8C%EC%9D%B4%EC%8D%AC-%EB%AA%BD%EA%B3%A0db-%EC%9E%94%EC%9E%AC%EB%AF%B8%EC%BD%94%EB%94%A9/dashboard)

๐ ๋ฐ์ ์: ๋ธ์ฐ์ (2021.03.20)

---

# 1.1 ๋น๋ฐ์ดํฐ์ NoSQL ์ดํด

## ๋น๋ฐ์ดํฐ

- ๊ธฐ์กด: ๊ด๊ณํ ๋ฐ์ดํฐ๋ฒ ์ด์ค (RDBMS)
    - SQL ์ธ์ด๋ก ์ฌ์ฉ ๊ฐ๋ฅ
    - SQL ๋ฐ์ดํฐ๋ฒ ์ด์ค
- ๋น๋ฐ์ดํฐ๋ ๊ธฐ์กด์ ๊ด๊ณํ ๋ฐ์ดํฐ๋ฒ ์ด์ค๋ก ์ฒ๋ฆฌํ๊ธฐ ์ด๋ ค์ด ๋ถ๋ถ ์กด์ฌ
- ๋น๋ฐ์ดํฐ: NoSQL ๋ฐ์ดํฐ๋ฒ ์ด์ค (Not only SQL, SQL๋ณด๋ค ์ข ๋ ๊ธฐ๋ฅ์ด ๋ง๋ค!)

## NoSQL (Not only SQL)

- SQL์ ์ ์ฅํ  ๋ฐ์ดํฐ์ ๊ท๊ฒฉ์ ๋ฏธ๋ฆฌ ๋ง๋ค์ด์ผ ํ๋ค โ ์ ์ฅํ๊ณ  ์ถ์ ๋ฐ์ดํฐ๋ฅผ ๋๋ฆฌ๊ณ  ์ถ์ ๋ ๊ท๊ฒฉ์ ์๋ก ์๋ฐ์ดํธ
- ์ด๋ฌํ RDBMS์ ํ๊ณ ๊ทน๋ณต์ ์ํด ๋ง๋ค์ด์ง ์๋ก์ด ํํ์ ๋ฐ์ดํฐ ์ ์ฅ์๊ฐ NoSQL
- ๊ณ ์ ๋ ์คํค๋ง ๋ฐ JOIN ์กด์ฌ X

### ๐กSQL vs. NoSQL

![1%20NoSQL%20%E1%84%8B%E1%85%B5%E1%84%92%E1%85%A2%20696399321788434aace237b1e9458201/Untitled.png](https://s3.us-west-2.amazonaws.com/secure.notion-static.com/5688166c-f202-43d5-bfb2-49aebc83e644/Untitled.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=AKIAT73L2G45O3KS52Y5%2F20210319%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20210319T180746Z&X-Amz-Expires=86400&X-Amz-Signature=d841f66a3c9b0a89e9b39f6c9f85233641351b83ef5949dc6a607cbdfdcaf3b9&X-Amz-SignedHeaders=host&response-content-disposition=filename%20%3D%22Untitled.png%22)

---

# 1.2 NoSQL์ ๋ํ์ ์ธ ๋ฐ์ดํฐ๋ฒ ์ด์ค mongodb ์๊ฐ

### โWhy NoSQL?

- NoSQL์ ๋น๋ฐ์ดํฐ๋ฅผ ๋ค๋ฃจ๋ ๋ฐ์ ์์ด ์ฑ๋ฅ ๋ฉด์์ ๊ฐ์ ์ด ์๋ค
- RDBS๋ read๋ฅผ ์ฃผ๋ก ํ  ๋๋ ์ฑ๋ฅ์ด ๋์์ง ์์ง๋ง, write์ ๋น์ค์ด ๋์ด๋๋ฉด ์ฑ๋ฅ์ด ์ ํ๋๊ฑฐ๋ ๋ถ์์ 
- ์ด๋น ๋ฐ์ดํฐ๊ฐ ์์ญ๋ง๊ฐ์ฉ ์์ด๋ ์๋น์ค๊ฐ ๋ง์์ง๋ ๊ฒฝ์ฐ(SNS, ์จ๋ผ์ธ ์๋น์ค ๋ฑ) NoSQL์ด ์ ๋ฆฌ
- NoSQL ๋ฐ์ดํฐ๋ฒ ์ด์ค๋ ๊ฐ๊ธฐ ๋ฐ์ดํฐ๋ฒ ์ด์ค๋ฅผ ๋ค๋ฃจ๋ ์ธํฐํ์ด์ค๊ฐ ๋ค๋ฅด๋ค
    - Key/Value Store
    - Wide Column Store
    - Document Store
    - Graph Store

    ![1%20NoSQL%20%E1%84%8B%E1%85%B5%E1%84%92%E1%85%A2%20696399321788434aace237b1e9458201/Untitled%201.png](https://s3.us-west-2.amazonaws.com/secure.notion-static.com/6678cba3-1cdd-4f21-8df5-fed747303f42/Untitled.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=AKIAT73L2G45O3KS52Y5%2F20210319%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20210319T180843Z&X-Amz-Expires=86400&X-Amz-Signature=e313e84072b5e77a4b0115c98aa3d6d2d1f92cade33643bed40496a2cb0edf0c&X-Amz-SignedHeaders=host&response-content-disposition=filename%20%3D%22Untitled.png%22)

## mongoDB

- document db
    - JSON ๊ธฐ๋ฐ ๋ฐ์ดํฐ ๊ด๋ฆฌ
    - JSON document = { "id":"01", "languange":"java", "edition": { "first": "1st", "second":"2nd", "third":"third" } }
- mongoDB document ์)

    ```json
    {
        "_id": ObjectId("5099803df3f42312312391"),
        "username": "davelee",
        "name": { first: "Dave", last: "Lee" }
    }
    ```

---

# 1.3 mongodb ๋ฐ์ดํฐ ๊ตฌ์กฐ์ ๊ด๋ จ ์ฉ์ด ์ ๋ฆฌ

## MongoDB ๋ฐ์ดํฐ ๊ตฌ์กฐ

- Database - Collection - Document
- Database๋  Collection์ ์งํฉ
- Collection์ Document์ ์งํฉ
- Collection์ RDBMS์ Table๊ณผ ์ ์ฌํ ๊ฐ๋์ด๋ Schema ์ ์ x
- Collection์ JSON ํํ์ Document๋ฅผ ๋ฃ๋๋ค
- RDBMS: Database - Table - Data

    โ ๋ฐ์ดํฐ๋ฒ ์ด์ค ์์ ํ์ด๋ธ์ด ์๊ณ , ๊ฐ๊ฐ์ ํ์ด๋ธ๋ง๋ค ๋ฐ์ดํฐ๊ฐ ์์ผ๋ฉฐ, ํ์ด๋ธ ๊ฐ ๊ด๊ณ๊ฐ ์๋ค. 

![1%20NoSQL%20%E1%84%8B%E1%85%B5%E1%84%92%E1%85%A2%20696399321788434aace237b1e9458201/Untitled%202.png](https://s3.us-west-2.amazonaws.com/secure.notion-static.com/be21720b-d87f-4ab1-ab49-ffa6bf131d5d/Untitled.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=AKIAT73L2G45O3KS52Y5%2F20210319%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20210319T180909Z&X-Amz-Expires=86400&X-Amz-Signature=02c3d77ae7c3f6e49107ef615bc546d867127a7efd4d1d8059ba8d583d8fdca1&X-Amz-SignedHeaders=host&response-content-disposition=filename%20%3D%22Untitled.png%22)

![1%20NoSQL%20%E1%84%8B%E1%85%B5%E1%84%92%E1%85%A2%20696399321788434aace237b1e9458201/Untitled%203.png](https://s3.us-west-2.amazonaws.com/secure.notion-static.com/90f9fdc2-51d6-4ad7-8f21-ed27d75da7f6/Untitled.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=AKIAT73L2G45O3KS52Y5%2F20210319%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20210319T180927Z&X-Amz-Expires=86400&X-Amz-Signature=63bbdc99503ae2e810c279971a005f9aa6149480ca11ec0cc27d61d8d2aa861e&X-Amz-SignedHeaders=host&response-content-disposition=filename%20%3D%22Untitled.png%22)