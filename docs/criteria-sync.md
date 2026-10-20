# Keeping criteria in sync with Green DiSC

`criteria.yml` lists the Green DiSC criteria for your track: one entry per criterion with its ID, title and category, for every tier. It's a reference copy that shows when Green DiSC changes its criteria. It is generated, so don't edit it by hand.

## How it works

The **Sync Green DiSC criteria** workflow (`.github/workflows/sync-criteria.yml`):

1. reads `track` and `criteria_ref` from `config.yml`;
2. reads the criteria from the [upstream Green DiSC repository](https://github.com/Cambridge-Sustainable-Computing-Lab/greenDiSC) at that ref and regenerates `criteria.yml`;
3. if anything changed, pushes the `greendisc/sync-criteria` branch and opens a pull request (or updates the open one); if nothing changed, closes any sync pull request still open from an earlier run.

`source_commit` in `criteria.yml` is the last upstream commit that changed your track's criteria files, not necessarily upstream's latest commit: upstream changes to other files (their README, overview PDF, other tracks) don't open a pull request.

The pull request links the upstream comparison between the previous and the new `source_commit`. `criteria.yml` only carries IDs and titles, so check that link for changes to the *Why / How / Acceptable Evidence* text that may affect your evidence.

If upstream changes its file format, the workflow fails instead of writing a wrong file. Check the run log, and report the problem to the toolkit maintainers.

## Running it

It runs at the start of each review, and whenever a change to `config.yml` reaches `main`, so changing `track` or `criteria_ref` keeps `criteria.yml` in step. You can also run it from the **Actions** tab → *Sync Green DiSC criteria* → *Run workflow*.

## Settings

In `config.yml`:

| Setting | Default | Meaning |
|---|---|---|
| `track` | `RG` | `RG` (Research Group), `CT` (Central Team) or `RCI` (Research Computing Infrastructure) |
| `criteria_ref` | `main` | Upstream branch, tag or commit SHA. Leave on `main` to follow upstream; set a SHA to pin. |

## Licence

The toolkit is released under the [BSD 3-Clause License](../LICENSE). The Green DiSC criteria it reads are licensed separately; see the [README](../README.md#licence).
