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
