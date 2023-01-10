        Digital Accessibility at Princess Margaret   

Apologies if you're navigating this using a screen reader - you may randomly hear facts about cats. This is due to the aria-live region demo in the second half. If it's any consolation - I thought I was going crazy.

Digital Accessibility at Princess Margaret
==========================================

[Slides](/slides//)

Today we'll define web accessibility, look at the legislation around it, and talk about strategies for incorporating accessibility in a team strategy, both retroactively (remediation) and moving forward (KPIs). In the second half, we'll focus on accessibility in code, and the special challenges your team is tackling.

* * *

Table of Contents
-----------------

*   Part 1: **Accessibility in the Organization**
    *   [The idea of accessibility](#the-idea)
    *   [Accessibility & law](#the-law)
        *   [The Access for Ontarians with Disabilities Act](#aoda)
        *   [The Web Content Accessibility Guidelines](#wcag)
    *   [Accessibility strategies](#strategies)
        *   [A team-based approach](#team-based)
        *   [Strategies for auditing](#auditing)
        *   [Key performance indicators](#kpis)
*   Part 2: **Technical Aspects of Digital Accessibility**
    *   [Code without barriers](#code-without-barriers)
        *   [Native accessibility](#native-a11y)
        *   [WAI-ARIA](#wai-aria)
        *   [Accessibility in the build pipeline](#accessibility-in-the-build-pipeline)
    *   [Special Challenges](#special-challenges)
        *   [Interactivity](#interactivity)
        *   [Informational graphics](#informational-graphics)

Part 1: Accessibility in the Organization
-----------------------------------------

*   [The idea of accessibility](#the-idea)
*   [Accessibility & law](#the-law)
    *   [The Access for Ontarians with Disabilities Act](#aoda)
    *   [The Web Content Accessibility Guidelines](#wcag)
*   [Accessibility strategies](#strategies)
    *   [A team-based approach](#team-based)
    *   [Strategies for auditing](#auditing)
    *   [Key performance indicators](#kpis)

Part 2: Technical Aspects of Digital Accessibility
--------------------------------------------------

*   [Code without barriers](#code-without-barriers)
    *   [Native accessibility](#native-a11y)
    *   [WAI-ARIA](#wai-aria)
    *   [Accessibility in the build pipeline](#accessibility-in-the-build-pipeline)
*   [Special Challenges](#special-challenges)
    *   [Interactivity](#interactivity)
    *   [Informational graphics](#informational-graphics)

* * *

![](/images/thinking.svg)

The idea of accessibility
-------------------------

**The point of the internet is accessibility.**

The web was conceived as a way of making information accessible. **The end-user can use whatever software or hardware they want.** Information is encoded in a standardized way so that the recipient of that information can interact with it however they see fit. This is the core principle of the internet.

If you understand this principle, then you understand "A11y" - web accessibility.

This principle of predictable encoding is what allows the internet to be accessible via refrigerator.

![Samsung Family Hub 2.0 refrigerator with built-in touch screen](/images/fridge.webp)

Note: Samsung is not a sponsor.

It also allows for a machine-readable internet powered by web‑crawling search engines, who can parse content and rank its relevance.

This principle is similarly responsible for the longevity of websites last updated in the mid-1990s.

[![Space Jam website](/images/spacejam.png)](https://spacejam.com)

The point of the internet is to be _accessible_ on Windows and Macs, on Netscape and Firefox and Chrome, phones and tablets and watches and treadmills.

The way this works is through the use of a markup language, HTML. HTML tags wrap content to communicate the type and purpose of content.

    <blockquote>
        This is a quote.
        <cite>This is the citation</cite>
    </blockquote>

The purpose of encoding the internet using a standardized markup language is to **make our content client-agnostic**. We encode the _intention_ of our content, be it a link, a document heading, an input field. This allows the receiving technology - the client - to render our content however it wants.

### The end-user's technology stack

> “It works on _my_ machine.”
> 
> \- Every developer, at some point.

If the idea of the internet is to allow the user to consume your content using whatever technology they see fit, then every developer must, at some point, come to terms with the fact that **other people exist**.

While developers develop, we keep track of our progress by looking at the end-result of our work, and we see it on our own monitors, interact with it using our own keyboards and mice, and look at it with our own eyes. This is all fine and good and necessary.

This only becomes a problem when we forget the fact that what we are building is not _only_ for our own computers, keyboards, mice, eyes, preferred browser, etc. etc.

![Responsive website mockup](/images/mockups.png)

This issue is, of course, not limited to developers. It arises, for example, when a designer provides a design in specific "desktop" and "mobile" sizes, but fails to consider issues that might come up at other sizes or zoom settings.

It arises when a copywriter over-uses idiom or jargon, or a product manager creates personas that ignore the fact that [\> 1 in 5 Canadians have a disability Opens in a new window](https://www150.statcan.gc.ca/n1/pub/11-627-m/11-627-m2022062-eng.htm).

![In 2017, 6.2 million (22%) Canadians aged 15 and older had a disability. 24% women; 20% men; 13% youth aged 15 to 24; 20% working-age adults aged 25 to 64; 38% seniors aged 65 and older.](/images/disability-in-canada.jpeg)

Via [Statistics Canada Opens in a new window](https://www150.statcan.gc.ca/n1/pub/11-627-m/11-627-m2022062-eng.htm)

For those of us who make things on the internet, to understand what we are building, we must understand the problem we are solving, a challenge that is a function of our own frame of reference.

This problem is this: **we cannot dictate the technologies of our end‑user**.

And, if we borrow from Marshall McLuhan, we can say that technologies are extensions of our selves. We take the problem one step further and say that we cannot dictate the end-user in either their technology or corporal faculties.

![Marshall McLuhan leaning on a TV. The TV is showing an image of Marshall McLuhan.](/images/mcluhan.jpeg)

Once we start trying to solve that problem, we are building the internet as intended - accessibly.

_"You can only view this website in Internet Explorer"_; _"you can only view this website on desktop"_; _"you can only view this website with your eyes"_ - these are all the same problem, and can all be **solved by understanding the product we build** when we build the internet.

![Edvard Munch's 'Anxiety' - a very anxious painting.](/images/munch.jpeg)

(Team photo)

It may seem like an overwhelming problem - having to consider the endless diversity of technologies, both present and future, even before we add in the endless spectrum of human ability.

Luckily, there is an inherent limit to this problem. **Part of the burden is on the end-user.**

We do not have to print physical copies of a website for people who do not own a computer. All we have to do is use our markup language to **encode our content in a predictable way**.

This is what allows the end-user to customize their personal technology stack in whatever way they see fit, given the resources (and the standards) at hand.

That stack includes hardware and software, network provider, and computer peripherals.

![A text-based browser, w3m, showing the Princess Margaret Wikipedia page.](/images/w3m.png)

Mine includes too many browser extensions, a dorky mechanical keyboard, and, sometimes, a text-based browser called [w3m Opens in a new window](https://w3m.sourceforge.net/).

The vast majority of accessibility standards are devoted to accommodating two possible aspects of a technology stack:

*   a category of software called "**screen readers**", and
*   the **_absence_ of a computer mouse**.

#### Screen readers

 

Screen readers are software programs that describe web content and interactions with text-to-speech.

There are, for better or for worse, a lot of them out there, making client support a little tricky.

![WebAIM screen reader survey results, showing a resurgence in popularity for JAWS since 2019.](/images/screen-reader-survey.png)

Especially since the most popular screen reader, JAWS, costs a minimum of $90 (annual student license), and $1000 for a perpetual personal license, and is only available on Windows computers, exclusively in the USA. _Image courtesy of [webaim.org Opens in a new window](https://webaim.org/)_

Luckily, out of the four screen readers with >10% market share, the three [JAWS Opens in a new window](https://www.freedomscientific.com/products/software/jaws/) alternatives are all free, with [VoiceOver Opens in a new window](https://support.apple.com/en-ca/guide/voiceover/welcome/mac) installed as a default application on Mac, and [Narrator Opens in a new window](https://support.microsoft.com/en-us/windows/complete-guide-to-narrator-e4397a0d-ef4f-b386-d8ae-c172f109bdb1) on Windows. NonVisual Desktop Access (NVDA) is Windows application available as a [free download Opens in a new window](https://www.nvaccess.org/download/).

As mentioned previously, most (but certainly not all) of the accessibility guidelines have to do with **making information available as text** (so screen readers can read it out), and with ensuring that **all interactions are possible** without the use of a mouse.

I had a very well-meaning colleague ask me if people using screen readers might ever _also_ need keyboard-only access.

I asked him to imagine for a moment that he is blind. "Okay, now how do you know where your mouse cursor is?"

He was under the impression that the keyboard-only accommodations applied only to people with motor-function issues. While he was correct that not everyone can physically manipulate a mouse, he forgot that using the mouse requires visual orientation in a virtual space.

**Screen reader users navigate using the keyboard.**

If they had to read every web page from top to bottom in their entirety, the web would be an extraordinarily boring, repetitive place. Instead, when using a screen reader, you **navigate with different landmarks**, including headings and links.

Many requirements have to do with helping orient a user, like **unique page titles**, and **text that contextualizes links**. Others, like providing a "**skip link**" before the main menu, help users to jump quickly to the content they're after.

We tend to think of "text alternatives" as descriptions of images. While image descriptions are necessary, it's important to remember how much information is conveyed visually in the layout of our pages and components.

![Form inputs with labels and border colours indicating error status](/images/material-form.png)

We associate label and "helper" text with form elements based their visual proximity. We might assume that a user can see a colour and associate it with an error status. We might assume that a user focussed on an input has read the error message below it.

Some associations that we might make visually are also connected natively in well-structured HTML. However, **when implicit connections aren't available, we can also make connections explicit**. (I'll go further into these techniques in the second, code-focussed half of this presentation.)

### Barriers beyond blindness

Aside from keyboard-control and text alternatives to graphics and context, there are a few additional concerns that the specifications consider:

*   **flashing content** can trigger seizures,
*   **information encoded in colours** can be inaccessible to colour-blind users,
*   users may **zoom into your content (even more than you'd think)**,
*   **poor colour-contrast** can be challenging to read,
*   **obtuse or overly complicated language** can obscure content,
*   **time-based interactions** can be a barrier for those with cognitive or motor impairments.

I can't go much further than this without delving into specific technical challenges and solutions, which I'll save for the second half of our session. At this point I want to step back and recognize that, while some of this might start to feel a little arcane and "edge-case"-y, there are terrific benefits that come from investing some time and energy into this kind of robust approach to making stuff on the internet.

### The Curb-cut Effect

![A slope in the sidewalk.](/images/curbcut.jpeg)

The term "curb-cut effect" was coined to describe **accommodations made for a disadvantaged community that result in a benefit for a wider population**.

Curb cuts - slopes in the pavement allowing for a smooth transition from a raised sidewalk to the street - were a rarity until well into the second half of the 20th century. Successful local pilot projects ran the 1940s to help disabled World War II veterans, but it took activists in the disability community another half-century to make them a mandatory feature of North American streets.

![Illustration of a diversity of people using a public crosswalk](/images/kailey-whitman.png)

Image credit [Kailey Whitman Opens in a new window](https://kaileywhitman.com/) via [Learning for Justice Opens in a new window](https://www.learningforjustice.org/magazine/fall-2021/the-curbcut-effect-and-championing-equity)

Yet for all the effort put into a reality, they are wildly popular, not just among the disabled community, but with stroller-pushers, grocery-cart aficionados, and just your average pedestrians, [90% of whom will opt to use them Opens in a new window](https://www.mcclatchydc.com/news/article24460762.html).

If you've been looking for an excuse to try TikTok, I highly recommend [Taylor Lindsay-Noel Opens in a new window](https://www.tiktok.com/@accessbytay?lang=en)'s accessibility reviews of Toronto establishments.

We can see curb cut effects - positive externalities of accessibility - everywhere on the web.

*   [85% of Netflix watchers use subtitles Opens in a new window](https://idealinsight.co.uk/infographics/netflix-captions).
*   Accessibility **overlaps widely with search engine optimization** (SEO), as search rankings are determined by digital webcrawlers who parse the text of your website.
*   Keyboard-control benefits "[**power users** Opens in a new window](https://www.nngroup.com/articles/ui-accelerators/)" of your website.
*   Accessibility is dependent on standards-compliant code, sensible layouts, readable colour schemes and font sizes, and clear labelling, all of which makes it a "**canary in the coal mine**" for the overall quality and usability of your site.

![A still from Stranger Things Season 4 featuring the subtitle, 'tentacles undulating moistly'.](/images/tentacles.jpeg)

2022 was the first time I've seen captions go viral _in context_.

* * *

**Further Reading:**

*   [Measuring disability in Canada Opens in a new window](https://www150.statcan.gc.ca/n1/pub/11-627-m/11-627-m2022062-eng.htm), _Statistics Canada_
*   [Diverse Abilities and Barriers Opens in a new window](https://www.w3.org/WAI/people-use-web/abilities-barriers/), _W3C Web Accessibility Initiative_
*   [Screen Reader User Survey #9 Results Opens in a new window](https://webaim.org/projects/screenreadersurvey9/), _WebAIM_
*   [The Curb-Cut Effect Opens in a new window](https://ssir.org/articles/entry/the_curb_cut_effect), _Stanford Social Innovation Review_
*   [Curb ramps liberate Americans with disabilities—and everyone else Opens in a new window](https://www.mcclatchydc.com/news/article24460762.html), _McClatchy DC_
*   [How & Why Accessibility Matters for SEO Opens in a new window](https://www.searchenginejournal.com/seo-accessibility/379582/), _Search Engine Journal_
*   [Accelerators Allow Experts to Increase Efficiency Opens in a new window](https://www.nngroup.com/articles/ui-accelerators/), _Nielsen Norman Group_
*   [Netflix and Captions? Opens in a new window](https://idealinsight.co.uk/infographics/netflix-captions), _Ideal Insight_

![](/images/lawyer.svg)

Accessibility & law
-------------------

Accessibility legislation everywhere is the result of hard-won battles by activists. In the 1970s, when the "Rolling Quads" [poured their own cement Opens in a new window](https://www.mcclatchydc.com/news/article24460762.html) ramps in the dead of night to create wheelchair-accessible sidewalks in the streets of Berkeley, CA.

In 1990, 60 activists left their wheelchairs and other mobility aids to crawled up the 100 steps to the U.S. Capitol building to protest the stalled Americans with Disabilities Act during the "[Capitol Crawl Opens in a new window](https://en.wikipedia.org/wiki/Americans_with_Disabilities_Act_of_1990#%22Capitol_Crawl%22)".

![A group of handicapped people led by 8-year-old Jennifer Keelan crawl up the steps of the U.S. Capitol in Washington, to draw support for a key bill pending in the House that would extend civil rights to disabled persons.](/images/capitol-crawl.jpeg)

Jeff Markowitz/AP Photo

Legislation has improved since then. Some.

In 2005, Ontario got the AODA, which includes provisions not just for accommodations in the built physical environment, but for the digital environment as well.

![AODA logo](/images/AODA.svg)

### The Access for Ontarians with Disabilities Act

Digital accessibility for publicly-available web content is mandated through the "Access for Ontarians with Disabilities Act" (AODA).

> 2\. By January 1, 2021, all internet websites and web content must conform with WCAG 2.0 Level AA, other than,
>   
>   i. success criteria 1.2.4 Captions (Live), and
>   
>   ii. success criteria 1.2.5 Audio Descriptions (Pre-recorded).
> 
> [O. Reg. 191/11, s. 14 (4) Opens in a new window](https://www.ontario.ca/laws/regulation/110191#BK14)

We should note this applies to public sector and large[1](#footnote1) organizations in Ontario, and is limited to content produced since 2012.

Pretty succinct for legislation, isn't it?

That's because the AODA defers to the WCAG - the accessibility guidelines set out by the World Wide Web Consortium (W3C). The W3C is an organization that governs standards for things like HTML and CSS.

**Deferring to the WCAG guidelines is typical** for the vast majority of digital accessibility legislation.

![W3C WAI-AA WCAG 2.0 conformance badge](/images/wcag2AA-blue.png)

### The Web Content Accessibility Guidelines

Ontario mandates compliance with WCAG standards Version 2.0, Level AA, barring a few exceptions.

Version 2.0 of the standards was published in 2008, and remains the standard used by the AODA. A more recent version, version 2.1, builds on the 2.0 standards for a more modern web, including accommodations for users of mobile devices. Accessibility testing tools tend to reference v2.1 by default, but this does not introduce any conflicts - **if you are in compliance with v2.1, you're in compliance with v2.0**.

Level AA is the second of three tiers of accessibility. Level A is the most basic, Level AAA the most rigourous.

These tiers each depend on any prior tiers, meaning **Level AA compliance requires Level A compliance**.

To generalize somewhat…

Most **Level A** requirements represent a lack of **barriers for users who access the website with assistive technologies** like a screen reader. For example, when a user makes an error in a form, the location of the error is identified with text.

![An error message in a form](/images/patterns-errors-userinput2.png)

**Level AA** requirements tend to provide a **basic level of assistance**. For example, when there is an error in a form, a message provides examples of successful inputs.

![Example text that helps resolve an error](/images/patterns-errors-userinput6.png)

**Level AAA** requirements tend to provide **assistance at a structural level**. For example, users are able to review, confirm and correct any information before a form is submitted.

![A confirmation screen.](/images/patterns-confirmation-acknowledgement-confirm-1.png)

Level AAA requirements generally must be considered at the initial design stage, whereas most Level A and AA requirements can largely be "retrofitted" onto existing content without significant restructuring.

* * *

**Further Reading:**

*   [Guide to the Act Opens in a new window](https://aoda.ca/guide-to-the-act/), _Accessibility for Ontarians with Disabilities Act_
*   [WCAG 2 Overview Opens in a new window](https://www.w3.org/WAI/standards-guidelines/wcag/), _W3C Web Accessibility Initiative_
*   [What is WCAG? Opens in a new window](https://www.deque.com/wcag/), _Deque_

![](/images/strategy.svg)

Accessibility strategies
------------------------

**Planning for accessibility involves the entire team** - developers, yes, but also design, content, and management. Once team members each understand the role they play in producing accessible content, it's possible to build, audit, fix and track your progress over time.

### A team-based approach to content

Let's look at some ways different team members can get involved.

#### Project manager

*   Assume you have a **diverse user base**, and develop personas accordingly. _If you don't have a diverse user base… maybe there's a reason?_
*   In the hiring process, _do not_ seek out team members with disabilities so that you can dump responsibilities on them, but _do_ **consider diversity an asset**.
*   Consider user testing with people using their own **personalized technology stack**, such as people who use assistive reading devices, people with color blindness impairments, or people with motor impairments.
*   Insist on **accessibility testing** as a standard part of the development lifecycle.
*   Get familiar with the accessibility **opportunities that go with each role** in your team. For example, you might consider taking the [free "Web Accessibility by Google" Udacity course Opens in a new window](https://www.udacity.com/course/web-accessibility--ud891).

#### Project manager (continued)

*   Insist on **accessibility testing** as a standard part of the development lifecycle.
*   Get familiar with the accessibility **opportunities that go with each role** in your team. For example, you might consider taking the [free "Web Accessibility by Google" Udacity course Opens in a new window](https://www.udacity.com/course/web-accessibility--ud891).

#### Design

*   **Familiarize yourself the categories of disability** most likely to affect the experience of a web product - vision impairments, hearing impairments, motor issues and cognitive disorders.
*   Get to know **a screen reader**.
*   Learn how to **[emulate different forms of colour-blindness Opens in a new window](https://firefox-source-docs.mozilla.org/devtools-user/accessibility_inspector/simulation/index.html)** using the browser tools.
*   Provide direction to the developers on **tab and focus order**.
*   When **customizing interactive elements** like form controls, **consult a developer** about what customizations are easy and which are burdensome. (The answers might surprise you!)
*   Provide WCAG-compliant **[touch targets Opens in a new window](https://www.w3.org/TR/mobile-accessibility-mapping/#touch-target-size-and-spacing)** in mobile designs.
*   Check your **[colour contrast Opens in a new window](https://webaim.org/resources/contrastchecker/)**
*   Aim for **[Universal Design Opens in a new window](https://en.wikipedia.org/wiki/Universal_design)** where possible.

#### Content

Copywriters should be prepared to provide…

*   **alternative text** for images (not always easy - consult the W3C's [alt text decision tree Opens in a new window](https://www.w3.org/WAI/tutorials/images/decision-tree/))
*   **link context**
*   **headings** to structure content
*   unique **page titles**
*   **captions or transcriptions** for audio-visual content
*   **form labels**, **instructions** and **error messages**

While not required by the AODA, WCAG Level AAA requirements include considerations when using **unusual words** and **abbreviations**, as well as for **reading level** and **pronunciation**.

### Accessibility within the team

All content considerations for the web can also apply to documents within the office - spreadsheets, PDFs, text documents, and slideshows included.

While we don't have time to cover all of these today, getting familiar with making accessible web content will also teach you how to make accessible documents. In the Microsoft Office suite of tools (Word, PowerPoint, etc.), there are built-in [accessibility checkers Opens in a new window](https://support.microsoft.com/en-us/office/improve-accessibility-with-the-accessibility-checker-a16f6de0-2f39-4a2b-8bd8-5ad801426c7f?ui=en-us&rs=en-us&ad=us), and most common office formats take accessibility in mind, like [Adobe PDFs Opens in a new window](https://www.adobe.com/accessibility/pdf/pdf-accessibility-overview.html) and [Google Docs, Slides and Sheets Opens in a new window](https://support.google.com/docs/answer/6199477?hl=en).

### Strategies for auditing

![Rear-projecting 1929 animated short film `Hell's Bells` onto our curtains while Karen (in a wolf costume) watches from the porch.](/images/halloween.jpeg)

The Instagram alternative text says: `"Photo shared by Simon Borer on October 31, 2022. May be an image of 1 person, child and indoor."` Actually it's an adult, outdoors on a porch.

When we ask, "have I made this digital stuff accessible?", we're actually asking, "**are my intentions clear?**"

When we test functionality in code, our tests can be quite simple:

    /* code */
    function sum(a, b) {
      return a + b;
    };
    /* test */
    test('adds 1 + 2 to equal 3', () => {
      expect(sum(1, 2)).toBe(3);
    });
    /* result */
    PASS  ./sum.test.js
    ✓ adds 1 + 2 to equal 3 (5ms)

When we test for accessibility, it's true that broken code can create barriers, but what we're actually testing is more complicated. We're testing whether we've **successfully communicated the purpose and intent of content**.

An automated test can tell us whether we're missing the `alt` attribute on an image.

    <img src="bird.jpg">

An automated test _cannot_ tell us whether an `alt` attribute is accurate…

    <img src="bird.jpg" alt="Airplane">

…and, especially, an automated test cannot tell if we've _communicated the purpose_ of showing that particular image.

    <img src="bird.jpg" alt="A bird on a wire, against the backdrop of the Great Smoky Mountains, reminding us that Leonard Cohen did his best work recording in Nashville.">

It's a cliché to say that "a picture is worth a thousand words", but when writing alternative text, or providing any text-based alternative to visual communication, you do have to ask the question, "**how many words is this worth?**" and then provide the same value to all users.

Communicating clearly and effectively is hard. Rarely is it as clear-cut as arithmetic. It's for this reason that testing (and strategizing for) accessibility **must involve both automated and manual effort**.

We are not yet in a place where it's trivial for a computer to tell the difference between a bird and an airplane, let alone _why you chose to show us a bird_.

Expert estimates of the percentage of accessibility issues that are possible to catch with automated tools vary widely, from the low end of [30% Opens in a new window](https://www.essentialaccessibility.com/blog/automated-accessibility-testing-tools-how-much-do-scans-catch) to around [57% Opens in a new window](https://github.com/dequelabs/axe-core#:~:text=you%20can%20find%20on%20average%2057%25%20of%20WCAG%20issues%20automatically), but at most, automated tests will leave the job half-done.

Let's talk about…

1.  How to find and fix existing accessibility issues (remediation)
2.  How to track and maintain your accessibility going forward (key performance indicators)

#### Remediation

Before you begin testing, it's important to set expectations. [tooltester.com Opens in a new window](https://www.tooltester.com/en/blog/accessible-websites/) reported their results of automated accessibility testing on the top 200 websites. These are their top 3 most accessible websites:

Site

Total assets

Errors

Warnings

% of site inaccessible

[Nih.Gov Opens in a new window](https://www.nih.gov/)

555

1

76

0.18%

[Cdc.gov Opens in a new window](https://www.cdc.gov/)

543

1

59

0.18%

[Gov.uk Opens in a new window](https://www.gov.uk/)

492

1

14

0.20%

Accessibility, particularly achieving full WCAG Level AAA compliance, is a lofty goal. It seems as though there is no site of appreciable size that is 100% compliant. The goal should be to **catch issues & interpret the warnings**, **understand the impact**, and **triage appropriately**, while **planning to avoid these issues** in the future.

That being said, let me share with you two test plans - one as an MVP, and one describing my own process.

##### A minimum viable test plan

0.  Perform all your **standard tests** to make sure your code is working properly - unit tests, HTML & CSS validation, etc.
1.  Use the browser tools to expose the "**accessibility tree**" - the structure and information made available to assistive technologies.

[![The website pmcobe.ca with accessibility tree exposed in the Firefox developer tools](/images/accessibility-tree.png)](/images/accessibility-tree.png)

You can do this in Chrome or Edge, but I personally prefer Firefox for this.

1.  Use the browser tools to expose the "**accessibility tree**" - the structure and information made available to assistive technologies.

[![The website pmcobe.ca with accessibility tree exposed in the Firefox developer tools](/images/accessibility-tree.png)](/images/accessibility-tree.png)

You can do this in Chrome or Edge, but I personally prefer Firefox for this.

2.  Use automated testing on a single page by opening it in Chrome.
3.  1.  Right-click anywhere on the page and choose "Inspect" to bring up the developers' tools.
    2.  In the dev tools menu bar, choose "Lighthouse", and select an accessibility audit.

[![Open dev tools screen shot in new window](/images/dev-tools.png)](/images/dev-tools.png)

ThisA Lighthouse audit quickly flags any computationally-discernible accessibility errors or warnings, with valuable resources to learn more about the issue.

[![Open lighthouse screen shot in new window](/images/lighthouse-audit.png)](/images/lighthouse-audit.png)

3.  Using Microsoft's [Accessibility Insights for Web browser extension Opens in a new window](https://accessibilityinsights.io/docs/web/overview/), perform a guided manual test.

[![Open Accessibility Insights for Web screen shot in new window](/images/aiw.png)](/images/aiw.png)

Accessibility Insights for Web guides you through the steps of a manual audit, with instructions and live visual aids.

Using these two tools will catch the a large majority of accessibility issues. They both provide results that are exportable as JSON, meaning you can easily triage and **incorporate the issues into your bug-tracking system**, tracking progress over time.

5.  Learn to use a screen reader.

The ideal way to supplement these two tools is by testing with the **actual user interface under test**.

I developed responsive websites for years using the dev tools' mobile emulators, and that was usually good enough, but about once a month the QA team would find a bug while using a real mobile device that wasn't represented in the emulators. Learning to use a screen reader fluently can take some time, but once it becomes a part of your experience, you will absolutely start building better applications.

##### A comprehensive test strategy

When I perform a site or content audit, I follow a similar process, but with a few more tools to help with the volume of content involved in a full site audit.

If you are planning to tackle a significant backlog of content, you may want to consider a process that has a longer set-up time, but can multi-task much more efficiently.

###### Automation

1.  Get **a list of all the URLs** you'll be auditing. If someone can provide full list/sitemap, that's great, but it's nice to run a Python script that returns all the pages, just to be sure.

Looping through each one of the pages in a headless browser…

2.  ↻ [**Validate** the HTML Opens in a new window](https://html-validate.org/)
3.  ↻ Perform an **automated accessibility check** with the [axe-core library Opens in a new window](https://github.com/dequelabs/axe-core) (the foundation of Lighthouse and [many other accessibility checkers Opens in a new window](https://github.com/dequelabs/axe-core/blob/develop/doc/projects.md#community-projects)).

###### Manual testing

Provided there is sufficient resources for it, I'd opt to perform these tests site-wide, however at minimum each one of these tests should be performed on one instance of every page template and interactive component.

4.  **Guided manual testing** with [AIW Opens in a new window](https://accessibilityinsights.io/docs/web/overview/).
5.  Manual **screen reader/keyboard-only usability** testing.

###### Reporting

6.  **Compile results** in JSON from steps 2-4, and convert to CSV (spreadsheet) format.
7.  **Incorporate notes** from usability testing.
8.  Categorize based on **severity**, **frequency** and **ease** of resolution.

### Key performance indicators

![Charles Goodhart](/images/Charles_Goodhart.jpeg)

> "When a measure becomes a target, it ceases to be a good measure".
> 
> \- [Goodhart's law Opens in a new window](https://en.wikipedia.org/wiki/Goodhart%27s_law)

Keeping in mind Goodhart's law, we can develop KPIs that keep us honest about the progress of our good intentions.

While KPIs are particular to an organization, there are certain indicators that have a lot of potential for **offering good insights** into the accessibility of the works being **remediated** or **produced**.

#### Candidate KPIs

Regression rate

Tracking the **re-appearance of fixed bugs**.

Remediation response time

Tracking the **time between the identification of an issue and its resolution** can indicate how well your team is set up to diagnose, prioritize and fix issues.

**Ratio** of WCAG **Level A** violations **versus Level AA**.

Level A violations tend to be much more severe, identifying "showstopper" barriers. This is a heuristic, but a [heuristic recommended by the W3C Opens in a new window](https://www.w3.org/WAI/RD/wiki/Benchmarking_Web_Accessibility_Metrics).

Code coverage

Once you have started to integrate testing into your build pipeline, you can track the **percentage of your codebase that is covered** by these tests.

Manual test coverage

Tracking the **percentage of your application covered by manual audits**.

#### Candidate KPIs (continued)

Code coverage

Once you have started to integrate testing into your build pipeline, you can track the **percentage of your codebase that is covered** by these tests.

Manual test coverage

Tracking the **percentage of your application covered by manual audits**.

##### Tool spotlight: Pa11y Dashboard

Most of the tools discussed thus far can produce a JSON output - a format that lends itself to integrating with tracking and visualization tools.

If you're looking for an "off-the-rack" solution, [pa11y Opens in a new window](https://github.com/pa11y) is a mature accessibility monitoring tool, with great visualization features. It does, of course, come with all the usual caveats of automated accessibility testing.

[![Open pa11y screen shot in new window](/images/pa11y-dashboard.jpeg)](/images/pa11y-dashboard.jpeg)

Via [github.com/pa11y Opens in a new window](https://github.com/pa11y/pa11y-dashboard)

If you're looking for an "off-the-rack" solution, [pa11y Opens in a new window](https://github.com/pa11y) is a mature accessibility monitoring tool, with great visualization features. It does, of course, come with all the usual caveats of automated accessibility testing.

[![Open pa11y screen shot in new window](/images/pa11y-dashboard.jpeg)](/images/pa11y-dashboard.jpeg)

Via [github.com/pa11y Opens in a new window](https://github.com/pa11y/pa11y-dashboard)

* * *

**Further Reading:**

*   [Accessibility for Teams Opens in a new window](https://accessibility.digital.gov/), _accessibility.digital.gov_
*   [Accessibility Strategy for Product Management Opens in a new window](https://www.tpgi.com/accessibility-strategy-for-product-management/), _David Sloan_
*   [Accessibility guidelines for UX Designers Opens in a new window](https://uxdesign.cc/accessibility-guidelines-for-a-ux-designer-c3ba775539be), _Avinash Kaur_
*   [Writing for Web Accessibility Opens in a new window](https://www.w3.org/WAI/tips/writing/), _W3C Web Accessibility Initiative_
*   [Create accessible Office documents Opens in a new window](https://support.microsoft.com/en-us/office/create-accessible-office-documents-868ecfcd-4f00-4224-b881-a65537a7c155), _Microsoft_
*   [Automated Accessibility Testing Tools: How Much Do Scans Catch? Opens in a new window](https://www.essentialaccessibility.com/blog/automated-accessibility-testing-tools-how-much-do-scans-catch), _Essential Accessibility_
*   [Accessibility Program Fundamentals: Choosing the right accessibility metrics Opens in a new window](https://www.deque.com/blog/accessibility-program-fundamentals-choosing-the-right-accessibility-metrics/), _Deque_

![](/images/code.svg)

Part 2:

Code without barriers
---------------------

Okay, one thing I want to clear up before we dig in - **accessibility lives or dies in the front-end**. Your front-end might be assembled by a server side language, a user might trigger error messages from the API, but **all that matters is the content delivered to the user**.

### Native accessibility

It's pretty common for people to take for granted the amount of functionality we get "**for free**" when we use semantic HTML.

Just as a small example, compare a `<button>` element to a `<div>` pretending to be a button…

Obviously the `<div>` requires some CSS to replicate the style, but more than this, it needs…

*   the `role` attribute to be **identifiable to assistive technologies**
*   the `tabindex` attribute to **become keyboard-focusable**
*   several CSS properties to mimic the **native cursor behaviour**, **text properties** and **visual state changes**
*   a **`keydown` listener** for both Enter and Spacebar

If there is a native HTML element whose semantics describe your content, **it is very likely accessible** by default.

#### People sleep on HTML

Need an accordion?

Try the [`<details>` Opens in a new window](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/details) element

What about auto-complete? 

How about a meter?

Volume 

Output meter set at 50

Okay that last one cheats a little - supplementing the default behaviour with a single line of javascript and an aria attribute.

Every HTML element except `<div>` & `<span>` have a semantic meaning. In other words, **your HTML is already communicating** with the client (browser, screen reader, web crawler, et al.) about your content. Provided you are not using your elements in a semantically _incorrect_ way, your elements are already doing a lot of heavy lifting for you.

This is the purpose of the structural elements introduced in HTML5. Elements like `<nav>`, `<header>`, `<main>`, `<footer>` etc. communicate document structure to the client.

This is also why heading tags (`<h1>`, `<h2>`, et al.) are _not_ meant to be used for styling - they communicate **how the content is organized**, and this organization is not just announced by the screen reader, but are an option for navigating through the document.

### WAI\-ARIA

There are three categories of HTML attributes. Native attributes, (user-defined) data-attributes, and ARIA attributes

ARIA attributes serve two purposes:

*   To supplement native semantics (or replace them when they have been broken), and
*   To alert users when a _part_ of the page has been updated.

#### When to use ARIA

1.  There is visual information on the page that has **no native text alternative format**, or
2.  There are **no native semantics** or native attribute available.
3.  There is a DOM node (including text) that can or does **update without a page refresh** being triggered, and

A little heads-up: not all ARIA attributes are well-supported. Some features work well everywhere, whereas others may be affected by the [combination of screen reader and browser](https://labs.levelaccess.com/index.php/Assistive_Technology_Browser_Combinations).

##### Visual information with no native text alternative format

What do we mean by this? Well, the obvious example of visual information is an image, but it _has_ a native text alternative format - the `alt` attribute.

![A 'close' button represented by an 'x'](/images/x-button.svg)

    <button 
            role="button"
            aria‑label="Click to close" 
            onclick="myDialog.close()">X</button>

One instance of visual information not having a native text alternative is when we use symbols (including alphanumeric characters) to **represent an available action** that makes sense in a visual context (like a dialog), but may not make sense if the user just hears their screen reader say "x".

In that case, we could use the `aria-label` attribute explain the purpose of the button.

The ARIA spec has their own taxonomy, but for now let's say there are three categories:

`role`

Supplements or overrides native semantics

labelling attributes

Attributes like `aria‑label`, `aria‑labelledby`, or `aria‑controls`, can describe an element, or point to a relationship with another element.

state attributes

Attributes like `aria‑live`, `aria‑expanded`, or `aria‑busy`, can be updated with JavaScript to communicate the _state_ of content.

#### An incomplete list of useful roles

role value

component

`grid`

A _navigable_ table (think of a [calendar with selectable dates](https://codepen.io/simonborer/pen/WNzjPBq), for example), with `row`, `rowheader`, `cell`, and `columnheader`.

`group`

A group of UI elements not in a perceivable page section (i.e. not grouped together in the code, but only by the contents' context).

`log`

A [chat](https://www.w3.org/WAI/WCAG21/working-examples/aria-role-log/chatlog.html), for example

`marquee`

Like a `log`, but not vital or linear, i.e. a carousel or stock ticker.

`presentation`

Similar in function to aria-hidden, this role tells the screen reader that the element is decorative, but support for it on natively focusable elements is kinda sketchy.

`status`

A status update message, i.e. "your changes have been saved".

`tablist`

A [group of tabs](https://codepen.io/simonborer/pen/BarRbJB), with the roles `tab` (for the tab triggers), and `tabpanel` (for the content revealed by the tab triggers).

`timer`

A time keeping element.

`tooltip`

An element that [provides additional information](https://dequeuniversity.com/library/aria/tooltip) when focussed/hovered. Note that this is a tricky pattern to do correctly, since it requires the focus-grabbing of a modal, but (often) in the context of focussing on a form element. Avoid tooltips in general when you can!

`tree`

With `treeitem`, describes a [navigable tree structure](https://codepen.io/simonborer/pen/yLKbwvg), like folders and files.

#### Component ("Widget") ARIA attributes

Aside from `role`, all other ARIA attributes are prefixed with `aria-`.

These attributes are broken up into different categories in the documentation, but are all applied to HTML in the same way - either hard-coded or applied via JavaScript.

"Widget" attributes are essentially all concerned with **communicating input** (or the output based on user input), or letting the user know **where they are** and **what content is available** to them.

#### An incomplete list of aria widget attributes

`aria-autocomplete="none|inline|list|both"` (w/ `role="combobox|textbox"`)

`aria-checked="true|false|mixed"` (w/ `role="checkbox|switch|(etc.)"`)

`aria-current="page|step|date|location|time|true|false"`

`aria-disabled="true|false"`

`aria-expanded="true|false"`

`aria-hidden="true|false|undefined"`

`aria-invalid="true|false|grammar|spelling"`

`aria-label={string}` (only for invisible text)

`aria-level={integer}` (w/ `role="grid|heading|listitem|row|tablist"`)

`aria-multiselectable="true|false"` (w/ `role="grid|listbox|tablist|tree"`)

`aria-pressed="true|false|mixed"` (w/ `role="button"`)

`aria-selected="true|false|undefined"` (w/ `role="gridcell|option|row|tab"`)

`aria-sort="ascending|descending|none|other"` (w/ `role="columnheader|rowheader"`)

#### ARIA live region attributes

ARIA attributes that are categorized as "live region" attributes are for **communicating changes in the document** to the user. We often assume that if something "pops up", or disappears from the page, the user will **see that change**.

Live region attributes all have the purpose of providing an **alternative to changes a user would notice visually**.

`aria-live="polite|assertive|off"` (used with aria-atomic)

`aria-atomic="true|false"`

`aria-relevant="additions|text|removals|all"`

`aria-busy="true|false"`

#### Implicit live region attributes

Some of these live region attributes are **automatically added** when we add a particular role to an element - meaning we don't need at add that live region attribute manually.

`role="alert"` has an implicit `aria-live="assertive"`

`role="status"` and `role="log"` have an implicit `aria-live="polite"`

`role="timer"` and `role="marquee"` have an implicit `aria-live="off"`

These can be overridden by explicitly declaring `aria-live` values.

##### ARIA relationship attributes

This next category of aria attributes defines **relationships between elements**. Often, relationships between elements (think a label and an input) are shown in the visual layout, but are hard to understand based purely on the DOM (or the audio output of the DOM). This category of attributes works by providing an **alternative to the information conveyed by the visual layout**.

`aria-controls={id}`

`aria-labelledby={id}`

`aria-describedby={id}` similar to `aria-labelledby`, but verbose instead of concise

`aria-flowto={id}` gives the user the option to move to an element, overriding the source order

### Working examples

We don't have time today to dive into code examples, but I have [examples in the notes](/#working-examples) for…

*   looking at expandable page regions,
*   modals (watch out for focus traps!),
*   live regions (including how to override implicit `aria-live` values),
*   `aria-busy` for content that is in the process of loading,
*   form elements and validation, and the
*   'roving tabindex'.

#### Expandable areas

For expandable areas, definitely use the [HTML5 details/summary elements Opens in a new window](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/details), as they have [great native support Opens in a new window](https://www.hassellinclusion.com/blog/accessible-accordions-part-2-using-details-summary/) in various assistive technologies.

Where that's not possible, you'll have to create your own.

This example is based on the example in the fantastic book [Inclusive Components Opens in a new window](https://inclusive-components.design/), by Heydon Pickering, which I _highly_ recommend if you want to get great at creating "curb-cut" style components.

#### Modals

The ARIA dialog role is a powerful one, but there are some things you need to remember:

*   Don't set a **focus trap** (always have a focusable 'exit' element)
*   Labelling is key - you're taking someone into a new context, and those landmarks are required

#### Live regions

Let's be polite while our timer is running.

See the Pen [abdNeyp](https://codepen.io/simonborer/pen/abdNeyp) by Simon Borer ([@simonborer](https://codepen.io/simonborer)) on [CodePen](https://codepen.io).

#### Feed

Let's use JavaScript to update the `aria-busy` attribute while our feed is loading.

See the Pen [bGEpXYJ](https://codepen.io/simonborer/pen/bGEpXYJ) by Simon Borer ([@simonborer](https://codepen.io/simonborer)) on [CodePen](https://codepen.io).

#### Form elements & validation

Okay, here's an important one: validation.

Here are some of my notes from the code, but it'll probably make more sense when you read the comments in the context of the demo.

*   `role="region"` means this element and its contents are a discrete section. This particularly comes into play when **defining live regions**.
*   We set the `aria-live` attribute so that the assistive technology know this region **will be updating**.
*   aria-live="polite" means the screen reader **waits until the user is inactive** before announcing the changes.
*   The aria-atomic attribute means the screen reader will **only read out the contents that have changed**. This is especially useful in something like a chat log. You wouldn't want to hear all the message read out every time a new message appeared.

Error messages are something that we want to pay particular attention to. Of course, we wouldn't want to tell a user that there is an error message when one hasn't been triggered, so it's **never enough just to visually hide error messages**.

Developers are generally expected to create form validation for two reasons:

1.  Patterns and requirements aren't necessarily **captured by native HTML**, and
2.  Native validation is **too visually opinionated** to "fit the brand".

Note that the 'alert' role is equivalent to aria-live="aggressive", meaning that **the user will be interrupted**.

##### Roving tabindex

A fieldset of radio buttons natively has what's know as a '**roving tabindex**'. When tabbing into the group, focus goes to the selected element. You can **control the input group with your arrow keys**, but **tabbing again takes you out of the group**. This makes sense, as tabbing through the options when you've already made your selection, or when you're navigating back through the page, wouldn't be ideal.

Radio buttons come with semantic grouping (the fieldset element), but it's a good idea to group together discrete sets of inputs with role="group"

The placeholder attribute is **not accessible**. That doesn't mean you can't use it - you just need to have an alternative version of the same information.

The pattern attribute is a great way to use client-side validation, but remember - it's **not a security measure**, it's a Usability feature.

### Accessibility in the build pipeline

Whether your build pipeline is a modern miracle of containerization, or as simple `npm run build`, you can add accessibility to your build process.

A basic validation step is to **check your code with the [axe-core library Opens in a new window](https://github.com/dequelabs/axe-core)**.

![Puppeteer running axe tools](/images/puppet-axe.png)

axe-core requires a browser, however it integrates with a variety of **headless browsers** and **DOM emulators** (or whatever you'd call JSDOM), so whether you prefer Jest, Puppeteer, Webdriver, or a host of others, you can use your preferred tool to run axe-core validation without visiting every page or component under test.

Since accessibility is, at its core, _usability_, it's also wise to explore **end-to-end testing**. Given the resources, [Cypress Opens in a new window](https://www.cypress.io/) can simulate a user journey, taking into account the requirements of a screen reader user. Bonus: Cypress has the ability to [integrate axe-core Opens in a new window](https://timdeschryver.dev/blog/setting-up-cypress-with-axe-for-accessibility#the-result).

I haven't tested out this myself, so caveat emptor, but I am particularly interested in Testing Library's **user-event focused approach** to the testing workflow. It's my strong suspicion that **Testing Library > Cypress + axe-core** might be the best accessibility testing suite currently available.

* * *

**Further Reading:**

*   [Why, How, and When to Use Semantic HTML and ARIA Opens in a new window](https://css-tricks.com/why-how-and-when-to-use-semantic-html-and-aria/), _CSS Tricks_
*   [Inclusive Components Opens in a new window](https://inclusive-components.design/), _Heydon Pickering_
*   [W3 recommended code patterns](https://www.w3.org/WAI/ARIA/apg/patterns/) that only use well-supported attributes & values.
*   [A11y Support](https://a11ysupport.io/) - an up-to-date test result library for aria-\* support that needs [more community support](https://a11ysupport.io/run-tests).
*   [PowerMapper tests](https://www.powermapper.com/tests/screen-readers/aria/).
*   [Testing for Accessibility Opens in a new window](https://testing-library.com/docs/dom-testing-library/api-accessibility/), _Testing Library_
*   [How to test for accessibility with Cypress Opens in a new window](https://www.deque.com/blog/how-to-test-for-accessibility-with-cypress/), _Deque_

![](/images/infographic.svg)

Special Challenges
------------------

Beyond the usual demands of web content, your team faces some special accessibility challenges. You are…

1.  **using SPA frameworks** to build…
2.  **interactive tools** for…
3.  **data visualization**.

### JavaScript frameworks

JavaScript frameworks present some special challenges for accessibility.

The _vast majority_ of them can be side-stepped with static generation or server-side rendering (SSR), as offered by Gatsby (static site generation) or Next.js (both).

However, once you understand the needs of an accessible application to **communicate state change**, all you have to do is **orient the user** and **tell them about any changes**, while **maintaining or supplementing semantics**.

#### Announcing changes, setting focus, and using web components

Sometimes in dynamic applications, we assume the user will **read from the beginning of any new content** we put in front of them, as SPAs offer the ability to show and hide whole new pages of content without triggering a traditional page navigation event.

With this in mind, it's incumbent upon us to make sure the `<title>` element always **reflects the page's current content**, and to either make an **`aria-live` announcement**, or **set focus** whenever we expect the _user_ to be focused somewhere new.

#### Web components

Modern frameworks often leverage web components. Custom elements can be wonderful for development ergonomics, but run the risk of side-stepping useful semantics.

If you create `<wonderful-button>` starting from a `<span>` element, you will have to create all the native functionality of a button from scratch.

However, if you _extend_ the `HTMLButtonElement`, then you're **adding to the semantics**, rather than trying to reproduce it.

### Interactivity

Responding to user input is, perhaps the most challenging aspect of accessibility. However, you already have the tools you need to accomplish this.

1.  Leverage **native semantic elements** for keyboard accessibility and their implicit aria roles.
2.  **Associate controls** with their corresponding labels.
3.  **Announce changes** with `aria-live` regions.

That's it!

### Informational graphics

The final challenge: informational graphics. How do you write an alt attribute for a chart that has a thousand data points?

![A graph with just a ridiculous amount of data points](/images/Graph_of_Bicycle_Speed.png)

The short answer is, **you don't**.

Now, if your charts and graphics were superficial, I would just tell you, "write the alt text (or svg `<title>` element) to correspond with the message you want to send to the reader".

However, your charts are not superficial.

![Princess Margaret interactive visualization](/images/adenine.png)

![Another interactive visualization, showing the complexity of the interaction](/images/Sambamba.png)

In instances where there is complex data relationships, the least arduous way to present a text alternative is to **transcribe** these relationships into a table (or whatever text-based format best suits the data). Then, you **link the visualization to the text alternative** via the `aria-details` attribute.

This attribute can even point to a link to another page, should the descriptive text be too large or distracting for the layout of the page.

    <img 
        src="pythagorean.jpg" 
        alt="Pythagorean Theorem" 
        aria-details="det">
    <p>
        See an 
        <a 
            href="http://foo.com/pt.html" 
            id="det">
        Application of the Pythagorean Theorem
        </a>.
    </p>

Example courtesy of the [W3C `aria-details` documentation Opens in a new window](https://w3c.github.io/aria/#aria-details).

Even beyond interactivity and data visualization is the combination of the two - interactive data rendered by visualization libraries like D3.js, leveraging the SVG API to create visualizations that are responsive to user input directly.

Full disclosure: I haven't had the pleasure of digging deep into D3 in a professional context. And while there is some very good literature on making D3 _visuals_ accessible, there isn't any writing (including in the official documentation) about making _interactivity applied to those visuals_ accessible.

However, I suspect there is a very good reason for that: the **SVG API is a subset of the DOM API**, meaning that elements of the Scalable Vector Graphics markup language have the **same event listeners and dispatchers** as HTML elements.

While adding accessible text to SVG elements requires a slightly different approach (adding `<title>` elements, rather than alt attributes), it appears that our ability to **announce changes**, **listen for keyboard events**, and **set focus appropriately** will work as well in SVG as it does in the rest of the DOM.

While this may not by a trivial task, particularly when you factor in the added challenge of testing your solutions, it absolutely seems possible.

Now it's just a matter of doing it.

…oh, and if you do do it - definitely document it and share your solutions. There is basically no one writing about this stuff. Quite the accessibility scoop!

* * *

**Further Reading:**

*   [Accessibility in React Opens in a new window](https://developer.mozilla.org/en-US/docs/Learn/Tools_and_testing/Client-side_JavaScript_frameworks/React_accessibility), _MDN Web Docs_
*   [Accessibility Opens in a new window](https://reactjs.org/docs/accessibility.html), _React_
*   [Extending native HTML elements Opens in a new window](https://web.dev/custom-elements-v1/#extending-native-html-elements), _web.dev_
*   [Accessible SVGs: Perfect Patterns For Screen Reader Users Opens in a new window](href), _Carie Fisher (Smashing Magazine)_
*   [Creating Accessible SVGs Opens in a new window](https://www.deque.com/blog/creating-accessible-svgs/), _Deque_
*   [Data Visualizations Opens in a new window](https://accessibility.digital.gov/visual-design/data-visualizations/), _accessibility.digital.gov_
*   [How Does This Data Sound? Opens in a new window](https://blog.interactivethings.com/how-does-this-data-sound-945ed27a1a95), _Luc Guillemot_
*   [SVG API Opens in a new window](https://developer.mozilla.org/en-US/docs/Web/API/SVG_API), _MDN Web Docs_
*   [An intro to designing accessible data visualizations Opens in a new window](https://fossheim.io/writing/posts/accessible-dataviz-design/), [An introduction to accessible data visualizations with D3.js Opens in a new window](https://fossheim.io/writing/posts/accessible-dataviz-d3-intro/), and [How to create a screen reader accessible graph like Apple's with D3.js Opens in a new window](https://fossheim.io/writing/posts/apple-dataviz-a11y-tutorial/), _Sarah L. Fossheim_
*   [Adventures in D3: Accessibility Opens in a new window](https://observablehq.com/@9a849ed5a351d187/adventures-in-d3-accessibility), _Daniel Lim_

* * *

Footnotes
---------

1“large organization” means an organization with 50 or more employees in Ontario, per [Reg. 191/11: INTEGRATED ACCESSIBILITY STANDARDS Opens in a new window](https://www.ontario.ca/laws/regulation/110191#BK14:~:text=%E2%80%9Clarge%20organization%E2%80%9D%20means%20an%20organization%20with%2050%20or%20more%20employees%20in%20Ontario) under the AODA.

[↑ Back to reference 1](#footnote1Return)