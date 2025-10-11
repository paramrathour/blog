# Wrath's blog

[![Gem Version](https://img.shields.io/gem/v/jekyll-theme-chirpy)][gem]&nbsp;

This website is created using [Chirpy Starter](chirpy-starter) and is hosted by [GitHub Pages](https://pages.github.com/).

## Repository Structure
This repository contains only _critical_ files used for making the [blog](https://paramrathour.github.io/blog/), i.e., only the following kind of files
- content files (blog data and personal information)
	- `_config.yml` - configuration of the site
	- `_data` - includes contacts and sharing links
	- `pages` - includes posts and collections
	- `assets/404.html` - the `404` error page
- select design files (possibly modified) from the [GitHub fork](https://github.com/cotes2020/jekyll-theme-chirpy/commits?author=semantic-release-bot) of the current gem version
	- `_includes`
	- `_layouts`
	- `_sass`
	- `assets/js`
	- `_plugins`
	- `.github/workflows`
- submodule
	- `assets/lib` - contains self-hosted [static-assets](https://github.com/cotes2020/chirpy-static-assets)
- also, media assets such as images and documents are stored in a separate repository called [website-assets](https://github.com/paramrathour/website-assets).

This separation allows user to focus on writing blogs while keeping away
- the [design files](https://github.com/cotes2020/jekyll-theme-chirpy/commits?author=semantic-release-bot) which allows easier version upgrade.
- the media assets which reduces size of this repository.

## Usage
To build the website
- Install [Jekyll](https://jekyllrb.com/docs/installation/) and [Git](https://git-scm.com/)
- Clone the repository using `git clone --recursive https://github.com/paramrathour/blog`
- In the repository directory,
	- run `bundle` to install dependencies
	- run `JEKYLL_ENV=production bundle exec jekyll serve` and open the website locally using the displayed URL

To create posts 
- Use [Jekyll Compose](https://github.com/jekyll/jekyll-compose) commands to work with draft posts and then publish the drafts

## Features
### Added
- Toggle `paginator_enable` in the `_config.yml` to enable/disable pagination: [@c8a9dc1](https://github.com/paramrathour/blog/commit/c8a9dc11ca9b64b935661dc9d1da96611fdd8861)
- 404 page [file](https://github.com/paramrathour/blog/blob/main/assets/404.html)
- Reading time and last modified date on the home page: [file](https://github.com/paramrathour/blog/commits/main/_layouts/home.html), [@8237eed](https://github.com/paramrathour/blog/commit/8237eed3d5b5a43171ca8a002fa6d957916338cc), [@4c3137c](https://github.com/paramrathour/blog/commit/4c3137c21a843b9b620b61db718ce40697b192e0)
### Modified
- Cross-platform Favicon support using [realfavicongenerator](https://realfavicongenerator.net/) (suggested by [wermos](https://wermos.github.io/blog/)): [file](https://github.com/paramrathour/blog/commits/main/_includes/favicons.html), [@be29e4e](https://github.com/paramrathour/blog/commit/be29e4e61003aa9c1e7eb352b5a017ad5be92103)
- Increased search results limit: [file](https://github.com/paramrathour/blog/blob/main/_includes/search-loader.html)
- Changed collections directory: [@92b83b0](https://github.com/paramrathour/blog/commit/92b83b095c62800ab40a369b8715bbd2fa7f8785)
- Larger tooltip size: [file](https://github.com/paramrathour/blog/blob/main/_includes/tooltip-style.html), [@a0ee300](https://github.com/paramrathour/blog/commit/a0ee3005cba5c02d2f2eee8b3dbbd8805adb8ad5)
- Removed avatar-border: [@727c8ec](https://github.com/paramrathour/blog/commit/727c8ec2e7cdc5433c5a2ed674b64c07028c1315), [@677ca90](https://github.com/paramrathour/blog/commit/677ca9039006e826553ebdfe170738524b4d5ce2#diff-8c681e1a819cb60f283844738bd2c82b0f99f3018983332a85bdf05dbd4eee90)
- Persistent color scheme across browser sessions, using `localStorage` instead of `sessionStorage`: [file](https://github.com/paramrathour/blog/commits/main/_includes/mode-toggle.html)
	- Stopped working after v7.2.0 update :( [issue](https://github.com/paramrathour/blog/issues/2)

[gem]: https://rubygems.org/gems/jekyll-theme-chirpy
[chirpy]: https://github.com/cotes2020/jekyll-theme-chirpy/
[chirpy-starter]: https://github.com/cotes2020/chirpy-starter
[use-template]: https://github.com/cotes2020/chirpy-starter/generate