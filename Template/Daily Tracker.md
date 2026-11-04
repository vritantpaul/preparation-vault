> <%*  
const baseDate = moment(tp.file.title, "Do MMMM YYYY");

const yesterday = baseDate.clone().subtract(1, "day").format("Do MMMM YYYY");
const tomorrow = baseDate.clone().add(1, "day").format("Do MMMM YYYY");

tR += `[[${yesterday}|⏮️]] | [[${tomorrow}|⏭️]]`;
%>

# Daily Targets 🎯

- [ ] Affairs Cloud Previous Day PDF (Read  & Highlight)
- [ ] Product Constancy
- [ ] Macroeconomics Deck
- [ ] General Awareness Deck
- [ ] One Scheme

<center>***</center>

> 📆Weekly PIB: [[(PIB) <% tp.date.now("MMMM") %> Week <% tp.date.now("W") %>]]
> 🗓️Daily Affairs Cloud: <%*  
const fileDate = moment(tp.file.title, "Do MMMM YYYY");  
const newFileName = `(AC) ${fileDate.subtract(1, "day").format("Do MMMM YYYY")}`;  
tR += `[[${newFileName}]]`;  
%>

---
# Newspaper Articles

- [ ] 

---

# Today's Agenda

- [ ] Today's Scheme: 

---
