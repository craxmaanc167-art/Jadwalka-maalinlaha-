# 🌙 Jadwalkayga Nolosha

App jadwal oo shaqeeya sida website iyo sida app taleefanka (PWA). Waxaa ku jira: jadwal maalinle / usbuucle / bille, diin, dhaqaale, waxbarasho, wax la bartay, qaladaad, iyo "Alle la hadal". Waxaa kale oo leh PIN, ogeysiis iyo Gmail.

## Faylasha
- `index.html` – app-ka (HTML + CSS + JS)
- `manifest.json` – macluumaadka app-ka (magac, midab, icon)
- `sw.js` – service worker (offline + ogeysiis)
- `icon-192.png`, `icon-512.png` – icon-yada

## 1. Isticmaal degdeg ah (kombiyuutarka)
Fur `index.html` browser-ka. (Halkan PIN, ogeysiis iyo Gmail way shaqeeyaan, laakiin dagista app-ka (install) iyo offline waxay u baahan yihiin website, eeg tallaabo 2.)

## 2. Ka dhig website qof walba soo dagi karo (bilaash)
Waxaad u baahan tahay oo keliya inaad faylasha geliso hosting (https). Waa kuwan ugu fudud:

**Netlify (ugu fudud, ma u baahna akoon si tijaabo ah):**
1. Gal https://app.netlify.com/drop
2. Soo jiid folder-ka `jadwal-app` (ama ZIP-ka la furay).
3. Waxaad heleysaa link sida `https://magacaaga.netlify.app`.

**GitHub Pages:**
1. Samee repository cusub oo GitHub ah, ku soo geli faylasha.
2. Settings → Pages → Branch: `main` → Save.
3. Link: `https://magacaaga.github.io/magac-repo/`

**Vercel / Cloudflare Pages** sidoo kale way shaqeeyaan: folder-ka soo geli, ma jiro build command.

Kadib link-ga la wadaag qof walba.

## 3. Sida qof uu u dagayo app-ka
Marka website-ku furan yahay:
- **Android (Chrome):** menu ⋮ → *Install app* (ama *Add to Home screen*), ama Dejinta ⚙️ → "Dag Jadwalkayga".
- **iPhone (Safari):** Share ⬆️ → *Add to Home Screen*.
- **Kombiyuutar (Chrome/Edge):** calaamadda dagista ee address bar-ka.

## 4. Gmail (Google Sign-In)
1. Gal https://console.cloud.google.com → APIs & Services → Credentials → Create Credentials → **OAuth client ID** → Web application.
2. Ku dar URL-ka website-kaaga "Authorized JavaScript origins" (tusaale `https://magacaaga.netlify.app`).
3. Koobiye Client ID-ga, kadibna fur `index.html` oo ku beddel:
   `const GOOGLE_CLIENT_ID = '';` → `const GOOGLE_CLIENT_ID = 'ID-gaaga.apps.googleusercontent.com';`
4. Dib u geli website-ka.

## Xusuusin muhiim ah
- Xogta qof kasta waxay ku kaydsan tahay **taleefankiisa/browser-kiisa**; ma jiro server. Isticmaale kasta xogtiisa keliya ayuu arkaa.
- Si xogta loogu wareejiyo qalab kale, isticmaal **Dejinta → Kayd (Backup)**.
- Ogeysiisku wuxuu shaqeeyaa marka app-ku furan yahay ama ku jiro dhabarka; ogeysiis marka app-ku gebi ahaanba xidhan yahay wuxuu u baahan yahay server (Push), taas oo la dari karo.
- PIN-ku waa ilaalin ku saabsan qalabka, ma ahan sir-qarin xirfad leh.
