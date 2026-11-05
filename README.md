Chia-Yu | B2B International Sales & Account Management Professional Portfolio

A high-performance, responsive executive resume and portfolio website designed for Chia-Yu, a senior B2B International Sales & Account Management professional with 12+ years of experience and an alumnus of National Taiwan University (NTU).

The application features a modern glassmorphism UI, robust light/dark mode support, built-in SEO and Generative Engine Optimization (GEO) machine-readable hints, and seamless serverless form submissions directly to Google Sheets.

🌟 Key Features

Executive & Bilingual Design: Tailored for international recruiters, global trade partners, and AI search engines, blending English and Traditional Chinese context.

Dynamic Theme Switcher: Fully responsive dark/light mode with robust persistent state management via localStorage and system preference detection.

Interactive Career Milestones: Showcases critical achievements, including the turnaround of Jin Sheu Enterprise's 2nd largest Japanese account ($1.31M to $1.81M revenue growth).

Serverless Contact Integration: Integrated with Google Apps Script (@OnlyCurrentDoc) to securely write visitor inquiries straight to a Google Spreadsheet without CORS limitations or backend maintenance overhead.

AI Search & GEO Optimization: Includes structured JSON-LD (ProfilePage schema) and dedicated AI content meta tags for optimal indexing by LLM-powered search engines.

🛠️ Tech Stack

Frontend: HTML5, Tailwind CSS (via CDN with custom configuration), FontAwesome 6.4.0, Inter Google Font.

Interactivity & State: Vanilla JavaScript (ES6+), DOM manipulation, LocalStorage.

Backend / Form Handling: Google Apps Script (GAS) Web App + Google Sheets.

Hosting Ready: Fully optimized as a single static file (index.html), compatible with GitHub Pages, Vercel, Netlify, or Cloudflare Pages.

🚀 Quick Start / Deployment

Since this project is contained within a single-file architecture (index.html), deployment is exceptionally straightforward:

Clone the repository:

git clone https://github.com/your-username/chiayu-portfolio.git
cd chiayu-portfolio


Local Testing:
Simply open index.html in your favorite web browser or run a local server (e.g., using VS Code Live Server).

Deploy to GitHub Pages:

Go to your repository Settings > Pages.

Set the source branch to main (or master) and folder to / (root).

Save and your portfolio will be live!

📊 Google Sheets Contact Form Setup (Optional)

To enable the live contact form writing directly to your Google Sheet:

Create a new Google Sheet with columns: Timestamp, Name, Email, Subject, and Message.

Open Extensions > Apps Script in the spreadsheet.

Paste the following script to handle POST requests:

function doPost(e) {
  var sheet = SpreadsheetApp.getActiveSpreadsheet().getActiveSheet();
  var data = e.parameter;
  sheet.appendRow([new Date(), data.name, data.email, data.subject, data.message]);
  return ContentService.createTextOutput(JSON.stringify({"result":"success"}))
                       .setMimeType(ContentService.MimeType.JSON);
}


Deploy as a Web App:

Execute as: Me

Who has access: Anyone

Paste the generated Web App URL into the configuration field on the portfolio contact form or directly into the input field in the UI.

📄 License

Distributed under the MIT License. See LICENSE for more information.
