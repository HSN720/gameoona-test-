============================================================
GAMEOONA — GITHUB PAGES DEPLOYMENT PACKAGE
============================================================

TARGET
  Repository:  gameoona-test-      (note the trailing hyphen)
  Live URL:    https://hsn720.github.io/gameoona-test-/
  Base path:   /gameoona-test-     (basePath + assetPrefix)

BUILD DATE
  2026-07-26 (rebuilt to include: craft-counter readability fix,
  mobile hero word-spacing, and the mobile header layout fix)

WHAT THIS IS
  A complete static export built for the GitHub Pages project subpath
  /gameoona-test-/. THIS folder (/hosting) IS the site root — there is
  no nested out/, website/ or hosting/ sub-folder.

HOW TO DEPLOY (replace the repo contents)
  Put the CONTENTS of this /hosting folder at the ROOT of the
  "gameoona-test-" repository (on the branch GitHub Pages serves).
  The repo root must contain:

     index.html   404.html   .nojekyll
     _next/   craft/   privacy/   terms/
     1.png ... 4.png   favicon.svg
     robots.txt   sitemap.xml   manifest.webmanifest   README.txt

  Do NOT nest these inside another folder. index.html must be at the
  repository root so it is served at /gameoona-test-/index.html.

  .nojekyll is REQUIRED: without it GitHub Pages' Jekyll step strips the
  _next/ folder (underscore-prefixed) and the site loads as unstyled text.

BUILD (how this was produced)
  next.config.mjs:
     output: "export", trailingSlash: true,
     basePath: "/gameoona-test-", assetPrefix: "/gameoona-test-",
     images: { unoptimized: true }
  Commands (in ../website):
     npm ci && npm run build      # emits website/out -> copied here

  Public assets (images, favicon) are prefixed with the base path in code
  via lib/base.ts (asset()), because Next.js does not apply basePath to
  next/image src for /public assets or to metadata icons. If the repo name
  changes, update BOTH next.config.mjs and lib/base.ts.

NOTES
  * Brand fonts load from the Fontshare CDN via CSS (system fallbacks
    otherwise).
  * .htaccess is intentionally omitted: GitHub Pages ignores it.
  * The icon is favicon.svg; add a favicon.ico only if you want legacy
    .ico support.
============================================================
