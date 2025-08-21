# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a static personal website for Christian Peters (empleh.github.io), hosted on GitHub Pages. The site is a multi-page portfolio showcasing speaking engagements, content creation, and book recommendations.

## Site Architecture

### Page Structure
- **Root (`/`)**: Main landing page with profile, recent content, and contact
- **Speaking (`/speaking`)**: Speaking engagements and presentations  
- **One Idea (`/one-idea`)**: Book reviews with key takeaways
- **Videos (`/videos`)**: Simple redirect to YouTube channel

### File Organization
```
/
├── index.html              # Main homepage
├── styles.css              # Global styles for entire site
├── images/                 # Profile and content images
├── speaking/index.html     # Speaking engagements page
├── one-idea/index.html     # Book recommendations page
└── videos/index.html       # YouTube redirect
```

## CSS Design System

### CSS Custom Properties (Variables)
The site uses a comprehensive design system defined in `:root`:
- **Colors**: `--primary-color` (#ffdd00), `--secondary-color` (#ffc107), `--accent-color` (#3a7bd5)
- **Dark mode**: Automatic via `@media (prefers-color-scheme: dark)`
- **Spacing**: Consistent margin/padding patterns
- **Transitions**: `--transition: all 0.3s ease`

### Component Classes
- `.card`: Main content containers with hover effects
- `.content-card`: Featured content with images
- `.talk-card`, `.book-card`: Specialized cards for different content types
- `.link-btn`: Primary button styling with hover animations
- `.social-icon`: Circular social media icons
- `.navigation`: Header navigation with active states

### Responsive Design
- Mobile-first approach with `@media` queries at 768px and 1024px
- Grid layouts that collapse to single column on mobile
- Flexible image sizing and typography scaling

## Development Workflow

### Making Changes
1. Edit HTML files directly (no build process required)
2. Update `styles.css` for styling changes
3. Test locally by opening HTML files in browser
4. All pages share the same CSS file - changes affect entire site

### Adding New Pages
1. Create new directory with `index.html`
2. Copy header/footer structure from existing pages
3. Update navigation links in all pages
4. Use existing CSS classes for consistency

### Image Management
- Store images in `/images/` directory
- Use relative paths: `../images/filename.jpg` for subpages
- External images (YouTube thumbnails, etc.) linked directly

## Content Patterns

### Navigation
Each page includes consistent navigation in header:
```html
<div class="navigation">
    <a href="/" class="nav-link [active]">Home</a>
    <a href="/speaking" class="nav-link [active]">Speaking</a>
    <a href="/one-idea" class="nav-link [active]">One Idea</a>
</div>
```

### Email Reveal Function
All pages include JavaScript function for email contact:
```javascript
function revealEmail() {
    var username = 'christian.peters';
    var domain = 'gmail.com';
    window.location.href = 'mailto:' + username + '@' + domain;
}
```

### Content Cards
Use `.content-card`, `.talk-card`, or `.book-card` for structured content with images and text.

## Deployment

This is a GitHub Pages site - changes pushed to main branch are automatically deployed. No build process or CI/CD pipeline required.