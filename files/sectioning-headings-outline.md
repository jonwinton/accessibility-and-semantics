# HTML: Sectioning, Headings, Accessibility & (A Bit Of) SEO

## The Document Outline

__[Per HTML5 Doctor](http://html5doctor.com/outlines/):__ "The document outline is the structure of a document, generated by the document’s headings, form titles, table titles, and any other appropriate landmarks to map out the document. The user agent can apply this information to generate a table of contents, for example. This table of contents could then be used by assistive technology to help the user, or be parsed by a machine like a search engine to improve search results. The outlining algorithm has been clearly defined in the [HTML5 spec](http://w3c.github.io/html/sections.html#outlines), so once all browsers and assistive technologies play ball, there will be some major accessibility wins."

__TL;DR:__ Outlines are generated using heading levels and (_in HTML5_) sectioning elements. We want a good document outline for SEO and accessibility.



## What Is A _"Sectioning Element"_?

Alright this is the fun part. There's two types of sectioning elements: [__Sectioning Root__](https://www.w3.org/TR/html5/sections.html#sectioning-root) and [__Sectioning Content__](https://www.w3.org/TR/html5/dom.html#sectioning-content-0).


### Sectioning Root

 Sectioning root is a container that __provides a scope__ for the discrete content sections that will be defined within it. _Each sectioning root gets its own individual outline_.The top level sectioning root of any page is formed by its `<body>` tags, so there is always an outline generated for any webpage, starting from the `<body>` tags and working through the sections it is broken into.

 Sectioning root tags include:

- [`<body>`](http://html5doctor.com/element-index/#body)
- [`<blockquote>`](http://html5doctor.com/element-index/#blockquote)
- [`<figure>`](http://html5doctor.com/the-figure-figcaption-elements/)
- [`<td>`](http://html5doctor.com/element-index/#td)
- [`<details>`](http://html5doctor.com/the-details-and-summary-elements/)
- [`<fieldset>`](http://html5doctor.com/element-index/#fieldset)

So the issue is that anytime you use one of these elements you generate a new document outline. That doesn't mean that you shouldn't use them, it means they should be used purposefully as a powerful tool.


### Sectioning Elements (The "_Discrete Content Sections_ of a Root")

Each sectioning root is broken into a series of content sections. These sections are created by placing sectioning content element tags around discrete pieces of content. Sectioning content elements __are nestable__ and __semantic__. The type that should be used depends on the nature of the content it will contain.

Sectioning content tags include:

- [`<section>`](http://html5doctor.com/the-section-element/)
- [`<article>`](http://html5doctor.com/the-article-element/)
- [`<nav>`](http://html5doctor.com/nav-element/)
- [`<aside>`](http://html5doctor.com/aside-revisited/)


## Heading Content

Text-only labels for sections of content. In the absence of sectioning content tags, the presence of a heading tag will still be interpreted as the beginning of a new content section.

- [`<h1> - <h6>`](http://html5doctor.com/element-index/#h)


### What Does The Spec Say?


"These elements represent headings for their sections.

The semantics and meaning of these elements are defined in the section on [Headings and sections](http://w3c.github.io/html/sections.html#headings-and-sections).

These elements have a rank given by the number in their name. The h1 element is said to have the highest rank, the h6 element has the lowest rank, and two elements with the same name have equal rank.

h1–h6 elements must not be used to markup subheadings, subtitles, alternative titles and taglines unless intended to be the heading for a new section or subsection. Instead use the markup patterns in the [Common idioms without dedicated elements](http://w3c.github.io/html/common-idioms-without-dedicated-elements.html#common-idioms-without-dedicated-elements) section of the specification."


### Key Takeaways of the Heading Element

- Heading elements label their section.
- Heading elements should __NOT__ be used to markup subheadings, subtitles alternative titles and taglines __UNLESS__ it's a title for a new section.
- Be intentional with your use of the `h1-h6` elements.
- Styling does not dictate heading level.
    - Do not tie your styles directly to a specific heading element, [__make a module__](https://gist.github.com/jonwinton/37f8cd0922b7ab6487adb6737debe67c)
- Make your best judgements when assigning heading level, but work with your content creators to determine proper heading levels.


## Tying It All Together

We like to make modular components, but we need to keep in mind how the overall page flows. Work with your team and designers to determine how content will be sectioned and be intentional with how you use HTML5 sectioning elements. Just because we have super cool elements doesn't mean we should use them all the time.

__When in doubt a `<div>` has no semantic meaning__

### Testing

Want to test your document outline? Go here: [HTML 5 Outliner](https://gsnedders.html5.org/outliner/).
There's also a [Chrome Extension](https://chrome.google.com/webstore/detail/html5-outliner/afoibpobokebhgfnknfndkgemglggomo?hl=en).


### SEO

New crawlers and SEO algorithms take into account HTML5 sectioning elements and leverage their functionality when taking SEO into account. The rule of "only one H1 per page" is dying. Work with your teams to educate them on this topic and fight for accessibility. Need some reading material? [Here ya go](http://webdesign.tutsplus.com/articles/the-truth-about-multiple-h1-tags-in-the-html5-era--webdesign-16824).


### Resources

- [HTML5 Doctor: Outlines](http://html5doctor.com/outlines/)
- [HTML 5 Outliner](https://gsnedders.html5.org/outliner/)
- [Chrome Outliner Extension](https://chrome.google.com/webstore/detail/html5-outliner/afoibpobokebhgfnknfndkgemglggomo?hl=en)
- [SEO & Multiple H1's & Sectioning](http://webdesign.tutsplus.com/articles/the-truth-about-multiple-h1-tags-in-the-html5-era--webdesign-16824)
- [Sectioning Root](https://www.w3.org/TR/html5/sections.html#sectioning-root)
- [Sectioning Content](https://www.w3.org/TR/html5/dom.html#sectioning-content-0)
- [Simple CSS Heading Module Gist](https://gist.github.com/jonwinton/37f8cd0922b7ab6487adb6737debe67c)
- [HTML5 Doctor: Body](http://html5doctor.com/element-index/#body)
- [HTML5 Doctor: Blockquote](http://html5doctor.com/element-index/#blockquote)
- [HTML5 Doctor: Figure/Figcaption](http://html5doctor.com/the-figure-figcaption-elements/)
- [HTML5 Doctor: Td](http://html5doctor.com/element-index/#td)
- [HTML5 Doctor: Details](http://html5doctor.com/the-details-and-summary-elements/)
- [HTML5 Doctor: Fieldset](http://html5doctor.com/element-index/#fieldset)
- [HTML5 Doctor: Section](http://html5doctor.com/the-section-element/)
- [HTML5 Doctor: Article](http://html5doctor.com/the-article-element/)
- [HTML5 Doctor: Nav](http://html5doctor.com/nav-element/)
- [HTML5 Doctor: Aside](http://html5doctor.com/aside-revisited/)



* Give sectioning content and root more meat
* Why is this a big deal
* Root can go into content