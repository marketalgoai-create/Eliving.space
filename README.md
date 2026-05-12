# eLiving Space — Website Files

## Files to upload to GitHub

| File | Purpose |
|------|---------|
| `index.html` | Main website |
| `admin.html` | Admin dashboard |
| `CNAME` | Tells GitHub Pages your custom domain |
| `_config.yml` | GitHub Pages config |
| `.nojekyll` | Prevents GitHub breaking your HTML |

**All 5 files must be uploaded.** The CNAME, _config.yml, and .nojekyll are what unlock HTTPS.

---

## 🔒 How to enable HTTPS on GitHub Pages — exact steps

### Step 1 — Upload all files to GitHub

1. Go to github.com → your repo `Eliving.space`
2. Click **Add file → Upload files**
3. Upload ALL 5 files: `index.html`, `admin.html`, `CNAME`, `_config.yml`, `.nojekyll`
4. Commit changes

> ⚠️ The `.nojekyll` file may be hidden on your computer (starts with a dot).
> On Mac: press **Cmd+Shift+.** to show hidden files before uploading.
> On Windows: it will show normally in File Explorer.

---

### Step 2 — Enable GitHub Pages

1. In your repo → click **Settings** (top menu)
2. In the left sidebar → click **Pages**
3. Under **Source** → select **Deploy from a branch**
4. Branch: **main** → Folder: **/ (root)** → click **Save**
5. Wait 2–3 minutes → refresh the page

---

### Step 3 — Set your custom domain

Still in **Settings → Pages**:

1. Under **Custom domain** → type `eliving.space` → click **Save**
2. GitHub will check DNS — it may say "DNS check in progress" — that's normal
3. Once DNS passes, tick the box **Enforce HTTPS** → click it

> If "Enforce HTTPS" is greyed out, your DNS isn't pointing correctly yet (see Step 4).

---

### Step 4 — Fix DNS in Hostinger (critical for HTTPS)

Go to **Hostinger → Domains → eliving.space → DNS Zone**

Delete any existing A records for `@`, then add these **4 GitHub IP A records**:

| Type | Name | Value | TTL |
|------|------|-------|-----|
| A | @ | 185.199.108.153 | 3600 |
| A | @ | 185.199.109.153 | 3600 |
| A | @ | 185.199.110.153 | 3600 |
| A | @ | 185.199.111.153 | 3600 |

Also add this **CNAME for www**:

| Type | Name | Value | TTL |
|------|------|-------|-----|
| CNAME | www | marketalgoai-create.github.io | 3600 |

> Replace `marketalgoai-create` with your actual GitHub username if different.

---

### Step 5 — Wait and verify

- DNS changes take **15 minutes to 24 hours** to propagate
- Once done, go back to **GitHub → Settings → Pages**
- You should see: ✅ "Your site is live at https://eliving.space"
- The **Enforce HTTPS** checkbox should now be tickable — tick it

---

### Why HTTPS wasn't working before

GitHub Pages HTTPS requires:
1. ✅ A `CNAME` file in the repo root with your domain
2. ✅ DNS A records pointing to GitHub's 4 IPs (not Hostinger's servers)
3. ✅ "Enforce HTTPS" ticked in GitHub Pages settings
4. ✅ `.nojekyll` file so GitHub doesn't process your HTML as Jekyll

All of these are now included in your file package.

---


