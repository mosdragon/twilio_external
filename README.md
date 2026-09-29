# MOSMB Wedding 2027 – SMS Opt-In Site

A GitHub Pages-hosted opt-in form for collecting guest phone numbers and SMS consent for wedding event notifications.

## Overview

This is a barebones, Twilio A2P 10DLC compliance-ready opt-in form that satisfies Twilio's Campaign Registration requirements for sending transactional SMS to wedding guests.

## Features

- **Compliant opt-in checkbox** – unchecked by default, separate from T&C
- **Required disclosures** – brand name, message frequency, rates, STOP to cancel
- **Links to legal docs** – Privacy Policy and Terms of Service both accessible
- **No backend** – static HTML, easily hosted on GitHub Pages
- **Mobile-responsive** – clean, minimal design

## What This Does

1. Collects guest phone numbers (optional field)
2. Requires explicit SMS consent via unchecked checkbox
3. Displays all Twilio-required messaging disclosures
4. Links to Privacy Policy and Terms of Service
5. Provides a public URL for Twilio compliance review

## Structure

```
twilio_external/
├── README.md                    (this file)
├── INSTRUCTIONS.md              (setup instructions)
├── index.html                   (the opt-in form)
├── privacy-policy.md            (privacy policy)
├── terms-and-conditions.md      (T&C)
├── _config.yml                  (GitHub Pages config)
└── assets/
    └── style.css                (minimal styling)
```

## Next Steps

1. **Inputs needed** (from user):
   - Phone number to display (personal or Twilio number – see INSTRUCTIONS.md)
   - Domain confirmation (mosdragon.github.io/twilio_external or custom domain)

2. **Build the site**:
   - Build `index.html` with the opt-in form
   - Copy legal docs (`privacy-policy.md`, `terms-and-conditions.md`)
   - Deploy to GitHub Pages

3. **Submit to Twilio**:
   - Public URL to the form
   - Screenshots of opt-in flow
   - URL to Privacy Policy and T&C

## Compliance Notes

- Checkbox is **unchecked by default** (active consent required)
- Phone number field is **optional** (not required for form submission)
- Messaging consent is **separate from T&C acceptance**
- All disclosures appear **at or adjacent to the checkbox**
- Privacy Policy includes required SMS-specific disclosures
- Terms of Service name the brand ("MOSMB Wedding 2027")

---

**Message frequency**: Up to 6 messages over 6 months  
**Brand name**: MOSMB Wedding 2027  
**Repository**: github.com/mosdragon/twilio_external