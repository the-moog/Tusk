This fork is (for the moment) just to look at the possibility of maintaining this code as Tusk (unlike other browser plugins) does not need a desktop proxy service
this means that it is better for systems where the user has limited capabilities to install system level apps.
First task: fix the very broken webdav.


# Tusk is no longer actively maintained.

* **Is it still safe?**  Yes. As far as the community is aware, Tusk's security model is still the same.  You may continue using Tusk, and I will keep the third party integrations (Dropbox, Google Drive, etc.) active.  Please contact me through [my website](https://subdavis.com) to report security concerns.
* **Why is it unsuppored?** Because I no longer prefer the keepass ecosystem.  I believe version control and data sync should be a core feature of any password manager.
* **Any good alternatives?** I've switched entirely to [Password Store](https://www.passwordstore.org/) + [BrowserPass](https://github.com/browserpass/browserpass-extension) and I'm happier now.  If you want something more user friendly, I highly recommend [Bitwarden](https://bitwarden.com/).  To remain with Keepass, try [Kee](https://kee.pm) or [KeepassXC-Browser](https://chrome.google.com/webstore/detail/keepassxc-browser/oboonakemofpalcgghocfoadofidjkkk).
* **Could someone else take over?** If you have a lot of time and are interested in taking over leadership of Tusk, please contact me through [my website](https://subdavis.com) and tell me about yourself and what you'd like to do with Tuisk.  It has over 25 thousand active users, and I'm sure they would all love to see the project live on.

----

# Tusk
> A modern, clean keepass browser extension built with Vue.js and kdbxweb.  Rebooted from perfectapi/CKP

![Tusk](https://user-images.githubusercontent.com/25948390/45255427-a466f300-b386-11e8-9321-931934faafb4.png "Tusk Logo")

## Installation

**Firefox:** https://addons.mozilla.org/en-GB/firefox/addon/keepass-tusk/

**Chrome:** https://chrome.google.com/webstore/detail/fmhmiaejopepamlcjkncpgpdjichnecm

## User Guide

This section provides how-to instructions for various features of Tusk.

* [WebDAV Support](https://github.com/subdavis/Tusk/wiki/WebDAV-Support) - Support for WebDAV file servers.
* [Custom Fields](https://github.com/subdavis/Tusk/wiki/Custom-Fields) - list of custom fields that Tusk supports.
* [Warnings and Errors](https://github.com/subdavis/Tusk/wiki/Warnings-and-Errors) - An explanation of the messages you may encounter.

#### How it works: Implementation Details

This section provides in-depth information about how tusk works under the hood.  We aim to provide better transparency and give users peace-of-mind.  Tusk may not be perfect, but it's better than proprietary black-box applications that hide design flaws from the community.

* [Credential Cache Memory](https://github.com/subdavis/Tusk/wiki/Credential-Cache-Memory) - How Tusk can optionally keep your master password cached.
* [Sensitive Data](https://github.com/subdavis/Tusk/wiki/Sensitive-Data) - How Tusk handles sensitive data like KeePass databases and keyfiles.

## Build Setup

Tusk requires:
* `node`
* `npm`
* `yarn`

```bash
# install dependencies
yarn install

# build static DLL resources (optional)
yarn build-dll

# build for production with minification
yarn build

# run the packer script targeted for 'chrome' and 'firefox' after build.
# this step generates the zip archives submitted to Chrome/Firefox addon marketplaces.
yarn bundle

# static reload with file watch for tests
yarn dev-tests
```

For detailed explanation on how things work, consult the [docs for vue-loader](http://vuejs.github.io/vue-loader).

## Running tests

To run tests, first build them with `yarn build-tests` or `yarn watch-tests` then open `tests/test.html` in a browser.

## Browser Permissions

> Tusk requires cross-origin permissions in order to inject credentials and query the storage backends on the user's behalf.

In chrome, these permissions requests are __always__ prompted to the user upon first use.

Because of Firefox's implementation of `browser.permissions`, it was necessary to request all permissions at install time to avoid code rot.  A deeper explanation of the firefox permissions can be found [on stackoverflow](https://stackoverflow.com/questions/47723297/firefox-extension-api-permissions-request-may-only-be-called-from-a-user-input)

## FAQ

> Why is it called Tusk?!

I originally wanted to call it *Elephant*, as in *An elephant never forgets.*  I tried this name on a couple of friends and they were unimpressed. I wanted to find a name that was more concise but keep the elephant imagery.  Ergo, tusk.

> What happened to CKPX?

This is it! CKPX has been rebranded as Tusk to mark its Firefox release.  The C in CKPX stood for 'Chrome'.

> Can I donate money?

I don't want your money.  Take whatever you would have given me and find a local charity -- a food bank, a women's shelter or an animal shelter, for example.  Enjoy your free software.

> So how can I support Tusk?

If you ❤️ Tusk, please consider leaving a positive review on [the Firefox Add-on store](https://addons.mozilla.org/en-GB/firefox/addon/keepass-tusk/) or [the Chrome webstore](https://chrome.google.com/webstore/detail/fmhmiaejopepamlcjkncpgpdjichnecm) - I'll be eternally grateful.

> Who made that awesome logo?

A super cool artist and graphic designer named [Gabriel Garcia](https://github.com/ggabogarcia)!  Thanks for our logo!
