# Landing Page Maintenance Guide

This guide will help you maintain and customize the Stomerij Monster landing page. Whether you're new to web development or need a quick reference, follow these instructions to make common updates safely and effectively.

## Table of Contents
1. [Updating Text and Styling](#updating-text-and-styling)
2. [Managing Links](#managing-links)
3. [Adding Privacy and Terms Pages](#adding-privacy-and-terms-pages)
4. [Troubleshooting](#troubleshooting)

## Updating Text and Styling

### Main Sections Overview
The landing page consists of these key sections:
- Header (Navigation)
- Hero Section
- Features Section
- FAQ Section
- Contact Section
- Footer

### Updating Text Content

#### Hero Section
To update the main headline, locate this section:
```html
<h1 class="text-4xl md:text-5xl lg:text-6xl font-bold text-gray-900 leading-tight mb-6">
    Stomerij Monster
    <span class="block text-blue-600 mt-2">Gratis Halen en Brengen</span>
</h1>
```
Simply replace the text while keeping the HTML tags intact.

#### Features Section
Each feature card follows this structure:
```html
<div class="bg-white p-8 rounded-2xl shadow-lg hover:shadow-xl transition-shadow duration-300">
    <h3 class="text-xl font-bold text-gray-900 mb-4">Gratis Ophaal- en Bezorgservice</h3>
    <p class="text-gray-600">Wij halen uw kleding gratis op en bezorgen deze weer schoon bij u thuis.</p>
</div>
```
To update a feature:
1. Find the feature card you want to change
2. Modify the text between the `<h3>` tags for the title
3. Modify the text between the `<p>` tags for the description

### Modifying Tailwind CSS Classes

#### Understanding Key Classes
- `container`: Centers content and sets max-width
- `mx-auto`: Centers elements horizontally
- `px-4`: Adds horizontal padding
- `py-24`: Adds vertical padding
- `text-xl`: Sets font size
- `font-bold`: Makes text bold
- `text-gray-600`: Sets text color

#### Responsive Design Classes
The site uses these breakpoints:
- `md:`: Applied at medium screens (768px+)
- `lg:`: Applied at large screens (1024px+)

Example:
```html
<div class="text-xl md:text-2xl lg:text-3xl">
```
This makes text larger as screen size increases.

## Managing Links

### Navigation Menu Links
Current navigation links are in two places:

1. Desktop Navigation:
```html
<div class="hidden md:flex space-x-8">
    <a href="#diensten" class="text-gray-600 hover:text-blue-600">Diensten</a>
    <a href="#voordelen" class="text-gray-600 hover:text-blue-600">Voordelen</a>
    <a href="#faq" class="text-gray-600 hover:text-blue-600">FAQ</a>
    <a href="#contact" class="text-gray-600 hover:text-blue-600">Contact</a>
</div>
```

2. Mobile Navigation:
```html
<div x-show="isOpen" class="md:hidden mt-4">
    <!-- Same links as desktop, must update both places -->
</div>
```

To update a link:
1. Locate the link in both desktop and mobile sections
2. Change the `href` attribute to your new destination
3. Update the link text between the `<a>` tags

### External Links
The main external link to update is:
```html
<a href="https://stomerijmonster.nl" class="bg-blue-600 text-white px-6 py-2">
    Direct Reserveren
</a>
```
Replace `https://stomerijmonster.nl` with your desired URL.

## Adding Privacy and Terms Pages

### Step 1: Add Footer Links
Locate the footer section and add new links:
```html
<div class="grid grid-cols-1 md:grid-cols-3 gap-8">
    <div>
        <h3 class="text-xl font-bold mb-4">Links</h3>
        <ul class="space-y-2">
            <!-- Add these new lines -->
            <li><a href="privacy.html" class="text-gray-400 hover:text-white transition-colors duration-300">Privacy Policy</a></li>
            <li><a href="terms.html" class="text-gray-400 hover:text-white transition-colors duration-300">Terms of Service</a></li>
        </ul>
    </div>
</div>
```

### Step 2: Create New Pages
1. Create `privacy.html` and `terms.html` in your root directory
2. Copy the header and footer from `index.html` to maintain consistency
3. Add your privacy and terms content between them

## Troubleshooting

### Common Issues

1. **Broken Links**
- Check that all `href` attributes start with either:
  - `#` for same-page links
  - `https://` for external links
  - Relative paths (`privacy.html`) for local pages

2. **Responsive Design Issues**
- If elements look wrong on mobile:
  - Check for `md:` and `lg:` classes
  - Ensure mobile menu is working
  - Test all breakpoints in browser dev tools

3. **Styling Problems**
- If styles aren't applying:
  - Verify Tailwind CSS link in header is working
  - Check class names for typos
  - Ensure classes are in the correct order

### Need Help?
- Use browser dev tools to inspect elements
- Check the Tailwind CSS documentation for class references
- Verify all JavaScript dependencies are loading
- Test all changes across different browsers and devices

Remember to always backup your files before making changes, and test thoroughly after each modification.