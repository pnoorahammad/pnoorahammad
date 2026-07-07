# Upload Guide — GitHub Profile README

This guide walks you through uploading your profile README to GitHub so it appears on your profile page.

---

## Step 1: Create the Profile Repository

1. Go to [github.com/new](https://github.com/new)
2. **Repository name:** Enter your exact GitHub username — `pnoorahammad`
3. **Visibility:** Set to **Public**
4. **Initialize:** Check "Add a README file" (you'll replace it)
5. Click **Create repository**

> **Important:** The repository name MUST exactly match your GitHub username (`pnoorahammad`). This is how GitHub knows to display it on your profile.

---

## Step 2: Upload Files

### Option A: Using Git (Recommended)

```bash
# Clone the repository
git clone https://github.com/pnoorahammad/pnoorahammad.git
cd pnoorahammad

# Copy all files from this project into the cloned repo
# (README.md, assets/, LICENSE, CONTRIBUTING.md)

# Stage, commit, and push
git add .
git commit -m "feat: add enterprise-quality GitHub profile README"
git push origin main
```

### Option B: Using GitHub Web Interface

1. Go to `https://github.com/pnoorahammad/pnoorahammad`
2. Click **Add file** → **Upload files**
3. Drag and drop:
   - `README.md`
   - `assets/` folder (with `banner.png`)
   - `LICENSE`
   - `CONTRIBUTING.md`
4. Add commit message: `feat: add enterprise-quality GitHub profile README`
5. Click **Commit changes**

---

## Step 3: Enable the Snake Animation (Optional)

The contribution snake animation requires a GitHub Actions workflow.

1. In your `pnoorahammad` repository, create the file:
   ```
   .github/workflows/snake.yml
   ```

2. Paste this content:

```yaml
name: Generate Snake Animation

on:
  schedule:
    - cron: "0 */12 * * *"  # Runs every 12 hours
  workflow_dispatch:

jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - name: Generate Snake Game
        uses: Platane/snk/svg-only@v3
        with:
          github_user_name: pnoorahammad
          outputs: |
            dist/github-snake.svg
            dist/github-snake-dark.svg?palette=github-dark

      - name: Push to output branch
        uses: crazy-max/ghaction-github-pages@v3.1.0
        with:
          target_branch: output
          build_dir: dist
        env:
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
```

3. Go to **Actions** tab in your repository
4. Find "Generate Snake Animation" and click **Run workflow**
5. Wait for completion — the snake SVG will be generated automatically

---

## Step 4: Verify Your Profile

1. Visit `https://github.com/pnoorahammad`
2. Your README should now display on your profile page
3. Check that:
   - ✅ Banner image loads correctly
   - ✅ Typing SVG animation works
   - ✅ All badges render properly
   - ✅ GitHub Stats cards load
   - ✅ Streak stats display
   - ✅ Activity graph renders
   - ✅ Trophies show up
   - ✅ All links work correctly
   - ✅ Snake animation plays (after workflow runs)

---

## Step 5: Customize (Optional)

### Update Project Links
If any repository names differ from what's in the README, update the links:
```
https://github.com/pnoorahammad/YOUR-REPO-NAME
```

### Replace the Banner
To use a custom banner:
1. Replace `assets/banner.png` with your own image
2. Recommended dimensions: **1500 × 500 pixels**
3. Keep the dark theme aesthetic for consistency

### Add a Profile Photo
GitHub automatically shows your profile photo from your account settings. No additional setup needed.

---

## Troubleshooting

| Issue | Solution |
|---|---|
| README not showing on profile | Ensure repo name is exactly `pnoorahammad` and is public |
| Banner not loading | Verify `assets/banner.png` exists and path is correct |
| Stats not loading | GitHub Stats API may take a few minutes to cache |
| Snake not generating | Run the workflow manually from the Actions tab |
| Badges broken | Check internet connection — badges load from shields.io |

---

## File Structure

```
pnoorahammad/
├── README.md              ← Main profile README (displayed on GitHub)
├── assets/
│   └── banner.png         ← Profile banner image
├── .github/
│   └── workflows/
│       └── snake.yml      ← Snake animation workflow (optional)
├── LICENSE                 ← MIT License
├── CONTRIBUTING.md         ← Contribution guidelines
└── UPLOAD_GUIDE.md         ← This file
```

---

**That's it! Your enterprise-quality GitHub profile is now live.**
