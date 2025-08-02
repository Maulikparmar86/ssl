# SSL Checker Pro - Centralized Structure

## Overview
This project has been reorganized to use a centralized structure with shared CSS, JavaScript, header, and footer files.

## File Structure

### CSS Files
- `css/style.css` - Main stylesheet with all styles organized by sections
- `css/shared.css` - Legacy shared styles (can be removed)

### JavaScript Files
- `js/main.js` - Main JavaScript file with all functionality
- Navigation functions
- Form handlers
- Mobile menu
- Tool interactions

### Includes
- `includes/header.html` - Centralized header with navigation
- `includes/footer.html` - Centralized footer with links and branding

### Templates
- `template.html` - Template for new pages
- `index.html` - Updated home page using centralized structure

## How to Use

### For New Pages
1. Copy `template.html` as your starting point
2. Update the title and meta description
3. Add your content in the main section
4. The header and footer will be automatically loaded

### For Existing Pages
1. Replace the `<style>` section with: `<link rel="stylesheet" href="css/style.css">`
2. Replace the `<script>` section with: `<script src="js/main.js"></script>`
3. Add header placeholder: `<div id="header-placeholder"></div>`
4. Add footer placeholder: `<div id="footer-placeholder"></div>`
5. Add the header/footer loading script

### Example Structure
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Your Page - SSL Checker Pro</title>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700;800&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="css/style.css">
</head>
<body>
    <!-- Include Header -->
    <div id="header-placeholder"></div>

    <!-- Main Content -->
    <main class="main-content">
        <div class="container">
            <!-- Your content here -->
        </div>
    </main>

    <!-- Include Footer -->
    <div id="footer-placeholder"></div>

    <!-- Load JavaScript -->
    <script src="js/main.js"></script>
    
    <!-- Load Header and Footer -->
    <script>
        fetch('includes/header.html')
            .then(response => response.text())
            .then(data => {
                document.getElementById('header-placeholder').innerHTML = data;
            });

        fetch('includes/footer.html')
            .then(response => response.text())
            .then(data => {
                document.getElementById('footer-placeholder').innerHTML = data;
            });
    </script>
</body>
</html>
```

## Benefits
- **Consistency**: All pages use the same header and footer
- **Maintainability**: Changes to header/footer only need to be made in one place
- **Performance**: CSS and JS are cached across pages
- **Organization**: Clean separation of concerns

## CSS Classes Available
- `.container` - Main content container
- `.tool-header` - Tool page header
- `.tool-interface` - Tool form container
- `.form-group` - Form field group
- `.form-label` - Form label
- `.form-input` - Form input
- `.submit-btn` - Submit button
- `.results-section` - Results container
- `.result-item` - Individual result item
- `.back-btn` - Back button

## JavaScript Functions Available
- `showPage(pageId)` - Navigate between pages
- `showTool(toolId)` - Navigate to specific tools
- `scrollToTools()` - Scroll to tools section
- Form handlers for SSL checker and CSR generator 