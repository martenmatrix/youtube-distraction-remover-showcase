<img alt="STiNE Logo" height="100" src="./assets/icon.svg"/>

# Unleash Focus: YouTube Distraction Blocker 

> This project is currently closed-source.

## Table of Contents

- [Making a production build](#making-a-production-build)
    - [Chrome](#chrome)
    - [Firefox and Chromium-based](#firefox-and-chromium-based)
    - [Safari](#safari)
    - [Uploading to a WebStore](#uploading-to-a-webstore)

## Making a production build

### Chrome
Creating a production build for Chrome is simple, run:

`plasmo build`

and a production build should be created in the `build` folder.

### Firefox and Chromium-based
When making a production build for Firefox or a Chromium-based browser, the `--target`-flag needs to be supplied as `<browser-name>-<manifest-version>`.

e.g. for Firefox and Manifest V3 run:

`plasmo build --target=firefox-mv3`

and the production build should show up in the `build` folder.

See the [Plasmo docs](https://docs.plasmo.com/framework/workflows/faq#what-are-the-officially-supported-browser-targets) for a list of supported targets.

### Safari
Making a production build for Safari requires a macOS device using `Big Sur 11.3` or higher and `XCode` must be installed.

1. Run `plasmo build target=safari-mv3`. A new folder should've been created in the `build`-folder.
2. Then run `xcrun /Applications/Xcode.app/Contents/Developer/usr/bin/safari-web-extension-converter ./build/safari-mv3-prod` to convert the extension to an XCode project.
3. Build the application in XCode.
4. Activate the extension in Safari, as described [here](https://developer.apple.com/documentation/safariservices/safari_app_extensions/building_a_safari_app_extension#2957925).

### Uploading to a WebStore
Same procedure as steps above, however instead of ~~`plasmo build`~~ `plasmo package` should be executed.

