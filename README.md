# JavaScript Developer Portfolio

A personal portfolio built with **HTML, CSS and plain JavaScript**, based on [Digital Innovation One's portfolio project](https://github.com/digitalinnovationone/js-developer-portfolio). Profile information is loaded from JSON and rendered into expandable sections for skills, languages, projects and experience.

## Start here

For a broader view of my work, visit [my GitHub profile](https://github.com/helberjf). Selected project repositories:

- [AWS Serverless Orders](https://github.com/helberjf/aws-serverless-orders)
- [E-commerce Platform Case Study](https://github.com/helberjf/ecommerce-platform-casestudy)
- [Logs Microservices](https://github.com/helberjf/logs-microservices)
- [Tutor Professor](https://github.com/helberjf/tutor-professor)

This repository demonstrates the portfolio site's rendering and layout. The linked repositories provide their own implementation details and current status.

## Run locally

Serve the repository with any static web server. For example, with Python installed:

```bash
python -m http.server 8000
```

Open `http://localhost:8000`. No package installation or build step is required.

**Data source:** [api.js](assets/js/api.js) currently fetches `data/profile.json` from this repository's **remote `main` branch on raw.githubusercontent.com**. Editing the local JSON does not change the displayed data until that data is published or the fetch URL is adjusted for local development. Internet access is required with the current configuration.

## Code tour

1. [index.html](index.html) defines the page and section structure.
2. [profile.json](data/profile.json) stores the profile content and project entries.
3. [api.js](assets/js/api.js) fetches the JSON; [main.js](assets/js/main.js) maps it into the DOM.
4. [acordeon.js](assets/js/acordeon.js) toggles the expandable sections.
5. [CSS files](assets/css) separate the header, skills, projects, experience and other visual sections.

## Implementation tradeoffs

| Choice | Benefit | Cost or boundary |
| --- | --- | --- |
| Separate content into JSON | Profile updates do not require rewriting each HTML section | The current remote URL couples local previews to the published branch and network availability. |
| Use plain DOM rendering | Keeps deployment simple and avoids a frontend build toolchain | Rendering and error states are managed manually; the current fetch flow does not provide a dedicated failure UI. |
| Build repeated content with HTML strings | Makes small authored lists concise to render | Content must remain trusted; arbitrary external content would require safe rendering and validation. |
| Organize information in expandable sections | Keeps a long profile compact | Discoverability and keyboard/screen-reader behavior need deliberate review. |

These are observable implementation tradeoffs rather than recorded historical decisions.

## Verification and next improvements

There is no automated test suite. A useful manual pass checks JSON loading, all section toggles, mobile layout, image paths and outgoing project links. Next improvements include a local data option, visible loading/error states, safer text rendering and accessibility checks for the expandable controls.

## Attribution

Based on **Digital Innovation One's `js-developer-portfolio`** learning project. The original portfolio also credits [Renan J. Paula's course repository](https://github.com/RenanJPaula/js-developer-portfolio). This version retains the course structure and DIO visual attribution while using personal portfolio content.
