# Configure DNS for chattertechai.com (Squarespace)

**Copyright (c) 2025 Joshua Hendricks Cole (DBA: Corporation of Light). All Rights Reserved. PATENT PENDING.**

---

## 🌐 Add DNS Records for GitHub Pages (Squarespace)

### Step 1: Access Squarespace DNS Settings (2 minutes)

1. Go to: https://domains.squarespace.com
2. Log in with your Squarespace account
3. Click on **chattertechai.com**
4. Click **DNS Settings** (or **Advanced Settings** → **DNS**)

**Quick Link:** https://domains.squarespace.com

---

### Step 2: Add 4 A Records for GitHub Pages (5 minutes)

Click **Add Record** and add these 4 A records one at a time:

```
Record Type: A
Host: @
Points To: 185.199.108.153
TTL: Auto

Record Type: A
Host: @
Points To: 185.199.109.153
TTL: Auto

Record Type: A
Host: @
Points To: 185.199.110.153
TTL: Auto

Record Type: A
Host: @
Points To: 185.199.111.153
TTL: Auto
```

**Visual Guide:**
```
+--------+------+---------------------+
| Host   | Type | Points To           |
+--------+------+---------------------+
| @      | A    | 185.199.108.153     |
| @      | A    | 185.199.109.153     |
| @      | A    | 185.199.110.153     |
| @      | A    | 185.199.111.153     |
+--------+------+---------------------+
```

---

### Step 3: Add CNAME Record for www (1 minute)

Add one CNAME record for the www subdomain:

```
Record Type: CNAME
Host: www
Points To: workofarttattoo.github.io.
TTL: Auto
```

**Important:** Add the trailing dot: `workofarttattoo.github.io.`

---

### Step 4: Remove Conflicting Records (If Needed)

If you see error "CNAME already exists", you need to remove old records:

1. Look for existing A or CNAME records pointing to Squarespace servers
2. Delete any records that conflict with GitHub Pages IPs
3. Common Squarespace IPs to remove:
   - 198.185.159.144
   - 198.185.159.145
   - 198.49.23.144
   - 198.49.23.145

---

### Step 5: Save & Wait (15-60 minutes)

1. Click **Save** at the bottom
2. DNS propagation: **15-60 minutes** (usually ~20 minutes)
3. Check status: https://www.whatsmydns.net/#A/chattertechai.com

---

## ⏰ While You Wait (Use Preview URLs!)

Your sites are LIVE on GitHub right now, just not at the custom domains yet!

**ChatterTech AI Preview:**
https://workofarttattoo.github.io/chattertechai/

**Sovereign Security Preview:**
https://workofarttattoo.github.io/red-team-tools/

You can share these URLs and test everything while DNS propagates!

---

## 🎯 After DNS Propagates (Step 6)

Once DNS is ready (check whatsmydns.net):

1. Go to: https://github.com/Workofarttattoo/chattertechai/settings/pages
2. Under **Custom domain**, enter: `chattertechai.com`
3. Click **Save**
4. Wait 1-2 minutes for DNS verification
5. Check **Enforce HTTPS** once available

---

## 🔍 Troubleshooting

### "Can't access chattertechai.com yet"
✅ **Solution:** DNS takes 15-60 minutes to propagate globally
✅ **Workaround:** Use preview URL: https://workofarttattoo.github.io/chattertechai/

### "DNS check unsuccessful" in GitHub
✅ Wait 15-30 more minutes
✅ Verify all 4 A records are correct
✅ Make sure you used `@` for host, not `chattertechai.com`

### "CNAME already exists" error
✅ Remove existing CNAME or A records in Squarespace DNS
✅ Delete any records pointing to Squarespace servers

---

## 📋 Quick Checklist

- [ ] Go to domains.squarespace.com
- [ ] Click chattertechai.com → DNS Settings
- [ ] Add 4 A records (all pointing @ to GitHub IPs)
- [ ] Add 1 CNAME record (www → workofarttattoo.github.io.)
- [ ] Remove any conflicting Squarespace records
- [ ] Click Save
- [ ] Wait 15-60 minutes
- [ ] Check https://www.whatsmydns.net/#A/chattertechai.com
- [ ] Add custom domain in GitHub Pages settings
- [ ] Enable HTTPS

---

## ✅ Verification Commands

**Check DNS (Terminal):**
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

**Check CNAME for www:**
```bash
dig www.chattertechai.com +short
```

Should show:
```
workofarttattoo.github.io.
185.199.108.153
185.199.109.153
185.199.110.153
185.199.111.153
```

---

**Copyright (c) 2025 Joshua Hendricks Cole (DBA: Corporation of Light). All Rights Reserved. PATENT PENDING.**
