# CCBR Quarto Themes

Professional Quarto HTML themes and templates for scientific documentation, inspired by the Frederick National Laboratory (FNL) style guide.

## Features

✨ **Modern Design**
- Professional gradient headers with custom backgrounds
- Teal and lime color scheme optimized for scientific content
- Responsive layouts with clean typography

🎨 **Custom Components**
- Service buttons with brand logos (GitHub, OneDrive, Google Drive, etc.)
- Multiple tab themes (Subtle, Poppy, Scientific, Gradient, Neon)
- Styled tables, callouts, and code blocks
- Author affiliation formatting

📚 **Font Awesome Integration**
- Pre-configured with Font Awesome 6.5.1
- Icon-enhanced buttons for common services

## Installation

### As a Quarto Extension (Recommended)

Install directly from GitHub:
```bash
quarto add yourusername/ccbr-themes
```

Replace `yourusername` with the actual GitHub username/organization.

### Manual Installation

1. Clone the repository:
```bash
git clone https://github.com/yourusername/ccbr-themes.git
```

2. Copy the `_template` folder to your project

3. Reference the CSS files in your `_quarto.yml`

## Usage

### Basic Setup

After installation, use the theme in your `_quarto.yml`:
```yaml
format:
  ccbr-html: default
```

Or configure manually:
```yaml
format:
  html:
    code-fold: true
    code-tools: true
    toc: true
    toc-location: body
    page-layout: full
    theme: default
    css:
      - resources/css/html_post_styles.css
      - resources/css/author_affiliation.css
      - resources/css/buttons.css
    include-in-header:
      - text: |
          <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.1/css/all.min.css">
```

### Document Header

Add metadata to your `.qmd` file:
```yaml
---
title: "Your Document Title"
subtitle: "Optional Subtitle"
author: 
  - name: "Your Name"
    affiliation: "Your Organization"
    email: "your.email@example.com"
date: today
format: ccbr-html
---
```

## Components

### Service Buttons

Add linked buttons with brand icons:

**Filled Buttons:**
```markdown
[GitHub Repository](https://github.com/user/repo){.btn-github}
[OneDrive Folder](https://onedrive.com/folder){.btn-onedrive}
[Google Drive](https://drive.google.com/folder){.btn-gdrive}
[Dropbox Files](https://dropbox.com/folder){.btn-dropbox}
[LinkedIn Profile](https://linkedin.com/in/user){.btn-linkedin}
[Follow on X](https://twitter.com/user){.btn-twitter}
[Join Slack](https://slack.com/invite){.btn-slack}
[Discord Server](https://discord.gg/invite){.btn-discord}
[YouTube Channel](https://youtube.com/@channel){.btn-youtube}
[Email Us](mailto:user@email.com){.btn-email}
[Documentation](https://docs.example.com){.btn-docs}
[Download File](files/data.zip){.btn-download}
[Download PDF](files/document.pdf){.btn-pdf}
```

**Outline Buttons:**
```markdown
[GitHub](https://github.com/user/repo){.btn-outline-github}
[OneDrive](https://onedrive.com/folder){.btn-outline-onedrive}
[Email](mailto:user@email.com){.btn-outline-email}
```

### Custom Tab Themes

Apply different tab styles to panel-tabsets:
```markdown
::: {.panel-tabset .theme-ccbr-subtle}
## Tab 1
Content here

## Tab 2
More content
:::
```

**Available themes:**
- `.theme-ccbr-subtle` - Professional and clean
- `.theme-ccbr-poppy` - Vibrant and fun
- `.theme-ccbr-scientific` - Minimal and precise
- `.theme-ccbr-gradient` - Modern gradients
- `.theme-ccbr-neon` - Bold and animated

### Callouts

Standard Quarto callouts are pre-styled:
```markdown
::: {.callout-note}
This is a note callout
:::

::: {.callout-tip}
This is a tip callout
:::

::: {.callout-warning}
This is a warning callout
:::
```

### Horizontal Rules

Different styles available:
```markdown
---

---{.thick}

---{.teal}

---{.thin}

---{.section}
```

## Customization

### Color Variables

Override default colors by adding to your custom CSS:
```css
:root {
  --lime: #7cc349;
  --teal: #296b7f;
  --teal-light: #4e9db5;
  --teal-dark: #19424e;
  --lime-light: #b1ee85;
  --lime-dark: #528230;
  --orange: #ecba4c;
}
```

### Custom Background

Replace the default banner background:

1. Add your image to `resources/img/`
2. Update `html_post_styles.css`:
```css
.quarto-title-banner {
  background: 
    linear-gradient(135deg, rgba(25, 66, 78, 0.9) 0%, rgba(41, 107, 127, 0.8) 50%, rgba(78, 157, 181, 0.7) 100%),
    url('path/to/your/image.png') center/cover !important;
}
```

## File Structure
```
ccbr-themes/
├── _extensions/
│   └── ccbr/
│       ├── _extension.yml
│       ├── html_post_template.html
│       └── resources/
│           ├── css/
│           │   ├── html_post_styles.css
│           │   ├── author_affiliation.css
│           │   ├── buttons.css
│           │   ├── datatable_ccbr.css
│           │   └── references.css
│           ├── fontawesome/
│           └── img/
├── _template/                  # Template files for manual use
└── README.md
```

## Examples

See the [examples](examples/) folder for complete working examples:
- `basic-example.qmd` - Simple document with buttons
- `advanced-example.qmd` - Full-featured document with tabs, callouts, and custom styling

## Requirements

- Quarto >= 1.2.0
- Internet connection (for Font Awesome CDN)

## Contributing

Contributions welcome! Please:

1. Fork the repository
2. Create a feature branch
3. Submit a pull request



## Credits

- Inspired by Frederick National Laboratory (FNL) style guide
- Icons provided by [Font Awesome](https://fontawesome.com)


## Changelog

### Version 1.0.0
- Initial release
- Service buttons with Font Awesome icons
- 5 custom tab themes
- Professional styling for scientific documentation