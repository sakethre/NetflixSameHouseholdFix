# Netflix Same Household Issue Code fix

A browser extension aiming to bypass the Netflix household verification prompts by employing different strategies depending on the page context. Total effort, less than 5 minutes if done right. 

**Supports:** `Chrome` (and Chromium-based browsers like Edge, Brave, Comet, Atlas, Dia, etc.) and `Firefox` (121+)

---

## Features

*   **Blocks Verification Request on `/watch`:** Prevents the specific GraphQL network request associated with the household check from running when you are on a video watching page (`/watch/`).
    *   On Firefox, only the household check operations (`CLCSInterstitialPlaybackAndPostPlayback`, `CLCSSendFeedback`) are blocked, on any Netflix page, so the player still loads normally.
*   **Hides Verification Modal on `/browse` (and others):** On pages *other* than `/watch/` (like the main browse page), it hides the household verification modal popup if it appears.
*   **Target:** Only affects `netflix.com` domains.


---

## Installation

**Google Chrome / Microsoft Edge / Chromium Browsers:** Extension not published on the Chrome Web Store, hence use the code here in this GitHub repo.


## Installation (Local Development/Testing)

As this extension is not published on the Chrome Web Store (no plans to), you need to load it manually. It's straightforward.
https://www.youtube.com/watch?v=ayMTZPphrJI for reference on manual loading of general Chrome extensions.

**Google Chrome / Microsoft Edge / Chromium Browsers such as Comet, Brave, Atlas, Dia, MS Edge and many:**

1.  Download or clone this repository to your local machine.
2.  Open your browser and navigate to `chrome://extensions` (or `edge://extensions`).
3.  Enable **Developer mode** (usually a toggle in the top-right corner).
4.  Click the **Load unpacked** button.
5.  Select the directory where you saved the extension files (the folder containing `manifest.json`).
6.  The extension should now be loaded and active.

**Firefox:**

1.  Download or clone this repository to your local machine.
2.  Open Firefox and navigate to `about:debugging#/runtime/this-firefox`.
3.  Click **Load Temporary Add-on...** and select the `manifest.json` file.
4.  Go to `about:addons`, click the extension, open the **Permissions** tab and turn on access for `netflix.com`. Don't skip this, without it the extension does nothing and shows no error.
5.  The extension should now be loaded and active.

Temporary add-ons get removed when Firefox restarts. To keep it permanently, either use Firefox Developer Edition/Nightly with `xpinstall.signatures.required` set to `false` in `about:config`, or sign it yourself as unlisted with `npx web-ext sign --channel=unlisted` (needs a free AMO account and a unique `id` in `manifest.json`).

---

## Caveats & Known Issues

*   **Netflix Video player UI is not visible:** If you don't see the video player UI, just refresh the page. That should fix it for you.

*   **Netflix Updates:** Netflix frequently updates its website and internal APIs. Any changes to the GraphQL endpoint URL, the request structure, the page structure (`/watch/` path), or the modal's CSS selectors/HTML structure could break this extension partially or completely.
*   **Console Errors:** When on a `/watch/` page, you **will** see network errors (often CORS-related) in the browser's developer console. This is an expected side effect of the extension successfully blocking the network request. While visually noisy, it generally does not impact performance.
*   **Fragile CSS:** The modal hiding relies on specific CSS class names and `data-uia` attributes. These might change without notice.

---

## Disclaimer

*   This extension is not endorsed by or affiliated with Netflix in any way.
*   Use this extension at your own risk. I assume no liability.
*   Modifying network requests or the DOM on third-party websites might violate their Terms of Service. Be aware of the potential consequences.
*   Saketh Reddy Narahari










