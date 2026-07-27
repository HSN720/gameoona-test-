============================================================
GAMEOONA — GITHUB PAGES DEPLOYMENT PACKAGE
============================================================

TARGET
  Repository:  gameoona-test-      (note the trailing hyphen)
  Live URL:    https://hsn720.github.io/gameoona-test-/
  Base path:   /gameoona-test-     (basePath + assetPrefix)

BUILD DATE
  2026-07-26 — includes: full mobile responsiveness pass (mobile
  sticky-hero reveal, gsap.matchMedia mobile animation timelines, resize/
  orientation ScrollTrigger.refresh, 44px+ touch targets), General Sans
  body typography, craft-counter readability fix, and the mobile header fix.

WHAT THIS IS
  A complete static export built for the GitHub Pages project subpath
  /gameoona-test-/. THIS folder (/hosting) IS the site root — there is no
  nested out/, website/ or hosting/ sub-folder.

HOW TO DEPLOY (replace the repo contents)
  Put the CONTENTS of this /hosting folder at the ROOT of the
  "gameoona-test-" repository (on the branch GitHub Pages serves).
  The repo root must contain:

     index.html   404.html   .nojekyll
     _next/   craft/   privacy/   terms/
     1.png ... 4.png   favicon.svg
     robots.txt   sitemap.xml   manifest.webmanifest   README.txt

  Do NOT nest these inside another folder. index.html must sit at the
  repository root so it is served at /gameoona-test-/index.html.

  .nojekyll is REQUIRED: without it GitHub Pages' Jekyll step strips the
  _next/ folder (underscore-prefixed) and the site loads as unstyled text.

BUILD (how this was produced)
  next.config.mjs: output "export", trailingSlash true,
  basePath/assetPrefix "/gameoona-test-", images.unoptimized true.
  In ../website:  npm ci && npm run build   ->  website/out copied here.
  Public assets (images, favicon) are prefixed with the base path in code
  via lib/base.ts. If the repo name changes, update BOTH next.config.mjs
  and lib/base.ts.

NOTES
  * Brand fonts load from the Fontshare CDN (Clash Display + General Sans).
  * .htaccess is intentionally omitted: GitHub Pages ignores it.
  * The icon is favicon.svg; add a favicon.ico only for legacy support.
============================================================
