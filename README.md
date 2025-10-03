# USCC Hearings Dataset & Scraper

This project collects, cleans, and structures data from the **U.S.–China Economic and Security Review Commission (USCC)** hearings. These hearings feature testimony from policymakers, academics, and experts, and provide key insights into the economic, political, and security dimensions of U.S.–China relations.

The dataset created here supports downstream research and visualization, forming part of a broader effort to map China’s global engagements (see also: *China Diplomatic Visits Dashboard*).

---

## 📌 Objective

* Build a **structured dataset** of USCC hearings and speakers.
* Extract **hearing-level metadata**: date, title, URL, transcript link.
* Extract **speaker-level details**: name, affiliation, profile URL.
* Produce **two CSVs** for analysis and dashboarding.

---

## 📂 Repository Structure

```
.
├─ code/
│  └─ USCCCHearingsDataScraping.ipynb                 # Final Jupyter Notebook scraper
│
├─ output/
│  ├─ uscc_master_hearings.csv    # Hearing-level dataset
│  └─ uscc_master_speakers.csv    # Speaker-level dataset
│
└─ README.md                      # Project documentation
```

---

## 🛠️ Methodology

* **Archive pagination**: Crawl `https://www.uscc.gov/hearings?type=hearing&page=N`.
* **Hearing pages**: Extract hearing date, title, transcript URL.
* **Speakers**: Collect speaker names, affiliations, and profile links.
* **Output**: Save standardized CSVs for reproducibility.

---

## 📊 Output

* **Master Hearings CSV** → 1 row per hearing
* **Speakers CSV** → 1 row per speaker per hearing

These datasets can be used for analysis in Python, R, Tableau, or Power BI.

---



## 🔧 Technologies Used

* Python (Requests, BeautifulSoup, Pandas)
* Jupyter Notebooks
* CSV

---

