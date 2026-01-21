# Namecard – Digital Name Card Platform

Namecard is a full-stack web application for creating and managing **digital business cards**.  
Users can register/login, build their own card with social links, and save other people’s cards into a personal contact list.  
An optional admin dashboard is included for managing themes and predefined social links.

---

## ✨ Key Features

- User authentication (register / login / logout)
- User profile management (update profile + profile image upload)
- Digital business card management (create / update / delete)
- Contact list system (save and remove contacts)
- Optional Admin dashboard (theme + social link management)

---

## 🏗️ System Overview

- **User** can create a digital name card and share it.
- **Contact List** lets users store other users’ cards for easy access.
- **Admin (Optional)** manages themes and preset social links to standardize UI/UX.

---

## 🔌 API Reference

### Service User

|path |method |authen |params |query | body | 
|:--|:--|:--:|:--|:--|:--|
|/auth/register |post |-|-|-|{email, passowrd, firstname, lastname, phone, profile(file)}|
|/auth/login|post|-|-|-|{email, password}|
|/auth/logout|post|-|-|-|-|
|/user/me|get|y|-|-|-|
|/user/update|patch|y|-|-|{firstName, lastName, jobPosition, phone, profileImage(file)}|
|/cards/me|get|y|-|-|-|
|/cards/create|post|y|-|-|{businessName, position, businessTel, businessEmail, logo(file), website, line, facebook, instagram, linkedin}|
|/cards/:id|put|y|:id|-|{businessName, position, businessTel, businessEmail, logo(file), website, line, facebook, instagram, linkedin}|
|/cards|delete|y|:id|-|-|
|/contacts-list/me|get|y|-|-|-|
|/contacts-list/create|post|y|-|-|{userId, contactId, namecardId}|
|/contacts-list|delete|y|:id|-|-|

---

### Admin Dashboard (Optional)

|path |method |authen |params |query | body | 
|:--|:--|:--:|:--|:--|:--|
|/admin|get|y|-|-|-|
|/admin|delete|y|:id|-|{userId}|
|/admin/theme|get|y|-|-|-|
|/admin/theme/create|post|y|-|-|{themeName}|
|/admin/theme/|delete|y|:id|-|-|
|/admin/social-link|get|y|-|-|-|
|/admin/social-link/create|post|y|-|-|{socialName, url}|
|/admin/social-link|delete|y|:id|-|-|

---

## 📌 Notes

- Endpoints marked with `authen = y` require authentication (e.g., JWT token).
- File uploads are used for `profile(file)`, `profileImage(file)`, and `logo(file)`.
- The Admin dashboard is optional and can be enabled depending on the project scope.

## 🎥 Demo Video
[![Namecard Digital Name Card Platform Demo](https://vumbnail.com/1156746818.jpg)](https://vimeo.com/1156746818)

This video demonstrates the AI-powered healthcare workflow, including user registration,
AI-assisted analysis, and admin management features.