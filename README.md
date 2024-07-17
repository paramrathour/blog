# Chirpy - Jekyll Theme

[![Gem Version](https://img.shields.io/gem/v/jekyll-theme-chirpy)][gem]&nbsp;
[![GitHub license](https://img.shields.io/github/license/cotes2020/chirpy-starter.svg?color=blue)][mit]

[Chirpy](chirpy) theme created using [Chirpy Starter](chirpy-starter) and hosted by [GitHub Pages](https://pages.github.com/).

This repository contains only _critical_ files used for making [this](https://paramrathour.github.io/blog/) blog, i.e., only those files that are useful for writing and ignores the irrelevant project files. This allows user to focus on writing blogs, keeping away the design aspects which also makes the template easier to upgrade.

Moreover, media assets such as images and documents are stored in a seperate repository called [website-assets](https://github.com/paramrathour/website-assets).

## Prerequisites
Follow the instructions in the [Jekyll Docs](https://jekyllrb.com/docs/installation/) to complete the installation of the basic environment. [Git](https://git-scm.com/) also needs to be installed.

## Installation
Sign in to GitHub and [**use Chirpy's template**][use-template] to generate a brand new repository and name it `USERNAME.github.io`, where `USERNAME` represents your GitHub username.

Then clone it to your local machine and run:

```console
$ bundle
```

## Usage
Please see the [theme's documentation](https://github.com/cotes2020/jekyll-theme-chirpy/wiki).

## Features Added/Modified
- Cross-platform Favicon support using [realfavicongenerator](https://realfavicongenerator.net/) (suggested by [Tirthankar](https://wermos.github.io/blog/)): [@be29e4e](https://github.com/paramrathour/blog/commit/be29e4e61003aa9c1e7eb352b5a017ad5be92103), [@3c37f4b](https://github.com/paramrathour/blog/commit/3c37f4bd881e346e143926d49a53855b3556fa8b), [@677ca90](https://github.com/paramrathour/blog/commit/677ca9039006e826553ebdfe170738524b4d5ce2#diff-e0cabb2a214bd2a1faee7bd1d3e767d217639b4b6cc38643c2b21b00a93cebd6)
- Toggle `paginator_enable` in the `_config.yml` to enable/disable pagination: [@c8a9dc1](https://github.com/paramrathour/blog/commit/c8a9dc11ca9b64b935661dc9d1da96611fdd8861)
- Larger tooltip size: [file](https://github.com/paramrathour/blog/blob/main/_includes/tooltip-style.html), [@a0ee300](https://github.com/paramrathour/blog/commit/a0ee3005cba5c02d2f2eee8b3dbbd8805adb8ad5)
- Changed collections directory: [@92b83b0](https://github.com/paramrathour/blog/commit/92b83b095c62800ab40a369b8715bbd2fa7f8785)
- Removed avatar-border: [@727c8ec](https://github.com/paramrathour/blog/commit/727c8ec2e7cdc5433c5a2ed674b64c07028c1315), [@677ca90](https://github.com/paramrathour/blog/commit/677ca9039006e826553ebdfe170738524b4d5ce2#diff-8c681e1a819cb60f283844738bd2c82b0f99f3018983332a85bdf05dbd4eee90)
- Increased search results limit: [file](https://github.com/paramrathour/blog/blob/main/_includes/search-loader.html)
- Post description in search results: [file](https://github.com/paramrathour/blog/blob/main/assets/js/data/search.json)
<!-- https://github.com/paramrathour/blog/commit/0ec971753fdca08f84b937d1edd775d52fc04e0d, https://github.com/paramrathour/blog/commit/f0dd0ee49f8532d28908efdb1b9a32bb4255f880 -->
- 404 page [file](https://github.com/paramrathour/blog/blob/main/assets/404.html)
## License

This work is published under [MIT][mit] License.

[gem]: https://rubygems.org/gems/jekyll-theme-chirpy
[chirpy]: https://github.com/cotes2020/jekyll-theme-chirpy/
[chirpy-starter]: https://github.com/cotes2020/chirpy-starter
[use-template]: https://github.com/cotes2020/chirpy-starter/generate
[CD]: https://en.wikipedia.org/wiki/Continuous_deployment
[mit]: https://github.com/cotes2020/chirpy-starter/blob/master/LICENSE
