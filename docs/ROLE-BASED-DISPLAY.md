# 👥 Role-Based Content Display

## Overview
The idiboss theme dynamically tailors content visibility based on the logged-in user's role. This ensures each user sees only the information relevant to them, enhancing clarity, security, and user experience.

## User Roles Defined
| Role      | Description                                                                 |
|-----------|-----------------------------------------------------------------------------|
| Supplier  | Creates and manages product offers. Needs full pricing details.             |
| Investor  | Invests in products; focuses on profit-related data.                        |
| Seller    | Handles sales; needs visibility on supplier fees.                           |
| Customer  | End consumer; sees only the final price.                                    |
| Marketer  | Manages marketing campaigns; views campaign metrics and content.            |

## Role Capabilities
Roles are implemented using WordPress's built-in roles and capabilities, with custom capabilities added as needed.

### Supplier Capabilities
- `edit_product_offers`
- `edit_others_product_offers` (if needed)
- `publish_product_offers`
- `delete_product_offers`
- `upload_files`

### Investor Capabilities
- `read`
- `view_investor_data` (custom capability)

### Seller Capabilities
- `read`
- `view_seller_data` (custom capability)

### Customer Capabilities
- `read`

### Marketer Capabilities
- `read`
- `edit_marketing_posts`
- `view_analytics`

## Content Filtering Logic
When displaying product offers, the system checks the current user's role and shows/hides fields accordingly.

### Pseudocode
if (user is Supplier) {
show all fields: base_price, investor_profit, supplier_fee, final_price, sale_duration;
} elseif (user is Investor) {
show base_price, investor_profit, final_price, sale_duration;
} elseif (user is Seller) {
show supplier_fee;
} elseif (user is Customer) {
show final_price;
} elseif (user is Marketer) {
show campaign fields (if applicable);
}


### Implementation in WordPress
Filters and template conditions are used to hide fields. For example, in the product modal template:
```php
$role = wp_get_current_user()->roles[0]; // Simplified; handle multiple roles
if ($role == 'supplier') {
    echo 'Base Price: ' . get_post_meta($post_id, 'base_price', true) . ' DA';
}
Multi-Role Users
If a user has multiple roles (e.g., Supplier and Investor), they see a combined view with all relevant fields. The dashboard displays separate sections for each role.

Security Considerations
Capabilities are checked before any data is displayed or actions are performed.

Nonces are used on all forms to prevent CSRF.

Data sanitization and validation are applied on input.

Role Color Coding (UI)
Roles are visually distinguished by color badges next to the user name:

Customer: Blue

Supplier: Green

Investor: Orange

Marketer: Purple

Seller: Gray (or a distinct color TBD)

---

### File: `docs/DASHBOARD.md`

```markdown
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
- WordPress functions (`wp_insert_post`, `update_post_meta`) triggered by these handlers.

## Implementation Notes
- Dashboard is accessible at `/dashboard/` via a custom page template.
- Conditional logic loads the appropriate sections based on user roles.
- All forms use nonces and sanitization.
- Media uploads are handled via WordPress's media handling functions, with custom UI.
