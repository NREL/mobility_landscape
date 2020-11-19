[![CII Best Practices](https://bestpractices.coreinfrastructure.org/projects/1767/badge)](https://bestpractices.coreinfrastructure.org/projects/1767) [![Dependency Status](https://img.shields.io/david/cncf/landscape.svg?style=flat-square)](https://david-dm.org/cncf/landscape)

# Interactive Mobility Landscape

![Interactive Mobility Landscape](https://github.com/NREL/mobility_landscape/images/imdl_logo)

- [Mobility Data Landscape](#interactive-mobility-landscape)
  * [Interactive Version](#interactive-version)
  * [New Entries](#new-entries)
  * [Logos](#logos)
  * [Corrections](#corrections)
  * [External Data](#external-data)
  * [Best Practices Badge](#best-practices-badge)
  * [License](#license)
  * [Formats](#formats)
  * [Installation](#installation)
  * [Vulnerability reporting](#vulnerability-reporting)
  * [Adjusting the Landscape View](#adjusting-the-landscape-view)

The [Interactive Mobility Data Landscape](https://nrel.github.io/mobility_landscape/) is a project intended as a map through the previously uncharted, growing mobility data science field. This attempts to categorize most of the data sources, specifications, and tools in the field of mobility. It has been built by the National Renewable Energy Laboratory's (NREL) Mobility, Behavior, and Advanced Powertrain (MBAP) research group as an internship project.

The software for the interactive landscape has been extracted to https://github.com/NREL/mobility_landscapeapp/tree/master/src. This repo includes all of the data and images specific to the mobility data landscape.

## Interactive Version

Please see [nrel.github.io](https://nrel.github.io/mobility_landscape/).

## New Entries

These are the steps to go through to upload a new entry:

1. After opening a pull request to landscape.yml, add a new entry within this file. Follow the order and format of previous entries.
1. Please search through the existing Categories and Subcategories before considering to add a new one. Generally speaking, a new subcategory is not created unless mulitple examples could exist within that subcategory.
1. Survey the filter list to understand the different options available for each variable. Please ensure to follow the same formatting as other entries in the landscape. If none of the filter options fit your entry, add a new variable option.
1. Please ensure that you additionally add a logo to your new entry as well, see [Logos](#logos)

* We are unlikely to create a new category for products/projects as we'd rather find the best home with the current options.
* We are generally not including commercial versions of open source software. The exception is that we are showing all Certified Kubernetes implementations.
* Closed source products need to link to a clear description of your product; no stealth mode companies.
* Your project or company needs a logo.

If you think your company or project should be included, please open a pull request to add it to [landscape.yml](landscape.yml). For the logo, you can either upload an SVG to the `hosted_logos` directory or put a URL as the value, and it will be fetched.

## Logos

The following rules will produce the most readable and attractive logos:

1. When multiple variants exist, use stacked (not horizontal) logos. For example, we use the second column (stacked), not the first (horizontal), of CNCF project [logos](https://github.com/cncf/artwork/#cncf-incubating-logos).
1. Don't use reversed logos (i.e., with a non-white, non-transparent background color). If you only have a reversed logo, create an issue with it attached and we'll produce a non-reversed version for you.
1. Match the item name to the English words in the logos. So an Acme Rocket logo that shows "Rocket" should have product name "Rocket", while if the logo shows "Acme Rocket", the product name should be "Acme Rocket". Otherwise, logos looks out of place when you sort alphabetically.
1. Logos shouldn't include a tagline, which allows them to be larger and more readable. The only exception is if the only format that the logo is ever shown includes the tagline.
1. Google images is often the best way to find a good version of the logo (but ensure it's the up-to-date version). Search for [grpc logo filetype:svg](https://www.google.com/search?q=grpc+logo&tbs=ift:svg,imgo:1&tbm=isch) but substitute your project or product name for grpc.
1. You can either upload an SVG to the `hosted_logos` directory or put a URL as the value, and it will be fetched.

## Corrections

Please open a pull request with edits to [landscape.yml](landscape.yml). The file [processed_landscape.yml](processed_landscape.yml) is generated and so should never be edited directly.

If your project isn't showing the license correctly, you may need to paste the unmodified text of the license into a LICENSE file at the root of your project in GitHub, in order for GitHub to serve the license information correctly.

## External Data

The canonical source for all data is [landscape.yml](landscape.yml). Once a day, we download data for projects and companies from the following sources:

* Project info from GitHub
* Market cap data from Yahoo Finance
* CII Best Practices Badge [data](https://bestpractices.coreinfrastructure.org/)

The update server enhances the source data with the fetched data and saves the result in [processed_landscape.yml](processed_landscape.yml) and as a JSON [file] (https://nrel.github.io/mobility_landscape/data.json), the latter of which is what the app loads to display data.

## Best Practices Badge

As explained at https://bestpractices.coreinfrastructure.org/:
>The Linux Foundation (LF) Core Infrastructure Initiative (CII) Best Practices badge is a way for Free/Libre and Open Source Software (FLOSS) projects to show that they follow best practices. Projects can voluntarily self-certify, at no cost, by using this web application to explain how they follow each best practice. The CII Best Practices Badge is inspired by the many badges available to projects on GitHub. Consumers of the badge can quickly assess which FLOSS projects are following best practices and as a result are more likely to produce higher-quality secure software. The interactive landscape displays the status (or non-existence) of a badge for each open-source project.

## License

Everything else is under the Apache License, Version 2.0, except for project and product logos, which are generally copyrighted by the company that created them, and are simply cached here for reliability. The trail map, static landscape, serverless landscape, and [landscape.yml](landscape.yml) file are alternatively available under the [Creative Commons Attribution 4.0 license](https://creativecommons.org/licenses/by/4.0/).

## Formats

The Mobility Landscape is available in these formats:

* [PNG](https://nrel.github.io/mobility_landscape/images/landscape.png)
* [PDF](https://nrel.github.io/mobility_landscape/images/landscape.pdf)

## Installation

You can install and run locally with the [install directions](https://github.com/NREL/mobility_landscapeapp#installing-locally). It's not necessary to install locally if you just want to edit [landscape.yml](landscape.yml). You can do so via the GitHub web interface.

## Vulnerability reporting

Please open an [issue](https://github.com/NREL/mobility_landscape/issues) or, for sensitive information, email k.shankari@nrel.gov.

## Adjusting the Landscape View
The file src/components/MainContent2.js describes the key elements of a
landscape big picture. It specifies where to put these sections: App Definition
and Development, Orchesteration & Management, Runtime,  Provisioning, Cloud,
    Platform, Observability and Analyzis, Special. Also it specifies where to
    locate the link to the serverless preview and an info with a QR code.

All these elements should have `top`, `left`, `width` and `height` properties to
position them. `rows` and `cols` specify how much columns or rows we expect in a
given horizontal or vertical section. 

When we see that those elements can not fit the sections, we need to either increase
the width of all the horizontal sections, or increase height and amount of rows
in a single horitzontal section and adjust the position of sections below.

Beside that, we have to adjust the width of a parent div (1620), the width in a
`src/components/BigPicture/FullscreenLandscape.js` (1640) and the width in a
`tools/renderLandscape.js` (6560, because of x4 zoom and margins)

Serverless has a same approach, files are
`src/components/BigPicture/ServerlessContent.js`,
  `src/components/BigPicture/FullscreenServerless.js` and
  `tools/renderLandscape.js`, with a full width of 3450 (because of x3 zoom and
      margins)

Sometimes the total height is changed too, then we need to adjust the height the
same way as we adjust the width.

We have an experimental `fitWidth` property, it is good when you want to get rid of
an extra space on the right of a section.

The best way to test that layout is ok, is to visit `/landscape` and
`/serverless`, and if it looks ok, run `PORT=3000 babel-node
tools/renderLandscape` and see the rendered png files, they are in `src/images`
folder
