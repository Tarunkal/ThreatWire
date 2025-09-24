# ThreatWire

# Objective 
This project automates the process of reading cybersecurity news, summarizing articles, and sending them via email to recipients using n8n. The workflow integrates RSS feeds, an LLM (Google Gemini), and email delivery to provide concise daily updates.
The goal is to build a streamlined cybersecurity news pipeline that reduces noise, saves time, and ensures stakeholders stay informed about critical threats and incidents.

# Step-by-Step Methodology
1. Trigger Setup
    - Workflow starts with a manual trigger # (Execute Workflow) to control execution.

2. RSS Feed Integration
    - An RSS Read node fetches the latest articles from trusted cybersecurity sources (e.g., KrebsOnSecurity).
    - Articles are collected as JSON objects containing title, link, publication date, and full content.

3. Item Limiting
     - A Limit node ensures only the top article(s) are processed (default: 1).
     - Prevents email overload and keeps summaries concise.

4. Summarization
   - The Summarization Chain node breaks down article content into manageable chunks.
   - Google Gemini Chat Model is used as the LLM to generate clean and professional summaries.

5. Email Delivery
    - The final summary is sent using a Gmail Send Message node.

**Email includes**:
  - Title of the article
  - Original article link
  - Summarized key points
  - Risk & Recommendations

  # Tools and Technology Used 

 - n8n – Workflow automation platform
 - RSS Feed – News source integration
 - Google Gemini Chat Model – Summarization and text processing
 - Gmail – Email delivery service

 # How to set up the Workflow 
 **📩 Email Summary Example**

- Title: Self-Replicating Worm Hits 180+ Software Packages
- Link: KrebsOnSecurity Article
- Summary: Key points of the malware attack, spread method, affected vendors, and recommendations.
- Risk & Recommendations: Highlights supply chain risks and best practices.

# 🚀 Future Enhancements
 
 **Planned improvements to expand cybersecurity functionality:**

- VirusTotal Integration – Automatically scan URLs, IPs, or file hashes found in news articles for malware indicators.
- Hybrid Analysis Integration – Extract and enrich threat intelligence from malware samples and suspicious files.
- ELK Stack (Elasticsearch, Logstash, Kibana) – Store and visualize alerts/summaries for historical analysis and real-time monitoring.
- Scheduled Daily Runs – Automate execution on a fixed schedule (e.g., every morning).
- Multi-channel Notifications – Extend reporting to Slack/Discord for team alerts.
- Threat Intelligence Database – Build a repository of all summarized articles with enrichment data for later reference.

<img width="1774" height="788" alt="Image" src="https://github.com/user-attachments/assets/c4fbf46a-1688-4c29-81c0-418dde58c60a" />
 Fig 1. Main Workflow

<img width="1878" height="856" alt="Image" src="https://github.com/user-attachments/assets/933da08b-1a1c-4c38-ada0-06bbf17b67c2" />
 Fig 2. RSS Read 

<img width="1884" height="912" alt="Image" src="https://github.com/user-attachments/assets/1827baae-c23f-45d7-89ad-556f6bbb181b" />
Fig 3. Summarization Chain 

<img width="1530" height="748" alt="Image" src="https://github.com/user-attachments/assets/a69f04fa-4d4f-44c1-83f8-a2a7d9bd63cc" />
Fig 4. Email Sample 
