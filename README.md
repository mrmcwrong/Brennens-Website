# Junior Seminar Research Project

[![Build Research Journal Site](../../actions/workflows/main.yml/badge.svg)](../../actions/workflows/main.yml)
[![Release Junior Seminar Research Report](../../actions/workflows/release.yml/badge.svg)](../../actions/workflows/release.yml)

For more information about the course requirements for your Junior Seminar
course in Computer and Information Science, please ask the course instructor and
refer to the syllabus for your course. To enable you to complete many of the
deliverables for the Junior Seminar course, this repository contains
instructions for your research journal and your junior seminar research report.
Quarto, serving as a build system for your site, will build your research report
as a website and a PDF.

## Course Requirements

### Research Journal

Your research journal contains posts reflecting on your experiences completing
your junior seminar research project. For the Spring 2026 semester, you are
responsible for writing the following seven research journal entries:

1. **Research Idea**: What is your research idea? Describe the problem you plan
   to investigate and your initial approach.
1. **Prototype Installation and Use**: How do you install and use your research
   prototype? Provide clear instructions and documentation.
1. **Brainstorming and Prototyping Experience**: What were your experiences with
   brainstorming your idea and then prototyping and presenting it? Reflect on
   the challenges and successes.
1. **Chapter 1 and 2 Reflections**: Combined post reflecting on:
   - Reflection from writing Chapter 1: Introduction
   - Reflection from writing Chapter 2: Background Related Work
1. **Chapter 3 and 4 Reflections**: Combined post reflecting on:
   - Reflection from writing Chapter 3: Methodology
   - Reflection from writing Chapter 4: Results
1. **Chapter 5 Reflection**: Overall reflection from writing Chapter 5:
   Conclusions and Future Work
1. **Overall Project Reflection**: Overall reflection on the
   research project and identification of your next steps

### Junior Seminar Research Report Chapters

All researchers in the Junior Seminar course in Computer and Information Science
must document their work in the form of a written research report. While
variations on the typical structure and contents of a research report can be
specific to a certain project, a typical Computer and Information Science
research report contains `5` chapters:

1. Introduction
1. Related Work
1. Methods
1. Experiments (Results)
1. Conclusions and Future Work

Students complete all five chapters during the Spring 2026 semester. Each
chapter should be approximately **5 to 7 pages** in length. More details about
the baseline requirements for the junior seminar research report are available
in the course syllabus and in the [CONTRIBUTING.md](CONTRIBUTING.md) file.

## Course Technology Use

### Enabling Site Build

This site deploys via GitHub Pages using the Quarto static site building system.

1. Go to the `Settings` menu on this repository and locate the `Pages` submenu.

![GitHub Settings, Pages submenu](https://raw.githubusercontent.com/ReadyResearchersTemplates/site-template/media/img/600%20-%20Site%20Template%20-%20Github%20Pages%20Menu.png)

2. On the resulting screen, find the `Build and deployment` menu; select `GitHub Actions`

![GitHub pages, Build and Deployment item](https://raw.githubusercontent.com/ReadyResearchersTemplates/site-template/media/img/600%20-%20Site%20Template%20-%20Github%20Actions%20Menu.png)

### `Private` vs. `Public` availability

You retain the choice to make your research journal private or public; the
`Pages` settings menu should allow either. Your URL will change depending on
which selection you make, and you should be able to find the resulting URL of
your journal by visiting the pages section of the repository's `Settings` menu.
Your URL should display at the top of the page:

![GitHub Pages url](https://raw.githubusercontent.com/ReadyResearchersTemplates/site-template/media/img/600%20-%20Site%20Template%20-%20Github%20URL.png)

### Release Tagging

Since this repository primarily contains Markdown and/or LaTeX source code, the
GitHub Actions configuration for it will compile the source code and
automatically release a PDF of the main file whenever the last commit is
associated with a [Git
Tag](https://git-scm.com/book/en/v2/Git-Basics-Tagging).

This will build a PDF file available in the "Releases" listing for this
repository. All release numbers for your writing in this repository should
adhere to the [Semantic Version](http://semver.org/) standard expected of
GitHub projects. Here this means that:

- `Major version` releases feature a tag number change reflecting full
  releases; generally these start at `1.0.0`
- `Minor version` releases indicate small changes or additions to documents;
  typically these increment the second digit in the version (e.g. `1.1.0`)

Please note that your instructor will expect that the PDF generated from
"tagged" releases of the file `JuniorSeminarReport.pdf` that has a version
number greater than `1.0.0` if it contains a final version of Chapter 1. It
should then contain a version number greater than `2.0.0` if it contains a
final version of Chapter 2 and so on. The idea is that each major release of
your junior seminar research project should contain a final version of the
chapter that is signaled by the semantic version number.

That is:

- if your commit is tagged `JuniorSeminarReport-1.0.0`, then
- the file `JuniorSeminarReport.pdf` should be available for download in the
  "Releases" tab in your GitHub repository for this project under the name
  `JuniorSeminarReport-1.0.0`.

To ensure you can create a release appropriately, make a single small change to
the `report/index.qmd` and:

1. Use `git` to `commit` your file changes using a `git commit` command
1. Create your first tag for this repository: type `git tag junior_seminar_report-0.1.0`.
1. You are now ready to push your changes with the tag number using `git push -u origin main --tags`

The above steps should build a version of your project and release it on GitHub!
If something does not work correctly, please contact Professor Gregory M.
Kapfhammer to explain the details of the challenges that you faced. You can
schedule an office hours appointment at:
[https://www.gregorykapfhammer.com/schedule/](https://www.gregorykapfhammer.com/schedule/)

It is also important to note that it is possible for a student to perform a
manual release of the PDF of their junior seminar research report. Again, please
communicate with Professor Kapfhammer for more information about the steps you
would take to perform a manual release. With that said, it is important to
stress that you should learn how to perform an automated release of your report
in PDF and only use the manual approach if there is a severe and extenuating
circumstance (e.g., GitHub Actions stops working for a short time) that prevents
you from performing an automated release.

When you make subsequent changes to your files and perform commits and you are
ready to release a new version of `JuniorSeminarReport.pdf`, then you should
again tag your work _before a `push` command_ with a tag that
adheres to the [Semantic Version](http://semver.org/) standard.

Each time that you correctly execute this sequence of commands you will release
a new version of your document to GitHub that is easily accessible as a PDF to
you and to your instructor.

While you are able to build copies of your PDF locally using the `quarto render`
command, the only copy that will be evaluated is that released to GitHub following
the procedure outlined above.

## Local Testing and Development

Before pushing your work to GitHub, you can test both the website and PDF
compilation locally to catch any errors early. This section explains how to build
and preview your work on your local machine.

### Prerequisites

To build and test locally, you need to have the following installed:

- **Quarto**: Download and install from [https://quarto.org/docs/get-started/](https://quarto.org/docs/get-started/)
- **Python 3.x**: For various build tools (often already installed on most systems)
- **LaTeX Distribution**: Required for PDF generation
  - **Windows**: Install [MiKTeX](https://miktex.org/)
  - **macOS**: Install [MacTeX](https://www.tug.org/mactex/)
  - **Linux**: Install TeX Live via your package manager (e.g., `sudo apt install texlive-full`)
  - **Any OS**: Alternatively, use TinyTeX via Quarto: `quarto install tinytex`

### Testing the Research Journal Website

To build and preview the research journal website locally:

1. Open a terminal and navigate to the root of your repository:

   ```bash
   cd path/to/your/repository
   ```

1. Render the entire website:

   ```bash
   quarto render
   ```

   This command will:

   - Build all journal entries and pages
   - Generate the website in the `_site` directory
   - Report any errors in your Markdown or configuration

1. Preview the website in your browser:

   ```bash
   quarto preview
   ```

   This will:

   - Start a local web server
   - Open your browser to view the site (typically at `http://localhost:XXXX`)
   - Automatically refresh when you make changes to files

1. If you encounter errors:

   - Check the terminal output for specific error messages
   - Verify that all `.qmd` files have valid YAML front matter (enclosed in `---`)
   - Ensure all images referenced in posts exist in the correct locations
   - Check that dates in posts are formatted correctly: `YYYY-MM-DD`

### Testing the Research Report PDF

To build and verify the junior seminar research report PDF locally:

1. Orient towards the report directory for your work, but bear in mind that most
   commands can be run from the root of this repository:

   ```bash
   cd report
   ```

1. From the root of this repository, render the research report as a PDF:

   ```bash
   quarto render index.qmd --to allegheny-cis-pdf
   ```

   This command will:

   - Compile all chapter files (`_introduction.qmd`, `_related_work.qmd`, etc.)
   - Generate a PDF using the Allegheny College CIS template
   - Create the output in `_site/report/index.pdf`

1. View the generated PDF:

   - The PDF will be located at: `_site/report/index.pdf`
   - Open this file with your PDF viewer to verify the output

1. If you encounter LaTeX errors:

   - Check that all citations in `references.bib` are properly formatted
   - Verify that all images in `report/images/` are in supported formats (PNG, JPG, PDF)
   - Ensure all cross-references to figures and tables are correct
   - Check that special LaTeX characters are properly escaped

### Testing Both Website and PDF Together

To test the complete build (both website and PDF):

1. From the root directory, run:

   ```bash
   quarto render
   quarto render report/index.qmd --to allegheny-cis-pdf
   ```

1. Check the outputs:

   - Website: `_site/index.html` (open in browser)
   - Research Report PDF: `_site/report/index.pdf`

### Continuous Preview During Development

For the best development experience, you can keep a preview running while you work:

1. In one terminal, run:

   ```bash
   quarto preview
   ```

1. Edit your files in your preferred text editor

1. Save your changes, and the preview will automatically refresh

1. When ready to test the PDF, open a second terminal and run:

   ```bash
   quarto render report/index.qmd --to allegheny-cis-pdf
   ```

This workflow allows you to catch errors quickly and see your changes immediately.

## Repository Structure

This repository is organized to support both your research journal website and
your research report PDF. Understanding the structure will help you navigate and
maintain your project effectively.

### Top-Level Directories and Files

- **`report/`**: Contains all files related to your junior seminar research report

  - `index.qmd`: Main report configuration file (title, authors, bibliography)
  - `_introduction.qmd`: Chapter 1 - Introduction
  - `_related_work.qmd`: Chapter 2 - Related Work
  - `_methods.qmd`: Chapter 3 - Methods
  - `_experiments.qmd`: Chapter 4 - Experimental Results
  - `_conclusion.qmd`: Chapter 5 - Conclusions and Future Work
  - `references.bib`: Bibliography file for all citations
  - `images/`: Directory for figures and diagrams used in the report

- **`posts/`**: Contains all journal entries organized by category

  - `activity/`: Activity-based journal entries (research planning, prototyping)
    - `journal-entry-1.qmd`: Research Idea
    - `journal-entry-2.qmd`: Prototype Installation and Use
    - `journal-entry-3.qmd`: Brainstorming and Prototyping Experience
  - `reflection/`: Reflection-based journal entries (chapter reflections)
    - `journal-entry-4.qmd`: Chapters 1 and 2 Reflections
    - `journal-entry-5.qmd`: Chapters 3 and 4 Reflections
    - `journal-entry-6.qmd`: Chapter 5 Reflection
    - `journal-entry-7.qmd`: Overall Project Reflection

- **`.github/workflows/`**: GitHub Actions automation

  - `main.yml`: Builds and deploys the website to GitHub Pages on every push
  - `release.yml`: Builds and releases the PDF when you create a version tag

- **`_extensions/`**: Contains the Allegheny CIS LaTeX template

  - Used automatically by Quarto to format your research report PDF

- **Configuration Files**:

  - `_quarto.yml`: Main Quarto configuration for website appearance and behavior
  - `about.qmd`: About page with instructor contact information
  - `index.qmd`: Homepage of your research journal website
  - `CONTRIBUTING.md`: Guidelines for writing your research report
  - `README.md`: This file - project documentation

### Generated Directories (Do Not Commit)

- **`_site/`**: Generated website and PDF output (created when you run `quarto render`)

  - `index.html`: Website homepage
  - `report/index.pdf`: Your research report PDF
  - Other HTML files for each journal entry and page

- **`.quarto/`**: Quarto cache directory (improves build speed)

### Where to Edit

- **For journal entries**: Edit files in `posts/activity/` or `posts/reflection/`
- **For research report**: Edit chapter files in `report/` directory
- **For website appearance**: Modify `_quarto.yml` configuration
- **For citations**: Add BibTeX entries to `report/references.bib`
- **For images**: Place files in `report/images/` and reference them in your
  chapters

## Seeking Assistance

If you are having trouble completing any part of this project, then please talk
with Professor Gregory M. Kapfhammer. In particular, if you have questions about
your research project, please see Professor Kapfhammer during office hours or
schedule an appointment at:

- **Professor Website**: [https://www.gregorykapfhammer.com/](https://www.gregorykapfhammer.com/)
- **Office Hours Scheduling**: [https://www.gregorykapfhammer.com/schedule/](https://www.gregorykapfhammer.com/schedule/)

Students who want to learn more about [Managing releases in a GitHub
repository](https://docs.github.com/en/repositories/releasing-projects-on-github/managing-releases-in-a-repository)
or other topics related to release management on GitHub are encouraged to check
the [GitHub Releases
Documentation](https://docs.github.com/en/repositories/releasing-projects-on-github/about-releases).
