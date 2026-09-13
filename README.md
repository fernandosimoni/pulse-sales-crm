# PulseSales — Sales CRM

[Português](README.pt-BR.md)

A portfolio project by [Fernando Simoni](https://github.com/fernandosimoni), built with AI assistance to demonstrate sales pipeline organization, lead handling and commercial metrics. All sample records are fictional. The application interface is in Brazilian Portuguese; monetary values use BRL.

## Business use case

Track opportunities from initial contact to closure, identify open pipeline value and estimate potential revenue using explicit stage probabilities. Import an existing lead list instead of retyping contacts.

## Features

- Six stages: New lead, Contact, Proposal, Negotiation, Won and Lost.
- Create and edit contact, company, email, phone, deal value, owner, next contact date and notes.
- Board and table views, contact search and owner filters.
- CSV import with column mapping; full portfolio export.
- Open pipeline, weighted forecast, win rate and average won deal size.
- Responsive layout, labeled controls and native dialogs.

## Metric definitions

| Metric | Calculation |
| --- | --- |
| Open pipeline | Sum of values in the four open stages |
| Weighted forecast | Open deal value × stage probability: 10%, 25%, 50%, 75% |
| Win rate | Won deals ÷ (won + lost deals) |
| Average deal size | Total won value ÷ number of won deals |

Metrics cover the entire portfolio, independent of search and owner filters. Undefined ratios show “—”. Forecast probabilities are illustrative assumptions, not an AI prediction or guaranteed revenue.

## Try it

[Hosted PulseSales](https://pulse-sales-crm.fernandosimoniuk.chatgpt.site) is currently restricted to the owner's account. Reviewers can run the repository locally.

Requires Python 3 and a modern browser:

```bash
git clone https://github.com/fernandosimoni/pulse-sales-crm.git
cd pulse-sales-crm
python -m http.server 8000 --directory dist
```

Open http://localhost:8000. No installation or external JavaScript dependencies are required.

### Suggested walkthrough

1. Click an opportunity, change its stage and save.
2. Observe changes to the pipeline, forecast and closed-deal metrics.
3. Switch between the board and table and filter by owner.
4. Export a CSV, import it again and map its columns.

## CSV behavior

Supports comma, semicolon or tab delimiters, UTF-8 and Windows-1252, up to 5 MB and 10,000 rows. Name is required. Other fields are optional; unmapped columns are not retained. Import replaces the current session's portfolio.

Unknown stages become New lead; absent or invalid values become zero. Invalid dates become empty. Rows without names are skipped and counted. Review imported values and stages before using metrics. Stage values are recognized by their Portuguese labels.

Export uses UTF-8 with BOM, quoted fields and spreadsheet-formula protection. This protection may prefix an apostrophe to text beginning with a formula character, including + in phone numbers.

## Privacy and limitations

Records stay in page memory only. There is no database, persistent storage, multi-user synchronization or audit history. Export before closing or refreshing, then import to resume. Imported contacts are not uploaded to a server or included in this repository.

The project demonstrates a workflow and metric logic; it does not claim real business results or production CRM readiness.

## Stack

HTML5 · CSS3 · JavaScript
