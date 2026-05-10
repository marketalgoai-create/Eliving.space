# eLiving Space — Website

Beautiful direct-booking landing page for your Valencia apartment.

## Files
- `index.html` — Main website (the one guests see)
- `admin.html` — Your private dashboard (price + availability management)

---

## 🚀 Deploying to GitHub + Vercel (free, ~10 minutes)

### Step 1: Create GitHub repo
1. Go to github.com → New repository
2. Name it `eliving-space`
3. Set to **Public** (required for free Vercel)
4. Click **Create repository**

### Step 2: Upload files
1. In your new repo, click **Add file → Upload files**
2. Upload `index.html` and `admin.html`
3. Click **Commit changes**

### Step 3: Deploy on Vercel
1. Go to [vercel.com](https://vercel.com) → Sign up with GitHub
2. Click **Add New Project**
3. Select your `eliving-space` repo
4. Leave all settings as default → click **Deploy**
5. Your site is live at `eliving-space.vercel.app` within 60 seconds ✅

### Step 4: Connect your domain (eliving.space)
In Vercel:
1. Go to your project → **Settings → Domains**
2. Type `eliving.space` and click **Add**
3. Vercel shows you DNS records to add

In Hostinger (your domain registrar):
1. Go to **DNS Zone** for eliving.space
2. Add the records Vercel gives you (usually an A record or CNAME)
3. Wait 5-30 minutes for propagation

Done! Your site is live at eliving.space 🎉

---

## 🔐 Admin Dashboard

Access at: `eliving.space/admin.html`

**Default login:**
- Username: `admin`
- Password: `eliving2026`

**IMPORTANT:** Change the password before going live!
Open `admin.html` and find this line near the top of the `<script>` section:
```
const ADMIN_PASS = 'eliving2026';
```
Change it to something strong.

**What you can do in the admin:**
- Change the nightly price (updates on the website instantly)
- Block/unblock dates on the calendar (click any date)
- Quick links to your Airbnb/Booking listings

---

## 📧 EmailJS — Booking Form

The contact form uses your EmailJS account. You'll need to set up the email template.

Go to [emailjs.com](https://emailjs.com) → Your template `template_42yu96t`

Make sure your template uses these variables:
```
From: {{from_name}} <{{from_email}}>
Phone: {{phone}}
Check-in: {{checkin}}
Check-out: {{checkout}}
Nights: {{nights}}
Guests: {{guests}}
Estimated Total: {{total}}
Message: {{message}}
```

---

## 🔒 CAPTCHA Setup

Currently using hCaptcha in **test mode** (always passes — good for testing).

To activate real CAPTCHA:
1. Go to [hcaptcha.com](https://hcaptcha.com) → Sign up free
2. Add your site (`eliving.space`)
3. Copy your **Site Key**
4. In `index.html`, find:
   ```
   data-sitekey="10000000-ffff-ffff-ffff-000000000001"
   ```
   Replace with your real site key.

---

## 📸 Photos

The gallery currently uses stock Unsplash photos as placeholders.

To add your real apartment photos:
1. Upload your photos to any free host: [Cloudinary](https://cloudinary.com) (free), or directly to your GitHub repo
2. In `index.html`, find the `<img src="https://images.unsplash.com/...">` tags
3. Replace each `src` with your photo URL

**Tip:** Rename your photos descriptively before uploading:
- `master-bedroom.jpg`
- `twin-bedroom.jpg`
- `kitchen.jpg`
- `terrace.jpg`
- `bathroom.jpg`

---

## 📱 WhatsApp Button

Pre-configured with +34 614 272 955. Opens a chat with a pre-filled message.
To change the message, find this in `index.html`:
```
https://wa.me/34614272955?text=Hi!%20I'm%20interested%20in%20booking...
```

---

## 🔄 Updating Your Site

Any change you make on GitHub automatically redeploys on Vercel (within ~30 seconds).

To update prices, availability, etc: just use the admin panel at `/admin.html`.
