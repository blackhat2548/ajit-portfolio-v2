# EmailJS Setup Guide - Detailed Instructions

This guide will help you set up the contact form to send emails directly to your Gmail account without any backend server.

## 📧 What is EmailJS?

EmailJS is a service that allows you to send emails directly from JavaScript without a backend server. It's perfect for static websites and offers:
- **Free tier**: 200 emails/month
- No credit card required
- Easy setup
- Secure email delivery

## 🚀 Complete Setup Process

### Step 1: Create EmailJS Account

1. Go to [https://www.emailjs.com/](https://www.emailjs.com/)
2. Click "Sign Up" (top right)
3. Create account with:
   - Email: `ajitmalik0018@gmail.com` (or your email)
   - Password: (create a strong password)
   - Accept terms and create account
4. Verify your email address

### Step 2: Add Email Service (Gmail)

1. After logging in, click **"Email Services"** in the left sidebar
2. Click **"Add New Service"** button
3. Choose **"Gmail"**
4. Click **"Connect Account"**
5. Select your Gmail account (`ajitmalik0018@gmail.com`)
6. Grant permissions
7. Your **Service ID** will be shown (e.g., `service_abc123`) - **SAVE THIS!**
8. Click "Create Service"

### Step 3: Create Email Template

1. Click **"Email Templates"** in the left sidebar
2. Click **"Create New Template"**
3. Fill in template:

**Template Name:** `Contact Form Submission`

**Subject:**
```
New Contact from {{from_name}} - Portfolio
```

**Content (Body):**
```
You have received a new message from your portfolio contact form!

From: {{from_name}}
Email: {{from_email}}
Subject: {{subject}}

Message:
{{message}}

---
This email was sent from your portfolio website.
Sender's email: {{from_email}}
```

4. Click "Save"
5. Your **Template ID** will be shown (e.g., `template_xyz789`) - **SAVE THIS!**

### Step 4: Get Your Public Key

1. Click your email/profile icon (top right)
2. Click **"Account"**
3. Go to **"General"** tab
4. Find **"Public Key"** section
5. Your public key will look like: `Abc123XYZ456` - **SAVE THIS!**

### Step 5: Update Your JavaScript File

Open the file `js/script.js` and make these changes:

**Find this line (around line 160):**
```javascript
emailjs.init('YOUR_PUBLIC_KEY');
```

**Replace with:**
```javascript
emailjs.init('Abc123XYZ456'); // Your actual public key
```

**Find this line (around line 182):**
```javascript
emailjs.send('YOUR_SERVICE_ID', 'YOUR_TEMPLATE_ID', formData)
```

**Replace with:**
```javascript
emailjs.send('service_abc123', 'template_xyz789', formData)
// Replace with your actual Service ID and Template ID
```

### Complete Example:

```javascript
// Initialize EmailJS
emailjs.init('k8J9mP2nQ5rS6tU7'); // Example public key

// Inside the form submit handler
emailjs.send('service_gmail_123', 'template_contact_456', formData)
    .then(function(response) {
        // Success handling
    }, function(error) {
        // Error handling
    });
```

## ✅ Testing Your Setup

### Test Form Locally:

1. Open `index.html` in your browser
2. Scroll to the contact section
3. Fill in the form:
   - Name: "Test User"
   - Email: "test@example.com"
   - Subject: "Testing Contact Form"
   - Message: "This is a test message"
4. Click "Send Message"
5. Check your email (`ajitmalik0018@gmail.com`)

### Test in EmailJS Dashboard:

1. Go to EmailJS dashboard
2. Click "Email Templates"
3. Select your template
4. Click "Test it" button
5. Fill in test data
6. Click "Send Test Email"

## 🔍 Troubleshooting

### Problem: Form submits but no email received

**Solutions:**
1. Check spam/junk folder
2. Verify Service ID and Template ID are correct
3. Check EmailJS dashboard → "History" for delivery status
4. Make sure Gmail service is properly connected

### Problem: Console shows "Invalid Public Key"

**Solutions:**
1. Double-check public key in `js/script.js`
2. Make sure there are no extra spaces
3. Verify you copied the full key

### Problem: CORS or network errors

**Solutions:**
1. Make sure EmailJS CDN script is loaded in `index.html`
2. Test with HTTPS (not file://)
3. Check browser console for specific errors

### Problem: Rate limit exceeded

**Solution:**
EmailJS free tier allows 200 emails/month. If exceeded:
1. Upgrade to paid plan
2. Wait for next month
3. Create new account (not recommended)

## 📊 Monitoring

### Check Email Delivery:

1. Go to EmailJS dashboard
2. Click "History" in sidebar
3. See all sent emails with status
4. Filter by date, template, or status

### View Statistics:

1. Dashboard shows:
   - Total emails sent
   - Success rate
   - Monthly usage
   - Remaining quota

## 🔒 Security Best Practices

1. **Never commit API keys to public repositories**
   - Public key is safe to expose (it's public)
   - Service ID and Template ID are also safe
   - Private key (if you have one) should never be exposed

2. **Enable reCAPTCHA** (Optional but recommended):
   - Go to "Security" in EmailJS dashboard
   - Enable reCAPTCHA
   - Add reCAPTCHA to your form

3. **Limit Form Submissions**:
   - Add client-side rate limiting
   - Implement honeypot fields for bots

## 💰 Pricing (as of 2026)

**Free Tier:**
- 200 emails/month
- All features
- No credit card required

**Personal ($15/month):**
- 10,000 emails/month
- Priority support

**Business ($30/month):**
- 50,000 emails/month
- Multiple users
- Advanced features

## 📝 Email Template Variables Reference

You can use these variables in your email template:

- `{{from_name}}` - Sender's name
- `{{from_email}}` - Sender's email
- `{{subject}}` - Email subject
- `{{message}}` - Message content
- `{{to_name}}` - Your name (optional)
- `{{reply_to}}` - Reply-to email (optional)

## 🎯 Advanced Configuration

### Auto-Reply to Sender:

Create a second template for auto-reply:

**Template Name:** `Auto Reply`

**Content:**
```
Hi {{from_name}},

Thank you for reaching out! I've received your message and will get back to you within 24-48 hours.

Best regards,
Ajit Malik
```

**Update JavaScript:**
```javascript
// Send to yourself
emailjs.send('service_id', 'template_contact', formData);

// Send auto-reply
emailjs.send('service_id', 'template_autoreply', {
    to_email: formData.from_email,
    from_name: formData.from_name
});
```

### Custom "From" Name:

In your template settings, set:
- From Name: `Portfolio Contact Form`
- From Email: `noreply@emailjs.com`

## 📞 Support

**EmailJS Support:**
- Documentation: [https://www.emailjs.com/docs/](https://www.emailjs.com/docs/)
- Community: [https://community.emailjs.com/](https://community.emailjs.com/)
- Email: support@emailjs.com

**Your Contact:**
- Email: ajitmalik0018@gmail.com
- Phone: +91 7016354226

## ✨ You're All Set!

Once you've completed these steps:
1. Your contact form will send emails directly to your Gmail
2. No backend server needed
3. Works on any static hosting (GitHub Pages, Netlify, Vercel, etc.)
4. Completely free for up to 200 emails/month

Happy coding! 🚀
