# 'pkgdown' Template for SciViews Packages <a href='https://www.sciviews.org/svPkgdown'><img src="man/figures/logo.png" align="right" height="134.5"/></a>

<!-- badges: start -->

[![R-CMD-check](https://github.com/SciViews/svPkgdown/actions/workflows/R-CMD-check.yaml/badge.svg)](https://github.com/SciViews/svPkgdown/actions/workflows/R-CMD-check.yaml) [![Codecov test coverage](https://codecov.io/gh/SciViews/svPkgdown/branch/main/graph/badge.svg)](https://codecov.io/gh/SciViews/svPkgdown?branch=main) [![CRAN status](https://www.r-pkg.org/badges/version/svPkgdown)](https://cran.r-project.org/package=svPkgdown) [![r-universe status](https://sciviews.r-universe.dev/badges/svPkgdown)](https://sciviews.r-universe.dev/svPkgdown) [![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT) [![Lifecycle: stable](https://img.shields.io/badge/lifecycle-stable-brightgreen.svg)](https://www.tidyverse.org/lifecycle/#stable)

<!-- badges: end -->

The {svPkgdown} package provides a custom style for SciViews R package sites generated automatically with {pkgdown}. Please don't use it unmodified for your own purpose outside of the <https://www.sciviews.org> web site (but you can reuse it as a starting point from your own template if you wish)!

Inspired by [tidytemplate](https://github.com/tidyverse/tidytemplate/), [lockedatapkg](https://github.com/lockedatapublished/lockedatapkg) and [rotemplate](https://github.com/ropensci/rotemplate).


## Installation

Being specific to SciViews packages, {svPkgdown} will never be available from CRAN. You can install it from the [SciViews R-Universe](https://sciviews.r-universe.dev) this way:

``` r
install.packages(c('svPkgdown', 'pkgdown'),
  repos = c('https://sciviews.r-universe.dev', 'https://cloud.r-project.org'))
```

You can install the latest version of {svPkgdown} from GitHub. Make sure you have the {devtools} R package installed:

``` r
install.packages("remotes")
```

Use `install_github()` to install {svPkgdown} from GitHub (source from **main** branch will be recompiled on your machine):

``` r
remotes::install_github("SciViews/svPkgdown")
```

R should install all required dependencies automatically, and then it should compile and install {svPkgdown}.


## How to use {svPkgdown}

Starting from a GitHub repository for an R package with no {pkgdown} site yet,

-   upgrade {usethis} to the latest development version using `remotes::install_github("r-lib/usethis")` if needed.
-   In you GitHub repo do `usethis::use_pkgdown()` then, `pkgdown::build_site()` to view how it renders with all defaults.
-   Add `docs` and `docs/` in `.gitignore` to avoid pushing your local version of the site to GitHub.
-   Edit `_pkgdown.yml`. For SciViews, a custom template is used by means of this {svPkgdown} package, based on the bootstrap `spacelab` template. You may also place additional information for the authors, for instance:

``` yaml
url: https://www.sciviews.org/svPkgdown

destination: docs

development:
  mode: auto

template:
  package: svPkgdown
  bootstrap: 3
  bootswatch: spacelab
  params:
    mathjax: true
  bslib:
    pkgdown-nav-height: 80px
    code_font: {google: "JetBrains Mono"}

toc:
  depth: 3

navbar:
  structure:
    left:  [intro, reference, articles, tutorials, news]
    right: [search, github]

home:
  strip_header: true

authors:
  Philippe Grosjean:
    href: https://phgrosjean.sciviews.org/
```

-   Regenerate your site with `pkgdown::build_site()`, or from RStudio, from the corresponding addin. Check its appearance.
-   Create a GitHub action to automatically regenerate the site on GitHub on every push with `usethis::use_github_action("pkgdown")`.
-   Commit and push, then check if the action is run (click on the little icon on the left of "Latest commit ..." on the main page of the repository).
-   In the repo settings, activate or reactivate **Pages** -\> **source** -\> "gh-pages branch" -\> **/root**. You may also check "Enforce HTTPS". Navigate to your site (the URL is provided directly in the settings page). If it does not work, try another push to refresh the site.
-   Once your site is operational, refer to it in the main page of your repo (edit the description at the top, and may be also place a link to it in the `README.md` file).

Further explanations on how to customize the {pkgdown} site [here](https://github.com/tidyverse/tidytemplate).


## Example sites

-   [{svUnit}](https://www.SciViews.org/svUnit/)

-   [{svGUI}](https://www.SciViews.org/svGUI/)

-   [{svMisc}](https://www.SciViews.org/svMisc/)


## Further explore {svPkgdown}

You can get further help about this package this way:

``` r
library(help = "svPkgdown")
package?svPkgdown
vignette("svPkgdown") # None is installed with install_github()
```

For further instructions, please, refer to the related web site at <https://www.sciviews.org/svPkgdown/>.


## Code of Conduct

Please note that the {inferit} package is released with a [Contributor Code of Conduct](https://contributor-covenant.org/version/2/1/CODE_OF_CONDUCT.html). By contributing to this project, you agree to abide by its terms.
