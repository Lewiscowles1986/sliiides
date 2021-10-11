---
talk: Styling the **Intrinsic Web**
venue: An Event Apart Fall Summit
date: 2021-10-11
script: |
  I'm here to talk about the future of CSS,
  but in order to understand where we're going —
slides:

# Cascade Intro ---------
- pre: The _Present of CSS_
  script: |
    we need to understand where we are –
- pre: The _Past of CSS_
  script: |
    And how we got here.

- pre: CSS exists
  title: For **Two Reasons**
  script: |
    In my mind CSS exists for two primary reasons

# responsive
- pre: 1. _CSS_ makes
  title: Styles **Responsive**
  script: |
    First,
    CSS makes styles responsive –

- pre: |
    `@media`
  title: |
    _`min-width`_
  script: |
    and not just to
    dimensions of a viewport --

- pre: |
    `@media`
  title: |
    _`prefers-reduced-motion`_
  script: |
    But user preferences --

- pre: |
    `@media`
  title: |
    _`hover`_
  script: |
    and device interfaces.

- img: no-harm/www-browser.jpg
  alt: The first world wide website & graphic browser
  position: top
  caption: |
    [WWW HyperMedia Browser](https://worldwideweb.cern.ch/browser/)
    & *Editor*
  script: |
    When Sir Tim
    and the team at CERN
    released the first
    hypermedia browser,
    it was designed for the NeXT machine,
    with a fancy graphic interface
- img: process/ibm-pc.jpg
  alt: Old IBM desktop
  position: top
  script: |
    But you can't make a web that's "world-wide",
    by saying "it works on my machine"
    and everyone else is an "edge-case".
- img: no-harm/line-mode.jpg
  alt: The second browser, a text-only terminal
  position: top
  caption: |
    [Line Mode Browser](http://line-mode.cern.ch/www/hypertext/WWW/TheProject.html),
    developed by **Nicola Pellow**
  script: |
    So right away they release a second browser,
    designed to work on any terminal with an internet connection.
- quote: |
    Web **for all**. Web **on everything**.
  cite: W3C [Mission Statement](w3.org/Consortium/mission.html#principles)
  script: |
    This becomes the _mission statement_ of the web --
    web for all, web on everything.
- img: unfriendly/braille.jpg
  alt: Braille interface and headphones
  script: |
    That includes assistive devices --
- img: unfriendly/agnesscott/smart-home.png
  alt: Google Home, Amazon Echo, and Apple HomePod
  script: |
    And non-visual media --
    always with the end-user in control of the outcome.

- quote: |
    There are **too many variables to consider.**
  cite: Keith J Grant
  caption: |
    [Resilient, Declarative, Contextual](https://keithjgrant.com/posts/2018/06/resilient-declarative-contextual/)
  script: |
    There are too many variables for us to consider,
    so we hand some of that control over to the browser,
    and to the user, and the device they're on.
- quote: |
    *Graphic design* of **unknown content**
    on an **infinite and unknown canvas**,
    across **operating systems, interfaces, & languages**...
  cite: me, on twitter...
  script: |
    Designing for the web is designing for _change_,
    designing systems that respond and adapt
    to unknown content on an infinite and unknown canvas,
    across operating systems, interfaces, & languages.

- quote:
    Provide **hints** that the browser **may or may not use**.
  cite: Håkon Lie
  script: |
    We provide hints and suggestions,
    semantic clues,
    but only the browser
    can put it all together.

- title: The **Cascade**
  script: |
    And the cascade describes that process --

- quote: |
    **An ordered list (cascade) of style sheets** …
    can be referenced from the same document.
  cite: Håkon Lie
  caption: https://w3.org/People/howcome/p/cascade.html
  script: |
    by accepting style sheets
    from everyone involved --

- quote: |
    The **user/browser** specifies _initial preferences_
    and **hands the remaining influence over** to the document.
  cite: Håkon Lie
  caption: https://w3.org/People/howcome/p/cascade.html
  script: |
    _Browsers_ & _users_ establish
    global defaults and preferences across the web,
    and then we fill in the details
    of our particular site

- title: Cascade **Origins**
  md: |
    - 🎨 **Author** (Document)
    - 👥 **User** Preferences
    - 🖥 **User Agent** (Browser)
  script: |
    These are the primary "cascade origins" --
    each one representing a
    different set of needs and concerns,

- pre: The _Cascade_
  title: Resolves **Merge Conflicts**
  script: |
    But these different perspectives,
    can sometimes be in conflict.
    So the rules of cascade & inheritance
    describe how to merge all three origins,
    and resolve those conflicts.

- md: |
    1. 🎨 **Author** (Document)
    2. 👥 **User** Preferences
    3. 🖥 **User Agent** (Browser)
  script: |
    In most cases,
    the user preferences will override the browser defaults,
    and (for better or worse)
    we're allowed to override both of them.

- quote: |
    If conflicts arise **the user should have the last word**,
    but one should also allow the author to attach style hints.
  cite: Håkon Lie
  caption: https://w3.org/People/howcome/p/cascade.html
  script: |
    But when things really get heated,
    when it really matters,
    the user and browser can insist --

- title: ❗**important**
  sub: A balance of power
  script: |
    That some styles are
    more important than others --

- md: |
    1. ==❗🖥 User Agent **Important**==
    2. ==❗👥 User **Important**==
    3. ==❗🎨 Author **Important**==
    4. 🎨 Author Styles
    5. 👥 User Preferences
    6. 🖥 User Agent Defaults
  script: |
    Creating _important origins_
    that cascade in reverse order.
    Important author styles aren't that special.
    That's us in the middle,
    with our normal and important styles side-by-side.
    But users can override us when they need to,
    and the browser finally decides
    what's out of bounds,
    what's possible on this device,
    what features are supported,
    and so on.

# reusable
- pre: 2. Style*Sheets*
  title: Make Styles **Reusable**
  script: |
    The second goal of CSS
    is to make our design objects reusable...

- lang: html
  code: |
    <P><FONT SIZE="4" COLOR="BLUE">…</FONT></P>
    <P><FONT SIZE="4" COLOR="BLUE">…</FONT></P>
    <P><FONT SIZE="4" COLOR="BLUE">…</FONT></P>
    <P><FONT SIZE="4" COLOR="BLUE">…</FONT></P>
    <P><FONT SIZE="4" COLOR="BLUE">…</FONT></P>
  script: |
    Instead of repeating the same styles
    over and over in our HTML

- title: CSS **Selectors**
  code: |
    p {
      color: blue;
    }
  script: |
    We can use selectors to apply styles broadly –

- pre: We use
  title: |
    **Classes** & **Attributes**
  caption: |
    🤔 Lingo taken from Object Oriented Programming
  script: |
    Creating patterns
    based on things like
    classes and attributes --

- pre: Combine them
  title: To **Compose Objects**
  script: |
    Which we can combine,
    to compose re-usable objects --

- title: |
    Design **Systems** & \
    **Component** Libraries
  script: |
    -- Design Systems & Component Libraries.

- face: nicolesullivan.jpg
  pre: |
    @stubbornella
  title: |
    **Nicole** Sullivan
  sub: |
    2009 [**Object Oriented CSS**](https://github.com/stubbornella/oocss)
  script: |
    CSS is object-oriented at its core,
    built around the semantic objects of HTML.
    People like Nicole Sullivan

- face: nataliedowne.jpg
  pre: |
    @natbat
  title: |
    **Natalie** Downe
  sub: |
    2008 [**CSS Systems**](http://www.slideshare.net/nataliedowne/css-systems-presentation)
  script: |
    And Natalie Downe
    helped to develop a systemic approach
    to all of this:
    describing fluid grids,
    and re-usable patterns.

- img: css-next/rwd.jpg
  alt: |
    A List Apart:
    Responsive Web Design
    by Ethan Marcotte (May 25, 2010)
  caption: |
    [Responsive Web Design](https://alistapart.com/article/responsive-web-design/)
    by **Ethan Marcotte**, 2010
  script: |
    And then browsers implemented Media Queries,
    and Ethan Marcotte coined the term
    "Responsive Web Design"

- title: Technical Ingredients…
  md: |
    - Fluid grids (%)
    - Flexible images (%)
    - Media queries
  script: |
    Based on fluid grids, flexible images, and media queries.
    Everything in percentages,
    adapting to the size of the browser
    at different media-query breakpoints.
    It's a really powerful approach,
    and it took over the industry for years.
    But now, while the idea of a responsive web,
    that core vision,
    is just as important as ever,
    the technology has changed dramatically.

- title: |
    **Flexbox** & **Grids** & …
  sub: |
    `min-`/`max-content`, `fit-content`, `minmax()`, `clamp()`, etc…
  script: |
    The web is still a fairly new medium,
    and we're rapidly developing new features
    to make it more responsive, and more reusable.
    Features like flexbox and grid
    (which have been around for years),
    and now also intrinsic sizing, aspect-ratios, and more.

- face: jensimmons.jpg
  pre: |
    @jensimmons
  title: |
    **Jen** Simmons
  md: |
    [Everything You Know About Web Design Just Changed](https://youtu.be/jBwBACbRuGY)
  script: |
    We're entering a new era of web design,
    and web layout,
    and we need to update how we work and how we think
    to really take advantage of these new features.
    You might say it's an evolution,
    not a revolution, but it's an important shit to understand.
    What Jen Simmons calls --

- title: |
    **Intrinsic** Web Design
  script: |
    Intrinsic Web Design.
    Rather than stripping out the
    intrinsic size of every image,
    and building 12-column percentage-based grids,

- pre: Responsive & Reusable
  title: |
    **Components**
  script: |
    we now have the power to make designs
    both responsive and reusable at a component level,
    building patterns and layouts
    that are based on the content itself.
    Taking that _intrinsic_ information,
    and building systems out of it.

- caption: |
    **Intrinsic Web Design** by
    [Jen Simmons](https://twitter.com/jensimmons/status/980980521848127488)
  md: |
    1. **Fluid** & **Fixed**
    2. Stages of **Squishiness**
    3. Truly **Two-Dimensional** Layouts
    4. **Nested** Contexts
    5. **Expand** & **Contract** Content
    6. Media Queries, **As Needed**
  script: |
    These new tools allow us to
    create responsive layouts that mix fluid and fixed components.
    We can go beyond fluid percentages
    to use flex values, grid fractions, minmax, clamp,
    and other tools to create stages of intrinsic squishiness --
    components growing and shrinking at different rate.
    We get truly two-dimensional layouts,
    nested contexts can use different layout rules,
    and content can expand and contract in various ways.
    Rather than designing outside-in with media queries,
    we can spend more time designing from the content out!

- quote: |
    Our medium is not done.
    Our medium is still
    **going through radical changes**.
  cite: Jen Simmons, *Designing with Grid*
  script: |
    We've come a long way,
    but we're still not done.
    CSS is a living language going through radical changes,
    and many of the new features build on this idea.

- pre: What's _Painful_
  title: About **Intrinsic Design**?
  script: |
    We're looking at the pain points that teams run into
    when they're working on intrinsic components,
    and asking how we can address those issues.
    I've been working on
    three of these new specifications in particular,
    and want to show you what's coming.

- title: CSS **Selectors** & **Specificity**
  script: |
    So let's jump back to the cascade for a minute,
    and selectors specifically.
    The cascade is so central to CSS
    that it doesn't get a lot of updates,
    but over the years it's starting to show some age.

- title: 💥 Conflict!
  css: |
    button          { background: gray; }
    .action         { background: darkblue; }
    [type=“submit”] { background: darkgreen; }
    #send           { background: maroon; }
  script: |
    Like the cascade origins,
    selectors create another potential conflict
    for the cascade to resolve.
    Since we can use multiple different selectors
    to target the same element --

- title: Selector **Specificity**
  caption: |
    [heuristic](https://en.wikipedia.org/wiki/Heuristic):
    a practical assumption
    that approximates the desired goal
  script: |
    The cascade needs to determine a winner,
    so it uses a clever heuristic --
    an educated guess --
    called specificity.

- md: |
    - `*` **(universal)**
    - `type`
    - `.class` & `[attr]`
    - `#ID`s **(single-use)**
  script: |
    We assume that each selector type is meant to
    represent a different goal or perspective,
    based on how narrowly that selector has been targeted.

- pre: |
    universal/type »
  title: Global **Defaults**
  script: |
    The most generic selectors,
    help us paint in broad strokes
    to establish low-priority defaults --
- pre: |
    attrs/classes »
  title: Common **Patterns**
  script: |
    Classes and attributes
    allow us to describe
    higher-priority patterns,
    that make up the majority of our styles --
- pre: |
    ID/style »
  title: Singular **Overrides**
  script: |
    Then one-off ID's are both
    the most narrowly targeted,
    and the highest priority.
- md: |
    1. *Unique* `#ID`s
    2. *Reusable* `.class`es & `[attributes]`
    3. *Element* `type`s
    4. *Universal* `*`
  script: |
    We can combine these selectors in various ways,
    but their specificity is always compared
    one "layer" at a time.
    Selectors with an ID will always override
    selectors without an ID,
    and so-on down the list.

- img: patterns/itcss-layers.png
  fit: contain
  background: white
  caption: |
    [**Inverted Triangle**](http://technotif.com/manage-large-css-projects-with-itcss/)
    CSS (ITCSS), by Harry Roberts
  script: |
    This is a rough approximation
    of the layers in our code --
    moving from global abstractions
    to narrowly targeted components and overrides. --

- title: Heuristics Can 💥**Fail**💥
  script: |
    But it's not perfect.

- title: Especially "**At Scale**"
  script: |
    As our projects become larger and more complex
    with more distributed teams
    and third-party integrations,
    there are _a lot_ of situations
    that don't fit the rule --

- css: |
    table[rules]:not([rules=""])> tr > td,
    table[rules]:not([rules=""])> * > tr > td,
    table[rules]:not([rules=""])> tr > th,
    table[rules]:not([rules=""])> * > tr > th,
    table[rules]:not([rules=""])> td,
    table[rules]:not([rules=""])> th
    {
      border-width: thin;
      border-style: none;
    }
  cation: |
    Firefox user-agent styles (`resource://gre-resources/html.css`)
  script: |
    Some low-priority defaults are very specific --

- css: |
    [hidden] {
      display: none !important;
    }
  script: |
    While some generic attributes,
    really ought to have more weight behind them.

- md: |
    1. ~~*Unique* `#ID`s~~
    2. ==*Reusable* `.class`es & `[attributes]`==
    3. ~~*Element* `type`s~~
    4. ~~*Universal* `*`~~
  script: |
    And out of all these specificity layers,
    there's only one that we can
    both _customize_ **and** _reuse_.
    Classes & attributes.

- css: |
    .block .element.modifier { /* 3 */ }
    .block__element--modifier { /* 1 */ }
  script: |
    So we spend a lot of our time
    fighting over _how many attributes_
    should be in a selector --

- img: patterns/itcss-metrics.png
  fit: contain
  background: white
  caption: |
    [**Inverted Triangle**](http://technotif.com/manage-large-css-projects-with-itcss/)
    CSS (ITCSS), by Harry Roberts
  script: |
    With rules and conventions
    to ensure our cascade specificity --

- img: patterns/itcss-layers.png
  fit: contain
  background: white
  caption: |
    [**Inverted Triangle**](http://technotif.com/manage-large-css-projects-with-itcss/)
    CSS (ITCSS), by Harry Roberts
  script: |
    matches carefully crafted layers of _intent_,

- title: ❗**important**
  sub: A balance of power
  script: |
    And throwing importance like a grenade
    when we get stuck,

- css: |
    .bootstrap-thing {
      font-weight: bold !important;
    }
  script: |
    Or if one part of the system
    doesn't play by the same rules.

# Layers ----------------
- section: |
    Cascade **Layers**
  caption: |
    [Working Draft](https://www.w3.org/TR/css-cascade-5/)
  script: |
    So that brings us to our first new feature:
    Cascade Layers.

- img: patterns/itcss-layers.png
  fit: contain
  background: white
  caption: |
    [**Inverted Triangle**](http://technotif.com/manage-large-css-projects-with-itcss/)
    CSS (ITCSS), by Harry Roberts
  script: |
    This will allow us to create our own
    custom layers of the cascade,
    that more explicitly represent
    the different parts of a system --
    and potentially different teams on a project,
    or even third-party code.
    You can think of these as
    customizable _layers of specificity_ --

- title: Stacked in **Layers**
  md: |
    1. Components?
    2. Themes?
    3. Frameworks?
    4. Resets?
  script: |
    Or like our own custom CSS Origins --
    but for things like resets, defaults,
    frameworks, themes, components,
    utilities --
    anything we want,
    in whatever order we need.

- md: |
    1. ❗**Important** Resets
    2. ❗**Important** Themes
    3. ❗**Important** Components
    4. Components
    5. Themes
    6. Resets
  script: |
    And the `important` flag works as intended.
    Inverting the layers
    when it becomes necessary for a lower layer
    to insist on something,
    and punch above it's weight.

- css: |
    @import url(headings.css) layer(default);
  script: |
    We can define a layer,
    give it a name,
    and add styles to it
    using either a layer function on the import rule --
- css: |
    @layer default {
      audio[controls] { display: block; }
      [hidden] { display: none !important; }
    }
  script: |
    Or by nesting styles inside the new at-layer rule --
- css: |
    @import url(headings.css) layer(default);

    @layer default {
      audio[controls] { display: block; }
      [hidden] { display: none !important; }
    }
  script: |
    -- Or both. Here we're creating a "default" layer
    with the `headings.css` import,
    and using the at-rule
    to add a few more styles to the same
    "default" layer.

- css: |
    @layer default { /* lowest */ }
    @layer theme { /* higher */ }
    @layer components { /* highest */ }
  script: |
    Layers stack in the order they were first defined,
    with the first layer at the bottom,
    and the last layer at the top.
    The highest layer will win conflicts,
    no matter what specificity is used
    for the selectors inside.

    Specificity only matters _inside_ each layer.

- css: |
    @layer framework {
      .menu > .dropdown > .item {
        background: whitesmoke;
      }
    }

    @layer override {
      .menu-item {
        background: lightcyan;
      }
    }
  script: |
    So this single `menu-item` class wins over
    the combined `menu`, `dropdown`, and `item` classes,
    because the `override` layer is defined
    after the `framework` layer.
    This makes it simple to override a tool like bootstrap,
    no matter how they write their selectors.

- css: |
    @layer default { /* … */ }
    @layer theme { /* … */ }

    /* still a lower layer than "theme" styles */
    @layer default { /* … */ }
  script: |
    But we don't need to keep all our styles in that same order.
    Once a layer has been established,
    we can add to it from anywhere in our code.
    The priority is based on when the layer name
    _first appears_.

- css: |
    @layer default;
    @layer theme;
    @layer components;

    @layer default {
      * { box-sizing: border-box; }
    }
  script: |
    We can even use the at-layer rule without any styles,
    just a name,
    to establish our order up front.
    After that,
    we load the code in any order,
    and it will just work.

    That's especially important if we're using CSS-in-JS,
    where styles might load in any order.

- css: |
    @layer default, theme, components;

    @layer default {
      * { box-sizing: border-box; }
    }
  script: |
    And there's a shorthand syntax to make that even easier,
    using a comma-separated list of layer names.

- css: |
    @layer default, tools, theme, components;
    @import url(tools.css) layer(tools);
  script: |
    One of the goals here
    is to make it so that we as authors
    get to define exactly where
    third-party tools belong
    in our layering.
    No matter what specificity those tools use internally,
    or whatever layers they create,
    we can always override them
    without resorting to specificity hacks.

- css: |
    /* tools.css */
    @layer theme { /* … */ }
    @layer components { /* … */ }
  script: |
    And this also gives
    framework or component-library authors
    a way to provide layers
    we can hook into --

- css: |
    @import url(tools.css) layer(tools);

    @layer tools.theme { /* … */ }
    @layer tools.custom { /* … */ }
  script: |
    Either directly,
    or by wrapping those layers into a contained namespace.
    We can create or access
    "nested" or "name-spaced" layers
    using a dot-notation to combine the names.

- css: |
    @layer tools {
      @layer custom {
        /* tools.custom */
      }
    }
  script: |
    Or we can actually nest the layer rules --
    it works the same way.

- title: |
    More Cascade **Control**
  script: |
    This gives us a lot more control
    over our corner of the cascade,
    so we're not totally reliant
    on selector specificity
    and code-order to determine
    what takes precedence.
    We have control over the cascade!

- title: |
    Fewer **Hacks**
  script: |
    Hopefully that allows us to replace
    all our specificity & importance hacks
    with more clearly defined patterns.

- pre: |
    _Unlayered_ styles
  title: |
    ~~Default Lowest Priority~~ \
    Default **Highest Priority**
  caption: |
    ⚠️ Changed 2021/10/06
    [Issue #6284](https://github.com/w3c/csswg-drafts/issues/6284#issuecomment-937262197)
  script: |
    Of course,
    we don't have to put all our styles into these layers --
    and for the sake of progressive enhancement,
    we likely want to start adding layers slowly.

    Un-layered styles will work the same way they always have,
    and belong to an implied "base layer"
    below all the others.

- title: Possible to **Polyfill**
  sub: Do we also need `@supports (layers)` conditional?
  script: |
    We should be able to polyfill layers
    with existing specificity tricks,
    to make it work on old browsers if needed.
    We could also consider adding an at-supports
    feature test if that seems useful.

- title: Cascade Layer **Resources**
  md: |
    - [Working Draft Spec](https://www.w3.org/TR/css-cascade-5/)
    - [Full layers Explainer](https://github.com/oddbird/css-sandbox/blob/main/src/scope/explainer.md)

# @@@ CUT IN AROUND 13:05

- img: css-next/breaking.jpg
  alt: Breaking Headlines
  script: |
    I'm sorry to interrupt you, Miriam,
    we have breaking news from the future.
    Your future.
    But still pre-recorded,
    so also still the past,
    for anyone watching this.
    The more recent past?
    My… previous future?
    Whatever, time is hard.
    It's a week after I recorded the initial talk,
    and there's some breaking news to report!

- title: |
    🚨 Try **Cascade Layers** Today 🚨
  sub: |
    [CodePen collection of layer demos](https://codepen.io/collection/BNjmma)
  md: |
    - **Firefox Nightly**: \
      » `about:config` \
      » `layout.css.cascade-layers.enabled`
    - **Chrome Canary**: \
      » `chrome://flags` \
      » `Enable CSS Cascade Layers`
    - **Safari Technology Preview**: \
      » `Develop`/`Experimental Features` (menu) \
      » `CSS Cascade Layers` \
      » (#133 has unlayered styles reversed, likely fixed in #134)
  caption: |
    ⚠️ Changed 2021/10/05
    [Issue #6284](https://github.com/w3c/csswg-drafts/issues/6284#issuecomment-937262197)
  script: |
    So:
    did I say Chrome & Safari are working on implementations?
    That's still true,
    but now Firefox has jumped ahead,
    and actually released a public prototype
    of cascade layers behind a flag!
    We can go to `about:config`, search for `cascade-layers`,
    and turn that on to start testing it out!

    At time of recording,
    Chrome has a runtime flag,
    which is less "public" a bit harder to use,
    but I've left a link to instructions here in my slides.
    Again, that will probably change by the time you watch this.
    So it's a good thing future-future Miriam is in the chat with you,
    and can hopefully provide you with any updated links.
    Miriam, do the thing, please.

    Since we have a prototype now, we should check it out, right?

- pen: layers-support
  caption: |
    ⚠️ Changed 2021/10/06
    [Issue #6284](https://github.com/w3c/csswg-drafts/issues/6284#issuecomment-937262197)
  script: |
    Layers are meant to help with overall style architecture,
    which makes it hard to capture a real use-case
    in a single, concise demo.
    But let's start with something real basic,
    to see some layers in action.
    In this case we're just showing that
    even low-specificity selectors in our override layer
    take precedence over high-specificity styles
    that are not layered.

    **Demo**: We can take that a bit farther
    by adding a second layer,
    and then using the layer-sorting statement
    to re-arrange which one takes precedence.
    We can also add `!important` flags here,
    if we want to see how that flips the priority.

# @@@ Demo at 21:25
- img: css-next/aea-beyond-vars.jpg
  alt: |
    Screenshot of AEA presentation interface for my talk,
    Beyond Variables at An Event Apart Spring Summit
  script: |
    If you saw my talk
    from the Spring Summit --
    Beyond Variables --
    it was all about using custom properties
    (CSS variables).
    And I showed this demo
    with a set of buttons,
    where everything comes down to the order of our styles.
    But let's say we want a more robust solution,
    so that the order doesn't matter as much?

    And I showed a way
    that you can stack custom properties
    so that the disabled state property
    always overrides the button theme property.
    Well now we can do that same thing with layers...

- pen: layers-btn
  script: |
    [demo]

- title: github.com/w3c/csswg-drafts
  script: |
    So now that we have all three major browser engines implementing,
    this spec is pretty stable.
    We're not expecting any major changes before this comes out --
    and it could roll out in all the major browsers pretty quickly.

    So I just want to take a second
    and highlight that process.
    How we got here.
    And how every step along the way is public,
    and something you can participate in.
    It all start on the csswg-drafts github,
    and that's where most of the action is.

- pre: Starts with
  title: The [**Proposal**](https://github.com/w3c/csswg-drafts/issues/4470) on Github
  script: |
    It all started with a proposal.
    I had no idea how this feature should look or work,
    I just documented the problems with specificity
    and suggested:
    _hey, what if authors had a better way to control this_?
    That lead to a lot of conversation,
    both in the issue thread,
    and on CSS Working Group calls
    (which are then transcribed and posted back to the issue).

    This was all before I joined the group,
    so I was relying on those transcripts in order to participate.
    There was some excitement, and also some concerns,
    so they asked me to work with a few people
    and flesh out a more detailed proposal
    with actual syntax.
    Again, we did that, and reported our progress back to the issue.
    Post a draft, get feedback, make adjustments, repeat.

- title: |
    [Editor's Draft](https://drafts.csswg.org/css-cascade-5/)
  script: |
    After a people were happy with the direction,
    we moved that into an Editor's Draft specification.
    This is like an official working branch for specs,
    that you plan to merge once it's been reviewed,
    and everyone agrees on the changes.

- title: |
    [Working Draft](https://www.w3.org/TR/css-cascade-5/)
  script: |
    At some point we had enough detail,
    and enough agreement,
    that the CSS Working Group approved a Working Draft.
    The first one is called a First Public Working Draft.

    Over the last year, we've been editing and refining:
    make changes in the Editor's Draft,
    then review and publish those changes as a new Working Draft.
    Back and forth.

    At the bottom of the document
    you can often see issues that have been documented,
    sometimes with links back to Github.
    The whole process is happening in public.

- title: |
    [**Web-Platform-Tests**](https://web-platform-tests.org/).org
  sub: |
    [wpt.live](http://wpt.live/) | [wpt.fyi](http://wpt.fyi/)
  script: |
    Once browsers start implementing the new feature,
    they also start to create Web Platform Tests.
    These is a test suite shared by all the browsers,
    the entire web platform,
    to test against.
    It's like caniuse, but fewer browsers and more details.
    You can run tests in your current browser
    by going to `wpt.live`,
    or see a report of the test status
    in major browser engines at `wpt.fyi`,
    or learn more and get involved at `web-platform-tests.org`.

- quote: |
    One of **the best ways a web developer can truly help**
    make websites work the same in every browser
    is to help **create more tests for WPT**.
    We all want interoperabilty.
    Testing is a way to get there, and not regress.
    But **we need more tests** written to check on more things.
  cite: Jen Simmons, [Twitter](https://twitter.com/jensimmons/status/1431432254211956736)
  script: |
    Seriously,
    if you're interested in web-standards
    or browser compatibility,
    this is a great place to get involved.

    Ok, I just wanted to show you all that.
    Back to you, past-past Miriam.
    In three, two …

# Scope ----------------
- section: |
    **Scoped** Styles
  script: |
    The next feature is also about how selectors work.
    With "scope",
    we're trying to address two issues
    that come up regularly,
    and drive people to use tools & conventions
    like BEM syntax or CSS-in-JS.

- pre: 1. Avoid
  title: |
    **Naming** Conflicts
  sub: (across _large teams_ & _projects_)
  script: |
    The first goal is to avoid
    naming conflicts as our projects grow.

- pre: 2. By
  title: Expressing **Membership**
  sub: (through _lower boundaries_ & _proximity_)
  script: |
    Which we can solve
    by focusing on our second goal:
    expressing "membership" or "ownership"
    in our selectors.

- css: |
    .title { /* global */ }
    .post .title { /* nested */ }
  caption: |
    _Membership_ is distinct from _ancestry_
  script: |
    While nested selectors
    might seem like a way to
    express membership --
    in this case
    a title that is inside a post --

- css: |
    .title { /* global */ }
    .post .title { /* nested */ }

    .post__title { /* BEM */ }
  caption: |
    _Membership_ is distinct from _ancestry_
  script: |
    That's not quite the same thing
    as _a post-title_.
    The first one only describes a nested structure,
    but the second describes
    a more clear membership in a component pattern.
    Not _all the titles in a post_,
    just the title that _belongs to_ the post.

- css: |
    .post__title { /* BEM */ }
    .title[data-JKGHJ] { /* Vue */ }
  script: |
    We don't have a good way to convey that
    using our current CSS selectors,
    unless we invent a new unique name
    for every kind of title,
    based on what it belongs to --
    either manually using a convention like BEM,
    or automated with JavaScript compilers.

- html: |
    <h2 class="title post__title">
  script: |
    And if we want some global title styles,
    we end up using multiple classes --
    and hoping the more targeted pattern will override
    the global pattern.

- img: csswg/components.jpg
  alt: wireframe of a site, with multiple nested components
  fit: contain
  background: '#e5e5e5'
  caption: |
    A "donut scope" with
    _lower boundaries_
    similar to shadow-DOM `slots`
  script: |
    Another way to think about this is
    to say that some components
    have lower boundaries --
    the component itself is a "donut"
    with a hole in the middle for content.
    We should be able to style a tab component,
    or a media-object,
    without worrying that we might accidentally
    style _everything inside_ it by mistake.

- pre: Different from
  title: Shadow-DOM **Encapsulation**
  script: |
    This might sound similar to shadow-DOM encapsulation,
    and there is certainly cross-over
    between scope & encapsulation.

- img: csswg/widget.jpg
  fit: contain
  alt: |
    Diagram shows a widget with solid boundaries,
    which cannot be penetrated
    in either direction
    (global styles can't get in, widget styles can't get out)
  background: white
  caption: |
    **Encapsulation**
    is designed for _isolated DOM widgets_
  script: |
    But the Shadow-DOM is designed
    around highly-isolated widgets.
    Boundaries are defined in the DOM,
    so that each element has a single scope,
    and styles are isolated from getting in or out.
    Scopes are never allowed to overlap at all.

- pre: Build-tools
  title: Provide **Scoped Styles**
  sub: BEM, CSS Modules, Vue, JSX, Stylable, etc
  script: |
    While that kind of encapsulation is useful sometimes,
    it's very different from the lighter-touch
    "scope" that we get from existing
    build-tools and conventions --

- img: csswg/scoped.jpg
  alt: |
    Diagram shows a component with porous boundaries,
    all styles can penetrate, or establish their own lower boundaries
  fit: contain
  background: white
  caption: |
    **Scope**
    is designed for _a unified system_
  script: |
    Where scopes reference the DOM,
    but they're more fluid --
    able to overlap,
    and integrate more smoothly
    with global design systems.
    Different scopes can have different boundaries,
    and global styles continue to apply globally.

    This provides us with a much lower-impact alternative.
    Scopes are defined in CSS,
    and can be re-used across components,
    or overlap & cascade together.

- css: |
    @scope (.media) to (.content) {
      img { /* only images that are "in scope" */ }
    }
  caption: |
    [CSSWG Scope Issue](https://github.com/w3c/csswg-drafts/issues/5809)
  script: |
    So we're proposing an at-scope rule,
    that accepts both a scope-root selector
    (in this case `media`)
    and a lower-boundary selector
    (in this case `content`).
    Any selectors inside the at-rule
    only apply _between_ the root
    and the lower-boundary.
    In this case we're styling images inside media,
    unless they are also inside the media content.

- md: |
    ```css
    .light-theme a { color: purple; }
    .dark-theme a { color: plum; }
    ```
  caption: |
    _DOM Proximity_
    is similar to _inheritance_
  script: |
    We can also talk about this
    in terms of _proximity_.
    These two selectors apply to links
    inside a light-theme or dark-theme class.
    And that works great,
    as long as we never nest one theme inside the other.
    Since our selectors both have the same specificity,
    and _ancestor proximity_ is not part of the cascade --

- demo: scope-proximity-issue
  script: |
    dark-theme will always override light theme
    in nested situations.

- css: |
    @scope ([data-theme=light]) to ([data-theme]) {
      a { color: purple; }
    }
    @scope ([data-theme=dark]) to ([data-theme]) {
      a { color: plum; }
    }
  script: |
    We can solve that problem using lower-boundaries,
    so that themes never bleed into each other --

- css: |
    @scope ([data-theme=light]) {
      a { color: purple; }
    }
    @scope ([data-theme=dark]) {
      a { color: plum; }
    }
  script: |
    But I think it would also make sense for
    scope proximity to be added as part of the scope feature.
    When specificity is equal,
    we would default to using the "closer" scope-root.
    This part of the spec is still being debated.

- title: A **Donut Selector**?
  script: |
    There has also been talk about adding
    some form of lower-boundary or donut selector syntax.

- css: |
    @scope (.media) to (.content) {
      img { border: red; }
    }

    /* as a selector, without proximity rules? */
    img:in(.media / .content) { border: red; }
  script: |
    That could be useful for some cases,
    but wouldn't have the same power
    to handle proximity relationships
    or wrap multiple selectors.

- title: Scope **Resources**
  md: |
    - [Full scope Explainer](https://github.com/oddbird/css-sandbox/blob/main/src/scope/explainer.md)
    - [CSSWG Issue](https://github.com/w3c/csswg-drafts/issues/5809)
    - [Draft Spec](https://github.com/w3c/csswg-drafts/issues/5809)
  script: |
    There's a lot more to the proposal,
    which you can look into if your interested.
    The CSSWG has expressed interest,
    feedback is welcome,
    and Chrome plans to prototype this soon,
    for more testing.

    But for now,
    this one is still theoretical.

# Container Queries ----------------
- section: |
    **Container** Queries
  script: |
    And that brings us to the real reason we're here.
    Container Queries.

- pen: media-v-container
  print: media-v-container-break
  script: |
    - Media queries let us respond to viewport
    - Same element in multiple containers,
      viewport isn't useful
    - Respond to containers instead

- img: csswg/cq-nested.jpg
  alt: |
    Nested grid-item containers
    inside the main container,
    also use small card layout
  fit: contain
  background: white
  caption: |
    Containers can be nested
  script: |
    No matter how those containers are nested.

- title: Layout **Loops**
  sub: CSS _Context_ vs _Content_
  script: |
    But trying to measure a "container" in CSS,
    and then make changes based on that measurement,
    poses a bit of a paradox.

- demo: normal-flow
  script: |
    One of the coolest responsive features in CSS,
    which we don't talk about nearly enough,
    is the way we calculate layout
    based on both context and content.
    Add more content,
    and a container will try to grow,
    but it might also be constrained by context,
    or explicit sizing.

    That's very cool,
    but if you add container queries,
    it becomes an infinite loop:
    as the container gets larger, we make the content smaller,
    which makes the container smaller,
    which makes the content larger.

- pre: 2010-2020
  title: 🚧 Laying **Foundations** 🚧
  script: |
    So for a long time,
    this seemed impossible to implement.
    But behind the scenes,
    a lot of people
    have been laying the groundwork in browsers.

- title: 2020 **Proposals**
  md: |
    - David Baron:
      [`@container`](https://github.com/dbaron/container-queries-implementability) \
      _limited by containment_
    - Brian Kardell:
      [`switch()`](https://bkardell.com/blog/AllThemSwitches.html) \
      _limited to paint_
  caption: |
    Different tradeoffs, worth pursuing both
  script: |
    Last year two proposals emerged,
    showing different ways we might pull this off.
    Both are interesting,
    but David Baron's approach has the most momentum right now,
    and I've been working on it
    to flesh out some of the details,
    and start writing a specification.

- title: Defining **Containers**
  script: |
    The first thing we need to do
    is define our containers --

- img: csswg/cq-nested-containers.jpg
  alt: |
    We need to define the containers
    for our cards to query
  fit: contain
  background: white
  script: |
    Any element we want to measure,
    query, and respond to.

- title: No **Content Sizing**
  script: |
    In order to avoid any layout loops,
    we need to turn off content-based sizing
    on those elements.
    Our containers need to be sized
    without reference to anything inside it.

- css: |
    .container {
      contain: size layout style;
    }
  script: |
    We already have a property for this!
    It's called `contain`,
    and allows us to "contain" various types of things.

    Size containment turns off content-based sizing,
    layout containment is kinda like a clearfix --
    wrapping around floats and margins --
    and style containment keeps list-counters
    from leaking out.

    And we're going to need all three of these
    for our container queries work.

- pre: 2D size containment
  title: Is **Too Restrictive**
  caption: |
    Need a flexible dimension ("Be afraid of heights")
  script: |
    But size-containment is…
    bad in most cases.
    It's just not possible to build all our layouts
    with explicit width and height!

- pen: css-rad
  script: |
    We need one axis to be fluid,
    and respond to content,
    so that we don't create accidental overflow.

- pre: We need
  title: |
    **Inline Size** Containment
  caption: |
    See the
    [Issues with Single-Axis Containment](https://github.com/w3c/csswg-drafts/issues/6426)
  script: |
    And usually we want to contain the `width`,
    or the inline-dimension,
    and allow the `height` to grow or shrink
    with the content.
    That's pretty standard web-layout best practice.

- css: |
    .container {
      contain: inline-size;
    }
  caption: |
    See the
    [Issues with Single-Axis Containment](https://github.com/w3c/csswg-drafts/issues/6426)
  script: |
    So we're adding an option to make
    single-axis containment possible.
    Contain `inline-size`.
    This isn't easy,
    and it's not totally solved, either.
    You can find more details
    in the linked issue.

- img: css-next/dragons.jpg
  position: bottom
  title: ⚠️ Dragons
  caption: |
    See the
    [Issues with Single-Axis Containment](https://github.com/w3c/csswg-drafts/issues/6426)
  script: |
    There are absolutely dragons lurking here,
    but we still have hope that it's possible.
    The current prototype side-steps these issues,
    in order to show the most common behavior --
    it's a proof of concept, not a finished product.

- css: |
    .container {
      contain: block-size;
    }
  script: |
    We're not sure if we can also support
    a `block-size` value.
    That would raise even more problems,
    but we'll work on it.
    Again, this works in the prototype
    by side-stepping the issues.

- css: |
    .sidebar, main, .grid-item {
      contain: inline-size layout style;
    }
  script: |
    Don't worry, you don't need to
    memorize and write out all these values.
    The browser will figure that out for you.

- css: |
    .sidebar, main, .grid-item {
      container-type: inline-size;
    }
  caption: |
    [CSSWG discussion of new syntax](https://github.com/w3c/csswg-drafts/issues/6174)
  script: |
    Instead of specifying all the containment required,
    we just say what type of container we want --
    or _what we want to query_.
    In this case we want to query the inline size.
    Browsers can take that,
    and apply the right containment
    in the background.

- pre: |
    _Warning_!
  title: |
    Not a **Stable Spec** (Yet)
  caption: |
    [Editor's Draft](https://drafts.csswg.org/css-contain-3/)
  script: |
    This changed recently,
    so some articles and demos
    might still use the old syntax.

    And the spec is still in active development,
    so it could change again.

- title: |
    **Querying** Containers
  script: |
    Once we have containers,
    we can begin to query them!

- css: |
    @container (min-width: 40em) {
      .card { /* ... */ }
      h2 { /* ... */ }
    }
  caption: |
    Each element queries the
    _nearest ancestor container_
  script: |
    A container-query
    looks exactly like a media-query,
    but with at-container instead of at-media.
    And each element will query
    the size of it's nearest ancestor container.

    Container's can't query themselves.
    That's ensures there are no loops.

- html: |
    <div class="container">
      <div class="container">
        <div class="container">
          We can nest containers!
        </div>
      </div>
    </div>
  script: |
    But we can nest containers
    as much as we need to --

- css: |
    .container { container-type: inline-size; }

    @container (width > 30em) {
      .container { padding: 2em; }
    }
  script: |
    And each container can respond
    to the one above it.

- css: |
    .sidebar {
      container-type: inline-size;
      container-name: sidebar;
    }

    @container sidebar (width > 30em) {
      .container { padding: 2em; }
    }
  caption: |
    [CSSWG issue for named containers](https://github.com/w3c/csswg-drafts/issues/6176)
  script: |
    If you don't want to rely on the nearest container,
    you can also give containers names,
    and only query containers with a specific name.

- css: |
    .sidebar { container-type: inline-size; }

    @container type(inline-size) (width > 30em) {
      .container { padding: 2em; }
    }
  caption: |
    [CSSWG issue for type queries](https://github.com/w3c/csswg-drafts/issues/6393)
  script: |
    Or only query a specific container type.

- pre:
    Chrome **Prototype**
  md: |
    1. Download/Update [Chrome Canary](https://www.google.com/chrome/canary/)
    2. Go to `chrome://flags` in the URL bar
    3. Search for "CSS Container Queries" & enable it
    4. You'll need to restart after turning it on
  caption: |
    [Codepen Demos](https://codepen.io/collection/XQrgJo)
  script: |
    Chrome already has a prototype,
    and you can start playing with it
    behind a feature flag.
    I've started collecting codepen demos
    to help you get started.

- pen: media-v-container
  script: |
    But why don't I just show you?

- pen: cq-quotes
  script: |
    My coworker David Herron,
    made this demo showing
    the same blockquote
    with three different designs
    based on the size of the container.

- pen: cq-flex
  script: |
    In some cases,
    like inside flexbox or grid,
    there is no outside container
    that will tell us the actual space available
    for each item.
    But we can get around that by adding a container
    around each component --
    in this case div.card is wrapping each article.
    The outer div establishes a container,
    and the inner article can query it.

- pen: cq-books
  script: |
    Max Böck has created this bookstore demo
    with self-contained web components.
    Each component host element is a container,
    and everything inside the component
    adjusts based on available size.

- pen: cq-icons
  script: |
    Una Kravets combines a number of different
    named containers to create this responsive card,
    with a responsive button,
    and a responsive icon.
    The named containers allow her to reference
    not just the most immediate context,
    but look higher up in the DOM
    to measure whatever container is most relevant.

- pen: cq-blinds
  script: |
    Of course, we can also get creative!
    Jhey Tompkins made these interactive blinds
    that get smaller as the container gets bigger.
    Because CSS doesn't have to be practical
    to be awesome.

- pen: cq-water
  script: |
    Stephanie Eckles joked that my containers don't hold water,
    so I made this demo to prove her wrong.

- pre: More to do...
  title: Container Query **Units**
  sub: |
    ~~`qw` | `qh` | `qi` | `qb` | `qmin` | `qmax`~~ \
    `cqw` | `cqh` | `cqi` | `cqb` | `cqmin` | `cqmax`
  caption: |
    ⚠️ Resolved 2021/10/06
    [Issue #5888](https://github.com/w3c/csswg-drafts/issues/5888#issuecomment-937291693)
  script: |
    We're also working on container-relative units,
    similar to vw, vh, vmin, vmax,
    but a percentage of the container size
    rather than the viewport.

# @@@ CUT IN AROUND 28:01

- img: css-next/breaking.jpg
  alt: Breaking Headlines
  script: |
    Sorry, sorry,
    future-past, past-future Miriam here again,
    with more breaking news!

- title: |
    🚨 Try **Query Units** Today 🚨
  script: |
    Query units are now also supported in the Chrome prototype!

- pre: Why `CQ`?
  title: Because _`CH`_ **Already Exists**
  caption: |
    ⚠️ Resolved 2021/10/06
    [Issue #5888](https://github.com/w3c/csswg-drafts/issues/5888#issuecomment-937291693)
  script: |
    You might also be asking why we went with `q` instead
    of, maybe, `c` for `container`.
    But we already have a "character unit" called `ch`,
    so we couldn't use that for "container height".
    Sometimes you're doing the best you can
    working around legacy code.
    If you have other ideas,
    this isn't set in stone yet,
    feel free to jump in and make suggestions
    on the github issue.

- pen: cq-units-basic
  script: |
    - respond to nearest relevant container (which might be root)
    - don't need to be inside `@container`

- pen: cq-units-nike
  script: |
    [demo]
    … Ok, back to past-past Miriam in three, two …

# @@@ OUT

- pre: More to do...
  title: Non-size **Queries**
  caption: |
    [CSSWG issue for other query ideas](https://github.com/w3c/csswg-drafts/issues/5989)
  script: |
    And we're working on queries
    that aren't about the container size.

- css: |
    @container style(--colors: invert) { … }
  caption: |
    ⚠️ Resolved 2021/10/06
    [Issue #6396](https://github.com/w3c/csswg-drafts/issues/6396#issuecomment-937299667)

  script: |
    We might be able to query the actual value
    of a property on the container,
    and change internal styles based on that property.

- css: |
    @container state(is-stuck) { … }
  caption: |
    [CSSWG issue for state queries](https://github.com/w3c/csswg-drafts/issues/6402)
  script: |
    Or check if our container is position-sticky,
    and currently in a "stuck" state.

    Both of these _should be possible_,
    but we haven't worked out all the details yet.

- title: Coming **Soon**
  sub: with a _polyfill_
  script: |
    If we can solve the inline containment issues,
    this could start rolling out in browsers
    by the end of the year,
    and Jonathan Neal is already working on a JavaScript polyfill
    to make it backwards compatible.

- css: |
    @container (width > 30em) { /* CQ support */ }

    @supports not (container-type: inline-size) {
      @media (width > 40em) { /* no CQ support */ }
    }
  script: |
    We can also use the at-supports rule,
    to create fallbacks natively in CSS.
    This is a great opportunity for progressive enhancement.

- title: CQ Proposal **Resources**
  md: |
    - [Specification](https://drafts.csswg.org/css-contain-3/)
    - [Original Explainer](https://github.com/oddbird/css-sandbox/blob/main/src/rwd/query/explainer.md)
    - [CSSWG project & issues](https://github.com/w3c/csswg-drafts/projects/18)
    - [More Articles & Demos »](/css-next/cq-resources/)
  script: |
    I'm recording this in advance,
    so some of the details might change.
    I'll share the link to my slides,
    so you can check for the latest resources.

# outro

- toc: true
  script: |
    All of these features are designed to work together
- pre: Building on
  title: Existing **CSS**
  script: |
    Building on the existing features of CSS --
- pre: Building on
  title: The **Cascade**
  script: |
    And the cascade
    that holds it all together --
- pre: Already make...
  title: Styles **Responsive**
  script: |
    But particularly the overlap
    between the two main goals of CSS:
    to make responsive --
- pre: Already make...
  title: Styles **Reusable**
  script: |
    and reusable styles.
    Building components that are inherently responsive --

- title: |
    **Intrinsic** Web Design
  sub: building _responsive components_ in CSS
  script: |
    and intrinsic.
    not forcing everything to be an exact percentage
    on a 12-column grid --
    but allowing for different components
    to manage their own intrinsic sizing and layouts and styles.
    Sometimes fluid, sometimes fixed,
    but always responsive to the overall needs of the page.
- quote: |
    Our medium is not done.
    Our medium is still
    **going through radical changes**.
  cite: Jen Simmons, *Designing with Grid*
  script: |
    We're not done,
    and you, as web designers and developers,
    are part of this process --
    helping the web achieve it's potential.
    I can't wait to see what you all build with this new tech,
    and I'm always eager to hear
    what else we can do
    to make the medium even more responsive.
