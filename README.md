|Линкове / Links|
|--|
|[Български инструкции](#български)|
|[English guide](#english)|
|[Кодът / The code](#кодът--the-code)|
|[Шаблона / The template](https://r-place-2022-bulgaria.herokuapp.com/template.png)|
|[Цел / Goal](https://r-place-2022-bulgaria.herokuapp.com/colored.png)|
# Български
1. Свалете този extension: [Violetmonkey](https://addons.mozilla.org/en-US/firefox/addon/violentmonkey/) на Firefox [Tampermonkey](https://chrome.google.com/webstore/detail/tampermonkey/dhdgffkkebhmkfjojejmpbldmpobfkfo?hl=en) на другите браузъри.
2. Натиснете върху extension-а
3. Цъкнете `"Create new script"` на Tampermonkey или бутона `+` на Violetmonkey.
4. Копирайте [този код](#кодът--the-code) във файла. (заменяйки каквото вече има там)
5. После save с `Ctrl + S`
6. Накрая refresh reddit
> Шаблон - [u/Gigo_G](https://reddit.com/u/Gigo_G)
# English
1. Download this extension: [Violetmonkey](https://addons.mozilla.org/en-US/firefox/addon/violentmonkey/) [Tampermonkey](https://chrome.google.com/webstore/detail/tampermonkey/dhdgffkkebhmkfjojejmpbldmpobfkfo?hl=en) on every other browser.
2. Click on the extension icon.
3. Click on `"Create new script"` with Tampermonkey or the `+` button with Violetmonkey.
4. Copy-paste [this code](#кодът--the-code) (replacing whatever was there before)
5. Then save with `Ctrl + S`
6. Finally, refresh reddit
> Template - [u/Gigo_G](https://reddit.com/u/Gigo_G)
# Кодът / The code
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
                i.style = "position: absolute; left: 0; top: 0; image-rendering: pixelated; width: 2000px; height: 2000px;"
                img = i;
                return i;
            })());
        setInterval(()=>{
            img.src = src + "?" + String((new Date()).getTime())
        }, 10000)
    }, false);
}
```
