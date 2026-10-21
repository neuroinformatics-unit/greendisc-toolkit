# Submitting your evidence

Green DiSC applications are a submission form plus supporting files, read by an auditor from another institution. As this repository is typically private, auditors will not be able to access the evidence directly. The **Export Green DiSC evidence** workflow turns your saved records into an evidence pack you can attach to your submission.

> [!NOTE]
> Exporting is optional and never runs by itself: run it when you prepare a submission. You can also attach the files in `data/` as they are, but they include record numbers (which correspond to issue numbers and may not make sense to an external auditor) and private information such as locations and tags of the assets; the export leaves those out.

## Exporting

**Actions** tab → *Export Green DiSC evidence* → *Run workflow*. When the run finishes, download **greendisc-evidence** from the run's page (under *Artifacts*; kept for 7 days) and unzip it.

Or, from a local clone, with [uv](https://docs.astral.sh/uv/) installed:

```sh
uv run --script https://raw.githubusercontent.com/neuroinformatics-unit/actions/<sha>/greendisc_toolkit/export_evidence/export_evidence.py --with-reviews
```

This writes `greendisc-evidence/` in the current directory. `--with-reviews` adds the review history and needs the [GitHub CLI](https://cli.github.com/), logged in; leave it out otherwise.

## What's in the pack

- `index.html`: a section per criterion (`#RG-01-B`, `#RG-DS1-B`, …) with its table, plus the review history (included by default when running the workflow; locally only with `--with-reviews`). Attach it with the CSV files, and point to its sections from your answers.
- `csv/RG-<id>.csv`: each criterion's rows as a spreadsheet.
- `guides/`: the e-waste (`03-B`) and green computing (`HPC3-B`) guides.

The **review history** lists every [review cycle](reviews.md): its name, due date, the date it was closed, and how many check-ins were done (e.g. `5 of 6`). It shows auditors that the evidence is kept up to date rather than gathered once, which also helps with criteria that ask for regular updates (e.g. `DS2-B` data cleaning) and with recertification.

**Location** and **Asset tag** are left out by default, and members are numbered (`member 1`, `member 2`, …) instead of named.

`G1-B` and `G2-B` aren't in the pack: attach or link your representative's profile or role description, and your onboarding material.

## Customising what's exported

By default, **Location** and **Asset tag** are left out. To leave out other columns too, or keep them all:

- **Workflow:** add inputs to the export step in `.github/workflows/export-evidence.yml`:

  ```yaml
        - id: export
          uses: neuroinformatics-unit/actions/greendisc_toolkit/export_evidence@<sha>
          with:
            drop-columns: Location,Asset tag,Supplier
            # keep-all: true        # leave no columns out
            # with-reviews: false   # leave out the review history
  ```

- **Locally:** pass the same as options, e.g. `--drop-columns "Location,Asset tag,Supplier"`, `--keep-all`, or `--out <folder>` to choose where the pack goes.

See more examples in the [action's documentation](https://github.com/neuroinformatics-unit/actions/blob/main/greendisc_toolkit/export_evidence/README.md).