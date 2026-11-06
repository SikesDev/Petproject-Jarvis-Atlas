# Work and school ingestion

Private cloud pipeline with exactly two authoritative outputs: `filtered-canvas.ics` and `work-schedule.ics`. A checksummed manifest and durable input receipts describe each published snapshot.

Canvas rules exclude non-actionable calendar information and duplicates; task titles are retained, while ambiguous titles require model classification. The original Canvas account URL and Power Automate input contract remain supported.

Work schedules use the source-specific parser plus independent GitHub-hosted vision of the original document. LibreOffice makes Word rendering cloud-compatible. OpenAI is only a fallback for failures/disagreements. Downstream scheduling begins only after a healthy two-feed snapshot has been published.
