# API Endpoints

This section describes the API endpoints exposed by the **YourProductName** platform. These endpoints enable clients to interact with various parts of the system, including user management, payment processing, and data retrieval. Each endpoint is described with its HTTP method, URL pattern, request parameters, and response format.

## 1. **User Management API**

### 1.1. **Create User**

- **Method**: `POST`
- **URL**: `/api/v1/users`
- **Description**: Creates a new user in the system.
- **Request Body**:
  ```json
  {
    "username": "johndoe",
    "email": "johndoe@example.com",
    "password": "securePassword123",
    "first_name": "John",
    "last_name": "Doe"
  }
  ```
- **Response**:
  - **Status Code**: `201 Created`
  - **Response Body**:
    ```json
    {
      "id": 123,
      "username": "johndoe",
      "email": "johndoe@example.com",
      "first_name": "John",
      "last_name": "Doe"
    }
    ```

### 1.2. **Get User Details**

- **Method**: `GET`
- **URL**: `/api/v1/users/{user_id}`
- **Description**: Retrieves the details of a specific user by their ID.
- **Path Parameters**:
  - `user_id`: The ID of the user to retrieve.
- **Response**:
  - **Status Code**: `200 OK`
  - **Response Body**:
    ```json
    {
      "id": 123,
      "username": "johndoe",
      "email": "johndoe@example.com",
      "first_name": "John",
      "last_name": "Doe"
    }
    ```

### 1.3. **Update User Information**

- **Method**: `PUT`
- **URL**: `/api/v1/users/{user_id}`
- **Description**: Updates the information of an existing user.
- **Path Parameters**:
  - `user_id`: The ID of the user to update.
- **Request Body**:
  ```json
  {
    "email": "newemail@example.com",
    "first_name": "John",
    "last_name": "Doe"
  }
  ```
- **Response**:
  - **Status Code**: `200 OK`
  - **Response Body**:
    ```json
    {
      "id": 123,
      "username": "johndoe",
      "email": "newemail@example.com",
      "first_name": "John",
      "last_name": "Doe"
    }
    ```

### 1.4. **Delete User**

- **Method**: `DELETE`
- **URL**: `/api/v1/users/{user_id}`
- **Description**: Deletes a specific user by their ID.
- **Path Parameters**:
  - `user_id`: The ID of the user to delete.
- **Response**:
  - **Status Code**: `204 No Content`

---

## 2. **Product Management API**

### 2.1. **Create Product**

- **Method**: `POST`
- **URL**: `/api/v1/products`
- **Description**: Adds a new product to the catalog.
- **Request Body**:
  ```json
  {
    "name": "Smartphone",
    "description": "Latest model smartphone with advanced features",
    "price": 599.99,
    "stock": 100
  }
  ```
- **Response**:
  - **Status Code**: `201 Created`
  - **Response Body**:
    ```json
    {
      "id": 456,
      "name": "Smartphone",
      "description": "Latest model smartphone with advanced features",
      "price": 599.99,
      "stock": 100
    }
    ```

### 2.2. **Get Product Details**

- **Method**: `GET`
- **URL**: `/api/v1/products/{product_id}`
- **Description**: Retrieves the details of a specific product by its ID.
- **Path Parameters**:
  - `product_id`: The ID of the product to retrieve.
- **Response**:
  - **Status Code**: `200 OK`
  - **Response Body**:
    ```json
    {
      "id": 456,
      "name": "Smartphone",
      "description": "Latest model smartphone with advanced features",
      "price": 599.99,
      "stock": 100
    }
    ```

### 2.3. **Update Product Information**

- **Method**: `PUT`
- **URL**: `/api/v1/products/{product_id}`
- **Description**: Updates the information of an existing product.
- **Path Parameters**:
  - `product_id`: The ID of the product to update.
- **Request Body**:
  ```json
  {
    "price": 579.99,
    "stock": 120
  }
  ```
- **Response**:
  - **Status Code**: `200 OK`
  - **Response Body**:
    ```json
    {
      "id": 456,
      "name": "Smartphone",
      "description": "Latest model smartphone with advanced features",
      "price": 579.99,
      "stock": 120
    }
    ```

### 2.4. **Delete Product**

- **Method**: `DELETE`
- **URL**: `/api/v1/products/{product_id}`
- **Description**: Deletes a specific product from the catalog.
- **Path Parameters**:
  - `product_id`: The ID of the product to delete.
- **Response**:
  - **Status Code**: `204 No Content`

---

## 3. **Order Management API**

### 3.1. **Create Order**

- **Method**: `POST`
- **URL**: `/api/v1/orders`
- **Description**: Creates a new order for a user.
- **Request Body**:
  ```json
  {
    "user_id": 123,
    "items": [
      {
        "product_id": 456,
        "quantity": 1
      }
    ],
    "total_price": 599.99
  }
  ```
- **Response**:
  - **Status Code**: `201 Created`
  - **Response Body**:
    ```json
    {
      "order_id": 789,
      "user_id": 123,
      "items": [
        {
          "product_id": 456,
          "quantity": 1
        }
      ],
      "total_price": 599.99,
      "status": "Pending"
    }
    ```

### 3.2. **Get Order Details**

- **Method**: `GET`
- **URL**: `/api/v1/orders/{order_id}`
- **Description**: Retrieves the details of a specific order by its ID.
- **Path Parameters**:
  - `order_id`: The ID of the order to retrieve.
- **Response**:
  - **Status Code**: `200 OK`
  - **Response Body**:
    ```json
    {
      "order_id": 789,
      "user_id": 123,
      "items": [
        {
          "product_id": 456,
          "quantity": 1
        }
      ],
      "total_price": 599.99,
      "status": "Pending"
    }
    ```

### 3.3. **Update Order Status**

- **Method**: `PUT`
- **URL**: `/api/v1/orders/{order_id}/status`
- **Description**: Updates the status of an existing order.
- **Path Parameters**:
  - `order_id`: The ID of the order to update.
- **Request Body**:
  ```json
  {
    "status": "Shipped"
  }
  ```
- **Response**:
  - **Status Code**: `200 OK`
  - **Response Body**:
    ```json
    {
      "order_id": 789,
      "status": "Shipped"
    }
    ```

### 3.4. **Cancel Order**

- **Method**: `DELETE`
- **URL**: `/api/v1/orders/{order_id}`
- **Description**: Cancels a specific order.
- **Path Parameters**:
  - `order_id`: The ID of the order to cancel.
- **Response**:
  - **Status Code**: `204 No Content`

---

## 4. **Authentication API**

### 4.1. **Login**

- **Method**: `POST`
- **URL**: `/api/v1/auth/login`
- **Description**: Authenticates a user and returns an authentication token.
- **Request Body**:
  ```json
  {
    "email": "johndoe@example.com",
    "password": "securePassword123"
  }
  ```
- **Response**:
  - **Status Code**: `200 OK`
  - **Response Body**:
    ```json
    {
      "token": "jwt_token_here"
    }
    ``

`

### 4.2. **Logout**

- **Method**: `POST`
- **URL**: `/api/v1/auth/logout`
- **Description**: Logs out the authenticated user, invalidating the current session.
- **Response**:
  - **Status Code**: `200 OK`
  - **Response Body**:
    ```json
    {
      "message": "Logged out successfully"
    }
    ```