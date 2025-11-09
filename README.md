Bhoomi-RTC is an open-source [API Wrapper / Utility Library / Educational Tool] designed to simplify the process of accessing, validating, and understanding the digital land records (RTC/Pahani) of Karnataka, India.Our goal is to leverage the publicly available information and structure of the Bhoomi system to aid researchers, developers, and citizens in making sense of this critical data.✨ Key FeaturesData Structure Mapping: Clear models and documentation for the various components of an RTC (Survey No., Hissa No., Owner Name, Khata, etc.).Validation Utilities: Functions to validate inputs (e.g., check if a Taluk ID is valid for a given District).[Specific Tool]: A utility to [e.g., parse a downloaded RTC PDF/HTML extract] into a machine-readable JSON format.Documentation Focus: Comprehensive guides on navigating the official landrecords.karnataka.gov.in portal steps (Viewing RTC, Mutation Status, etc.).🚀 Getting StartedThis guide assumes you are familiar with the basic concepts of the Bhoomi portal and Karnataka land record terminology.PrerequisitesPython 3.8+ (or specify your main language)[Any key non-standard library, e.g., requests, pandas, BeautifulSoup]InstallationClone the Repository:Bashgit clone https://github.com/YourUsername/Bhoomi-RTC.git
cd Bhoomi-RTC
Install Dependencies:Bashpip install -r requirements.txt
Run Example:Bash# Example: Running the land details parser script
python examples/parse_rtc_data.py --survey_no 123/A/1
💡 Usage Example: Parsing an RTC ExtractUse the core RtcParser class to structure the details you extract from the Bhoomi portal.Pythonfrom bhoomi_rtc.parser import RtcParser

# Assume 'raw_html_content' is the content copied from the official RTC view page
with open("downloaded_rtc_view.html", "r") as f:
    raw_html_content = f.read()

parser = RtcParser(raw_html_content)
rtc_data = parser.get_structured_data()

print(f"Village: {rtc_data['village_name']}")
print(f"Owner Count: {len(rtc_data['owner_details'])}")
print(f"Current Crops: {rtc_data['crop_details']['current_year']}")

# Output the full structured data
import json
print(json.dumps(rtc_data, indent=2))
⚠️ Disclaimer: This project is a third-party utility and is NOT affiliated with the Government of Karnataka. The official source for all legal land records is the Karnataka Bhoomi Portal.📜 Bhoomi RTC TerminologyTermFull FormPurposeRTCRecord of Rights, Tenancy, and CropsThe primary land ownership document (Pahani).Pahani(Local Name for RTC)Proof of ownership, crop details, and liabilities.MRMutation RegisterDocument recording every change of land ownership.SurnocSub-Division No.A number that further divides a Survey Number.HissaPart/FractionA sub-section of a Surnoc (e.g., 123/A/1).🤝 ContributionWe welcome contributions! If you have optimized methods for data handling or new utility functions related to Karnataka's land records, please submit a Pull Request.Fork this repository.Commit your changes (git commit -m 'feat: Add new RTC parsing logic').Open a Pull Request against the main branch.Code of Conduct | Contributing Guidelines✉️ Contact & SupportFor issues, questions, or general discussion, please use the GitHub Issues tab.Project Maintainer: [Your GitHub Handle]Project Link: [https://github.com/YourUsername/Bhoomi-RTC]
