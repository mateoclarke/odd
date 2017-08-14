City of Austin Design, Technology, and Innovation Fellows Website
==========================

This repo is for our public-facing site, which is hosted on austintexas.io.  This site is the main funnel for fellows program recruiting and outreach.

The site is forked from [usds.gov](https://usds.gov), which is built on the [U.S. Web Design Standards](https://playbook.cio.gov/designstandards/) and uses Jekyll to generate static pages.

## Setup
---
1. If you're using a Mac, install homebrew (see http://brew.sh/)
2. After installing git (`brew install git`), `cd` to the directory where you want to check-out the site, and then clone it (`git clone https://github.com/usds/website.git`)
3. Install rvm (`\curl -sSL https://get.rvm.io | sudo bash -s stable`), make your current user a member of the rvm group, and then install a new version of ruby (`rvm install 2.3.1`) or make sure you're using it: `rvm use 2.3.1`
4. Install the `bundler` gem, then use bundler to install other project dependencies (`gem install bundler && bundle install`)

## Running
---
1. In the directory you checked out the website into, run `jekyll serve` to start the webserver
2. Navigate to http://localhost:4000 in your browser to see your changes

## Usage

### Navigation

Zilker generates site-wide navigation automatically, with zero configuration. The primary "global" navigation renders Jekyll's `site.pages` sorted by URL and optionally by a `position` front-matter property, if set.

Pages in subfolders, like `parent/child.md`, render as visual children of their parent, e.g. `parent.md`. The parent page must exist for the child page to appear in the navigation.

The navigation logic is recursive, and works with deeply nested children, but exceeding two levels is not recommended.

### Collections

Zilker also supports per-section sub-navigation using Jekyll [Collections]. Given a collection named `example`, each document in [_example/](_example/) will include navigation to the other documents in the collection when output.

To show a collection in the primary navigation, Zilker looks for a "collection index" page at the site root, e.g. [example.md](example.md). The page's front-matter must include a `collection` property matching the collection key in [_config.yml](_config.yml), and its permalink must match the collection's.

Sorting and parent-child relationships work the same way in a collection's sub-navigation as in the primary navigation.

[Collections]: https://jekyllrb.com/docs/collections/
