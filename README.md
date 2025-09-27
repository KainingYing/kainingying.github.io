# Academic Homepage

A data-driven academic homepage template that separates content from presentation.

## Architecture

- `index.html` - Main template file with styling and JavaScript
- `meta/` - JSON configuration files containing all content data
  - `profile.json` - Personal information, contact details, and bio
  - `news.json` - News and announcements
  - `papers.json` - Publications with `selected` field to mark featured papers
  - `education.json` - Educational background
  - `experiences.json` - Work experiences and internships
  - `misc.json` - Miscellaneous information and footer

## Usage

1. Update the JSON files in the `meta/` folder with your information
2. The webpage will automatically load and render the content dynamically
3. No need to modify `index.html` for content updates

## Features

- **Dynamic Content Loading**: All content is loaded from JSON files
- **Publication Management**: Single publication list with `selected` field for featured papers
- **BibTeX Integration**: Inline BibTeX display with copy and download functionality
- **Responsive Design**: Modern and clean UI
- **Easy Maintenance**: Update content by editing JSON files only

## Updating Content

To update your homepage:

1. **Profile Information**: Edit `meta/profile.json`
2. **News**: Add/edit entries in `meta/news.json`
3. **Publications**: Update `meta/papers.json` (set `selected: true` for featured papers)
4. **Education**: Modify `meta/education.json`
5. **Experiences**: Update `meta/experiences.json`
6. **Other Info**: Edit `meta/misc.json`

The changes will be reflected immediately when you refresh the page.

## Publication Data Structure

Each publication in `meta/papers.json` has the following structure:

```json
{
  "title": "Paper Title",
  "authors": "Author list with <b>Your Name</b> for bold formatting",
  "venue": "Conference/Journal Name Year",
  "selected": true,  // Set to true for featured publications
  "highlight": "Spotlight",  // Optional: for special recognition
  "phdPeriod": false,  // Set to false for pre-PhD work (adds separator)
  "links": [
    { "type": "Paper", "url": "paper_url" },
    { "type": "Code", "url": "code_url" },
    { "type": "BibTeX", "url": "bibtex_file_path" }
  ]
}
```

- `selected: true` papers will appear in the "Selected" tab
- `phdPeriod: false` papers will appear below the "Ph.D. Period ↑" separator in the full list
- Empty `url` fields will display as plain text without links
- BibTeX files should be placed in the `bib/` folder and referenced by their relative path

## BibTeX Integration

When users click a BibTeX link, the citation will be displayed in an inline text box directly below the corresponding paper with:
- **Copy functionality**: One-click copy to clipboard
- **Download functionality**: Download as .bib file
- **Keyboard shortcuts**: Press ESC to close
- **Click outside**: Click anywhere outside the box to close
- **Inline display**: Shows directly under the paper for better context 