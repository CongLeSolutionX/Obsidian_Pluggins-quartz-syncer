---
title: Roadmap and Changelog
description: Changelog and feature roadmap for Quartz Syncer.
created: 2025-05-16T12:59:31Z+0200
modified: 2025-07-03T14:31:57Z+0200
publish: true
---

## Upcoming

## Planned

- Excalidraw support.
- Canvas support.
- Built-in Quartz Themes support.
- TTRPG-related plugin support.

## Someday

- Manage Quartz configuration.
- Manage Quartz layout.
- Manage Quartz components.

## Released

### 1.8.7

- Added support for Dataview [inline fields](https://blacksmithgu.github.io/obsidian-dataview/annotation/add-metadata/#inline-fields)
	- This works for inline fields defined inside Obsidian comment syntax as well (`%%`)
- Updated documentation.

### 1.8.6

- Added options to configure the keys used for the created, updated, and published timestamps.
	- Supports a comma-separated list of options to check. Quartz Syncer will use the first matching value per note.
	- Defaults to the options recognized by Quartz.
- Updated documentation.

### 1.8.5

- Added setting option to override the need for a publish flag in the note properties.
	- This option is disabled by default.
- Added documentation for previously undocumented functions.
- Updated documentation.

### Version 1.8.4

- Addressed feedback for initial Obsidian release.
- Upgraded frontmatter engine to use Obsidian built-ins.
- Updated documentation.

### Version 1.8.3

- Rewrote plugin compiler logic.
- Improved multi-device cache synchronization logic.
- Cleaned up connection validation.
- Updated documentation.

### Version 1.8.2

- Added support for the [Fantasy Statblocks](https://github.com/javalent/fantasy-statblocks) plugin.
- Removed polling in favor of `MutationObserver`.
- Updated documentation.

### Version 1.8.1

- Fixed caching to be vault-specific.
- Updated documentation.

### Version 1.8.0

- Significant performance improvements.
- Added caching of compiled files to reduce processing time and GitHub API calls.
	- The processed files are stored in Obsidian's [localStorage](https://developer.mozilla.org/en-US/docs/Web/API/Window/localStorage).
- Added settings related to performance.
	- Enable cache: whether to save compiled files to cache. Defaults to true.
	- Sync cache: whether to save compiled files to the plugin's `data.json` as well. This is recommend for users that synchronize their vaults between multiple devices to ensure consistency. Defaults to true.
	- Persist cache: whether to keep the cache in the localStorage when the plugin unloads. This is only recommended for users that start Obsidian with plugins disabled, such as when using the [Lazy Plugins](https://github.com/alangrainger/obsidian-lazy-plugins) plugin. Defaults to false.
	- Clear cache: Clears the cache when pressed.
- Improved preview performance.
- Visual indicators for loading and publishing.
	- Added loading bars to indicate progress.
	- Added partial indicators for folders that have both checked and unchecked files.
	- Automatically flag files for deletion that are in the remote repository, but not in the local vault.
		- These are generally deleted, renamed, or moved.
- Rewrote link resolution logic.
- New commands:
	- Clear cache for current file.
	- Clear cache for all files.
		- Calling this command will prompt for confirmation.
- Folder suggester no longer fetches all files instead of just folders.
- Added release GitHub Action.
- Updated documentation.

### Version 1.7.1

- Datacore integration improvements.
- Fixed Datacore callouts.
- Fixed aliases and permalinks not passing through when set inside note properties.
- Updated documentation.

### Version 1.7.0

- Experimental [[Settings/Integrations/Datacore|Datacore]] support.
- Updated documentation.

### Version 1.6.9

- Fixed MathJax embedding inside callouts and multi-layer embeddings.
- Updated documentation.

### Version 1.6.8

- Fixed DataviewJS queries not always returning correct data.
- Fixed MathJax collapsing to inline queries when embedded.
- Updated documentation.

### Version 1.6.7

- Fixed issues related to alias generation on non-embedded links to blocks or headings.
- Removed redundant `decodeURI` call on blobs.
- Removed redundant function calls in Dataview processor.
- Removed unused utility functions.
- Replaced many CSS rules with Obsidian CSS properties to better integrate with Obsidian themes.
- Fixed grammatical error in embed settings description.
- Expanded settings tabs to show names on desktop.
	- Tablet and mobile still only show name on the active tab.
- Updated dependencies.

### Version 1.6.6

- Re-implemented the settings modal to use built-in Obsidian functionality.
- Settings that are overridden by other settings are now automatically hidden.
- Settings modal will now remember the last settings tab opened, instead of always opening the GitHub tab.
- Added missing heading to the Frontmatter settings tab.
- Removed redundant rendering calls.
- Restructured import statements.

### Version 1.6.5

- Fixed icons in publication center not showing correctly.
- Fixed broken link in project README file.
- Removed unnecessary warning.
- Updated manifest.

### Version 1.6.4

- Fixed embedded math blocks incorrectly parsing to inlined math blocks.
- Moved all inlined styling to CSS classes.
- Changed buttons in publication center to sticky.
	- This makes the buttons always visible at the bottom of the modal, even when displaying larger tree.
- Removed unused code.
- Updated manifest.
- Updated documentation.

### Version 1.6.3

- Fixed mobile folder selector styling.

### Version 1.6.2

- Use Obsidian built-in for rendering Dataviewjs to markdown.

### Version 1.6.1

- Implemented Obsidian built-in folder suggester.
- Removed now-unused popperjs dependency.
- Moved cog loading animation styling to CSS.

### Version 1.6.0

- Fixed embedding issues when embedding blocks.
- Embeddings are now handled by Quartz Syncer instead of Quartz.
	- This behavior can be configured in the settings `Quartz > Apply embeds`.
- Added settings menu for Quartz Themes.
	- This currently does nothing, but will be used for managing and applying Obsidian themes to Quartz.
- Fixed some minor typos.
- Updated documentation.

### Version 1.5.3

- Added note counts to the publication center.
- Added tabbed settings menu.
- Updated documentation.

### Version 1.5.2

- Restored use of `innerHTML` in the Dataview compiler.
	- This only affects `dataviewjs` queries. These are an optional, opt-in component of the Dataview plugin. See [Dataview JavaScript API documentation](https://blacksmithgu.github.io/obsidian-dataview/api/intro/) for details.

### Version 1.5.1

- Addressed Obsidian's automated feedback.

### Version 1.5.0

- Added to Obsidian Community Plugin list.
- Added separate settings for configuring note properties/frontmatter.
- Added option to only pass valid Quartz properties.
	- This can be overridden by setting the new `Include all properties` option.
- Updated publication center headings to better reflect functionality.
- Cleaned up all unused and redundant functions.
- Finished up all of the essential documentation.

### Version 1.4.1

- Fixed links to embedded notes resolving to the wrong URL when deploying from a subfolder.

### Version 1.4.0

- Added support for setting a vault folder as Quartz content folder.
	- This setting is recommended for users with mixed content vaults or users who want to dedicate a specific folder to their Quartz site content.
	- Specific folder can be configured in the plugin settings.
- Added configuration option for specifying publish frontmatter key.
	- The default key is `publish`, matching Obsidian Publish's default key.
	- The frontmatter key is used to expose notes to Quartz Syncer. Any note without the specified key or eith they key set to `false`/unchecked checkbox will not show up in Quartz Syncer.
	- The key should be a boolean/Checkbox (source mode/live-preview mode respectively.)
- Added Obsidian commands for modifying a note's publication status:
	- `Quartz Syncer: Add publish flag`: adds the specified publish flag to the current note frontmatter if not already present and sets it to `true`. This exposes the note to Quartz Syncer.
	- `Quartz Syncer: Remove publish flag`: adds the specified publish flag to the current note frontmatter if not already present and sets it to `false`. This hides the note from Quartz Syncer.
	- `Quartz Syncer: Toggle publication status`: toggles the note's visibility to Quartz Syncer.
- Added support for all embed filetypes that Quartz also supports. This includes the following:
	- Note: `md`
	- Image: `png`, `jpg`, `jpeg`, `gif`, `webp`, `svg`
	- Audio (new): `mp3`, `wav`, `ogg`
	- Video (new): `mp4`, `mkv`, `mov`, `avi`
	- Document (new): `pdf`
- Added a new icon.
- Added this documention website.
- Fixed deleting multiple files in single commit.

### Version 1.3.1

- Fixed Dataview query results not displaying correctly inside nested callouts.

### Version 1.3.0

- Exposed the following options for user configuration in plugin settings view:
	- Pass frontmatter.
	- Image file compression.
	- Use permalink for Quartz URL.
	- Pass note's created date to Quartz.
	- Pass note's last modification date to Quartz.
- Fixed incorrect links to embedded notes.
- Fixed path resolution resolving to wrong path in some cases.

### Version 1.2.0

- Initial beta release as Quartz Syncer.

### Version 1.1.0

- Support for configuring Quartz path.

### Version 1.0.0

- Forked from [Ole Eskild Steensen](https://github.com/oleeskild)'s [Digital Garden plugin](https://github.com/oleeskild/obsidian-digital-garden).
