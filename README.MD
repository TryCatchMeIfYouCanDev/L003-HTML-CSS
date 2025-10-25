# Hyperlinks and Page Structure in HTML

## 1. Introduction

In HTML, hyperlinks connect web pages, documents, or other resources, and are defined with the `<a>` (anchor) tag. This inline element does not interrupt the content flow and can link to:

* External web pages
* Local files
* Email addresses
* Telephone numbers
* Specific sections within the same page

## 2. Basic Structure of the `<a>` Tag

```html
<a href="https://www.example.com">Visit Example</a>
```

### Main Attributes

* **href**: Defines the link destination (URL or path).
* **target="_blank"**: Opens the link in a new browser tab (not a new window).
* **title**: Provides a tooltip or short description of the link.
* **rel**: Defines the relationship between the current page and the linked document (e.g., `rel="tag"`, `rel="bookmark"`).
* **tabindex**: Sets the tab navigation order for accessibility.
* **accesskey**: Defines a keyboard shortcut for quick access.
* **aria-label**: Improves accessibility by describing the purpose of the link.

## 3. Absolute vs Relative Paths

### Absolute Paths

An absolute path is a full URL that points to a resource on the Internet.

```html
<a href="https://www.google.com/">Go to Google</a>
```

* Always points to the same external resource.
* Independent from the file location in your site.
* Ideal for linking to external websites.

### Relative Paths

A relative path locates a file based on the current page’s directory.

```html
<a href="corsi.html">Corsi</a>
```

**Examples:**

* Same folder: `news2.html`
* Subfolder: `documenti/ita/corsi.html`
* Parent folder: `../../index.html`
* Root folder: `/index.html`

> Note: In local testing, relative paths may require Visual Studio Code Go Live to simulate a server.

## 4. Internal Page Anchors

Internal links allow users to jump to a specific section of the same page.

```html
<a href="#perAziende">Per Aziende</a>
<div id="perAziende">Content here...</div>
```

* The href value starts with a hash `#` followed by the target element’s id.
* Useful for long pages or documentation sites (e.g., Wikipedia).

**Keyboard Shortcuts:**

* Windows: Alt Gr + #
* Mac: Option + #

## 5. Accessibility and WAI-ARIA

To improve accessibility, links can include attributes defined by WAI-ARIA:

```html
<a href="#Storia" title="Storia HTML5" aria-label="Vai al link interno Storia" rel="bookmark" tabindex="1" accesskey="s" role="link">Storia</a>
```

* `aria-label`: Describes the link for screen readers.
* `role="link"`: Clarifies the element’s function.
* Reference: WAI-ARIA Standards – W3C

## 6. The `<title>` Tag and SEO

The `<title>` element:

* Appears in the browser tab.
* Provides a quick reference to the page.
* Cannot be formatted.
* Helps when saving bookmarks or using search engines.

**Best Practices:**

* Avoid identical titles for multiple pages.
* Use meaningful titles that describe the page content.
* Titles improve usability and search engine visibility.

## 7. Link Behaviour and Browser Tabs

* `<a target="_blank">` opens the link in a new tab, not a new window.
* Opening a new tab avoids blocked pop-ups.
* Pop-unders are windows that open behind the main browser window.
* Modern design prefers modal windows (z-index) rather than pop-ups.

## 8. Project Structure and File Management

Good organisation helps maintain websites.

**Recommended Folder Structure:**

```
project/
│
├── index.html
├── /css/
├── /images/
├── /scripts/
└── /pages/
```

**Naming Rules:**

* Avoid spaces in filenames (%20 breaks URLs).
* Avoid mixing uppercase and lowercase; prefer camelCase or underscores: `corsiWeb`, `corsi_web`.
* File and folder names are case-insensitive but consistency is recommended.

## 9. Development and Deployment

* Test locally first (use Go Live in VS Code).
* After testing, upload files via FTP.
* HTTP allows online page viewing.
* Emulators can simulate server behaviour.

## 10. Static vs Dynamic Pages

* **Static Pages**: Individually created `.html` files.
* **Dynamic Pages**: Generated from templates and databases using server-side languages.

**Example:**
A wine catalogue could dynamically generate pages for each wine by linking a template to a database. This is similar to Mail Merge in Word and Excel.

## 11. Summary

* Use `<a>` for links to web pages, files, emails, or sections.
* Distinguish absolute vs relative paths.
* Use meaningful `<title>` tags for usability and SEO.
* Organise files and folders logically.
* Test links locally before publishing.
* Prefer modal windows over pop-ups.
* Use accessibility attributes (e.g., `aria-label`, `role`) when needed.
