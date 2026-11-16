# Morrowlane Resource Hub

A simple internal website where Morrowlane employees find approved, current documents in one place.

- **Owner:** Regional Operations (reviewed quarterly)
- **Pages:** `index.html` (Home), `operations.html` (Operations Resources), `client.html` (Client Resources)
- **Styles:** `styles.css` (shared by all three pages)
- **Documents:** the `files/` folder
- **Hosting:** Netlify, published straight from this GitHub repository. There is no build step: whatever is in the repository is what goes live.

## Before you change anything

Never add any of these to this site:

- Real client names, logos, site addresses, floor plans or access codes
- Real contracts, pricing or vendor rates
- Employee personal data, passwords or credentials

Only add documents that Regional Operations has approved.

## Replace a document with a newer version

Use this when the document is the same, only updated.

1. Give the new file **exactly the same name** as the old one (for example `site-visit-checklist.pdf`).
2. Put it in the `files/` folder, replacing the old file.
3. Update the **Last updated** date everywhere the document appears (see "Where each document appears" below). Each date appears in two forms, and both must change:

   ```html
   <time datetime="2026-11-15">Nov 15, 2026</time>
   ```

   - `datetime="YYYY-MM-DD"`: the date as numbers, for browsers and screen readers.
   - The text between the tags: the date people see, written like `Nov 15, 2026`.

4. If the file size changed, update the size too (for example `6 KB`). To find the size, right-click the file, choose **Properties** (Windows) or **Get Info** (Mac), and round to the nearest KB.
5. If this is now one of the most recently updated documents, update the **Recently updated** list on `index.html` (see below).
6. Commit and push to GitHub. Netlify publishes the change within a minute or two.

## Add a new document

1. Name the file in lowercase with hyphens between the words and no spaces (for example `vendor-onboarding-guide.pdf`).
2. Put it in the `files/` folder.
3. Open `operations.html` or `client.html`, depending on who the document is for.
4. Copy one whole existing card, from `<li class="card">` to its matching `</li>`, and paste it below the last card.
5. In the copied card, change:
   - the document name in the `<h2>`
   - the file type (`PDF` or `DOCX`) and size
   - the "Use this when..." sentence (keep it to one sentence)
   - both forms of the Last updated date
   - the button's `href` (for example `files/vendor-onboarding-guide.pdf`)
   - the button text. It must include the document name, for example `Open Vendor Onboarding Guide (PDF, 7 KB)`. For Word files use `Download ...` and keep the word `download` in the link, as on the Client Update Template card.
6. Open `index.html` and add a link to the new document in the matching card on Home, so every document stays one click from Home.
7. If it belongs in **Recently updated**, update that list too (see below).
8. Commit and push to GitHub.

Adding a new page, file type or feature? Check with Regional Operations first: the hub is kept to three pages on purpose.

## Remove a document

1. Delete its card from `operations.html` or `client.html`.
2. Delete its link from `index.html`, both in the card on Home and in **Recently updated** if it is listed there.
3. Delete the file from `files/`.
4. Commit and push to GitHub.

## Update the "Recently updated" list on Home

In `index.html`, find the section headed **Recently updated**. It lists the 3 most recently updated documents, newest first. Each entry looks like this:

```html
<li>
  <a href="files/site-visit-checklist.pdf">Site Visit Checklist (PDF, 6 KB)</a>
  <span class="meta">Updated <time datetime="2026-11-15">Nov 15, 2026</time></span>
</li>
```

Swap entries in or out so it always shows exactly 3, and keep the dates matching the document cards.

## Where each document appears

| Document | File | Card on | Also linked on Home |
| --- | --- | --- | --- |
| Site Visit Checklist | `files/site-visit-checklist.pdf` | `operations.html` | Operations card, Recently updated |
| Workplace Setup Guide | `files/workplace-setup-guide.pdf` | `operations.html` | Operations card |
| Client Update Template | `files/client-update-template.docx` | `client.html` | Client card, Recently updated |
| Service Overview Deck | `files/service-overview-deck.pdf` | `client.html` | Client card, Recently updated |
| Office Move Planning Checklist | `files/office-move-planning-checklist.pdf` | `client.html` | Client card |

## Check your change

Open `index.html` in a web browser straight from your computer. Then click through to each page and each document, and make sure every link opens the right file.

## Deploying on Netlify

- Connect this GitHub repository to Netlify.
- Build command: leave empty.
- Publish directory: the repository root (leave empty or use `.`).

Every push to the main branch then publishes automatically.
