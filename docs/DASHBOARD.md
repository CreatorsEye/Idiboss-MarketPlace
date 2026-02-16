# 🖥 Custom User Dashboard

## Overview
The custom dashboard replaces the default WordPress admin for front-end users. It provides a familiar, Facebook-inspired interface where users can manage their profile, create posts, and view role-specific content.

## Dashboard Layout

## Profile Section
- **Profile Picture:** Uploaded via front-end form.
- **Banner Picture:** Larger cover image.
- **User Name:** Displayed left of profile picture.
- **Role Badge:** Colored label next to name.

## Dashboard Sections by Role
### Supplier Section
- List of own product offers with edit/delete options.
- Form to create new product offer (title, description, images, pricing).
- Quick stats: number of active offers, total sales, etc.

### Investor Section
- List of invested products with profit data.
- Charts/graphs showing investment performance (future enhancement).
- Key metrics: Base Price, Investor Profit, Final Price, Sale Duration.

### Seller Section
- Supplier fee information for products they are selling.
- List of sales with commission earned.

### Customer Section
- Order history (future e-commerce integration).
- Saved products.

### Marketer Section
- Campaign creation form.
- Analytics dashboard (future).

## Front-End Content Management
Users can create and manage posts (including product offers) without accessing wp-admin. This is achieved through:
- Custom templates with forms.
- AJAX submission handlers.
- WordPress functions triggered by these handlers.

## Implementation Notes
- Dashboard is accessible at `/dashboard/` via a custom page template.
- Conditional logic loads the appropriate sections based on user roles.
- All forms use nonces and sanitization.
- Media uploads are handled via WordPress's media handling functions, with custom UI.
