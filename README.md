# [peerweb.site](https://peerweb.site/) ![Twitter Follow](https://img.shields.io/twitter/follow/Weedshaker?style=social)
[![PH](https://api.producthunt.com/widgets/embed-image/v1/featured.svg?post_id=203739&theme=light)](https://www.producthunt.com/posts/peerweb-site?utm_source=badge-featured&utm_medium=badge&utm_souce=badge-peerweb-site)
## Real Time Peer to Peer Web Site Host from your Browser

### Description
Send Texts, Pictures and Videos embedded in HTML with CSS and JavaScript through WebRTC in acquaintance of WebTorrents for files, live edited P2P as well as static Torrents. No conversation data passes a server nor is saved anywhere but **sent directly from browser to browser**. Your website disappears from the aether as soon as you close or reload your tab, except of your WebTorrent snapshots. *(Saving in-site WebTorrents is not yet supported.)*

<img src="https://weedshaker.github.io/PeerWebSite/img/screenshot1.png" align="left" width="45%">
<img src="https://weedshaker.github.io/PeerWebSite/img/screenshot2.png" align="right" width="45%">
<br clear="right"/>

### Functionalities
1. **Use WebTorrent for files**: This will enable WebTorrent for added files. It allows video steaming and will perform better in case your site is file heavy. It is mandatory for multiple files to load efficiently. Although, it may not work well with other browsers but Chrome.

2. **Activate Live Session & Copy Link**: *(Sometimes unstable due to causes of ICE failed or other issues with WebRTC, require a reload or use Webtorrent/Snapshot.)* This opens a session/peer to peer room where your audience can join and see your changes in real time. Your site will not be reachable, once you close your browser tab. *You could have a two way communication, if you join the room/site not through the link with hash but manually put the channel name into the input field.*

3. **Take Snapshot & Copy Link**: This bundles all your text and files into a WebTorrent. Which is like a snapshot of your site to share. Your link with the content stays accessible as long as at least one person has your sites WebTorrent active. More info about WebTorrents can be found [here](https://webtorrent.io/). In case you need to memorize a generated snapshot link, simply use [tinyurl](https://tinyurl.com/), there you can convert your long https://peerweb.site/#magnet:?xt=urn:btih:a... url into a tiny url, which is easy to remember.

4. **Download Files**: To download a picture -> double click. To download a video -> long press. (Default behaviors vary between different browsers and devices. *These possibly conflict.*)

5. **WebTorrent Desktop**: You can host your site reliably from your Mac, Windows or Ubuntu and keep it online. Simply create your site at peerweb.site, once done, click "Take Snapshot & Copy Link":
    1. Open the browsers console and type: `getAllTorrents()`. Save the text file and copy/paste each of the magnetURIs to your [WebTorrent Desktop](https://webtorrent.io/desktop/) client. Wait until WebTorrent Desktop has downloaded all magnetURI/files.
    2. open the browsers console and type: `getAllTorrentFiles()`. Save the files and load each of the files separately into your [WebTorrent Desktop](https://webtorrent.io/desktop/) client. To re-up your site, just reload the same files into [WebTorrent Desktop](https://webtorrent.io/desktop/).
After this is done, you can close your tab at peerweb and your site stays online as long as WebTorrent Desktop hosts it or other people start seeding your peerweb.site.


### Use Cases
1. **Quickly and directly transfer data from one device to an other** without the need of sending an e-mail or texting yourself and feeding content to the big data servers from facebook, google, aws or companions. I often have pictures and texts on the smartphone or second computer and need to share them fast and uncomplicated, without login and logging, to my other device(s).

2. **Share Content Temporarily** by opening a peerweb.site session.

3. **Create your Torrent aka. Snapshot** with your content in no-time and share it to the vast world.

4. **Full JavaScript applications eg. games, single page apps, etc.** to host them from your browser tab.
    *Use the browser dev-tools to manipulate `class="note-editable"` aka rich text editor area. Create or copy/paste your html/js/css and open a snapshot link at a fresh window in incognito mode to view the result*
    1. A ServiceWorker will support loading WebTorrents, if fetch, src, href, etc. references the same file name an already present WebTorrent file has (short: first upload files in peerweb.site and then reference them by only file name within scripts, html, etc.), without using the magnetURI/blob as reference.
    2. Alternatively, you can use [WebTorrent Desktop](https://webtorrent.io/desktop/) or ([Instant.io](https://instant.io/)) to host all your assets, make sure to create a magnetURI for each file and don't bundle them. Then copy/paste or create your indexes html at peerweb.site in the editors container `class="note-editable"`. Make sure to use magnetURIs as referenced values for fetch, src, href, etc. in your scripts/html. You must reference them as src example: `src="https://magnet:?xt=urn:...`, prepend `https://` before `magnet`.

### Further Development
Give me a star on Github, which will motivate me to tide up the code and write Docs for it, that other Developers could have an easy entry to participate, which will bring this App to what you wish for as a peer to peer, privacy and opensource enthusiast.

### Pitfalls
This beta application has been only tested in Chrome. Don't expect miracles, it's a pure hobby, side project and due to bleeding edge sometimes buggy.

### Road map
1. Tide up Code, get rid of jspm, move UI to WebComponents based Event Driven Architecture

2. Add [IPFS](https://ipfs.io/) support and increase stability by more carefully handle webtorrent and webrtc events, likely with a [es6 Proxy Wrapper](https://weedshaker.github.io/ProxifyJS/)

3. WebGL Drawing, drag and drop Grids Layouts, other TextEditors without Bootstrap and Jquery, better Video Player, rotate Images, WebTorrent Desktop preview, WebRTC one direction video broadcast

4. Load/Save including WebTorrents

5. Search Engine (by km/miles-radius, topic, etc., to opt in your peerwebsite.)

6. Raspberry-pi auto seed with auto unseed (after one download, etc.). Would allow a pick-up e-mail p2p alternative and a channel slack-like p2p alternative.

### Tests
1. Simple pictures + text snapshot (webtorrent) hosting test from my Raspberry Pi 3b+ by [webtorrent-hybrid](https://github.com/webtorrent/webtorrent-hybrid). Step 1: peerweb.site console: `getAllTorrents()`. Step 2: copy/paste magnetURI for the peerWebSite.txt (html) and two magnetURIs for pictures into webtorrent-hybrid to download the files. Step 3: `webtorrent-hybrid seed [path/file]` to host it permanently at: https://peerweb.site/#magnet:?xt=urn:btih:123646487058d49b7d25d59842cd04862eee8822&dn=peerWebSite.txt&tr=udp%3A%2F%2Ftracker.leechers-paradise.org%3A6969&tr=udp%3A%2F%2Ftracker.coppersurfer.tk%3A6969&tr=udp%3A%2F%2Ftracker.opentrackr.org%3A1337&tr=udp%3A%2F%2Fexplodie.org%3A6969&tr=udp%3A%2F%2Ftracker.empire-js.us%3A1337&tr=wss%3A%2F%2Ftracker.btorrent.xyz&tr=wss%3A%2F%2Ftracker.openwebtorrent.com&tr=wss%3A%2F%2Ftracker.fastcast.nz ~~up since May 16th 2020~~ failed after 8 hours. Trying to resolve the issue at [webtorrent-hybrid/issues](https://github.com/webtorrent/webtorrent-hybrid/issues/67). Update: After using `--verbose` flag it has been Up since the 27th of May.

### Global Scope
Type `App` in the dev-tools console to expose the whole peerweb.site application. Interesting is `App.WebTorrentReceiver.client` for debugging the WebTorrent client.

### Big Thanks to
Muaz Khan, Feross and all others who contributed to this repo and this repos dependencies! Also thanks for your support, using this application, spreading the word and a github star ;-)

*PeerWebSite is released under MIT License . Copyright (c) Silvan Strübi.*
