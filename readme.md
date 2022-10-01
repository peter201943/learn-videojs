
# Learn VideoJS

## Folder Breakdown
- **`01-native-html/`**
  - Trying browsers' built-in video players
- **`02-videojs-basic/`**
  - Minimal VideoJS example
- **`03-videojs-code/`**
  - Accessing VideoJS players from JavaScript `<script>` blocks
- **`04-videojs-pro/`**
  - A more professional setup, using NPM to manage plugins

## VideoJS Notes
- About: Created 2022-09-30 to learn about video players in web browsers, specifically [VideoJS](https://videojs.com/)
- Misc: Native video player must be muted to automatically play
- Setup: the `<video>` element `` date-setup `` attribute uses quoted-JSON, not JavaScript-object-literals
  - Example: `` data-setup='{"autoplay": "muted","controls": true, "loop": true} ``
    - Note: Must use quotation marks around keys
- CRUCIAL: `<video>`  must have `` data-setup="{}" `` attribute
- CRUCIAL: `<video>`  must have `` class="video-js" `` attribute
- CRUCIAL: `<body>`   must have `` <script src="https://vjs.zencdn.net/7.20.3/video.min.js"></script> `` element *after* all other elements
- CRUCIAL: `<head>`   must have `` <link href="https://vjs.zencdn.net/7.20.3/video-js.css" rel="stylesheet" /> `` element
- Feature: "Playlists" are not a native feature, and must be provided via plugins
- Feature: VideoJS plugins are not noteworthy enough to have common CDN's available, hence should be provided locally (via NPM)
- Requirement: Setup NPM for VanillaJS Website
- Misc: Consider placing all webpages in a `/pages/` or `/public/` folder, so as to keep the root directory clean
- Misc: Consider placing all resources into appropriate categorical folders
  - Example: Images and videos and audio in `/media/`
  - Example: Stylesheets in `/styles/`
  - Example: Website-specific JavaScript in `/src/`
- Feature: Custom styling requires the base theme be included first, and then the custom theme

## VideoJS References
- [x] [YouTube: HTML5 Video Programming](https://www.youtube.com/playlist?list=PLSkTiyK6-uFd85cPVw6RcXn9MFNwms6L3)
- [x] [YouTube: Custom Video Player in React JS](https://www.youtube.com/watch?v=oITDcIjJBlY)
  - Suggests a much better way of managing a website
  - Using NPM, JSX
- [x] [Mozilla: `<source>`: The Media or Image Source element](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/source)
- [x] [Mozilla: `<video>`: The Video Embed element](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/video)
- [x] [GeeksForGeeks: HTML `<video>` crossorigin Attribute](https://www.geeksforgeeks.org/html-video-crossorigin-attribute/)
- [x] [Mozilla: `<script>`: The Script element](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/script)
- [x] [StackOverflow: Multiple initialization of Video.js player on ajax loaded part of page](https://stackoverflow.com/questions/14070127/multiple-initialization-of-video-js-player-on-ajax-loaded-part-of-page)
- [x] [VideoJS: Embed a Video.js Player](https://videojs.com/guides/embeds/)
- [x] [Video.js: Options Reference](https://videojs.com/guides/options/)
- [x] [Video.js: Setup](https://videojs.com/guides/setup/)
- [x] [StackOverflow: using jquery to create videojs](https://stackoverflow.com/questions/26356193/using-jquery-to-create-videojs)
- [x] [VideoJS: Layout](https://videojs.com/guides/layout/)
- [x] [StackOverflow: video.js responsive not working](https://stackoverflow.com/questions/24290484/video-js-responsive-not-working)
- [x] [GitHub: Interoperatibility with bootstrap #7116](https://github.com/videojs/video.js/issues/7116)

## NPM Notes
- Installation: Install [NodeJS](https://nodejs.org/en/) first (NPM is included and uses some NodeJS functions)
- Setup: Add Plugins to VS Code
  - Debugger for Chrome/Edge/Firefox
  - IntelliCode
  - (TODO: List used extensions for web development)
- Note: `npm` can be used in any folder-level (even within a project which already has npm in use - but this is an advanced technique - not recommended for beginning)
- Setup: `` npm init `` in appropriate folder
- Setup: Creates `node_packages` and places each plugin as a sub-directory
- Setup: Run `` npm install video.js `` to add VideoJS
- Setup: Run `` npm install videojs-playlist `` to add a VideoJS Plugin
- Setup: Run `` npm install @videojs/themes ``
- CRUCIAL: Node-style-javascript is *incompatible* with browser-style-javascript, a ***BUNDLER*** must be used to convert Node-Packages into useable Browser-Libraries (See [Bundler Notes](#bundler-notes))
- Misc: [Bootstrap](https://www.npmjs.com/package/bootstrap) and [LoDash](https://lodash.com/) are commonly included packages that just makes things better
  - (`` npm install bootstrap@v5.2.1 ``, `` npm install lodash ``)
  - Warning: LoDash requires *bundling* before using (See [Bundler Notes](#bundler-notes))

## NPM References
- [x] [YouTube: NPM For Front-End Development - Node.js Modules In The Browser](https://www.youtube.com/watch?v=dHHEz-qDvko)
- [x] [YouTube: Module Bundlers Explained... Webpack, Rollup, Parcel, and Snowpack](https://www.youtube.com/watch?v=5IG4UmULyoA)
- [x] [YouTube: Easy Frontend JS Workflow With No Framework](https://www.youtube.com/watch?v=8rD9amRSOQY)
- [x] [LogRocket: The top latest build tools for JavaScript](https://blog.logrocket.com/the-top-latest-build-tools-for-javascript/)
- [x] [GeeksForGeeks: What is global installation of dependencies in Node.js ?](https://www.geeksforgeeks.org/what-is-global-installation-of-dependencies-in-node-js/)

## Bundler Notes
- Setup: Run `` npm install --save-dev webpack webpack-cli `` (Note how webpack is not needed in the final website itself, so we do not save it for "production")
  - Alternative: Run `` npm install --global webpack webpack-cli `` (This installs it for a given computer, not just a given project)
- CRUCIAL: Must edit `packages.json` with relevant building parameters, see [YouTube: Module Bundlers Explained... Webpack, Rollup, Parcel, and Snowpack](https://www.youtube.com/watch?v=5IG4UmULyoA) for details
- Execution: Run `` npm run build ``
- CRUCIAL: Most builders output results to `/dist/`, must link to `/dist/` from html (webpage code)
  - Example: Bundling Website Code
    - Old: `` <script type="module" href="../src/index.js"></script> `` 
    - New: `` <script type="module" href="../dist/main.js"></script> ``
- Ecosystem: There are a lot of bundlers, with their own annoying differences
  - WebPack: Requires lots of configuration, takes awhile to build
  - Parcel: 
  - Snowpack: Faster build times

## Credits
- [Today is Friday, in California](https://www.youtube.com/watch?v=9WaYCdQ8FOQ)
  - [Today is Friday in California [Full Scene]](https://www.youtube.com/watch?v=m1CW3MrwTeY)
- [Wrap the Towel around the Rat carefully](https://www.youtube.com/watch?v=BTH40ElpYow)
  - [Manual Restraint and Common Compound Administration Routes in… JoVE Video](https://www.youtube.com/watch?v=s9skgg7dHIA)
- Lithuanian Troops train with a Javelin
  - [File:UK and Lithuanian troops conduct anti-tank live-fire training (2022-03-08).webm](https://en.wikipedia.org/wiki/File:UK_and_Lithuanian_troops_conduct_anti-tank_live-fire_training_(2022-03-08).webm)
    - [Wikipedia: FGM-148 Javelin: Training](https://en.wikipedia.org/wiki/FGM-148_Javelin#Training)

## Interesting VideoJS Plugins
- [ ] [`videojs-playlist` - A plugin to enable playlists in video.js](https://www.npmjs.com/package/videojs-playlist)
- [ ] [`videojs-playlist-ui` - A playlist video picker for video.js and videojs-playlist](https://www.npmjs.com/package/videojs-playlist-ui)
- [ ] [`videojs-errors` - A plugin that displays user-friendly messages when Video.js encounters an error.](https://www.npmjs.com/package/videojs-errors)
- [ ] [`videojs-hotkeys` - A plugin for Video.js that enables keyboard hotkeys when the player has focus.](https://www.npmjs.com/package/videojs-hotkeys)
- [ ] [`videojs-share` - Share plugin for video.js. Allows user to copy video url / embed code and share video to social networks.](https://www.npmjs.com/package/videojs-share)
- [ ] [`@videojs/themes` - Monorepo for Video.js themes 💅.](https://www.npmjs.com/package/@videojs/themes)
