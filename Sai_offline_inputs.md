$ Todo
# Humans LLM's switch

i saw the parallel.ai website which has this toggle of Human, Machine and when we select machine the entire page gets rendered into text format. we can do that for hextra pages as well

## relevant docs from Hextra
https://imfing.github.io/hextra/docs/guide/configuration/#llmstxt-support

LLMS.txt Support 
To enable llms.txt output format for your site, which provides a structured text outline for large language models and AI agents, add the llms output format to your site’s hugo.yaml:

hugo.yaml
outputs:
- home: [html]
+ home: [html, llms]
  page: [html]
  section: [html, rss]

This will generate an llms.txt file at your site’s root containing:

Site title and description
Hierarchical listing of all sections and pages
Page summaries and publication dates
Direct links to all content
The llms.txt file is automatically generated from your content structure and makes your site more accessible to AI tools and language models for context and reference.

---
# Done

# new landing page
I think Landing on about page is not that appealing. the home page should be small intro of me with small photo then followed by recent blog + recent TIL followed by recent projects

_________________________________
|title: A V S Sai Babu          |
|short summary  | small photo   |
|recent TIL    | Recent blog    |
|Projects summary cards         |
---------------------------------

# Website icon
Owl line icon. love owls and its connototation with wisdom etc.

## Relevant Docs from Hextra:
https://imfing.github.io/hextra/docs/guide/configuration/#logo-and-title
Logo and Title 
To modify the default logo, edit hugo.yaml and add the path to your logo file under static directory. Optionally, you can change the link that users are redirected to when clicking on your logo, as well as set the width & height of the logo in pixels.

hugo.yaml
params:
  navbar:
    displayTitle: true
    displayLogo: true
    logo:
      path: images/logo.svg
      dark: images/logo-dark.svg
      link: /
      width: 40
      height: 20

https://imfing.github.io/hextra/docs/guide/configuration/#favicon
Favicon 
To customize the favicon for your site, place icon files under the static folder to override the default favicons from the theme:

Basic Setup 
At minimum, include favicon.svg in your static folder. This will be used as the default favicon for your site.

You can create an adaptive SVG favicon that responds to system theme preferences by using CSS media queries within the SVG itself, following the approach described in Building an Adaptive Favicon.


