# Gull Harbor website

Three pages for GitHub Pages: a home page that points to the App Store, plus the privacy policy and the support page that Apple requires. They're plain HTML and CSS, with no build step and nothing loaded from other sites.

| Page | File | Where its address goes in App Store Connect |
|---|---|---|
| Home | `index.html` | Marketing URL, on the version page (optional) |
| Privacy policy | `privacy/index.html` | Privacy Policy URL, under App Privacy (required) |
| Support | `support/index.html` | Support URL, on the version page (required). The page's button starts an email to jprose96@gmail.com |

## Put it online

The listing already points at **https://jprosenblatt.github.io/gull-harbor/**: `docs/appstore/upload/metadata/en-US/` has `support_url.txt`, `privacy_url.txt` and `marketing_url.txt`. So the repository must be called exactly `gull-harbor`, on the `jprosenblatt` account.

1. On github.com, signed in as `jprosenblatt`, make a new **public** repository called `gull-harbor`. GitHub Pages is free only for public repositories, and this one holds only the site, not the game.
2. In the new repository, choose **Add file › Upload files**. Drag in everything *inside* this folder (`index.html`, `privacy`, `support`, `assets` and this README), then commit.
3. Open **Settings › Pages**. Set the source to **Deploy from a branch**, the branch to `main` and the folder to `/ (root)`, then save.
4. About a minute later the site is live:
   - home: https://jprosenblatt.github.io/gull-harbor/
   - privacy policy: https://jprosenblatt.github.io/gull-harbor/privacy/
   - support: https://jprosenblatt.github.io/gull-harbor/support/

   Open each one on your phone.
5. Paste the three addresses from those files into App Store Connect: the support and marketing URLs on the version page, and the privacy policy URL under App Privacy.

If the site ends up somewhere else, change the three files to match.

## The App Store link

The home page's "View on the App Store" button links to https://apps.apple.com/app/gull-harbor/id6825458182 (Apple ID 6825458182). That address has no country in it, so each visitor gets their own country's store.

## Changing a page

- Edit the HTML directly. The colours and fonts are the brand's (`docs/branding/README.md`), and they're set in `assets/site.css`.
- When the privacy policy changes, update its effective date. It's true of the game today: no data collected, no network code, no third-party SDKs. Check it again if the game ever gains analytics, ads, Game Center, iCloud sync or links out; `../privacy-and-age-rating.md` lists what would change.
- The screenshots in `assets/shots/` are copies of `../upload/screenshots/iphone-6.9/`, 1434 px wide. If the set changes, remake them with `sips -s format jpeg -s formatOptions 78 -Z 1434 <screenshot> --out assets/shots/<name>.jpg`.
- To preview the site on your Mac, run `python3 -m http.server --directory docs/appstore/website` and open http://localhost:8000.
