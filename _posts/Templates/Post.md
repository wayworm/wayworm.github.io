---
creation date: <% tp.file.creation_date() %>
modification date: <% tp.file.last_modified_date("dddd Do MMMM YYYY HH:mm:ss") %>
math: true
categories: [dev-journal, project-notes, how-to, meta, tools-I-like]
tags: 
---
<%*
const date = tp.date.now("YYYY-MM-DD");
const rawTitle = tp.file.title;
const hyphenatedTitle = rawTitle.trim().replace(/\s+/g, "-");
const newTitle = `${date}-${hyphenatedTitle}`;
await tp.file.rename(newTitle);
%>


**Technologies:** _e.g. Python, Flask, PostgreSQL_  
**Role:** _e.g. Developer, Researcher_

---

## Project Summary

A short description of what the project is and what it does. Aim for one or two clear sentences.

---

## Why I Built This

What prompted this project? Was it a personal need, a curiosity, a challenge, or something else?

---

## Process and Decisions

Walk through your approach. What were the key decisions you made and why? Mention any trade-offs or interesting ideas you explored.

---

## Tools and Stack

A concise list of the major tools, frameworks, or platforms used, with optional notes on why you chose them.

---

## Key Features or Highlights

Pick a few things that worked particularly well, or parts you're proud of. This is a good place to show your thinking.

---

## What I Learned

Any takeaways, insights, or things you’d approach differently next time.

---

## Links and References

- [GitHub Repo](#)  
- [Live Site / Demo](#)  
- [Docs or Related Posts](#) _(optional)_