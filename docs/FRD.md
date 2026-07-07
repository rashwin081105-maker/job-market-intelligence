# Functional Requirements Document (FRD)

## 1. Data Sources
- Indeed job search (via API/connector), filtered to Chennai, Tamil Nadu
- Fields per job: title, company, location, posted date, job type, description (full text), URL

## 2. Data Collection Requirements
- Search across 4 role-title variations: Data Analyst, Business Analyst, BI Analyst, Junior Data Analyst
- Deduplicate by job ID
- Target: 150-300 unique postings

## 3. Processing Requirements
- Clean description text (strip formatting artifacts)
- Extract skills/tools via keyword matching (SQL, Excel, Power BI, Python, Tableau, Google Data Studio, R, Advanced Excel, etc.)
- Extract experience level via pattern matching (e.g., "0-2 years", "fresher", "3+ years")
- Tag each posting with role category

## 4. Storage Requirements
- SQL schema:
  - `jobs` table: id, title, company, location, posted_date, role_category, experience_level, url
  - `job_skills` table: job_id, skill_name

## 5. Analysis Requirements
- Top N skills by frequency (overall and by role category)
- Experience-level distribution
- Top hiring companies by posting count
- Skill co-occurrence (which tools appear together)

## 6. Dashboard Requirements
- Filterable by role category
- Visuals: skill frequency bar chart, experience-level breakdown, top companies table, skill co-occurrence view
- Tool: Google Data Studio

## 7. Documentation Requirements
- GitHub README with problem statement, approach, tech stack, screenshots
- BRD/FRD included in `/docs`
