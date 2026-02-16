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
To ensure a smooth user experience without page reloads, all form submissions are handled via AJAX.

### JavaScript Example
```javascript
jQuery('#post-submission-form').on('submit', function(e) {
    e.preventDefault();
    var formData = new FormData(this);
    formData.append('action', 'handle_frontend_post_submission');
    formData.append('nonce', frontendAjax.nonce);
    
    jQuery.ajax({
        url: frontendAjax.ajaxurl,
        type: 'POST',
        data: formData,
        processData: false,
        contentType: false,
        success: function(response) {
            if (response.success) {
                // Show success message
                jQuery('#form-message').html('<div class="success">Post created!</div>');
                // Optionally reset form or update list
            } else {
                jQuery('#form-message').html('<div class="error">' + response.data + '</div>');
            }
        },
        error: function() {
            jQuery('#form-message').html('<div class="error">An error occurred.</div>');
        }
    });
});
