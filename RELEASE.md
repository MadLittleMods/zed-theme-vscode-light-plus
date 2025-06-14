### Releasing a new version

 1. Check you are on the `main` branch (`git status`, `git checkout main`), then come up
    with a version number `vX.Y.Z`
 1. Update `version` in `extension.toml` to match the new version number
 1. `git tag -a vX.Y.Z -m "vX.Y.Z"`
 1. `git push origin vX.Y.Z`
 1. Make a new release on GitHub with the tag `vX.Y.Z` linking to the changelog
 1. Publish the theme in the [Zed extension repository](https://zed.dev/extensions) with
    the following instructions,
    https://zed.dev/docs/extensions/developing-extensions#updating-an-extension
