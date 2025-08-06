# DocTools

## Description
This repo contains the public releases of xmldocer, an internal preprocessor for [docfx](https://github.com/dotnet/docfx) used by tms. It is used to compile the docs at https://github.com/tmssoftware/smartsetup

## Installation
1. Download the release for the os.
2. Install [docfx](https://github.com/dotnet/docfx): `dotnet tool install -g docfx`

> [!Warning]
> If you have an old docfx version installed by chocolatey or similar, uninstall it first. Those aren't getting more updates.

3. Install [Node.js](https://nodejs.org/en/download)  This is needed for syntax highlighting.
4. Optionally, grab DocSpy from https://github.com/agallero/docspy/releases/latest. DocSpy is not needed, but it makes it simple to review and build the docs.

## Usage
To compile the [SmartSetup](https://github.com/tmssoftware/smartsetup) docs, you need to type:
```shell
xmldocer VCL <path-to-smartsetupdoc.ini> --verbose
```
If using DocSpy, setup that command in the docspy config, so you can rebuild the docs from there.

## Writing docs
Being a preprocessor to [docfx](https://dotnet.github.io/docfx/) you can use all the markdown mentioned here: https://dotnet.github.io/docfx/docs/markdown.html
Besides, that we provide some special constructs:
  * To insert an image, write `{{#image}}imagename.png{{//image}}` and save a `imagename.png` file at `\images`
  * If you want to provide a different image for dark mode users, save the dark image as `imagename_dark.png`. No changes in the markdown files are necessary, the dark image will be used automatically when the user is in dark mode.
