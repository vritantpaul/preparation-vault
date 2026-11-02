---
tags:
  - Scheme
  - ObsidianToAnki
---
TARGET DECK: Schemes

<%*
// 1. Safety check for QuickAdd
if (!app.plugins.plugins.quickadd) {
    new Notice("QuickAdd plugin is required for the checklist feature.");
    return;
}

// 2. Grab the title of the current note to insert into the cards
const schemeName = tp.file.title;

// 3. Define the Anki card blocks with dynamic title insertion
const blocks = {
    "Launch Date": `START\nBasic++\nWhen was the <b>${schemeName}</b> scheme launched?\nBack: \nFootnotes:\nSource: [[${schemeName}.pdf]]\nReverse:\nTags: Schemes\nEND`,
    
    "Nodal Ministry": `START\nBasic++\nWhat is the nodal ministry of the <b>${schemeName}</b> scheme?\nBack: \nFootnotes:\nSource: [[${schemeName}.pdf]]\nReverse:\nTags: Schemes\nEND`,
    
    "Implementing Agency": `START\nBasic++\nWhat is the implementing agency of the <b>${schemeName}</b> scheme?\nBack: \nFootnotes:\nSource: [[${schemeName}.pdf]]\nReverse:\nTags: Schemes\nEND`,
    
    "Budgetary Outlay": `START\nBasic++\nWhat is the budgetary outlay of the <b>${schemeName}</b> scheme?\nBack: \nFootnotes:\nSource: [[${schemeName}.pdf]]\nReverse:\nTags: Schemes\nEND`,
    
    "Budgetary Split": `START\nBasic++\nWhat is the $Centre : State$ budgetary split of the <b>${schemeName}</b> scheme?\nBack: \nFootnotes:\nSource: [[${schemeName}.pdf]]\nReverse:\nTags: Schemes\nEND`,
    
    "Tenure": `START\nBasic++\nWhat is the tenure of the <b>${schemeName}</b> scheme?\nBack: \nFootnotes:\nSource: [[${schemeName}.pdf]]\nReverse:\nTags: Schemes\nEND`,
    
    "Eligibility": `START\nBasic++\nWhat are the eligibility criteria for the <b>${schemeName}</b> scheme?\nBack: \nFootnotes:\nSource: [[${schemeName}.pdf]]\nReverse:\nTags: Schemes\nEND`,
    
    "Tagline": `START\nBasic++\nWhat is the tagline of the <b>${schemeName}</b> scheme?\nBack: \nFootnotes:\nSource: [[${schemeName}.pdf]]\nReverse:\nTags: Schemes\nEND`,
    
    "Features": `START\nBasic++\nWhat are the features of the <b>${schemeName}</b> scheme?\nBack: \nFootnotes:\nSource: [[${schemeName}.pdf]]\nReverse:\nTags: Schemes\nEND`,
    
    "Objectives": `START\nBasic++\nWhat are the objectives of the <b>${schemeName}</b> scheme?\nBack: \nFootnotes:\nSource: [[${schemeName}.pdf]]\nReverse:\nTags: Schemes\nEND`
};

// 4. Extract the headings for the QuickAdd popup
const titles = Object.keys(blocks);

// 5. Trigger the checklist popup (defaults to all checked)
const selectedTitles = await app.plugins.plugins.quickadd.api.checkboxPrompt(titles, titles);

if (!selectedTitles) {
    new Notice("Template insertion cancelled.");
    return "";
}

// 6. Gather the selected text blocks and append "---" to EVERY single one
let result = "";
selectedTitles.forEach(title => {
    result += blocks[title] + "\n\n---\n\n";
});

// 7. Output the final result to the note
tR += result;
%>