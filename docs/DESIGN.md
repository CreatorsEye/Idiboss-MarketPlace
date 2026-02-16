# 🎨 Design System

## Color Palette
- **Primary Green:** `#00A859` – Used for accents, buttons, links.
- **White:** `#FFFFFF` – Background color.
- **Dark Gray:** `#333333` – Body text.
- **Light Gray:** `#F5F5F5` – Background for cards, modals.

## Role Badge Colors
| Role      | Color      | Hex Code   |
|-----------|------------|------------|
| Customer  | Blue       | `#0073AA`  |
| Supplier  | Green      | `#00A859`  |
| Investor  | Orange     | `#F56E28`  |
| Marketer  | Purple     | `#9B51E0`  |
| Seller    | Gray       | `#6C757D`  |

## Typography
- **Primary Font:** System fonts stack.
- **Headings:** Bold, 24px (h1), 20px (h2), etc.
- **Body:** Regular, 16px.
- **Labels:** Medium, 14px.

## Spacing
- **Grid Gap:** 20px between product tiles.
- **Tile Padding:** 15px.
- **Dashboard Margins:** 25px around main content.
- **Profile Spacing:** User name left of profile picture with 15px gap.

## Image Specifications
| Image Type         | Dimensions | Aspect Ratio | Notes                          |
|--------------------|------------|--------------|--------------------------------|
| Featured Product   | 300x300 px | 1:1          | Uniform grid appearance        |
| Profile Picture    | 150x150 px | 1:1          | Circular crop                  |
| Banner Picture     | 1200x300 px| 4:1          | Cover image on dashboard       |
| Product Gallery    | 600x400 px | 3:2          | For slider/modal               |

## UI Components
### Buttons
- **Primary:** Green background, white text, rounded corners.
- **Secondary:** White background, green border, green text.
- **Disabled:** Gray background, light text.

### Modals
- White background, subtle shadow, rounded corners.
- Close button (X) in top-right.
- Overlay background: semi-transparent black.

### Forms
- Input fields: Light gray border, padding, border-radius.
- Labels: Bold.
- Error messages: Red text.
- Success messages: Green text.

### Product Tile
- Image container: Fixed size, object-fit cover.
- Product name: 16px, medium weight.
- Hover effect: Slight shadow, image zoom.

## Responsive Design
- **Desktop:** Grid with 4 columns.
- **Tablet:** Grid with 2 columns.
- **Mobile:** Grid with 1 column, stacked layout for dashboard.

## Icons
- Use Font Awesome or Dashicons for consistency.

## Accessibility
- Color contrast meets WCAG AA standards.
- Alt text for images.
- Keyboard navigation support.
- ARIA labels for interactive elements.
