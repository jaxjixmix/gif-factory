# English translation of GIF Factory

This is an English translation of **[WoYun520/gif-factory](https://github.com/WoYun520/gif-factory)** (MIT licensed, © the original author). Upstream is the source of truth; this fork exists so English readers can use the same skill, styles and workflows.

## What was translated

- Every Markdown document: [README.md](README.md), [GUIDE.md](GUIDE.md), [GALLERY.md](GALLERY.md), [SKILL.md](SKILL.md), `styles/**`, `references/**`, `skills/**`, `examples/**`, `agents/**`.
- Prose values inside the JSON/YAML artifacts (`styles/catalog.json`, review/production/prompt manifests, `agents/openai.yaml`).
- User-visible strings in the `scripts/*.py` exporters (bundle and preview filenames, CLI help and messages).

## What was not translated

- **Media assets are the originals.** Every `.gif`, `.mp4`, `.webp`, `.png` file is byte-identical to upstream; previews that contain Chinese lettering still show Chinese lettering. Translating them would mean regenerating the sample art, which would no longer be the author's work.
- Chinese-language example inputs that only make sense in Chinese (e.g. `skills/dynamic-art-signature/assets/chinese/*.json` calligraphy parameter sets).
- File names, directory names, style ids, JSON keys, commands, flags and link targets — the layout is 1:1 with upstream so diffs against upstream stay readable.

Two directories were renamed because their Chinese names escaped into URLs:

| Upstream | Here |
| --- | --- |
| `examples/mixed-actions/01-真人/` | `examples/mixed-actions/01-real-people/` |
| `examples/mixed-actions/02-二次元/` | `examples/mixed-actions/02-anime/` |

Every reference to them in docs, `styles/catalog.json` and `docs/previews/review.json` was updated.

## Style names (English / Chinese alias)

Chinese style names are kept in parentheses on first mention in each document, because that is what users type when invoking the skill. The English names line up with the style ids:

| Style id | English | Chinese |
| --- | --- | --- |
| `pixel-light` | Pixel Light Motion | 像素轻动效 |
| `pixel-actions` | Pixel Full Actions | 像素完整动作 |
| `illustrated-actions` | Illustrated Character Actions | 插画角色动作 |
| `photo-people` | Photographic People | 真人风 |
| `photo-pets` | Photographic Pets | 宠物写实 |
| `clay-mascot` | Clay Mascot | 黏土吉祥物 |
| `lenticular` | Lenticular Card | 电子光栅卡 |
| `comic-fusion` | Comic Fusion | 漫画印刷融合 |
| `type-linked` | Type-Linked | 文字联动 |
| `dynamic-signatures` | Dynamic Art Signature | 动态艺术签名 |
| `compact-storybook` | Compact Storybook | 紧凑动态绘本 |

## Syncing with upstream

```bash
git remote add upstream https://github.com/WoYun520/gif-factory.git
git fetch upstream
git merge upstream/main
```

Translation fixes are welcome as pull requests here. Improvements to the skill itself belong upstream.

## License

MIT, unchanged — see [LICENSE](LICENSE).
