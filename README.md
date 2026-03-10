# Java Web Crawler

This project implements a **multithreaded web crawler in Java**.  
It demonstrates several important backend engineering concepts including:

- Web crawling fundamentals
- HTTP requests
- HTML parsing
- Recursion
- Graph traversal
- Multithreading
- Maven dependency management
- Basic crawler architecture

The crawler starts from a **seed URL**, downloads the page, extracts links, and recursively visits those links up to a fixed depth.

---

# 1. How Web Crawlers Work

A **web crawler** (also known as a spider or bot) is a program that automatically browses web pages and discovers links.

Search engines use crawlers to build indexes of the internet.

Typical workflow:

1. Start with a **seed URL**
2. Download the page
3. Extract links
4. Visit the discovered links
5. Repeat the process

Example crawl tree:

Start: https://abcnews.com

├── link1
│     ├── link1.1
│     └── link1.2
├── link2
│     ├── link2.1
│     └── link2.2

This crawler implements a depth-limited recursive crawl.

2. High Level Architecture

The system contains three main parts:

                Main.java
                    │
                    │ creates
                    ▼
           WebCrawler instances
                    │
                    │ starts
                    ▼
             Thread execution
                    │
                    │ runs
                    ▼
                 crawl()
                    │
                    │ downloads pages
                    ▼
                request()
                    │
                    │ parses HTML
                    ▼
                 Jsoup

Three crawlers run simultaneously on different news websites.