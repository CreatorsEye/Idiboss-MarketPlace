# 🔧 Technical Details

## Database Integration
- **Hostinger MySQL database** is used for storage.
- Standard WordPress tables are utilized, with additional meta fields for custom data.
- Optimized queries via WordPress functions.

## Custom Post Types
### Product Offers (`product_offers`)
- Supports title, editor, thumbnail, custom fields.
- Archive at `/offers/`.
- Custom meta boxes for pricing and images.

### Marketing Campaigns (`marketing_campaign`) – Future
- For marketers to create campaigns.

## User Roles and Capabilities
Custom roles are added via WordPress functions in the theme's `functions.php`. Capabilities are assigned accordingly to control access to features.

## Front-End Assets
- CSS and JS are enqueued properly using WordPress functions.
- Localized scripts pass AJAX URLs and nonces to JavaScript.

## Template Hierarchy
Custom templates are used:
- `page-dashboard.php` for dashboard.
- `archive-product_offers.php` for product grid.
- `single-product_offers.php` for single product view (though modal may override).
- Modal content loaded via AJAX or inline in the page.

## AJAX Handlers
All front-end actions that require server interaction use WordPress AJAX API:
- `wp_ajax_nopriv_*` for non-logged-in actions (if any).
- `wp_ajax_*` for logged-in users.

## Security Measures
- **Nonces** on all forms and AJAX requests.
- **Capability checks** before any data modification.
- **Data sanitization** on all inputs.
- **File upload validation** for type and size.
- **Output escaping** to prevent XSS.

## Performance Considerations
- Image dimensions are standardized to reduce layout shifts.
- Lazy loading for images in grids.
- AJAX requests are lightweight and return only necessary data.
- Caching where appropriate.

## Dependencies
- WordPress 5.0+
- PHP 7.4+
- MySQL 5.6+
- Hostinger hosting (optimized but not required)

## Development Workflow
- Version control via Git.
- Local development environment.
- Deployment via manual upload or CI/CD.
