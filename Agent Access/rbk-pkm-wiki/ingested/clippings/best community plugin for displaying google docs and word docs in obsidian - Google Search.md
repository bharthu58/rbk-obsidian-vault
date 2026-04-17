---
title: "best community plugin for displaying google docs and word docs in obsidian - Google Search"
source: "https://www.google.com/search?q=best+community+plugin+for+displaying+google+docs+and+word+docs+in+obsidian&sca_esv=0667ee56d50f5041&rlz=1C1VDKB_enUS1138US1138&sxsrf=ANbL-n4nsAol0JwfXP3Gz5eWtnRtYePI4g%3A1774668495022&fbs=ADc_l-aN0CWEZBOHjofHoaMMDiKpV6Bbbmx4QVaoKkiRQ2jlwvCHF0Eqz8cUq4JjDCZnrJEBkqnc9LrI8nUkWhrkCUsnugMp6AVAyhwz9WGS2CP4W-aoa2GkfLeFU91AwX2GFsXD6EA5AYPvV6O61ZRE1aOjB47M_VhpDcIvMP2Ns42cg9E9UHRH_52oNX5bCPgE-YHOPvHsPEm01wT6YEitPMgtr09aJA&aep=1&ntc=1&sa=X&ved=2ahUKEwiMovWp08GTAxXiMlkFHbiKAIkQ2J8OegQICxAE&biw=2271&bih=1241&dpr=1.5&mstk=AUtExfATmpeVSSotq0480GPXhmIAcWCJuOIpV3_wIi71BVsb1d9GbH2qW8PJX-zFYmW4ArQAcMkEcNct3NOexqxsHoyN5OhLrr860DDO-j7RcXwwDKiMa54OQFMmHLIi18wYYE1-q_GKVj1nDMp9OGG4juHCynNS8DzfZ6goEYvfg_PWMnyLIaNqSmiX72RyVLQC7ngsQdHzDMexMdt3vAbW_Pu2gD8fmQXZixlOUjwVy-pCGcAKp0OUJg_tNrPB34OcPh-raUhsXaKHuW9jYCfclJRbq6CidiCmHgF8Y0V3l5AF0VAxLX_BNJ_ts9v5AbbyFuWDiqfPNNfuxQ&csuir=1&mtid=-0rHaZT5LdLX5NoPnYenwQw&udm=50#sv=CBASgAMK_QIKCNrZ29IPAggBEvACCgwKCrrZ29IPBCABOAMKigEKhwHC2dvSD4ABen4iG3NnZV8tMHJIYWQzV0k2YWY1Tm9QZzRXWC1BbzABYNepwwJqA0FJTXJGQiYKE2ZlZWRiYWNrX2VudHJ5cG9pbnQSD3NnZV9tc2FmX2FjdGlvbqoBDE1BR0lfRkVBVFVSRbIBDAoAEgRCTFVSGAAgAKABhwHgAQHoAQH4AQEK0gEKzwHK2dvSD8gBEqABIp0BL3NlYXJjaC9hYm91dC10aGlzLXJlc3VsdD9vcmlnaW49d3d3Lmdvb2dsZS5jb20mcmVxPUNnQVNNd29uQ2dJSWNRb2hDRjFpSFFvTVkyOTFiblJ5ZVY5dVlXMWxFZzFWYm1sMFpXUWdVM1JoZEdWekVnUUtBZ2hsR2dJSUFCb0FJZ0lRQVVnQVdBQm9BQSZobD1lbi1VUyZnbD1VUxoWaHR0cHM6Ly93d3cuZ29vZ2xlLmNvbVoAYAFoAHAAeACAAQEg58rRzQxKCBACGAEgASgB"
author:
published:
created: 2026-03-27
description:
tags:
  - "clippings"
---
best community plugin for displaying google docs and word docs in obsidian

To display Google Docs and Microsoft Word files within Obsidian, the "best" plugin depends on whether you want to

**embed** the live document or **convert** it into Markdown for native editing.

**1\. Best for Microsoft Word (.docx)**

For Word documents, the most streamlined community plugin is **[Docxer](https://www.obsidianstats.com/plugins/docxer)**.

- **What it does:** Allows you to preview `.docx` files directly inside Obsidian instead of just seeing a file link.
- **Key Feature:** It includes a "Convert" button that transforms the Word doc into a standard Obsidian Markdown note with one click.
- **Alternative:** For advanced users, the **[Obsidian Pandoc](https://forum.obsidian.md/t/integrating-microsoft-office-documents/32055)** plugin is the gold standard for high-fidelity conversion between Word and Markdown, though it requires installing the Pandoc software on your computer first.

**2\. Best for Google Docs**

There is no single "one-click" plugin that renders a fully editable Google Doc natively as if it were a local note, but you can achieve this using two methods:

- **Live Embedding (No Plugin Needed):** Use a standard HTML `<iframe>`. In Google Docs, go to *File > Share > Publish to web*, copy the link, and paste it into your Obsidian note like this:  
	`<iframe src="YOUR_LINK_HERE" width="100%" height="500px"></iframe>`
- **Google Drive Sync:** The **Google Drive Sync** plugin by Richard Xiang (updated for 2026) is the best for keeping your Google Drive and Obsidian vault in parity, though it focuses more on file synchronization than live inline editing of `.gdoc` files.

**3\. Comparison of Methods**

<table><tbody><tr><th colspan="undefined">Goal</th><th colspan="undefined">Recommended Tool</th><th colspan="undefined">Benefit</th></tr><tr><td colspan="undefined"><strong>View Word Docs</strong></td><td colspan="undefined"><strong><a href="https://github.com/Developer-Mike/obsidian-docxer">Docxer</a></strong></td><td colspan="undefined">Simple inline preview and easy conversion.</td></tr><tr><td colspan="undefined"><strong>Convert Word to MD</strong></td><td colspan="undefined"><strong>Pandoc Plugin</strong></td><td colspan="undefined">Most accurate formatting for complex documents.</td></tr><tr><td colspan="undefined"><strong>Embed Google Docs</strong></td><td colspan="undefined"><strong>Standard <code><iframe></code></strong></td><td colspan="undefined">Provides a live, scrollable view of the cloud doc.</td></tr><tr><td colspan="undefined"><strong>Sync with G-Drive</strong></td><td colspan="undefined"><strong>Google Drive Sync</strong></td><td colspan="undefined">Best for cross-platform access and backup.</td></tr></tbody></table>

**Pro Tip:** To even see these files in your sidebar, ensure you have enabled **"Detect all file extensions"** in Obsidian Settings under *Files & Links*.