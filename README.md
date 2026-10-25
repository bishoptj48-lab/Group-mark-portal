# GroupMark Student Results Portal

A lightweight, modern, client-side web portal where students can securely view their group project evaluations, contribution details, leader ratings, and final lecturer grades.

---

## 🚀 Features

- **Confidential & Secure**: Powered by zero-knowledge client-side SHA-256 cryptographic hashing (`gm:<REG_NUMBER>`). Student names and plain-text registration numbers are never stored in `results.json` or visible in network requests.
- **Official Result Slip**: Displays the student's group, project name, individual role, recorded tasks/contributions, peer leader mark, and lecturer final mark.
- **Print & PDF Support**: Click **Print / Save PDF** (`window.print()`) for a clean, formal academic transcript format suitable for printing or saving to PDF.
- **Fast Testing / Demo**: Built-in sample chips allow instant testing with demo student IDs.
- **Responsive & Dark Mode**: Seamlessly adapts to phones, tablets, and desktop displays with automatic and manual light/dark theme toggle.
- **Zero Dependencies**: Self-contained single-page application with no external frameworks or libraries required.

---

## 🌐 How to Host on GitHub Pages (Step-by-Step)

You can host this site 100% free on **GitHub Pages** in under 3 minutes.

### Method 1: GitHub Web Upload (Fastest — No Git Install Required)

1. **Sign in to GitHub**:
   - Go to [github.com](https://github.com) and log in to your account.
2. **Create a new repository**:
   - Click the **+** (plus icon) in the top-right corner &rarr; **New repository**.
   - Name it (for example: `groupmark-results` or `groupmark-portal`).
   - Set visibility to **Public** (required for free GitHub Pages).
   - Leave "Initialize with a README" unchecked.
   - Click **Create repository**.
3. **Upload the website files**:
   - On the new repository page, click the link that says **"uploading an existing file"**.
   - Drag and drop or browse to select all files from this folder:
     - `index.html`
     - `results.json`
     - `favicon.svg`
     - `.nojekyll`
     - `README.md`
   - Scroll down, write a commit message like `Initial commit: GroupMark website`, and click **Commit changes**.
4. **Enable GitHub Pages**:
   - In your repository, click **Settings** (tab at the top).
   - In the left sidebar, click **Pages** (under the "Code and automation" section).
   - Under **Build and deployment &rarr; Source**, choose **Deploy from a branch**.
   - Under **Branch**, select `main` (or `master`) and leave the folder as `/ (root)`.
   - Click **Save**.
5. **Visit your live site**:
   - Wait about 30–60 seconds.
   - Refresh the Pages settings tab; you will see a banner:
     > *"Your site is live at `https://<your-username>.github.io/<repo-name>/`"*
   - Click the link to open your live student portal!

---

### Method 2: Using Git CLI (Optional)

If you have Git installed, open PowerShell in this folder (`GroupMark-Website`) and run:

```powershell
git init
git branch -M main
git add .
git commit -m "Deploy GroupMark Student Results Portal"
git remote add origin https://github.com/<your-username>/<repo-name>.git
git push -u origin main
```

Then go to **Repository Settings &rarr; Pages &rarr; Branch: main &rarr; Save**.

---

## 🔄 How to Update Results Later

Whenever the lecturer updates marks in the GroupMark desktop app:

1. Open the **GroupMark** desktop application.
2. Go to the **Final marks** page (signed in as Lecturer).
3. Click **Publish results for website (results.json)**.
4. Save the file.
5. In your GitHub repository:
   - Click on `results.json`.
   - Click the pencil icon (Edit) or click **Add file &rarr; Upload files** and drag the new `results.json`.
   - Commit the change.
6. GitHub Pages will automatically refresh within 60 seconds!

---

## 🔐 Security Information

GroupMark hashes each student's normalized registration number using SHA-256 before generating `results.json`:

$$\text{Key} = \text{SHA256}(\text{"gm:"} + \text{REG\_NUMBER})$$

Because SHA-256 is a one-way cryptographic function, students cannot reverse other students' hashes or view names from the file. Only a student who already knows their exact registration number can unlock their personal statement.
