# News Article Summarizer (n8n Workflow)

![License](https://img.shields.io/github/license/Mintberry1628/news-article-summarizer-n8n)
![Languages](https://img.shields.io/github/languages/top/Mintberry1628/news-article-summarizer-n8n)
![Platform](https://img.shields.io/badge/platform-RaspberryPi-green)
![Last Commit](https://img.shields.io/github/last-commit/Mintberry1628/news-article-summarizer-n8n)


This project demonstrates how to automatically summarize new news articles or web content collected in Notion using n8n. Summaries are delivered directly to your Telegram account.


## Table of Contents

- [Folder Structure](#folder-structure)
- [Use Case](#use-case)
- [Workflow Overview](#workflow-overview)
- [Prerequisites](#prerequisites)
- [Setup & Configuration](#setup--configuration)
- [How it Works (Step by Step)](#how-it-works-step-by-step)
- [Screenshots](#screenshots)
- [Lessons Learned](#lessons-learned)
- [Findings](#findings)
- [Credits](#credits)

---

## Folder Structure

```
.
├── .gitignore
├── LICENSE
├── README.md
├── img/
│   ├── <workflow.png>
├── n8n/
│   └── News_Article_Summarizer.json
```

---

## Use Case

You want to receive regular, concise summaries of new articles, blogs, or news pieces that you save in a Notion database—without having to read each article in full.

---

## Workflow Overview

This n8n workflow:

- Triggers automatically when a new link is added to your Notion database.
- Extracts the URL and fetches the full article content using a web extraction API.
- Uses OpenAI to generate a summary of the article.
- Sends the summary to your Telegram account as a formatted message.

---

## Prerequisites

- A running n8n instance (Docker, cloud, self-hosted, etc.)
- A Notion integration and API key
- An OpenAI API key (or alternative summarization service)
- A Telegram bot token and chat ID

---

## Setup & Configuration

1. Clone or download this repository.
2. Import the News_Article_Summarizer.json file into your n8n instance.
3. Set up credentials in n8n:
 	- Notion API key and database ID
 	- OpenAI (or alternative) API key
 	- Telegram bot token and chat ID
4. Set your desired Notion database in the trigger node.
5. (Optional) Adjust prompt or summary length as needed.

---

## How it Works (Step by Step)

1. Trigger: The workflow starts automatically when a new link/page is added in Notion.
2. Extract URL: The workflow extracts the article URL from the Notion entry.
3. Fetch Article Content: The workflow calls a web extraction API to retrieve the full article text.
4. Summarization: The article is summarized by OpenAI or another LLM.
5. Telegram Notification: The summary is sent to your Telegram as a formatted message.

---

## Screenshots

![Workflow Overview](img/workflow.png)

*Full n8n workflow for summarizing news articles from Notion.*

---

## Lessons Learned

- Web extraction APIs may fail or not support paywalled content.
- Notion API triggers may be slightly delayed depending on plan and configuration.
- AI-generated summaries are highly dependent on the quality of the extracted text.
- Sending summaries via Telegram is efficient, but other outputs (email, Slack, Notion) are also possible.

---

## Findings

- n8n is highly flexible for building personal content pipelines and can integrate many data sources.
- This workflow can be extended for other content types (blog posts, newsletters, scientific articles, etc.).
- Prompt engineering can improve the quality of AI-generated summaries.

---

## Credits

- Workflow developed and documented by Mintberry1628.
- Powered by n8n, OpenAI, and Notion API.
- Inspired by the open automation and productivity community.

---

**For questions or suggestions, feel free to open an issue or contact me via GitHub.**
