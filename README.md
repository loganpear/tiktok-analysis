# tiktok-analysis

A small end-to-end analysis project for my TikTok account **@humbletoker** (“Humble Tokker”). The goal is to turn my video content into structured data (metrics + transcripts), analyze what correlates with higher performance, and convert that into actionable content changes.

## What’s in here

- `notebooks/`
  - ``data-pipeline.ipynb`` — notebook for extracting and processing raw data.
  - ``transcript-analysis.ipynb`` — main notebook (analysis + results)
- `data/`
  - `derived/` - Processed data ready for analysis.
    - ``tiktok_manifest.csv``
    - ``tiktok_manifest_with_transcripts.csv``
    - ``tiktok_transcripts.csv``
    - ``transcript_analysis_ready.parquet``
  - `tiktok-studio-downloads/` - Raw data downloads (unused)
    - ``Content.csv``
    - ``profile_videos_counts.csv``
- `report/`
  - ``final-report.pdf`` — written summary of methods + takeaways

## Pipeline (high level)

1. Collect video-level metrics (views, likes, shares / rates, timestamps, etc.)
2. Download audio and transcribe with Whisper
3. Clean + merge into one table (CSV) with metrics + transcript features
4. Analyze:
   - template/format comparisons (e.g., “no one except” vs “everyone except”)
   - phrase-level signals from transcripts

## Key takeaways (current)

- The **“no one except”** format strongly outperforms **“everyone except”** in my dataset.
- The CTA phrase **“share plus more”** shows up heavily in top performers and not in bottom performers.
- **“birthday”** looks promising, but needs more samples to be confident.
