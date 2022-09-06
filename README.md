# vpicave.club

This is the official website for the VPI Cave Club. Jekyll was picked for the simplicity of content modification and the seperation of template and content.

## Install Dependencies

To contribute, you must install [Ruby](https://www.ruby-lang.org/en) on your system. You also need [Ruby Bundler](https://bundler.io) which can be installed like so:

```shell
gem install bundler
```

## Setup

First, clone the repository.

```shell
git clone https://github.com/cernec1999/vpicave.club
```

Next, change into the cloned repository and install the dependencies. Note: You must have Ruby installed and in your system path, in addition to the bundler, as described in the previous section.

```shell
cd vpicave.club
bundle install
```

Next, checkout the dev branch.

```shell
git checkout dev
```

Finally, launch the development server.

```shell
jekyll serve
```

## Adding Content

Adding content to the site is fairly simply. To create a page, simply create a file in **\_posts** with this format:

```shell
yyyy-mm-dd-my-awesome-title.md
```

Using [Markdown Syntax](https://www.markdownguide.org/), add content to your new file. You can (and should) use [Front Matter](https://jekyllrb.com/docs/front-matter) to add metadata to your page. Here is example syntax for the Membership Requirements page.

```yaml
---
layout: page
title: Membership Requirements
desc: Are you up to the challenge?
image: /assets/img/home.jpg
category: Prospective Members
---
```

The most important keys in the Front Matter are **layout** and **category**. The **layout** key specifies which HTML layout to use (normally, you should keep this **page** unless you're doing something crazy). The **category** key specifies what category in the navigation bar to lump the post in. If you feel that a post doesn't belong in a category on the website, feel free to specify a different category name; there is no process to "create a category" - this is done automatically.

For more information, consult pages that were already created in the **\_posts** directory.

## Editing Committees

To edit committees, you must familiarize yourself with YAML syntax. Then, edit the page **\_posts/2019-08-02-committees.md**. If you'd like, you can copy this syntax; this is the easiest way.

Here is some example Front Matter YAML:

```yaml
---
layout: committees
title: Committees
desc: For administrative purposes
image: /assets/img/home.jpg
category: Members
committees:
  - name: "Committee 1"
    desc: "This is a description"
    contact: "mailto:committee-email@vpicaveclub.org"
    members:
      - name: "Person 1"
        role: "My Position"
        img: /assets/img/committees/person.jpg
        contact: mailto:president@vpicaveclub.org
      - name: "Person 2"
        img: /assets/img/committees/person2.jpg
  - name: "Committee 2"
    desc: "Second committee"
    contact: "mailto:committee-2-email@vpicaveclub.org"
    members:
      - name: "Person 3"
      - name: "Person 4"
---
```

Under each person, the **role** key, the **img** key, and **contact** key are unnecessary. You should only have a **contact** key if there is a **role** key under the particular person. The page will use the **contact** key for the committee as the contact if there is no **contact** key for the person.

## Publishing Content

To publish content, you must submit a Pull Request (PR) in GitHub and merge the content from dev into master. Here is a [Github Guide](https://docs.github.com/en/github/collaborating-with-issues-and-pull-requests/creating-a-pull-request) that explains the process of submitting a Pull Request.
