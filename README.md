# Marp Presentation Auto-Converter & Deployer

This project automatically converts Marp Markdown presentations into HTML and PowerPoint (PPTX) formats and deploys the HTML versions to GitHub Pages.

## How to Use

1.  **Create your presentation:**
    *   Write your presentation using Marp Markdown syntax. Save it as a `.md` file (e.g., `my_awesome_slides.md`).

2.  **Add to `report/` directory:**
    *   Place your new `.md` file into the `report/` directory in this repository.

3.  **Commit and push:**
    *   Commit your new presentation file (and any local images it uses if you've added them to the repository) to the `main` branch and push your changes.
    ```bash
    git add report/your_new_presentation.md
    git commit -m "Add new presentation: your_new_presentation"
    git push origin main
    ```

## Automation Workflow

Once you push changes to `.md` files in the `report/` directory on the `main` branch, a GitHub Actions workflow will automatically perform the following:

1.  **Convert Files:**
    *   Each Markdown file in `report/` is converted into:
        *   An **HTML file** (e.g., `your_new_presentation.html`) located in the `html/` directory.
        *   A **PowerPoint (PPTX) file** (e.g., `your_new_presentation.pptx`) located in the `output/` directory.

2.  **Generate Summary Page:**
    *   An updated `html/summary.html` file is generated. This page lists all your presentations with links to view the HTML version online or download the PPTX version.

3.  **Commit Outputs:**
    *   The generated `html/` directory (including `summary.html` and all slide HTML files) and the `output/` directory (with PPTX files) are automatically committed back to your `main` branch. This means you can always find the latest generated outputs directly in your repository.

4.  **Deploy to GitHub Pages:**
    *   The contents of the `html/` directory are deployed to GitHub Pages.

## Accessing Your Presentations

*   **Live HTML Slides:**
    *   View your presentations online at:
        `https://clarencechien.github.io/marpsite/<presentation_name>.html`
        (e.g., `https://clarencechien.github.io/marpsite/your_new_presentation.html`)

*   **Summary Page:**
    *   Access the summary of all presentations at:
        `https://clarencechien.github.io/marpsite/summary.html`

*   **Files in Repository:**
    *   Find all source Markdown files in the `report/` directory on your `main` branch.
    *   Find the generated HTML files (including `summary.html`) in the `html/` directory on your `main` branch.
    *   Find the generated PPTX files in the `output/` directory on your `main` branch.
