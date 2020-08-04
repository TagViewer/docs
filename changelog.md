---
description: Release versioning conforms to the SemVer specification.
---

# Release Changelog

### v1.1.1

#### Adds

* TagSpace Error Detection: If there are errors in the manifest file for the TagSpace, TagViewer will refuse to open it to prevent further corruption.

#### Fixes/Improves

* Removing Items from TagSpace: Removing an item previously caused metadata modification to not work correctly, due to an error in the internal manifest.

### v1.1.0

#### Adds

* Collapsing filter groups: if you have many tags/properties in your TagSpace, it can be hard to find the one you need, even with the built-in searching capability. Now you can collapse the sections \(tag, color, and property\) to only show the one\(s\) you need.
* Pressing enter to add a filter: previously you would need to click the plus button next to the filter, but intuitively users expect the filter to be added when they press enter.
* Advanced color and tag filter compatibility checks: another way this release reduces clutter in the Filters tabs is by hiding options that would be redundant, conflicting, or moot.
* Pressing escape to stop searching filter options: again, users expect to be able to exit an action with the escape key, so it makes sense to extend this to searching the filter options. \(Note that the search button only appears if you have more than three offers, so you may not have it.\)
* Color preview underlines in the filter quake dialog: this is a feature that not many users know about; for the users that prefer the keyboard, it's a quicker way to compose filters. Anyway, within this dialog, any six-digit hex color you enter will be underlined to give you a preview of that color.
* Recently Opened menu in the application's menu bar: you can now see your recently opened TagSpaces in the menu bar, and use intuitive accelerators \(Ctrl + Alt + &lt;index in the menu&gt;\) to open them.

#### Fixes / Improves

* Set the media number to 1 when a TagSpace is opened: previously the media number would sometimes not be 1 when you open a TagSpace.
* Properly verify resolution filters: the second parameter was previously not verified which could have caused confusing behavior.
* Clear the inputs for a filter offer when it's added: this simplifies the process of adding multiple filters, and doesn't retain information that is no longer useful.
* The filter menu sometimes overflowed past its area causing some filters to be inaccessible.
* Better performance in large TagSpaces

#### Removes

* Disable spellcheck in the filter quake dialog: while a spellchecker that worked would be helpful, the built-in one was not.
* Limit the open history to ten entries.

### v1.0.1

Fix a critical bug where users could access functions that relied on information that was not available \(for example, configuring a TagSpace when one is not open\).

### v1.0.0

The first release, so no changelog yet.



