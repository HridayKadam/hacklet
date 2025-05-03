# 🖍️ Notelet – Instant Text Highlighter & Note Taker (Bookmarklet)

**Notelet** is a minimal yet powerful bookmarklet that lets you highlight any text on any website, tag it instantly, and save it for later reference — all without any extension or extra tools.

## 🔧 How It Works

1. Add the bookmarklet to your bookmarks bar.
2. Click it → you'll see: “Notelet active – select text to tag.”
3. Select any text on a webpage.
4. A prompt asks for a tag (e.g., "important", "idea", "todo").
5. It saves the highlight and tag to your browser’s `localStorage`.

## 💡 Why Use This?

- Instantly take notes while reading online
- Organize highlights with custom tags
- No accounts, no syncing, no extensions — just one click

## 📥 Installation

1. Create a new bookmark.
2. Set the URL to the following code (no newlines):

```javascript
javascript:(function(){document.addEventListener("mouseup",function(){const t=window.getSelection().toString().trim();if(t){const g=prompt("Add a tag for this highlight:","note");if(g!==null){const n=JSON.parse(localStorage.getItem("notelet")||"[]");n.push({text:t,tag:g});localStorage.setItem("notelet",JSON.stringify(n));alert(`Saved: "${t}" [${g}]`)}}});alert("Notelet active – select text to tag.");})();
