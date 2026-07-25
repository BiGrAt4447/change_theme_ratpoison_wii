## 🎮 Wii‑Style UI Theme for LightDM

This document describes a **Wii‑style LightDM theme concept**, designed to be simple to implement and visually close to the original Wii interface.

---

## 🎨 Visual Style

### Background
- Solid light blue (`#5AC8FA`) or gradient from light blue to white  
- Soft white “wave” shapes at the bottom, similar to Wii Channels  

### Panels / Boxes
- Rounded rectangles with white background and subtle grey border (`#DDDDDD`)  
- Slight drop shadow for depth  
- Generous spacing — Wii interfaces are airy and uncluttered  

### Buttons
- Rounded corners (radius ≈ 12px)  
- Light grey (`#F5F5F5`), hover to slightly darker (`#E0E0E0`)  
- Text in dark grey (`#333333`), centered and bold  

### Font
- Clean sans‑serif: **Noto Sans**, **Roboto**, or **DejaVu Sans**  
- Font sizes:  
  - Title: 26–32 px  
  - Labels: 16–18 px  

### Cursor
- Use a **Wii‑style hand cursor** (PNG) for pointer  
- Set via LightDM greeter CSS (GTK or WebKit theme)

---

## 🧩 Layout

### Top Center
- Logo text: **Wii‑Linux NGX** in grey and blue  

### Center Panel
White rounded box containing:
- Username field  
- Password field  
- Session selector (e.g., Ratpoison)  
- Login button labeled **Start**

### Bottom Bar
- Small text showing hostname, time, and optionally “Press A to Start!”

---

## 🛠️ LightDM GTK Greeter Configuration Example

Edit `/etc/lightdm/lightdm-gtk-greeter.conf`:

```ini
[greeter]
background=/usr/share/wii-linux-ngx/wii_lightdm_bg.png
theme-name=WiiLightDM
icon-theme-name=Adwaita
font-name=Noto Sans 11
indicators=~session;~clock;~host

🧪 Simple CSS Example (for WebKit Greeter)

If you use a WebKit greeter, your CSS could look like:
```css
body {
  background: linear-gradient(#5AC8FA, #FFFFFF);
  font-family: "Noto Sans", sans-serif;
}

#login-panel {
  background: #FFFFFF;
  border-radius: 16px;
  border: 1px solid #DDDDDD;
  box-shadow: 0 4px 12px rgba(0,0,0,0.1);
  padding: 24px;
}

button {
  background: #F5F5F5;
  border-radius: 12px;
  border: 1px solid #DDDDDD;
  padding: 8px 16px;
  font-weight: bold;
  color: #333333;
}

button:hover {
  background: #E0E0E0;
}
```
🧱 Optional Add‑Ons

You can extend the theme with:

    A full CSS + asset pack (PNG background, cursor, logo)

    A wii-lightdm-theme folder structure ready to drop into /usr/share/lightdm/themes/

    A dark mode variant or animated “Press A to Start” version
