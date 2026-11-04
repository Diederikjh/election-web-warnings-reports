# Election website reports

Public report index: <https://diederikjh.github.io/election-web-warnings-reports/>.

This repository hosts multiple independent static reports. Each report lives in
its own top-level folder and keeps its HTML, JSON, CSV, screenshots, and merged
assets together. Publishing or updating one folder preserves every other report.

| Report folder | Websites | Scan attempts | Public report |
| --- | ---: | ---: | --- |
| `2026-local-elections-first/` | 8 | 10 | [View report](https://diederikjh.github.io/election-web-warnings-reports/2026-local-elections-first/) |
| `2026-local-elections-voting-day/` | 8 | 27 | [View report](https://diederikjh.github.io/election-web-warnings-reports/2026-local-elections-voting-day/) |

## Repository structure

```text
index.html                 # Report index
README.md                  # This guide and report links
reports-index.json         # Machine-readable report catalog
.nojekyll                  # Serve generated files directly
.gitattributes             # Recognize standard CSV CRLF line endings
<report-path>/
  index.html
  results.json
  summary.csv
  screenshots/
  merged/                  # Supporting assets from merged scans, when present
```

GitHub Pages publishes the root of the `gh-pages-merged` branch. All links within an
individual report are relative to that report's folder.

## Add or update a report

Use the publishing helper from the scanner repository:
[Diederikjh/election-web-warnings](https://github.com/Diederikjh/election-web-warnings).
From that checkout, run:

```bash
bash scripts/publish-report.sh /path/to/local/report \
  --repository Diederikjh/election-web-warnings-reports \
  --branch gh-pages-merged \
  --path your-new-report-name
```

Choose a lowercase folder name containing letters, numbers, and hyphens. Reuse a
path to replace that report, or choose a new path to add a report. The command
refreshes the index and this README while retaining all other report folders
and Git history. It does not change the original scanner repository's Pages site.
