# WeeklyPDFPlannerCreator
**Purpose:** Create custom planners as PDFs with python. This was designed specifically for the [Supernote A6X](https://supernote.com/) but could be used for any digital planner or even as a print-out! 

**Jump right to the code:**
[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/emcarthur/WeeklyPDFPlannerCreator/blob/main/WeeklyPlanner.ipynb)

**Skip to the final planner files:** `{YEAR}_WeeklyPlanner_withBookmarks.pdf`

I was inspired by [this workflow](https://www.youtube.com/watch?v=NN6KQI4Nslk) but wanted a weekly planner instead of a daily planner and I wanted to specifically customize it to my needs. I created a weekly template (svg) and python script that allows you to customize a weekly planner to your hearts desire. With a few tweaks, it could be a montly or daily planner as well.

### Overview of repo contents and steps to create a planner
* **To create a template for each page**
    *   *Optional:* I first drafted out a template using MS word with some tables: `template_draft.docx`. I then exported this as a pdf: `template_draft.pdf`. 
    *   Then I imported the pdf into [inkscape (free)](https://inkscape.org/) to save an editable svg. You can directly just create a template in inkscape without MS word.
    *   I edited the svg to look exactly how I wanted. Make sure to set the document properties size to the size of the document you want (e.g. A5, A6).
    *   I created some placeholder text for parts of the template that I wanted to be dynamically updated (eg. "Month1 Day1" or "D1" "D2"). Just make sure this text is centered and where you want the final text to end up.
    *   *Optional:* I converted other text to objects so their formatting is always consistent (Path > Object to Path)
    *   I saved this as `template.svg`
*   **To fill in the dates and combine the 52 weeks into a single large pdf**
    *   The Jupyter notebook `WeeklyPlanner.ipynb` will do this for you! Edit the "CONFIG" cell at the top with the year and file output name. You can easily edit & run this online in Google Colabs or download it to edit locally.
    *   Essentially this code reads in the template, finds the placceholder text, and replaces it with the appropriate dates. It then adds each week together into a large pdf and then saves it. 
    *   If you want to make custom edits, parsing of the template is done with the function `updateSVGdates`.
*   **To add montly bookmarks to the pdf for easy navigation**
    *   If you want to add monthly bookmarks to your pdf, you can use [PDF Escape](https://www.pdfescape.com/) (free), Adobe acrobat (not free), or [other online tools](https://www.ilovefreesoftware.com/21/featured/online-add-bookmarks-to-pdf-free-websites.html).
    *   With PDF escape, upload your pdf. Go to the "Bookmarks" panel (looks like a page with a little red tab). Scroll to the page you want to add a bookmark to. Click "add" and title your bookmark. (Tip: use the view:fit to precisely bookmark the right page).
