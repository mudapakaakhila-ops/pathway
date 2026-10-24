# Pathway After 10 (పదవ తరగతి తర్వాత మార్గం)

> **Tagline:** *Explore your interests. Discover what comes next.*  
> **Student Guidance Initiative • India**

---

## 1. Project Overview

**Pathway After 10** is an interactive, presentation-ready educational discovery platform designed to help Class 10 students across India make thoughtful, stress-free decisions about what to study next.

### Key Objectives & Tone:
- **Broaden Horizons Beyond Just 2 Streams:** Demystifies the full spectrum of post-10th education in India, including **Intermediate (+2)** (MPC, BiPC, CEC, MEC, Arts/Humanities, Vocational), **3-Year Polytechnic Engineering Diplomas**, **Industrial Training Institutes (ITI / Skilled Trades)**, and recognized routes like **RGUKT 6-Year Integrated B.Tech**, **Agricultural Diplomas**, **Paramedical Diplomas**, and **Open Schooling (NIOS/TOSS)**.
- **Empathetic & Non-Judgmental:** Academic marks are treated as an optional factor. Every route—especially vocational and hands-on craftsmanship—is presented with dignity and clear long-term pathways.
- **Guidance, Not Admission or Salary Guarantees:** Emphasizes that this is a guidance portal. No false promises of guaranteed seats, government jobs, or specific salaries are ever made.
- **Complete Client-Side Privacy:** All questionnaire answers and marked roadmap steps are stored exclusively in the student's browser (`localStorage`). No server tracking, no ads, no registration required.
- **Bilingual Accessibility:** Full English and Telugu (తెలుగు) language toggle with authentic regional terminology and typography.

---

## 2. Main Student Journey

The platform provides a continuous, demonstration-ready flow:

$$\text{Home} \longrightarrow \text{Student Questions} \longrightarrow \text{Recommendations} \longrightarrow \text{Path Details} \longrightarrow \text{Compare Paths} \longrightarrow \text{Personal Roadmap} \longrightarrow \text{Next Actions}$$

1. **Home:** Introduces the dilemma faced by 15-year-old Class 10 students, explains the guidance approach, and offers 1-click **Presentation Demo Personas**.
2. **Student Discovery Quiz:** 8 short, optional questions covering:
   - State of study (Telangana, Andhra Pradesh, or All-India)
   - Academic comfort / marks (optional with 1-click skip)
   - Favorite subjects and activities
   - Preferred daily work/learning style (Practical, Computer-based, People-focused, Academic, Creative)
   - Annual study budget
   - Travel vs. Hostel preference
   - Career timeline (Start earning in 1-3 yrs vs. Balanced 3-4 yrs vs. Long-term 5+ yrs)
   - Appetite for competitive entrance examinations
3. **Tailored Recommendations:** Dynamically scores and presents 3 to 4 high-alignment pathways explaining:
   - Why it may suit the student's specific profile
   - What to consider before choosing
   - Typical duration and estimated cost ranges (Govt vs. Private)
   - Possible next courses and career directions
   - A sensible alternative route
   - 3 actionable next steps
4. **Step-by-Step Interactive Roadmap:** Vertical timeline node tree breaking down Class 10 → Admissions → Coursework → Intermediate/Lateral milestones → Degree/Job. Each step expands with admission procedures and local verification requirements, allowing students to mark steps as **Interested (★)**, **Need to Research (🔍)**, or **Completed (✓)**.
5. **Side-by-Side Comparison Matrix:** Compare up to 3 pathways simultaneously on duration, entry criteria, fee ranges, entrance exams, further study routes, career directions, and time to first job.
6. **College & Course Explorer:** Searchable, filterable directory by State, District, Course Category, and Budget with institution detail modals and official verification hints.
7. **Sources & Verification:** Official government portals (TS BIE, BIEAP, SBTET, AICTE, NCVT, NIOS, etc.), a 5-step checklist for parents and students, realistic salary guidance principles, and an educational acronyms glossary.
8. **About & Presentation Guide:** Detailed problem statement, architectural specs, ethical guidelines, and a classroom presentation script for teachers.

---

## 3. Technology Stack

- **Structure:** Semantic HTML5 with accessibility ARIA tags and SEO metadata.
- **Styling:** Modern Vanilla CSS3 design system featuring:
  - Frosted glassmorphism navigation and cards (`backdrop-filter`)
  - Curated dark slate & emerald/teal color scheme (`#0a0f1d`, `#0d9488`, `#6366f1`, `#f59e0b`)
  - Fluid typography with Google Fonts (`Outfit`, `Inter`, `Noto Sans Telugu`)
  - Smooth micro-interactions, responsive grid systems, and animated vertical timeline nodes
- **Logic:** Native ES6+ JavaScript modules (`app.js`, `storage.js`, `recommender.js`, data modules).
- **Zero External Dependencies / Zero Build Step:** Runs immediately without requiring Node.js, Webpack, or npm packages.

---

## 4. How to Run Locally

### Option A: Using the Included PowerShell Server (Recommended for Windows)

A lightweight static server script `serve.ps1` using native `.NET HttpListener` is included in the project root:

1. Open PowerShell in the project directory:
   ```powershell
   powershell -ExecutionPolicy Bypass -File .\serve.ps1 -Port 8080
   ```
2. Open your web browser and navigate to:
   ```
   http://127.0.0.1:8080/
   ```

### Option B: Using Python (if installed)
```bash
python -m http.server 8080
```
Then visit `http://127.0.0.1:8080/`.

### Option C: Using Node.js / npx (if installed)
```bash
npx serve .
```

---

## 5. Presentation Demo Personas (1-Click Walkthrough)

To present this website to teachers or evaluators without entering 8 questionnaire answers manually, click any of the **Demo Persona** cards on the Home page:

- **Persona 1: Ananya (Tech & Long-term Degree)**
  - *Profile:* High academic comfort, loves math & coding, interested in entrance exams and 4-5 year degrees.
  - *Outcome:* Recommends **Intermediate MPC** and **Polytechnic CME**, leading to B.Tech and software engineering.
- **Persona 2: Kiran (Hands-on & Early Earning)**
  - *Profile:* Hands-on workshop orientation, budget-conscious, desires to start earning in 1-3 years.
  - *Outcome:* Recommends **Polytechnic Diploma in Engineering** and **ITI Skilled Trades (Electrician/Fitter)** with apprenticeships.
- **Persona 3: Bhavana (Business & Governance)**
  - *Profile:* Interested in commerce, business, public administration, and law; prefers a balanced 3-year timeline.
  - *Outcome:* Recommends **Intermediate CEC**, **Intermediate MEC**, and **Humanities / Law**.

---

## 6. Information Quality & Sample Data Notice

### What Data is Sample / Illustrative:
- **College Directory (`js/data/colleges.js`):** The institutions listed (such as *Government Polytechnic Masab Tank*, *Andhra Polytechnic Kakinada*, *Govt Junior College Nampally*, etc.) represent realistic regional examples. However, their exact fee bands, intake capacities, and hostel fees are illustrative sample data for student discovery.
- **Salary Guidance:** Any salary references are framed as broad directional estimates based on published reports. The portal explicitly informs students that earnings depend on location, employer, skills, and market conditions.

### How to Replace Sample Data with Verified Official Information:
All college and course data is kept in a clean, structured JSON-compatible ES module at `js/data/colleges.js`:
```javascript
{
  id: "col_01",
  name: "Government Polytechnic Masab Tank",
  category: "Polytechnic / Diploma",
  type: "Government",
  state: "Telangana",
  district: "Hyderabad",
  coursesOffered: [...],
  admissionMode: "State PolyCET Counselling",
  tuitionFeeBand: "₹3,800 - ₹5,000 / year",
  affiliatingBody: "SBTET Telangana & AICTE Approved",
  verificationUrlHint: "sbtet.telangana.gov.in"
}
```
To update or verify data:
1. Consult current admission brochures published by state boards (e.g., TS BIE, BIEAP, SBTET).
2. Edit or append verified institution records directly in `js/data/colleges.js`.
3. For new states or districts, add values to `STATES_LIST` and `DISTRICTS_LIST` in `colleges.js`.

---

## 7. How to Deploy to a Hosting Service

Since **Pathway After 10** uses vanilla web standards, it can be hosted on any static hosting provider for free in minutes:

### Deploy to GitHub Pages:
1. Push this repository to GitHub.
2. In your GitHub repository, navigate to **Settings** → **Pages**.
3. Under **Branch**, select `main` (or `master`) and folder `/ (root)`.
4. Click **Save**. Your site will be live at `https://<username>.github.io/<repo-name>/`.

### Deploy to Netlify:
1. Drag and drop the project folder directly onto [app.netlify.com/drop](https://app.netlify.com/drop), or connect your GitHub repository.
2. Set publish directory to `.`. No build command is needed.

### Deploy to Vercel:
1. Install Vercel CLI (`npm i -g vercel`) or import the Git repository on [vercel.com](https://vercel.com).
2. Choose "Other" framework preset and deploy.

---

## 8. Privacy & Ethics Statement

- **Zero Server Tracking:** No telemetry, cookies, or tracking scripts.
- **Local Storage Only:** Answers are stored in browser `localStorage` and can be completely wiped with one click using the **Reset Data** button in the header.
- **Equal Dignity for All Vocations:** ITI trades, polytechnic diplomas, open schooling, and humanities are presented with the same respect as conventional engineering and medical streams.
