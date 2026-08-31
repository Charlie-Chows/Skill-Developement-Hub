# AGENTS.md

# SKILL DEVELOPMENT HUB — AI DEVELOPMENT SPECIFICATION

> **This document is the source of truth for building and modifying this project.**
>
> Read this file completely before making structural, visual, or functional changes.

---

# 1. PROJECT IDENTITY

## Product

**Skill Development Hub**

## Purpose

Build a premium, modern, image-rich website for a skill-development and career-learning platform.

The website should communicate:

- Practical skill development
- Technology learning
- Real-world projects
- Expert mentorship
- Career readiness
- Structured learning
- Confidence
- Professional growth
- Community
- Continuous improvement

Core message:

> **Learn practical skills. Build real projects. Become career-ready.**

The experience should feel like a modern education product, not a traditional coaching institute.

---

# 2. EXISTING PROJECT STRUCTURE — DO NOT CHANGE

The current project structure is the source of truth.

```text
/
├── 404.html
├── AGENTS.md
├── global.css
├── index.css
├── index.html
├── logo_trimmed.webp
├── ui_ux.jpg
├── web_dev.jpg
├── woman.jpg
│
├── assets/
│
├── css/
│   ├── about.css
│   ├── blog.css
│   ├── contact.css
│   ├── login.css
│   ├── services.css
│   └── signup.css
│
└── html/
    ├── about.html
    ├── admin.html
    ├── blog.html
    ├── contact.html
    ├── login.html
    ├── services.html
    ├── signup.html
    └── user.html
```

## Strict structure rules

Do NOT:

- Create React projects.
- Create Vue projects.
- Create Angular projects.
- Create Next.js projects.
- Create Vite projects.
- Create Webpack configuration.
- Create npm build systems.
- Create a `src/` directory.
- Create a `components/` directory.
- Create a `pages/` directory.
- Create a `js/` directory.
- Move existing HTML files.
- Move existing CSS files.
- Rename existing files.
- Introduce unnecessary folders.

JavaScript should remain inside the corresponding HTML files unless a future explicit instruction changes this architecture.

The `assets/` folder may contain additional images or supporting static assets when necessary.

---

# 3. TECHNOLOGY RULES

Use only:

- HTML5
- CSS3
- Vanilla JavaScript
- GSAP
- GSAP ScrollTrigger
- Font Awesome CDN when icons are required

Do NOT use:

- React
- Vue
- Angular
- Svelte
- Next.js
- Nuxt
- Astro
- Tailwind CSS
- Bootstrap
- jQuery
- TypeScript
- Webpack
- Vite
- Sass/SCSS
- Material UI
- Chakra UI
- Other component frameworks
- Other CSS frameworks

Use the simplest technology that solves the problem.

---

# 4. EXISTING FILE RESPONSIBILITIES

## Root

### `index.html`

Home page markup.

### `index.css`

Home-page-specific CSS.

### `global.css`

Global design system and reusable styles.

### `404.html`

404 page.

### `logo_trimmed.webp`

Existing brand logo.

Do not replace it.

### `web_dev.jpg`

Existing Web Development image.

### `ui_ux.jpg`

Existing UI/UX image.

### `woman.jpg`

Existing hero/person image.

Reuse these where relevant before introducing replacements.

---

# 5. HTML DIRECTORY

All secondary public/auth/dashboard HTML pages belong here:

```text
html/
├── about.html
├── admin.html
├── blog.html
├── contact.html
├── login.html
├── services.html
├── signup.html
└── user.html
```

Do not move these pages to the root.

---

# 6. CSS DIRECTORY

Page-specific styles belong here:

```text
css/
├── about.css
├── blog.css
├── contact.css
├── login.css
├── services.css
└── signup.css
```

## Important

There is no `user.css` or `admin.css` currently.

Therefore:

- Dashboard-specific CSS may be placed in the corresponding HTML `<style>` block if necessary.
- Or shared dashboard styles may be added carefully to `global.css`.
- Do not create dashboard CSS files unless explicitly requested.

---

# 7. PATH RULES

Because secondary HTML pages are inside `html/`, paths must be correct.

From:

```text
index.html
```

Use:

```text
html/about.html
html/services.html
html/blog.html
html/contact.html
html/login.html
html/signup.html
```

From:

```text
html/about.html
```

Use:

```text
../index.html
../logo_trimmed.webp
../global.css
../css/about.css
```

Similarly, all secondary pages must use `../` when referencing root-level files.

Never create broken paths such as:

```text
html/html/about.html
```

or:

```text
html/logo_trimmed.webp
```

unless the asset actually exists there.

---

# 8. DESIGN DIRECTION

The website must feel:

- Premium
- Modern
- Energetic
- Aspirational
- Human
- Technology-focused
- Career-oriented
- Trustworthy
- Clean
- Spacious
- Interactive
- Image-rich

Think:

**Premium SaaS + modern education platform + technology culture.**

Avoid:

- Generic coaching website aesthetics
- Old-fashioned education portals
- Excessive gradients
- Excessive glassmorphism
- Cheap template aesthetics
- Cartoonish education graphics
- Excessively rounded everything
- Dense card grids
- Visual clutter
- Random decorative effects

---

# 9. COLOR PALETTE

Use the existing project color system.

Primary tokens:

```css
--bg-main: #f8fafc;
--text-dark: #0f172a;
--text-muted: #64748b;

--primary-coral: #ff6b6b;
--primary-gradient: linear-gradient(135deg, #ff8a00, #e52e71);

--accent-pink: #f472b6;
--accent-purple: #c084fc;
--accent-blue: #60a5fa;
--accent-amber: #fbbf24;

--glass-bg: rgba(255, 255, 255, 0.65);
--glass-border: rgba(255, 255, 255, 0.8);
--glass-shadow: 0 20px 40px -15px rgba(0, 0, 0, 0.07);
```

Do not replace the visual system with unrelated colors.

## Color usage

Primary background:

- Very light
- Soft
- Clean

Primary text:

- Deep navy

Accent:

- Orange
- Pink
- Purple
- Blue
- Amber

Gradient:

```text
Orange → Pink
```

Use gradients selectively.

Do not make every component gradient.

---

# 10. TYPOGRAPHY

The project uses:

```css
Plus Jakarta Sans
```

Continue using it.

Typography should have strong hierarchy.

Recommended:

```text
Hero:
Very large / bold / tight line-height

Section heading:
Large / bold

Card heading:
Medium-large / semibold-bold

Body:
Readable / muted

Metadata:
Small / medium
```

Use:

```css
clamp()
```

for major responsive headings.

Avoid decorative fonts.

---

# 11. GLOBAL CSS PRINCIPLES

`global.css` should contain:

- Reset
- Root tokens
- Typography
- Body
- Container
- Buttons
- Common utility classes
- Shared cards
- Shared badges
- Shared glass panels
- Shared focus states
- Shared responsive rules where appropriate

Do not place complex page-specific layouts in `global.css`.

---

# 12. CONTAINER SYSTEM

Use a consistent content width.

Preferred maximum:

```css
max-width: 1240px;
```

Use:

```css
width: 100%;
margin-inline: auto;
padding-inline: 24px;
```

Adjust padding responsively.

Avoid random container widths across sections.

---

# 13. SPACING SYSTEM

Use a consistent vertical rhythm.

Typical major section spacing:

```text
Desktop:
100px – 140px

Tablet:
80px – 100px

Mobile:
64px – 80px
```

Do not use identical spacing blindly.

Spacing should reflect hierarchy.

---

# 14. BUTTON SYSTEM

Buttons should feel premium and tactile.

Primary CTA:

- Gradient or strong brand accent
- White text when using gradient
- Rounded pill or softly rounded rectangle
- Clear hover state

Secondary CTA:

- White/light surface
- Border
- Dark text or brand accent

Hover:

```text
translateY(-2px)
```

plus a subtle shadow.

Avoid excessive button animations.

---

# 15. BRAND LOGO

Use:

```text
logo_trimmed.webp
```

Do not replace it.

Do not generate another logo.

Do not use random logo images from the internet.

If the logo requires a visual variation:

- Use CSS filters.
- Use background/surface treatment.
- Preserve the original asset.

---

# 16. IMAGE-RICH DESIGN REQUIREMENT

The website MUST be image-rich.

Images should carry meaningful visual weight.

Prioritize:

- Students
- Developers
- Designers
- Mentors
- Collaboration
- Technology workspaces
- Laptops
- Coding
- Product design
- Learning
- Career development
- Workshops
- Project building
- Professional portraits

Use real imagery rather than relying entirely on CSS shapes.

---

# 17. EXISTING IMAGE ASSETS

Use the current assets intentionally.

### `woman.jpg`

Use for:

- Hero
- Student/learner visual
- Mentorship visual
- Career transformation visual

### `web_dev.jpg`

Use for:

- Web Development course
- Curriculum
- Course cards

### `ui_ux.jpg`

Use for:

- UI/UX course
- Design learning
- Curriculum

Do not repeatedly use the same image in every section.

---

# 18. ONLINE IMAGES

If additional imagery is required:

- Use high-quality, relevant sources.
- Prefer stable image URLs.
- Use image dimensions/aspect ratios that match the layout.
- Do not use watermarked images.
- Do not use random unrelated stock photography.
- Use `loading="lazy"` below the fold.
- Hero images may use eager loading.

Do not add unnecessary image dependencies.

---

# 19. IMAGE QUALITY

Every important image should have:

- Correct aspect ratio
- `object-fit: cover` where appropriate
- Rounded/clipped container
- Good crop
- Consistent visual treatment

Prevent layout shift by defining:

```css
aspect-ratio
```

or explicit dimensions when useful.

---

# 20. ALT TEXT

Meaningful image:

```html
alt="Developer learning frontend development on a laptop"
```

Decorative image:

```html
alt=""
```

Never use:

```text
image
photo
picture
img1
```

---

# 21. GLOBAL HEADER

Every public page should use a consistent header.

Desktop:

```text
Logo
Home
About
Services
Blog
Contact
Login / Primary CTA
```

The header should feel:

- Minimal
- Premium
- Spacious
- Clean

Prefer sticky/fixed positioning when appropriate.

After scrolling, the header may become:

- Slightly translucent
- Glassmorphic
- More compact
- Softly shadowed

Do not make it visually heavy.

---

# 22. HEADER RESPONSIVENESS

Desktop:

- Full navigation visible.

Mobile:

- Navigation hidden.
- Hamburger visible.
- Login/CTA may be moved into the menu.
- Menu becomes a full-screen or large overlay.

Hamburger must work.

---

# 23. MOBILE MENU

The hamburger menu must:

1. Open.
2. Animate in.
3. Prevent body scroll.
4. Display all important links.
5. Display CTA.
6. Show close button.
7. Close when a link is clicked.
8. Close when Escape is pressed.
9. Restore body scroll.
10. Be keyboard usable.

Animation:

```text
Overlay fade
+
Navigation stagger
+
CTA entrance
```

Use GSAP if already loaded.

---

# 24. HEADER PATHS

From root `index.html`:

```text
Home → index.html
About → html/about.html
Services → html/services.html
Blog → html/blog.html
Contact → html/contact.html
Login → html/login.html
```

From secondary pages:

```text
Home → ../index.html
About → about.html
Services → services.html
Blog → blog.html
Contact → contact.html
Login → login.html
```

---

# 25. FOOTER

Public pages should use a consistent footer.

Possible groups:

```text
Brand
Learning
Company
Resources
Support
Social
CTA
Copyright
```

Do not create a completely different footer per page.

---

# 26. HOME PAGE — EXACTLY 10 MAJOR SECTIONS

`index.html` must contain exactly:

**10 major sections.**

Do not add an 11th major section unless explicitly requested.

---

# 27. HOME — SECTION 1: HERO

Hero purpose:

Immediately explain:

- What the platform is.
- What learners gain.
- Why it is valuable.

Recommended composition:

```text
LEFT:
Eyebrow
Headline
Description
Primary CTA
Secondary CTA

RIGHT:
Large learner image
Floating course card
Rating/outcome card
Progress card
Decorative gradients
```

Use asymmetric composition.

Suggested headline direction:

> Build Skills That Move Your Career Forward.

Do not treat this exact sentence as mandatory if final content changes.

Hero must be visually strong.

---

# 28. HERO IMAGE TREATMENT

Use `woman.jpg` or the most relevant approved image.

Possible treatments:

- Arch
- Rounded portrait
- Organic mask
- Large rounded rectangle
- Gradient frame
- Overlapping cards
- Image collage

Do not distort the image.

---

# 29. HERO FLOATING CARDS

Use a limited number.

Possible:

```text
4.9 Rating
10K+ Learners
95% Progress
Project Completed
```

Numbers must NOT be fabricated.

If real values are unavailable:

- Use non-numeric labels.
- Or use obvious placeholder content during development.

Do not present fake statistics as real.

---

# 30. HERO ANIMATION

Recommended order:

```text
Navbar
↓
Eyebrow
↓
Headline
↓
Paragraph
↓
CTA
↓
Hero image
↓
Floating cards
```

Use:

- Fade
- Slide
- Mask reveal
- Scale
- Stagger

Do not make the page wait too long before becoming usable.

---

# 31. HOME — SECTION 2: TRUST / OUTCOMES

Purpose:

Build credibility.

Possible:

- Learning community
- Partner logos if supplied
- Ratings
- Learner outcomes
- Certifications
- Course completion

If actual logos or claims are not supplied, do not fabricate them.

Visual patterns:

- Logo marquee
- Metric strip
- Floating badges
- Horizontal scrolling labels

---

# 32. HOME — SECTION 3: LEARNING PATHS

Show major learning categories.

Possible:

```text
Web Development
Full-Stack Development
UI/UX Design
Data / AI
Leadership
Career Development
```

Cards should include:

- Image
- Category
- Description
- Metadata
- Arrow
- Hover interaction

Prefer:

- Bento grid
- Asymmetric grid
- Featured card + smaller cards

Avoid six identical rectangles.

Existing:

```text
web_dev.jpg
ui_ux.jpg
```

should be reused where appropriate.

---

# 33. HOME — SECTION 4: WHY LEARN WITH US

Focus on differentiators:

- Expert mentorship
- Practical projects
- Structured curriculum
- Career guidance
- Interview preparation
- Industry-focused learning

Recommended:

```text
Large image
+
Editorial text
+
Feature list
```

Use a strong visual composition.

---

# 34. HOME — SECTION 5: REAL-WORLD PROJECTS

Purpose:

Show learners what they build.

Use:

- Project screenshots
- UI previews
- Code previews
- Product cards
- Technology tags
- Difficulty
- Category

Visual patterns:

- Horizontal gallery
- Overlapping cards
- Large featured project
- Stacked previews

Project imagery should dominate.

---

# 35. HOME — SECTION 6: MENTORS

Show credible mentors/instructors.

Possible card:

```text
Portrait
Name
Role
Expertise
Skill tags
```

Avoid fake credentials.

If no real mentor data is available, use clearly editable placeholder content rather than invented real-world claims.

Visual pattern:

- Large portrait
- Hover reveal
- Offset cards
- Editorial grid

---

# 36. HOME — SECTION 7: STUDENT JOURNEY

Tell the learning story:

```text
Start
↓
Learn
↓
Practice
↓
Build
↓
Prepare
↓
Launch
```

Use:

- Timeline
- Progress bar
- Sticky image
- Animated checkpoints
- Floating achievement cards

This should feel like movement and progress.

---

# 37. HOME — SECTION 8: STUDENT STORIES

Use:

- Large student image
- Quote
- Name
- Course
- Role/outcome where supplied

Possible visual treatment:

- Testimonial spotlight
- Large quote
- Image collage
- Horizontal slider
- Marquee

Do not create fake testimonials.

Use placeholders when final content is unavailable.

---

# 38. HOME — SECTION 9: CAREER OUTCOMES

Show measurable outcomes only when supplied.

Possible:

- Learners trained
- Projects built
- Courses
- Mentors
- Career transitions

Visual treatment:

- Large counters
- Progress rings
- Editorial statistics
- Charts
- Image collage

Counters should animate only on valid numerical content.

---

# 39. HOME — SECTION 10: FINAL CTA

End with a strong conversion section.

Suggested direction:

> Ready to Build Your Next Skill?

Include:

- Primary CTA
- Secondary action if needed
- Large image/collage
- Gradient background/glow
- Floating learning UI

This is the visual conclusion of the page.

---

# 40. ABOUT PAGE — EXACTLY 8 MAJOR SECTIONS

File:

```text
html/about.html
```

Use:

```text
1. About Hero
2. Mission
3. Our Story
4. Learning Philosophy
5. Teaching Approach
6. Mentors / Team
7. Values / Impact
8. CTA
```

Do not make this a wall of text.

Use imagery and editorial composition.

---

# 41. SERVICES PAGE — EXACTLY 8 MAJOR SECTIONS

File:

```text
html/services.html
```

Use:

```text
1. Courses Hero
2. Course Categories
3. Featured Programs
4. Curriculum / Course Detail
5. Learning Benefits
6. Practical Projects
7. Career Support
8. CTA
```

Course cards should communicate:

- Image
- Course
- Level
- Duration
- Skills
- Description
- CTA

---

# 42. BLOG PAGE — EXACTLY 8 MAJOR SECTIONS

File:

```text
html/blog.html
```

Use:

```text
1. Blog Hero
2. Featured Article
3. Categories
4. Latest Articles
5. Technology / Career Articles
6. Learning Resources
7. Newsletter
8. CTA
```

Use editorial layouts.

Avoid generic blog-card repetition.

---

# 43. CONTACT PAGE — EXACTLY 8 MAJOR SECTIONS

File:

```text
html/contact.html
```

Use:

```text
1. Contact Hero
2. Contact Information
3. Contact Form
4. Support / Assistance
5. FAQ
6. Location / Learning Center
7. Social / Community
8. CTA
```

Contact form requires frontend validation.

---

# 44. 404 PAGE

Root file:

```text
404.html
```

Include:

- 404
- Explanation
- Back to Home
- Go Back

Back Home:

```text
index.html
```

Go Back:

```javascript
history.back();
```

If history is unavailable:

```text
index.html
```

Visual direction:

- Large typography
- Soft gradient
- Floating course UI
- Minimal motion

---

# 45. LOGIN PAGE

File:

```text
html/login.html
```

Include:

- Logo
- Email
- Password
- Custom role dropdown
- Login
- Forgot Password
- Social login button 1
- Social login button 2
- Create Account

Visual design must match the public website.

---

# 46. LOGIN ROLE DROPDOWN

Do NOT use:

```html
<select>
```

Use custom HTML/JS.

Roles:

```text
User
Admin
```

Required behavior:

- Open
- Close
- Select
- Outside click close
- Escape close
- Visible active state
- Responsive
- Keyboard-friendly

---

# 47. LOGIN VALIDATION

Validate:

```text
Email required
Valid email
Password required
Role selected
```

On success:

```text
User → html/user.html
Admin → html/admin.html
```

No backend is required unless explicitly requested.

---

# 48. LOGIN SESSION

If login state is required:

Use:

```javascript
localStorage
```

Store only non-sensitive frontend demo information.

Do NOT store:

- Real passwords
- API keys
- Secrets
- Tokens supplied by real authentication systems

---

# 49. USERNAME DISPLAY

For demo UI:

```text
john.doe@gmail.com
```

may display:

```text
Hello John Doe
```

Use simple frontend parsing.

---

# 50. LOGIN REDIRECTS

Forgot Password:

```text
../404.html
```

Social Login:

```text
../404.html
```

Create Account:

```text
signup.html
```

---

# 51. SIGNUP PAGE

File:

```text
html/signup.html
```

Include:

- Logo
- Email
- Password
- Confirm Password
- Role dropdown
- Sign Up

Validation:

- Required fields
- Valid email
- Password requirement
- Confirm password
- Password matching
- Role selected

Success:

```text
login.html
```

No backend account creation.

---

# 52. USER DASHBOARD

File:

```text
html/user.html
```

The User Dashboard should feel like a real learning product.

Suggested navigation:

```text
Dashboard
My Courses
Projects
Progress
Profile
Logout
```

Possible content:

- Continue learning
- Current course
- Course progress
- Upcoming lesson
- Projects
- Certificates
- Achievements
- Learning streak
- Recommendations

User dashboard priority:

**Learning + Progress + Personal Growth**

---

# 53. ADMIN DASHBOARD

File:

```text
html/admin.html
```

Admin must NOT be a copy of User.

Suggested navigation:

```text
Overview
Learners
Courses
Mentors
Analytics
Settings
Logout
```

Possible content:

- Learners
- Course enrollments
- Course performance
- Mentor activity
- Completion rates
- Support requests
- Platform metrics

Do not fabricate business numbers as factual data.

---

# 54. USER VS ADMIN

User:

```text
Learning
Progress
Courses
Projects
Achievements
Profile
```

Admin:

```text
Management
Learners
Courses
Mentors
Analytics
Settings
```

The two dashboards must have different information hierarchy.

---

# 55. DASHBOARD RESPONSIVENESS

Desktop:

- Sidebar
- Header
- Main content

Tablet:

- Narrow sidebar or collapsible sidebar

Mobile:

- Sidebar becomes drawer/overlay
- Hamburger controls it
- Content becomes single-column

No horizontal scrolling.

---

# 56. LOGOUT

Logout must:

1. Clear demo login/session data.
2. Redirect to:

```text
../index.html
```

from dashboards.

---

# 57. COURSE CARD DESIGN

Reusable course cards can contain:

- Image
- Category
- Title
- Description
- Instructor
- Level
- Duration
- Rating
- Skill tags
- CTA

Possible hover:

```text
Image zoom
Card lift
Arrow movement
Overlay
```

Use only one or two effects at once.

---

# 58. GLASSMORPHISM

Glass can be used for:

- Floating cards
- Header
- Small UI
- Badges
- Hero overlays

Do not make the entire website glassmorphic.

Use:

```css
backdrop-filter: blur(...)
```

only where useful.

---

# 59. BENTO GRIDS

Bento layouts are encouraged for:

- Learning paths
- Features
- Projects
- Dashboard summaries
- Career outcomes

Vary card sizes.

Do not make every card identical.

---

# 60. EDITORIAL LAYOUTS

Use editorial layouts for:

- About
- Why Learn With Us
- Mentors
- Testimonials
- Learning Journey

Use:

- Large typography
- Offset images
- Strong whitespace
- Asymmetric positioning

---

# 61. OVERLAPPING ELEMENTS

Use overlaps for visual depth.

Examples:

```text
Image
+
Floating card
+
Badge
```

or:

```text
Large project image
+
small metadata card
```

Ensure overlaps do not break mobile layout.

---

# 62. ANIMATION PHILOSOPHY

Animation is important but must remain intentional.

Every major section should have a visual motion concept.

Do not:

```text
fade-up everything
```

Use different animation directions and patterns.

---

# 63. GSAP

Use GSAP for:

- Hero entrance
- Section reveals
- Stagger
- Counters
- Image movement
- Floating cards
- Marquees
- Scroll storytelling
- Hover interactions where useful

Load GSAP before using it.

---

# 64. GSAP SCROLLTRIGGER

Use ScrollTrigger for:

- Section entrance
- Image reveal
- Staggered cards
- Horizontal galleries
- Parallax
- Sticky storytelling
- Progress timelines
- Counters
- CTA reveal

Do not create hundreds of ScrollTriggers.

---

# 65. HERO ANIMATION TIMELINE

Preferred:

```text
0ms:
Header

150ms:
Eyebrow

250ms:
Heading

400ms:
Description

500ms:
CTA

650ms:
Image

800ms:
Floating UI
```

These values are guidelines.

Adjust according to actual composition.

---

# 66. TEXT REVEALS

Possible:

- Fade + translate
- Line reveal
- Word reveal
- Mask reveal
- Blur + fade

Use character animation sparingly.

Hero heading may use word/line animation.

Do not animate every heading character-by-character.

---

# 67. IMAGE REVEALS

Possible:

```text
clip-path
scale
opacity
translate
```

Recommended:

```text
Image starts slightly scaled
+
masked/offset
↓
reveals
↓
settles at scale 1
```

Avoid aggressive zoom.

---

# 68. STAGGER

Related elements may use:

```text
50ms – 150ms
```

Example:

```text
Card 1 → 0ms
Card 2 → 80ms
Card 3 → 160ms
Card 4 → 240ms
```

Keep sequences short.

---

# 69. FLOATING ELEMENTS

Selected cards/decorations may float:

```text
Y: 0 → -8px → 0
Duration: 3–6 seconds
```

Good targets:

- Achievement badge
- Course card
- Decorative orb
- Progress card

Do not float:

- Main navigation
- Forms
- Important buttons
- Main text

---

# 70. MARQUEE

Use for:

- Skills
- Technologies
- Partner logos when supplied
- Categories
- Learning outcomes

Marquee should be smooth and continuous.

Do not make it too fast.

---

# 71. COUNTERS

Counters may animate:

```text
0 → target
```

Only use real/approved values.

If the value is unknown, do not invent it.

---

# 72. PARALLAX

Use subtle parallax for:

- Hero background
- Large images
- Decorative shapes
- CTA background

Avoid excessive movement.

---

# 73. PINNED SECTIONS

Use pinned sections only where storytelling benefits.

Good:

```text
Learning Journey
Career Transformation
Project Building
```

Do not pin ordinary cards.

---

# 74. HOVER SYSTEM

Use subtle interactions:

```text
translateY(-3px)
scale(1.02)
image scale(1.04)
shadow increase
arrow translate
```

Do not combine all effects.

---

# 75. RESPONSIVE DESIGN

Every page must work at:

- 1440px
- 1280px
- 1024px
- 860px
- 768px
- 600px
- 480px
- 390px
- 320px

Do not rely exclusively on fixed desktop dimensions.

---

# 76. MOBILE DESIGN

Do not simply shrink desktop.

Instead:

- Recompose layouts.
- Stack sections.
- Reduce decoration.
- Preserve hierarchy.
- Keep CTAs accessible.
- Crop images intentionally.
- Convert horizontal layouts into vertical stories.
- Simplify dashboard navigation.
- Reduce animation intensity.

---

# 77. RESPONSIVE BREAKPOINTS

Suggested:

```css
1200px
1024px
860px
768px
600px
480px
```

Avoid excessive breakpoints.

Use fluid sizing with:

```css
clamp()
min()
max()
```

where useful.

---

# 78. NO HORIZONTAL OVERFLOW

The final website must not produce accidental horizontal scrolling.

Check:

- Hero
- Marquees
- Images
- Cards
- Dashboard
- Tables
- Navigation
- Decorative elements

Avoid:

```css
width: 100vw;
```

when it causes scrollbar issues.

---

# 79. ACCESSIBILITY

Use semantic elements:

```html
<header>
<nav>
<main>
<section>
<article>
<footer>
```

Interactive controls must be actual:

```html
<button>
```

or:

```html
<a>
```

where appropriate.

Forms need labels.

Images need alt text.

Maintain readable contrast.

---

# 80. KEYBOARD ACCESS

Important controls should support:

- Tab
- Enter
- Space
- Escape

Especially:

- Hamburger
- Mobile close
- Dropdown
- Forms
- Dashboard navigation

---

# 81. FOCUS STATES

Never remove focus outlines without replacement.

Use a visible focus state.

Example:

```css
:focus-visible {
  outline: 3px solid rgba(...);
  outline-offset: 3px;
}
```

Use a color compatible with the existing palette.

---

# 82. REDUCED MOTION

Implement:

```css
@media (prefers-reduced-motion: reduce)
```

When reduced motion is enabled:

- Reduce transitions.
- Disable major parallax.
- Disable continuous floating.
- Reduce ScrollTrigger movement.
- Keep content visible.
- Preserve functionality.

GSAP code should detect reduced-motion where practical.

---

# 83. PERFORMANCE

Prefer animating:

```text
transform
opacity
```

Avoid unnecessary animation of:

```text
width
height
top
left
```

Avoid:

- Huge images
- Excessive DOM nodes
- Hundreds of ScrollTriggers
- Repeated listeners
- Duplicate scripts
- Heavy libraries
- Unnecessary video
- Excessive blur

---

# 84. IMAGE LOADING

Below-fold images:

```html
loading="lazy"
```

Hero:

```html
loading="eager"
```

when justified.

Do not lazy-load critical above-the-fold imagery.

---

# 85. JAVASCRIPT ARCHITECTURE

JavaScript belongs in each corresponding HTML page.

Use clear sections:

```javascript
// Navigation
// Mobile menu
// Dropdown
// Form validation
// Dashboard
// GSAP animations
// ScrollTrigger
```

Avoid global variable pollution where possible.

Use:

```javascript
const
let
```

instead of:

```javascript
var
```

---

# 86. MISSING ELEMENT GUARDS

When initializing shared behavior:

```javascript
const element = document.querySelector(...);

if (element) {
  // behavior
}
```

Do not allow missing optional elements to crash the entire page.

---

# 87. MOBILE MENU IMPLEMENTATION

The mobile menu must:

```javascript
open
close
Escape
outside click where appropriate
body lock
body unlock
```

Avoid duplicate event listeners.

---

# 88. CUSTOM DROPDOWN IMPLEMENTATION

Custom dropdown must support:

```text
Open
Close
Select
Outside click
Escape
Selected state
```

Prefer a button-based trigger.

Do not use native `<select>` for the specified role selector.

---

# 89. FORM VALIDATION

Show:

- Error
- Success
- Invalid state
- Required state

Validation should not rely only on HTML attributes.

Use JavaScript for meaningful feedback.

---

# 90. DASHBOARD STATE

Demo authentication can use:

```javascript
localStorage
```

Possible keys:

```text
skillHubUser
skillHubRole
```

Use namespaced keys to avoid collisions.

Do not store sensitive credentials.

---

# 91. DASHBOARD PROTECTION

If demo login state is required:

```text
No role
→ redirect to login
```

If:

```text
role === "user"
```

allow User Dashboard.

If:

```text
role === "admin"
```

allow Admin Dashboard.

This is only frontend demo behavior, not real authentication security.

---

# 92. USER DASHBOARD UI

Prioritize:

- Continue learning
- Course progress
- Projects
- Achievements
- Upcoming learning
- Recommendations

Use visual UI:

- Progress bars
- Course thumbnails
- Stat cards
- Timeline
- Project previews

---

# 93. ADMIN DASHBOARD UI

Prioritize:

- Learner management
- Course management
- Mentor management
- Analytics
- Platform activity

Use visual UI:

- KPI cards
- Tables
- Progress bars
- Charts
- Activity lists

Do not use a chart library.

Use:

- CSS
- SVG
- Canvas

when charts are required.

---

# 94. DASHBOARD CHARTS

Charts should:

- Be responsive.
- Animate.
- Have labels.
- Match the color palette.
- Remain readable.
- Avoid unnecessary decoration.

Possible:

```text
SVG line chart
SVG bar chart
CSS progress
SVG donut
```

---

# 95. CONTENT STYLE

Content should be:

- Human
- Clear
- Motivating
- Practical
- Career-focused
- Concise

Prefer:

> Build practical skills you can use at work.

Avoid:

> Advanced competency acquisition architecture.

---

# 96. NO FABRICATED CLAIMS

Do not invent:

- Student counts
- Hiring percentages
- Salary increases
- Company partnerships
- Accreditations
- Certifications
- Instructor credentials
- Ratings
- Reviews
- Course completion percentages

If content is unavailable:

Use:

```text
[Student count]
[Instructor name]
[Course duration]
```

or neutral placeholder copy that is clearly editable.

---

# 97. NO FAKE LOGOS

Do not create fake partner/company logos.

If no approved logos exist:

Use:

- Technology names
- Skill labels
- Neutral learning categories

Do not imply partnerships.

---

# 98. COURSE CONTENT

Course categories can include:

```text
Web Development
Full-Stack Development
UI/UX Design
Data / AI
Leadership
Career Development
```

These are design/content directions, not claims about actual courses unless confirmed.

---

# 99. SOCIAL LINKS

If real social URLs are not provided:

Do not invent them.

Use:

- Placeholder buttons
- `#`
- Or omit the link until supplied

Do not create fake social profiles.

---

# 100. ICON SYSTEM

Use Font Awesome where useful.

Examples:

```html
<i class="fa-solid fa-code"></i>
<i class="fa-solid fa-graduation-cap"></i>
<i class="fa-solid fa-briefcase"></i>
<i class="fa-solid fa-arrow-right"></i>
```

Do not overuse icons.

Icons should reinforce meaning.

---

# 101. DECORATIVE BACKGROUNDS

Use:

- Radial gradients
- Soft blobs
- Grid textures
- Noise-like subtle overlays
- Blurred gradient orbs

Keep opacity low.

Decorations should never compete with content.

---

# 102. GRADIENT ORBS

Good use:

```text
Hero background
CTA background
Section transition
```

Bad use:

```text
Every card
Every button
Every heading
```

Use a small number of controlled decorative elements.

---

# 103. GLASS CARDS

Good use:

```text
Hero floating card
Stats overlay
Progress card
Header after scroll
```

Keep content surfaces mostly solid/light for readability.

---

# 104. IMAGE MASKS

Image masks are encouraged for:

- Hero
- About
- Mentors
- CTA

Possible shapes:

- Rounded arch
- Blob
- Organic rectangle
- Diagonal clip

Do not use complicated masks if they harm responsive behavior.

---

# 105. SECTION TRANSITIONS

Sections should flow naturally.

Use:

- Background shifts
- Gradient glows
- Image overlap
- Soft borders
- Large spacing

Avoid arbitrary dividers everywhere.

---

# 106. PAGE LOADING

Do not create a long blocking preloader.

If a preloader is necessary:

- Keep it under a short duration.
- Never hide content indefinitely.
- Respect reduced motion.
- Allow page usability quickly.

---

# 107. SCROLL BEHAVIOR

Use:

```css
scroll-behavior: smooth;
```

only if it does not interfere with accessibility.

Anchor links should account for sticky header height.

---

# 108. ANCHOR TARGETS

When sections are directly linked:

```css
scroll-margin-top
```

should account for the sticky header.

---

# 109. CSS ORGANIZATION

Organize page CSS roughly:

```text
Page variables
Hero
Section 1
Section 2
Section 3
...
Footer adjustments
Responsive
```

Use comments for major areas.

Avoid thousands of unexplained selectors.

---

# 110. CSS NAMING

Prefer descriptive classes:

```text
hero-content
course-card
course-image
mentor-card
journey-step
testimonial-card
dashboard-sidebar
```

Avoid:

```text
box1
thing
item2
abc
```

---

# 111. CSS SPECIFICITY

Avoid excessive:

```css
!important
```

Use it only when genuinely necessary.

Avoid deeply nested selectors.

---

# 112. HTML STRUCTURE

Use semantic structure.

Example:

```html
<main>
  <section class="hero">
    ...
  </section>

  <section class="learning-paths">
    ...
  </section>
</main>
```

Do not build the entire page from generic `<div>` elements.

---

# 113. LINKS VS BUTTONS

Use:

```html
<a>
```

for navigation.

Use:

```html
<button>
```

for actions.

Do not use clickable `<div>` elements for normal controls.

---

# 114. EXTERNAL CDNS

Only use trusted CDNs.

Do not add random external scripts.

Do not add:

- Tracking scripts
- Unknown analytics
- Unknown widgets
- Suspicious JavaScript

unless explicitly requested.

---

# 115. SECURITY

Never put:

- API keys
- Passwords
- Secrets
- Private tokens

inside frontend source.

Frontend demo authentication is not secure authentication.

---

# 116. RESPONSIVE IMAGE CROPPING

Use:

```css
object-fit: cover;
object-position: center;
```

Adjust `object-position` when the subject needs preservation.

On mobile, prioritize faces and important visual subjects.

---

# 117. MOBILE TYPOGRAPHY

Hero heading should remain impactful but fit comfortably.

Avoid:

- Extremely large text causing overflow.
- Long unbroken words.
- Tiny body text.

Use:

```css
font-size: clamp(...)
```

---

# 118. MOBILE CTA

Primary CTA should be easy to tap.

Recommended minimum touch target:

```text
44px
```

Do not place tiny links beside important buttons.

---

# 119. MOBILE CARDS

On mobile:

- Use one-column layouts where needed.
- Avoid cramped two-column cards.
- Preserve image visibility.
- Maintain card spacing.
- Keep metadata readable.

---

# 120. MOBILE MARQUEES

Marquees must not cause page overflow.

Use an internal clipped track.

Example concept:

```css
overflow: hidden;
```

Do not let the moving track expand the page width.

---

# 121. MOBILE DASHBOARD

The dashboard should transform from:

```text
Sidebar
+
Content
```

into:

```text
Top bar
+
Drawer
+
Content
```

Do not force a desktop sidebar into a 320px screen.

---

# 122. ANIMATION RESPONSIVENESS

On mobile:

- Reduce movement distance.
- Reduce number of simultaneous elements.
- Reduce parallax.
- Avoid expensive pinned layouts when they create usability problems.

---

# 123. REDUCED MOTION IMPLEMENTATION

Use a JS flag:

```javascript
const prefersReducedMotion =
  window.matchMedia('(prefers-reduced-motion: reduce)').matches;
```

If true:

- Use minimal GSAP animations.
- Avoid continuous loops.
- Avoid major parallax.

---

# 124. GSAP CONTEXT

Where multiple animations are initialized together, use GSAP context where appropriate.

Example concept:

```javascript
const ctx = gsap.context(() => {
  // animations
});
```

Avoid duplicate initialization.

---

# 125. SCROLLTRIGGER CLEANUP

Do not create duplicate ScrollTriggers after dynamic reinitialization.

Where necessary:

```javascript
ScrollTrigger.refresh();
```

or kill/rebuild the relevant animation context.

---

# 126. HOVER ON TOUCH DEVICES

Do not rely on hover for essential information.

If a card's content is essential:

- Show it by default on mobile.
- Use click/tap interaction when appropriate.

---

# 127. LOADING STATES

Forms and demo interactions should provide feedback.

Examples:

```text
Submitting...
Success
Please check the highlighted fields
```

Do not create fake network delays unless visually necessary.

---

# 128. ERROR STATES

Error messages should be:

- Clear
- Close to the affected field
- Readable
- Non-destructive

Avoid vague:

```text
Something went wrong.
```

when a specific explanation is available.

---

# 129. EMPTY STATES

Dashboard sections with no data should not look broken.

Example:

```text
No projects yet.
Start your first project to see it here.
```

Use a visual empty state.

---

# 130. NAVIGATION ACTIVE STATES

Current page should be visually identifiable.

Use:

- Accent color
- Underline
- Small indicator
- Background highlight

Do not rely only on color.

---

# 131. HEADER SCROLL STATE

A sticky header can change after scrolling.

Possible:

```text
Top:
Transparent/light

Scrolled:
White/glass
+
shadow
+
smaller padding
```

Transition:

```text
200–350ms
```

---

# 132. SECTION REVEALS

Every major section may use one main reveal.

Examples:

```text
Text left
Image right

Heading top
Cards bottom

Image scale
Text fade

Horizontal project track
```

Avoid repeating the same animation everywhere.

---

# 133. VISUAL HIERARCHY

Every section must answer:

1. What is this?
2. Why does it matter?
3. What should I look at?
4. What should I do?

If a section cannot answer these visually, simplify it.

---

# 134. IMAGE-FIRST SECTIONS

At least several major Home sections should be strongly visual.

Recommended:

```text
Hero
Learning Paths
Why Learn With Us
Projects
Mentors
Journey
Testimonials
CTA
```

Do not create a text-heavy website.

---

# 135. DESIGN DENSITY

Use whitespace.

Do not fill every area.

Premium design depends on:

```text
Content
+
Whitespace
+
Hierarchy
+
Controlled decoration
```

---

# 136. CARD RADIUS

Use a consistent radius system.

Possible:

```text
Small:
12px

Medium:
18px

Large:
24–32px

Pills:
999px
```

Do not use 20 different radius values.

---

# 137. SHADOWS

Shadows should be:

- Soft
- Low opacity
- Large blur
- Subtle

Avoid dark, heavy shadows.

---

# 138. BORDERS

Use subtle borders:

```text
rgba(15, 23, 42, 0.06)
```

or the existing glass border.

Avoid thick borders.

---

# 139. BACKDROP BLUR

Use sparingly.

Too much blur hurts:

- Performance
- Contrast
- Clarity

---

# 140. PAGE-SPECIFIC THEMING

Pages may have slightly different visual emphasis but must still share:

- Typography
- Color system
- Header
- Button system
- Spacing
- Card language
- Animation language

Do not make pages look like unrelated websites.

---

# 141. ABOUT VISUAL DIRECTION

About should feel:

```text
Human
+
Purposeful
+
Editorial
+
Trustworthy
```

Use real imagery and strong mission statements.

---

# 142. SERVICES VISUAL DIRECTION

Services should feel:

```text
Product catalog
+
Learning platform
+
Technology
```

Use course imagery and metadata.

---

# 143. BLOG VISUAL DIRECTION

Blog should feel:

```text
Modern publication
+
Technology magazine
+
Career resource
```

Use strong article imagery.

---

# 144. CONTACT VISUAL DIRECTION

Contact should feel:

```text
Friendly
+
Accessible
+
Professional
```

Use visual contact information rather than only a form.

---

# 145. AUTH VISUAL DIRECTION

Login/signup should feel:

```text
Focused
+
Premium
+
Simple
```

Do not overload authentication pages with animations.

---

# 146. DASHBOARD VISUAL DIRECTION

User:

```text
Learning workspace
```

Admin:

```text
Management workspace
```

Both should use the same brand system but different hierarchy.

---

# 147. CONTENT PLACEHOLDERS

If final copy is unknown, use obvious editable placeholders.

Good:

```text
[Course Description]
[Instructor Name]
[Course Duration]
```

Bad:

```text
We have 98% placement with top companies.
```

when not supplied.

---

# 148. DEVELOPMENT WORKFLOW

Before changing a page:

1. Read `AGENTS.md`.
2. Inspect the current HTML.
3. Inspect the relevant CSS.
4. Identify reusable existing styles.
5. Preserve working behavior.
6. Make the smallest appropriate change.
7. Check responsive behavior.
8. Check navigation paths.
9. Check animations.
10. Check console errors.

---

# 149. DO NOT REWRITE UNRELATED FILES

If changing:

```text
services.html
```

do not rewrite:

```text
blog.html
```

unless necessary.

Keep changes scoped.

---

# 150. BEFORE ADDING A NEW COMPONENT

Ask:

```text
Does an existing component already solve this?
```

If yes:

- Reuse it.

If no:

- Create a reusable pattern if the component will appear more than once.

---

# 151. BEFORE ADDING ANIMATION

Ask:

```text
What does this animation communicate?
```

If the answer is only:

```text
It looks cool.
```

simplify or remove it.

---

# 152. ANIMATION QUALITY STANDARD

Good:

```text
Smooth
Fast
Directional
Purposeful
Responsive
Accessible
```

Bad:

```text
Slow
Jumpy
Random
Overdone
Blocking
```

---

# 153. HERO QUALITY STANDARD

The hero should communicate the product within approximately the first viewport.

Visitor should understand:

```text
What:
Skill Development Hub

Who:
People developing practical skills

Why:
Career growth

Action:
Start learning / Explore courses
```

---

# 154. ABOVE-THE-FOLD PRIORITY

Above the fold should contain:

- Brand
- Navigation
- Main proposition
- CTA
- Strong image
- One or two credibility signals

Do not push the primary message below the fold.

---

# 155. SEO BASICS

Every public page should have:

```html
<title>
<meta name="description">
```

Use meaningful titles.

Example:

```text
Skill Development Hub | Learn Skills That Move Your Career Forward
```

Avoid duplicate page titles.

---

# 156. SEMANTIC HEADINGS

Use:

```text
One primary H1
H2 for major sections
H3 for cards/subsections
```

Do not use headings purely for visual size.

---

# 157. LINK ACCESSIBILITY

Avoid vague navigation when possible.

Prefer:

```text
Explore Courses
View Projects
Meet Our Mentors
```

over:

```text
Click Here
```

---

# 158. FORM LABELS

Every form control must have an associated label.

Do not rely only on placeholders.

---

# 159. PLACEHOLDER USAGE

Placeholder text can support a label.

It should not replace the label.

---

# 160. ARIA

Use ARIA only when needed.

Examples:

```text
aria-expanded
aria-controls
aria-label
aria-current
```

Do not add unnecessary ARIA.

---

# 161. MOBILE HAMBURGER ACCESSIBILITY

Button should include:

```html
aria-label="Open navigation"
```

When open:

```html
aria-expanded="true"
```

Update state dynamically.

Close button:

```html
aria-label="Close navigation"
```

---

# 162. CUSTOM DROPDOWN ACCESSIBILITY

Trigger can use:

```text
aria-expanded
aria-haspopup
```

Update selected state.

Escape should close.

---

# 163. PERFORMANCE BUDGET MINDSET

Prefer:

```text
Fewer elements
+
Better images
+
Better animation
```

over:

```text
Many elements
+
Many effects
```

---

# 164. NO EXCESSIVE BLUR

Do not create huge blurred objects covering large areas.

Use small soft glows.

---

# 165. NO EXCESSIVE BORDER GRADIENTS

Gradient borders are an accent, not a default card treatment.

---

# 166. NO EXCESSIVE PILL UI

Pills are appropriate for:

- Tags
- Filters
- Small metadata
- Buttons

Not every card or section.

---

# 167. NO GENERIC ICON WALL

Do not create rows of 20 icons just to fill space.

Use icons when they communicate meaning.

---

# 168. NO RANDOM DECORATION

Every decorative shape should have a reason:

- Balance composition
- Guide attention
- Reinforce brand
- Add depth

Remove decorative elements that distract.

---

# 169. VISUAL STORYTELLING

The page should tell a progression:

```text
Discover
↓
Choose
↓
Learn
↓
Practice
↓
Build
↓
Grow
```

Use this principle when arranging sections.

---

# 170. CONVERSION FLOW

Primary visitor journey:

```text
Hero
↓
Trust
↓
Learning paths
↓
Benefits
↓
Projects
↓
Mentors
↓
Journey
↓
Stories
↓
Outcomes
↓
CTA
```

Do not break this flow with unrelated content.

---

# 171. CTA CONSISTENCY

Primary CTA language should be consistent.

Possible:

```text
Start Learning
Explore Courses
Enroll Now
Build Your Skills
```

Choose one primary language and reuse it.

---

# 172. BUTTON HIERARCHY

Every section should not have five competing buttons.

Use:

```text
Primary
+
Optional secondary
```

---

# 173. IMAGE OVERLAY TEXT

When placing text over images:

- Ensure contrast.
- Use gradient overlay if necessary.
- Do not place long paragraphs over busy photography.

---

# 174. IMAGE CROPS

For faces:

```text
object-position: center top;
```

may be preferable.

For environment:

```text
object-position: center;
```

Adjust according to actual image.

---

# 175. HERO MOBILE IMAGE

On mobile:

- Keep the hero image visible.
- Place it after the primary message or beside it if space allows.
- Preserve the subject.
- Avoid hiding the main visual entirely.

---

# 176. MOBILE SECTION ORDER

Do not preserve a desktop two-column structure if it harms storytelling.

Reorder content when appropriate.

---

# 177. TABLET DESIGN

Tablet should be treated as a genuine intermediate layout.

Do not allow desktop cards to become cramped.

---

# 178. CSS MEDIA QUERIES

Keep responsive rules organized near the bottom of page CSS.

Avoid scattering mobile rules throughout hundreds of selectors.

---

# 179. JAVASCRIPT COMMENTS

Comment only meaningful sections.

Good:

```javascript
// Mobile navigation
// Hero entrance timeline
// Course filter
```

Avoid comments for obvious lines.

---

# 180. NO INLINE STYLE SPRAWL

Do not generate huge amounts of inline styling.

Use CSS files.

Small dynamic styles through JS are acceptable when required.

---

# 181. INLINE SCRIPT LOCATION

If JavaScript is inside HTML:

Prefer placing it before:

```html
</body>
```

unless there is a specific reason otherwise.

---

# 182. GSAP CDN

If using CDN GSAP, load:

```text
GSAP
ScrollTrigger
```

before the animation code.

Do not load multiple versions.

---

# 183. ANIMATION INITIALIZATION

Initialize after DOM is ready.

If the script is at the end of body, direct initialization is acceptable.

---

# 184. SCROLLTRIGGER MOBILE

Check whether a complex animation is appropriate on small screens.

Disable or simplify expensive interactions where appropriate.

---

# 185. MARQUEE IMPLEMENTATION

Prefer CSS animation or GSAP.

Avoid unnecessary third-party marquee libraries.

---

# 186. IMAGE CAROUSELS

If a carousel is required:

- Implement with Vanilla JS.
- Add previous/next buttons.
- Add accessible labels.
- Support keyboard where practical.
- Avoid adding a carousel library.

---

# 187. TESTIMONIAL SLIDER

If implemented:

- Keep controls visible.
- Avoid autoplay that is too fast.
- Respect reduced motion.
- Provide accessible labels.

---

# 188. COURSE FILTERS

If filters are needed:

- Use buttons/chips.
- Update visible courses with JS.
- Provide active state.
- Make it mobile-friendly.

---

# 189. SEARCH

If a search UI is required:

- Use a real input.
- Filter content with JS.
- Show empty state.
- Do not pretend to perform server-side search.

---

# 190. BLOG FILTERS

Categories may include:

```text
All
Development
Design
Career
Leadership
Technology
```

Only include categories that match actual content.

---

# 191. FAQ

FAQ can use:

```text
Accordion
```

Requirements:

- Keyboard accessible
- `aria-expanded`
- Smooth height animation
- One-open-at-a-time optional

---

# 192. ACCORDION ANIMATION

Use:

```text
height
opacity
```

carefully.

Do not animate expensive properties unnecessarily.

---

# 193. CONTACT FORM

Suggested fields:

```text
Name
Email
Subject
Message
```

Optional:

```text
Learning interest
```

Validate.

---

# 194. FORM SUCCESS

A successful demo submission can show:

```text
Thanks — your message has been received.
```

No real backend unless explicitly requested.

---

# 195. SOCIAL LOGIN

Social login buttons are demo UI unless a real authentication integration is explicitly requested.

Do not claim successful third-party authentication.

---

# 196. ADMIN DATA

Admin dashboard data should be clearly demo data if not supplied.

Example:

```text
Demo analytics
Sample learners
```

Do not represent fabricated values as actual company data.

---

# 197. USER DATA

User dashboard can use demo/localStorage data.

Keep it simple.

---

# 198. LOGOUT STATE

After logout:

```text
localStorage.removeItem(...)
```

then:

```text
window.location.href = "../index.html";
```

---

# 199. ERROR HANDLING

JavaScript should fail gracefully.

Do not allow one missing optional element to break:

- Navigation
- Forms
- Animations
- Dashboard

---

# 200. FINAL QUALITY CHECK

Before declaring the project complete, verify:

## Structure

- All existing files remain.
- No unnecessary framework.
- No broken paths.
- No unnecessary folders.

## Home

- Exactly 10 major sections.
- Hero is strong.
- Images are meaningful.
- CTA is clear.

## Secondary pages

- About exactly 8 sections.
- Services exactly 8 sections.
- Blog exactly 8 sections.
- Contact exactly 8 sections.

## Auth

- Login works.
- Signup works.
- Role dropdown works.
- Validation works.
- Redirects work.

## Dashboards

- User and Admin are distinct.
- Responsive sidebar works.
- Logout works.

## Header

- Desktop navigation works.
- Hamburger works.
- Close works.
- Escape works.
- Body scroll lock works.

## Visual

- Color palette is consistent.
- Typography is consistent.
- Images are high quality.
- Spacing is intentional.
- No visual clutter.

## Animation

- Hero animates.
- Sections reveal.
- Staggers are smooth.
- ScrollTrigger is controlled.
- Reduced motion works.

## Responsive

Test:

```text
1440
1280
1024
768
600
480
390
320
```

No horizontal overflow.

## Accessibility

- Semantic HTML
- Labels
- Alt text
- Focus states
- Keyboard navigation
- ARIA where appropriate
- Reduced motion

## Performance

- Lazy-load below-fold images.
- Avoid unnecessary libraries.
- Animate transforms/opacity.
- Avoid excessive ScrollTriggers.
- Avoid giant images.

---

# 201. AI AGENT EXECUTION RULES

When asked to build a page:

### Step 1

Read this file.

### Step 2

Inspect the existing relevant files.

### Step 3

Preserve existing working functionality.

### Step 4

Use the current design tokens.

### Step 5

Reuse existing images/assets.

### Step 6

Build semantic HTML.

### Step 7

Build responsive CSS.

### Step 8

Add JavaScript behavior.

### Step 9

Add GSAP animation.

### Step 10

Test navigation paths.

### Step 11

Check mobile.

### Step 12

Check for console errors.

### Step 13

Check for horizontal overflow.

### Step 14

Check reduced-motion behavior.

### Step 15

Do not modify unrelated pages.

---

# 202. WHEN ASKED TO "MAKE IT PREMIUM"

Do NOT simply add:

- More gradients
- More shadows
- More blur
- More animation
- More cards

Instead improve:

```text
Typography
Spacing
Composition
Imagery
Hierarchy
Interaction
Motion
Consistency
```

---

# 203. WHEN ASKED TO "MAKE IT MORE ANIMATED"

Do NOT animate every element.

Instead add:

1. Better hero choreography.
2. Scroll-based reveals.
3. Image masks.
4. Staggered cards.
5. One meaningful pinned story.
6. Subtle floating elements.
7. Counters where valid.
8. Marquee where useful.
9. Hover interactions.

---

# 204. WHEN ASKED TO "MAKE IT IMAGE-RICH"

Prioritize:

```text
Hero image
Course images
Project screenshots
Mentor portraits
Student stories
Learning visuals
Career imagery
CTA collage
```

Do not just add decorative stock photos.

---

# 205. WHEN ASKED TO "MAKE IT MODERN"

Use:

- Strong typography
- Asymmetric grids
- Bento layouts
- Editorial composition
- Soft gradients
- Glass accents
- Image masks
- Product-style UI
- Controlled motion
- Generous whitespace

Avoid:

- Generic Bootstrap-like grids
- Heavy borders
- Tiny text
- Dense layouts
- Excessive gradients

---

# 206. WHEN ASKED TO CHANGE COLORS

Use the existing palette first.

Do not introduce a completely different color system unless explicitly instructed.

---

# 207. WHEN ASKED TO CHANGE LAYOUT

Preserve:

- Content hierarchy
- Responsive behavior
- Navigation
- Accessibility
- Brand language

Do not destroy working functionality simply to achieve a visual change.

---

# 208. WHEN ASKED TO ADD A NEW PAGE

First determine:

1. Where the page belongs.
2. Which CSS file it should use.
3. How navigation paths should work.
4. Which shared header/footer pattern it should use.
5. Which page section count applies.

Do not create a random new architecture.

---

# 209. WHEN ASKED TO MODIFY EXISTING PAGE

Do not rewrite the whole project.

Modify only:

```text
Relevant HTML
+
Relevant CSS
+
Relevant inline JS
```

unless the requested feature genuinely requires more.

---

# 210. FINAL DESIGN STANDARD

The finished website should look like a real premium product.

The desired feeling:

```text
Modern education
+
Technology
+
Career growth
+
Human mentorship
+
Real projects
+
Premium visual design
```

The user should immediately understand:

> **This platform helps me learn practical skills, build real projects, and move toward a stronger career.**

---

# 211. NON-NEGOTIABLE RULES

Always:

- Use the current folder structure.
- Use Vanilla HTML/CSS/JS.
- Use GSAP/ScrollTrigger for advanced animation.
- Use the existing logo.
- Use the existing color palette.
- Make the website responsive.
- Make the website image-rich.
- Make the website animation-rich but controlled.
- Preserve accessibility.
- Respect reduced motion.
- Avoid fabricated claims.
- Avoid broken paths.
- Avoid horizontal overflow.
- Keep JavaScript inside the corresponding HTML pages.
- Keep page-specific CSS in `css/`.
- Keep global styles in `global.css`.
- Keep Home styles in `index.css`.

Never:

- Introduce React.
- Introduce Tailwind.
- Introduce a build system.
- Move the current HTML structure.
- Replace the logo.
- Invent partnerships.
- Invent testimonials.
- Invent business statistics.
- Add random dependencies.
- Sacrifice usability for animation.

---

# 212. BUILD PHILOSOPHY

Build the site as if it were being prepared for a serious public launch.

Prioritize:

```text
1. Clarity
2. Visual hierarchy
3. Content
4. Imagery
5. Responsive layout
6. Interaction
7. Animation
8. Performance
9. Accessibility
```

Do not reverse this order.

The final implementation should be visually ambitious while remaining maintainable, responsive, accessible, and fast.
