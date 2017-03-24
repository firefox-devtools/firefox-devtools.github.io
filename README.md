# Firefox Developer Tools

These are the tools provided by Firefox for developers to inspect Web code.

This repository aims to provide a general overview of how the tools are built, who's working on them, and how to get involved. If you are looking for user support, there's [a whole area at MDN](https://developer.mozilla.org/en-US/docs/Tools) dedicated to it.

We abide by our [code of conduct](https://dxr.mozilla.org/mozilla-central/source/devtools/CODE_OF_CONDUCT.md) and expect all contributors to do the same.

## Working on the code and contributing

### `mozilla-central` vs `devtools-html`

The bulk of the code is hosted in the Firefox repository (we call it `mozilla-central`, often abbreviated as `m-c`), in the [devtools](https://dxr.mozilla.org/mozilla-central/source/devtools) folder. Development of newer pieces of the tools is happening in GitHub, on the [devtools-html](https://github.com/devtools-html/) organisation.

Code in `m-c` takes longer to set up from scratch, as it involves installing Mercurial and binary tools such as compiler to build a version of Firefox in your machine, but it is required if you want to work on most of the tools (as the majority of them are in this repository). Here are [the instructions](https://wiki.mozilla.org/DevTools/Hacking) plus this [very good article](https://eduardoboucas.com/blog/2017/02/09/contributing-firefox-devtools.html).

The repositories in `devtools-html` are more straightforward if you're used to *the GitHub workflow*: you clone them, and then run `npm install && npm run` or similar. Roughly, you can work with each repository individually and we periodically we generate JavaScript bundles that are then copied into `m-c`.

### Bugs and issue trackers

Since we have code in two different places, issues and bugs are to be found in two different places:

* For code in `m-c`: [http://firefox-dev.tools/](http://firefox-dev.tools/) which also lets you filter by good bugs for beginners.
* For code in `devtools-html`: [this page](https://github.com/search?l=&q=org%3Adevtools-html+state%3Aopen&type=Issues) lists all the issues across the organisation.
<!--TODO: ^^ add label:"help wanted" or similar to the query to get easy issues-->

## Documentation

Broadly speaking, the tools are divided in two parts: the server and the client. A **server** is anything that can be debugged: for example, your browser, but it could also be Firefox for Android, running on another device. The **client** is the front-end side of the tools, and it is what developers interact with when using the tools.

Since these two parts are decoupled, we can connect to any server using the same client. This enables us to debug multiple types of servers, using the same protocol to communicate.

You will often hear about `actors`. Each feature that can be debugged (for example, network) is exposed via an `actor`, which provides data about that specific feature. It's up to each server to implement some or all actors; the client needs to find out and decide what it can render on the front-side when it connects to the server. So when we want to debug a new feature, we might need to do work in two parts of the code: the server (perhaps implementing a new actor, or extending existing ones) and the client (to display the debugging data returned by the actor).

Often, an actor will correspond to a panel. But a panel might want to get data from multiple actors.

You might also hear about `the toolbox`. The toolbox is what everyone else calls `developer tools` i.e. the front-end that you see when you open the tools in your browser.

This is just a brief overview. For more detailed documentation:

* There is a [docs](https://dxr.mozilla.org/mozilla-central/source/devtools/docs) folder on `m-c` with technical information about the tools and about each individual panel. We are publishing [an HTML version of these documents](http://firefox-dev.tools/docs/) as well.
* [Internal technical documentation](https://wiki.mozilla.org/DevTools#Internal_Technical_Documentation) (NOTE: we're migrating from here to the folder mentioned above).
* Additionally, check out each GitHub repository for documentation specific to that repository or module.
* Not strictly a roadmap, but these are [some of our 2017 goals](https://groups.google.com/forum/#!topic/mozilla.dev.developer-tools/e-WTOb1U8Sc).

## People and modules

The tools are broadly divided into panels. Each panel has one or more owners, who mostly work(s) on that panel and are the best people to ask if you have specific questions about the code.

<!-- TODO: from https://wiki.mozilla.org/DevTools/GetInvolved#Communication but update it -->
<!-- TODO: * show organisations in github (doesn't work if people don't make their membership public) -->

## News and demos

We publish news and updates to two blogs:

* [Nightly](https://blog.nightly.mozilla.org/tag/devtools/) for features newly added to Firefox Nightly. This is the place to request feedback from early adopters!
* [Hacks](https://hacks.mozilla.org/category/developer-tools/) when features reach more stable versions of Firefox.

You're more than encouraged to help us talk about the tools by writing an article, making a demo, or both! We also wrote [some guidelines for making demos](https://github.com/devtools-html/devtools-demos).

## Getting in touch

There are various ways to get in touch with us:

* To request features or report errors:
  * You can [file bugs in Mozilla's bugzilla](https://bugzilla.mozilla.org/enter_bug.cgi?product=Firefox&component=Developer%20Tools)
  * or under each repository in [devtools-html](https://github.com/devtools-html) for code in GitHub
* We have [a section](https://discourse.mozilla-community.org/c/devtools) on the Mozilla forum. If you want to ask questions, this is a great way to get in touch with us and also ensuring that your question is visible to other people (and hopefully help them as well).
* We also have a [mailing list](https://groups.google.com/forum/#!forum/mozilla.dev.developer-tools). For people who prefer mail to forums.
* If you'd prefer to chat, there's a `#devtools` channel in `irc.mozilla.org`, but bear in mind that perhaps the person that could help you best is not online when you ask the question. For that reason, it might be better to use the forum or mailing list instead.
* Contributors to `debugger.html` also hold [periodic hangouts and have a slack channel](https://github.com/devtools-html/debugger.html#discussion).

## Processes

Most changes will be done via either the "pick a bug and send a patch" or "send a PR" processes.

For substantial changes, we ask that a "request for comment" (RFC) document is provided first, so we can examine what the implications of a change will be. Here is [how to follow the RFC process](https://github.com/devtools-html/rfcs/).

## People

<style>
  .people-grid {
    display: grid;
    grid-template-columns: repeat(8, 1fr);
    grid-gap: 10px;
    grid-auto-rows: minmax(100px, auto);
  }
</style>

<div class="people-grid">
{% for person in site.github.organization_members %}
  <a style="display:block;text-align:center;" src="{{ person.html_url }}">
  <img style="width:48px;max-height:48px;" src="{{ person.avatar_url }}"/>
  <div>{{ person.login }}</div>
  </a>
{% endfor %}
</div>
