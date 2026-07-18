# CafeManager - Mobile-First Income Management System

A comprehensive web application for managing daily collection data from multiple cafeterias and eco-shops across office locations.

## Architecture Overview

- **Frontend**: GitHub-hosted HTML/CSS/JavaScript (mobile-responsive)
- **Backend**: Google Apps Script (serverless functions)
- **Data**: Google Sheets (master data + user credentials)
- **Deployment**: Apps Script Web App + GitHub Pages (static files)

## Components

### Frontend (GitHub-hosted)
- `html/index.html` - User data entry form
- `html/adminReport.html` - Admin consolidated reports
- `html/shopPanel.html` - Individual shop reports
- `js/config.js` - Configuration and API wrapper
- `css/` - Responsive styles

### Backend (Google Apps Script)
- `Code.gs` - Single backend file with all business logic
  - Authentication (users & admins)
  - Data processing and validation
  - Report aggregation and PDF generation
  - CSV export

### Database (Google Sheets)
- Master data sheets per location
- USER_CREDENTIALS sheet for authentication
- No modifications needed to existing structure

## Setup Instructions

### 1. Deploy Apps Script

1. Open your Google Sheet: `https://docs.google.com/spreadsheets/d/1HIxY9hwjI2ITVRvl3_v5kABZJtS7lffYFoqihLRPO5s/`
2. Go to **Extensions > Apps Script**
3. Replace the code with `Code.gs` from this repository
4. Click **Deploy > New Deployment**
5. Select Type: **Web app**
6. Execute as: Your email
7. Who has access: **Anyone**
8. Copy the deployment URL

### 2. Update Frontend Config

1. Edit `html/js/config.js`
2. Replace `YOUR_DEPLOYMENT_ID` with your deployment URL
3. Example: `https://script.google.com/macros/d/AKfycbxXXXXXXXXXXXXXXXXXXXXXXXXXX/usercontent`

### 3. Host HTML Files

#### Option A: GitHub Pages (Recommended)
1. Go to repository Settings > Pages
2. Enable GitHub Pages from main branch, `/root` or `/docs` folder
3. Your site: `https://venu68108-debug.github.io/cafemanager`

#### Option B: Self-Hosted
- Copy HTML files to any web server
- Update `config.js` with correct paths

## Usage

### For Data Entry Users
1. Go to: `https://venu68108-debug.github.io/cafemanager/html/index.html`
2. Login with provided credentials
3. Enter daily collection data
4. View your monthly report

### For Shop Managers
1. Go to: `https://venu68108-debug.github.io/cafemanager/html/shopPanel.html`
2. Select date range
3. Download PDF report

### For Admins
1. Go to: `https://venu68108-debug.github.io/cafemanager/html/adminReport.html`
2. Login with admin credentials
3. View consolidated reports from all locations
4. Export as CSV or PDF

## Mobile Responsiveness

- Optimized for all device sizes (320px - 1920px)
- Touch-friendly buttons and inputs
- Vertical stack layout for mobile
- Responsive tables with scroll
- Fast load times

## Security Notes

- User credentials hashed with SHA-256
- CORS-safe API communication
- Admin-only access controls
- No sensitive data in localStorage

## Troubleshooting

### "Config file not found"
- Ensure `js/config.js` is in correct path
- Check `APPS_SCRIPT_URL` in config.js

### "Failed to call function"
- Verify deployment URL is correct
- Check Apps Script deployment hasn't expired
- Ensure user has access to Google Sheet

### Mobile rendering issues
- Clear browser cache (Ctrl+Shift+Delete)
- Try different mobile browser
- Check viewport meta tag is present

## License

Internal use only.

## Support

Contact: [Your contact info]
