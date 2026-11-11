# Vidyora: school management portal

A school management portal in a single file, with a light glass design and Apple-style scroll animations. One installation serves several schools, and each school has separate portals for admins, teachers and students.

Open `index.html` in any modern browser. There is nothing to install or build.

## What's inside

**Home page (the product)**
- Scroll-linked hero, module walkthrough and a sideways-scrolling "A day at school" section
- Animated icons and illustrated characters (inline SVG, no image files)
- Portal cards for Student, Teacher and Admin
- Pricing: School plan at ₹3,000 per school, per month, with a checkout sheet (UPI, card, net banking; 1, 3, 6 or 12 months)
- Request a 1-hour demo: opens the portal with sample data, a countdown and a role switcher
- Contact form, with the office in Bhubaneswar, Odisha

**Inside each school**

| Section | Student | Teacher | Admin |
|---|---|---|---|
| Overview / school home page | ✓ | ✓ | ✓ (school home page) |
| Notice board | read | read | post, pin, delete |
| Mark sheet (previous year, half-yearly, current year) | own | edit class | view class |
| Syllabus tracker | read | update | update |
| Attendance | own calendar | take class attendance | students and teachers |
| Leave | apply | apply, approve students | approve anyone |
| Fees | pay | — | collection overview |
| Health records | own, read only | class, read only | edit |
| Analytics | — | ✓ | ✓ plus fees |
| Support staff | — | directory | manage |
| School setup (subjects, people, profile) | — | — | ✓ |
| Assistant (confirms before every change) | ✓ | ✓ | ✓ |

Sample schools: Halcyon Academy (Bhubaneswar), Kalinga Valley School (Cuttack) and Sunrise Public School (Puri).

## The assistant

The **Ask** button opens an assistant that answers questions and proposes changes. You confirm or cancel each change before it applies.

- On claude.ai it uses Claude through the artifact `sample` capability.
- Anywhere else, including GitHub Pages, `window.claude` doesn't exist. The assistant then falls back to a built-in command parser that understands a fixed set of phrasings, for example "apply for sick leave tomorrow", "mark Vihaan absent", "approve Kabir Sen's leave" or "post a notice: …".
- To use a real AI model outside claude.ai, connect it to your own backend: send the chat to an LLM API from your server. Never put an API key in this file.

## Demo-only parts (to do before going live)

- **Data:** sample data lives in the page and resets on reload. A real deployment needs a backend and database.
- **Sign-in:** pre-filled demo credentials, and any password works. Add real authentication.
- **Payments:** fee and subscription checkouts are simulated. Connect a payment gateway such as Razorpay.
- **1-hour demo:** the timer lives in the browser (localStorage). To enforce one demo per school, check it on the server.
- **Contact form:** not connected to email or a CRM yet.
- **Branding:** "Vidyora" is a working name. Add your real email and phone number to the contact section.

## Publish with GitHub Pages

1. Upload `index.html` and `README.md` to the root of the repository.
2. Go to **Settings → Pages**, set Source to *Deploy from a branch*, choose `main` and `/ (root)`, then click Save.
3. After a minute the site is live at `https://<your-username>.github.io/<repo-name>/`.

Fonts load from Google Fonts. Everything else (styles, scripts, icons, illustrations) is inside `index.html`.

## Tech

Plain HTML, CSS and JavaScript in one file, with no frameworks or dependencies. Fonts are Instrument Serif and Instrument Sans. The design respects `prefers-reduced-motion`.
