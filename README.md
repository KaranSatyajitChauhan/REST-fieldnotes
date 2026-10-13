<div align="center">

# REST FIELDNOTES

### `> A Developer's Guide to RESTful APIs_`

**HTTP • REST Architecture • API Security • Technical Documentation**

<br>

![HTML](https://img.shields.io/badge/HTML5-E34F26?style=flat-square&logo=html5&logoColor=white)
![CSS](https://img.shields.io/badge/CSS3-1572B6?style=flat-square&logo=css&logoColor=white)
![Documentation](https://img.shields.io/badge/TYPE-TECHNICAL_DOCUMENTATION-181717?style=flat-square)
![AI Assisted](https://img.shields.io/badge/DEVELOPMENT-AI_ASSISTED-00875A?style=flat-square)
![Status](https://img.shields.io/badge/STATUS-IMPLEMENTED-2EA44F?style=flat-square)

<br>

**A six-chapter technical documentation website built entirely with HTML5 and CSS3.**

[Explore Documentation](index.html) •
[HTTP Examples](examples-resources.html) •
[View Stylesheet](css/style.css)

---

</div>

## `01 / PROJECT OVERVIEW`

REST Fieldnotes is a structured, multi-page technical documentation website designed to explain the fundamental concepts of RESTful API development.

The project combines **technical writing, frontend engineering, and API architecture knowledge** into a responsive documentation interface.

Unlike a traditional landing page, REST Fieldnotes prioritizes:

- Clear technical explanations
- Structured information architecture
- Developer-friendly navigation
- Readable HTTP and JSON examples
- Accessible documentation components
- Maintainable frontend implementation

> [!IMPORTANT]
> **Project Classification:** Academic Portfolio Project
>
> REST Fieldnotes is a static educational website. It explains REST API concepts but does not implement a functioning API, backend service, or database.

---

## `02 / HTTP REQUEST PREVIEW`

The following example illustrates the kind of HTTP communication explained throughout the documentation.

### Request

```http
GET /api/v1/projects HTTP/1.1
Host: api.example.com
Accept: application/json
```

### Response

```http
HTTP/1.1 200 OK
Content-Type: application/json
```

```json
{
  "success": true,
  "data": [
    {
      "id": 101,
      "name": "REST Fieldnotes",
      "type": "Documentation",
      "status": "Example"
    }
  ]
}
```

**Response interpretation**

| Component | Meaning |
|:----------|:--------|
| `GET` | Requests a resource representation |
| `/api/v1/projects` | Illustrative resource endpoint |
| `200 OK` | Successful HTTP request |
| `application/json` | JSON representation |
| `data` | Example response payload |

> These examples are illustrative and are not executed by this website.

---

## `03 / TECHNOLOGY PROFILE`

```text
┌───────────────────────────────────────────────────────┐
│                                                       │
│                 TECHNOLOGY STACK                      │
│                                                       │
├───────────────────────────────────────────────────────┤
│                                                       │
│  MARKUP          HTML5                                │
│  STYLING         CSS3                                 │
│  LAYOUT          CSS Grid / Flexbox                   │
│  RESPONSIVENESS  CSS Media Queries                    │
│  DESIGN SYSTEM   CSS Custom Properties                │
│  INTERACTION     Native HTML Elements                 │
│  DOCUMENTATION   HTTP / JSON Examples                 │
│  AI ASSISTANCE   OpenAI Codex                         │
│                                                       │
├───────────────────────────────────────────────────────┤
│                                                       │
│  JavaScript      NOT REQUIRED                         │
│  Framework       NONE                                 │
│  Backend         NONE                                 │
│  Database        NONE                                 │
│  Dependencies    NONE                                 │
│                                                       │
└───────────────────────────────────────────────────────┘
```

### Engineering Decisions

| Decision | Reason |
|:---------|:-------|
| Semantic HTML5 | Clear document structure and accessibility |
| Shared CSS stylesheet | Consistent styling across all chapters |
| Native navigation | No client-side router required |
| CSS Grid | Structured documentation layouts |
| Flexbox | Flexible navigation and component alignment |
| CSS variables | Centralized design configuration |
| Native `<details>` | Expandable navigation without JavaScript |
| Static HTML pages | Lightweight deployment and maintenance |

---

## `04 / DOCUMENTATION ROADMAP`

The documentation is organized into six interconnected chapters.

```text
REST FIELDNOTES
│
├── 01  OVERVIEW
│       └── Introduction and learning objectives
│
├── 02  HTTP & REST
│       ├── HTTP fundamentals
│       ├── Client-server architecture
│       ├── REST architectural principles
│       └── Stateless communication
│
├── 03  METHODS & STATUS CODES
│       ├── GET / POST / PUT
│       ├── PATCH / DELETE
│       ├── HTTP status codes
│       └── Safety and idempotency
│
├── 04  REQUESTS & RESPONSES
│       ├── HTTP message structure
│       ├── Request headers
│       ├── Response headers
│       └── JSON representations
│
├── 05  SECURITY & API DESIGN
│       ├── Authentication
│       ├── Authorization
│       ├── API versioning
│       ├── Error handling
│       ├── Pagination
│       └── Rate limiting
│
└── 06  EXAMPLES & RESOURCES
        ├── HTTP request examples
        ├── JSON response examples
        ├── API error examples
        └── Technical references
```

### Chapter Navigation

| Chapter | Documentation | Source |
|:-------:|:--------------|:-------|
| `01` | Overview | [index.html](index.html) |
| `02` | HTTP & REST | [http-rest.html](http-rest.html) |
| `03` | Methods & Status Codes | [methods-status.html](methods-status.html) |
| `04` | Requests & Responses | [requests-responses.html](requests-responses.html) |
| `05` | Security & API Design | [security-design.html](security-design.html) |
| `06` | Examples & Resources | [examples-resources.html](examples-resources.html) |

---

## `05 / SYSTEM ARCHITECTURE`

### Multi-Page Documentation Architecture

```text
                      USER / BROWSER
                            │
                            ▼
                  ┌───────────────────┐
                  │    index.html     │
                  │   Entry Point     │
                  └───────────────────┘
                            │
                            ▼
                  ┌───────────────────┐
                  │   Navigation      │
                  │   HTML Anchors    │
                  └───────────────────┘
                            │
             ┌──────────────┼──────────────┐
             │              │              │
             ▼              ▼              ▼
       HTTP & REST       METHODS        SECURITY
             │              │              │
             └──────────────┼──────────────┘
                            │
                            ▼
                  ┌───────────────────┐
                  │ Shared Stylesheet │
                  │   css/style.css   │
                  └───────────────────┘
```

### Architecture Characteristics

**Separation of Concerns**

HTML defines document structure and content, while CSS manages presentation and responsive behavior.

**Shared Styling**

A single stylesheet provides a consistent visual system across six documentation pages.

**Native Navigation**

The browser handles page transitions and fragment navigation using standard HTML anchors.

**Static Delivery**

The website does not require server-side rendering, JavaScript execution, or API communication.

---

## `06 / REPOSITORY STRUCTURE`

```text
rest-api-documentation/
│
├── index.html
│
├── http-rest.html
│
├── methods-status.html
│
├── requests-responses.html
│
├── security-design.html
│
├── examples-resources.html
│
├── css/
│   └── style.css
│
├── assets/
│   └── images/
│       └── .gitkeep
│
├── README.md
│
└── .gitignore
```

### File Responsibilities

| File | Responsibility |
|:-----|:---------------|
| `index.html` | Documentation entry point |
| `http-rest.html` | HTTP and REST concepts |
| `methods-status.html` | Methods and response codes |
| `requests-responses.html` | HTTP message structures |
| `security-design.html` | API security and design |
| `examples-resources.html` | Examples and references |
| `css/style.css` | Shared visual design system |
| `README.md` | Project documentation |

---

## `07 / INTERFACE ENGINEERING`

### Documentation Layout

The website uses a documentation-focused interface with:

- A desktop sticky sidebar
- Chapter-based navigation
- Responsive content sections
- Numbered documentation chapters
- Readable technical typography
- Dark code example panels
- Previous/next chapter navigation

### Responsive Behavior

| Viewport | Layout Behavior |
|:---------|:----------------|
| Desktop | Sidebar and main content |
| Tablet | Responsive navigation and reading area |
| Mobile | Stacked navigation and content |
| Print | Simplified documentation presentation |

### CSS Techniques

The implementation uses:

```css
/* Representative layout concepts */

display: grid;

display: flex;

grid-template-columns: minmax(0, 1fr);

position: sticky;

font-size: clamp(1rem, 2vw, 1.5rem);
```

These examples illustrate CSS techniques used in the project rather than reproducing its complete stylesheet.

---

## `08 / ACCESSIBILITY`

The documentation interface incorporates accessibility-oriented design practices.

| Feature | Implementation |
|:--------|:---------------|
| Semantic landmarks | Header, navigation, main, footer |
| Heading hierarchy | Structured chapter headings |
| Keyboard navigation | Native links and focus states |
| Skip navigation | Direct access to main content |
| Current-page indicator | `aria-current="page"` |
| Expandable navigation | Native `<details>` and `<summary>` |
| Code readability | Scrollable, focusable code panels |
| Reduced motion | CSS media preference support |
| Print accessibility | Print-specific layout rules |

> [!NOTE]
> The project aims toward WCAG 2.2 AA principles. Complete accessibility conformance has not been independently verified.

---

## `09 / LOCAL DEVELOPMENT`

### Requirements

```text
Required:
  - Modern web browser
  - Text editor

Optional:
  - Visual Studio Code
  - Git

Not required:
  - Node.js
  - npm
  - JavaScript framework
  - Local development server
```

### Clone Repository

After publishing the project to GitHub:

```bash
git clone https://github.com/YOUR_USERNAME/rest-api-documentation.git
```

### Open Project

```bash
cd rest-api-documentation
```

### Launch

Open:

```text
index.html
```

in your preferred browser.

**No dependency installation or build process is required.**

---

## `10 / DEVELOPMENT & VALIDATION`

### Source-Level Review

The original development documentation records the following Codex-assisted source checks.

| Verification | Recorded Result |
|:-------------|:----------------|
| Six HTML pages inspected | Passed |
| Unique element IDs | Passed |
| Internal navigation references | Passed |
| 189 local links and anchors | Resolved |
| Five JSON example bodies | Parsed |
| CSS brace consistency | Passed |
| Focus and reduced-motion rules | Present |
| Script and dependency checks | No scripts or imports |
| Selected text contrast pairs | 6.04:1–13.26:1 |

These are recorded source-check results, not independently repeated browser tests.

### Manual Testing Checklist

- [ ] Open all six HTML pages
- [ ] Verify chapter navigation
- [ ] Test internal anchor links
- [ ] Verify active-page indicators
- [ ] Test mobile responsiveness
- [ ] Test tablet responsiveness
- [ ] Inspect desktop layouts
- [ ] Verify code block scrolling
- [ ] Test keyboard navigation
- [ ] Test expandable topic navigation
- [ ] Check browser compatibility
- [ ] Validate HTML and CSS
- [ ] Review accessibility behavior
- [ ] Test print layouts

**Current status:** Manual browser and assistive-technology testing pending.

---

## `11 / AI-ASSISTED ENGINEERING`

### Development Workflow

```text
PROJECT REQUIREMENTS
        │
        ▼
AI-ASSISTED PLANNING
        │
        ▼
HTML PAGE STRUCTURE
        │
        ▼
SHARED CSS ARCHITECTURE
        │
        ▼
RESPONSIVE IMPLEMENTATION
        │
        ▼
SOURCE-LEVEL REVIEW
        │
        ▼
PERSONAL REVIEW & TESTING
        │
        ▼
GITHUB PUBLICATION
```

The first five implementation stages were supported by OpenAI Codex. Personal review, manual browser testing, and publication remain to be completed or documented.

### AI Integration

**OpenAI Codex** assisted with:

- Requirements interpretation
- Project architecture
- Multi-page HTML scaffolding
- Semantic markup
- CSS implementation
- Responsive layout development
- Accessibility considerations
- Technical content organization
- Source-level validation
- README documentation

### Engineering Responsibility

AI-assisted development is used to support implementation efficiency and technical exploration.

Generated code should be reviewed, understood, and tested before being treated as production-ready.

### Personal Development Record

| Activity | Status |
|:---------|:-------|
| AI-assisted planning | Completed |
| HTML/CSS generation | Completed |
| Source-level checks | Completed |
| Manual code modifications | To be documented |
| Browser testing | Pending |
| GitHub publication | Pending |

---

## `12 / TECHNICAL KNOWLEDGE`

This project brings together two areas of software engineering.

### Frontend Engineering

```text
HTML5
 ├── Semantic Structure
 ├── Multi-Page Navigation
 ├── Accessibility
 └── Technical Content Organization

CSS3
 ├── Grid Layouts
 ├── Flexbox
 ├── Responsive Design
 ├── Design Tokens
 └── Print Styling
```

### Backend & API Fundamentals

```text
REST API CONCEPTS
 ├── HTTP Communication
 ├── Client-Server Architecture
 ├── Stateless Requests
 ├── Resource-Oriented Design
 ├── HTTP Methods
 ├── Status Codes
 ├── JSON Representations
 ├── Authentication
 ├── Authorization
 ├── Error Handling
 ├── Pagination
 └── Rate Limiting
```

These topics are documented and illustrated rather than implemented as a functioning backend.

---

## `13 / TECHNICAL REFERENCES`

The guide draws on established specifications and primary technical resources.

| Resource | Subject |
|:---------|:--------|
| [REST Architectural Style](https://ics.uci.edu/~fielding/pubs/dissertation/rest_arch_style.htm) | REST constraints |
| [RFC 9110](https://www.rfc-editor.org/rfc/rfc9110.html) | HTTP Semantics |
| [RFC 5789](https://www.rfc-editor.org/rfc/rfc5789.html) | HTTP PATCH |
| [RFC 8259](https://www.rfc-editor.org/rfc/rfc8259.html) | JSON |
| [RFC 6750](https://www.rfc-editor.org/rfc/rfc6750.html) | Bearer Token Usage |
| [RFC 6749](https://www.rfc-editor.org/rfc/rfc6749.html) | OAuth 2.0 |
| [RFC 9457](https://www.rfc-editor.org/rfc/rfc9457.html) | HTTP API Problem Details |

---

## `14 / PROJECT PREVIEW`

Screenshots will be added after manual testing.

| Preview | Status |
|:--------|:-------|
| Desktop Overview | Pending |
| Documentation Sidebar | Pending |
| HTTP/JSON Examples | Pending |
| Tablet Layout | Pending |
| Mobile Layout | Pending |

Future screenshots will be stored in:

```text
assets/images/
```

---

## `15 / FUTURE DEVELOPMENT`

Planned improvements may include:

- Refining responsive layouts after testing
- Improving accessibility based on validation results
- Adding technical diagrams
- Expanding HTTP caching documentation
- Adding conditional request examples
- Introducing content negotiation explanations
- Improving technical exercises
- Adding real screenshots

The project will continue to prioritize readable documentation and lightweight frontend architecture.

---

## `16 / DEVELOPER`

```text
┌────────────────────────────────────────────────────┐
│                                                    │
│  DEVELOPER PROFILE                                 │
│                                                    │
│  Name       Karan Satyajit Chauhan                 │
│  Role       Full-Stack Developer                   │
│                                                    │
│  Focus Areas                                       │
│  ──────────────────────────────────────────────    │
│                                                    │
│  > Software Engineering                            │
│  > Backend Development                             │
│  > REST API Architecture                           │
│  > Enterprise Applications                         │
│  > Frontend Engineering                            │
│  > AI-Assisted Development                         │
│                                                    │
└────────────────────────────────────────────────────┘
```

**Technical Interests**

`Java` · `JavaScript` · `React` · `Node.js` · `Express.js` · `REST APIs` · `SQL` · `MongoDB`

---

## `17 / PROJECT STATUS`

| Milestone | Status |
|:----------|:-------|
| Project planning | Complete |
| Six documentation chapters | Implemented |
| Shared CSS architecture | Implemented |
| Responsive CSS rules | Implemented |
| Technical examples | Implemented |
| Initial source review | Complete |
| Manual browser verification | Pending |
| GitHub repository publication | Pending |
| Live deployment | Pending |

---

<div align="center">

### `END OF DOCUMENTATION`

---

**REST FIELDNOTES**

*Understand the protocol. Design the interface. Document the architecture.*

**HTML5 + CSS3 | REST API Fundamentals | AI-Assisted Development**

Developed by **Karan Satyajit Chauhan**

</div>