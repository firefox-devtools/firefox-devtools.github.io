# Firefox Developer Tools

Welcome! [Firefox](https://www.mozilla.org/firefox/) DevTools is an open source toolbox for inspecting, debugging, and modifying web code. We work closely with the community in the development and design of our projects. Help us maintain an inclusive environment by following our [code of conduct](CODE_OF_CONDUCT.md).

## Documentation

* [Contributor documentation](http://docs.firefox-dev.tools/).
* [MDN DevTools user guides](https://developer.mozilla.org/en-US/docs/Tools).

## News and demos

We publish news and updates to two blogs:

* [Nightly](https://blog.nightly.mozilla.org/tag/devtools/) for features newly added to Firefox Nightly. This is where we request feedback from early adopters.
* [Hacks](https://hacks.mozilla.org/category/developer-tools/) for when features reach more stable versions of Firefox.

You're more than encouraged to talk, write articles, or [make demos](https://github.com/firefox-devtools/demos) about the tools. Let us know 🙂

## Getting in touch

* Bug reports or feature requests:
  * [File bugs in Mozilla's Bugzilla](https://bugzilla.mozilla.org/enter_bug.cgi?product=DevTools) (please respect the [etiquette](https://bugzilla.mozilla.org/page.cgi?id=etiquette.html))
  * or under each repository in [firefox-devtools](https://github.com/firefox-devtools) for code in GitHub.
  * Report vulnerabilities to `security@mozilla.org`. [More info](https://www.mozilla.org/en-US/security/#For_Developers).
* [List of open bugs](http://bugs.firefox-dev.tools/). Might be interesting if you want to contribute.
* [DevTools forum](https://discourse.mozilla-community.org/c/devtools).
* [Mailing list](https://groups.google.com/forum/#!forum/mozilla.dev.developer-tools).
* [Weekly status updates](https://docs.google.com/document/d/1lxy0IzUM14dYACk_q862vVYwpU1AA4NQVrUNAm6uc-8/)
* Chat:
  * Join the [Firefox DevTools Slack](https://devtools-html-slack.herokuapp.com/),
  * or IRC: `#devtools` channel on `irc.mozilla.org`.
* Twitter: [@FirefoxDevTools](https://twitter.com/FirefoxDevTools).

## Processes

Most changes will be done via either the "pick a bug and send a patch" or "send a PR" processes.

For substantial changes, we ask that a "request for comment" (RFC) document is provided first, so we can examine what the implications of a change will be. Here is [how to follow the RFC process](https://github.com/firefox-devtools/rfcs/).

### People and modules

The tools are broadly divided into panels. Each panel has one or more owners, who mostly work(s) on that panel and are the best people to ask if you have specific questions about the code.

* about:debugging: jdescottes, ochameau, ladybenko, daisuke
* Accessibility Inspector: yzen
* Animation Inspector: gl, pbro, daisuke
* Console: bgrins, nchevobbe
* Debugger: jlast, dwalsh, loganfsmyth
* DOM: honza
* Font Editor: rcaliman, gl, pbro
* Framework: Browser integration, toolbox and test infrastructure: bgrins, ochameau, honza
* Inspector: gl, pbro, jdescottes, rcaliman, mtigley, bwerth, mikeratcliffe
* JSON Viewer: honza
* Memory: gregtatum
* Network Monitor: honza
* Performance: gregtatum, julienw
* Remote protocol and server infrastructure: ochameau, yulia
* Responsive Design Mode: gl, bwerth, mtigley
* Scratchpad: jdescottes
* Style Editor: gl
* Storage Inspector: mikeratcliffe
* CSS & Themes: ladybenko
* UX: victoria
* WebIDE: ochameau, jdescottes
