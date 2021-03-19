![osm-website](https://user-images.githubusercontent.com/686194/88725480-03e85c00-d0e1-11ea-8e3e-92eaf971b918.png)

Welcome to the source file repository for the [Open Service Mesh website](https://openservicemesh.io). The website is a simple static site, built with [Hugo](https://gohugo.io/) and hosted on [Netlify](https://app.netlify.com/sites/openservicemesh/settings/general).

---

## Structure

There are various parts to a hugo site, these are the key bits:

```
/public        // 'dist' generated website - do not edit
/resources     // compiled css assets - do not edit
/themes        // source files for the website - edits go here
config.yaml
```

Looking for logos? Latest brand assets for OSM can be found over at [/community/logos](https://github.com/openservicemesh/osm/tree/main/community/logos).


## Development

```
// run hugo to have the pipes rebuild and recompile
# hugo

// make sure to commit the generated results to git
# git add resources/*
```

#### Editing the Content

The website is broken up into html partials per section (e.g. navbar, footer, about, community). To edit the content, you need to modify [these source html files](https://github.com/openservicemesh/osm-www/tree/main/themes/clean-landing/layouts/partials) in the site theme.

*Do not make edits** to the code in the `/public` directory, this is overwritten each time the site is rebuilt!

In addition, certain pieces of content are set globally via the [config.yaml](https://github.com/openservicemesh/osm-www/blob/main/config.yaml#L10) file:

* site descrition
* site webfonts
* navbar: links
* about section: feature points
* _etc_

##### Editing Open Service Mesh Docs


docs.openservicemesh.io is a static site. The documentation content needs to be located at `content/docs/`.

To ensure the docs content renders correctly in the theme, each page will need to have [front matter](https://gohugo.io/content-management/front-matter/) metadata. Example front matter:

```
---
title: "Docs Home"
linkTitle: "Home"
description: "OSM Docs Home"
weight: 1
type: docs
---
```

## Front Matter Notes:

* inclusion of `type: docs` is important for the theme to properly index the site contents
* the `linkTitle` attribute allows you to simplify the name as it appears in the left-side nav bar - ideally it should be short and clear - whereas the title can handle longform names for pages/documents.

## Versioning the Docs Site

When a new OSM release is cut, the docs site should be updated to reflect the version change. The underlying Docsy theme has versioning support built-in.

<img width="244" alt="Screen Shot 2020-10-27 at 11 25 23 AM" src="https://user-images.githubusercontent.com/686194/97345732-a979ab80-1847-11eb-8c42-1b52c422a722.png">

## Release and Versioning Process:

1. Create an archive of the current `main` branch, following the naming convention used by [prior releases](https://github.com/openservicemesh/osm/branches). Push this archival branch to `upstream`.

<img width="301" alt="Screen Shot 2020-10-27 at 11 11 17 AM" src="https://user-images.githubusercontent.com/686194/97343954-5999e500-1845-11eb-96f4-d9d59352a830.png">

2. Once a release version branch is pushed to `upstream`, Netlify will build and deploy the documentation found within that branch. Within a couple of minutes of the branch push, the version of the site should be accessible at `https://<BRANCHNAME>--osm-docs.netlify.app/`

```
example:
release-v0-7--osm-docs.netlify.app
```

Test the url for the branch once deployed to ensure it is working.

3. Update the site version menu to reflect the changes

<img width="723" alt="Screen Shot 2020-10-27 at 11 36 02 AM" src="https://user-images.githubusercontent.com/686194/97346387-9ca98780-1848-11eb-8179-523dcbed79c0.png">

The version dropdown menu in set in the sites' `config.toml` (L73) file - adding a new `params.versions` archival entry for the prior release/branch, using the url from Netlify. The current release at the top of the list should reflect (i) the new version and (ii) the primary docs website url.

Example _(where v5 is new and v4 is now an archival prior release):_

```
[[params.versions]]
  version = "v0.5"
  url = "https://docs.openservicemesh.io"

[[params.versions]]
  version = "v0.4"
  url = "https://release-v0.4--osm-docs.netlify.app"
```

See [the Doscy versioning docs](https://www.docsy.dev/docs/adding-content/versioning/) for more information on these theme config parameters.

> Note: the versioning controls are forward-facing only due to the nature of git branch history. The documentation website and netlify build process was added after `release-v0.4`, so only future releases will be deployed in this manner. The first release to be properly archived in this way will be `release-v0.5`. Trying to access archival urls for earlier versions (0.1 to 0.4) will not work because they predate this documentation website.



# Site Development

## Notes

* built with the [Hugo](https://gohugo.io/) static site generator
* custom theme uses [Docsy](https://www.docsy.dev/) as a base, with [Bootstrap](https://getbootstrap.com/) as the underlying css framework and some [OSM custom sass](https://github.com/openservicemesh/osm/pull/1840/files#diff-374e78d353e95d66afe7e6c3e13de4aab370ffb117f32aeac519b15c2cbd057aR1)
* deployed to [Netlify](https://app.netlify.com/sites/osm-docs/deploys) via merges to main. (@flynnduism can grant additional access to account)
* metrics tracked via Google Analytics

## Install dependencies:

* Hugo [installation guide](https://gohugo.io/getting-started/installing/)  
* NPM packages are installed by running `yarn`. [Install Yarn](https://yarnpkg.com/getting-started/install) if you need to.  

## Run the site:

```
// install npm packages
yarn

// rebuild the site (to compile latest css/js)
hugo

// or serve the site for local dev
hugo serve
```

## Deploying the site:

The site auto deploys the main branch via [Netlify](https://app.netlify.com/sites/osm-docs). Once pull requests are merged the changes will appear at docs.openservicemesh.io after a couple of minutes. Check the [logs](https://app.netlify.com/sites/osm-docs/deploys) for details.

[![Netlify Status](https://api.netlify.com/api/v1/badges/8c8b7b52-b87f-42e0-949a-a784c3ca6d9a/deploy-status)](https://app.netlify.com/sites/osm-docs/deploys)

`hugo serve` will run the site locally at [localhost:1313](http://localhost:1313/)

##### How to Add a Blog Post

If you'd like to submit an OSM-related blog post to the site, we are happy to consider your contribution.

Blog posts are created via pull requests. You can test locally with hugo and/or see the preview after submitting the pull request.

Add a new file to the `content/blog/` directory whose name is the hyphen-delimited title. The files must be markdown formatted. See the [existing titles for examples](https://github.com/openservicemesh/osm-www/tree/main/content/blog) of the format. Add the header meta-data to the file using this format (note the permalink structure). Recommended but optional fields are authorname which should be name(s); these are displayed verbatim. authorlink is the link used by authorname.

```
---
title: "A Fancy Title"
slug: "fancy-title"
authorname: "Captain Awesome"
authorlink: "https://example.com"
date: "2020-03-15T09:00:00+08:00"
---
```

Add the content below the ``---`` as Markdown. The title does not need to be included in this section. Any images should be placed in the `/content/blog/images/` directory. Images should be losslessly compressed to reduce their size. Tools, such as ImageOptim, can be used.

To summarize the content on the blog index page, insert a ``<!--more-->`` break in your markdown. This will truncate the content with a Read More link.



#### Editing the Theme

The site uses a custom Hugo theme called [clean-landing], which is a boilerplate based off of the [hugo-fresh](https://themes.gohugo.io/hugo-fresh/) theme by Luc Perkins. The theme uses the Bulma css framework, which provides a mobile-friendly reponsive grid (using flexbox), icon sets and easily configurable site parameters.

* [Theme parameters](https://github.com/openservicemesh/osm-website/blob/main/config.yaml#L10)
* [Bulma CSS docs](https://bulma.io/)

Any design changes should be to the source SASS files here, which are will generate new CSS files each time Hugo recompiles, via [hugo pipes](https://gohugo.io/hugo-pipes/). Remember to commit any changes to the generated css/js files afterwards (the `/resources` folder)!


## Deployment

The site is automatically rebuilt on Netlify when changes are merged into `main` branch. You view build logs by clicking on the badge below:

[![Netlify Status](https://api.netlify.com/api/v1/badges/20d9e614-d807-496f-ade7-99510b5fd12c/deploy-status)](https://app.netlify.com/sites/openservicemesh/deploys)

## Trademarks

This project may contain trademarks or logos for projects, products, or services. Authorized use of Microsoft trademarks or logos is subject to and must follow [Microsoft's Trademark & Brand Guidelines](https://www.microsoft.com/en-us/legal/intellectualproperty/trademarks/usage/general). Use of Microsoft trademarks or logos in modified versions of this project must not cause confusion or imply Microsoft sponsorship. Any use of third-party trademarks or logos are subject to those third-party's policies.

## Contributing

If you would like to contribute to the OSM website, see [CONTRIBUTING.md](CONTRIBUTING.md).

## Code of Conduct

This project has adopted the [CNCF Code of Conduct](https://github.com/cncf/foundation/blob/master/code-of-conduct.md). See [CODE_OF_CONDUCT.md](CODE_OF_CONDUCT.md) for further details.
