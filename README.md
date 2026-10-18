# 👑 Royal Feast — Luxury Restaurant & Premier Catering Website

A modern, professional, fully responsive restaurant and catering website engineered for a **senior web developer portfolio and CV**. Built with clean semantic HTML5, modern CSS3, Bootstrap 5, vanilla JavaScript, and frontend EmailJS integration.

---

## 🌟 Live Demo & Portfolio Highlights

- **Aesthetic**: Royal emerald green (`#081d13`), regal gold accents (`#c59d5f`, `#e5c378`), soft cream, and pure white typography.
- **7 Complete Pages**:
  1. `index.html` — Hero section, about preview, featured services, popular food categories, gallery preview, testimonials, why choose us, CTA banner, and footer.
  2. `about.html` — Brand heritage, mission, vision, core values, master culinary team, and food safety/HACCP certifications.
  3. `services.html` — 11 detailed catering service cards (Weddings, Birthdays, Corporate, Mehndi, Family Feasts, Buffet, Live BBQ, Desi, Chinese, Desserts, Beverages) with pre-fill booking links.
  4. `gallery.html` — Responsive visual showcase with live category filtering (All, Weddings, Desi Food, BBQ, Desserts, Events) and custom full-screen Lightbox modal.
  5. `packages.html` — Silver, Gold Imperial, and Crown Sovereign catering tiers, clear starting price disclaimers, and a comprehensive Custom Quotation Builder.
  6. `contact.html` — Professional contact and event booking form with validation, past date prevention, tasting session concierge, and venue location.
  7. `privacy.html` — Complete data protection disclosures tailored to catering reservations.
- **Interactive JavaScript Features**:
  - Filterable gallery with smooth transitions and keyboard-accessible Lightbox modal.
  - Floating WhatsApp button with customizable business number and pre-filled inquiry.
  - Form validation with live feedback and prevention of past event dates.
  - Smooth scrolling, sticky blur navbar, active link detection, and back-to-top button.
  - Image fallback handler ensuring zero broken images even offline.
  - Automatic copyright year updater.

---

## 📁 Project Structure

```text
Royal Feast/
│
├── index.html              # Home Page
├── about.html              # About Us & Master Chefs
├── services.html           # 11 Dedicated Catering Service Cards
├── gallery.html            # Category Filter Gallery & Lightbox
├── packages.html           # Catering Packages & Custom Quote Form
├── contact.html            # Contact & Event Booking Page
├── privacy.html            # Comprehensive Privacy Policy
│
├── css/
│   └── style.css           # Master custom stylesheet & design system
│
├── js/
│   ├── main.js             # Navigation, gallery filters, lightbox, WhatsApp, utils
│   └── email.js            # EmailJS configuration, form validation & dispatch
│
├── assets/
│   ├── images/
│   │   ├── logo.svg        # Royal Feast brand crest & typography
│   │   ├── favicon.svg     # Regal crown browser icon
│   │   └── pattern.svg     # Subtle luxury watermark pattern
│   └── icons/
│
├── robots.txt              # Search engine crawler instructions
├── sitemap.xml             # XML sitemap for SEO indexing
└── README.md               # Complete documentation & configuration guide
```

---

## 📧 EmailJS Integration Guide

All contact and quotation submissions are targeted for:
👉 **`u382322@gmail.com`**

The integration code is centralized in [`js/email.js`](file:///C:/Users/bse23/Desktop/Royal%20Feast/js/email.js).

### Step-by-Step EmailJS Setup:

1. **Create an EmailJS Account**:
   - Visit [https://www.emailjs.com/](https://www.emailjs.com/) and register for a free account.

2. **Add an Email Service**:
   - Go to **Email Services** > **Add New Service**.
   - Select **Gmail** (or your SMTP provider).
   - Authenticate with the target account: `u382322@gmail.com`.
   - Copy your **Service ID** (e.g., `service_abc123`).

3. **Create Email Templates**:
   - Go to **Email Templates** > **Create New Template**.
   - Set the subject: `New Royal Feast Catering Inquiry: {{subject}}`
   - Include these template variables in the template body:
     ```html
     <h3>New Royal Feast Event Inquiry</h3>
     <p><strong>Full Name:</strong> {{from_name}}</p>
     <p><strong>Email Address:</strong> {{from_email}}</p>
     <p><strong>Phone / WhatsApp:</strong> {{phone}}</p>
     <p><strong>Event Type:</strong> {{event_type}}</p>
     <p><strong>Event Date:</strong> {{event_date}}</p>
     <p><strong>Estimated Guests:</strong> {{guest_count}}</p>
     <p><strong>Venue Location:</strong> {{event_location}}</p>
     <p><strong>Selected Package / Services:</strong> {{selected_package}} {{menu_preferences}}</p>
     <p><strong>Client Notes:</strong><br>{{message}} {{special_notes}}</p>
     <p><small>Submitted at: {{submission_time}}</small></p>
     ```
   - Copy your **Template ID** (e.g., `template_xyz456`).

4. **Obtain Your Public Key**:
   - Navigate to **Account** > **API Keys**.
   - Copy your **Public Key** (e.g., `user_XXXXXXX` or public key token).

5. **Update `js/email.js`**:
   Open [`js/email.js`](file:///C:/Users/bse23/Desktop/Royal%20Feast/js/email.js) and replace the placeholder credentials:
   ```javascript
   const ROYAL_EMAIL_CONFIG = {
     SERVICE_ID: "YOUR_SERVICE_ID",          // Insert your real Service ID
     TEMPLATE_CONTACT: "YOUR_TEMPLATE_ID",    // Insert your Contact Template ID
     TEMPLATE_QUOTATION: "YOUR_TEMPLATE_ID",  // Insert your Quotation Template ID
     PUBLIC_KEY: "YOUR_PUBLIC_KEY",          // Insert your real Public Key
     RECIPIENT_EMAIL: "u382322@gmail.com",
     ENABLE_PORTFOLIO_DEMO: true             // Set false when real keys are added
   };
   ```

### 💡 Portfolio Demo Mode
While credentials are placeholders (`YOUR_SERVICE_ID`), the website will automatically run in **Portfolio Demonstration Mode** (`ENABLE_PORTFOLIO_DEMO: true`). It validates every input, simulates realistic network latency, and displays a transparent demonstration banner explaining how data is packaged for `u382322@gmail.com` without throwing unhandled API errors.

---

## 💬 WhatsApp Integration Guide

A floating WhatsApp contact button is active on all pages, plus in-page inquiry buttons.

### Changing the WhatsApp Business Phone Number:
Open [`js/main.js`](file:///C:/Users/bse23/Desktop/Royal%20Feast/js/main.js) and update the configuration at line 8:
```javascript
const ROYAL_WHATSAPP_CONFIG = {
  // Format: Country code without leading '+' or '00' (e.g., '923001234567' or '15551234567')
  phoneNumber: "923001234567",
  defaultMessage: "Hello Royal Feast! I would like to inquire about your catering services for an upcoming event."
};
```

---

## 🚀 How to Run Locally

You can run this website on any modern browser:

### Option 1: Direct File Launch
Double click `index.html` in your file explorer to open it in Chrome, Edge, Firefox, or Safari.

### Option 2: Using Python HTTP Server (Recommended)
Open a terminal in the project directory:
```bash
python -m http.server 8000
```
Then visit `http://localhost:8000` in your browser.

### Option 3: Using VS Code Live Server
Right-click `index.html` in VS Code and select **Open with Live Server**.

---

## 🛡️ Form Validation & Security Standards

- **Name Validation**: Minimum 2 characters, trimmed.
- **Email Validation**: Strict regex compliance (`name@domain.com`).
- **Phone Validation**: Minimum 7 digits, supports international formatting `+`.
- **Date Protection**: The date picker automatically sets `min` attribute to tomorrow's date, preventing invalid bookings in the past.
- **Anti-Spam / Anti-Duplicate**: Submit buttons are disabled and replaced with loading spinners during request processing.
- **Zero Exposed Passwords**: No private email passwords or secret backend tokens are stored in frontend code.

---

## 🎨 Technology Stack

- **HTML5**: Semantic tags (`<header>`, `<nav>`, `<main>`, `<section>`, `<article>`, `<footer>`).
- **CSS3**: Custom design system, CSS variables, glassmorphism, responsive flex/grid layouts.
- **Bootstrap 5.3.3**: Responsive grid, utilities, collapse mobile menu, and modals.
- **Bootstrap Icons 1.11.3**: Crisp vector icons throughout navigation, cards, and footers.
- **Vanilla JavaScript**: Zero heavy external jQuery dependencies for maximum performance and portfolio demonstration.
- **EmailJS SDK v4**: Seamless browser email dispatch.

---

## 👨‍💻 Developer Portfolio Note
This project demonstrates modern frontend engineering best practices:
- Modular, well-commented JavaScript with separation of concerns.
- Reusable CSS variables and utility classes.
- Accessible form controls with ARIA attributes and descriptive labels.
- Cross-browser compatibility and responsive performance on mobile, tablet, and desktop screens.
