# Google Form Randomization Spammer

> A Tampermonkey userscript that automates filling out a Google Form by randomly selecting available non-text options and repeatedly submitting responses.

---

## ⚙️ Purpose
This tool programmatically simulates responses on a Google Form by:
- Parsing each question on the form,
- Identifying non-text answer options (radio buttons, checkboxes, dropdowns),
- Randomly choosing one option for each question (skipping free-text fields),
- Submitting the form and optionally repeating the process.

**Intended use:** testing, development, and load-simulation on forms you own or have explicit permission to test.

---

## 🧩 Features
- Detects questions and available selectable options automatically.  
- Skips questions that require typing (text inputs).  
- Looping/repeat behavior to submit many responses.  
- Implemented as a Tampermonkey userscript (pure JavaScript).  
- Simple configuration for submission count and timing.

---

## 🚀 Getting Started

### Prerequisites
- A browser with [Tampermonkey](https://www.tampermonkey.net/) or another userscript manager installed.  
- Access to the Google Form you intend to test (you must own it or have permission).  
- Basic ability to edit the userscript to adjust the `@match` pattern or tweak selectors.

### Installation
1. Clone this repository or download the userscript file.  
2. Open Tampermonkey and create a new script.  
3. Paste the userscript code from this repo into the new Tampermonkey script.  
4. Update the script header `@match` or `@include` line to target your Google Form URL.  
5. Save and enable the script.  
6. Open the target Google Form. The script will attempt to auto-select answers and submit responses.

### Configuration
Inside the script you can:
- Set the number of submissions or run indefinitely.  
- Add delays between selections and submissions to appear more human-like.  
- Adjust selectors or logic for forms with custom layouts or unusual question types.

---

## 📝 Code Overview
- `main.js` (or the primary userscript file):  
  - Scans the form DOM to locate question blocks.  
  - Detects selectable options for each question (radio, checkbox, dropdown).  
  - Randomly picks an option per question and triggers submission.  
  - Ignores text-only questions to avoid typing arbitrary text.  
  - Contains loop/delay logic for repeated submissions.

---

## ⚠️ Important Considerations & Ethics
- Use this script **only** on forms you own or where you have explicit authorization.  
- Automated submissions can violate Google’s Terms of Service and may trigger rate limits, CAPTCHA, or account restrictions.  
- Excessive automated traffic may impact the target service or other users. Adjust delays and volume responsibly.  
- This project is provided for testing and educational purposes; misuse is discouraged and may have legal or contractual consequences.

---

## 🛠 Troubleshooting
- If the script fails to find options, inspect the form DOM — Google occasionally changes markup. Update selectors accordingly.  
- If submissions stop working, Google may have added anti-automation measures (CAPTCHAs, rate limits). The script cannot bypass those protections.  
- Ensure Tampermonkey is enabled and the `@match` pattern matches your form URL.

---

## Contributing
Contributions (bug fixes, selector improvements, or documentation enhancements) are welcome. Please open an issue describing the change before submitting a PR.

---

## License
Choose and add a license (e.g., MIT) — or state otherwise. Example: `MIT License` (replace this line with your chosen license file).

---

## Disclaimer

This software is intended for legitimate testing, development, and educational use only. The author **expressly disclaims** any and all liability for damages, claims, losses, or expenses arising from the misuse of this project, including but not limited to automated misuse, abusive submissions, or actions by bad actors. By using this repository you agree that you are responsible for how you use the code and for obtaining any necessary permissions before interacting with third-party forms, services, or systems.

This project is provided **without warranty** of any kind. If you plan to use this code in any environment where legal, ethical, or contractual issues may arise, seek advice from qualified legal counsel.
