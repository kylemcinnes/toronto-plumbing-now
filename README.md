# Toronto Plumbing Now - Lead Generation Site

A professional, mobile-first lead generation website designed for Toronto-based plumbing companies. This site is built to capture high-intent plumbing leads and is available for exclusive rental.

## 🌟 Features

### A1. Call Tracking Button
- **Mobile Floating Button**: Prominent floating call button on mobile devices
- **Phone Number**: `+1-416-555-0199` (placeholder - update with real number)
- **CTA Text**: "Call Now for a Licensed Toronto Plumber"
- **JavaScript Tracking**: Console logging for analytics integration (CallRail, Google Analytics ready)

### A2. Lead Capture Form
- **Complete Contact Form** with all required fields:
  - Name (required)
  - Phone Number (required)
  - Email (optional)
  - Service Type Dropdown (Drain Cleaning, Emergency Plumbing, Clogged Toilet, Sump Pump, Other)
  - Zip/Postal Code (required)
  - Message (optional)
- **Formspree Integration**: POST action to `https://formspree.io/f/your-form-id`
- **Form Validation**: Client-side validation with required field indicators
- **Success Handling**: Confirmation message and form reset
- **Debug Logging**: JSON console output for form submissions

### A3. Local SEO-Friendly Structure
- **HTML5 Semantic Markup**: Proper heading hierarchy and semantic elements
- **Optimized Meta Tags**:
  - Title: "Licensed & Affordable Plumbers in Toronto | Toronto Plumbing Now"
  - Description: "Need an emergency plumber in Toronto? Get fast, licensed, affordable service from trusted professionals. Call us now or request a quote."
- **Structured Data**: JSON-LD LocalBusiness schema with:
  - Business information
  - Address and coordinates
  - Service offerings
  - Operating hours
- **Local Keywords**: Optimized content for:
  - Emergency Plumbing
  - Drain Cleaning
  - Backflow Testing
  - Commercial Plumbing
  - Clogged Drains Toronto
- **Service Area Pages**: Placeholder sections for Toronto neighborhoods

### A4. Mobile-First Design
- **Responsive Layout**: Bootstrap 5 with custom CSS
- **Mobile Optimization**: Floating call button, touch-friendly interface
- **Performance Focused**: Vanilla CSS, system fonts, optimized images
- **Professional Blue Theme**: Consistent plumbing industry color scheme
- **Visual Hierarchy**: Dominant CTAs for calls and quotes

### A5. "Rent This Site" Page
- **Dedicated Rental Page**: `/rent-this-site.html`
- **Lead Generation Platform Info**: Explains the rental opportunity
- **Inquiry Form**: Company details, contact info, service areas
- **Site Performance Stats**: Visual representation of site capabilities

## 📁 File Structure

```
toronto-plumbing-now/
├── index.html              # Main landing page
├── rent-this-site.html     # Site rental inquiry page
├── README.md              # This documentation
└── favicon.ico            # Site favicon (to be added)
```

## 🚀 Setup Instructions

### 1. Basic Setup
1. Upload all files to your web server
2. Update the phone number in `index.html` (search for `+1-416-555-0199`)
3. Replace Formspree form IDs:
   - Main form: `your-form-id` in `index.html`
   - Rental form: `your-rental-form-id` in `rent-this-site.html`

### 2. Formspree Configuration
1. Create a free account at [Formspree.io](https://formspree.io)
2. Create two forms:
   - Main lead capture form
   - Rental inquiry form
3. Replace the placeholder form IDs in both HTML files

### 3. Analytics Integration
The site is ready for:
- **CallRail**: Add tracking code to `handleCallClick()` function
- **Google Analytics**: Add GA4 tracking code
- **Google Tag Manager**: Add GTM container code

### 4. Customization Options

#### Phone Number
```html
<!-- Update in index.html -->
<a href="tel:+1-416-555-0199" class="btn btn-primary btn-lg" onclick="handleCallClick()">
    📞 Call Now: (416) 555-0199
</a>

<!-- Update in rent-this-site.html -->
<p>📞 (416) 555-0199</p>
```

#### Formspree Form IDs
```html
<!-- Main form in index.html -->
<form id="leadForm" action="https://formspree.io/f/your-form-id" method="POST">

<!-- Rental form in rent-this-site.html -->
<form id="rentalForm" action="https://formspree.io/f/your-rental-form-id" method="POST">
```

#### Business Information
Update the structured data in `index.html`:
```json
{
    "name": "Toronto Plumbing Now",
    "telephone": "+1-416-555-0199",
    "address": {
        "streetAddress": "123 Main Street",
        "addressLocality": "Toronto",
        "addressRegion": "ON",
        "postalCode": "M5V 3A8"
    }
}
```

## 🎨 Design Features

### Color Scheme
- **Primary Blue**: `#0056b3`
- **Secondary Blue**: `#007bff`
- **Accent Blue**: `#e3f2fd`
- **Dark Blue**: `#003d82`

### Typography
- **System Fonts**: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto
- **Responsive Sizing**: Mobile-optimized font sizes
- **Professional Hierarchy**: Clear heading structure

### Interactive Elements
- **Hover Effects**: Smooth transitions on buttons and cards
- **Mobile Call Button**: Fixed position, prominent styling
- **Form Validation**: Real-time feedback and required field indicators
- **Smooth Scrolling**: Navigation link behavior

## 📱 Mobile Optimization

### Responsive Breakpoints
- **Mobile**: < 768px
- **Tablet**: 768px - 992px
- **Desktop**: > 992px

### Mobile-Specific Features
- Floating call button (hidden on desktop)
- Touch-friendly button sizes
- Optimized form layout
- Reduced padding and margins

## 🔧 Technical Details

### Dependencies
- **Bootstrap 5.3.0**: CDN-loaded for responsive grid and components
- **Vanilla JavaScript**: No additional JS libraries required
- **CSS Custom Properties**: Modern CSS with custom variables

### Performance Optimizations
- **CDN Resources**: Bootstrap loaded from CDN
- **System Fonts**: No external font loading
- **Optimized Images**: Unsplash integration for placeholder images
- **Minimal JavaScript**: Lightweight, efficient code

### SEO Features
- **Meta Tags**: Complete Open Graph and standard meta tags
- **Structured Data**: JSON-LD schema markup
- **Semantic HTML**: Proper heading hierarchy and landmarks
- **Local Keywords**: Toronto-specific plumbing terms

## 📞 Call Tracking Integration

### Current Implementation
```javascript
function handleCallClick() {
    console.log('Call button clicked - Phone: +1-416-555-0199');
    // Future integration: CallRail, Google Analytics, etc.
}
```

### CallRail Integration Example
```javascript
function handleCallClick() {
    // CallRail tracking
    if (typeof CallRail !== 'undefined') {
        CallRail.track('clicked_call_button');
    }
    
    // Google Analytics tracking
    if (typeof gtag !== 'undefined') {
        gtag('event', 'click', {
            'event_category': 'engagement',
            'event_label': 'call_button'
        });
    }
}
```

## 📊 Analytics Setup

### Google Analytics 4
Add to `<head>` section:
```html
<!-- Google tag (gtag.js) -->
<script async src="https://www.googletagmanager.com/gtag/js?id=GA_MEASUREMENT_ID"></script>
<script>
  window.dataLayer = window.dataLayer || [];
  function gtag(){dataLayer.push(arguments);}
  gtag('js', new Date());
  gtag('config', 'GA_MEASUREMENT_ID');
</script>
```

### Google Tag Manager
Add to `<head>` section:
```html
<!-- Google Tag Manager -->
<script>(function(w,d,s,l,i){w[l]=w[l]||[];w[l].push({'gtm.start':
new Date().getTime(),event:'gtm.js'});var f=d.getElementsByTagName(s)[0],
j=d.createElement(s),dl=l!='dataLayer'?'&l='+l:'';j.async=true;j.src=
'https://www.googletagmanager.com/gtm.js?id='+i+dl;f.parentNode.insertBefore(j,f);
})(window,document,'script','dataLayer','GTM-XXXXXXX');</script>
```

## 🚀 Deployment

### Recommended Hosting
- **Netlify**: Easy deployment with form handling
- **Vercel**: Fast static site hosting
- **GitHub Pages**: Free hosting for static sites
- **Traditional Web Hosting**: Any standard web hosting service

### Domain Setup
- **Primary Domain**: `torontoplumbingnow.com`
- **SSL Certificate**: Required for form submissions
- **DNS Configuration**: Point to hosting provider

## 📝 Customization Checklist

Before going live, ensure you've updated:

- [ ] Phone number in all locations
- [ ] Formspree form IDs
- [ ] Business address in structured data
- [ ] Company name and branding
- [ ] Analytics tracking codes
- [ ] Call tracking integration
- [ ] Favicon file
- [ ] Meta descriptions and titles
- [ ] Service area information

## 📞 Support

This site is designed as a lead generation platform for Toronto plumbing companies. For technical support or customization requests, contact the developer.

---

**Disclaimer**: This site is not owned or operated by a plumbing company. It is an independent lead generation platform available for rental to qualified Toronto-based plumbing businesses. 