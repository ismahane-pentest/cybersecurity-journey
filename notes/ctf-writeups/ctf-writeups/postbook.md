# Postbook — Hacker101 CTF Writeup

## 📋 Overview
- **Challenge**: Postbook
- **Platform**: Hacker101 CTF
- **Difficulty**: Easy
- **Flags Found**: 7/7
- **Points Earned**: 28

## 🎯 Flags Discovered

### Flag 0 — IDOR (Private Post Access)
- **Vulnerability**: Access to admin's private post via ID manipulation.
- **Steps**: Change `id=3` to `id=2` in view.php URL.
- **Flag**: `^FLAG^fa080edd48a08c3e261effebc49168c4e941d38865a97a97a374e70f10cac52d$FLAG$`

### Flag 1 — Hidden Field Tampering (Create Post)
- **Vulnerability**: Manipulating hidden `user_id` field during post creation.
- **Steps**: Change `user_id` value from your ID to `1` (admin).
- **Flag**: `^FLAG^40fe7901c94f44c62b0df910fd0b471a341c4794359b6863229517feaa13ad27$FLAG$`

### Flag 2 — Hidden Field Tampering (Edit Post)
- **Vulnerability**: Manipulating hidden `id` field during post editing.
- **Steps**: Change `id` value to `1` (admin's post).
- **Flag**: `^FLAG^4f59a6a35f5124d5801bf02bd189030a048cf483873319acc56bc96011a4b7d4$FLAG$`

### Flag 3 — IDOR (Post ID 945)
- **Vulnerability**: Access to hidden post via ID enumeration.
- **Steps**: Change `id` to `945` in view.php URL.
- **Flag**: `^FLAG^e5eb6799fb7f6a6b666b9be85d5645002410cb1b62ce836e4888e127a8f65210$FLAG$`

### Flag 4 — Hidden Field Tampering (Save Edit)
- **Vulnerability**: Saving edits to a post you don't own.
- **Steps**: Change hidden `id` field to `1` and save.
- **Flag**: `^FLAG^17cb4a57c9fd6674ed6fd75f1dad8fc29e3c1bd7c388203d0b8594490d2a24f8$FLAG$`

### Flag 5 — Cookie Tampering
- **Vulnerability**: Changing `id` cookie to MD5 of admin's ID.
- **Steps**: Change cookie `id` to `c4ca4238a0b923820dcc509a6f75849b`.
- **Flag**: `^FLAG^b5aee08a04892321bb6da680e37e2093a9596935be2b7efd42323864db84025b$FLAG$`

### Flag 6 — Delete IDOR
- **Vulnerability**: Deleting admin's post via MD5 manipulation.
- **Steps**: Change delete `id` parameter to MD5 of `1`.
- **Flag**: `^FLAG^...$FLAG$`

## 🧠 Lessons Learned
- **Hidden Fields**: Never trust client-side hidden fields.
- **Cookies**: Always check if cookies are predictable.
- **MD5**: Not a secure hashing algorithm for sensitive data.
- **IDOR**: Test all numeric parameters.

---
*Writeup by [Your Name] — Hacker101 CTF*
