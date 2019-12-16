# urlbar-weather

Watch a [short demo video](https://imgur.com/a/T81yjxJ).

## Instructions
Be advised that the weather result is not currently supported in Nightly.
Apply the stack of patches starting with [D56639](https://phabricator.services.mozilla.com/D56639)
to test this extension.

1. Clone this repo and install the dependencies.
2. Create a file `src/secret_keys.js` with the following contents:
```
/* This Source Code Form is subject to the terms of the Mozilla Public
* License, v. 2.0. If a copy of the MPL was not distributed with this
* file, You can obtain one at http://mozilla.org/MPL/2.0/. */

"use strict";

const DARKSKY_SECRET_KEY = "<YOUR_API_KEY_HERE>";
const BING_SECRET_KEY = "<YOUR_API_KEY_HERE>";
```
  Also note that if you wish to use live data with your API key, you must
  disable the TESTING_MODE boolean in `src/background.js`.

2. `web-ext build`
3. In your local build of Firefox, open about:debugging.
4. Install the .zip file created by `web-ext build` as a temporary add-on.
5. Search for "weather" or "weather in `<LOCATION_NAME>`" in the Urlbar.

## Known issues
- The weather result occasionally will not show up the first time it is triggered (caching issue).