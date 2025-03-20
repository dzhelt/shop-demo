## Shop Requirements

### 🛍️ Product Catalog
- view list of products
- filter products by category, price, and stock availability.
- sorting products by price, popularity
- view one product and its details
- search a product

### 🛒 Shopping Cart
- add products to the cart
- remove products from the card
- change quantity of products in the cart
- cart should remember already added products between client sessions

### 👨‍💻Order placement
- Users can place an order from the cart.
- Ability to choose a delivery address and contact details.
- Order confirmation before payment.
- Tracking order and its statuses: "Processing", "Paid", "Shipped", "Delivered".

### 💳 Payment Processing
- Payment via PayPal, Stripe (or another payment provider).
- Verification of payment status (successful/unsuccessful).
- Sending a receipt via email after successful payment.

### 🔐 Authentication and Registration
- User registration with email and password.
- Login via JWT tokens.
- User roles: customer, administrator.

### 🎛️ Admin Panel
- Admins can add, edit, and delete products.
- Order management (change statuses, cancel orders).
- User management (block users, change roles).