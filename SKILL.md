---
name: aaz-image-gen
description: Generate images via AAZ AI Proxy (Google nano-banana models).
homepage: https://api.aazai.ru/public/docs
metadata:
  {
    "openclaw":
      {
        "emoji": "🎨",
        "requires": { "env": ["AAZ_API_KEY"] },
        "primaryEnv": "AAZ_API_KEY",
      },
  }
---

# AAZ Image Generation

Always communicate with the user in Russian language.

Generate images with Google nano-banana models through the AAZ API.
Auth token is in `$AAZ_API_KEY`.

```bash
curl -s -X POST "https://api.aazai.ru/api/ai-proxy/txt2img?model=google/nano" \
  -H "Authorization: Bearer $AAZ_API_KEY" \
  -H "Content-Type: application/json" \
  -d '{"prompt": "A futuristic city at sunset", "aspect_ratio": "9:16"}'
```

Models:
- `google/nano` — standard quality
- `google/nano-pro-1K` — pro, 1024px
- `google/nano-pro-2K` — pro, 2048px
- `google/nano-pro-4K` — pro, 4096px

Parameters:
- `prompt` (required) — image description
- `aspect_ratio` — default `9:16` (vertical/mobile). Options: `1:1`, `16:9`, `9:16`, `4:3`, `3:4`, `21:9`, `9:21`
- `seed` (int) — reproducible generation
- `output_format` — `png` (default), `jpeg`, `webp`

Response example:
```json
{
  "success": true,
  "url": "https://img.aazai.ru/i/abc123",
  "images": {
    "byId": {
      "original": "https://img.aazai.ru/i/abc123",
      "large": "https://img.aazai.ru/i/abc123?w=1k",
      "medium": "https://img.aazai.ru/i/abc123?w=800",
      "small": "https://img.aazai.ru/i/abc123?w=400",
      "thumb": "https://img.aazai.ru/i/abc123?w=thumb"
    }
  },
  "metadata": {
    "model": "google/nano",
    "width": 768,
    "height": 1344,
    "seed": 42
  },
  "billing": {
    "charged": 8,
    "balance": 1036.70
  }
}
```
