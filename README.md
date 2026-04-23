# CUSTOM VERSION (with a modifed worklow)

- add javascript-kernels (iframe and worker)
- remove PS5 kernel
- add extension to open notebook from URL - [jupyterlab-open-url-parameter](https://jupyterlite.readthedocs.io/en/stable/howto/content/open-url-parameter.html)

Every change in the code trigger the workflow (github action) then download the created artifact (the link is in Actions/*choose the last run*/build/upload artifact/artifact download url)

Unzip the folder and run a webserver (ie `npx http-server`)

To remove menus on the "notebook" version, add the following css in the file /notebooks/index.html

```html
...
<meta name="Description" content="WASM powered Jupyter running in the browser." />
<style type="text/css">
  .jp-nb-interface-switcher-button {
    visibility: hidden;
  }

  #top-panel-wrapper, #menu-panel-wrapper {
    display: none !important;
    height: 0 !important;
    min-height: 0 !important;
    margin: 0 !important;
    padding: 0 !important;
    border: 0 !important;
  }

</style>
<link rel="manifest" href="../manifest.webmanifest" />
...
```
It's also possible to see the generated version of jupyterlite on github pages https://ae3e.github.io/jupylitedemo

There's 3 main url :
- https://ae3e.github.io/jupylitedemo/lab for the `lab` version
- https://ae3e.github.io/jupylitedemo/tree for the files explorer of the `notebooks` version
- https://ae3e.github.io/jupylitedemo/notebooks/?path=python.ipynb to display a single notebook with the `notebooks` version

# JupyterLite Demo

[![lite-badge](https://jupyterlite.rtfd.io/en/latest/_static/badge.svg)](https://jupyterlite.github.io/demo)

JupyterLite deployed as a static site to GitHub Pages, for demo purposes.

## ✨ Try it in your browser ✨

➡️ **https://jupyterlite.github.io/demo**

![github-pages](https://user-images.githubusercontent.com/591645/120649478-18258400-c47d-11eb-80e5-185e52ff2702.gif)

## Requirements

JupyterLite is being tested against modern web browsers:

- Firefox 90+
- Chromium 89+

## Deploy your JupyterLite website on GitHub Pages

Check out the guide on the JupyterLite documentation: https://jupyterlite.readthedocs.io/en/latest/quickstart/deploy.html

## Further Information and Updates

For more info, keep an eye on the JupyterLite documentation:

- How-to Guides: https://jupyterlite.readthedocs.io/en/latest/howto/index.html
- Reference: https://jupyterlite.readthedocs.io/en/latest/reference/index.html

This template provides the Pyodide kernel (`jupyterlite-pyodide-kernel`), the JavaScript kernel (`jupyterlite-javascript-kernel`), and the p5 kernel (`jupyterlite-p5-kernel`), along with other
optional utilities and extensions to make the JupyterLite experience more enjoyable. See the
[`requirements.txt` file](requirements.txt) for a list of all the dependencies provided.

For a template based on the Xeus kernel, see the [`jupyterlite/xeus-python-demo` repository](https://github.com/jupyterlite/xeus-python-demo)


