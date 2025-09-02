# Microsoft-Rewards-Script
Automated Microsoft Rewards script, however this time using TypeScript, Cheerio and Playwright.

Under development, however mainly for personal use!

## How to setup ##
1. Download or clone source code
2. Change `accounts.example.json` to `accounts.json` and add your account details
3. Change `config.json` to your liking
4. Run `npm i` to install the packages
5. Run `npm run build` to build the script
6. Run `npm run start` to start the built script

## Notes ##
- If you end the script without closing the browser window first (only with headless as false), you'll be left with hanging chrome instances using resources. Use taskmanager to kill these or use the included `npm run kill-chrome-win` script. (Windows)
- If you automate this script, set it to run at least 2 times a day to make sure it picked up all tasks, set `"runOnZeroPoints": false` so it doesn't run when no points are found.

## Config ## 
| Setting        | Description           | Default  |
| :------------- |:-------------| :-----|
|  baseURL    | MS Rewards page | `https://rewards.bing.com` |
|  sessionPath    | Path to where you want sessions/fingerprints to be stored | `sessions` (In ./browser/sessions) |
|  headless    | If the browser window should be visible be ran in the background | `false` (Browser is visible) |
|  parallel    | If you want mobile and desktop tasks to run parallel or sequential| `true` |
|  runOnZeroPoints    | Run the rest of the script if 0 points can be earned | `false` (Will not run on 0 points) |
|  clusters    | Amount of instances ran on launch, 1 per account | `1` (Will run 1 account at the time) |
|  saveFingerprint.mobile    | Re-use the same fingerprint each time | `false` (Will generate a new fingerprint each time) |
|  saveFingerprint.desktop    | Re-use the same fingerprint each time | `false` (Will generate a new fingerprint each time) |
|  workers.doDailySet    | Complete daily set items | `true`  |
|  workers.doMorePromotions    | Complete promotional items | `true`  |
|  workers.doPunchCards    | Complete punchcards | `true`  |
|  workers.doDesktopSearch    | Complete daily desktop searches | `true`  |
|  workers.doMobileSearch    | Complete daily mobile searches | `true`  |
|  workers.doDailyCheckIn    | Complete daily check-in activity | `true`  |
|  workers.doReadToEarn    | Complete read to earn activity | `true`  |
|  searchOnBingLocalQueries    | Complete the activity "search on Bing" using the `queries.json` or fetched from this repo | `false` (Will fetch from this repo)   |
|  globalTimeout    | The length before the action gets timeout | `30s`   |
|  searchSettings.useGeoLocaleQueries    | Generate search queries based on your geo-location | `false` (Uses EN-US generated queries)  |
|  searchSettings.scrollRandomResults    | Scroll randomly in search results | `true`   |
|  searchSettings.clickRandomResults    | Visit random website from search result| `true`   |
|  searchSettings.searchDelay    | Minimum and maximum time in milliseconds between search queries | `min: 3min`    `max: 5min` |
|  searchSettings.retryMobileSearchAmount     | Keep retrying mobile searches for specified amount | `2` |
|  logExcludeFunc | Functions to exclude out of the logs and webhooks | `SEARCH-CLOSE-TABS` |
|  webhookLogExcludeFunc | Functions to exclude out of the webhooks log | `SEARCH-CLOSE-TABS` |
|  proxy.proxyGoogleTrends     | Enable or disable proxying the request via set proxy | `true` (will be proxied) |
|  proxy.proxyBingTerms     | Enable or disable proxying the request via set proxy | `true` (will be proxied) |
|  webhook.enabled     | Enable or disable your set webhook | `false` |
|  webhook.url     | Your Discord webhook URL | `null` |

## Features ##
- [x] Multi-Account Support
- [x] Session Storing
- [x] 2FA Support
- [x] Passwordless Support
- [x] Headless Support
- [x] Discord Webhook Support
- [x] Desktop Searches
- [x] Configurable Tasks
- [x] Microsoft Edge Searches
- [x] Mobile Searches
- [x] Emulated Scrolling Support
- [x] Emulated Link Clicking Support
- [x] Geo Locale Search Queries
- [x] Completing Daily Set
- [x] Completing More Promotions
- [x] Solving Quiz (10 point variant)
- [x] Solving Quiz (30-40 point variant)
- [x] Completing Click Rewards
- [x] Completing Polls
- [x] Completing Punchcards
- [x] Solving This Or That Quiz (Random)
- [x] Solving ABC Quiz
- [x] Completing Daily Check In
- [x] Completing Read To Earn
- [x] Clustering Support
- [x] Proxy Support

## Disclaimer ##
Your account may be at risk of getting banned or suspended using this script, you've been warned!
<br /> 
Use this script at your own risk!
