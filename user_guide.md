# Interactive Project Hub Deployment & Maintenance Guide

This guide ensures you can deploy your interactive dashboard using GitHub Pages and maintain all content using a simple, text-based Markdown workflow.

---

## 1. Initial Deployment to GitHub Pages

This process assumes you have Git installed and a GitHub account.

### Step 1: Create the Local Repository and File Structure

**Create a Folder:**  
Create a local folder for your project (e.g., `~/Projects/ResearchHub`).

**Initialize Git:**  
Open your terminal, navigate to the folder, and initialize Git:

```bash
git init
```

**Create Subdirectories:**

```bash
mkdir projects
mkdir logs
```

**Add the HTML Dashboard File:**  
Create a file named `index.html` in the root of your `ResearchHub` folder.  
Paste the entire code from the Canvas document (**GitHub Dashboard Preview**) into this `index.html` file.

> **Note:** Renaming it to `index.html` is critical, as GitHub Pages uses this name as the entry point.

**Add Markdown Content Files:**  
Create the Markdown files in their respective folders using the templates provided in *project_hub_templates.md*.

---

### Step 2: Commit and Push to GitHub

**Create a Private GitHub Repository:**  
Log in to GitHub and create a new private repository (e.g., `research-hub`).

**Connect and Commit:**  
Connect your local folder to the remote repository, stage all files, and push them.

```bash
# Replace YOUR_USERNAME and research-hub
git remote add origin https://github.com/YOUR_USERNAME/research-hub.git
git add .
git commit -m "Initial Interactive Hub deployment"
git push -u origin main
```

---

### Step 3: Enable GitHub Pages

1. Go to **Settings** on your GitHub repository page.  
2. In the left sidebar, click **Pages**.  
3. Configure:

   - **Source:** Deploy from a branch  
   - **Branch:** `main` (or `master`)  
   - **Folder:** `/` (root)

4. Click **Save**.

Wait a few minutes; your live dashboard will be accessible at:

```
https://YOUR_USERNAME.github.io/research-hub/
```

---

## 2. Content-Only Maintenance Workflow

**Core principle:**  
**Never edit `index.html` unless changing the visual design.**  
All content updates happen in Markdown files.

---

### A. Moving Projects in the Pipeline

**File to Edit:** `README.md`

1. **Locate the Card:**  
   Find the project card under its current stage (e.g., `## IDEA`).

2. **Cut & Paste:**  
   Cut the entire card line (starts with `- Card:`) and paste it under the new stage header (e.g., `## PREPARATION`).

3. **Update Status:**  
   Change the `Status:` value accordingly.

**Example Card Format (do not change structure):**

```
- Card: Project Name | Lead: X | Start: YYYY-MM-DD | Status: New Status | Link: projects/projectA.md
```

---

### B. Adding Daily Progress

**File to Edit:** `logs/daily-log.md`

The dashboard shows the **top 5 days**, so always add new entries to the top.

**Add New Entry Structure:**

```md
## YYYY-MM-DD (Day)
| Project | Task/Update | Time Spent | Next Steps |
| :--- | :--- | :--- | :--- |
| Project X (Stage) | [What was done] | [Time] | [What to do next] |
```

---

### C. Updating Project Details and Log

**File to Edit:** `projects/yourproject.md`

**Update Running Log:**

```md
## LOG
* YYYY-MM-DD: New key event or progress note.
* YYYY-MM-DD: Older note...
```

**Update Metadata:**  
Under `## METADATA`, edit the value fields (e.g., stage, Overleaf link, collaborators, etc.).

---

### D. Archiving a Finished Project

**File to Edit:** `README.md`

1. Cut the project card line from its pipeline stage (e.g., `## PUBLICATION`).
2. Paste it under the `## ARCHIVE` section.
3. Add an **End date** field.

**Archive Format Example:**

```md
## ARCHIVE
- Card: Project Name | Lead: X | Start: YYYY-MM-DD | End: YYYY-MM-DD | Link: projects/archive_finished.md
```

---

### E. Syncing All Changes

After editing any Markdown file locally, push the updates:

```bash
git add .
git commit -m "Content Update: Daily log and project status changes"
git push
```

Your live dashboard will update shortly after the push.
