<div align="center">

<h1>📦 pic-cdn</h1>

<p>A self-hosted image library with <strong>7,000 hand-picked images</strong> across 7 categories.<br>
No API key. No rate limits. Just raw GitHub CDN URLs that always work.</p>

[![](https://img.shields.io/badge/7%2C000%20images-a78bfa?style=for-the-badge&logoColor=white)](./index.json)
[![](https://img.shields.io/badge/7%20categories-818cf8?style=for-the-badge&logoColor=white)](./index.json)
[![](https://img.shields.io/badge/GitHub%20Raw%20CDN-6366f1?style=for-the-badge&logo=github&logoColor=white)](https://raw.githubusercontent.com/faisaljs/pic-cdn/main)
[![](https://img.shields.io/badge/MIT%20License-4f46e5?style=for-the-badge&logoColor=white)](./LICENSE)

</div>

---

## preview

<div align="center">

<table>
<tr>
<td align="center"><img src="https://raw.githubusercontent.com/faisaljs/pic-cdn/main/girls/0.jpg" width="100" height="100" style="border-radius:8px"/><br/><sub><b>girls</b></sub></td>
<td align="center"><img src="https://raw.githubusercontent.com/faisaljs/pic-cdn/main/boys/0.jpg" width="100" height="100" style="border-radius:8px"/><br/><sub><b>boys</b></sub></td>
<td align="center"><img src="https://raw.githubusercontent.com/faisaljs/pic-cdn/main/anime/0.jpg" width="100" height="100" style="border-radius:8px"/><br/><sub><b>anime</b></sub></td>
<td align="center"><img src="https://raw.githubusercontent.com/faisaljs/pic-cdn/main/couples/0.jpg" width="100" height="100" style="border-radius:8px"/><br/><sub><b>couples</b></sub></td>
<td align="center"><img src="https://raw.githubusercontent.com/faisaljs/pic-cdn/main/banners/42.jpg" width="100" height="100" style="border-radius:8px"/><br/><sub><b>banners</b></sub></td>
<td align="center"><img src="https://raw.githubusercontent.com/faisaljs/pic-cdn/main/wallpapers/0.jpg" width="100" height="100" style="border-radius:8px"/><br/><sub><b>wallpapers</b></sub></td>
<td align="center"><img src="https://raw.githubusercontent.com/faisaljs/pic-cdn/main/server-icons/0.jpg" width="100" height="100" style="border-radius:8px"/><br/><sub><b>server-icons</b></sub></td>
</tr>
</table>

</div>

---

## what is this

A static image library hosted on GitHub. Every image is a plain `.jpg` file served directly over GitHub's CDN — no server, no auth, no downtime. Fetch a URL and you have an image. That's the entire thing.

Built for Discord bots, web projects, and anything that needs a reliable stream of images without dealing with API keys or rate limits. If GitHub is up, this is up.

---

## categories

| category | images | aspect | description |
|----------|-------:|--------|-------------|
| `girls` | 1,000 | 1:1 | Female profile pictures |
| `boys` | 1,000 | 1:1 | Male profile pictures |
| `anime` | 1,000 | 1:1 | Anime-style profile pictures |
| `couples` | 1,000 | 1:1 | Couple profile pictures |
| `banners` | 1,000 | 3:1+ | Discord / Twitter banners |
| `wallpapers` | 1,000 | 16:9 | Desktop wallpapers |
| `server-icons` | 1,000 | 1:1 | Server / community icons |

---

## how to use

Images follow a simple, predictable URL pattern. Pick a category, pick any number from `0` to `999`:

```
https://raw.githubusercontent.com/faisaljs/pic-cdn/main/{category}/{n}.jpg
```

Fetch `index.json` once to get the counts, then build any URL you need:

```
https://raw.githubusercontent.com/faisaljs/pic-cdn/main/index.json
```

```js
async function random(category) {
  const { base_url, categories } = await fetch(
    "https://raw.githubusercontent.com/faisaljs/pic-cdn/main/index.json"
  ).then(r => r.json());

  const n = Math.floor(Math.random() * categories[category]);
  return `${base_url}/${category}/${n}.jpg`;
}

await random("anime");        // → .../anime/487.jpg
await random("server-icons"); // → .../server-icons/62.jpg
```

```python
import httpx, random as rnd

index = httpx.get("https://raw.githubusercontent.com/faisaljs/pic-cdn/main/index.json").json()

def random(category: str) -> str:
    n = rnd.randint(0, index["categories"][category] - 1)
    return f"{index['base_url']}/{category}/{n}.jpg"

random("wallpapers")  # → .../wallpapers/213.jpg
```
---

## npm package

An npm wrapper is also available if you prefer installing via a package manager.

```bash
npm install piccdn
```

→ [npmjs.com/package/piccdn](https://www.npmjs.com/package/piccdn)

```js
import { random, url } from "piccdn";

await random("anime");          // → full URL to a random anime image
url("wallpapers", 42);          // → .../wallpapers/42.jpg
```

The package ships with TypeScript types and zero dependencies — it's a thin wrapper around the same raw CDN URLs above.

---

## direct links

No code needed. Any of these URLs work as-is:

```
https://raw.githubusercontent.com/faisaljs/pic-cdn/main/girls/0.jpg
https://raw.githubusercontent.com/faisaljs/pic-cdn/main/boys/0.jpg
https://raw.githubusercontent.com/faisaljs/pic-cdn/main/anime/0.jpg
https://raw.githubusercontent.com/faisaljs/pic-cdn/main/couples/0.jpg
https://raw.githubusercontent.com/faisaljs/pic-cdn/main/banners/0.jpg
https://raw.githubusercontent.com/faisaljs/pic-cdn/main/wallpapers/0.jpg
https://raw.githubusercontent.com/faisaljs/pic-cdn/main/server-icons/0.jpg
```

Replace `0` with any number from `0` to `999`.

---

## credits

Built and maintained by [faisal](https://github.com/faisaljs).<br>

---

<div align="center">

[MIT](LICENSE) &copy; 2026 [faisal](https://github.com/faisaljs) &nbsp;·&nbsp; [index.json](https://raw.githubusercontent.com/faisaljs/pic-cdn/main/index.json)

</div>
