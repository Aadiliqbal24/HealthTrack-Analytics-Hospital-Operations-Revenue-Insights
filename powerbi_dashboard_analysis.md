# Power BI Dashboard — Hospital Performance Overview: Analysis & Insights

Business questions and analysis mapped exactly to this dashboard.

---

### 1. KPI Cards — Total Revenue, Total Appointment, Avg Treatment Cost, No Show Rate

**Business Questions:**
- How much total revenue has the hospital generated, and how many appointments does that represent?
- Is the average treatment cost reasonable relative to typical hospital billing?
- Is the no-show rate high enough to be an operational concern?

**Analysis:**
₹37M in total revenue across 5,000 appointments works out to roughly
₹7,400 per appointment on average — close to the ₹6.81K "Average Treatment
Cost" KPI shown, so the two numbers line up well as a sanity check. The
**7.80% No Show Rate** is the number worth flagging first: at this volume,
that's roughly 390 missed appointments — each one representing lost
doctor time and lost potential revenue. This is the single biggest
efficiency lever on this dashboard.

---

### 2. Revenue by Department (Bar Chart)

**Business Questions:**
- Which departments generate the most revenue?
- Is revenue concentrated in a few departments, or spread evenly?
- Should low-revenue departments (Cardiology, Dermatology) be reviewed for staffing or demand issues?

**Analysis:**
Gynecology and General Medicine lead clearly, with a steady decline through
ENT, Neurology, Pediatrics, Orthopedics, down to Cardiology and Dermatology
at the bottom. Unlike a sharp 80/20 drop-off, this is a **gradual decline**
— suggesting fairly even distribution of patient demand across departments,
rather than one or two departments dominating. Cardiology and Dermatology
being lowest is worth a follow-up: is that lower patient demand, fewer
doctors assigned to those departments, or lower per-visit billing?

---

### 3. Appointment Status (Donut Chart)

**Business Questions:**
- What share of scheduled appointments are actually completed?
- How much revenue is being lost to cancellations and no-shows combined?

**Analysis:**
80.14% Completed, 12.06% Cancelled, 7.8% No-show. Combined, **nearly 1 in
5 appointments (19.86%) never result in a completed visit** — that's a
significant chunk of scheduled doctor time not converting into revenue.
This directly supports investing in better appointment reminders or a
waitlist system to fill cancelled slots.

---

### 4. Monthly Revenue (Line Chart)

**Business Questions:**
- Is hospital revenue growing, shrinking, or seasonal?
- Which months see revenue spikes or dips, and why?

**Analysis:**
Revenue is volatile rather than steadily trending — a sharp dip in
February, a strong peak in May (₹4.3M), another dip around September, and
a smaller recovery toward December. This pattern suggests **seasonal or
event-driven demand** (e.g. flu season, monsoon-related illnesses, festival
periods affecting elective procedures) rather than steady organic growth.
Worth overlaying against known seasonal health trends to explain the May
peak specifically.

---

### 5. Doctor Performance Table (Total Revenue, Appointments, Avg Treatment Cost, No Show Rate)

**Business Questions:**
- Which doctors generate the most revenue, and is that from high volume or high treatment cost per visit?
- Which doctors have unusually high no-show rates, and could that indicate a scheduling or communication issue?
- Should top performers (Dr. Sanjay Nair, Dr. Sowmya Nair) be studied for best practices to share across the department?

**Analysis:**
Dr. Sanjay Nair leads on both revenue (₹30.23L) and appointment volume
(260) with a mid-range treatment cost (₹11,223) — a volume-driven top
performer. In contrast, Dr. Sowmya Nair earns nearly as much (₹27.58L)
from fewer appointments (238) but the highest treatment cost in the top
list (₹10,793) — a value-driven performer. **No-show rate varies
noticeably by doctor** (from 4.86% for Dr. Ganesh Gupta up to 10.33% for
Dr. Vikram Nair) — this is worth investigating per-doctor rather than
only at the hospital level, since it may point to specific scheduling
slots or communication gaps for individual doctors.

---

## Overall Executive Takeaway

1. **No-show + cancellation = ~20% of scheduled appointments** — the
   single biggest operational improvement opportunity.
2. **Revenue is fairly evenly spread across departments** — no major red
   flag, but Cardiology/Dermatology are worth a demand review.
3. **Doctor performance has two distinct patterns** — volume-driven vs
   value-driven — useful for coaching and resource allocation decisions.
