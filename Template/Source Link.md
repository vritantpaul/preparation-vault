<%*
const url = await navigator.clipboard.readText();

// Get selected text
let text = tp.file.selection() || "text";

// Remove Obsidian wiki-link brackets [[ ]]
text = text.replace(/^\[\[|\]\]$/g, "");

// Also handle cases like [[file|alias]]
if (text.includes("|")) {
  text = text.split("|")[1];
}

tR = `<a href="${url}">${text}</a>`;
-%>
