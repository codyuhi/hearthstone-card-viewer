# hearthstone-card-viewer
Cody Uhi's response to the Blizzard tech take-home assessment

To start the app, follow the steps below:

1. Clone the repo

```
git clone https://github.com/codyuhi/hearthstone-card-viewer
```

2. Navigate to the `app` directory

```
cd app
```

3. Install all necessary dependencies

```
yarn install
```

4. Create a `.env` file in the `app` directory

```
touch .env
```

5. Populate the `.env` file with your Blizzard URL, Blizzard Client ID, and Blizzard Client Secret as demonstrated below (case-sensitive).  For information on generating a Blizzard Client ID/Secret, see [the docs](https://develop.battle.net/documentation/guides/getting-started)

```
VUE_APP_LOGIN_URL=https://us.battle.net
VUE_APP_API_URL=https://us.api.blizzard.com
VUE_APP_CLIENT_ID=<YOUR_CLIENT_ID>
VUE_APP_CLIENT_SECRET=<YOUR_CLIENT_SECRET>
```

5. Serve the app with `yarn serve`

```
yarn serve
```

Enjoy!
