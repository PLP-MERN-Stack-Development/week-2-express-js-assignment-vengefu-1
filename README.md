# Express.js RESTful API Assignment

## 🚀 How to Run the Server

1. Install dependencies:
   ```
   npm install
   ```
2. Start the server:
   ```
   npm start
   ```
   The server will run on [http://localhost:3000](http://localhost:3000).

## 📚 API Endpoints

### Root

- `GET /`
  - **Response:**  
    `Hello World from Express!`

### Products

- `GET /api/products`
  - List all products.

- `GET /api/products/:id`
  - Get a product by ID.

- `POST /api/products`
  - Create a new product.
  - **Body:**  
    ```json
    {
      "name": "Product Name",
      "description": "Description",
      "price": 100,
      "category": "category",
      "inStock": true
    }
    ```

- `PUT /api/products/:id`
  - Update a product by ID.
  - **Body:** (same as POST)

- `DELETE /api/products/:id`
  - Delete a product by ID.

## 🔐 Authentication

All API routes require an `Authorization` header:
```
Authorization: Bearer secret-token
```

## 📝 Example Requests

**Get all products:**
```sh
curl -H "Authorization: Bearer secret-token" http://localhost:3000/api/products
```

**Create a product:**
```sh
curl -X POST -H "Content-Type: application/json" -H "Authorization: Bearer secret-token" \
-d '{"name":"Book","description":"A good book","price":20,"category":"books","inStock":true}' \
http://localhost:3000/api/products
```

**Get a product by ID:**
```sh
curl -H "Authorization: Bearer secret-token" http://localhost:3000/api/products/1
```

**Update a product:**
```sh
curl -X PUT -H "Content-Type: application/json" -H "Authorization: Bearer secret-token" \
-d '{"price":25}' http://localhost:3000/api/products/1
```

**Delete a product:**
```sh
curl -X DELETE -H "Authorization: Bearer secret-token" http://localhost:3000/api/products/1
```

## ⚙️ Environment Variables

See [.env.example](.env.example) for required environment variables.