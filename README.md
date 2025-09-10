# GitHub Pages Stream Site

Ye repo ek static GitHub Pages site banata hai jahan tum stream link aur 5 promo links dikhla sakte ho.

## Deploy (simple)
1. GitHub pe naya repo banao (public). Name koi bhi rakh sakte ho (for example `my-stream-room`).
2. Is repo me files upload karo: `index.html`, `redirect.html`, `config.json`, `styles.css`, `assets/offline.jpg`.
3. Repo > Settings > Pages > Source select karo: `main` branch and `/ (root)` -> Save. Thodi der me site `https://<your-username>.github.io/<repo>/` pe live ho jayegi.

## Kaise links / stream change karein
- GitHub repo me `config.json` open karo -> Edit -> Commit changes. Page refresh karne par naye config reflect ho jayega.

## Token-based simple access
- `config.json` me `access_token` field fill kar do (kuch random string).
- Jab user site kholega, page `?k=<token>` parameter check karega ya prompt maangega.
- **Note:** token client-side होने की वजह se secure nahi hai; koi bhi repo-dekhega token dekh lega.

## CORS aur Stream issues
- Agar stream `.m3u8` ya remote media pe host hai aur CORS headers nahi diye gaye to browser health-check/fetch ho sakta hai block.
- Agar stream player error de to browser DevTools ki Console me network errors check karo.

## Redirect behavior
- Promo buttons redirect to `redirect.html?id=1` etc. Redirect page `config.json` padhkar target par client-side redirect karta hai.

## Agar chahie to main kar dunga
- GitHub Actions-based admin to update config.json from a web form (advanced).
- Firebase-based authentication (real access control).
