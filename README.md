# juliantay.org

The tabs are **About · CV · Writings · Projects**.

- **Writings** has two groups:
  - **Academic:** Papers (`_papers/`) and Publications & Research (`_data/research.yml`)
  - **Reflections:** Philoso-Journal (`writings/journal/_posts/`) and Film Critiques (`writings/films/_posts/`)
- **Projects** has two sub-sections:
  - Professional (one file per project in `_projects/`)
  - Personal (one file per project in `_projects/`, marked `section: personal`)
- **About** shows three "Latest" cards automatically: the newest journal entry, the newest paper, and the project marked `featured: true`.

GitHub Pages rebuilds the site automatically every time you save a change on github.com.

## Words you will see on GitHub

- **Repository ("repo"):** a folder on GitHub that holds all the site's files. Your site is one repository.
- **Commit:** GitHub's word for "save". Every save is recorded, so any mistake can be undone.
- **GitHub Pages:** GitHub's free hosting. It turns the files in your repository into the live website.

## Setting up (about 45 minutes, once)

### A. Create your GitHub account

1. Go to **github.com** and click **Sign up**.
2. Enter your email, a password, and a username. Your username is `juliantay555`.
3. Complete the puzzle and enter the code GitHub emails you.
4. If GitHub asks survey questions, skip them or choose the free plan. You do not need to pay for anything.
5. Recommended: turn on two-factor authentication (profile picture → Settings → Password and authentication).

### B. Create the repository

6. Click the **+** at the top right → **New repository**.
7. Under **Repository name**, type exactly `juliantay555.github.io`.
8. Choose **Public**, leave everything else as it is, and click **Create repository**.

### C. Upload the site

9. On your computer, double-click `juliantay.org.zip` to unzip it. This creates a folder called `juliantay.org`.
10. Back on the repository page, click the link **uploading an existing file**. It is in the line "Get started by creating a new file or uploading an existing file".
11. Open the `juliantay.org` folder, select everything inside it (Cmd+A on a Mac, Ctrl+A on Windows), and drag it all into the GitHub page.
    - Drag the **contents**, not the folder itself. If the site later shows a "404" page, this is usually the reason.
    - Use Chrome or Edge if possible; they upload folders most reliably.
12. Wait for the file list to finish loading, then click the green **Commit changes** button.
13. Check that the repository's main page lists `_config.yml`, `index.html`, `CNAME`, and folders such as `_layouts` and `writings` at the top level.

### D. Turn on GitHub Pages

14. In the repository, click **Settings** (top row), then **Pages** (left column).
15. Under **Build and deployment → Source**, choose **Deploy from a branch**. Under **Branch**, choose `main` and `/ (root)`, then click **Save**.
16. Wait about two minutes. Click the **Actions** tab: a green tick means the site was built, and a red cross means something went wrong (send Claude a screenshot). The site now works at `https://juliantay555.github.io`.
17. Back in **Settings → Pages**, under **Custom domain**, type `juliantay.org` and click **Save**. It may say the DNS check is in progress; that is expected until step E is done.

### E. Connect juliantay.org in Cloudflare

18. Log in at **dash.cloudflare.com** and click **juliantay.org**.
19. In the left menu, click **DNS → Records**.
20. If any A or CNAME records already exist for `@` or `www`, delete them.
21. Click **Add record** five times, once for each row below. For each record, click the orange cloud so it turns grey and reads **DNS only**, then click **Save**.

   | Type  | Name | IPv4 address / Target |
   |-------|------|------------------------|
   | A     | @    | 185.199.108.153        |
   | A     | @    | 185.199.109.153        |
   | A     | @    | 185.199.110.153        |
   | A     | @    | 185.199.111.153        |
   | CNAME | www  | juliantay555.github.io     |

22. Wait between ten minutes and a few hours, then return to GitHub → **Settings → Pages**. When it says "DNS check successful", tick **Enforce HTTPS**. If the box is greyed out, wait a little longer; GitHub is still issuing the security certificate.
23. Visit **https://juliantay.org**. The site is live.

### F. Protect the domain (5 minutes)

24. On GitHub, click your profile picture → **Settings → Pages → Add a domain**, and enter `juliantay.org`.
25. GitHub shows a TXT record. Add it in Cloudflare (DNS → Records → Add record, type TXT), then click **Verify** on GitHub. This stops anyone else from using your domain on GitHub.
26. In Cloudflare, go to **Domain Registration → Manage domains** and make sure **auto-renew** is on.

## Posting the weekly journal entry (about 2 minutes)

1. Open your repository on github.com and click **Add file → Create new file**.
2. In the file name box, type:
   `writings/journal/_posts/2026-10-04-short-name.md`
   Use that week's date (`YEAR-MONTH-DAY`), then a short name in lower case with hyphens instead of spaces.
3. Paste this and write the entry underneath:

   ```
   ---
   title: "Title of this week's entry"
   ---

   First paragraph.

   Second paragraph. Leave an empty line between paragraphs.
   ```

4. Click **Commit changes**.

Within about two minutes, the entry appears in the Philoso-Journal under its month. It also appears on the About page as the latest card. Entry numbers (No. 1, No. 2 and so on) are assigned automatically in date order, so do not type them.

Notes:

- **Future dates:** entries dated in the future do not appear until that day (Singapore time).
- **Fixing a typo:** open the file, click the pencil icon, edit, and commit.
- **Formatting:** `*italics*` and `**bold**`.

## Posting a film critique

Film critiques work the same way as journal entries, but the file goes in `writings/films/_posts/`, for example `writings/films/_posts/2026-10-06-perfect-days.md`. You can add a line naming the film, which appears under the title:

```
---
title: "Title of your critique"
film: "Perfect Days (2023), dir. Wim Wenders"
---

Your critique here.
```

## Personal projects (for example, the ant colonies)

Personal projects are cards, like professional ones. Each is a file in `_projects/` with `section: personal`, for example `_projects/messor-structor.md`. To add one, copy that file and change the lines between the `---` markers.

To add photos to a project:

1. Upload each image into `assets/photos/` (open `assets`, then **Add file → Upload files**; to create the `photos` folder the first time, start a new file named `assets/photos/placeholder.txt`).
2. In the project file, put this on its own line where the photo should appear:
   `![Short description of the photo](/assets/photos/file-name.jpg)`

Photos straight from a phone are large. Keeping each one under about 1 MB makes pages load faster.

## Papers

Each paper is its own file in `_papers/`. For example, `_papers/ants-in-the-heat-of-survival.md` looks like this:

```
---
title: "Ants in the Heat of Survival"
date: 2025-02-25
topic: Ecology & Environmental Ethics
---

The paper's text goes here, one blank line between paragraphs.

A sentence with a footnote.[^1]

[^1]: The footnote text, for example a Chicago-style citation.
```

- **Footnotes:** a footnote marker `[^1]` in the text links to its note `[^1]:`. The notes can sit anywhere below the text; the site numbers them in order and lists them at the end of the paper, with links back.
- **Titles on the Papers page** become links as soon as a paper file contains text. Papers with no text yet are listed without a link.
- **Adding a paper:** create a new file in `_papers/` with the same three lines at the top. The `topic` must match one of the headings in `_data/paper-topics.yml`.
- **Course details, prompts and works:** the lines at the top of a paper file can also hold `course:`, `instructor:`, `coauthor:`, a `prompt:` (shown in a shaded box above the essay) and a `works:` list (shown as "Works discussed"). The art history papers show how these are written.
- **Converting from Word or Google Docs** by hand is slow because of the footnotes. The simplest route is to send the .docx files to Claude, which converts them, footnotes included.

## Adding a professional project

Copy an existing file in `_projects/`. Then change these lines between the `---` markers:

- `title`
- `order`: its position on the page, where 1 is first
- `with`
- `period`
- `status`
- `summary`: one sentence

Keep `section: professional`. To feature a different project on the About page, move `featured: true` to that project's file. Only one project should have it.

## Other edits

- **Tabs:** edit the `nav:` list in `_config.yml`.
- **Renaming "Reflections":** edit the word in `writings/index.html`.
- **Back and forward buttons:** the two arrows beside your name step through pages visited on the site, like the browser's own arrows. They are defined at the bottom of `_layouts/default.html`.
- **Colours and fonts:** edit the top of `assets/style.css`.
- **Undoing a mistake:** every commit is saved, so an earlier version can always be restored. Ask Claude how.
