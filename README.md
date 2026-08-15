# CodeTorch addons
combine new and existing features and themes for the [CodeTorch](https://codetorch.net) website and project editor into one easy-to-access and configurable browser extension. The mission is to provide a centralized, up-to-date platform for community development of new features and themes for Scratch.

### About addons

An addon mainly consists of one or more userscripts (written in JavaScript) or userstyles (written in CSS) that run on the Scratch website or project editor.

Each addon declares its own addon manifest. (`addon.json` file). This file specifies under which circumstances each one of its userscripts and userstyles should be injected into the page. It also contains user-facing information, such as the description of the feature, and information about the addon's settings.

Userscripts work similarly to [extension content scripts](https://developer.chrome.com/docs/extensions/develop/concepts/content-scripts) running in the "main world" (the unprivileged context where `chrome.*` extension APIs are not available). Userscripts have access to `addon.*` APIs. They can use these built-in utilities for various purposes: waiting until a certain element exists on the page, listening to settings change events, getting a reference to the Scratch VM object, etc.

Addons are designed to be compatible with each other. They are also developed with performance, internationalization, accessibility, and privacy in mind.

### About the extension

The Scratch Addons browser extension provides a settings page where users can enable, disable and configure addons. The extension interprets addon manifests, stores the user's settings, and provides APIs to userscripts. A new version of the extension is released to the stores regularly with new addons and features.

### Addons beyond the Scratch Addons browser extension

Other open-source projects (such as Scratch forks) can also make use of the addons. Hence, the CodeTorch built-in addons to the editor in Edit > Addons.

### File structure

#### Addons
- `addons-l10n`: Translation for addon strings (one file per addon).
- `addon-api`: Implementation of the `addon.*` JavaScript APIs.
- `addons`: Each addon has its own directory, which must include an addon manifest file named `addon.json`.
- `libraries`: Third-party libraries and other utilities, some of which are used by addons.

#### Others
- `.github`: GitHub templates, workflows, and contributing files.
- `_locales`: Translation strings for the browser extension (excluding addons).
- `background`: Background scripts for the extension.
- `content-scripts`: Content scripts, which among other things, execute userscripts and inject userstyles to the page.
- `images`: Logos, screenshots and icons (excluding addon-specific images).
- `popups`: Addon pages that are only accessible through the extension popup (for example, Scratch Messaging).
- `webpages`: The settings page, extension popup, and other pages.

## Installation

No building is required. The best way to download the source is with Git:

``` bash
git clone https://github.com/ilim-cell/CodeTorchAddons.git
```
or by downloading the latest release as a ZIP, then unpacking.

### Loading the extension (Chrome)

To load the extension into most Chromium-based browsers, go to `chrome://extensions`, turn on developer mode, click "Load unpacked", and select the `ScratchAddons` folder.

### Loading the extension (Firefox)

Go to `about:debugging`, select "This Firefox", click "Load Temporary Add-on...", and select the `manifest.json` file in the `ScratchAddons` folder.

> [!WARNING]
> Firefox extensions loaded this way are removed when the browser is closed.

## Contributing

### Suggestions and bug reports

If you found a bug or have a suggestion [create an issue](https://github.com/ilim-cell/CodeTorchAddons/issues/new/choose) after checking for duplicates.
If you found a security vulnerability, please follow the instructions in our [Security Policy](https://github.com/ilim-cell/CodeTorchAddons/tree/master/.github/SECURITY.md) instead.

> [!CAUTION]
> Please do not create public bug reports for security vulnerabilities.

### Code

Before contributing code, please read our [contributing guidelines](https://github.com/ilim-cell/CodeTorchAddons/blob/master/.github/CONTRIBUTING.md).

> [!TIP]
> We recommend using [Visual Studio Code](https://code.visualstudio.com) as the code editor.

## License

CodeTorch Addons is licensed under the terms of the [GNU General Public License v3.0](https://github.com/ilim-cell/CodeTorchAddons/blob/master/LICENSE). This follows the same license as the upstream fork Scratch Addons.

Other third-party libraries used are listed on [/libraries/README.md](https://github.com/ilim-cell/CodeTorchAddons/tree/master/libraries#readme).
