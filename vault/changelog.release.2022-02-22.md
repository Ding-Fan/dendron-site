---
id: ixhyxsx79zqjy25s7q9liud
title: '0.83'
desc: ''
updated: 1645493812159
created: 1645488383028
---

Dendron 0.83 has sprouted  🌱

**Breaking changes:** This release of Dendron updates the publishing configuration within `dendron.yml`. This update is not backwards compatible, meaning that older versions of `dendron-cli` will not be able to publish a migrated workspace.

- More information: [[0.83 Changelog|dendron://dendron.dendron-site/changelog.release.2022-02-22#changelog]].

Pod V2 preview continues to grow: you can now export the contents of a hierarchy, filtered by a target vault. This means the multi-vault workspaces can be more targeted in their exports without including notes from undesired vaults.

- More information: [[Pod v2 exportScope|dendron://dendron.dendron-site/dendron.topic.pod-v2.config#exportscope]]

File Links now support block anchors (` ^block-anchor`)! This means that you can create comments in your code, and link directly to the comment blocks. Optionally, you can link line numbers.

> Block anchors are more reliable because they will always refer to the marked line, but Dendron has to modify the file to insert a block anchor which looks like `^this`. You are free to move the anchor anywhere in the file or to put comment markers like `//` or `#` or anything else before them.

- More information: [[File Links|dendron://dendron.dendron-site/dendron.topic.links#file-links]]

## Highlights
- enhance(pods): add vault filter for pods-v2 hierarchy export
- enhance(notes): change dendron id format to be alphanumeric lowercase
- enhance(workspace): Block Anchor support for non-note files
- deprecate(publishing): Legacy publishing has now been removed from `dendron-cli`. Dendron users that haven't yet migrated from `dendron buildSite` commands must migrate to using the `dendron publish` commands.

## Everything Else
- enhance(workspace): calculate backlinks and anchors in engine for improved editor responsiveness
- fix(workspace): Journal Note Consistency with Title and Traits
- fix(workspace): Dendron will try to parse non-dendron files in `onFirstOpen`
- fix(workspace): error message to be readable in error toast
- fix(publish): horizontal line's height in publishing
- fix(publish): properly set siteIndex when it's not explicitly set by config

## Community

### General

- We added [bookmark bot](https://top.gg/bot/453939662168260612) to the Dendron Discord, meaning that users can now react to a message with `:bookmark:` 🔖 and Bookmarker will save it for them in a direct message.

### Starboard and TIL Highlights
<!-- TODO: update links. Delete section is no new items-->
> These are highlights from the [[Dendron Discord|dendron://dendron.dendron-site/community.discord.channels]] `#starboard` and `#today-i-learned` channels.

- ⭐ `seadude` shared how to create clickable areas of images that he found useful in [reveal.js presentations](https://marketplace.visualstudio.com/items?itemName=evilz.vscode-reveal): _"Today I learned you can create a clickable area (or more than one) of an image and have it link anywhere."_
    - Useful for RevealJS presentations, etc.
    - Done by using the `usemap` parameter of `<img>` and `<map>` HTML tags
    - Example:

    ```html
    <img src="https://c.pxhere.com/photos/70/93/egg_hammer_threaten_violence_fear_intimidate_hit_beat-767438.jpg!d" usemap="#map" height="550"/>

    <map name="map">
        <area shape="circle" coords="330,350,50" alt="egg" href=".\assets\pdfs\timeline2.pdf" target="_blank">
        <area shape="circle" coords="430,250,50" alt="mallet" href=".\assets\pdfs\timeline3.pdf" target="_blank">
    </map>
    ```

- 💡 `seadude` shared information about [VS Code Snippets](https://code.visualstudio.com/docs/editor/userdefinedsnippets):
    - Related: [Dendron Snippet Maker](https://marketplace.visualstudio.com/items?itemName=dendron.dendron-snippet-maker)
    - Example 1: You can set a default value for a variable by using a colon (`:`). The `DUE:` property in the below snippet defaults to the current current month, date, hour but can be modified.

    ```json
    "TODO": {
    "prefix": "stodo",
    "body": [
        "- [ ] ${1:Enter Task}",
        "- **CAPTURED:**        ${CURRENT_YEAR}-${CURRENT_MONTH}-${CURRENT_DATE}T${CURRENT_HOUR}:${CURRENT_MINUTE}:${CURRENT_SECOND}-08:00",
        "- **DUE:**             ${CURRENT_YEAR}-${2:${CURRENT_MONTH}}-${3:${CURRENT_DATE}}T${4:${CURRENT_HOUR}}:${5:${CURRENT_MINUTE}}:00-08:00",
        "- **PRIORITY:**        ${6|HIGH,MEDIUM,LOW|}",
        "- **STATUS:**          ${7|TODO,WAITING,IN PROGRESS,DONE|}",
        "- **NOTES:**           ",
        "    - $0",
        ],
        "description": "Capture new TODO"
    }
    ```

    - Example 2: You can set dropdown values for a variable using a pipe (`|`).

    ```json
    "Context Switch": {
      "prefix": "scontext",
      "body": [
        "- **TYPE:**          ${1|COMMS,SUPPORT,RESEARCH,MEETING,DEVELOPMENT,TESTING,VALIDATION,CI/CD,PROJECT MGMT,CONSULTING,DOCUMENTATION,ADMINISTRATION,TRAINING,BREAK|}",
        "- **PROJECT:**       ${2|PROJ1,PROJ2|}",
        "- **TOOLS:**         ${3|N/A,PYTHON,AZURE,POWER APPS,POWER AUTOMATE,POWER BI,SHAREPOINT,DENDRON|}",
        "- **START:**         ${CURRENT_YEAR}-${CURRENT_MONTH}-${CURRENT_DATE}T${CURRENT_HOUR}:{$CURRENT_MINUTE}:${CURRENT_SECOND}-08:00",
        "- **END:**           ",
        "- **DURATION:**      ",
        "- **NOTES:**         ",
        "    - $0",
        "---"
        ],
        "description": "Capture new context switch"
    }
    ```

- 💡 `scriptautomate` shared a link to the [Sourcegraph VS Code extension](https://marketplace.visualstudio.com/items?itemName=sourcegraph.sourcegraph): _"TIL about the Sourcegraph extension for VS Code. I feel like it has interesting potential. Like, imagine searching public Dendron vaults directly from your VS Code?"_

### Dendron Reading Series

This week's entry in the [[Dendron Reading Series|dendron://dendron.dendron-site/community.events.reading-series]].

![[dendron://dendron.dendron-site/community.events.reading-series.2022.02.22]]

### Event Reminders

- **Greenhouse Talks:** Visit the [[Greenhouse Talks|dendron://dendron.dendron-site/community.events.greenhouse]] for notes from previous sessions.
    - Subject: _Getting Things Done (GTD) and Other Task-Management Workflows (with Dendron!)_
    - Description: _Interested speakers from the community will take 5 - 10 minutes each to present their workflows for managing actionable information, followed by an open discussion. The event will be recorded and later published online._
    - Next: [Fri, Feb 25, 4:00 PM PST / 00:00 UTC](https://link.dendron.so/luma)
    - [Greenhouse Talk Recordings - YouTube Playlist](https://link.dendron.so/greenhouse)
- **Office Hours:** Visit the [[Office Hours page|dendron://dendron.dendron-site/community.events.office-hours]] for notes from previous sessions.
    - Next: [Wed, Mar 02, 9:00 AM - 9:30 AM PST](https://link.dendron.so/luma)
    - [Office Hour Recordings - YouTube Playlist](https://link.dendron.so/6yPa)
- **New User Tuesdays:** Visit the [[New User Tuesdays page|dendron://dendron.dendron-site/community.events.new-user-tuesdays]] for notes from previous sessions.
    - Next: [Tue, Mar 08, 8:30 AM - 9:00 AM PST](https://link.dendron.so/luma)

### Thank You's

A big **thanks** to the following gardeners that brought up issues, contributions, and fixes to this release :man_farmer: :woman_farmer: 
Visit [[Discord Roles|dendron://dendron.dendron-site/community.discord.roles]] for more information.

## Changelog
![[dendron://dendron.dendron-site/changelog#0830,1:#0820]]
