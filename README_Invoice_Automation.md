# 📄 Invoice Automation (OCR → Google Sheets)

**Open-source tool for automatic invoice data extraction (OCR) and saving structured data to Google Sheets using Make and PDF.co.**

---

## 🔧 What Does It Do?

This solution allows you to scan an invoice using your phone, save it as a PDF in Dropbox, and then automatically extract invoice data and store it in Google Sheets.  
If you already have invoices in PDF format, simply upload them to the monitored Dropbox folder.

---

## 🧰 Requirements

- **Make** account – free plan is sufficient  
- **PDF.co** account – free 30‑day trial available  
  After the trial period, a subscription is required (approx. USD 10/month).  
  This is the cost of using an external service – the project author does not charge any fees.
- Google account with access to **Google Sheets**
- **Dropbox** account – free plan (2 GB) is sufficient

---

## 📸 How It Works

1. **Scan the invoice with your phone**  
   Using the Dropbox mobile app (Android / iOS).  
   You can also manually upload an existing PDF file to the Dropbox folder.

2. **The file lands in the invoices folder**  
   The scan or PDF should be placed in a dedicated folder, e.g. `OCR_Invoices`.  
   This folder is continuously monitored by the automation.

3. **Make scenario is triggered**  
   - On the free Make plan, the automation checks for new files every 15 minutes  
   - You can also run it manually to process files immediately  
   - Default limit: 3 invoices processed concurrently

4. **PDF.co processes the invoice (OCR)**  
   Key data is extracted from the document, e.g. invoice number, date, amount, tax ID, etc.

5. **Data is saved to Google Sheets**  
   All extracted data is automatically written to a prepared spreadsheet, ready for export, analysis, or integration with other systems.

---

## 🛠️ Step-by-Step Setup

### 1. Create Required Accounts
- Register at [Make.com](https://www.make.com)
- Register at [PDF.co](https://app.pdf.co/signup)
- Create a Dropbox account at [dropbox.com](https://www.dropbox.com)
- Ensure you have a Google account (for Google Sheets)

---

### 2. Prepare Google Sheets

Create a spreadsheet with columns such as:
- Invoice number, Issue date, Sale date, Payment due / Paid, Seller name, Seller tax ID, Seller street, Seller city, Seller postal code, Seller country, Buyer name, Buyer street, Buyer city, Buyer postal code, Buyer country, Product/service, Net amount, VAT amount, Gross amount, Currency, VAT %, Payment method, Quantity, Notes

Sample Google Sheet (template):  
https://docs.google.com/spreadsheets/d/1XcNod5BhFseqvn1TxVz4i1LwbOT3YndlpyLGaeusaug/edit  
You can copy it and reuse it – just clear the rows and keep the headers.

---

### 3. Create Dropbox Folder

- Install the **Dropbox** mobile app (Android / iOS)
- Log in and create a folder, e.g. `OCR_Invoices`
- You can:
  - upload PDFs manually
  - or **scan invoices directly with your phone** using Dropbox’s *Scan* feature  
    👉 *Recommended – provides the best PDF quality for OCR*

---

### 4. Import Make Scenario (Blueprint)

To get started quickly, import the prepared Make scenario (blueprint).

#### 🔽 Step 1: Download Blueprint from GitHub

1. Go to the GitHub repository  
2. Locate `Faktury-rachunki.blueprint.json`  
   or use this direct link:  
   https://github.com/PabloPapito/AutomatyzacjaFaktur/blob/main/Faktury-rachunki.blueprint.json
3. Click **Download**

---

#### 🧩 Step 2: Import Blueprint in Make

1. Log in to [Make.com](https://www.make.com)
2. Go to **Scenarios**
3. Click **+ Create a new scenario**
4. Open the menu (⋮) → **Import blueprint**
5. Select the downloaded `Faktury-rachunki.blueprint.json`
6. Click **Import**

Done – the scenario is now available in your account.

---

### 🔌 Step 3: Configure Connections

Each module requires authentication. Click on each module and configure it as follows:

#### ✅ Dropbox
1. Open the **Dropbox – Watch Files** module
2. Click **Add** and log in to your Dropbox account
3. Name the connection (e.g. `Dropbox – Invoices`)
4. Select the monitored folder (e.g. `/OCR_Invoices`)

#### ✅ PDF.co (API Key)
1. Go to https://app.pdf.co
2. Open **Profile** and copy your **API Key**
3. In Make, open the **PDF.co** module → **Add**
4. Paste the API key and confirm

#### ✅ Google Sheets
1. Open the **Google Sheets** module
2. Click **Add** and log in to your Google account
3. Approve permissions  
   *(Sheet and columns are already configured in the blueprint)*

#### ✅ JSON (Parser)
No additional configuration required – it processes data returned by PDF.co automatically.

---

### ▶️ Running the Automation

1. Upload an invoice PDF to the Dropbox folder
2. Click **Run once** to test the scenario
3. Within seconds, extracted data will appear in Google Sheets

---

## ⚠️ Notes

- On the free Make plan, the scenario runs every 15 minutes
- You can trigger it manually using **Run once**
- Default concurrency limit: 3 invoices (configurable)
- PDF.co requires a paid plan after the trial period – cost is on the user side  
  **The author does not charge any fees for this project**

---

## 💡 Who Is This For?

This tool is especially useful if:
- You run an accounting office and process invoices daily
- You are an accountant or business owner who wants to save time
- You are tired of manual data entry into Excel
- You want a simple, practical automation that works for you

No programming skills are required.  
If something gets stuck – the project author is available to help.

---

## 🤝 License & Usage

This project is **open source**. You are free to:
- run it yourself
- modify it to fit your needs
- extend and share it further

Need help with customization or deployment?

📩 Contact:
- Website: https://automatyzacjabiurowa.pl  
- LinkedIn: https://www.linkedin.com/in/golen/

---

## 🔗 Useful Links

- https://make.com
- https://pdf.co
- https://dropbox.com
- https://sheets.google.com

---

## 🧩 Possible Extensions

- Support for additional invoice formats (Word, JPG images)
- Integration with invoicing systems
- Notifications (e.g. email, Slack)

---

Time is money. Automation saves both. 🚀
