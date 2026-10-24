# Earned Event Speaker Opportunity Scout

A tiny, open-source tool for B2B tech companies that want to win **earned** (non-paid) conference speaking slots. It does two things:

1. **Generates a reusable research brief** from your company profile: expertise, target audience, geography, speaker bios, and exclusions. Paste the brief into any AI assistant with web search (ChatGPT, Claude, Perplexity) or hand it to a researcher. The brief asks for results in a CSV format you can import straight back into the tracker.
2. **Tracks CFP opportunities** in a simple table: event, dates and location, CFP deadline (with overdue and due-soon highlighting), fit, source link, submission status, and notes.

No account, no API key, no backend. Everything is a single HTML file. Your data is saved in your browser's localStorage and can be exported or imported as CSV at any time.

## Run it locally

No build step. Pick one:

**Option 1: just open the file**

```
open index.html          # macOS
start index.html         # Windows
xdg-open index.html      # Linux
```

Or double-click `index.html` in your file manager.

**Option 2: serve it (optional)**

```
python3 -m http.server 8000
# then visit http://localhost:8000
```

Serving it keeps localStorage tied to `localhost` instead of the file path, which is slightly more stable if you move the file around.

## How to use it

1. Fill in the **Company profile**: expertise/domain, target audience (personas, users vs. decision makers, account type and size), event geography, speaker bios, and exclusions (for example: no pay-to-play slots, no webinars, no competitor-run events). The profile saves automatically as you type.
2. Click **Generate research brief**, then copy it or download it as Markdown. Re-run it monthly or quarterly; the brief is built to be reused.
3. Run the brief through your AI assistant of choice. Ask it to verify every deadline on the organizer's own CFP page; the brief includes this rule.
4. Paste or import the results into the **CFP opportunity tracker**. The research brief requests a CSV block with the exact header the importer expects:

   ```csv
   Event,Event Date & Location,CFP Deadline,Fit,Source URL,Status,Notes
   ```

   Save that block as a `.csv` file and use **Import CSV**. Or add rows by hand.
5. Update the **Status** column as you go: Watching, Drafting, Submitted, Accepted, Rejected, Closed. Deadlines within 14 days are flagged amber; passed deadlines are flagged red.
6. **Export CSV** any time for a backup or to share the pipeline with your team.

Click **Load sample (fictional company)** to see a filled-in example. The sample company, speakers, and events are all made up.

## Data and privacy

All data stays in your browser (localStorage). Nothing is sent anywhere. Clearing your browser data clears the tracker, so export a CSV backup periodically. Data is also scoped per browser and per machine; the CSV export/import is how you move it.

## Contributing

It's one HTML file by design. Bug fixes and small, dependency-free improvements are welcome. Please keep it working offline with no accounts, keys, or build tooling.

## License

[MIT](LICENSE)
