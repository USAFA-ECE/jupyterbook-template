# Jupyter Book Template for GitHub Pages

A simple demo of how to deploy a [Jupyter Book](https://jupyterbook.org/en/stable/intro.html) static website to [GitHub Pages](https://docs.github.com/en/pages/getting-started-with-github-pages/about-github-pages) that is automatically built with [GitHub Actions](https://docs.github.com/en/actions).

Pages are deployed to `<username>.github.io/<repository-name>`. The live example of this demo is at https://usafa-ece.github.io/jupyterbook-template/

- Recommend reading [Structure the Table of Contents](https://jupyterbook.org/en/stable/structure/toc.html) for the `book/_toc.yml` file
- Recommend reading [Markdown files](https://jupyterbook.org/en/stable/file-types/markdown.html) in Jupyter Books
- Recommend reading [Configuration reference](https://jupyterbook.org/en/stable/customize/config.html) for the `book/_config.yml` file

## How it works

This repository uses the strategy of [Publishing from a branch](https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site#publishing-from-a-branch) to deploy the static site.

It has two branches:

- `main` which holds the all the Markdown and other files to generate the Jupyter Book. Treat this branch like any other with pushes & pull requests.
- `gh-pages` which is a special branch to GitHub Pages. It is automatically updated with the built HTML files by the Actions. Don't touch this branch!

The book itself is in the `book/` directory. If you change the name of this directory you also must changes it in the `deploy.yml` file.

On every push or pull event to `main` an Action workflow is triggered.
That workflow follows the instructions in `.github/workflows/deploy.yml` to run `jupyter-book build`. After the build creates the HTML files for the static site, the workflow pushes the files to the `gh-pages` branch.

GitHub automatically deploys whatever `index.html` file it finds at the root of `gh-pages` **after** you tell it to do so in settings, see below.

## Usage

This is a template repository, so you can [create your own repository from this template](https://docs.github.com/en/repositories/creating-and-managing-repositories/creating-a-repository-from-a-template#creating-a-repository-from-a-template).

### Setup

1. Follow the docs to edit your repository settings and tell pages to deploy from `gh-pages` branch. See [Publishing from a branch](https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site#publishing-from-a-branch)
2. Use the drop down menu to tell GitHub pages to deploy from `/root` on that branch
3. Manually trigger a workflow on the `main` branch to verify everything is working.
4. Cruise through the `book/_config.yml` to update everything.

![github pages settings](https://user-images.githubusercontent.com/6315292/208469724-203ad297-d4b0-4205-88a3-33988e3d4889.png)

### Modify book content

Making updates to the content can be as simple as adding/editing the Markdown or Jupyter Book YAML files and pushing to `main`. No depenedencies needed!

#### Preview site before you push

If you want to build the site locally, you need to install Jupyter Book.
This requires Python 3.9 or higher, which you should run in a virtual environment.

To use a virtual environment...

```bash
python3 -m venv env
source env/bin/activate
```

Install requirements

```bash
pip install -r requirements.txt
```

Make whatever changes you want to the site inside the `book/` directory.

Build the book

```bash
jupyter-book build book/
```

The static files will now be located in `book/_build/`. View the website by opening `index.html` in any browser

```bash
firefox book/_build/index.html
```

You have to rebuild every time you make changes in order to preview them.

Note that `_build/` is in the `.gitignore` file because the actions build what is actually deployed.

Once satisfied, push to `main` and github actions will auto-deploy!
