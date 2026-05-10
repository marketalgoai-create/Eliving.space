# eLiving Space — Complete Website

Two files. Upload both to GitHub. Done.

## Files in this package
| File | Purpose |
|------|---------|
| `index.html` | Main website — everything guests see |
| `admin.html` | Your private dashboard — manage price & availability |

---

## 🚀 Deploy in 10 minutes (GitHub → Vercel → eliving.space)

### Step 1 — Push to GitHub
1. github.com → **New repository** → name it `eliving-space` → Public → Create
2. Click **Add file → Upload files**
3. Upload `index.html` and `admin.html`
4. Click **Commit changes**

### Step 2 — Deploy on Vercel (free)
1. vercel.com → Sign up with GitHub (free)
2. **Add New Project** → select `eliving-space`
3. Leave all settings default → **Deploy**
4. ✅ Live at `eliving-space.vercel.app` in ~60 seconds

### Step 3 — Connect eliving.space domain
In **Vercel → your project → Settings → Domains**:
- Add `eliving.space`
- Vercel shows you DNS records to copy

In **Hostinger DNS Zone** for eliving.space:
- Add the A record or CNAME that Vercel provides
- Wait 5–30 min for DNS to propagate

✅ Your site is live at **eliving.space**

---

## 🔐 Admin Dashboard

**URL:** `eliving.space/admin.html`

**Default login:**
- Username: `admin`
- Password: `eliving2026!`

⚠️ **Change the password before going live!** Open `admin.html` and find:
```javascript
const ADMIN_PASS = 'eliving2026!';
```
Change it to something only you know.

### What you can do in the admin:
- **Change the nightly price** → updates on website instantly
- **Block/unblock dates** on calendar → click any date
- **Quick links** to Airbnb, Booking.com, WhatsApp

---

## 📧 EmailJS — Booking Form

Your credentials are already wired in:
- Public key: `-SduMLzkgFgrXbrYP`
- Service ID: `service_2vzoblw`
- Template ID: `template_42yu96t`

### Set up your email template on emailjs.com
Your template (`template_42yu96t`) should use these variables:

```
Subject: New Booking Request — {{from_name}}

Name:     {{from_name}}
Email:    {{from_email}}
Phone:    {{phone}}
Check-in: {{checkin}}
Check-out:{{checkout}}
Nights:   {{nights}}
Guests:   {{guests}}
Total:    {{total}}
Message:  {{message}}
```

---

## 🔒 hCaptcha (GDPR-compliant CAPTCHA)

Currently using the **test sitekey** (`10000000-ffff-ffff-ffff-000000000001`) which always passes — fine for testing.

**To activate real CAPTCHA:**
1. Go to hcaptcha.com → Sign up (free)
2. Add your site `eliving.space`
3. Copy your **Site Key**
4. In `index.html`, find and replace:
   ```
   data-sitekey="10000000-ffff-ffff-ffff-000000000001"
   ```
   with your real sitekey.

---

## 📸 Photos

All photos load from your GitHub repo:
```
https://raw.githubusercontent.com/marketalgoai-create/Eliving.space/main/[filename]
```

**Make sure your photos repo is Public** — otherwise images won't load on the live site.

To check: go to github.com/marketalgoai-create/Eliving.space → Settings → make it Public.

---

## 🍪 GDPR / Legal pages

The site includes:
- **Cookie consent banner** (Accept / Decline) on first visit
- **Terms & Conditions** modal (footer link)
- **Privacy Policy** modal (footer link)
- **Cookie Policy** modal (footer link)

All stored in `localStorage` — no database needed.

---

## 💡 How price & availability work

Both are stored in `localStorage` of your browser:
- Price: `localStorage.setItem('eliving_price', '260')`
- Blocked dates: `localStorage.setItem('eliving_blocked', '[...]')`

**Important:** Always manage from the same browser/device. If you clear browser data or switch devices, settings reset. For multi-device management, contact us to upgrade to a Supabase backend.

---

## ✅ Pre-launch checklist

- [ ] Change admin password in `admin.html`
- [ ] Set up EmailJS template at emailjs.com
- [ ] Get real hCaptcha sitekey from hcaptcha.com
- [ ] Make your GitHub photos repo Public
- [ ] Point eliving.space DNS to Vercel
- [ ] Test booking form end-to-end
- [ ] Test on mobile
