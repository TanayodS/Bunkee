<h1 align="center">Tanayod Suthimathakorn</h1>
# Thailand Top 50 Companies Scraper

A Python project to scrape the top 50 companies in Thailand from [WorkVenture](https://top50.workventure.com/) and export the data to CSV or Excel format.

## 🎯 Features

- **Web Scraping**: Automatically fetches company data from https://top50.workventure.com/
- **Data Extraction**: Extracts company name, rank, description, website link, and logo
- **Multiple Export Formats**: Support for CSV and Excel (XLSX) export
- **Error Handling**: Comprehensive logging and error handling
- **Debug Mode**: Detailed console output to understand page structure
- **Dynamic Content**: Uses Selenium to handle JavaScript-rendered content

## 📋 Prerequisites

- Python 3.7 or higher
- Google Chrome browser installed
- pip (Python package manager)

## 🚀 Installation

1. **Clone the repository** (or create a new project folder):
```bash
git clone https://github.com/TanayodS/thailand-top50-companies.git
cd thailand-top50-companies
```

2. **Create a virtual environment** (recommended):
```bash
# On Windows
python -m venv venv
venv\Scripts\activate

# On macOS/Linux
python3 -m venv venv
source venv/bin/activate
```

3. **Install required packages**:
```bash
pip install -r requirements.txt
```

## 📦 Dependencies

Install all dependencies at once:
```bash
pip install selenium webdriver-manager beautifulsoup4 pandas openpyxl
```

**Individual packages:**
- `selenium` - Browser automation for dynamic content
- `webdriver-manager` - Automatic ChromeDriver management
- `beautifulsoup4` - HTML parsing and content extraction
- `pandas` - Data manipulation and CSV/Excel export
- `openpyxl` - Excel file generation

## 💻 Usage

### Option 1: Run the Debug Scraper (Recommended First Time)

```bash
python scraper_debug.py
```

This will:
- Open a Chrome browser window
- Load the website
- Display debug information about page structure
- Help identify what data is available

### Option 2: Run the Main Scraper

```bash
python scraper.py
```

### Option 3: Use in Your Python Code

```python
from scraper_debug import ThailandTop50Scraper

# Create scraper instance
scraper = ThailandTop50Scraper()

# Run scraper
scraper.scrape()
```

## 📁 Project Structure

```
thailand-top50-companies/
├── scraper.py              # Main scraper implementation
├── scraper_debug.py        # Debug version with detailed output
├── requirements.txt        # Python dependencies
├── README.md              # This file
├── .gitignore             # Git ignore patterns
└── output/
    ├── thailand_top50_companies.csv    # Export file (CSV)
    └── thailand_top50_companies.xlsx   # Export file (Excel)
```

## 🔧 Configuration

Edit the scraper to customize:

```python
# In scraper_debug.py or scraper.py

# Change target URL
url = "https://top50.workventure.com/"

# Adjust wait time (in seconds)
time.sleep(5)  # Increase if page loads slowly

# Toggle headless mode (no browser window)
# options.add_argument('--headless')

# Change output filename
filename = "my_companies.csv"
```

## 📊 Output Format

### CSV Export
The CSV file contains columns:
| Column | Description |
|--------|------------|
| rank | Company ranking (1-50) |
| company_name | Official company name |
| description | Company description/tagline |
| link | Company website/profile URL |
| logo | Company logo image URL |

### Excel Export
Same structure as CSV but in `.xlsx` format with formatting.

## 🐛 Troubleshooting

### Issue: "No such file or directory: chromedriver"
**Solution**: Install `webdriver-manager`
```bash
pip install webdriver-manager
```

### Issue: Chrome window doesn't open
**Solution**: Install Google Chrome browser from https://www.google.com/chrome/

### Issue: "No companies found"
**Solution**: 
- The website structure may have changed
- Run `scraper_debug.py` to see what's on the page
- Share the debug output for assistance

### Issue: Module not found errors
**Solution**: Ensure all dependencies are installed
```bash
pip install -r requirements.txt
# or
pip install selenium webdriver-manager beautifulsoup4 pandas openpyxl
```

### Issue: Script hangs/freezes
**Solution**: Increase the wait time in the script
```python
time.sleep(8)  # Increase from 5 to 8 seconds
```

## 🔍 Debugging Tips

1. **Run debug version first**:
   ```bash
   python scraper_debug.py
   ```

2. **Check browser console** (F12 in Chrome) for JavaScript errors

3. **Inspect HTML structure**:
   - Right-click on page → "Inspect" 
   - Look for company name, rank, description elements

4. **Enable verbose output**:
   - Modify logging level to DEBUG in the script

5. **Check file permissions**:
   - Ensure write access to the output directory

## 📝 Example Output

When running successfully, you'll see:
```
============================================================
🚀 Thailand Top 50 Companies Scraper
============================================================
Target URL: https://top50.workventure.com/

📥 Setting up Chrome driver...
✓ Chrome driver ready

📡 Loading webpage (waiting 5 seconds for JavaScript to load)...
✓ Page loaded

📄 Parsing page content...
📋 Page title: Top 50 Companies | WorkVenture

🔎 Searching for company data...
✓ Found 50 elements using selector: <div>

  1. Company Name 1 - Description...
  2. Company Name 2 - Description...
  ...

✅ Successfully scraped 50 companies!
💾 Exported to: thailand_top50_companies.csv

🔒 Closing browser...
✓ Done
```

## 🤝 Contributing

Feel free to improve this project:
- Fix bugs or improve scraping logic
- Add new features (filtering, sorting, etc.)
- Optimize performance
- Improve documentation

## ⚠️ Legal & Ethical Notes

- **Respect robots.txt**: Check `top50.workventure.com/robots.txt`
- **Terms of Service**: Review website ToS before scraping
- **Rate Limiting**: Add delays between requests to avoid overloading servers
- **Educational Use**: Use this project responsibly and legally
- **Website Changes**: Structure may change; update selectors as needed

## 📞 Support

If you encounter issues:

1. Check troubleshooting section above
2. Run debug version: `python scraper_debug.py`
3. Share error messages and console output
4. Check internet connection

## 📄 License

This project is open source and available under the MIT License.

## 👤 Author

**TanayodS**  
Created: May 11, 2026

---

**Happy Scraping! 🎉**
