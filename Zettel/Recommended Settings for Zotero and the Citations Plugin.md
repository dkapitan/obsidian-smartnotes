project::[[Getting Started]]
- [ ] #cont/in/read 

> [!NOTE] Anything not mentioned here is optional

==Here ist the installation guide as a downloadable PDF: [[Zotero Installation Guide.pdf]]==

# Zotero
1. Install [Zotero](http://zotero.org)
2. Install [Attanger](https://github.com/MuiseDestiny/zotero-attanger) (see guide below)
3. Install [Better BibTeX](https://retorque.re/zotero-better-bibtex/) (see guide below)
#### Guide
1. Download the latest released xpi-file ([Attanger](https://github.com/MuiseDestiny/zotero-attanger/releases) / [BetterBibteX](https://github.com/retorquere/zotero-better-bibtex/releases/)).
2. In Zotero open Tools/Plugins. 
3. Click on settings (the cog wheel) and install the plugins from file. 
4. Activate the plugins (if they are not automatically activated).

# Settings / General
1. Uncheck "Automatically attach associated PDFs and other files when savings items"

# Settings / Sync
1. Link your Zotero Account (create one if you haven't one yet)
2. Check "Sync automatically"
- [Zotero Help on Syncing](https://www.zotero.org/support/sync)

# Settings / Export
- Item Format: Better BibLaTeX
- Note Format: Markdown + Rich Text
- Check both boxes for "Include Zotero Links"
# Settings / Attanger
- Source Path / Root Directory - choose your default download folder
- Read title from PDF file: Choose "Always"
- Attach file "Link" to the Zotero Item/Collection
- Destination Path / Root Directory: choose the PDFs folder in your vault
# Better BibTeX
- Citation keys: zotero.clean
- Check "Force citation key to plain text"
- Check "Enable citation key search"
- The section "Automatic export" will appear once you exported the library as described below.
1. Go to File / Export Library...
2. Format: Better BibLaTeX
3. Check "Export Notes"
4. Check "keepUpdated"
5. Check "worker"
6. Leave everything else unchecked.
7. Click "OK" and save the file "My Library.bib" in the root folder of your Obsidian vault. 

# Citation Plugin
- Citation database format: "BibLaTex"
- Citation database path: Choose the "My Library.bib" file from the root folder of your Obsidian vault (the one you saved from Zotero with Better BibTeX)
- Literature note folder: Choose the literature notes folder from your vault (in the starter-kit that is "Literature Notes")
- Literature note title template: 
```
@{{citekey}}
```
- Literature note content template: 
```
#### {{title}}
##### {{authorString}} ({{year}}) 
{{publisherPlace}} {{publisher}} {{containerTitle}} {{page}} {{DOI}} {{isbn}}, [Zotero]({{zoteroSelectURI}}) [PDF]({{citekey}}.pdf)
##### tags: 
>[!ABSTRACT]+
>{{abstract}}
---
#### Notes:
{{note}}
```
- Markdown primary citation template:
```
[[@{{citekey}}|{{title}} ({{authorString}} {{year}})]]
```
- Markdown secondary citation template: 
```
[[@{{citekey}}|({{authorString}} {{year}})]]
```

## Check Hotkeys for Citations

You need at least a hotkey for 
- "Insert literature note link" (in the starter kit: Ctrl+Shift+E / Cmd+Shift+E)
- "Insert Markdown citation" (in the starter kit: Ctrl+Shift+Q / Cmd+Shift+Q)
