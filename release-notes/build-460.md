# Build 460 (WIP):

## UX/UI Improvements:
- Moved CodeEditor's full screen buttons to the bottom of the widget.
- Fixed keyboard support for checkboxes
- Added keyboard support to lists
- Improved the UX of checkbox lists "Select All", "Select None" bulk actions
- Changed the cursor to be a `grab` cursor when hovering over table headers to indicate that they are a scrollable container

## API Changes:
- `media.file.upload` event now passes the `$path` argument by reference.
- Added new global JS function `ocJSON()` to framework.js (also available in separate `framework.parser.js`) for parsing loose JSON safely
- Added ability to specify a LESS file to be used as a default backend brand CSS override with the config item `brand.customLessPath`
- Updated references to deprecated `event.which` and other methods of determining the selected keys to the new `event.key`
- Added new method `removePermission($owner, $code)` to the BackendAuth manager class to enable plugins to dynamically remove permissions from the available list registered with the BackendAuth manager class.
- Added support for SparkPost mail driver

## Bug Fixes:
- Reverted improvements to table column width handling on Chrome (specifically for long unbroken text values in columns) introduced in Build 444 as it was causing other issues on mobile.
- Reduced inconsistencies with results generated by `\October\Rain\Database\Attach\Resizer` class, specifically for .gif images by processing .gif images with `imagescale()` instead of `imagecopyresampled()`
- Fixed an issue where attempting to modify the available Settings Items through the `SettingsManager` could fail if a user wasn't provided to `filterItemPermissions()` at that point in the request

## Security Improvements
- Prevent tabnabbing that could theoretically occur from a backend user clicking the "Preview" button in the backend navigation and having the tab taken over by the frontend site

## Translation Improvements:
- Improved Polish translation

## Performance Improvements:
- Very minor performance improvement calling `JSON.parse()` instead of `$.parseJSON()` in core JS
- Added support for lazy loading the backend navigation menu icons / images

## Community Improvements:
- Switched to using GitHub actions instead of Travis for CI on the main octobercms/october repository
- Added initial frontend testing suite under `tests/js`

## Dependencies
- Updated Dropzone from v4.0.1 to v5.5.1
- Updated Modernizr from v3.6.0 to v3.7.1
- Updated jQuery.Mousewheel from v3.1.9 to v3.2.0