# Portal Agent

## Purpose

Weekly portal health check for bank/foundation/government/transparency.

## Inputs

- **Base URL**: `https://ttony106-source.github.io/kamakazi-partner-portal`
- **Required paths**:
  - `bank/`
  - `foundation/`
  - `government/`
  - `transparency/`
- **Required PDFs**:
  - `bank/CRA_Package_v1.pdf`
  - `bank/Renewal_Deck_v1.pdf`
  - `foundation/Foundation_Pack_v1.pdf`
  - `foundation/Use_of_Funds_v1.pdf`
  - `government/PRM_Brief_v1.pdf`
  - `government/City_County_Pack_v1.pdf`
- **Schedule**: Cron `0 14 * * 1` (Mondays 14:00 UTC)

## Outputs

GitHub Issue titled:
```
Portal Agent Report — <date> — <status>
```

Where `<status>` is one of:
- `✅ ALL OK` - All portals and required PDFs returned HTTP 200
- `⚠️ ACTION NEEDED` - One or more required files/pages failed

Issue body contains:
- Success: "All portals and required PDFs returned HTTP 200."
- Failure: List of failed files/pages with HTTP status codes

## Escalation

If status is `⚠️ ACTION NEEDED` two weeks in a row, create a P1 task in ops board.

_(Escalation workflow to be implemented in future iteration)_
