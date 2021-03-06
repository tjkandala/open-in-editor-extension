# open-in-editor (Sourcegraph extension)

Adds a button at the top of files in both Sourcegraph app and code hosts like GitHub (when the Sourcegraph browser extension is installed) that will open the current file in your editor of choice. 

![Screenshot](https://user-images.githubusercontent.com/206864/89693503-774d5300-d8c3-11ea-9582-23e768ff5ef7.png)

## Installing

For Sourcegraph.com, it can be enabled here: https://sourcegraph.com/extensions/sourcegraph/open-in-editor

Otherwise, follow instructions here to publish it privately: https://docs.sourcegraph.com/extensions/authoring/publishing

## Settings

- Add `openineditor.basePath` to your user settings to open files in the editor. Copy one of the following lines depending on the editor you would like to use. Supported editors:
  - `vscode` (Visual Studio Code): `"openineditor.editor": "vscode"`
  - `idea` (JetBrains IntelliJ IDEA): `"openineditor.editor": "idea"`
  - `sublime` (Sublime Text, requires a URL handler installed such as [this one for macOS](https://github.com/inopinatus/sublime_url))
  - `custom` (requires also setting `openineditor.customUrlPattern`): `"openineditor.editor": "custom"`
- `openineditor.basePath`: The base path where your git repos live. This extension requires all git repos to be cloned under this path with their original names.
- `openineditor.customUrlPattern`: If you set `openineditor.editor` to `custom`, this must be set. Use placeholders `%file`, `%line`, and `%col` to mark where the file path, line number, and column number must be replaced. Example URL for IntelliJ IDEA: `idea://open?file=%file&line=%line&column=%col`
