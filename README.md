> **This is a maintained fork** of [ryanjamurphy/review-obsidian](https://github.com/ryanjamurphy/review-obsidian), kept by Mike Schmitz ([Practical PKM](https://practicalpkm.com)).
>
> **Why it exists:** Obsidian 1.15 ships `Plugin`, `Modal` and `PluginSettingTab` as native JavaScript classes. Review 1.6.6 was compiled to ES5, so it fails to load with a `Class constructor … cannot be invoked without 'new'` error. Version **1.6.7** of this fork is the same plugin, rebuilt with esbuild targeting ES2018 so the classes stay native. Nothing else about how it works has changed, and it keeps the plugin id `review-obsidian`, so your existing settings carry over.
>
> **Install with [BRAT](https://github.com/TfTHacker/obsidian42-brat):** Add beta plugin → `bobbleheadjoe/review-obsidian`.
>
> **Build:** `npm install && npm run build` produces `main.js`. Release assets are `main.js` and `manifest.json`.

## Review

A plugin for [Obsidian](https://obsidian.md).

Review allows you to add the current note to a future note (or past note, if you want to, I guess) to make sure you review it again on that date.

This can be useful for project review (e.g., Getting Things Done), as a tickler file (e.g., Getting Things Done, again), spaced repetition, and to remind you of past failures or that embarrassing thing you did yesterday. 

Review integrates with (and therefore requires) the [Natural Language Dates plugin](https://github.com/argenos/nldates-obsidian). Please install it first.

### Setup
Make sure you _review_ (heh) the plugin's settings to assign:
- A heading for the review section (defaults to `## Review`).
- A prefix for each line added when you invoke Review (e.g., 
- A prefix for each block added when you invoke Review on a block (e.g., using `!` will make each block an embed automatically)
- A default for each review (e.g., if you use `tomorrow`, you can just hit <kbd>enter</kbd> when you invoke Review to put the thing you're reviewing on tomorrow's daily note

### How to use

- Use the command palette to access the Review command (or assign a hotkey to it).
- Once you invoke the command palette, the plugin asks for a date. Use natural language ("tomorrow," "in three weeks," "two days ago," "November 5")
- The plugin relies on the Natural Language Dates plugin to translate your given date into a daily note name as per your settings in that plugin
- The plugin then creates a new daily note for the given day with a new review section (or appends this section to the given daily note, if one already existed).

### Demo
![A gif showing the use of this plugin as described above.](https://i.imgur.com/9AqrSKy.gif)

### Manually installing the plugin

- Copy `main.js` and `manifest.json` to your vault's plugins folder, under `[YourVaultFolder]/.obsidian/plugins/review-obsidian/`.
