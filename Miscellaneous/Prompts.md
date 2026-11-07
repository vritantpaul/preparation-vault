# For Affairs Cloud

# Basic ++

```markdown
Act as an expert Anki card creator for Current Affairs. Your goal is to convert the provided text into an exhaustive set of Anki cards.

Follow these strict rules:
1. Format: Provide the final output as a two-column .txt file. Output should be in code block for easy copying.
2. Separator: Use a pipe (|) to separate the "front" and "back" columns. Use only one pipe per line.
3. Limit: The preferred number of card is 20 with an upper limit of 30. Try not to touch the upper limit unless the provided content it too big to cover in less cards.
4. Minimum Information Principle (MIP):  Each card must be atomic. If a sentence contains multiple pieces of information (e.g., a date, a location, and a name), create separate cards for each rather than one long, information-heavy card.
5. Exception: There are two cases where you might not follow MIP:
	- When doing so will lead to loss of context. This usually happens in the case of lists (sets).
	- When following MIP will exceed the card limit. In that case, merge "easily digestible" facts into one card. For example, you can combine the date and place of an event.
6. Exhaustiveness: Ensure every single detail from the source (dates, amounts, locations, specific ministries, and names) is included in the cards.
7. To Avoid: Every card should be self-contained. Therefore, don't do anything that would obscure the information. For instance, "When are the NHIS and ASISSE surveys scheduled to start?". This is an example of a poorly formulated question as "NHIS" and "ASISSE" are abbreviations which makes this card depend on other cards (which contain the expanded form of the abbreviations). 

HTML Styling (Must Adhere):
1. Use <b>text</b> tags to bold key terms in the front (and not in the back).
2. Use <br> for any necessary line breaks (e.g., when listing multiple items).

Structure:
- Column 1 (Front): A concise question or "fill-in-the-blank" statement.
- Column 2 (Back): The specific answer.
  
CRITICAL: Double-check that every front-side question contains <b> tags around the key term. If a card does not have bolding on the front, it is a failure of the format.
```

## Cloze

### Original

```markdown
You are a question setter for the General Awareness section of Phase 1 of the RBI Grade B exam. Your goal is to convert the provided text into an exhaustive set of Anki cards which are relevant from the POV of the exam.

> NOTE: Keep in mind the difference between an Anki card and a note. An Anki note can contain multiple Anki cards.

Follow these rules:
1. Type: You will create cloze deletion cards with preferably one cloze deletion per note with an upper cap of 3 cloze deletions per note. 
2. Minimum Information Principle (MIP):  Each card must be atomic. If a sentence contains multiple pieces of information (e.g., a date, a location, and a name), create separate cards for each rather than one long, information-heavy card.
3. Exhaustiveness: Ensure every single detail from the source (dates, amounts, locations, specific ministries, and names) is included in the cards.
4. Limit: Keep the number of Anki cards to a minimum (preferably within 30). If following MIP results in too many cards, in that case, merge "easily digestible" facts into one card. For example, you can combine the date and place of an event.
5. Links: IGNORE ANY OBSIDIAN STYLE LINKS in the format: [[link|text]]. 
   
Format: There are two types of format you can use:
6. BASIC: Create cloze deletion cards like the Basic note type of Anki. For instance,
Question?<br><br>{{c1::Answer.}}
Prefer this formatting style if the note contain only one card. 

7. FILL-IN-THE-BLANK: Multiple cloze deletion cards in one note. For instance,
This is a {{c1::passage}} that contains some {{c2::text}}.
Prefer this formatting style if the note contain multiple cards.

> NOTE: Prefer (1) over (2) most of the time. Use (2) whenever two or more cards operate under the same context and creating separate cards becomes inefficient.

HTML Styling (Must Adhere):
1. Use <b>text</b> tags to bold key terms. No need to bold text which is already in cloze deletion
2. Use <br> for any necessary line breaks (e.g., when listing multiple items) or for BASIC formatting style.
   
Output: Output as a .txt file where each line is one note.
```

### Claude Updated

```markdown
You are a question setter for the General Awareness section of Phase 1 of the RBI Grade B exam. Your goal is to convert the provided text into a compact, high-yield set of Anki cloze cards that cover the exam-relevant facts in the source.

> DEFINITIONS: A NOTE is one line of output. A CARD is one distinct cloze number inside a note ({{c1::...}}, {{c2::...}}). Reusing the same number for several blanks in one note (e.g., two {{c1::...}}) still makes ONE card, with all those blanks hidden together.

PROCESS (follow in order):
1. Read the whole source and group the facts by topic: same event, scheme, institution, report, committee, person, or list. 
2. Create ONE note per group. All related facts go into that note.
3. Count the cards. If the total exceeds 30, merge the least important groups or leave minor details visible as context. Then output.

RULES:
1. HARD LIMIT: Maximum 30 cards in total across all notes. This is a ceiling, not a target; short sources should produce far fewer cards. Never exceed it, even if that means merging facts.
2. ATOMIC = ONE COHERENT IDEA, NOT ONE DATUM. Facts that naturally belong together are one idea and must stay together on one card. Examples of facts to combine: date + place of an event; name + designation; scheme + ministry + launch year; the members of a short list; a body + its headquarters. Split into separate cards only when the facts are unrelated, or when combining them would make the card too long or confusing to recall (e.g., a list of more than 4 items, or several unrelated numbers).
3. CLOZE LIMITS: Use at most 3 cloze numbers (c1, c2, c3) per note. Prefer one or two. You may hide more than one span under the same number if they should be recalled together.
4. EXAM-RELEVANT COVERAGE: Include every exam-relevant fact (names, dates, amounts, targets, locations, ministries, institutions, rankings, abbreviations, key numbers). A fact that is relevant but minor should stay in the note as visible context (not clozed) rather than getting its own card. Skip pure narrative, filler, opinions, and generic background that cannot be asked as a question.
5. LINKS: IGNORE ANY OBSIDIAN-STYLE LINKS in the format [[link|text]]. Use only the display text, without link syntax.

FORMAT (choose per note):
1. FILL-IN-THE-BLANK (default for related facts): one sentence or short passage with one or more cloze numbers.
   Example: The {{c1::Scheme Alpha}} was launched in {{c2::2024}} by the {{c2::Ministry of Finance}}.
   Use this whenever two or more facts share the same subject or context.
2. BASIC (only for a genuinely standalone single fact): a question followed by the answer in a cloze.
   Example: Which ministry administers Scheme Alpha?<br><br>{{c1::Ministry of Finance}}

BAD vs GOOD (illustrative, fictional facts):
Source: "Scheme Alpha was launched in Mumbai on 5 March 2024 by the Ministry of Finance."
BAD (3 notes, 3 cards for one event):
 - Where was Scheme Alpha launched?<br><br>{{c1::Mumbai}}
 - When was Scheme Alpha launched?<br><br>{{c1::5 March 2024}}
 - Which ministry launched Scheme Alpha?<br><br>{{c1::Ministry of Finance}}
GOOD (1 note, 2 cards):
 - <b>Scheme Alpha</b> was launched in {{c1::Mumbai}} on {{c2::5 March 2024}} by the {{c2::Ministry of Finance}}.

HTML STYLING (must adhere):
1. Use <b>text</b> to bold key terms. Do not bold text that is already inside a cloze deletion.
2. Use <br> for line breaks (e.g., listing items, or separating question and answer in BASIC format).

SELF-CHECK BEFORE OUTPUT:
- Total cards (distinct cloze numbers across all notes) is 30 or fewer.
- No two notes cover the same topic; related facts are grouped.
- No note exists only to test a date, place, or name that belongs to another note's topic.
- Every note has at most 3 cloze numbers.

OUTPUT: Output as a .txt file where each line is one note. No numbering, headings, or commentary.
```
# For Finance Current Affairs 
 

```
Act as an expert Anki card creator for Finance Current Affairs. Your goal is to convert the provided text into an exhaustive set of Anki cards.

Follow These Strict Rules:
1. Format: Provide the final output as a three-column .txt file. Output should be in code block for easy copying.
2. Separator: Use a pipe (|) to separate the "front", "back" and "footnotes" columns. Use only one pipe per line.
3. Limit: The maximum number of cards should not exceed 30.
4. Minimum Information Principle (MIP): Each card must be atomic. If a sentence contains multiple pieces of information (e.g., a date, a location, and a name), create separate cards for each rather than one long, information-heavy card.
5. Handling Loss of Context: If a card is concept heavy, and will lead to loss of context if MIP is followed. You can add a footnote. The footnote must not be important enough that it requires its own card. The purpose of a footnote is to add context. That's why YOU DON'T HAVE TO ADD A FOOTNOTE FOR EVERY CARD, especially fact-heavy cards.
6. Exception: There are two cases where you might not follow MIP:
	- When doing so will lead to loss of context. This usually happens in the case of lists (sets).
	- When following MIP will exceed the card limit. In that case, merge "easily digestible" facts into one card. For example, you can combine the date and place of an event.
   
Example for Explaining Point 5 and 6:
Front: What are the supply side impediments to financial inclusion?
Back: 

1. Restricted range of services at BC outlets → uneven access.
2. Lack of prescribed minimum standards → poor standardisation and monitoring.
3. Non-transparent fees and unauthorized charges.*
4. Low representation of women BC agents → reduced outreach and inclusivity.

Footnote: * Most BCs did not display service fees, and concerns existed about unauthorized or unaccounted upfront charges in addition to bank-built transaction charges.

Notice that asterisk. If you are adding a footnote, you are to put an asterisk on the point or keyword you are expanding on.

7. Exhaustiveness: Ensure every single detail from the source (dates, amounts, locations, and names) is included in the cards.
8. Paraphrasing: If the content is verbose, for instance, a definition, you have to paraphrase, simplify, and shorten it for easy retention, instead of just copy-pasting. Make sure the reworded version does not compromise the essence of the content.
9. To Avoid: Every card should be self-contained. Therefore, don't do anything that would obscure the information. For instance, "When are the NHIS and ASISSE surveys scheduled to start?". This is an example of a poorly formulated question as "NHIS" and "ASISSE" are abbreviations which makes this card depend on other cards (which contain the expanded form of the abbreviations). 

HTML Styling (Must Adhere):
1. Use <b>text</b> tags to bold key terms in the front (and not in the back).
2. Use <br> for any necessary line breaks (e.g., when listing multiple items).
3. For lists, enclose every item of the list with <li>item</li>.
4. For ordered list, enclose the entire list in <ol>list<ol>.
5. For unordered list, enclose the entire list in <ul>list</ul>.

Structure:
- Column 1 (Front): A concise question or "fill-in-the-blank" statement.
- Column 2 (Back): The specific answer.
- Column 3 (Footnote): Optional. Adding context by expanding on a particular keyword or list. 

<front> | <back> | <footnote>

Example:
Final output of the above card will look like:
What are the top three impediments which accounts for the inability to get credit in the household segment? | <ol><li>Lack of awareness about the procedure</li><li>Unavailability of the nearby bank branch</li><li>Lack of collateral</li></ol> | Most BCs did not display service fees, and concerns existed about unauthorized or unaccounted upfront charges in addition to bank-built transaction charges.

Another Example (Fill-in-the-Blank Type):
India has solidified its position as the global leader in real-time digital payments by processing nearly ____ of all global real-time payments.| 50% | 

CRITICAL: Double-check that every front-side question contains <b> tags around the key term. If a card does not have bolding on the front, it is a failure of the format.
```

# For Generating Definitions

```
Define the following terms in a precise and specific manner.  
Limit each definition to 1–2 sentences.  
Include defining characteristics (how it works, key feature, or use-case).  
Avoid general or textbook-style vague wording.  
Format as a numbered list.

Terms:  
```

# For Category Wise Mapping of GA Questions

```
The GA file consists of general awareness questions asked in the RBI Grade B examination for the past 6 years, while the AC Content Page consists of broad topic wise classification of questions. I want you to map each question to its respective category and tell me how many questions are asked from each category each year. Make a table. And if there are no questions asked from a certain category skip it. The first column should contain the categories from the AC Content Page file and the rest should contain years.
```