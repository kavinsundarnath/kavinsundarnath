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

# 📬 Simple Newsletter System (Google Sheets + Apps Script)

This project implements a lightweight newsletter system using:

- **Google Sheets** as the subscriber database  
- **Google Apps Script** as the backend (email + API)  
- **Any static website** (e.g. GitHub Pages) as the frontend  

It supports:
- Email subscription (double opt-in)
- Email confirmation
- Unsubscribe links
- Manual newsletter sending

No external services required.

---

## 🧩 Architecture Overview

Website (HTML + JS)
↓
Google Apps Script (Web App)
↓
Google Sheet (Subscribers)
↓
Gmail (Emails sent via your account)

---

## 📄 Google Sheet Structure

Create a Google Sheet with a tab named: subscribers


Add **exactly these columns** in row 1:

| Column | Name             | Description |
|------|------------------|------------|
| A | email | Subscriber email |
| B | status | `PENDING` / `CONFIRMED` / `UNSUBSCRIBED` |
| C | token | Confirmation token |
| D | requested_at | Subscription request time |
| E | confirmed_at | Confirmation time |
| F | ip | Optional |
| G | unsubscribed_at | Unsubscribe time |

---

## ⚙️ Apps Script Setup

1. Open the Google Sheet  
2. Go to **Extensions → Apps Script**
3. Paste the backend code into `Code.gs`
4. Save the project

---

## 🌍 Deploy as Web App

1. Click **Deploy → New deployment**
2. Type: **Web app**
3. Execute as: **Me**
4. Who has access: **Anyone**
5. Deploy and copy the Web App URL

This URL is your backend API.

---

## ✉️ Subscribe Flow (Website)

From your website, send a **POST request**:

```js
fetch("WEB_APP_URL", {
  method: "POST",
  headers: { "Content-Type": "application/json" },
  body: JSON.stringify({ email })
});


Add **exactly these columns** in row 1:

| Column | Name             | Description |
|------|------------------|------------|
| A | email | Subscriber email |
| B | status | `PENDING` / `CONFIRMED` / `UNSUBSCRIBED` |
| C | token | Confirmation token |
| D | requested_at | Subscription request time |
| E | confirmed_at | Confirmation time |
| F | ip | Optional |
| G | unsubscribed_at | Unsubscribe time |

---

## ⚙️ Apps Script Setup

1. Open the Google Sheet  
2. Go to **Extensions → Apps Script**
3. Paste the backend code into `Code.gs`
4. Save the project

---

## 🌍 Deploy as Web App

1. Click **Deploy → New deployment**
2. Type: **Web app**
3. Execute as: **Me**
4. Who has access: **Anyone**
5. Deploy and copy the Web App URL

This URL is your backend API.

---

## ✉️ Subscribe Flow (Website)

From your website, send a **POST request**:

```js
fetch("WEB_APP_URL", {
  method: "POST",
  headers: { "Content-Type": "application/json" },
  body: JSON.stringify({ email })
});

What happens

Email is stored as PENDING

A confirmation email is sent

User must click the confirmation link

Confirmation link format: WEB_APP_URL?email=USER_EMAIL&token=TOKEN

Unsubscribe link format: WEB_APP_URL?action=unsubscribe&email=USER_EMAIL




