# Stock-Management-API

## stock-management

REST APIs to handle stock basic operation. 

### start the service

```bash
git clone https://github.com/vikasjaiswal24/Stock-Management-API.git
cd stock-management-api
mvn clean install
mvn spring-boot:run
```

### run the tests
```bash
mvn test
```

### APIs
- update stock of a particular product via Postman

```bash
POST    http://localhost:8080/coremedia/api/updateStock

Request-Body

{
	"id": "ST2019",
	"timeStamp": "2019-01-12T17:52:15.015Z",
	"productId" : "1001",
	"quantity" : "10"
}

Note:- Add 3 to 4 products with different product ids. 

response
status-code 201 if everything went well and the new entry for stock was added/updated
```

+ get current stock available of a particular product

```bash
GET    http://localhost:8080/coremedia/api/stock?productId=1001

Response-Body

{
    "productId": 1001,
    "requstTimeStamp": "2019-04-13T17:07:46.890+0000",
    "stock": {
        "id": "S2018",
        "timeStamp": "2019-01-12T17:52:15.015+0000",
        "quantity": 10
    }
}
```

- get all the stock details

```bash
GET    http://localhost:8080/coremedia/api/allStock

Response-Body

[
    {
        "timeStamp": "2019-01-12T17:52:15.015+0000",
        "productId": 1001,
        "quantity": 10,
        "id": "S2019"
    },
    {
        "timeStamp": "2019-01-12T17:53:15.015+0000",
        "productId": 2001,
        "quantity": 20,
        "id": "S2019"
    },
    {
        "timeStamp": "2019-01-12T17:54:15.015+0000",
        "productId": 3001,
        "quantity": 30,
        "id": "S2019"
    },
    {
        "timeStamp": "2019-01-12T17:55:15.015+0000",
        "productId": 4001,
        "quantity": 40,
        "id": "S2019"
    }
]
```


