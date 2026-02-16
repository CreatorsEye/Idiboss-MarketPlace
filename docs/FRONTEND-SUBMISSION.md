# 📝 Front-End Post Submission

## Overview
Investors, Suppliers, and Marketers can create and manage their own posts directly from their custom dashboards, completely bypassing the WordPress admin. This feature provides an intuitive, seamless experience and reinforces role-specific functionality.

## Submission Interface by Role

### Common Fields (All Roles)
- **Title** (text input)
- **Content** (textarea/WYSIWYG)
- **Image Upload** (multiple, 1-5 images, first becomes featured)

### Supplier-Specific Fields
- Base Price (DA)
- Investor Profit (DA)
- Supplier Fee (DA)
- Final Price (DA)
- Sale Duration (days)

### Investor-Specific Fields
- Base Price (DA)
- Investor Profit (DA)
- Final Price (DA)
- Sale Duration (days)

### Marketer-Specific Fields
- Campaign Name
- Target Audience
- Marketing Content
- Budget (optional)

## AJAX-Based Submission
To ensure a smooth user experience without page reloads, all form submissions are handled via AJAX. The process involves:

- The form is submitted via JavaScript, which sends data to a WordPress AJAX handler.
- The handler verifies the user's capabilities and nonce.
- The post is created using WordPress functions.
- Meta fields and images are saved.
- A JSON response (success or error) is returned and displayed to the user.

## Real-Time Feedback
- **Success/Error Notifications:** Displayed in a message area.
- **Progress Indicators:** Show while uploading/submitting.
- **Post Preview:** Optionally show a preview of the created post.

## Validation and Security
- Nonce verification on all AJAX requests.
- Capability checks before allowing submission.
- Sanitization of all input fields.
- Validation of file types and sizes for image uploads.

## User Experience Considerations
- Forms are styled consistently with the theme (green/white).
- Clear labels and placeholders.
- Inline validation for required fields.
- Responsive design for mobile use.
