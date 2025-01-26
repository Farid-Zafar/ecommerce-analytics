# 📂 Data Folder Overview

Welcome to the `data` folder for the E-Commerce Analytics Project repository! This folder contains all the datasets required for analyzing orders, inventory, products, users, and distribution centers to support various business insights.

---

## 📊 Contents of the Data Folder

The `data` folder is organized to house the following datasets:

### 1. **Orders**
- **File**: `orders.csv`
- **Schema**:
  - `order_id` (Integer): Unique identifier for the order.
  - `user_id` (Integer): Reference to the user who placed the order.
  - `status` (String): Current status of the order (e.g., "Cancelled", "Complete").
  - `gender` (String): Gender of the user who placed the order.
  - `created_at` (Timestamp): Timestamp when the order was created.
  - `returned_at` (Timestamp): Timestamp when the order was returned (if applicable).
  - `shipped_at` (Timestamp): Timestamp when the order was shipped.
  - `delivered_at` (Timestamp): Timestamp when the order was delivered.
  - `num_of_item` (Integer): Number of items in the order.

---

### 2. **Order Items**
- **File**: `order_items.csv`
- **Schema**:
  - `id` (Integer): Unique identifier for the order item.
  - `order_id` (Integer): Reference to the associated order.
  - `user_id` (Integer): Reference to the user who placed the order.
  - `product_id` (Integer): Identifier of the product.
  - `inventory_item_id` (Integer): Reference to the specific inventory item.
  - `status` (String): Current status of the item (e.g., "Complete", "Cancelled").
  - `created_at` (Timestamp): Timestamp when the item was created.
  - `shipped_at` (Timestamp): Timestamp when the item was shipped.
  - `delivered_at` (Timestamp): Timestamp when the item was delivered.
  - `returned_at` (Timestamp): Timestamp when the item was returned (if applicable).
  - `sale_price` (Decimal): Sale price of the item.

---

### 3. **Products**
- **File**: `products.csv`
- **Schema**:
  - `id` (Integer): Unique identifier for the product.
  - `cost` (Decimal): Cost price of the product.
  - `category` (String): Category to which the product belongs.
  - `name` (String): Name of the product.
  - `brand` (String): Brand of the product.
  - `retail_price` (Decimal): Retail price of the product.
  - `department` (String): Department associated with the product (e.g., "Women").
  - `sku` (String): Stock Keeping Unit for the product.
  - `distribution_center_id` (Integer): Reference to the distribution center storing the product.

---

### 4. **Users**
- **File**: `users.csv`
- **Schema**:
  - `id` (Integer): Unique identifier for the user.
  - `first_name` (String): First name of the user.
  - `last_name` (String): Last name of the user.
  - `email` (String): Email address of the user.
  - `age` (Integer): Age of the user.
  - `gender` (String): Gender of the user.
  - `state` (String): State where the user resides.
  - `street_address` (String): Full street address of the user.
  - `postal_code` (String): Postal code of the user's address.
  - `city` (String): City where the user resides.
  - `country` (String): Country of residence.
  - `latitude` (Decimal): Latitude coordinate of the user's location.
  - `longitude` (Decimal): Longitude coordinate of the user's location.
  - `traffic_source` (String): Traffic source through which the user reached the platform (e.g., "Search").
  - `created_at` (Timestamp): Timestamp when the user registered.

---

### 5. **Distribution Centers**
- **File**: `distribution_centers.csv`
- **Schema**:
  - `id` (Integer): Unique identifier for the distribution center.
  - `name` (String): Name of the distribution center.
  - `latitude` (Decimal): Latitude coordinate of the distribution center.
  - `longitude` (Decimal): Longitude coordinate of the distribution center.

---

### 6. **Inventory Items**
- **File**: `inventory_items.csv`
- **Schema**:
  - `id` (Integer): Unique identifier for the inventory item.
  - `product_id` (Integer): Reference to the associated product.
  - `created_at` (Timestamp): Timestamp when the inventory item was created.
  - `sold_at` (Timestamp): Timestamp when the inventory item was sold (if applicable).
  - `cost` (Decimal): Cost price of the inventory item.
  - `product_category` (String): Category of the associated product.
  - `product_name` (String): Name of the associated product.
  - `product_brand` (String): Brand of the associated product.
  - `product_retail_price` (Decimal): Retail price of the associated product.
  - `product_department` (String): Department of the associated product.
  - `product_sku` (String): SKU of the associated product.
  - `product_distribution_center_id` (Integer): Distribution center ID for the inventory item.

---

### 7. Events (Marketing Events)
- **File**: 'events.csv'
- **Schema**:
  - `id` (Integer): Unique identifier for the event.
  - `user_id` (Integer): Identifier for the user associated with the event.
  - `sequence_number` (Integer): Sequential number indicating the order of events for a given session.
  - `session_id` (String): Unique identifier for the user's session during which the event occurred.
  - `created_at` (Timestamp): Timestamp when the event was recorded.
  - `ip_address` (String): IP address of the user at the time of the event.
  - `city` (String): City where the event originated.
  - `state` (String): State where the event originated.
  - `postal_code` (String): Postal code corresponding to the event location.
  - `browser` (String): Browser used by the user during the event (e.g., "Firefox", "Safari").
  - `traffic_source` (String): Marketing source that directed the user to the platform (e.g., "Adwords", "YouTube").
  - `uri` (String): URI path accessed by the user (e.g., "/cancel").
  - `event_type` (String): Type of event logged (e.g., "cancel").


## 🛠️ Data Extraction Process

The datasets in this folder were exported from **BigQuery**, specifically from the public dataset `bigquery-public-data.thelook_ecommerce`. Below are the SQL queries executed in the BigQuery console to extract the data:

```sql
SELECT * FROM `bigquery-public-data.thelook_ecommerce.distribution_centers`;
SELECT * FROM `bigquery-public-data.thelook_ecommerce.events`;
SELECT * FROM `bigquery-public-data.thelook_ecommerce.inventory_items`;
SELECT * FROM `bigquery-public-data.thelook_ecommerce.order_items`;
SELECT * FROM `bigquery-public-data.thelook_ecommerce.orders`;
SELECT * FROM `bigquery-public-data.thelook_ecommerce.products`;
SELECT * FROM `bigquery-public-data.thelook_ecommerce.users`;

