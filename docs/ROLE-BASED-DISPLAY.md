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
- Ability to create, edit, publish, and delete their own product offers.
- Ability to upload files (images).

### Investor Capabilities
- Read access to product offers, plus visibility of profit-related fields.

### Seller Capabilities
- Read access to product offers, with visibility of supplier fee.

### Customer Capabilities
- Read access to product offers, seeing only final price.

### Marketer Capabilities
- Read access, plus ability to create marketing posts and view analytics.

## Content Filtering Logic
When displaying product offers, the system checks the current user's role and shows/hides fields accordingly. For example, a Supplier sees all pricing fields, while a Customer sees only the final price. This is implemented using conditional checks in templates and custom database queries.

## Multi-Role Users
If a user has multiple roles (e.g., Supplier and Investor), they see a combined view with all relevant fields. The dashboard displays separate sections for each role.

## Security Considerations
- Capabilities are checked before any data is displayed or actions are performed.
- Nonces are used on all forms to prevent CSRF.
- Data sanitization and validation are applied on input.

## Role Color Coding (UI)
Roles are visually distinguished by color badges next to the user name:
- **Customer:** Blue
- **Supplier:** Green
- **Investor:** Orange
- **Marketer:** Purple
- **Seller:** Gray
