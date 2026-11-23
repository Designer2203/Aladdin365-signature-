# Aladdin365 Email Signature Generator

A single-page tool that lets every employee generate their own Aladdin365 email signature, preview it live, and copy it as rich HTML into Gmail or Outlook.

## Files

```
index.html          Generator: form, live preview, Copy signature / Copy HTML code
assets/logo.png         Aladdin365 logo (2x, shown at 188 x 59)
assets/itme-badge.png   INDIA ITME 2026 badge (2x, shown at 95 x 114)
assets/facebook.png     Social icons (2x, shown at 20 x 20)
assets/instagram.png
assets/linkedin.png
```

## Setup (one time, for the web admin)

1. Upload the whole folder to the company website, for example
   `https://www.aladdin365.com/email-signature/`.
2. Make sure the images open in a browser over HTTPS, e.g.
   `https://www.aladdin365.com/email-signature/assets/logo.png`.
3. If you use a different location, edit `CONFIG.IMAGE_BASE_URL` at the top of the
   `<script>` in `index.html` (it must end with `/`).
4. Share the page link with employees.

The copied signature always uses `CONFIG.IMAGE_BASE_URL`; the on-page preview uses the local `assets/` files.
If the images aren’t uploaded yet, the pasted signature shows broken images.

## Better image quality

The assets were cut from the exported JPG artboard. For the sharpest result, export the logo,
badge and icons from Illustrator as PNG at 2x with the same file names and replace them.

## Editing event details

Hall/stall number, event name and dates are fixed text inside `buildSignature()` in `index.html`.
Replace the badge image and these strings when the event changes.

## Email-client notes

- Built with nested tables and inline CSS only; no external CSS, no web-font dependency.
- Poppins is used where installed; otherwise Segoe UI (Outlook/Windows) or Helvetica/Arial.
- Classic Outlook for Windows ignores `border-radius`, so the purple Hall/Stall box shows square corners there.
- The signature is 1000 px wide, matching the artboard. On narrow phone screens it will scroll or scale down, as fixed-layout email signatures do.
