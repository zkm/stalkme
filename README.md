# StalkMe (jQuery Lifestream)

A simple static site bundling the jQuery Lifestream plugin and examples for generating an aggregated social activity stream from multiple services.

This repo contains the plugin sources, service adapters, CSS, and several HTML demos under `source/` and the root. It’s suitable for viewing locally or hosting with GitHub Pages.

## Features
- Aggregates updates from many services (Twitter, GitHub, YouTube, etc.).
- Drop-in jQuery plugin (`jquery.lifestream.js`).
- Example pages and CSS for quick start.

## Quick Start
1. Open any demo HTML, e.g. [index.html](index.html) or [source/example.html](source/example.html).
2. Ensure jQuery and `jquery.lifestream.js` are included.
3. Initialize on a container:

```html
<div id="lifestream"></div>
<script>
  $(function () {
    $('#lifestream').lifestream({
      list: [
        { service: 'github', user: 'octocat' },
        { service: 'twitter', user: 'jack' }
      ]
    });
  });
</script>
```

Service adapter files live in [source/src/services](source/src/services). See existing adapters for required fields.

## Development
- Primary plugin sources: [source/src/core.js](source/src/core.js) and [source/src/services/*](source/src/services).
- Built/minified files: [source/jquery.lifestream.min.js](source/jquery.lifestream.min.js).
- Styles: [css/lifestream.css](css/lifestream.css) and [source/css/lifestream.css](source/css/lifestream.css).

### Building
Legacy build scripts are available under [source/build](source/build). They don’t require modern Node tooling; however, they are optional. For most uses you can load `jquery.lifestream.js` directly.

## CI / Deployment
This repo includes a GitHub Actions workflow that:
- Runs basic lint checks for HTML/CSS/JS.
- Publishes the repository to GitHub Pages when pushing to `main`/`master`.

Enable GitHub Pages:
- In your repository settings, set Pages source to “GitHub Actions”.

## Contributing
- Add new service adapters in [source/src/services](source/src/services) following existing patterns.
- Keep plugin API stable; avoid breaking changes.
- Open a PR with clear description and a demo if possible.

## License
See [source/LICENSE](source/LICENSE).
