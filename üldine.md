## Üldine

#### Teemad millega ennast kurssi viia

###### Mis asi on DTO Data Transfer Object

Json
```json
{
  "make": "Toyota",
  "model": "Corolla",
  "year": 2022,
  "colour": "Blue",
  "mileage": 15000
}
```

XML
```xml
<Car>
  <Make>Toyota</Make>
  <Model>Corolla</Model>
  <Year>2022</Year>
  <Colour>Blue</Colour>
  <Mileage>15000</Mileage>
</Car>
```

* Miks võib XML olla parem kui JSON?
* Mis valdkonnas on XML siiani standard?

WSDL
```xml
<?xml version="1.0" encoding="UTF-8"?>
<definitions xmlns:wsdl="http://schemas.xmlsoap.org/wsdl/"
             xmlns:xsd="http://www.w3.org/2001/XMLSchema"
             xmlns:tns="http://example.com/car"
             targetNamespace="http://example.com/car"
             name="CarSchema">

  <types>
    <xsd:schema targetNamespace="http://example.com/car"
                xmlns:xsd="http://www.w3.org/2001/XMLSchema">
      <xsd:element name="Car">
        <xsd:complexType>
          <xsd:sequence>
            <xsd:element name="Make" type="xsd:string"/>
            <xsd:element name="Model" type="xsd:string"/>
            <xsd:element name="Year" type="xsd:int"/>
            <xsd:element name="Colour" type="xsd:string"/>
            <xsd:element name="Mileage" type="xsd:int"/>
          </xsd:sequence>
        </xsd:complexType>
      </xsd:element>
    </xsd:schema>
  </types>

</definitions>
```

###### HTTP protokoll

GET request/response

```
GET /cars/123 HTTP/1.1
Host: api.example.com
Accept: application/json
```

```
HTTP/1.1 200 OK
Content-Type: application/json

{
  "id": 123,
  "make": "Toyota",
  "model": "Corolla",
  "year": 2022,
  "colour": "Blue",
  "mileage": 15000
}
```

Post request/response
```
POST /cars HTTP/1.1
Host: api.example.com
Content-Type: application/json
Content-Length: 95

{
  "make": "Toyota",
  "model": "Corolla",
  "year": 2022,
  "colour": "Blue",
  "mileage": 15000
}
```

```
HTTP/1.1 201 Created
Content-Type: application/json
Location: https://api.example.com/cars/124

{
  "id": 124,
  "make": "Toyota",
  "model": "Corolla",
  "year": 2022,
  "colour": "Blue",
  "mileage": 15000,
  "createdAt": "2025-06-15T10:35:21Z"
}
```


Näide kõikide autode laadimise kohta
```html
GET /cars?make=Toyota&model=Corolla&year=2022 HTTP/1.1
Host: api.example.com
Accept: application/json
```

```html
HTTP/1.1 200 OK
Content-Type: application/json

[
  {
    "id": 123,
    "make": "Toyota",
    "model": "Corolla",
    "year": 2022,
    "colour": "Blue",
    "mileage": 15000
  }
]
```


See kuidas reeglina päringuid tehakse - REST
```
## 🌐 What is a REST API?

A **REST API** (Representational State Transfer API) is a way for systems to communicate over **HTTP** using standard web methods:

- `GET` – Retrieve data  
- `POST` – Create data  
- `PUT` / `PATCH` – Update data  
- `DELETE` – Remove data  

### 🔑 Key Concepts:
- **Resources** are represented by URLs (e.g., `/cars`, `/users/123`)
- **Stateless** – Each request contains all the information it needs (no server memory of past requests)
- **Uses JSON or XML** as the data format (most commonly JSON)

### 📦 Example:
```http
GET /cars/123     → returns data for car with ID 123  
POST /cars        → creates a new car entry
```


Login examplse 

```html
POST /login HTTP/1.1
Host: api.example.com
Content-Type: application/json
Content-Length: 49

{
  "username": "john.doe",
  "password": "secret123"
}
```


```html
HTTP/1.1 200 OK
Content-Type: application/json

{
  "token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9...",
  "userId": 42,
  "expiresIn": 3600
}
```


Leht kus saab JWT sisse vaadata: https://jwt.io/

Siin jäime pooleli
```
###### Stateless
###### Cookie - JWT, muu info
###### Mis asi on veebiserver?
###### Mis porte kasutatakse?
###### Dev tools
###### Mida tähendab API

###### HTTPS - põhimõte
###### Kelle vahel turvaline?
###### Millal pole vaja?

###### Mis asi on websocket?
```

