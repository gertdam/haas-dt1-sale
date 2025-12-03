# HAAS DT-1 Sale Project

## Project Summary

Sales page for a HAAS DT-1 CNC drilling/tapping center with all associated tooling and equipment, owned by IMBU BV (Netherlands).

**Live Site:** https://gertdam.github.io/haas-dt1-sale/

**Repository:** https://github.com/gertdam/haas-dt1-sale

## Owner

- **Company:** IMBU BV
- **Contact:** Gert Dam, Managing Director
- **Email:** gdam@imbu.nl

## The Machine

**HAAS DT-1** - Compact vertical machining center (Serial #1154161)
- Built: August 2018
- High-speed drilling and tapping machine
- Original purchase: €57,480 from Landré (Netherlands HAAS distributor)

### Machine History
- **2018-2021:** Demo machine in Landré showroom
- **October 2021:** Purchased by IMBU BV
- **2021-2025:** Used exclusively for prototyping (never production)
- **December 1, 2025:** Full service by Landré (report available)

### Key Stats
- Spindle hours: ~502 (exceptionally low for age)
- Power-on hours: ~1,764
- Condition: Excellent

## What Was Built

### Sales Page (index.html)
Single-file static HTML with embedded CSS/JS containing:
- Dark industrial theme
- Hero section with clickable image (opens lightbox)
- Machine history timeline
- Photo gallery (19 images) with lightbox navigation
- Equipment tables (toolholders, cutting tools, clamping)
- Document browser (55 PDFs organized by category)
- Investment summary
- Contact section

### Directory Structure
```
/
├── index.html              # Main sales page
├── assets/
│   ├── images/            # 19 full-size JPG photos
│   ├── thumbs/            # 19 thumbnail images (400px)
│   └── documents/
│       ├── landre/        # Machine purchase order
│       ├── ceratizit/     # 45 tooling invoices
│       └── leering/       # 9 Lang clamping invoices
├── data/
│   ├── inventory.json     # Master inventory data
│   └── *.json             # Extracted invoice data
└── source-documents/      # Original source files
    ├── landre/
    ├── ceratizit/
    ├── leering/
    └── images-original/   # Original HEIC photos
```

## Technical Details

### Image Processing
- Converted 19 HEIC images to JPG using macOS `sips`
- Generated thumbnails at 400px max dimension
- All images accessible in lightbox with keyboard navigation

### PDF Processing
- Extracted data from 55 invoices using Python/pdfplumber
- Organized into JSON inventory files
- All PDFs accessible via document browser

### Features
- Self-contained (no CDN dependencies)
- Responsive design
- Lightbox with arrow key navigation
- Document browser with category tabs
- Hover effects on hero image with "Click to enlarge" hint

## Hosting

- **Platform:** GitHub Pages
- **URL:** https://gertdam.github.io/haas-dt1-sale/
- **Repository:** Public (view-only for others, only owner can edit)

## Investment Summary

| Category | Amount |
|----------|--------|
| Machine (HAAS DT-1) | €57,480 |
| Tooling (Ceratizit) | ~€15,750 |
| Clamping (Lang) | ~€9,000 |
| **Total** | **~€82,230** |

Note: Tooling shown for reference only. Some items are new, others used or discarded. For pricing purposes, assume no tooling is included.

## Local Development

To run locally:
```bash
python3 -m http.server 8000
# Open http://localhost:8000
```

## Deployment

Changes are deployed by pushing to the main branch:
```bash
git add .
git commit -m "Description of changes"
git push
```

GitHub Pages will automatically rebuild within 1-2 minutes.
