# VSCode Light+ theme for [Zed](https://zed.dev/)

Port of the Light+ (Default Light+) theme from Visual Studio Code to Zed.

Zed | VSCode
--- | ---
![Zed example with Light+](./screenshots/zed/zed-vscode-light-plus-theme1.png) | ![VSCode example with Light+](./screenshots/vscode/vscode-light-plus-theme1.png)
![Zed example with Light+](./screenshots/zed/zed-vscode-light-plus-theme2.png) | ![VSCode example with Light+](./screenshots/vscode/vscode-light-plus-theme2.png)


## Installation

TODO: Publish extension -> https://zed.dev/docs/extensions/developing-extensions

Workaround: Copy the JSON theme file to `~/.config/zed/themes/` or see the [*developer
notes* on how to *locally link a
theme/extension*](./dev-notes.md#locally-link-theme-extension) for more information.


## Current Limitations

### Dim and washed out colors

The whole genesis of this theme port was because every light Zed theme was all
dim/dull/muted and washed out (everything is grey-ish) with not enough contrast. This
theme is an improvement but doesn't totally solve the problem because it seems to be a
fundamental issue with how Zed handles rendering and colors (as experienced on Manjaro,
arch-based Linux). See the following issues for more context:

 - https://github.com/zed-industries/zed/issues/9057
 - https://github.com/zed-industries/zed/issues/19100
 - https://github.com/zed-industries/zed/issues/17890
 - https://github.com/zed-industries/zed/issues/8293#issuecomment-2299761507
 - https://github.com/zed-industries/zed/issues/15521
 - Even the theme previews on [zed-themes.com](https://zed-themes.com/) are much more
   vibrant because the browser is rendering things as expected.


### Syntax Highlighting

Zed's bundled `highlights.scm` files at
`https://github.com/zed-industries/zed/tree/main/crates/languages/src` often do not
define all the queries for syntax nodes needed to style the theme. This means that some
syntax nodes have different colors when compared to the original theme.


## Development

As you can see if you dive into the theme file, there are plenty of things that are not
filled in as I couldn't see where they were being used in Zed. Feel free to create PR's
to fill in any gaps (include screenshots and context).

Also see the [*developer notes*](./dev-notes.md) for more information.
