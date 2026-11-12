---
tags:
  - DailyCA
---
> <%*
const title = tp.file.title.replace("GA - ", "");
const currentDate = moment(title, "Do MMMM YYYY", true);

if (!currentDate.isValid()) {
    tR += "Invalid date in filename!";
} else {
    const previousDate = currentDate.clone().subtract(1, "day");
    const nextDate = currentDate.clone().add(1, "day");

    tR += `[[GA - ${previousDate.format("Do MMMM YYYY")}|⏪]] | [[GA - ${nextDate.format("Do MMMM YYYY")}|⏩]]`;
}
%>
> <u>File Link</u>: