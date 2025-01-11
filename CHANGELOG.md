# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [Unreleased]

### Added

- support for `fzf-lua` as a folder picker
- Added option `g:himalaya_config_path` to customize the TOML configuration file.

### Changed

- Adjusted code for Himalaya CLI `v1.0.0-beta`.
- Disabled CLI logs for them not to mess up with errors. [#21]

### Fixed

- Fixed changing folder using telescope due to script function not accessible from lua env [#47].
- Fixed copy, move and delete not working when using multiple ids [#147].
- Fixed too long JSON string not being processed [#98].

## [0.7.1]

### Added

- Replaced system calls by async jobs [cli#230].
- Set email listing page size to windows height [cli#46].

### Fixed

- Fixed `cancel` reply after exiting the email edition buffer.

### Changed

- The Vim plugin has been removed from the
  [monorepo](https://github.com/soywod/himalaya) and extracted into
  its own [repo](https://git.sr.ht/~soywod/himalaya-vim). It was a
  good occasion to refactor the code and refresh the API. Here the
  list of the breaking changes:
  - config `g:himalaya_mailbox_picker` became `g:himalaya_folder_picker`
  - config `g:himalaya_telescope_preview_enabled` became `g:himalaya_folder_picker_telescope_preview`
  - keybind `himalaya-mbox-input` became `himalaya-folder-select`
  - keybind `himalaya-mbox-prev-page` became `himalaya-folder-select-previous-page`
  - keybind `himalaya-mbox-next-page` became `himalaya-folder-select-next-page`
  - keybind `himalaya-msg-read` became `himalaya-email-read`
  - keybind `himalaya-msg-write` became `himalaya-email-write`
  - keybind `himalaya-msg-reply` became `himalaya-email-reply`
  - keybind `himalaya-msg-reply-all` became `himalaya-email-reply-all`
  - keybind `himalaya-msg-forward` became `himalaya-email-forward`
  - keybind `himalaya-msg-copy` became `himalaya-email-copy`
  - keybind `himalaya-msg-move` became `himalaya-email-move`
  - keybind `himalaya-msg-delete` became `himalaya-email-delete`
  - keybind `himalaya-msg-attachments` became `himalaya-email-download-attachments`
  - keybind `himalaya-msg-add-attachment` became `himalaya-email-add-attachment`

[#21]: https://github.com/pimalaya/himalaya-vim/issues/21

[cli#46]: https://github.com/pimalaya/himalaya/issues/46
[cli#230]: https://github.com/pimalaya/himalaya/issues/230
