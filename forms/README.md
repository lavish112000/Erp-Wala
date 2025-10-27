# Email Forms Setup Guide

This directory contains three separate form pages for lead capture with EmailJS integration.

## 📁 Form Pages

1. **demo-request.html** - Simple demo request form (Blue theme)
2. **personalized-demo.html** - Personalized demo with date selection (Purple theme)
3. **free-consultation.html** - Detailed consultation form (Green theme)

## 🔧 EmailJS Configuration

### Step 1: Get Your EmailJS Public Key

1. Go to [EmailJS Dashboard](https://dashboard.emailjs.com/)
2. Sign up or log in
3. Go to **Account** → **General**
4. Copy your **Public Key**

### Step 2: Create Email Template

1. In EmailJS Dashboard, go to **Email Templates**
2. Click **Create New Template**
3. Use this template structure:

```
New Form Submission: {{form_type}}

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
📋 SUBMISSION DETAILS
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

👤 Full Name:          {{full_name}}
📧 Email:              {{email}}
📞 Phone:              {{phone}}
🏫 Institution:        {{institution_name}}

{{#preferred_date}}
📅 Preferred Date:     {{preferred_date}}
{{/preferred_date}}

{{#role}}
💼 Role:               {{role}}
{{/role}}

{{#number_of_students}}
👥 Number of Students: {{number_of_students}}
{{/number_of_students}}

{{#requirements}}
📝 Requirements:
{{requirements}}
{{/requirements}}

{{#message}}
💬 Message:
{{message}}
{{/message}}

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
🕐 Submitted: {{submission_date}}
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
```

4. Save the template and copy the **Template ID**

### Step 3: Update Form Files

Replace the placeholders in all three form files:

#### In `demo-request.html`, `personalized-demo.html`, and `free-consultation.html`:

**Line with `emailjs.init`:**
```javascript
emailjs.init('YOUR_PUBLIC_KEY'); // Replace with your EmailJS public key
```
👉 Replace `YOUR_PUBLIC_KEY` with your actual public key

**Line with `emailjs.send`:**
```javascript
emailjs.send('service_x4eo2tt', 'YOUR_TEMPLATE_ID', templateParams)
```
👉 Replace `YOUR_TEMPLATE_ID` with your template ID

## ✅ Complete Configuration Example

```javascript
// Initialize EmailJS
emailjs.init('abcd1234XYZ'); // Your public key

// Send email
emailjs.send('service_x4eo2tt', 'template_abc123', templateParams)
```

## 🎨 Form Features

### All Forms Include:
- ✅ **Honeypot spam protection** (hidden field to catch bots)
- ✅ **Loading states** with spinner animation
- ✅ **Success/Error messages** with icons
- ✅ **Form validation** (required fields)
- ✅ **Smooth animations** (slide-in effect)
- ✅ **Back to home** link
- ✅ **Responsive design** (mobile-friendly)

### Form-Specific Fields:

#### 1. Demo Request Form
- Full Name
- Email
- Phone
- Institution Name

#### 2. Personalized Demo Form
- Full Name
- Email
- Phone
- Institution Name
- **Preferred Date** (date picker with min date = today)
- **Requirements** (optional textarea)

#### 3. Free Consultation Form
- Full Name
- Email
- Phone
- Institution Name
- **Role** (dropdown: Principal, Administrator, IT Manager, Teacher, Other)
- **Number of Students** (dropdown: 1-100, 101-500, 501-1000, 1000+)
- **Message** (optional textarea)

## 🔗 Integration with Main Site

The buttons in `index.html` are connected to these forms:

1. **Header "Request a Demo"** → `forms/demo-request.html`
2. **Hero "Book a Personalized Demo"** → `forms/personalized-demo.html`
3. **CTA "Schedule My Free Consultation"** → `forms/free-consultation.html`

## 🧪 Testing

1. Fill out a form with test data
2. Check EmailJS Dashboard → **Logs** to see if the email was sent
3. Check your inbox for the formatted email

## 🎯 Template Parameters

Each form sends these parameters to EmailJS:

| Parameter | Demo Request | Personalized Demo | Free Consultation |
|-----------|--------------|-------------------|-------------------|
| form_type | ✅ | ✅ | ✅ |
| full_name | ✅ | ✅ | ✅ |
| email | ✅ | ✅ | ✅ |
| phone | ✅ | ✅ | ✅ |
| institution_name | ✅ | ✅ | ✅ |
| preferred_date | ❌ | ✅ | ❌ |
| requirements | ❌ | ✅ | ❌ |
| role | ❌ | ❌ | ✅ |
| number_of_students | ❌ | ❌ | ✅ |
| message | ❌ | ❌ | ✅ |
| submission_date | ✅ | ✅ | ✅ |

## 🚀 Going Live

### Final Checklist:
- [ ] Replace `YOUR_PUBLIC_KEY` in all 3 forms
- [ ] Replace `YOUR_TEMPLATE_ID` in all 3 forms
- [ ] Test each form submission
- [ ] Verify emails are received
- [ ] Check email formatting
- [ ] Test on mobile devices
- [ ] Verify spam protection works

## 📧 Email Service Details

- **Service ID**: `service_x4eo2tt` (Already configured)
- **Template ID**: You need to create and add yours
- **Public Key**: You need to add yours

## 🔒 Security Features

1. **Honeypot Field**: Hidden field that bots fill out, real users don't see
2. **Client-side Validation**: Required fields, email format, phone format
3. **EmailJS Rate Limiting**: Built-in protection against spam
4. **No Backend Required**: Secure, serverless email delivery

## 💡 Customization

### Change Form Colors:
- Blue theme → Update `focus:ring-blue-500`, `bg-blue-600`
- Purple theme → Update `focus:ring-purple-500`, `bg-purple-600`
- Green theme → Update `focus:ring-green-500`, `bg-green-600`

### Add More Fields:
1. Add HTML input in the form
2. Add the field name to `templateParams` object
3. Update EmailJS template to include `{{field_name}}`

## 📞 Support

If you encounter issues:
1. Check browser console for errors
2. Verify EmailJS credentials are correct
3. Check EmailJS dashboard logs
4. Ensure template variables match parameter names

---

**Created**: October 27, 2025  
**Service**: EmailJS (service_x4eo2tt)  
**Forms**: 3 separate pages with dedicated themes
