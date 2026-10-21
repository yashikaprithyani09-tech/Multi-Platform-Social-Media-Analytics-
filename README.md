# Multi-Platform-Social-Media-Analytics-
## Project Overview

* **Intern ID:** `CITS9397’
* **Author:** [Yashika Prithyani]
* **Domain:** Data Analytics
* **Tool Used:** Microsoft Power BI Desktop
* **Target Platforms:** Instagram, TikTok, YouTube

Multi-Platform Social Media Analytics Dashboard in Power BI analyzing Instagram, TikTok, and YouTube performance metrics, optimal posting windows, engagement drivers, and content conversion funnel.

This report transforms raw multi-channel social media metrics into actionable intelligence—evaluating audience growth, content retention, optimal posting windows, emotional engagement drivers, and CTA conversion efficiency.

##  Strategic Key Performance Indicators (KPIs)

* **Top-Funnel Growth & Reach:** Aggregate tracking of total followers, total reach, impression scale, and likes across platforms.
* **Optimal Posting Windows:** Matrix breakdown analyzing impression density across time frames (*Morning, Afternoon, Evening, Night*) to identify peak performance hours.
* **Hook Strength vs. Retention:** Visualizing early viewer retention to refine video intro strategies.
* **Psychological Drivers:** Categorizing engagement performance based on emotional audience triggers (*Curiosity, Inspiration, Urgency, etc.*).
* **CTA Conversion Analysis:** Evaluating conversion rate variance between CTA vs. non-CTA content posts.

---

## 🛠️ Data Pipeline & ETL Steps (Power Query)

1. **Data Import & Cleaning:** Imported raw multi-platform social media dataset and formatted date values to `Date` and numeric metrics to `Whole Number`.
2. **Missing Value Handling:** Replaced `null` or missing entries in numeric metrics with `0` to prevent computation errors in aggregate DAX formulas.
3. **Text Normalization:** Standardized casing and stripped trailing whitespaces across categorical columns like `Platform` (*Instagram, TikTok, YouTube*) and `Posting Window`.

---

## 📐 Core DAX Measures & Dynamic Formatting

### Dynamic Platform Color Assignment
Dynamic conditional formatting measure applied to display platform-specific brand hex colors across visual values:

```dax
Platform Font Color = 
SWITCH(
    SELECTEDVALUE('Fact_SocialMedia'[Platform]),
    "Instagram", "#FF00A0",
    "TikTok", "#25F4EE",
    "YouTube", "#FF0000",
    "#FFFFFF")

