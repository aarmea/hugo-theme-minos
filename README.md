# Minos

**_A simple and retro styled theme, concentrated more on your ideas._**

Minos is a Hugo theme ported from Hexo theme [Minos](https://github.com/ppoffice/hexo-theme-minos). Requires Hugo v0.20+.

## Screenshots

![Home](https://cdn.rawgit.com/carsonip/hugo-theme-minos/cb2cdd88/images/screenshot.png)
![Article](https://cdn.rawgit.com/carsonip/hugo-theme-minos/cb2cdd88/images/article.png)
![Tag](https://cdn.rawgit.com/carsonip/hugo-theme-minos/cb2cdd88/images/tag.png)

## Features

* Everything in the original Mino theme, except
    * Gallery (fancybox)
    * Duoshuo comment
    * Search box
    * Hierarchical categories (since this isn't supported in Hugo)
* Smart table of contents (will highlight and expand current section in TOC)
* Disqus
* Google Analytics
* [KaTeX](https://github.com/Khan/KaTeX)
* Syntax highlighting using [highlight.js](https://github.com/isagalaev/highlight.js)
* Automatically playing and pausing videos as they become (in)visible while scrolling

## Installation

To install Minos as your theme, first clone this repository in the `themes/` directory:

```
$ cd themes/
$ git clone --depth 1 https://github.com/carsonip/hugo-theme-minos
```

Second, specify `hugo-theme-minos` as your default theme in the config.toml file. Just add the line

```
theme = "hugo-theme-minos"
```

## Options

### Pagination
```
paginate = 10
```

### Smart TOC
```
[params]
    smartToc = true
```

### Disqus
```
[params]
    disqusShortname = "xxxxxx"
```

### Google Analytics
```
[params]
    googleAnalytics = "UA-123-45"
```

### KaTeX
```
[params]
    katex = true
```

For other configuration variables, visit [Hugo documentation](https://gohugo.io/overview/configuration/#configuration-variables).

## Post Params

### Featured Image displayed in index.html
```
+++
featuredImage = "img/foobar.jpg"
+++
```

### Whether a page is a blog post
```
+++
blogpost = true
+++
```

If it is not set, the generated page will not have a date or navigation to the
next or previous post. If your site overrides the default archetypes, it is
recommended to also add this line to your archetypes for blog-like sections.

## Usage

### Automatically playing and pausing videos with scrolling

VP9 (and H.264 to a lesser extent) are great at keeping file sizes down, but
with the tradeoff of expensive CPU-based decoding if your GPU does not support
it. This feature lets you use these formats in place of GIFs for short, silent,
and repeating videos to save on bandwidth without paying the CPU cost when the
video is not visible.

To use it, place your VP9 and fallback videos somewhere accessible and add it to
your article using the `<video>` tag with the `playpause-with-visibility` class:

```
<video autoplay muted loop class="playpause-with-visibility">
  <source src="/path/to/your/video.webm" type="video/webm">
  <source src="/path/to/your/video.mp4" type="video/mp4">
</video>
```

`autoplay` is needed to have behavior that is as close as possible with
JavaScript disabled.

The script interprets `loop` to mean that the video is GIF-like. If `loop` is
specified, the script will also mute the video and disable controls.

Please be a good Net citizen by refraining from autoplaying videos with sound,
regardless of whether you use this feature.

## Contributing

1. Fork it!
2. Create your feature branch: `git checkout -b my-new-feature`
3. Commit your changes: `git commit -am 'Add some feature'`
4. Push to the branch: `git push origin my-new-feature`
5. Submit a pull request :D

## Original Author

PPOffice

* https://github.com/ppoffice

## Ported by

Carson Ip

* https://github.com/carsonip

## License

Licensed under the MIT License. See the [LICENSE](https://github.com/carsonip/hugo-theme-minos/blob/master/LICENSE.md) file for more details.
