http://maruan.alshedivat.com (https://alshedivat.github.io/al-folio/)

# Resources

## Asynchronous channel

## Zoom rooms

## Collaborative whiteboard (miro)

## Github

### Projects

### Boards

### Tasks and Issues

(#### Assign labels)

(#### Assign people)

### Repos

## Shared documents

## ITU document server

## Mailing list

## Calendar

# User stories

## Create a new workstream (coordinator)

1. ### Create mailing list

1. ### Create calendar

1. ### Create meeting series on Zoom

1. ### Create asynchronous channel (discord/slack)

1. ### Create project.md in _projects
1. Fill out with above info + descriptipon
1. Add project (project card)
1. Add project image for full text

1. ### Create "projectname".bib in _bibliography
Insert bibitems of related publications

1. ### Have known contributors fill out the contributor template (including yourself) and add to repo

## Update workstream resources (coordinator)

### Modify resources
See "Create a new workstream (coordinator)"

### Update project.md
Go to the repo ... and modify markdown

### Add publications
Add bibitems to "projectname".bib

## Join a Project / Workstream (contributor)

1. ### Add personal information
   #### Add Name
   #### Add Affiliation
   #### Add Brief Profile

1. ### Subscribe to project mailing list
   #### Add Email Id
   
1. ### Join channel 
   #### Add me to Git Hub (Project Repo)
   #### Add me to Trello Board (Project Management Board)
   #### Add me to Miro Board (White Board)
   #### Add me to Zoom (Video Conferencing tool)
   #### Add me to Slack (Chat / Communication channel)
   #### Add me to Discord (Chat / Communication channel)
       
1. ### Add your contributor info to repo
   #### Add your role (Project Driver/Lead/Principal Investigator, Project Developer, Project Associate)
   
# Preliminaries

Have [Ruby](https://www.ruby-lang.org/en/downloads/) and [Bundler](https://bundler.io/) installed on your system (*hint: for ease of managing ruby gems, consider using [rbenv](https://github.com/rbenv/rbenv)*)

For more about how to use Jekyll, check out [this tutorial](https://www.taniarascia.com/make-a-static-website-with-jekyll/).
Why Jekyll? Read this [blog post](https://karpathy.github.io/2014/07/01/switching-to-jekyll/)!


# Workflow

IMAGE/Graph

Steps
1. git pull 
1. Edit content in markdown (see categories below)
1. Save
1. bundle exec jekyll build
1. git add .
1. git commit -m "..."
1. git push

...current scenario
1. login to ftp
1. transfer _site folder content

...future scenario 1
1. ssh into webserver
1. git pull

...future scenario 2
1. automated script ()upon new commit)
   1. sshes into webserver 
   1. git pull

...future scenario 3
1. automated script (upon commit)
   1. bundle exec jekyll build
   1. git add .
   1. git commit 
   1. sshes into webserver
   1. git pull upon new commit in github


# Adding content

## Pages

## Projects

## Posts

## News

## Publications

# Housekeeping

## Everyone

###

## Project drivers

## Contributors


### Installation

Assuming you do

```bash
$ git clone https://github.com/aiaudit-org/website.git
$ cd website
$ bundle install
$ bundle exec jekyll serve
```
to have a look at the website locally.

Alternatively you can use the .devcontainer functionality in VS Code. Inside the container simply run 
```bash
$ bundle exec jekyll serve
```

Now, you can add contents in markdown. When you are done


## Features

### Publications

Your publications page is generated automatically from your BibTex bibliography.
Simply edit `_bibliography/papers.bib`.
You can also add new `*.bib` files and customize the look of your publications however you like by editing `_pages/publications.md`.

Keep meta-information about your co-authors in `_data/coauthors.yml` and Jekyll will insert links to their webpages automatically.

<p align="center"><img src="assets/img/publications-screenshot.png" width=800></p>


### Collections

This Jekyll theme implements `collections` to let you break up your work into categories.
The theme comes with two default collections: `news` and `projects`.
Items from the `news` collection are automatically displayed on the home page.
Items from the `projects` collection are displayed on a responsive grid on projects page.

<p align="center"><img src="assets/img/projects-screenshot.png" width=700></p>

You can easily create your own collections, apps, short stories, courses, or whatever your creative work is.
To do this, edit the collections in the `_config.yml` file, create a corresponding folder, and create a landing page for your collection, similar to `_pages/projects.md`.


### Layouts

**al-folio** comes with stylish layouts for pages and blog posts.

#### The iconic style of Distill

The theme allows you to create blog posts in the [distill.pub](https://distill.pub/) style:

<p align="center"><a href="https://alshedivat.github.io/al-folio/blog/2018/distill/" target="_blank"><img src="assets/img/distill-screenshot.png" width=700></a></p>

For more details on how to create distill-styled posts using `<d-*>` tags, please refer to [the example](https://alshedivat.github.io/al-folio/blog/2018/distill/).

#### Full support for math & code

**al-folio** supports fast math typesetting through [KaTeX](https://katex.org/) and code syntax highlighting using [GitHub style](https://github.com/jwarby/jekyll-pygments-themes):

<p align="center">
<a href="https://alshedivat.github.io/al-folio/blog/2015/math/" target="_blank"><img src="assets/img/math-screenshot.png" width=400></a>
<a href="https://alshedivat.github.io/al-folio/blog/2015/code/" target="_blank"><img src="assets/img/code-screenshot.png" width=400></a>
</p>

#### Photos

Photo formatting is made simple using [Bootstrap's grid system](https://getbootstrap.com/docs/4.4/layout/grid/).
Easily create beautiful grids within your blog posts and project pages:

<p align="center">
  <a href="https://alshedivat.github.io/al-folio/projects/1_project/">
    <img src="assets/img/photos-screenshot.png" width="75%">
  </a>
</p>


### Other features

#### Theming
Six beautiful theme colors have been selected to choose from.
The default is purple, but you can quickly change it by editing `$theme-color` variable in the `_sass/_themes.scss` file.
Other color variables are listed there as well.

#### Social media previews
**al-folio** supports preview images on social media.
To enable this functionality you will need to set `serve_og_meta` to `true` in your `_config.yml`.
Once you have done so, all your site's pages will include Open Graph data in the HTML head element.

You will then need to configure what image to display in your site's social media previews.
This can be configured on a per-page basis, by setting the `og_image` page variable.
If for an individual page this variable is not set, then the theme will fall back to a site-wide `og_image` variable, configurable in your `_config.yml`.
In both the page-specific and site-wide cases, the `og_image` variable needs to hold the URL for the image you wish to display in social media previews.


## Contributing

Contributions to al-folio are very welcome!
Before you get started, please take a look at [the guidelines](CONTRIBUTING.md).

If you would like to improve documentation, add your webpage to the list below, or fix a minor inconsistency or bug, please feel free to send a PR directly to `master`.
For more complex issues/bugs or feature requests, please open an issue using the appropriate template.


## FAQ

Here are some frequently asked questions.
If you have a different question, please ask on [gitter](https://gitter.im/alshedivat/al-folio).

1. **Q:** When I preview my website locally everything looks great, but when I deploy it on GitHub bibliography Liquid tags are not recognized.
   How do I fix this? <br>
   **A:** GitHub Pages rendering does not support certain Jekyll plugins, and `jekyll-scholar` that we use to render bibliography is one of them. Please make sure you deploy your website to GitHub using `bin/deploy` script that circumvents the issue.

2. **Q:** When I deploy my fork of al-folio, it says `Deployed successfully!`
   But when I open `<my-github-username>.github.io`, I get `Page not found (404)` error.
   How do I fix this? <br>
   **A:** For personal webpages, please run `bin/deploy --user`.
   (See also relevant past issues: [#5](https://github.com/alshedivat/al-folio/issues/5), [#49](https://github.com/alshedivat/al-folio/issues/49), [#86](https://github.com/alshedivat/al-folio/issues/86).)


## License

The theme is available as open source under the terms of the [MIT License](https://opensource.org/licenses/MIT).

Originally, **al-folio** was based on the [\*folio theme](https://github.com/bogoli/-folio) (published by [Lia Bogoev](http://liabogoev.com) and under the MIT license).
Since then, it got a full re-write of the styles and many additional cool features.
