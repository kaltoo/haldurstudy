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
