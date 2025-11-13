# Christopher Dixon - Portfolio Website

A professional portfolio website showcasing full-stack software engineering projects and expertise.

## Features

- **Responsive Design**: Mobile-first approach with smooth animations and parallax effects
- **Interactive Portfolio**: Lightbox gallery for project showcase
- **Working Contact Form**: Integrated with Formspree for email handling
- **SEO Optimized**: Complete meta tags, Open Graph, and structured data
- **Accessible**: Screen reader friendly with proper ARIA labels and semantic HTML
- **Performance**: Optimized images and efficient CSS/JS loading

## Technologies Used

- **Frontend**: HTML5, CSS3 (SASS), JavaScript (jQuery)
- **Template**: Strata by HTML5 UP
- **Form Handling**: Formspree integration
- **Icons**: Font Awesome
- **Fonts**: Google Fonts (Source Sans Pro)

## Setup Instructions

### For Development

1. Clone the repository:
   ```bash
   git clone https://github.com/JukemJ/JukemJ.github.io.git
   cd JukemJ.github.io
   ```

2. Open `index.html` in your web browser or use a local server:
   ```bash
   # Using Python
   python -m http.server 8000
   
   # Using Node.js
   npx http-server
   
   # Using PHP
   php -S localhost:8000
   ```

3. Navigate to `http://localhost:8000` to view the site

### Contact Form Setup

The contact form is configured to work with Formspree. To set up your own:

1. Sign up at [Formspree.io](https://formspree.io)
2. Create a new form endpoint
3. Update the form action in `index.html`:
   ```html
   <form method="post" action="https://formspree.io/f/YOUR_FORM_ID">
   ```

### Customization

#### Update Personal Information
- Edit contact details in the "Get In Touch" section
- Replace social media links in the footer
- Update the bio and professional summary

#### Add New Projects
- Add project images to `images/fulls/` and `images/thumbs/`
- Update the portfolio section in `index.html`
- Include project descriptions with technology stacks

#### Modify Styling
- Main styles: `assets/css/main.css`
- SASS source files: `assets/sass/`
- Compile SASS: `sass assets/sass/main.scss assets/css/main.css`

## Project Structure

```
├── index.html              # Main HTML file
├── assets/
│   ├── css/
│   │   ├── main.css        # Compiled styles
│   │   └── fontawesome-all.min.css
│   ├── js/
│   │   ├── main.js         # Custom JavaScript + form handling
│   │   ├── jquery.min.js   # jQuery library
│   │   └── other libraries
│   ├── sass/               # SASS source files
│   └── webfonts/          # Font Awesome fonts
├── images/
│   ├── fulls/             # Full-size portfolio images
│   ├── thumbs/            # Thumbnail images
│   └── avatar.jpg         # Profile picture
└── README.md              # This file
```

## Browser Support

- Chrome (latest)
- Firefox (latest)
- Safari (latest)
- Edge (latest)
- Internet Explorer 11+

## Performance Optimization

- Images are optimized for web
- CSS and JavaScript are minified
- Font loading is optimized
- Responsive images with proper sizing

## License

Design based on Strata by HTML5 UP, licensed under CCA 3.0.
Custom code and content © Christopher Dixon.

## Contact

- **Website**: [dixn.dev](https://dixn.dev)
- **Email**: chris@dixn.dev
- **GitHub**: [JukemJ](https://github.com/JukemJ)
- **LinkedIn**: [chris-dixn](https://linkedin.com/in/chris-dixn)