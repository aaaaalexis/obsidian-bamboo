# Bamboo

> _Bamboo splits cleanly at its nodes, so should your words._

**Bamboo** patches Obsidian's built-in CodeMirror editor to use proper word segmentation for Chinese, Japanese, and Korean (CJK) text.

## Comparison

In my experience, Bamboo produces better splits, but [Word Splitting](https://github.com/aidenlx/cm-chs-patch) is the long-standing plugin for Chinese word splitting. Here's how the two compare:

|                         | Bamboo                                                    | Word Splitting                                            |
| ----------------------- | --------------------------------------------------------- | --------------------------------------------------------- |
| **Languages**           | Traditional Chinese, Simplified Chinese, Japanese, Korean | Simplified Chinese                                        |
| **Segmentation engine** | `Intl.Segmenter` with regex fallback                      | `Intl.Segmenter` (zh-CN only) with optional Jieba runtime |
| **Vim mode support**    | No                                                        | Yes                                                       |
| **Custom word lists**   | No                                                        | Yes (requires Jieba)                                      |

## Installation

**From the Obsidian Community Plugins browser:**

1. Open **Settings → Community plugins** and disable Safe Mode if prompted.
2. Click **Browse** and search for **Bamboo**.
3. Click **Install**, then **Enable**.

**Manual installation:**

1. Download `main.js` and `manifest.json` from the [latest release](../../releases/latest).
2. Copy them into your vault at `.obsidian/plugins/bamboo/`.
3. Reload Obsidian and enable the plugin under **Settings → Community plugins**.

## How It Works

Bamboo uses the browser's built-in [`Intl.Segmenter`](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Intl/Segmenter) API to find natural word boundaries in Chinese, Japanese, and Korean text. When that API is not available, a fallback rule-based segmenter kicks in automatically.

The plugin automatically detects whether the text around your cursor is CJK and steps aside for regular Latin text, so it never changes how you work with English, code, or anything else.

## Supported Languages

- Chinese (Traditional & Simplified)
- Japanese (Hiragana, Katakana, Kanji)
- Korean (Hangul)

## License

Bamboo is licensed under the [MIT license](LICENSE).

---

_This plugin was built entirely with **GitHub Copilot**, powered by **Claude Sonnet 4.6** and **GPT-5.3-Codex**._
