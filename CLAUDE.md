# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is the **Netlas CookBook** — an educational guide and practical reference for using [Netlas](https://netlas.io/) search tools for cybersecurity, OSINT, penetration testing, and digital forensics. It is published under CC0 1.0 Universal (public domain).

The repository is documentation-first: the primary artifact is `README.md`, supplemented by runnable example scripts and screenshots.

## Repository Structure

- `README.md` — Main documentation with table of contents, explanations, and embedded code examples
- `scripts/` — Runnable examples organized by security domain:
  - `osint/` — WHOIS, certificate analysis, FTP banners, web scraping
  - `pentest/` — CVE search, subdomain enumeration, SQL injection, favicon hash
  - `dfir/` — Malware search, SMTP banners, subnet search
  - `crypto/` — Mining farm detection, Bitcoin nodes, cryptominers
  - `darknet/` — Tor exit nodes, .onion site collection
  - `common_problems/` — CSV export, rate limiting, punycode handling
  - Root-level examples in Python, Bash, Node.js, and Ruby
- `images/` — Screenshots documenting each use case in the README

## Running Scripts

Scripts have no build system or package manager. To run a Python script:

```bash
pip install netlas
python scripts/osint/some_script.py
```

Most scripts require a Netlas API key, typically passed as an argument or set via environment variable. Check the script header or corresponding README section for usage.

## Content Conventions

- Each use case in README.md has a corresponding screenshot in `images/` and often a script in `scripts/`
- Code blocks in README use full-line fences (not inline backticks for multi-line code)
- Screenshots are PNG/JPEG named descriptively to match the use case
- Scripts follow a consistent pattern: initialize Netlas connection → query → parse and print JSON results

## Key Technologies

- **Netlas Python library** (`netlas`) — primary API client
- **Direct HTTP requests** — `requests` library with Netlas REST API
- **Data parsing** — `BeautifulSoup`, `regex`, `json`
- Language examples: Python (primary), Bash (cURL/jq), Node.js, Ruby
