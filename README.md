# bug-fixes-and-performance-improvements
Verified localization of "Bug fixes and performance improvements" changelog.
Ready to use with [fastlane](https://fastlane.tools).

## Examples
Running this lane will upload the release notes to App Store Connect for all
languages. If you already store your app's metadata in the `fastlane/metadata`
folder, create a new folder (e.g. `fastlane/metadata-bug-fixes`) for this
release-notes-only metadata and specify it in `metadata_path` parameter.
otherwise this will delete your app's current metadata from App Store Connect.

```ruby
desc "Upload release notes"
lane :upload_release_notes do
  deliver(
    app_identifier: "com.example.MyApp",
    app_version: get_version_number(target: "MyApp"),
    force: true,
    skip_binary_upload: true,
    skip_screenshots: true,
    metadata_path: "fastlane/metadata",
  )
end
```
