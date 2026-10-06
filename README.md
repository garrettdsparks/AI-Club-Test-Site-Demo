# UConn AI Club website

The homepage has two direct AI chat links:

- `chat/` — full-viewport AI chat with a key sidebar, a large scrolling conversation area, and a bottom composer.
- `ai-would-you-rather/` — floating AI chat, opened automatically.

Both show the OpenRouter key field at the top. Paste your own key, click **Use / update key**, and send a theme. **Clear key / demo** or refreshing clears the key from page memory. Navigating to the other route also starts a new session. Never commit a key into the source.

Built-in chat replies need no key. The homepage links directly to both chat routes.

## Files

- `index.html` — homepage and direct chat links.
- `chat/index.html` and `ai-would-you-rather/index.html` — the two chat layouts.
- `assets/chat.js` — shared chat behavior and OpenRouter request.
- `assets/chat.css` — shared chat styling.
- `assets/markdown.js` — lightweight Markdown rendering: bold, emphasis, lists, headings, links, quotes and code. Raw HTML stays literal text. This is a common Markdown subset, not full CommonMark.

The existing GitHub **pages build and deployment** workflow publishes pushes. Keep **Settings → Pages → Deploy from a branch → main → /(root)**.

To add a route, create `my-page/index.html` and link to `my-page/` from the homepage. Use `../` to return home from a child page. Keep relative links for GitHub Pages repository paths.

The chatbot keeps conversation context in page memory. Follow-ups are normal chat, not a new game each time. **New chat** clears messages while keeping the session key. Refresh clears both. Prior messages are sent to OpenRouter for context; very long conversations prompt you to start a new chat.
