# Smart Outfit Planner

Mini project · TYCS (B.Sc. Computer Science) · Tilak College of Science and Commerce, Vashi

A front-end web application that suggests outfits from the user's own wardrobe based on occasion, temperature, rain and color match.

## Folder structure

```
smart-outfit-planner/
├── index.html      Page structure
├── css/style.css   Design and responsive layout
├── js/app.js       All logic (wardrobe, scoring, weather, weekly plan)
└── README.md       This file
```

## How to run

1. Unzip the folder.
2. Double-click `index.html`. It opens in your browser. No installation is needed.
3. Optional: in VS Code, install the "Live Server" extension, right-click `index.html` and choose "Open with Live Server".

Internet is only needed for the Google Fonts and the optional "Use live weather" button. Everything else works offline.

## How to use

1. Open **My wardrobe**. A sample wardrobe is already loaded. Add your own pieces with the form.
2. Open **Outfit planner**. Choose an occasion, set the temperature and tick rain if needed.
3. Click **Suggest outfits** to see three matched outfits. Click **Show different options** for more.
4. Click **Save outfit** on the ones you like.
5. Open **Weekly plan**. Choose a saved outfit for each day, or click **Auto-plan my week**.
6. Click **Print** to print the weekly plan.

## How the suggestion works

Every combination of top + bottom + footwear (+ optional outerwear and accessory) that suits the chosen occasion is scored:

| Factor | Weight | Rule |
|---|---|---|
| Color match | 50% | Neutral shades (black, white, grey, navy, beige, brown) pair with anything. Other colors score high when close in hue or opposite on the color wheel. More than two bold hues lowers the score. |
| Weather fit | 45% | Total warmth of the layers is compared with a target for the temperature. Below 16°C an outer layer is required. At 27°C and above (without rain) no outer layer is used. |
| Accessory | 5% | Small bonus when an accessory is added. |

When it is raining, footwear not marked "Works well in rain" loses points.

The three best outfits are shown, using different tops where possible.

## Technologies used

- HTML5
- CSS3 (Grid, Flexbox, custom properties)
- JavaScript ES6
- localStorage for saving data in the browser
- Open-Meteo API for optional live weather (no API key needed)

## Publish online (free)

1. Create a GitHub account and a new repository.
2. Upload the files with the same folder structure.
3. Go to Settings → Pages, choose the `main` branch and save.
4. Your site link appears after a minute.

## Possible questions in viva

- **Why localStorage?** The project has no backend. localStorage keeps the user's wardrobe in their own browser.
- **How is color matching done?** Colors are converted from HEX to HSL. Hue difference decides if two colors suit each other.
- **What is the future scope?** User login with a database, photo upload for clothes, AI-based style learning, shopping suggestions for missing pieces.

## Developed by

Chandan Prasad · TYCS · Tilak College of Science and Commerce (Autonomous), Vashi, Navi Mumbai
