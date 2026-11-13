# LIMS System Readiness

An interactive status site for the LIMS rollout. It shows the system landscape (LIMS Core with Data Platform, MES, SAP and Teamcenter), an overall traffic light, IT and business milestones, a detail page per system with open tasks, and the CP / IQC configuration status on the LIMS Core page.

It is one static file (`index.html`) with no build step and no server.

## Run it locally
Double-click `index.html` and it opens in your browser.

## Publish it with GitHub Pages
1. Create a new repository on GitHub (for example `lims-readiness`).
2. Upload `index.html`, `README.md` and `.nojekyll` (**Add file → Upload files**), then commit.
3. Go to **Settings → Pages**. Under **Build and deployment**, choose **Deploy from a branch**, then pick `main` and `/ (root)`. Click **Save**.
4. After a minute or so the site is live at `https://<your-user>.github.io/lims-readiness/`.

If your company uses GitHub Enterprise, Pages may need to be enabled by an admin, and the site can be restricted to people in your organisation.

## Update the status
1. Open the site and click **Edit** (top right).
2. Use the pencil and bin icons to change or remove tasks, milestones, systems and CP/IQC process steps. Use **+ Add** to create new ones. Target dates can be typed as a calendar week (CW).
3. Your changes save automatically, **but only in your own browser**.
4. To publish them for everyone, click **Download index.html** and upload that file to the repository, replacing the old one. GitHub Pages republishes it automatically.

Other buttons in edit mode:
- **Download data.json / Copy data**: a backup of the data only.
- **Import data**: load a `data.json` backup.
- **Discard local changes**: go back to what is published.

All data lives in the `<script id="lims-data">` block near the top of `index.html`, so you can also edit it directly on GitHub.

### Overall traffic light rules
- **Green**: every integration is completed and no task is overdue.
- **Amber**: any integration is still open, or any task is past its target date.
- **Red**: any system is marked "Delayed / At risk", or 3 or more tasks are overdue.

You can override the light by hand in edit mode (click the traffic light).
