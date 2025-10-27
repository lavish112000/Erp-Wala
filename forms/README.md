# Form Pages - FormSubmit Integration

This directory contains three separate form pages for lead capture using **FormSubmit.co** (free email service).

## 📁 Form Pages

1. **demo-request.html** - Simple demo request form (Blue theme)
2. **personalized-demo.html** - Personalized demo with date selection (Purple theme)
3. **free-consultation.html** - Detailed consultation form (Green theme)

## ✅ Already Configured

**Good news!** All forms are already set up with FormSubmit and ready to use. No API keys or configuration needed!

### How It Works

1. User fills out the form
2. Form submits to FormSubmit.co
3. You receive a professional table-formatted email at: `lalitchoudhary112000@gmail.com`
4. User is redirected to a thank you page (or stays on the form)

### First-Time Setup (One-Time Only)

**Important:** The first time someone submits a form, FormSubmit will send a confirmation email to verify your email address.

1. Wait for the confirmation email from FormSubmit
2. Click the confirmation link
3. After confirmation, all future submissions will work automatically

## 🔧 FormSubmit Features

### Built-in Features (Already Configured)

### Built-in Features (Already Configured)

- ✅ **Professional Email Format**: Table-based layout for easy reading
- ✅ **Spam Protection**: Honeypot field catches bots
- ✅ **Custom Subject Lines**: Each form type has unique subject
- ✅ **No Captcha**: Smooth user experience
- ✅ **Unlimited Submissions**: Completely free
- ✅ **No API Keys**: Zero configuration required

### Form-Specific Email Subjects

- **Demo Request**: "New Demo Request from Millennium Academy"
- **Personalized Demo**: "New Personalized Demo Request from Millennium Academy"
- **Free Consultation**: "New Free Consultation Request from Millennium Academy"

## 🎨 Form Features

### All Forms Include

- ✅ **Honeypot spam protection** (hidden _honey field)
- ✅ **Responsive design** (mobile-friendly)
- ✅ **Form validation** (required fields)
- ✅ **Smooth animations** (slide-in effect)
- ✅ **Back to home** link
- ✅ **Professional styling** with Tailwind CSS
- ✅ **Color-coded themes** (Blue/Purple/Green)

### Form-Specific Fields

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

1. Fill out a form with real data
2. Submit the form
3. Check your email (`lalitchoudhary112000@gmail.com`)
4. On first submission, confirm your email with FormSubmit
5. Future submissions will arrive instantly!

## 📧 Changing Email Address

To send form submissions to a different email:

1. Open each form file (demo-request.html, personalized-demo.html, free-consultation.html)
2. Find the line: `action="https://formsubmit.co/lalitchoudhary112000@gmail.com"`
3. Replace with your email: `action="https://formsubmit.co/YOUR_EMAIL@example.com"`
4. Save and test with a submission
5. Confirm the new email address when FormSubmit sends verification

## 🔒 Security Features

1. **Honeypot Field** (`_honey`): Hidden field that bots fill out, real users don't see
2. **Client-side Validation**: Required fields, email format, phone format
3. **FormSubmit Protection**: Built-in rate limiting and spam filtering
4. **No Backend Required**: Secure, serverless email delivery

## 💡 Advanced Configuration (Optional)

FormSubmit supports additional features via hidden fields:

### Redirect After Submission

Add this field to redirect users to a thank you page:

```html
<input type="hidden" name="_next" value="https://yourdomain.com/thanks.html">
```

### Auto-Reply to User

Send a confirmation email to the form submitter:

```html
<input type="hidden" name="_autoresponse" value="Thank you for contacting Millennium Academy!">
```

### CC Additional Email

Send a copy to another email address:

```html
<input type="hidden" name="_cc" value="admin@yourdomain.com">
```

## 📁 Backup Files

EmailJS versions are kept as backups:

- `demo-request-emailjs.html`
- `personalized-demo-emailjs.html`
- `free-consultation-emailjs.html`

These can be deleted or kept for reference.

## 📞 Support

If emails aren't arriving:

1. Check spam/junk folder
2. Verify you clicked the FormSubmit confirmation link
3. Test with a different email provider
4. Check browser console for errors
5. Ensure form `action` URL is correct

---

**Service**: FormSubmit.co (Free)  
**Email**: lalitchoudhary112000@gmail.com  
**Last Updated**: October 27, 2025  
**Forms**: 3 separate pages with dedicated themes
