# 🛍️ Product Catalog API

A simple and efficient REST API for managing product catalogs, built with Spring Boot 3 using Java 17.

## 🚀 Technologies

- **Java 11**
- **Spring Boot 3.2.3**
- **Spring Data JPA**
- **H2 Database** (in-memory)
- **Maven**
- **Lombok**

## 📋 Requirements

- Java 11 or higher
- Maven 3.6+

## 🏗️ Project Structure

```
src/
├── main/
│   ├── java/
│   │   └── com/example/productcatalog/
│   │       ├── ProductCatalogApiApplication.java
│   │       ├── controller/
│   │       │   └── ProductController.java
│   │       ├── model/
│   │       │   └── Product.java
│   │       ├── repository/
│   │       │   └── ProductRepository.java
│   │       ├── service/
│   │       │   ├── ProductService.java
│   │       │   └── ProductServiceImpl.java
│   │       └── exception/
│   │           ├── ProductNotFoundException.java
│   │           └── GlobalExceptionHandler.java
│   └── resources/
│       └── application.properties
```

## 🚀 Quick Start

1. **Clone the repository:**
   ```bash
   git clone <your-repo-url>
   cd product-catalog-api
   ```

2. **Run the application:**
   ```bash
   mvn spring-boot:run
   ```

3. **Application will be available at:**
   - API: http://localhost:8080
   - H2 Console: http://localhost:8080/h2-console

## 📚 API Endpoints

### Get All Products
```http
GET /products
```

**Response:**
```json
[
  {
    "id": 1,
    "name": "Laptop",
    "description": "High-performance laptop",
    "price": 999.99
  }
]
```

### Get Product by ID
```http
GET /products/{id}
```

**Response:**
```json
{
  "id": 1,
  "name": "Laptop",
  "description": "High-performance laptop",
  "price": 999.99
}
```

### Create New Product
```http
POST /products
Content-Type: application/json

{
  "name": "Smartphone",
  "description": "Latest smartphone model",
  "price": 699.99
}
```

**Response:**
```json
{
  "id": 2,
  "name": "Smartphone",
  "description": "Latest smartphone model",
  "price": 699.99
}
```

### Update Product
```http
PUT /products/{id}
Content-Type: application/json

{
  "name": "Updated Laptop",
  "description": "Updated description",
  "price": 1099.99
}
```

### Delete Product
```http
DELETE /products/{id}
```

## 🛠️ Usage Examples with cURL

### Create Product
```bash
curl -X POST http://localhost:8080/products \
  -H "Content-Type: application/json" \
  -d '{
    "name": "Gaming Mouse",
    "description": "High-precision gaming mouse",
    "price": 89.99
  }'
```

### Get All Products
```bash
curl http://localhost:8080/products
```

### Get Product by ID
```bash
curl http://localhost:8080/products/1
```

### Update Product
```bash
curl -X PUT http://localhost:8080/products/1 \
  -H "Content-Type: application/json" \
  -d '{
    "name": "Updated Gaming Mouse",
    "description": "Updated description",
    "price": 99.99
  }'
```

### Delete Product
```bash
curl -X DELETE http://localhost:8080/products/1
```

## 🗄️ Database

The project uses H2 in-memory database for simplicity in development and testing.

**H2 Console Access:**
- URL: http://localhost:8080/h2-console
- JDBC URL: `jdbc:h2:mem:productdb`
- Username: `sa`
- Password: `password`

## ⚠️ Error Handling

The API returns appropriate HTTP status codes:

- `200 OK` - successful operation
- `201 Created` - product successfully created
- `204 No Content` - product successfully deleted
- `404 Not Found` - product not found
- `500 Internal Server Error` - internal server error

## 🧪 Testing

To run tests:
```bash
mvn test
```

## 📦 Building

To create a JAR file:
```bash
mvn clean package
```

The JAR file will be created in the `target/` folder.

## 🔧 Configuration

Main settings in `application.properties`:

```properties
# H2 Database
spring.datasource.url=jdbc:h2:mem:productdb
spring.datasource.username=sa
spring.datasource.password=password

# JPA
spring.jpa.hibernate.ddl-auto=update
spring.jpa.show-sql=true

# H2 Console
spring.h2.console.enabled=true
spring.h2.console.path=/h2-console
```

## 🤝 Contributing

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## 📄 License

This project is licensed under the MIT License - see the `LICENSE` file for details.

## 👨‍💻 Author

Created with ❤️ to demonstrate Spring Boot REST API capabilities.

---

⭐ If you like this project, give it a star! 