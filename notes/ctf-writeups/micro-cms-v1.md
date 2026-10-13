# Micro-CMS v1 — Hacker101 CTF Writeup

## 📋 Overview
- **Challenge**: Micro-CMS v1
- **Platform**: Hacker101 CTF
- **Difficulty**: Easy
- **Flags Found**: 4/4
- **Points Earned**: 8

## 🎯 Flags Discovered

### Flag 0 — IDOR (Insecure Direct Object Reference)
- **Vulnerability**: Access to private page via URL manipulation.
- **Steps**:
  1. Navigate to `/page/edit/5`
  2. The page "Private Page" contains the flag.
- **Flag**: `^FLAG^28a5ca3234c61c46eeb50f05c5ebf789b92d2ca5912676546f0e895da3f4b6be$FLAG$`

### Flag 1 — Stored XSS in Page Title
- **Vulnerability**: Cross-Site Scripting (XSS).
- **Steps**:
  1. Edit any page.
  2. Inject `<script>alert(1)</script>` in the title field.
  3. Save and view the page source.
- **Flag**: `^FLAG^f97c56c55bd85644e223e73bf7674a8d5b9585f7506662fe260a5792c102d036$FLAG$`

### Flag 2 — SQL Injection
- **Vulnerability**: SQL Injection in page parameter.
- **Steps**:
  1. Identify injectable parameter in URL.
  2. Use `' UNION SELECT 1,flag,3 FROM flags-- -`
  3. Flag appears in the response.
- **Flag**: `^FLAG^9d11d0a05a22c504dad8377783029024ca40d92470d52450880a8b146f504545$FLAG$`

### Flag 3 — Stored XSS in Button
- **Vulnerability**: Stored XSS in button element.
- **Steps**:
  1. Edit "Markdown Test" page (id=2).
  2. Replace `<button>Some button</button>` with `<button onclick="alert('XSS')">Some button</button>`.
  3. Save and view source.
- **Flag**: `^FLAG^9d11d0a05a22c504dad8377783029024ca40d92470d52450880a8b146f504545$FLAG$`

## 🧠 Lessons Learned
- **IDOR**: Always check for pages that can be accessed by changing IDs.
- **XSS**: Test both title and content fields for XSS.
- **SQL Injection**: Simple `'` can reveal SQL errors.
- **Source Code**: Always check page source for hidden comments.

## 🛠️ Tools Used
- Browser (Firefox/Chrome)
- Burp Suite (for intercepting requests)
- Manual testing

---
*Writeup by [Your Name] — Hacker101 CTF*
