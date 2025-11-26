# CTI Browser Extension Test Suite

A comprehensive testing page for evaluating the capabilities and limitations of Cyber Threat Intelligence (CTI) browser extensions.

## 🎯 Purpose

This test suite helps assess how well CTI browser extensions can detect and highlight Indicators of Compromise (IOCs) across various scenarios, including:

- Static HTML content
- Dynamically loaded content (SPA simulation)
- Virtual DOM re-rendering (React/Vue simulation)
- Obfuscation techniques (Canvas, Base64, CSS, etc.)
- Shadow DOM (open and closed)
- Iframes (same-origin)
- Forms and input fields
- Various HTML structures (tables, lists, code blocks)
- Performance under load (100+ IOCs)

## 🚀 Quick Start


### Run Locally

```bash
# Clone the repository
git clone https://github.com/YOUR-USERNAME/browser-extension-test.git
cd browser-extension-test

# Open in browser
open index.html
# or
python -m http.server 8000
# then visit http://localhost:8000
```

## 📋 Test Sections

### 1. Static IOCs (Baseline)
Tests basic detection with 15 static IOCs including:
- IP addresses (IPv4)
- Domain names
- URLs
- File hashes (MD5, SHA1, SHA256)
- CVE identifiers
- Email addresses

**Expected Result:** All extensions should detect these.

### 2. Dynamic Content (SPA Simulation)
Tests detection of IOCs added after initial page load.
- Manual load via button
- Auto-load every 5 seconds
- Simulates infinite scroll behavior

**Tests:** MutationObserver implementation

### 3. Virtual DOM / Re-rendering
Simulates React/Vue component re-renders.
- Manual re-render
- Auto re-render every 3 seconds

**Tests:** Highlight persistence after DOM updates

### 4. Obfuscation Tests
Tests various obfuscation techniques:
- **Canvas rendering** - IOCs drawn in canvas
- **Base64 encoding** - Encoded IOCs
- **CSS pseudo-elements** - IOCs in ::before/::after
- **Zero-width characters** - IOCs with invisible chars
- **Homoglyphs** - Cyrillic characters disguised as Latin

**Expected Result:** Most extensions will fail these tests.

### 5. Shadow DOM
Tests Shadow DOM access:
- **Open Shadow DOM** - Accessible to extensions
- **Closed Shadow DOM** - Typically inaccessible

**Tests:** Shadow DOM traversal capability

### 6. Iframes
Tests cross-frame detection:
- Same-origin iframe with IOCs

**Tests:** Cross-frame content access

### 7. Forms & Input Fields
Tests IOC detection in form elements:
- Input fields
- Textareas

**Tests:** Form element scanning

### 8. Special Formats
Tests IOC detection in structured content:
- Tables
- Lists (ul/ol)
- Code blocks (pre/code)

**Tests:** Complex HTML structure parsing

### 9. Performance Test
Tests extension performance with 100+ IOCs.

**Tests:** Scalability and performance limits

### 10. Results Checklist
Interactive checklist to track test results with JSON export capability.

## 📊 Using the Test Suite

1. **Install your CTI extension** in your browser
2. **Load the test page** (live or local)
3. **Observe which IOCs are highlighted** by the extension
4. **Interact with buttons** to trigger dynamic content tests
5. **Check the results** in the interactive checklist
6. **Export results** as JSON for documentation

## 🔧 GitHub Pages Deployment

This repository includes automatic deployment to GitHub Pages via GitHub Actions.

### Setup Instructions

1. **Fork or create this repository**

2. **Enable GitHub Pages**:
   - Go to repository Settings → Pages
   - Source: "GitHub Actions"

3. **Push to main branch**:
   ```bash
   git add .
   git commit -m "Initial commit"
   git push origin main
   ```

4. **Access your test page**:
   - `https://YOUR-USERNAME.github.io/browser-extension-test/`

The workflow automatically deploys on every push to `main`.

## 📝 Test Results Format

Export JSON format:
```json
{
  "timestamp": "2024-11-26T10:30:00.000Z",
  "tests": {
    "test-1": true,
    "test-2": false,
    ...
  }
}
```

## 🤝 Contributing

Contributions are welcome! Please feel free to submit issues or pull requests to:
- Add new test cases
- Support additional IOC types
- Improve test coverage
- Fix bugs

## 📄 License

This project is open source and available for testing CTI browser extensions.


## ⚠️ Disclaimer

This test suite uses example IOCs from documentation ranges (TEST-NET-1, TEST-NET-2, TEST-NET-3) and fictional domains. No real threat intelligence is included.

## 📧 Contact

For questions or issues, please open a GitHub issue in this repository.
