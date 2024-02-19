# About The BITS-ACB Organization Repo and Docs 

## First, About BITS

BITS is an acronym for 
[Blind Information Technology Specialist](https://bits-acb.org).  
ACB is for the 
[American Council of the Blind](https://acb.org).
BITS is [an affiliate of ACB](https://www.acb.org/affiliate-BITS).
Click through any of these links to learn more about BITS, ACB, and how they're related.

## About the BITS-ACB Organization on github

In the interest of growing participation in BITS,
It was decided to create somewhat formal learning opportunities.
The first of these was a Python programming course starting in early 2024.
The BITS-ACB organization was created on github to support that effort.

## About this Documentation

As of February, 2024, we're using github pages as the documentation site for the BITS-ACB organization.
The docs are written in markdown and converted to HTML using 
[mkdocs with the material theme](https://squidfunk.github.io/mkdocs-material/).
Github pages works slightly differently for project repos than for personal account or organization github pages.
For details, see this [article on deploying mkdocs to github pages](https://www.mkdocs.org/user-guide/deploying-your-docs/).
The documentation repo structure will make more sense if you read that article (it's not too long).

### Where is the the Documentation

There are two repos you'll need to clone if you want to work with the docs (these are URLs for using SSH):
``` bash
git@github.com:BITS-ACB/bits-acb.gh-pages.git
```
``` bash
git@github.com:BITS-ACB/bits-acb.github.io.git
```
The ``` bits-acb.gh-pages ``` repo has all the markdown and any other associated files used to generate the HTML.
The ``` bits-acb.github.io ``` repo is there because that's how github pages works for personal and organization accounts.

### Updating and Building the Documentation

First, you need Python.
I've been using 3.11 but I think mkdocs will work with 3.9, maybe 3.10 (check the mkdocs-material docs).
The only additional Python package you should need to install is:
``` bash 
pip install mkdocs-material
```

To edit and deploy changes, you need to clone both repos listed above.
It's best to keep them in the same parent directory, there's a command below making that assumption.
For example:
``` bash
~/bits-acb-work/
    bits-acb.gh-pages/
    bits-acb.github.io/
```

The ``` bits-acb.gh-pages ``` repo is the only one you should edit.

Anyone is welcome to edit existing documentation for corrections and/or clarification.
If you want to add new topics,
please follow the existing structure for where to add.

For details on how mkdocs and the material theme work, see the links above.
For the most part, you'll only need to work with markdown, which is fairly standard.
If you're adding new content, you'll need to add the file to the mkdocs.yml file in the root of the ``` bits-acb.gh-pages ``` repo.

#### Checking Your Work

Once you've made changes in the ``` bits-acb.gh-pages ``` repo, 
you can build and view those changes locally.
In the root of the repo, where the mkdocs.yml file lives, run:
``` bash 
mkdocs serve 
```
Mkdocs will build the site and start a simple web server to give you local access to the documentation.
If the build went well, you should see your local copy of the docs, with your changes at:
[http://localhost:8000](http://localhost:8000).

You can keep this server running while you make changes to your local copy of the docs.
Your changes will be reflected automatically in the browser.

#### Deploy Your Changes to Github Pages 

1. Commit and push your changes in ``` bits-acb.gh-pages ``` to the main branch on github.
1. In the root directory of the ``` bits-acb.github.io ``` repo, run the following command:
``` bash 
mkdocs gh-deploy --config-file ../bits-acb.gh-pages/mkdocs.yml  --remote-branch main 
```

If all went well, you should see your changes at:
[https://bits-acb.github.io](https://bits-acb.github.io)
(it might take a few minutes depending on how busy github is).
