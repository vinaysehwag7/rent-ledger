# Rent Ledger: a free web app for landlords

A single-page app that any landlord can open in a browser and use for one building with any number of flats. There's no sign-up and no server. Each person's data stays in their own browser on their own phone.

## What's in this folder

| File | What it is |
|---|---|
| `index.html` | The whole app |
| `manifest.webmanifest`, `icon.svg`, `icon-192.png`, `icon-512.png` | Let people install it on their home screen like an app |
| `sw.js` | Lets the app open without internet after the first visit |

Upload all of these files together, in one folder. No build step is needed.

## How a new landlord starts

1. Open the link and tap **Download template**.
2. Fill in one row per flat. Only Flat and Rent are required. The other columns are optional: tenant name, WhatsApp number, start date, security deposit, water, electricity rate, previous and current meter reading, previous balance, and paid this month.
3. Upload the sheet, give the building a name and pick the billing month.

The app also reads other sheets if their columns have recognisable names, like Flat, Tenant, Rent, Water or Previous reading. People can try it first with **sample data**.

## Hosting it for free (pick one)

**Netlify Drop (easiest, no code)**
1. Go to app.netlify.com/drop and sign up for a free account.
2. Drag this folder, or the unzipped `rent-ledger-app.zip`, onto the page.
3. You get a link like `https://something.netlify.app`. In Site settings you can rename it, for example to `rentledger-yourname.netlify.app`.

**GitHub Pages (free; best if Claude will keep updating it)**
1. Create a free GitHub account and a new public repository, for example `rent-ledger`.
2. Upload these files, then go to Settings → Pages → Deploy from branch → `main` / root.
3. The link will be `https://<username>.github.io/rent-ledger/`.

**Cloudflare Pages** also works. Choose Workers & Pages → Create → Pages → Upload assets, then upload the folder.

The app needs HTTPS for home-screen install and offline use. All three hosts above provide it.

## Things to know

- **Data stays on the device.** Clearing browser data deletes it. Tell users to tap ⋯ → **Download a backup** now and then. To move to a new phone, restore that file on the new phone.
- **One building per browser.** To manage a second building, use a different browser or profile, or keep a backup of each building and restore the one you need.
- **WhatsApp:** the Send button opens WhatsApp with the bill already typed. The landlord taps send.
- **Possible next step:** an optional sign-in with cloud sync, so data follows the landlord across devices and can't be lost. This needs a free backend such as Supabase or Firebase, and an account to own it.
