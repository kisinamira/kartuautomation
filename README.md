# Karaganda Technical University Website

## Overview

This is a static informational website about Karaganda Technical University (КарТУ), a leading technical university in Kazakhstan. The website provides information about the university, notable alumni, university rankings, and a photo gallery. It is built as a simple static HTML site with CSS styling, served using a lightweight Python HTTP server.

## User Preferences

Preferred communication style: Simple, everyday language.

## System Architecture

### Frontend Architecture

**Static HTML/CSS Design**
- Single-page application using semantic HTML5
- No JavaScript framework or library dependencies
- Content is presented in Russian language
- Uses semantic HTML elements (`<main>`, `<h1>-<h3>`, `<ul>`, `<ol>`, lists, images)
- Responsive design with viewport meta tag for mobile compatibility

**Styling Approach**
- External CSS stylesheet (`css/style.css`)
- Modern CSS features including:
  - CSS box model reset with universal selector
  - Gradient backgrounds using `linear-gradient`
  - Box shadows and border-radius for visual depth
  - Custom typography with fallback font stack
  - Color scheme based on blue tones (#1a4d8f, #2563eb, #3b82f6)

**Content Structure**
- University overview section
- Notable alumni list (unordered list)
- University rankings (ordered list with external link)
- Image gallery section with three university photos

### Backend Architecture

**Development Server**
- Python-based HTTP server using built-in `http.server` and `socketserver` modules
- Custom request handler (`NoCacheHTTPRequestHandler`) extends `SimpleHTTPRequestHandler`
- Implements cache prevention headers to ensure fresh content during development
- Serves on port 5000 and binds to all interfaces (0.0.0.0)

**Rationale**: A simple Python server was chosen for local development and testing, avoiding the need for complex server configurations. The no-cache headers ensure that changes to HTML/CSS are immediately visible during development.

**Alternatives Considered**: 
- Node.js live-server or http-server packages
- Apache/Nginx for production deployment
- Python Flask/FastAPI for more complex server needs

**Pros**: Simple, no dependencies beyond Python standard library, easy to understand
**Cons**: Not suitable for production, lacks HTTPS, limited features

## External Dependencies

### Runtime Dependencies
- **Python 3.x**: Required to run the development server (standard library modules only)

### Static Assets
- **Images**: Three PNG images referenced in the gallery section:
  - `images/kartu_main.png` - Main university building
  - `images/kartu_campus.png` - Campus view
  - `images/kartu_students.png` - Students
  - Note: An alternate HTML file references .jpg versions of these images

### External Links
- **QS World University Rankings**: Link to TopUniversities.com for Karaganda Technical University profile

### Browser Requirements
- Modern web browser with HTML5 and CSS3 support
- No JavaScript required for core functionality

### File Structure
```
/
├── index.html           # Main HTML page
├── server.py            # Development server
├── css/
│   └── style.css        # Stylesheet (partial file in repository)
├── images/              # Image assets directory (referenced but not in repo)
│   ├── kartu_main.png
│   ├── kartu_campus.png
│   └── kartu_students.png
└── attached_assets/     # Alternative version of HTML
    └── КарТУ_1762409224370.html
```