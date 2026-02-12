# Ajit Malik - Portfolio Website

A modern, dynamic portfolio website showcasing customer success and operations expertise with animated backgrounds, interactive elements, and a working contact form.

## 🌟 Features

- **Modern Design**: Clean, professional design with gradient effects and animations
- **Responsive Layout**: Fully responsive design that works on all devices
- **Interactive Animations**: Particle effects, floating shapes, and scroll animations
- **Working Contact Form**: Email integration without backend using EmailJS
- **Sections Include**:
  - Hero section with animated profile
  - Skills showcase with detailed competencies
  - Professional experience timeline
  - Certifications display
  - Contact form with real-time email delivery

## 📁 Project Structure

```
portfolio-website/
├── index.html          # Main HTML file
├── css/
│   └── style.css       # All styling
├── js/
│   └── script.js       # JavaScript for animations and contact form
└── README.md          # This file
```

## 🚀 Quick Start

### 1. Clone or Download

```bash
git clone https://github.com/Ajitmalik18/portfolio-website.git
cd portfolio-website
```

### 2. Set Up Contact Form (EmailJS)

The contact form uses **EmailJS** - a free service that sends emails without a backend server.

#### Step-by-Step Setup:

1. **Create EmailJS Account**
   - Go to [EmailJS](https://www.emailjs.com/)
   - Sign up for a free account (Free tier: 200 emails/month)

2. **Add Email Service**
   - In EmailJS dashboard, click "Add New Service"
   - Choose Gmail (or your preferred email provider)
   - Connect your Gmail account
   - Note down your **Service ID** (e.g., `service_abc123`)

3. **Create Email Template**
   - Go to "Email Templates"
   - Click "Create New Template"
   - Use this template structure:

   ```
   Subject: New Contact from {{from_name}}
   
   From: {{from_name}}
   Email: {{from_email}}
   Subject: {{subject}}
   
   Message:
   {{message}}
   ```

   - Note down your **Template ID** (e.g., `template_xyz789`)

4. **Get Public Key**
   - Go to "Account" → "General"
   - Copy your **Public Key** (e.g., `Abc123XYZ456`)

5. **Update JavaScript File**
   - Open `js/script.js`
   - Replace the placeholders:

   ```javascript
   // Line 160: Replace with your Public Key
   emailjs.init('YOUR_PUBLIC_KEY');
   
   // Line 182: Replace with your Service ID and Template ID
   emailjs.send('YOUR_SERVICE_ID', 'YOUR_TEMPLATE_ID', formData)
   ```

   Example:
   ```javascript
   emailjs.init('Abc123XYZ456');
   emailjs.send('service_gmail123', 'template_contact456', formData)
   ```

### 3. Test Locally

Simply open `index.html` in your web browser. The contact form will work immediately after EmailJS setup.

### 4. Deploy to GitHub Pages

1. **Create GitHub Repository**
   ```bash
   git init
   git add .
   git commit -m "Initial commit"
   git branch -M main
   git remote add origin https://github.com/YOUR_USERNAME/portfolio-website.git
   git push -u origin main
   ```

2. **Enable GitHub Pages**
   - Go to your repository on GitHub
   - Click "Settings" → "Pages"
   - Under "Source", select "main" branch
   - Click "Save"
   - Your site will be live at: `https://YOUR_USERNAME.github.io/portfolio-website/`

## 🎨 Customization

### Update Personal Information

Edit `index.html` to update:
- Name and title
- Skills and experience
- Social media links
- Phone number and email
- Certifications

### Change Colors

Edit `css/style.css` - update CSS variables:

```css
:root {
    --primary: #6366f1;     /* Main purple/blue */
    --secondary: #8b5cf6;   /* Secondary purple */
    --accent: #ec4899;      /* Pink accent */
    --cyan: #06b6d4;        /* Cyan accent */
    --dark: #0f172a;        /* Dark background */
    --light: #f8fafc;       /* Light text */
}
```

### Modify Animations

Adjust animation speeds in `css/style.css`:
- `float-diagonal`: Floating shapes animation
- `pulse-orb`: Gradient orbs pulsing
- `rotate-logo`: Logo rotation

## 📧 Contact Form Configuration

### Email Template Variables

The contact form sends these variables to your email:

- `{{from_name}}` - Sender's name
- `{{from_email}}` - Sender's email
- `{{subject}}` - Message subject
- `{{message}}` - Message content
- `{{to_name}}` - Your name (Ajit Malik)

### Troubleshooting Contact Form

**Form not sending?**
1. Check browser console (F12) for errors
2. Verify EmailJS keys are correct
3. Make sure you're not exceeding free tier limit (200 emails/month)
4. Check EmailJS dashboard for failed deliveries

**Not receiving emails?**
1. Check spam folder
2. Verify Gmail service is connected in EmailJS
3. Test with EmailJS's test feature in dashboard

## 🔧 Technical Details

### Technologies Used
- HTML5
- CSS3 (with CSS Variables and Animations)
- Vanilla JavaScript
- EmailJS for contact form
- Font Awesome for icons
- Google Fonts (Poppins)

### Browser Compatibility
- Chrome (latest)
- Firefox (latest)
- Safari (latest)
- Edge (latest)
- Mobile browsers

## 📱 Responsive Breakpoints

- Desktop: > 768px
- Tablet: 481px - 768px
- Mobile: ≤ 480px

## 🎯 Performance Optimizations

- Minimal external dependencies
- CSS animations use GPU acceleration
- Optimized particle count for performance
- Lazy loading for animations (Intersection Observer)

## 📄 License

This project is open source and available under the MIT License.

## 👤 Contact

**Ajit Malik**
- Email: ajitmalik0018@gmail.com
- Phone: +91 7016354226
- LinkedIn: [linkedin.com/in/ajitmalik](https://linkedin.com/in/ajitmalik)
- GitHub: [github.com/Ajitmalik18](https://github.com/Ajitmalik18)

## 🙏 Acknowledgments

- Font Awesome for icons
- Google Fonts for typography
- EmailJS for contact form functionality

---

Made with ❤️ by Ajit Malik
