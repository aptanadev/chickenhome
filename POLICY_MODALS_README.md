# Policy Modals Implementation

## Overview
Implementasi popup full screen untuk Privacy Policy dan Terms of Use pada website ChickenHome.

## Files Created

### 1. `_includes/policy-modals.html`
File HTML yang berisi struktur modal untuk:
- Privacy Policy Modal
- Terms of Use Modal

Konten mencakup:
- Header dengan judul dan tombol close
- Body dengan konten lengkap policy
- Footer dengan tombol close
- Responsive design

### 2. `css/policy-modal.css`
File CSS yang mengatur styling untuk:
- Modal overlay dengan background gelap (95% opacity)
- Modal content dengan animasi slide down
- Responsive design untuk mobile, tablet, dan desktop
- Custom scrollbar styling
- Hover effects dan transitions
- Gradient header dengan warna dari template

### 3. `js/policy-modal.js`
File JavaScript yang mengatur functionality:
- Open/close modal functions
- Event listeners untuk links di footer
- Close modal dengan:
  - Tombol X
  - Tombol Close di footer
  - Click outside modal
  - ESC key
- Prevent background scrolling ketika modal terbuka

## Files Modified

### 1. `_includes/footer.html`
Updated link Privacy Policy dan Terms of Use:
```html
<li><a href="#privacy-policy" id="privacyPolicyLink">Privacy Policy</a></li>
<li><a href="#terms-of-use" id="termsOfUseLink">Terms of Use</a></li>
```

### 2. `_includes/head.html`
Menambahkan link ke CSS file:
```html
<link rel="stylesheet" href="{{ "/css/policy-modal.css" | prepend: site.baseurl }}">
```

### 3. `_includes/js.html`
Menambahkan script untuk modal functionality:
```html
<script src="{{ "/js/policy-modal.js" | prepend: site.baseurl }}"></script>
```

### 4. `_layouts/default.html`
Menambahkan include untuk policy modals:
```html
{% include policy-modals.html %}
```

## Features

### Design Features
- ✅ Full screen overlay dengan background gelap
- ✅ Centered modal dengan max-width 900px
- ✅ Smooth animations (fade in, slide down)
- ✅ Responsive design untuk semua ukuran layar
- ✅ Custom scrollbar dengan warna brand
- ✅ Gradient header menggunakan warna template
- ✅ Professional typography dengan proper spacing

### Functionality Features
- ✅ Click link untuk membuka modal
- ✅ Close dengan tombol X
- ✅ Close dengan tombol Close di footer
- ✅ Close dengan click di luar modal
- ✅ Close dengan ESC key
- ✅ Prevent background scrolling
- ✅ Multiple modals support (Privacy & Terms)

### Content Features
- ✅ Privacy Policy mencakup:
  - Information Collection
  - How We Use Information
  - Information Sharing
  - Data Security
  - User Rights
  - Cookies Policy
  - Policy Changes
  - Contact Information

- ✅ Terms of Use mencakup:
  - Acceptance of Terms
  - Use License
  - User Account
  - Prohibited Uses
  - Intellectual Property
  - Disclaimer
  - Limitations
  - Links to Other Websites
  - Termination
  - Governing Law
  - Changes to Terms
  - Contact Information

## Customization

### Colors
Warna otomatis mengambil dari `site.data.template.color`:
- Primary color (default: #fed136)
- Secondary color (default: #fec810)

Untuk mengubah warna, edit `_data/template.yml`:
```yaml
color:
  primary: fed136
  secondary: fec810
```

### Content
Untuk mengubah konten Privacy Policy atau Terms of Use, edit file:
`_includes/policy-modals.html`

### Styling
Untuk mengubah styling, edit file:
`css/policy-modal.css`

## Browser Compatibility
- ✅ Chrome/Edge (modern versions)
- ✅ Firefox (modern versions)
- ✅ Safari (modern versions)
- ✅ Mobile browsers (iOS Safari, Chrome Mobile)

## Responsive Breakpoints
- Desktop: > 768px (full modal)
- Tablet: 481px - 768px (90% width)
- Mobile: ≤ 480px (98% width, adjusted padding)

## Usage

### Open Modal Programmatically
```javascript
// Open Privacy Policy modal
window.policyModal.open('privacyPolicyModal');

// Open Terms of Use modal
window.policyModal.open('termsOfUseModal');
```

### Close Modal Programmatically
```javascript
// Close specific modal
window.policyModal.close('privacyPolicyModal');
```

## Testing Checklist
- [ ] Click Privacy Policy link → modal opens
- [ ] Click Terms of Use link → modal opens
- [ ] Click X button → modal closes
- [ ] Click Close button → modal closes
- [ ] Click outside modal → modal closes
- [ ] Press ESC key → modal closes
- [ ] Check responsive on mobile
- [ ] Check responsive on tablet
- [ ] Check scrolling in modal body
- [ ] Check background scroll prevention
- [ ] Check animations are smooth

## Notes
- Modal menggunakan Jekyll liquid templates untuk dynamic content
- Last Updated date otomatis menggunakan Jekyll date filter
- Email dan phone placeholders menggunakan site variables
- CSS menggunakan liquid syntax untuk warna dinamis (normal untuk melihat lint errors)

## Future Enhancements
- [ ] Add print functionality
- [ ] Add download as PDF option
- [ ] Add version history
- [ ] Add multi-language support
- [ ] Add cookie consent integration
