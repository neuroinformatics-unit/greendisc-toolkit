# Keeping criteria in sync with Green DiSC

`criteria.yml` lists the Green DiSC criteria for your track: one entry per criterion with its ID, issue label, title and category. The review workflows read it to create one issue per criterion. It is generated, so don't edit it by hand.

## How it works

The **Sync Green DiSC criteria** workflow (`.github/workflows/sync-criteria.yml`):

1. reads `track` and `criteria_ref` from `config.yml`;
2. reads the criteria from the [upstream Green DiSC repository](https://github.com/Cambridge-Sustainable-Computing-Lab/greenDiSC) at that ref and regenerates `criteria.yml`;
3. if anything changed, pushes the `greendisc/sync-criteria` branch and opens a pull request (or updates the open one).

The pull request links the upstream comparison between the previous and the new `source_commit`. `criteria.yml` only carries IDs and titles, so check that link for changes to the *Why / How / Acceptable Evidence* text that may affect your evidence.

If upstream changes its file format, the workflow fails instead of writing a wrong file. Check the run log, and report the problem to the toolkit maintainers.

## Running it

Run it from the **Actions** tab → *Sync Green DiSC criteria* → *Run workflow*. Run it once after creating your repository from the template, to create `criteria.yml`.

## Settings

In `config.yml`:

| Setting | Default | Meaning |
|---|---|---|
| `track` | `RG` | `RG` (Research Group), `CT` (Central Team) or `RCI` (Research Computing Infrastructure) |
| `criteria_ref` | `main` | Upstream branch, tag or commit SHA. Leave on `main` to follow upstream; set a SHA to pin. |

## Permissions

The job needs `contents: write` (to push the sync branch) and `pull-requests: write` (to open the pull request), using the default `GITHUB_TOKEN`.

The repository must allow workflows to open pull requests: **Settings → Actions → General → Workflow permissions → Allow GitHub Actions to create and approve pull requests**. Organisations can disable this setting for all their repositories; ask an organisation owner if it is greyed out.

## Licence

The toolkit is released under the [BSD 3-Clause License](../LICENSE). The Green DiSC criteria it reads are licensed separately; see the [README](../README.md#licence).
