# Build 1.0.455:

## UX/UI Improvements:
- Implemented easy impersonation of backend users through the backend - feature controlled by the new `backend.impersonate_users` permission
- Open `rowlink` rows in a new tab when the Command or Ctrl key is held down (previously only did it for the Ctrl key)
- Added disabled style for `switch` field types

## API Changes:
- Changed the FileUpload FormWidget to process uploads with a `onUpload` AJAX handler instead of the `checkUploadPostback` method
- Changed the default value of `cache.disableRequestCache` to be `null` which now disables the in memory request cache during CLI requests and enables it during HTTP requests. Other values are explicit `true` or `false`.
- Brought the `AuthManager` and `User` classes more in line with Laravel's Auth library; full support is still a far ways off though.
- Removed the mediafinder buttons from the `RichEditor` and `MarkdownEditor` FormWidgets when the user does not have permission to use the media library.

## Bug Fixes:
- Fixed issue with retaining transparency when making thumbnails for some image files
- Fixed issue that could cause potential data loss with complicated implementations of the Repeater formwidget.
- Fixed issue where the DatePicker was ignoring the value of `ignoreTimezone` when in mode `date`

## Translation Improvements:
- Improved Dutch translation