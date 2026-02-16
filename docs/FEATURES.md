# ✨ Core Features

## 1. Product Offers with Image Functionality
Products are showcased in a responsive grid layout inspired by Facebook Marketplace.

- **Standardized Imagery:** Featured images have uniform dimensions, ensuring a professional and cohesive appearance across the platform.
- **Multi-Image Upload:** Users can upload 1 to 5 images per product. The first uploaded image is automatically set as the featured image.
- **Interactive Slider:** Clicking the featured image opens an interactive slider that allows users to browse all additional product images effortlessly.

## 2. Product Grid & Pop-Up Modal
Products are arranged in a clean, responsive grid where each tile displays:
- Featured image
- Product name

**Clicking any product tile opens a detailed pop-up modal** (rather than navigating to a separate page). The modal contains:
- Enlarged view of the featured image
- Gallery of all additional images
- Full product description and specifications
- Pricing details tailored to the user's role
- Availability data
- Supplier information
- Sale duration

This modal-based approach keeps the browsing experience fluid and consistent.

## 3. Role-Based Content Display
The platform customizes content visibility based on user roles, enhancing clarity, security, and relevance.

| Role      | Visible Information                                                                                   |
|-----------|--------------------------------------------------------------------------------------------------------|
| Supplier  | Can create/manage products and view all pricing details: Base Price, Investor Profit, Supplier Fee, Final Price, Sale Duration |
| Investor  | Views profit-related data: Base Price, Investor Profit, Final Price, Sale Duration                     |
| Seller    | Focuses primarily on Supplier Fee information                                                          |
| Customer  | Sees only the Final Price for simplicity                                                               |
| Marketer  | Views campaign-related metrics and marketing content                                                   |

**All prices are displayed in DZD with “DA” formatting.**

## 4. Custom User Dashboard
Inspired by Facebook profiles, each user’s dashboard features:

- **Profile Section:**
  - Profile picture
  - Banner picture
  - User name displayed to the left of the profile picture with adequate spacing
  - Role name displayed next to the user name in a distinct color (see [Design System](./DESIGN.md))

- **Dashboard Functionality:**
  - Users can create posts and manage content directly from their profile page, **completely bypassing the WordPress admin panel**.
  - Multi-role users access a combined dashboard with tailored sections for each assigned role (e.g., Supplier and Investor sections appear together).

## 5. Front-End Post Submission (Advanced)
Investors, Suppliers, and Marketers can create and manage their own posts directly from their custom dashboards. This feature is detailed in [FRONTEND-SUBMISSION.md](./FRONTEND-SUBMISSION.md).

## 6. Scalability & Future Enhancements
The theme is designed to accommodate future growth. See [ROADMAP.md](./ROADMAP.md) for planned features.
