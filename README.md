# 🏢 BWIW - Sales Intelligence Dashboard

> A fully interactive, print-ready FMCG Sales Dashboard built in a **single HTML file**.  
> No backend. No server. No subscription. Open the file — it just works.

![Dashboard Preview](preview.png)

---

## ✨ Live Demo

👉 **[Open Dashboard](https://YOUR-USERNAME.github.io/bwiw-sales-dashboard/BWIW_Dashboard_v5.html)**

---

## 📌 What This Is

A production-grade Sales Intelligence Dashboard built for **BHAI-BROTHER CORPORATION**,  
an FMCG distributor operating across Bangladesh.

The dashboard processes **266,000+ raw transaction rows** entirely in the browser —  
no cloud, no API, no server required.

---

## 🚀 Features

| Feature | Detail |
|---|---|
| 📊 **8 Interactive Charts** | Region, Daily Trend, Brand Donut, Delivery Status, Retail vs Wholesale, SPO Ranking, Category, Distributor Table |
| 💡 **5 KPI Scorecards** | Sales Revenue, Order Value, Fulfillment Rate, Unique Customers, Total Invoices |
| 🔽 **5 Live Filters** | Region, Brand, Delivery Status, Customer Type, Approval Status |
| ⬆ **File Upload** | Upload any `.xlsx` file — dashboard updates instantly |
| 📐 **A4 Landscape Layout** | Print-ready 297mm × 210mm, 2-page split |
| 💻📱 **Device Toggle** | Laptop view ↔ Mobile view — real layout switch |
| 📸 **Screenshot Export** | Capture full dashboard as PNG — share on WhatsApp or email |
| ⬇ **Excel & CSV Export** | 3-sheet Excel (Area Summary, Top 15, Bottom 15) + filtered CSV |
| 🔄 **Refresh Button** | Re-runs all calculations with updated timestamp |
| 🚫 **Zero Dependencies** | No npm, no build step, no internet required after first load |

---

## 📂 Project Structure

---

## 🖥️ How to Use

### Option A — Open directly (no install)
```bash
# Just download and open in any browser
open BWIW_Dashboard_v5.html
```

### Option B — Upload your own data
1. Open the dashboard in Chrome or Edge
2. Click **⬆ Upload File** in the top toolbar
3. Select your `.xlsx` file (must have these columns):

| Column | Description |
|---|---|
| `Region` | Sales region name |
| `BrandName` | Product brand |
| `SalesDPTotal` | Sales value in BDT |
| `OrderDPTotal` | Order value in BDT |
| `OrderDate` | Date of order |
| `CustomerType` | RETAIL or WHOLESALE |
| `DeliveryStatus` | Full / Partial / Pending / Cancel |
| `ApprovalStatus` | Approved / Pending |
| `CategoryName` | Customer category |
| `SPOName` | Sales Personnel Officer name |
| `DistributorName` | Distributor name |
| `CustomerCode` | Unique customer ID |
| `InvoiceNo` | Invoice number |

4. Dashboard updates automatically — all 8 charts, all 5 KPIs, all filters

---

## 📊 Dashboard Pages

### Page 1 — Overview
- KPI scorecards (Sales, Orders, Fulfillment Rate, Customers, Invoices)
- Sales vs Orders by Region (horizontal bar)
- Daily Sales Trend with peak/low highlights
- Brand Revenue Share (donut)
- Delivery Status breakdown (donut)
- Retail vs Wholesale by Region (bar)

### Page 2 — Operational Detail
- Key Insights strip (auto-generated, 5 metrics)
- Top 15 SPOs accountability ranking
- Category-wise Revenue
- Top 10 Distributors table with fulfillment bars

---

## 🛠️ Tech Stack

| Library | Version | Purpose |
|---|---|---|
| [Chart.js](https://chartjs.org) | 4.4.0 | All charts |
| [SheetJS (xlsx)](https://sheetjs.com) | 0.18.5 | Excel file parsing & export |
| [html2canvas](https://html2canvas.hertzen.com) | 1.4.1 | Screenshot capture |
| [DM Sans](https://fonts.google.com/specimen/DM+Sans) | — | Typography |
| Vanilla JS | ES2020 | Everything else |

**No React. No Vue. No build step. No node_modules.**

---

## ⚡ Performance

| Metric | Value |
|---|---|
| Raw rows processed | 266,000+ |
| Processing method | Chunked (20K rows/tick, non-blocking) |
| Aggregated records | ~10,435 |
| Total file size | ~880 KB (data embedded) |
| Browser requirement | Chrome 90+ / Edge 90+ / Firefox 88+ |

---

## 🗂️ Data Architecture

The dashboard uses a **column-store format** with integer-encoded dimension lookups
to minimize JSON size and maximize filter performance:

```javascript
// Instead of storing strings repeatedly:
{ region: "CENTRAL", brand: "NAVRATNA", ... }  // ❌ large

// We store integer indices + a lookup table:
{ Region: 0, BrandName: 7, ... }               // ✅ compact
lookups.Region[0] === "CENTRAL"
```

Filters run in **O(n)** with cross-filter aware option counts (each dropdown
shows live BDT sales excluding its own filter, updating as other filters change).

---

## 📸 Screenshots

| Page 1 — Overview | Page 2 — Operations |
|---|---|
| *(add your screenshot here)* | *(add your screenshot here)* |

---

## 📄 License

MIT License — free to use, modify, and distribute.  
See [LICENSE](LICENSE) for details.

---

## 🤝 Contributing

Pull requests are welcome. For major changes, open an issue first.

---

## 👤 Author

**SHAGAR GOSHAMI**  
🌐www.linkedin.com/in/shagar-goshami



---

*Built with ❤️ — no backend harmed in the making of this dashboard.*
