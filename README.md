# kavinsundarnath.com — From Zero to Live

This repository documents the **entire journey of creating kavinsundarnath.com**, starting from **not even having a GitHub account**, all the way to a **live custom-domain website hosted on GitHub Pages**.

The site is intentionally simple:

- No backend  
- No frameworks  
- No build tools  
- Only **HTML + CSS**

---

## 1. Creating a GitHub account

1. Visited https://github.com  
2. Clicked **Sign up**  
3. Created a GitHub account  
4. Verified email address  
5. Logged in  

This account is required because **GitHub Pages** is used for hosting.

---

## 2. Creating the repository

1. Clicked **New repository**
2. Repository name: `kavinsundarnath`


3. Visibility: **Public**
4. Initialized **without** README
5. Created the repository

This repository hosts all website files.

---

## 3. Buying the domain (Namecheap)

1. Visited https://www.namecheap.com  
2. Searched for: kavinsundarnath.com


3. Purchased the domain  
4. Completed payment  

At this stage, the domain exists but does not point anywhere.

---

## 4. Pointing the domain to GitHub Pages (DNS setup)

### A) Open DNS settings

1. Namecheap Dashboard → **Domain List**
2. Click **Manage**
3. Go to **Advanced DNS**

---

### B) Add GitHub Pages A records

| Type | Host | Value | TTL |
|----|----|----|----|
| A | @ | 185.199.108.153 | Automatic |
| A | @ | 185.199.109.153 | Automatic |
| A | @ | 185.199.110.153 | Automatic |
| A | @ | 185.199.111.153 | Automatic |

---

### C) Add CNAME for `www` (optional)

| Type | Host | Value |
|----|----|----|
| CNAME | www | `<github-username>.github.io` |

---

### D) DNS propagation

- Usually minutes
- Sometimes a few hours

---

## 5. Enabling GitHub Pages

1. Repository → **Settings**
2. Open **Pages**
3. Source: `Deploy from a branch`
4. Branch: `main`
5. Folder: `/ (root)`
6. Save

---

## 6. Connecting the custom domain

1. Settings → **Pages**
2. Custom domain: kavinsundarnath.com
3. Save
4. DNS check succeeds

---

## 7. Adding the CNAME file

Create a file named: CNAME

Contents: kavinsundarnath.com

---

## 8. Enabling HTTPS

1. Settings → Pages
2. Enable **Enforce HTTPS**

Your site is now available at: https://kavinsundarnath.com


