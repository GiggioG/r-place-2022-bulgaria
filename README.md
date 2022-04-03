|Език / Language|
|--|
|[Български](#български)|
|[English](#english)|
# Български
1. Свалете това: https://chrome.google.com/webstore/detail/tampermonkey/dhdgffkkebhmkfjojejmpbldmpobfkfo?hl=en
2. Натисни върху extension-а
3. "Create new script"
4. Копи-пейст този код (върху целия файл):
```javascript
'use strict';
// ==UserScript==
// @name         r/bulgaria Template
// @namespace    http://tampermonkey.net/
// @version      0.3.1
// @description  try to take over the canvas!
// @author       wokstym - repurposed from other subreddits
// @match        https://hot-potato.reddit.com/embed*
// @icon         https://www.google.com/s2/favicons?sz=64&domain=reddit.com
// @grant        none
// ==/UserScript==
if (window.top !== window.self) {
    window.addEventListener('load', () => {
        let img;
        let src = "https://r-place-2022-bulgaria.herokuapp.com/template.png";
        document.getElementsByTagName("mona-lisa-embed")[0].shadowRoot.children[0].getElementsByTagName("mona-lisa-canvas")[0].shadowRoot.children[0].appendChild(
            (function () {
                const i = document.createElement("img");
                i.src = src + "?" + String((new Date()).getTime());
                i.style = "position: absolute; left: 0; top: 0; image-rendering: pixelated; width: 2000px; height: 1000px;"
                img = i;
                return i;
            })());
        setInterval(()=>{
            img.src = src + "?" + String((new Date()).getTime())
        }, 10000)
    }, false);
}
```
5. После save: ctrl + s
6. Накрая refresh reddit
Шаблон [u/Gigo_G](https://reddit.com/u/Gigo_G)
# English
1. Download this: https://chrome.google.com/webstore/detail/tampermonkey/dhdgffkkebhmkfjojejmpbldmpobfkfo?hl=en
2. Click on the extension icon.
3. "Create new script"
4. Copy-paste this code (replacing the one already there):
```javascript
'use strict';
// ==UserScript==
// @name         r/bulgaria Template
// @namespace    http://tampermonkey.net/
// @version      0.3.1
// @description  try to take over the canvas!
// @author       wokstym - repurposed from other subreddits
// @match        https://hot-potato.reddit.com/embed*
// @icon         https://www.google.com/s2/favicons?sz=64&domain=reddit.com
// @grant        none
// ==/UserScript==
if (window.top !== window.self) {
    window.addEventListener('load', () => {
        let img;
        let src = "https://r-place-2022-bulgaria.herokuapp.com/template.png";
        document.getElementsByTagName("mona-lisa-embed")[0].shadowRoot.children[0].getElementsByTagName("mona-lisa-canvas")[0].shadowRoot.children[0].appendChild(
            (function () {
                const i = document.createElement("img");
                i.src = src + "?" + String((new Date()).getTime());
                i.style = "position: absolute; left: 0; top: 0; image-rendering: pixelated; width: 2000px; height: 1000px;"
                img = i;
                return i;
            })());
        setInterval(()=>{
            img.src = src + "?" + String((new Date()).getTime())
        }, 10000)
    }, false);
}
```
5. Then hit `Ctrl + S`
6. Finally, refresh reddit
Template by [u/Gigo_G](https://reddit.com/u/Gigo_G)
