# 🏗 Technical Architecture

## Overview
Custom WordPress theme built entirely without third-party plugins. Every feature is manually coded to ensure complete control, security, and performance optimization.

## Tech Stack
| Component   | Technology               | Purpose                               |
|-------------|--------------------------|---------------------------------------|
| CMS         | WordPress Core           | Content management foundation         |
| Database    | Hostinger MySQL          | Optimized data storage                |
| Front-End   | PHP, JavaScript (AJAX), CSS | Dynamic user interface              |
| Back-End    | WordPress PHP APIs       | Custom functionality                  |

## System Architecture Diagram

## Database Schema

### Custom Post Type: product_offers
The main content type for product offers, stored in standard WordPress posts table with post_type = 'product_offers'.

### Post Meta Fields
Each product offer stores the following meta fields:
- `base_price` (decimal) – The starting price of the product as set by the supplier.
- `investor_profit` (decimal) – The additional profit per product that an investor earns.
- `supplier_fee` (decimal) – The fee the supplier takes from the selling price.
- `final_price` (decimal) – The selling price displayed to the end customer.
- `sale_duration` (integer) – The period (in days) during which the product will be available for sale.
- `product_images` (array) – IDs of attached images (1 to 5).

### User Meta Fields
- `profile_picture` (attachment ID)
- `banner_picture` (attachment ID)
- `dashboard_settings` (array) – User preferences for dashboard layout.

## Key Architectural Decisions
- **Separation of Concerns:** Template files separate presentation from logic.
- **Role-Based Filtering:** Content is filtered at the query level based on user capabilities.
- **AJAX for Front-End Actions:** All form submissions use AJAX to maintain a seamless experience.
- **No Reliance on Plugins:** All functionality is custom-coded, reducing dependencies and improving performance.
- 
