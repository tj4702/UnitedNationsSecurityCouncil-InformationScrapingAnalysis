# USCC Hearings Scraping Code

This folder contains the notebook **`USCCCHearingsDataScraping.ipynb`**, which automates the collection and cleaning of data from the **U.S.–China Economic and Security Review Commission (USCC)** hearings archive. The goal is to transform unstructured web pages into clean, analyzable datasets of hearings and speakers.

---

## 📌 What the Code Does

The notebook builds a pipeline that:

1. **Navigates through the USCC hearings archive** (`https://www.uscc.gov/hearings?type=hearing&page=N`).
2. **Extracts hearing-level metadata**, including:

   * Date of hearing (standardized to `YYYY-MM-DD`).
   * Title of the hearing.
   * URL of the hearing page.
   * Transcript PDF link (if available).
3. **Parses each hearing’s page for speaker information**, capturing:

   * Speaker name (cleaned and standardized).
   * Affiliation / organization.
   * Profile link (if available).
4. **Cleans and organizes the data** into structured tables.
5. **Exports the results** into two reproducible CSVs:

   * `uscc_master_hearings.csv` → one row per hearing.
   * `uscc_master_speakers.csv` → one row per speaker per hearing.

---

## 🔧 Dependencies Used and Why

* **requests**

  * To send HTTP requests and fetch the raw HTML of USCC pages.
  * Reliable for handling pagination across multiple archive pages.

* **BeautifulSoup (bs4)**

  * To parse the HTML pages and extract structured information (titles, dates, speaker lists, links).
  * Used because USCC’s site is static and doesn’t require heavy tools like Selenium.

* **pandas**

  * To organize scraped data into DataFrames.
  * Provides easy cleaning, standardization, and CSV export.

* **time**

  * Used for pauses between requests (polite scraping, reducing server strain).

These libraries were chosen for simplicity, reliability, and transparency — ensuring the pipeline remains lightweight but powerful.

---

## 📊 What Data is Scraped

1. **Hearing-Level Data (Master Hearings CSV)**

   * `date` → standardized to `YYYY-MM-DD`.
   * `title` → hearing name as published.
   * `url` → direct hearing page link.
   * `transcript_url` → link to the official transcript PDF.

2. **Speaker-Level Data (Speakers CSV)**

   * `hearing_date` → date of hearing (to join with master).
   * `hearing_title` → hearing title (to join with master).
   * `speaker_name` → cleaned name of each participant.
   * `speaker_organization` → affiliation / institution.
   * `speaker_profile_url` → direct link to speaker bio, if provided.

---

## 📈 How This Data Helps

* **Research Transparency**: Turns scattered hearing pages into structured datasets for analysis.
* **Policy Analysis**: Lets you track themes of USCC hearings over time (e.g., tech security, trade, military).
* **Network Mapping**: The speaker dataset allows analysis of who testifies most often, their affiliations, and institutional networks.
* **Integration with Other Projects**: Can be combined with the *China Diplomatic Visits Dashboard* to create a broader “Mapping Global China” dataset linking U.S. monitoring with Chinese foreign engagements.
* **Visualization**: Ready for dashboards in Tableau, Power BI, or Python (e.g., frequency plots, speaker networks, geographic focus).

---

## 🚀 Running the Code

1. Open `USCCCHearingsDataScraping.ipynb` in Jupyter Notebook/Lab.
2. Install dependencies:

   ```bash
   pip install requests beautifulsoup4 pandas
   ```
3. Run all cells in order.
4. Clean CSV outputs will be generated in the `output/` folder.
