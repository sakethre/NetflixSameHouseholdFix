# Netflix Household No More 

A browser extension aiming to bypass the Netflix household verification prompts by employing different strategies depending on the page context. Total effort, less than 5 minutes if done right. 

**Supports:** `Chrome` (and Chromium-based browsers like Edge, Brave, Comet, Atlas, Dia, etc.) 
**Supports:** `Chrome` (and Chromium-based browsers like Brave, Comet, MS Edge) | Yet to write code for:  `Firefox`(Update: Not worth the effor, just use chromium?)

---

## Features

*   **Blocks Verification Request on `/watch`:** Prevents the specific GraphQL network request associated with the household check from running when you are on a video watching page (`/watch/`).
*   **Hides Verification Modal on `/browse` (and others):** On pages *other* than `/watch/` (like the main browse page), it hides the household verification modal popup if it appears.
*   **Target:** Only affects `netflix.com` domains.


---

## Installation

**Google Chrome / Microsoft Edge / Chromium Browsers:** Extension not published on chrome store hence use this code here in this githib.


## Installation (Local Development/Testing)

As this extension is not published on chrome store(no plans to). You need to load it manually, its striagnforward.
https://www.youtube.com/watch?v=ayMTZPphrJI for reference on manual loading of general chrome extensions

**Google Chrome / Microsoft Edge / Chromium Browsers such as Comet, Brave, Atlas, Dia, MS Edge and many:**

1.  Download or clone this repository to your local machine.
2.  Open your browser and navigate to `chrome://extensions` (or `edge://extensions`).
3.  Enable **Developer mode** (usually a toggle in the top-right corner).
4.  Click the **Load unpacked** button.
5.  Select the directory where you saved the extension files (the folder containing `manifest.json`).
6.  The extension should now be loaded and active.

---

## Caveats & Known Issues

*   **Netflix Video player UI is not visible:** If you dont see the video player UI, just refresh the page. that should fix it for you.

*   **Netflix Updates:** Netflix frequently updates its website and internal APIs. Any changes to the GraphQL endpoint URL, the request structure, the page structure (`/watch/` path), or the modal's CSS selectors/HTML structure could break this extension partially or completely.
*   **Console Errors:** When on a `/watch/` page, you **will** see network errors (often CORS-related) in the browser's developer console. This is an expected side effect of the extension successfully blocking the network request. While visually noisy, it generally does not impact performance.
*   **Fragile css:** The modal hiding relies on specific CSS class names and `data-uia` attributes. These might change without notice.

---

## Disclaimer

*   This extension is not endorsed by or affiliated with Netflix in any way.
*   Use this extension at your own risk. I assume no liability.
*   Modifying network requests or the DOM on third-party websites might violate their Terms of Service. Be aware of the potential consequences.
*   Saketh Reddy Narahari









