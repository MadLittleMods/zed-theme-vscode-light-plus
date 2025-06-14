### Releasing a new version

 1. Check you are on the `main` branch (`git status`, `git checkout main`), then come up
    with a version number `vX.Y.Z`
 1. Update `version` in `extension.toml` to match the new version number
 1. Tag a new release: `git tag -a vX.Y.Z -m "vX.Y.Z"`
 1. Push the tag to the repo: `git push origin vX.Y.Z`
 1. Make a new release on GitHub with the tag `vX.Y.Z` linking to the changelog
 1. Publish the theme in the [Zed extension repository](https://zed.dev/extensions) with
    the following instructions,
    https://zed.dev/docs/extensions/developing-extensions#updating-an-extension
    1. Go to your fork/checkout of the https://github.com/zed-industries/extensions repo
    1. Update the `version` field for the extension in `extensions.toml`
    1. Update the extension's submodule to the commit of the new version.
        1. `cd extensions/vscode-light-plus`
        1. `git pull`
        1. `git checkout vX.Y.Z`
        1. `cd ../../`
   1. Make a new branch/PR with the changes: "Update `vscode-light-plus` theme extension to `vX.Y.Z`"
