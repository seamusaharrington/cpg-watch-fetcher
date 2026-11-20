# CPG Watch fetcher

Downloads the full text of every Royal Children's Hospital Clinical Practice Guideline
(https://www.rch.org.au/clinicalguide/) once a week and saves it to `latest/bundle.json`.
The CPG Watch weekly check reads that file through the GitHub API, so it gets the real page
text even though its own cloud network cannot reach rch.org.au.

- Runs every Monday at about 5:05 am Melbourne time (Sunday 18:05 UTC), before the 6:46 am check.
- Can be run by hand: Actions tab → "Fetch RCH CPG pages" → Run workflow.
- `fetch_rch.py` uses only the Python standard library. Text extraction is `tools/pagecheck.py`
  (the same code the tracker uses), so page hashes stay comparable between runs.
- `extra_urls.txt` lists retired guideline URLs that are still probed each week.

Independent tracker, not produced or endorsed by the Royal Children's Hospital.
Keep this repository private: it holds copies of RCH page text.
