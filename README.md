# UnitedNationsSecurityCouncil-InformationScrapingAnalysis
Scrapes and structures data from USCC hearings, capturing hearing dates, titles, transcripts, and speaker details. Produces clean, reproducible datasets for analysis and dashboards, supporting research on U.S.–China policy, strategy, and diplomacy.



### Project Description

This project builds a structured dataset of hearings organized by the **U.S.–China Economic and Security Review Commission (USCC)**, a U.S. government body that monitors and reports on the national security implications of the U.S.–China relationship. The hearings, which bring together policymakers, academics, and experts, provide valuable insights into economic, strategic, and diplomatic developments involving China.

The goal of this project is to scrape, clean, and standardize hearing information into a format that is useful for data analysis and visualization. Using **Python (Requests, BeautifulSoup, Pandas)**, the pipeline collects hearing metadata such as the date, title, URL, and transcript link, along with detailed information on each speaker, including their name, organization, and profile link if available. The result is two reproducible datasets:

* A **master hearings dataset** (one row per hearing), containing structured metadata.
* A **speakers dataset** (one row per speaker per hearing), capturing the individuals and institutions shaping discourse on China.

All code is implemented in a single Jupyter Notebook (`Take2.ipynb`), making the workflow transparent and easy to reproduce. The pipeline iterates through the USCC hearings archive, visits each hearing page, extracts structured information, and writes the results to **CSV files** with standardized naming (`YYYYMMDD_uscc_master_hearings.csv` and `YYYYMMDD_uscc_people_hearings.csv`).

This work builds on previous efforts in the **China Diplomatic Visits Dashboard**, which focused on international visits by Chinese leaders. Together, these projects form part of a broader initiative—**Mapping Global China**—to create transparent, accessible datasets that allow researchers, policymakers, and the public to better understand China’s global engagements.

The datasets created here are intended to support downstream analysis, whether through Tableau dashboards, Python-based visualizations, or integration with larger research pipelines. Future work may extend the project by applying natural language processing (NLP) techniques to classify hearing topics (economic, military, technology, etc.), building interactive dashboards of hearing frequency and speaker networks, and linking USCC data to other open-source datasets on China.


