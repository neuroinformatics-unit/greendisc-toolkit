# Recording evidence

Each member keeps **one record issue** listing the equipment they use or look after. The toolkit saves these records to CSV files in `data/`, which become the inventories for your Green DiSC submission.

| Section | Criteria | Saved to |
|---|---|---|
| Hardware | `01-B` computing hardware inventory; `02-B` unused equipment (items with status `unused`) | `data/hardware.csv` |

More sections (data resources, data cleaning, pipelines) and a separate group record are coming.

## Creating your record

1. **Issues → New issue → My Green DiSC record.**
2. Fill in the table: one row per item, copying a row to add more. The comment above the table (visible when editing) says what each column expects. **Type** is free text; use the suggested names where they fit so items are counted together. Leave a cell blank if you don't know; it is saved as `unknown` so it can be filled in later.
3. Click **Create**. The bot labels it `unsaved changes` and replies with how to save it.
4. Comment `/save` (just that, on its own). The bot checks every row, saves them, replies with a summary (including how many values are still `unknown`) and removes the `unsaved changes` label.

**Keep your record open.** It's yours for as long as you're in the group; it is only closed when you leave (see below).

If something is wrong (say, `broken` as a status, or `22` as a year), nothing is saved: the bot replies listing each problem by row and column. Edit the issue, fix them and comment `/save` again.

## Keeping it up to date

Edit your record issue, change the table and comment `/save` again. Your saved rows are replaced by the current table.

Editing the table adds the `unsaved changes` label, and a successful `/save` removes it. Until then your edits are not in the saved data, so the review can find unsaved records with the issue search `is:issue label:"unsaved changes"`.

- **New item:** add a row.
- **Item no longer used:** set its status to `unused` and say in **Action** what will happen to it.
- **Item gone:** set its status to `disposed` and say in **Action** what happened (returned, donated, recycled, …). Keep the row: Green DiSC asks what happened to equipment.

Find your record with the issue search `is:issue label:personal-record author:@me`.

Each person has one record. Opening a second one gets it closed with a link to the first.

## Who can save

Only people with write access to the repository (owners, members and collaborators) can save records; comments from anyone else are ignored. Anyone with write access can save any record, so the Green DiSC representative can update the record of someone who has left.

## When someone leaves

The representative updates their record (each item's status, with an **Action** saying what happened, e.g. `returned to IT`), comments `/save`, then closes the issue. Closed records stay in the data; `/save` still works on them if something needs correcting later.

## The CSV files

The bot is the only writer of `data/*.csv`. Each row has a `record` column with its issue number, which is how a later `/save` finds the rows to replace, so **don't edit the CSV files directly**: change the issue and `/save` instead, or your edit will be overwritten.

## Privacy

**Location** and **Asset tag** are optional, and owner names are implied by who created each record. Keep the repository private if you record them. The public summary only ever contains counts, never rows.

## Permissions

The workflow (`.github/workflows/save-record.yml`) needs `contents: write` (to commit the CSV files) and `issues: write` (to label and comment on record issues, and close duplicates), using the default `GITHUB_TOKEN`.
