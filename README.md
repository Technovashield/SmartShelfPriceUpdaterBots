# WoolworthPriceUpdatesPromotions
“UiPath RPA Project for automating price updates &amp; promotions at Woolworths.”
🛒 Woolworths Price Updates and Promotions Bot

📌 Project Overview

Project Name: Woolworths Price Updates and Promotions BotTechnology Stack: UiPath Studio 25.10, UiPath Data Service, Excel/CSV, Outlook Desktop IntegrationGoal: Automate price updates in a Data Service entity based on promotional rules, using robust error handling, audit logs, and reporting.

🔧 Functional Flow

flowchart TD
    A[Start: Main.xaml] --> B[Read Data: Products + Promotions CSV]
    B --> C[Calculate Final Prices Based on Promotions]
    C --> D[Generate Updated Products CSV and Summary Report]
    D --> E[Update Data Service with New Final Prices]
    E --> F[If Error: Invoke ErrorHandling.xaml]
    F --> G[Log to File and Send Outlook Email]
    G --> H[End]

📁 Folder Structure

ProjectRoot/
├── Data/
│   ├── ProductsData.csv
│   ├── PromotionsData.csv
│   └── UpdatedProductsData.csv
├── Reports/
│   └── ProductSummaryReport.xlsx
├── Logs/
│   └── ErrorLog_yyyyMMdd.txt
├── PriceCalculation/
│   └── CalculatePrices.xaml
├── DataUpdate/
│   └── UpdateData.xaml
├── ErrorHandling/
│   └── ErrorHandling.xaml
├── Main.xaml
└── README.md

⚙ Workflow Files

1. CalculatePrices.xaml

Reads product and promotion data

Applies flat or percentage discounts

Ensures no negative prices

Writes results to UpdatedProductsData.csv

Filters and exports summary to ProductSummaryReport.xlsx

2. UpdateData.xaml

Reads UpdatedProductsData.csv

Matches ProductID with Product entity records

Updates the FinalPrice field in the Data Service

Logs successful updates and handles mismatches

3. ErrorHandling.xaml

Captures any exception passed

Appends the error details to a log file

Sends an Outlook email notification with error details

🚀 Deployment Instructions

🧩 Prerequisites

UiPath Studio (2023.10 or later recommended)

Outlook Desktop App installed

UiPath Excel, System, Mail, and Data Service packages installed

Product entity in Data Service with: ProductID, ProductName, FinalPrice

✅ Run Instructions

Place all CSVs in Data/ folder

Ensure your entity is populated with test/mock data

Open Main.xaml and run the project

Monitor logs in the Output panel or Logs/ folder

📬 Email & Logging Setup

Outlook Mail: Uses Send Outlook Mail Message activity (not Office 365 version)

File Logging: Appends errors to /Logs/ErrorLog_yyyyMMdd.txt

🔍 Sample Use Cases

Automatically apply promotional discounts to Woolworths products

Generate pricing reports for review

Update backend database without manual data entry

Get notified if anything fails during the update process

✅ GitHub Upload Instructions

Step-by-Step (Manual Upload via Git Bash)

cd path/to/your/project
git init
git add .
git commit -m "Initial commit: Woolworths Bot"
git remote add origin https://github.com/Technovashield/woolworths-bot.git
git push -u origin main

OR:

Use GitHub web interface:

Click "Add file" > "Upload files"

Upload everything (XAML, CSV, folders, README)

Commit to main branch

👩‍💻 Author & Credits

Built by: Roopa KansaraRole: RPA Automation DeveloperGuided by: Project Planning + Mentorship + Best Practices

📄 License

This UiPath project is open for demonstration and learning purposes. Not intended for commercial distribution without appropriate licensing agreements.
