# E-Commerce API

A Django REST Framework based e-commerce API with JWT authentication, product management, and order processing capabilities.

## Features

- User authentication with JWT tokens
- Product management (CRUD operations)
- Order processing
- Search, filter, and sort functionality
- Admin interface for data management

## Prerequisites

- Python 3.8 or higher
- pip (Python package manager)

## Installation

1. Clone the repository:

```bash
git clone <repository-url>
cd ecommerapi
```

2. Create and activate a virtual environment:

```bash
python -m venv venv
source venv/bin/activate  # On Windows use: venv\Scripts\activate
```

3. Install dependencies:

```bash
pip install django
pip install djangorestframework
pip install djangorestframework-simplejwt
pip install django-filter
```

4. Run database migrations:

```bash
python manage.py makemigrations
python manage.py migrate
```

5. Create a superuser for admin access:

```bash
python manage.py createsuperuser
```

## Running the Server

Start the development server:

```bash
python manage.py runserver
```

The API will be available at `http://localhost:8000/api/v1/`

## API Endpoints

### Authentication

- `POST /api/v1/users/login/` - Login and get JWT tokens
- `POST /api/v1/token/refresh/` - Refresh JWT token

### Products

- `GET /api/v1/products/` - List all products
- `POST /api/v1/products/` - Create a new product
- `GET /api/v1/products/{id}/` - Get product details
- `PUT /api/v1/products/{id}/` - Update a product
- `DELETE /api/v1/products/{id}/` - Delete a product

### Orders

- `GET /api/v1/orders/` - List user's orders
- `POST /api/v1/orders/` - Create a new order
- `GET /api/v1/orders/{id}/` - Get order details
- `PUT /api/v1/orders/{id}/` - Update an order
- `GET /api/v1/orders/my_orders/` - Get current user's orders

### Users

- `POST /api/v1/users/` - Register a new user

## Admin Interface

Access the admin interface at `http://localhost:8000/admin/` using your superuser credentials.

## API Features

### Filtering

Use query parameters to filter results:

```
/api/v1/products/?category=Electronics
/api/v1/orders/?status=Pending
```

### Searching

Search products by name or description:

```
/api/v1/products/?search=keyword
```

### Sorting

Sort results using the ordering parameter:

```
/api/v1/products/?ordering=price
/api/v1/products/?ordering=-price  # Descending order
```

## Authentication

All API endpoints (except user registration and login) require JWT authentication. Include the JWT token in the Authorization header:

```
Authorization: Bearer <your-jwt-token>
```
