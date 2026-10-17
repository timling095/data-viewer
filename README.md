# data-viewer

Code-only viewer pages for the team's benchmark packs, served with GitHub Pages:
https://timling095.github.io/data-viewer/

| path | pack | data read from |
|---|---|---|
| `pack1/` | Pack 1 | `Vincentllxz/Steerability-oooi`, `benchmark/pack_1/` (`viewer_data.json.gz`, `results/<source>/<dim>.jsonl.gz`) |

These pages hold no benchmark content. Each one fetches the pack's rows and results from the private repo through the
GitHub contents API, with a read-only token the viewer pastes once under 資料來源 (kept in that browser only).

## Updating

- New results (a steering run, a re-export): push them to the pack in the private repo. Nothing changes here.
- A new page version: rebuild in the team repo and copy the page here:

      python3 team/bench/ship_2/build_viewer.py --pages <path to this repo>

  then commit and push `pack1/index.html`.
- A new pack: add a folder with its page and a line on `index.html`.
