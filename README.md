# REST fieldnotes

### A six-page REST API Development Guide

**HTML5 + CSS3** · **Static website** · **No dependencies** · **Academic portfolio project**

Learn the fundamentals. Follow a request. Return to the details when you need them.

> **Project status**  
> Implemented with OpenAI Codex assistance. Personal review, browser testing, and manual GitHub publication are pending. The examples are illustrative; this project does not implement an API.

**[Open the guide](index.html)** · **[Read the examples](examples-resources.html)** · **[Explore the CSS](css/style.css)**

**Author profile:** Karan Satyajit Chauhan  
**Repository:** [Add your GitHub repository URL]  
**Live demo:** [Add your published website URL]

---

## Contents

- [Overview and objectives](#overview-and-objectives)
- [Six chapters, one simple structure](#six-chapters-one-simple-structure)
- [Quick start](#quick-start)
- [Design and responsive behavior](#design-and-responsive-behavior)
- [Understanding the implementation](#understanding-the-implementation)
- [Accessibility and compatibility](#accessibility-and-compatibility)
- [Review and manual testing](#review-and-manual-testing)
- [AI-Assisted Development](#ai-assisted-development)
- [Learning review](#learning-review)
- [Screenshots](#screenshots)
- [Manual GitHub publication](#manual-github-publication)
- [Completion checkpoint](#completion-checkpoint)

## Overview and objectives

REST fieldnotes is a documentation website built as the third independent project in an HTML/CSS academic portfolio. It combines a readable technical guide with an interface suitable for future reference.

The revised scope uses **six HTML pages**, rather than one long document. Each chapter contains related topics, an on-page contents list, consistent chapter navigation, and previous/next links.

Objectives:

- Communicate API concepts accurately without pretending to build a working API.
- Practice multi-page information architecture and consistent navigation.
- Use semantic HTML, responsive CSS, readable code examples, and accessible native elements.
- Keep the folder structure small and the implementation understandable.
- Disclose AI assistance and leave honest space for personal modifications and testing.

### Technology stack and scope

Only **HTML5 and CSS3** power this site. There is no JavaScript, TypeScript, framework, external CSS library, backend, database, package manager, or build system. System fonts and CSS styling provide the entire visual design.

Code blocks display HTTP and JSON as text; they do not execute. No search, copy-to-clipboard control, API playground, login, or contact form is simulated.

## Six chapters, one simple structure

1. **[Overview](index.html)** — Introduction, learning path, and scope.
2. **[HTTP & REST](http-rest.html)** — HTTP fundamentals, REST constraints, client–server architecture, and stateless communication.
3. **[Methods & Status Codes](methods-status.html)** — GET, POST, PUT, PATCH, DELETE, safety, idempotency, and common statuses.
4. **[Requests & Responses](requests-responses.html)** — Message structure, headers, and JSON representations.
5. **[Security & API Design](security-design.html)** — Authentication, authorization, versioning, error handling, pagination, rate limiting, and best practices.
6. **[Examples & Resources](examples-resources.html)** — GET/POST exchanges, JSON responses, API errors, and primary references.

The sidebar also includes an expandable index of all **12 original guide topics**, preserving the initial requirements across the six chapters.

```text
rest-api-documentation/
├── index.html
├── http-rest.html
├── methods-status.html
├── requests-responses.html
├── security-design.html
├── examples-resources.html
├── css/
│   └── style.css
├── assets/
│   └── images/
│       └── .gitkeep
├── README.md
└── .gitignore
```

All pages live at the project root. One relative stylesheet supports every page. `.gitkeep` preserves the empty images folder when published with Git; it has no browser role.

## Quick start

1. Open the `rest-api-documentation` folder.
2. Double-click `index.html`, or open it through your browser's Open File command.
3. Follow chapter cards or the sidebar to the other pages.
4. Edit any HTML page or `css/style.css`, save, and refresh your browser.

**No installation or server is required.** Keep all six HTML files together and retain the stylesheet path.

The README uses standard Markdown headings, spacing, navigation links, callouts, and fenced code for readability on GitHub. Markdown renderers control the README's fonts and colors; the website's CSS does not style GitHub Markdown. Preview it in a Markdown viewer or after upload. The HTML links above may show source files in GitHub; the eventual live demo URL will open the rendered website.

## Design and responsive behavior

The interface uses an editorial documentation style: warm white surfaces, dark text, a green accent, numbered chapters, and dark code panels. Responsive typography and a bounded reading width help keep long explanations comfortable to scan.

On desktop, a **sticky sidebar** follows the reader within the document. Its height is bounded so navigation remains scrollable on short screens. At `48rem` and below, it becomes a normal top panel; chapter links wrap into a grid. At `30rem`, cards and chapter navigation stack into one column.

Fluid widths and `minmax(0, 1fr)` prevent content columns from forcing page overflow. Code blocks scroll horizontally within their own panel, preserving indentation. Keyboard users can focus these blocks to scroll them. At print time, code wraps and site navigation is hidden for a readable chapter printout.

The intended testing ranges are approximately 320–767px, 768–1023px, and 1024px and wider. Intermediate widths and browser zoom require testing too; breakpoints are content-driven rather than device guarantees.

## Understanding the implementation

### HTML: meaning before appearance

- **`header`, `main`, and `footer`** identify the site's top area, unique chapter content, and closing information.
- **`nav` landmarks** have distinct accessible labels for chapters, topics, breadcrumbs, on-page contents, and pagination.
- **`article`** represents the self-contained chapter; **`section`** groups topics and references its heading through `aria-labelledby`.
- One **`h1`** labels each page. Main topics use `h2`; callouts and cards use `h3`. The contents list has a small visual heading while retaining heading semantics.
- **`dl`, `dt`, and `dd`** pair concepts such as HTTP methods with explanations. Lists represent reading paths, navigation, and recommendations.
- **`figure` and `figcaption`** associate code excerpts with descriptions. **`pre` and `code`** preserve formatting and identify literal examples.
- **`details` and `summary`** let readers expand the complete topic index without JavaScript.

### How navigation works

`href="methods-status.html"` opens a sibling page. `href="#status-codes"` moves to an ID on the current page. `href="methods-status.html#status-codes"` does both.

Each page marks its current sidebar link with `aria-current="page"`. That attribute is written into the HTML; no script detects the active page. Styling `[aria-current="page"]` gives readers a visual location cue.

The skip link targets `main`, which has `tabindex="-1"`. This lets it receive focus without becoming an additional ordinary tab stop. Verify actual focus transfer in target browsers.

### CSS: a small shared system

**Custom properties** centralize colors, radius, and reading width. Changing `--accent` updates navigation, focus, and callout colors. Recheck contrast after theme changes.

**Grid** controls the sidebar/content structure, chapter cards, status cards, and pagination. `minmax(0, 1fr)` allows content to shrink without an intrinsic-width overflow. **Flexbox** handles branding, small navigation rows, and link card interiors.

**Sticky positioning** keeps the desktop sidebar visible without taking it out of normal flow. **Media queries** remove sticky behavior and collapse columns on smaller screens. `clamp()` scales headings between explicit limits.

**Hover states** emphasize links and tint cards. **`:focus-visible`** outlines anchors, summaries, and code panels. The code focus ring uses a light color inside its dark panel. **Reduced-motion rules** disable smooth scrolling and the card color transition.

### Professional practices and maintenance

The stylesheet has six labelled sections: defaults, site navigation, chapter typography, reference/code components, pagination/footer, and responsive/print rules. Class names describe purpose (`chapter-header`, `definition-list`, `code-example`) rather than a framework of generic utility classes.

Navigation is intentionally repeated in six HTML files. This avoids templating dependencies, but it introduces a maintenance responsibility: if you rename or add a page, update chapter links, topic links, and previous/next links consistently across every file.

For a future chapter, copy an existing page and update its title, description, heading, active-page marker, content IDs, contents list, pagination, and shared navigation. Avoid adding another abstraction until the maintenance cost actually warrants it.

## Accessibility and compatibility

The project aims toward WCAG 2.2 AA, with **no claim of verified conformance**.

- Named landmarks and logical headings support navigation.
- A skip link and focus indicators support keyboard use.
- The native topic disclosure works without a custom scripted control.
- Active navigation uses text, a border, and color.
- Decorative arrows and marks are hidden from assistive technology where appropriate.
- Code panels are keyboard-focusable and preserve readable indentation.
- Reduced motion and print presentation have explicit CSS rules.
- No informative images are used. Add meaningful alternative text if you introduce them later.

Current mainstream browsers support the main features used here: Grid, Flexbox, sticky positioning, custom properties, `clamp()`, and `details`. Fonts, focus behavior, scrollbars, and printing can differ. Historical and embedded browsers are not guaranteed.

## Review and manual testing

Source review examines organization, links, headings, code presentation, responsive rules, native interaction, and dependency scope. Static checks are limited inspections, not a full HTML validator or a browser accessibility audit.

**Browser and assistive technology testing: pending.** Record only tests actually performed.

### Checks completed by Codex

- **Six pages inspected:** unique IDs, a single primary heading per page, basic tag nesting, metadata, and correct active-chapter markers passed.
- **189 local file/anchor references:** all destinations resolved, including cross-page topic anchors and stylesheet references.
- **Five JSON example bodies:** parsed successfully.
- **CSS source:** balanced braces, focus/reduced-motion rules, and absence of imports, scripts, or `!important` overrides checked.
- **Seven text color pairs:** calculated contrast ratios ranged from **6.04:1 to 13.26:1**, exceeding 4.5:1 for those specific source pairs.

These PowerShell source checks do not verify rendered layouts, every computed color combination, standards-complete validity, or WCAG conformance.

### Practical testing checklist

- [ ] Open every page offline and confirm the shared stylesheet loads.
- [ ] Test all chapter links, cards, topic links, breadcrumbs, contents anchors, and previous/next links.
- [ ] Confirm the correct chapter is marked active on all six pages.
- [ ] Inspect at 320, 375, 768, 1024, and 1440px and intermediate widths. Check navigation wrapping, cards, definitions, and code panels.
- [ ] Verify no horizontal **page** overflow. Any long code should scroll inside its panel.
- [ ] Test a short desktop viewport; confirm the sticky sidebar can scroll to every link.
- [ ] Navigate by keyboard: use the skip link, inspect focus, open/close the topic index with Enter or Space, and scroll code panels.
- [ ] Test 200% and 400% zoom; confirm reflow and access to all content.
- [ ] Enable reduced motion and verify smooth scrolling/card transitions are disabled.
- [ ] Use a screen reader to check landmarks, headings, current-page announcements, and code labels.
- [ ] Measure contrast, including muted text and code captions: at least 4.5:1 for normal text, 3:1 for large text; inspect focus visibility too.
- [ ] Test Chrome/Edge, Firefox, and Safari where available; record versions and differences.
- [ ] Print-preview a chapter; inspect code wrapping and page breaks.
- [ ] Run full HTML validation for all six files and review CSS validation messages in context.
- [ ] Proofread technical content and check external reference destinations.
- [ ] Add real screenshots, the repository URL, and a live URL only after those exist.

### Technical sources

Primary references are linked beside relevant explanations and collected on the Resources page. They include [Fielding's REST chapter](https://ics.uci.edu/~fielding/pubs/dissertation/rest_arch_style.htm), [HTTP Semantics](https://www.rfc-editor.org/rfc/rfc9110.html), [PATCH](https://www.rfc-editor.org/rfc/rfc5789.html), [JSON](https://www.rfc-editor.org/rfc/rfc8259.html), [Bearer Token Usage](https://www.rfc-editor.org/rfc/rfc6750.html), [OAuth 2.0](https://www.rfc-editor.org/rfc/rfc6749.html), and [Problem Details](https://www.rfc-editor.org/rfc/rfc9457.html).

Naming, versioning, pagination shapes, and retry guidance are presented as design recommendations or illustrative contracts, rather than universal REST requirements.

## AI-Assisted Development

OpenAI Codex assisted with **planning, scaffolding, code generation, and review**, including multi-page organization, semantic HTML, shared CSS, responsive adjustments, reference research, and this README.

Do not present this implementation as independently written without assistance. Codex source checks are distinct from your own manual modifications and browser testing. No personal contributions, manual results, or learning achievements are assumed.

### Your editable development record

**What Codex generated**  
Initial six HTML chapters, shared CSS, project scaffold, explanatory content, README, and source checks. [Record later assisted changes.]

**What I manually modified**  
[Pending — describe your actual edits and why you made them.]

**What I tested**  
[Pending — record browser/version, viewport/device, date, method, and observed results.]

**What I learned**  
[Pending — write explanations you can apply independently.]

## Learning review

### Five important concepts to practice

1. **Information architecture:** Group a broad topic into linked chapters and keep navigation consistent.
2. **Semantic documentation:** Choose landmarks, headings, definitions, and code elements according to meaning.
3. **Responsive reading:** Combine bounded line length, fluid columns, sticky navigation, and local code scrolling.
4. **Accessible navigation:** Use native links, skip navigation, current-page markers, disclosures, and visible focus.
5. **Technical precision:** Distinguish architectural constraints, HTTP rules, and optional API conventions, while citing sources.

### Five technical interview questions and answers

**1. How does this multi-page site work without a router or JavaScript?**

Native anchors open sibling HTML files. A fragment identifier targets an element on the destination page. Every page loads the same relative stylesheet, and current-page state is explicit in its markup.

**2. Why use sticky positioning for the sidebar instead of fixed positioning?**

Sticky remains in normal document flow while staying near the viewport edge during scrolling. Fixed positioning would require more manual space management. Here the sidebar also has a bounded scroll area and becomes static on smaller screens.

**3. Why put examples in `pre` and `code`, and why make `pre` focusable?**

`pre` preserves whitespace and `code` identifies literal code. Horizontal overflow stays inside the panel. A focusable panel gives keyboard users a direct way to scroll long lines; its accessible label provides context.

**4. What is the difference between statelessness and not storing data?**

Stateless communication means each request contains the context needed for interpretation. A server may still store persistent resources. This distinction is explained in the guide using the original REST constraints.

**5. What is the main maintenance tradeoff of this no-build multi-page structure?**

The structure is simple and opens offline, but navigation markup is repeated. Renaming a chapter requires coordinated edits across pages. Link checks and explicit review help prevent drift without introducing a templating tool.

### Three future improvements

1. Refine layout and accessibility based on real browser, keyboard, and screen reader testing.
2. Add reviewed chapters on caching, conditional requests, or content negotiation while preserving the simple structure.
3. Add genuine screenshots and reviewed exercises, and keep technical references current.

## Screenshots

Screenshots are pending. These captions identify useful views to capture after testing:

- **Desktop overview:** sticky sidebar, reading path, and chapter cards.
- **Desktop examples:** captions and formatted HTTP/JSON blocks.
- **Tablet:** responsive navigation and reading width.
- **Mobile:** stacked chapters, definitions, and code panel scrolling.

Save images under `assets/images/`, then replace these placeholders with Markdown image links and useful alternative text. No placeholder image is presented as a tested screenshot.

## Manual GitHub publication

No Git commands, remote operations, repository creation, or deployment were performed for you.

### Create your repository

1. Sign in to GitHub and select **New repository**.
2. Choose `rest-api-documentation` or your own name, add a description, and choose visibility.
3. Create an empty repository without initializing a README, license, or `.gitignore`; these local files already exist.
4. Copy its HTTPS URL and verify your account and repository name.

### Run the commands yourself

Open PowerShell in this project folder, not the parent workspace. Replace the example remote with your actual repository URL before running that command.

```powershell
cd 'D:\SkillDevelopment\AI_Implementation_And_integration\HTML_CSS_Only\rest-api-documentation'
git init
git status
git add *.html css assets README.md .gitignore
git status
git commit -m "Build six-page HTML and CSS REST API guide"
git branch -M main
git remote add origin https://github.com/YOUR_USERNAME/rest-api-documentation.git
git remote -v
git push -u origin main
```

- **`git init`** creates local version history in this project. It does not create the GitHub repository.
- **`git status`** shows untracked, staged, and modified files; review the list before saving a commit.
- **`git add`** stages the HTML pages and listed project files. It does not upload them.
- **`git commit`** saves the staged snapshot locally. If prompted for author identity, configure your chosen name/email before retrying.
- **`git branch -M main`** names the current development branch `main`. Plain `git branch` lists local branches.
- **`git remote add origin ...`** records the GitHub URL under the name `origin`; **`git remote -v`** lets you verify it.
- **`git push -u origin main`** uploads commits and sets the upstream branch. Authenticate using GitHub's supported flow; do not put credentials in project files.

For later edits: review status, stage relevant files, commit with a useful message, and push. If the remote already contains differing commits, inspect the situation rather than force-pushing blindly.

Repository upload does not itself publish the rendered website. Hosting is a separate manual step. Add the live demo link only after publication and testing.

## Completion checkpoint

- [ ] I reviewed all six HTML pages and the shared CSS.
- [ ] I tested the site and recorded actual results.
- [ ] I understand the navigation, layout, and accessibility decisions.
- [ ] I uploaded this project to its own GitHub repository.

Confirm these steps once finished. Implementation is complete; personal verification and publication remain yours to record.
#   R E S T - f i e l d n o t e s  
 