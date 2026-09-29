# Setup Instructions – MOSMB Wedding 2027 SMS Opt-In

## Critical Decision: Phone Number to Display

**You must decide which number to put on the form:**

### Option A: Your Personal Phone Number
- **Use this if**: Guests know your personal number and expect to text you
- **Pros**: Guests can reach you directly; feels personal
- **Cons**: Your personal number is visible on a public website
- **Format**: Display exactly as guests would dial it (e.g., `(404) 555-0123` or `+1-404-555-0123`)

### Option B: Your Twilio Phone Number (Recommended for Compliance)
- **Use this if**: You bought a dedicated Twilio number for this campaign
- **Pros**: Better for compliance review; separates personal/business; Twilio routes messages through their platform
- **Cons**: Guests may not recognize the number; you'll need to inform them separately
- **Format**: Display as Twilio provides it (e.g., `+1-415-555-0199`)
- **How to find it**: Check your Twilio Console → Phone Numbers → Active Numbers

**Recommendation**: Use the Twilio number. Twilio reviewers expect to see the number they're approving, and it's cleaner for campaign tracking.

---

## Files to Build/Copy

### 1. **index.html** (needs to be built)
The opt-in form. Must include:

**Form fields:**
- Text input: "Phone Number" (optional, no `required` attribute)
- Checkbox: SMS consent (unchecked by default, separate from T&C)

**Required disclosures (at or adjacent to checkbox):**
```
"By providing your phone number and checking the box above, you agree to receive 
text messages from MOSMB Wedding 2027. Message frequency: up to 6 messages over 
6 months. Msg & data rates may apply. Reply STOP to unsubscribe. 
[Link to Privacy Policy] | [Link to Terms of Service]"
```

**Button:** Submit form (can be a standard button or Google Form redirect, as long as it's compliant)

**Design:**
- Mobile-responsive
- Clean, minimal (no animations or distracting elements)
- Clear typography
- Links to Privacy Policy and T&C must be publicly accessible

### 2. **privacy-policy.md** (already created, copy from parent)
Located at: `/home/claude/PRIVACY_POLICY.md`

**Modifications needed:**
- Change brand name from generic to "MOSMB Wedding 2027"
- Update "Contact Us" section with your contact info (email or phone)
- Add SMS-specific disclosures (already included in earlier draft):
  - Non-sharing of phone numbers
  - Message frequency (up to 6 over 6 months)
  - "Msg & data rates may apply"
  - How to opt out (Reply STOP)

### 3. **terms-and-conditions.md** (already created, copy from parent)
Located at: `/home/claude/TERMS_AND_CONDITIONS.md`

**Modifications needed:**
- Update brand name to "MOSMB Wedding 2027" (top and throughout)
- Remove any generic language; keep it specific to wedding SMS
- Ensure it mentions the registered brand name explicitly

### 4. **_config.yml** (GitHub Pages config)
Basic Jekyll config for GitHub Pages:
```yaml
theme: jekyll-theme-minimal
title: MOSMB Wedding 2027
description: SMS Event Notifications
markdown: kramdown
```

### 5. **assets/style.css** (optional, minimal styling)
Keep it simple:
- Readable font (serif or sans-serif, 16px+)
- Good contrast (dark text on light background)
- Mobile-first responsive design
- Form inputs clearly styled and labeled

---

## Deployment Steps

1. **Clone/initialize repo locally**:
   ```bash
   cd /Users/osama/code/twilio_external
   git init
   ```

2. **Add files**:
   - Copy `index.html`, `privacy-policy.md`, `terms-and-conditions.md`
   - Create `_config.yml`
   - Create `assets/style.css`
   - Keep this `README.md` and `INSTRUCTIONS.md`

3. **Commit and push to GitHub**:
   ```bash
   git add .
   git commit -m "Initial commit: wedding SMS opt-in form"
   git branch -M main
   git remote add origin https://github.com/mosdragon/twilio_external.git
   git push -u origin main
   ```

4. **Enable GitHub Pages**:
   - Go to repo Settings → Pages
   - Source: Deploy from a branch
   - Branch: `main` / `root`
   - Save

5. **Visit the live site**:
   - URL: `https://mosdragon.github.io/twilio_external/`
   - Verify form displays correctly
   - Test links to Privacy Policy and T&C

---

## Twilio Submission

Once the site is live, you'll submit to Twilio:

1. **Public URL to form**: `https://mosdragon.github.io/twilio_external/`
2. **Campaign message_flow description**:
   ```
   Guests opt in via our wedding website form at [URL].
   They provide their phone number (optional field) and check an unchecked-by-default 
   checkbox to consent to receive SMS updates about the MOSMB Wedding 2027.
   
   The form displays all required disclosures:
   - Brand name (MOSMB Wedding 2027)
   - Message frequency (up to 6 messages over 6 months)
   - "Msg & data rates may apply"
   - Opt-out instructions (Reply STOP)
   - Links to Privacy Policy and Terms of Service
   
   Privacy Policy: [URL]/privacy-policy.md
   Terms of Service: [URL]/terms-and-conditions.md
   ```

3. **Screenshots** (optional, but helpful):
   - Screenshot of the form on desktop
   - Screenshot of the form on mobile
   - Upload to a public location or share directly with Twilio

---

## Checklist Before Submitting to Twilio

- [ ] Phone number field is **optional** (no `required` attribute)
- [ ] SMS consent checkbox is **unchecked by default**
- [ ] Checkbox is **separate from T&C acceptance**
- [ ] All 4 required disclosures appear at/near the checkbox:
  - [ ] Brand name (MOSMB Wedding 2027)
  - [ ] Message frequency (up to 6 over 6 months)
  - [ ] Rates disclosure (Msg & data rates may apply)
  - [ ] Opt-out instructions (Reply STOP to unsubscribe)
- [ ] Links to Privacy Policy and T&C are publicly accessible
- [ ] Privacy Policy includes SMS-specific disclosures
- [ ] Terms of Service names the brand explicitly
- [ ] Site is live on GitHub Pages (publicly accessible)
- [ ] Form is mobile-responsive
- [ ] No JavaScript required to view consent language (static HTML preferred)

---

## Questions?

- **Twilio compliance questions**: https://help.twilio.com/articles/11847054539547-A2P-10DLC-Campaign-Approval-Best-Practices
- **A2P errors**: https://www.twilio.com/docs/api/errors (search error code)
- **Message frequency**: Double-check this is accurate before submitting

---

**Next**: Switch to the other Claude model to build `index.html` and finalize legal docs.