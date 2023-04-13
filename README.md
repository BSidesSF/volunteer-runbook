# BsidesSF Volunteer Runbook

Static HTML site using Mkdocs to render a readthedocs themed site of the BsidesSF volunteer runbook. This is deployed to https://bsidessf.org/volunteer-runbook

## How to Deploy

GitHub Pages are configured to serve files from the root of the `deployed` branch.

[GitHub actions](.github/workflows/deploy-static-site.yml) are set for this repo. Upon a commit or merge to main the Github runner will rebuild the site and push it to the `deployed` branch for GitHub pages

To deploy changes manually, run `deploy.sh` The `mkdocs gh-pages` command inside will build and commit it to the `deployed` branch.

## I've Never Used MkDocs Before

To edit a page, edit the associated markdown file and merge to main.
To add a page, create a new `<name>.md` markdown file, add it in the `nav:` section of `mkdocs.yml` to add it to the navigation tree, and merge to main

For full documentation visit [mkdocs.org](https://www.mkdocs.org).

### Helpful Local Commands

* `mkdocs serve` - Start the live-reloading docs server.
* `mkdocs build` - Build the documentation site.
* `mkdocs -h` - Print help message and exit.

### Project layout

```
├── README.md                   # This file
├── deploy.sh                   # Script to deploy the site from a local computer
├── docs                        # The folder for all markdown files with documentation
│   ├── attendee-facing         # Folder for attendee facing roles
│   │   ├── role.md
│   ├── behind-the-scenes       # Folder for behind the scenes roles
│   │   ├── role.md
│   ├── extra.css               # Extra CSS to add on top of the RTD theme
│   ├── index.md                # File for the root of the site
│   └── safety-ops              # Folder for Safety Ops roles
│       ├── role.md
├── mkdocs.yml                  # Configuration for MkDocs, including navigation tree
├── requirements.txt            # Required Python packages to use and run MkDocs
└── site                        # Output directory of the MkDocs build files
```