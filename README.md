# svPkgdown <a href='https://www.sciviews.org/svPkgdown'><img src='man/figures/logo.png' align="right" height="134.5" /></a>

<!-- badges: start -->
[![Project Status: WIP – Initial development is in progress, but there
has not yet been a stable, usable release suitable for the
public.](https://www.repostatus.org/badges/latest/wip.svg?branch=master)](https://www.repostatus.org/#wip)
[![Linux build Status](https://api.travis-ci.com/SciViews/svPkgdown.svg )](https://travis-ci.com/github/SciViews/svPkgdown)
<!-- badges: end -->

The 'svPkgdown' R package provides a custom style for SciViews R package sites generated automatically with 'pkgdown'. Please don't use it for your own purpose outside of the https://www.sciviews.org web site!

Inspired by [tidytemplate](https://github.com/tidyverse/tidytemplate/), [lockedatapkg](https://github.com/lockedatapublished/lockedatapkg) and [rotemplate](https://github.com/ropensci/rotemplate).

## How to use 'svPkgdown'

Starting from a Github Repository for an R package with no 'pkgdown' site yet,

1. upgrade `usethis` to the latest development version using `remotes::install_github("r-lib/usethis")`.
2. In you Github repo do `usethis::use_pkgdown()` then, `pkgdown::build_site_external()` to view how it renders with all defaults.
3. Add `docs` and `docs/` in `.gitignore` to avoid pushing your local version of the site to Github.
4. Edit `_pkgdown.yml`. For SciViews, a custom template is used by means of this `svPkgdown` package, based on the bootstrap `spacelab` template. You may also place additional infor for the authors, for instance:

``` yaml
destination: docs
template:
  params:
    bootswatch: spacelab
    mathjax: true
authors:
  Philippe Grosjean:
    href: https://phgrosjean.sciviews.org/
```

5. Regenerate your site with `pkgdown::build_site_external()`, or from RStudio, from the corresponding addin. Check its appearance.
6. Create a Github action to automatically regenerate the site on Github on every push with `usethis::use_github_action("pkgdown.yaml")`.
7. Commit and push, then check if the action is trigerred (click on the little icon on the left of "Latest commit ..." on the main page of the repo.
8. In the repo settings, activate or reactivate **Github Pages** -> **source** -> "gh-pages branch". You may also check "Enforce HTTPS". Navigate to your site (the URL is provided directly in the settings page). If it does not work, try another push to refresh the site.
9. Once your site is operational, refer to it in the main page of your repo (edit the description at the top, and may be alsdo place a link to it in the `README.md` file).

Further explanations on how to customize the 'pkgdown' site [here](https://github.com/tidyverse/tidytemplate).

## Example sites

  - [`svUnit`](https://www.SciViews.org/svUnit/)

  - [`svGUI`](https://www.SciViews.org/svGUI/)

  - [`svMisc`](https://www.SciViews.org/svMisc/)

## Installation

You can install the latest version of 'svPkgdown' from Github. Make sure you have the 'devtools' R package installed:

```r
install.packages("devtools")
```

Use `install_github()` to install the 'svPkgdown' package from Github (source from **master** branch will be recompiled on your machine):

```r
devtools::install_github("SciViews/svPkgdown")
```

R should install all required dependencies automatically, and then it should compile and install 'svPkgdown'.

## Further explore 'svPkgdown'

You can get further help about this package this way:

```r
library(help = "svPkgdown")
pckage?svPkgdown
vignette("svPkgdown") # None is installed with install_github()
```

For further instructions, please, refer to the related web site at https://www.sciviews.org/svPkgdown/.

## Code of Conduct

Please note that the svSweave project is released with a [Contributor Code of Conduct](https://contributor-covenant.org/version/2/0/CODE_OF_CONDUCT.html). By contributing to this project, you agree to abide by its terms.
