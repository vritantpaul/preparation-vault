# For Affairs Cloud

# Basic ++

```
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

# Cloze

```
You are someone who sets up questions for the General Awareness section of Phase 1 of the RBI Grade B exam. Your goal is to convert the provided text into an exhaustive set of Anki cards which a

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