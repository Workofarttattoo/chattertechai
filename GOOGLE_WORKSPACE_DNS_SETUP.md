# Configure DNS for chattertechai.com (Google Workspace)

**Copyright (c) 2025 Joshua Hendricks Cole (DBA: Corporation of Light). All Rights Reserved. PATENT PENDING.**

---

## 🌐 Add DNS Records for GitHub Pages

Since you bought chattertechai.com through Google Workspace, follow these steps:

### Step 1: Access Google Domains Settings (2 minutes)

**Option A - Through Google Workspace Admin:**
1. Go to: https://admin.google.com
2. Click **Domains** in the left menu
3. Click **Manage domains**
4. Click on **chattertechai.com**
5. Click **DNS** in the left menu

**Option B - Direct Google Domains:**
1. Go to: https://domains.google.com
2. Click on **chattertechai.com**
3. Click **DNS** in the left menu

---

### Step 2: Add A Records for GitHub Pages (4 minutes)

Click **Manage custom records** and add these 4 A records:

```
Type: A
Host name: @ (or leave blank)
TTL: 1 hour
Data: 185.199.108.153

Type: A
Host name: @ (or leave blank)
TTL: 1 hour
Data: 185.199.109.153

Type: A
Host name: @ (or leave blank)
TTL: 1 hour
Data: 185.199.110.153

Type: A
Host name: @ (or leave blank)
TTL: 1 hour
Data: 185.199.111.153
```

**Visual Guide:**
```
+----------------+------------+--------+---------------------+
| Host name      | Type       | TTL    | Data                |
+----------------+------------+--------+---------------------+
| @              | A          | 1h     | 185.199.108.153     |
| @              | A          | 1h     | 185.199.109.153     |
| @              | A          | 1h     | 185.199.110.153     |
| @              | A          | 1h     | 185.199.111.153     |
+----------------+------------+--------+---------------------+
```

---

### Step 3: Add CNAME Record for www (1 minute)

Add one more record for the www subdomain:

```
Type: CNAME
Host name: www
TTL: 1 hour
Data: workofarttattoo.github.io
```

**Visual Guide:**
```
+----------------+------------+--------+--------------------------------+
| Host name      | Type       | TTL    | Data                           |
+----------------+------------+--------+--------------------------------+
| www            | CNAME      | 1h     | workofarttattoo.github.io      |
+----------------+------------+--------+--------------------------------+
```

---

### Step 4: Save and Wait (10-60 minutes)

1. Click **Save** at the bottom
2. DNS propagation takes 10-60 minutes (usually ~15 minutes)
3. You can check status at: https://www.whatsmydns.net/#A/chattertechai.com

---

### Step 5: Configure Custom Domain in GitHub (2 minutes)

Once DNS is propagated:

1. Go to: https://github.com/Workofarttattoo/chattertechai/settings/pages
2. Under **Custom domain**, enter: **chattertechai.com**
3. Click **Save**
4. Wait 1-2 minutes
5. Check **Enforce HTTPS** once it's available

---

## 🔍 Troubleshooting

### "DNS check was unsuccessful"
- Wait 15-30 more minutes for DNS propagation
- Verify all 4 A records are correct
- Check you used @ (or blank) for host name, not chattertechai.com

### "CNAME already exists"
If you see this error, you might have conflicting records:
1. In Google Domains DNS, look for existing CNAME records
2. Remove any CNAME record pointing elsewhere
3. Add the GitHub Pages CNAME

### "Domain is already taken"
Someone else may have claimed it on GitHub Pages:
1. Go to GitHub Pages settings
2. Remove the custom domain
3. Wait 5 minutes
4. Re-add chattertechai.com

---

## ✅ Verification (How to confirm it worked)

**Test 1: DNS Lookup**
Open Terminal and run:
```bash
dig chattertechai.com +short
```

Should show:
```
185.199.108.153
185.199.109.153
185.199.110.153
185.199.111.153
```

**Test 2: Visit Site**
Go to: https://chattertechai.com

Should show your ChatterTech AI landing page!

---

## 📋 Quick Reference Card

**What you're adding:**
- 4 A records pointing @ to GitHub Pages IPs
- 1 CNAME record pointing www to your GitHub Pages URL

**Where:**
- Google Admin: admin.google.com → Domains → Manage → chattertechai.com → DNS
- OR Google Domains: domains.google.com → chattertechai.com → DNS

**How long:**
- Total setup time: ~7 minutes
- DNS propagation: 10-60 minutes (usually 15)

---

## 🚨 Important Notes

1. **Don't delete existing Google Workspace MX records!**
   - Keep all MX records for email to work
   - Only add the A and CNAME records above

2. **Wait for DNS propagation**
   - Don't panic if it doesn't work immediately
   - Takes 10-60 minutes to propagate globally

3. **HTTPS will take a few hours**
   - GitHub generates SSL certificate automatically
   - Can take 2-24 hours for HTTPS to work
   - Site will work on HTTP immediately

---

## 📞 Need Help?

If you get stuck:
1. Screenshot the error message
2. Check current DNS: https://www.whatsmydns.net/#A/chattertechai.com
3. Verify GitHub Pages is enabled
4. Wait longer (DNS can take up to 48 hours in rare cases)

---

**Copyright (c) 2025 Joshua Hendricks Cole (DBA: Corporation of Light). All Rights Reserved. PATENT PENDING.**
