Bucks Sauce — static HTML clone (homepage)

Folder contents
  index.html   Full page: markup + CSS + JS in one file
  assets/      All images (logo, bottles, packs, characters, food cutouts, dishes)

How to run
  Open index.html directly in a browser, or serve the folder:
    python3 -m http.server 8000   ->  http://localhost:8000

Notes
  - Tailwind is loaded from the CDN (cdn.tailwindcss.com) and fonts (Anton +
    Inter Tight) from Google Fonts, so an internet connection is needed.
  - Everything else (images, animations, carousel, sticky stacks, loader,
    scroll-pinned steps, marquees) is local and dependency-free vanilla JS.
