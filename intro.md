# Computational Medicine Group Onboarding

In this book you will find resources, references and tutorials on various topics that are relevant to our activity as a group.

## How do I contribute to this site?

Contributing to this site involves use of GitHub, Markdown or Jupyter Notebooks, and the command line. It is built with [Jupyter Book](https://jupyterbook.org/) technology, but it is fairly simple to work with. To start, you will need to do the following:

1. Clone the book's repository (available on the top-right) onto your computer.
2. Install Jupyter Book (to generate the updated website HTML after editing) by running
```
pip install -U jupyter-book
```
3. Install `ghp-import` (to publish the updated HTML using GitHub Pages) by running
```
pip install ghp-import
```

After this is done, you will be able to update existing pages or create new ones. Pages are handled _via_ source files that include [Juypyter Notebooks](https://jupyter.org/) and [MyST flavoured Markdown](https://jupyterbook.org/en/stable/reference/cheatsheet.html) pages. Jupyter Book then takes the source files and builds a static HTML website (which is what you're seeing here).

### How to update existing pages

1. Pull from `remote` to make sure you have the latest website on your computer.
2. Edit the Markdown or Jupyter Notebook file that corresponds to the page.
3. Push your changes to the repository.
```{note}
Only push the changes to the source files (i.e. the file you just edited). Do not push the `_build/` folder, which contains the HTML files for the website. It should be included in the `.gitignore` file, so normally Git will ignore the folder and impede this from happening.
```
4. Build the webpage on your computer (generate updated HTML files) by running
```
jupyter-book build .
```
from the `main` branch of the `onboarding/` directory.
5. Publish the updated website by running
```
ghp-import -n -p -f _build/html
```
from the `main` branch of the `onboarding/` directory.
```{note}
There is no need to push anything other than the source files you pushed in step 3. `ghp-import` handles pushing the HTML changes to remote all by itself.
```

### How to create new pages

1. Pull from `remote` to make sure you have the latest website on your computer.
2. Edit the `_toc.yml` file to account for your new page. In this file, `chapters` refer to pages that constitute a part of a subject (for example, `biostats` is a part of `Statistical and Data Analysis`) and `sections` refer to subpages within that chapter (for example, `electroforce` is a subpage of `instruments`). This should be a correctly classified a `file` entry, with its value being the path to the new page without suffix (i.e. without `.md` or `.ipynb`).
3. Create the new file in the corresponding folder and edit it accordingly.
4. Follow from step 3 of "How to update existing pages".
