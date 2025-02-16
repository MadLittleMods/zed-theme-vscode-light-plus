# Developer notes

A collection of references and notes while developing this project.


## Extract the colors from a VSCode theme

In VSCode, use `Developer: Generate Color Theme From Current Settings` from the command
pallete  to generate a JSON file with the colors of the current theme. The commented out
lines in the JSON file are the default values being used but not specifically set in the
theme.

(source: https://stackoverflow.com/questions/47970372/how-to-get-the-colors-of-the-current-theme-in-vs-code)

The source for Light+ is available in the VSCode repository:

 - [`microsoft/vscode` -> `extensions/theme-defaults/themes/light_vs.json`](https://github.com/microsoft/vscode/blob/a948ee5bec485e4dde01abc6d6e289e3f64dbb14/extensions/theme-defaults/themes/light_vs.json)
 - [`microsoft/vscode` -> `extensions/theme-defaults/themes/light_plus.json`](https://github.com/microsoft/vscode/blob/a948ee5bec485e4dde01abc6d6e289e3f64dbb14/extensions/theme-defaults/themes/light_plus.json)


## VSCode theme importer

There is a [theme importer in the Zed
codebase](https://github.com/zed-industries/zed/tree/main/crates/theme_importer) that is
compatible with VSCode themes but it didn't seem to work that well for me with the
Light+ theme. I ended up just creating a new theme from scratch and only using the
`syntax` section.

References:

 - https://github.com/zed-industries/zed/issues/7111



## Zed theme development

> Themes are stored in the `themes/` subdirectory under the Zed config: `~/.config/zed/themes/`.
>
> *-- https://zed.dev/blog/user-themes-now-in-preview*

There is a JSON schema defining the structure of a Zed theme but I wasn't finding great
tools to consume it. Your editor will give suggestions and descriptions for the fields
when editing the JSON file but it's not the greatest for discovery. The best I found was
this [JSON schema
viewer](https://json-schema.app/view/%23%2Fdefinitions%2FThemeStyleContent?url=https%3A%2F%2Fzed.dev%2Fschema%2Fthemes%2Fv0.2.0.json)
from Atlassian.


### Locally link theme/extension

To test a theme file, you can locally link the theme file to `~/.config/zed/themes/`.

```sh
ln -s ~/Documents/github/zed-theme-vscode-light-plus/themes/vscode-light-plus.json ~/.config/zed/themes/vscode-light-plus.json
```

To test the extension as a whole, you can locally link the repo to [installed extension
location](https://zed.dev/docs/extensions/installing-extensions#installation-location)
and run `Zed: reload extensions` command in Zed editor to get it to show up.

```sh
ln -s ~/Documents/github/zed-theme-vscode-light-plus ~/.local/share/zed/extensions/installed/vscode-light-plus
```

References:

 - https://zed.dev/docs/extensions/themes
