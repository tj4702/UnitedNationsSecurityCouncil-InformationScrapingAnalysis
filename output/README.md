# Exploring the USCC Hearings Datasets

As part of my project on **scraping and structuring data from the U.S.–China Economic and Security Review Commission (USCC)** hearings, I generated two key outputs:

* `uscc_master_hearings.csv`
* `uscc_master_speakers.csv`

Together, they provide a structured window into how the United States publicly documents and debates its evolving relationship with China. Let’s break down what each dataset contains, how it was built, and why it matters.

---

## 📂 1. Master Hearings Dataset (`uscc_master_hearings.csv`)

This file captures **one row per hearing**. Think of it as the “index” of all hearings in the USCC archive.

### Columns:

* **date** → Standardized as `YYYY-MM-DD`, making it easy to sort and filter by year, month, or even analyze seasonal trends in hearings.
* **title** → The official title of the hearing (e.g., *“An Axis of Autocracy? China’s Relations with Russia, Iran, and North Korea”*). Titles are rich signals of what topics were prioritized in U.S. policy discussions at the time.
* **url** → The link to the hearing’s landing page. This acts as your gateway to full context (agendas, background documents).
* **transcript_url** → Direct PDF link to the hearing transcript. This makes it possible to run **NLP pipelines** (topic modeling, keyword extraction, sentiment analysis) without manually hunting for files.

### Why it matters:

This dataset gives you the **timeline of hearings**, allowing for trend analysis:

* How often hearings are held.
* Shifts in thematic focus (e.g., economics in one period, tech security in another).
* Easy cross-linking with external world events (trade wars, Taiwan tensions, etc.).

---

## 📂 2. Master Speakers Dataset (`uscc_master_speakers.csv`)

While the hearings dataset tells you **when** and **what**, this file tells you **who** is shaping the conversation.

### Columns:

* **hearing_date** & **hearing_title** → These keys link each speaker back to their hearing in the master dataset.
* **speaker_name** → Cleaned speaker names (standardized to remove artifacts like “Panel%203”).
* **speaker_organization** → Affiliation, which is crucial for mapping **institutional influence** (e.g., think tanks, government agencies, academia).
* **speaker_profile_url** → Links to individual bios when available, useful for deeper profiling.

### Why it matters:

This dataset allows for **network analysis of voices in U.S.–China debates**:

* Which experts are called most frequently.
* Which think tanks, agencies, or universities dominate testimony.
* How representation changes over time (e.g., more tech-sector voices in later years).

---

## 🧩 Putting It All Together

The beauty of these two datasets is that they complement each other:

* `uscc_master_hearings.csv` gives the **macro picture** (timeline + topics).
* `uscc_master_speakers.csv` gives the **micro picture** (who spoke, from where, when).

Together, they form the foundation for:

* **Tableau / Power BI Dashboards** → frequency of hearings, speaker affiliation breakdowns.
* **NLP Research** → topic modeling of transcripts.
* **Network Graphs** → mapping institutional ecosystems in U.S.–China policy debates.

---

This is more than just scraping — it’s about transforming **static government web pages** into a **living dataset** that opens new avenues for research, visualization, and policy insight.


