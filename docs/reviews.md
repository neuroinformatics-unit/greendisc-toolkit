# Running reviews

Green DiSC asks for evidence that's kept up to date, not a one-off snapshot. The toolkit organises this as **review cycles**: the period leading up to a review, usually every few months. Each cycle is a GitHub milestone whose due date is the review date.

## Starting a cycle

The Green DiSC representative starts each cycle, usually right after finishing the previous one:

1. Decide when the review should be done by.
2. Go to **Actions → Start Green DiSC review → Run workflow**.
3. Enter that date as `YYYY-MM-DD` (e.g. `2026-12-10`). The cycle is named `Review-<year>-<month>` of that date; type a different name if you prefer, without spaces (GitHub's milestone links break on them, so they're replaced with hyphens).
4. Click **Run workflow**.

Alternatively, with the [GitHub CLI](https://cli.github.com/): `gh workflow run review.yml -f due=2026-12-10` (add `-f name=...` for a different name).

Only people with the **Maintain** or **Admin** role can start a review; for anyone else the run stops with an error and creates nothing.

## What it creates

1. **A criteria sync.** If Green DiSC's criteria changed since the last cycle, it opens a pull request, and the representative's check-in gets an item to check the upstream changes and merge it. If the sync itself fails (for example, upstream can't be reached or its file format changed), the review still starts; the failed run shows why.
2. **A milestone** for the cycle, due on the review date. Its progress bar shows how many check-ins are done.
3. **A check-in issue for each member**, assigned to them. A check-in is a to-do list:
   - **your personal record:** check everything is up to date, then comment `/save`;
   - **the group record:** check everything is up to date;
   - **the guides:** go over them, opening pull requests to make changes as needed, and review any open pull requests to update the guides. Anyone with Write access can approve and merge them.

   Commenting `/save` on your personal record ticks its item. Saving an unchanged record counts: it shows the record was looked at. Tick the other items yourself as you do them, then **close the check-in**. If an item is unticked, or your record wasn't saved during this review (ticking its item by hand doesn't count), the check-in is reopened with a note of what's left.
4. **The representative's check-in.** The representative starts each review and gets this check-in; if someone else starts a review for them, reassign it to the representative. It has the same items as members' check-ins, plus:
   - review members' changes to the group record and comment `/save` on it;
   - check the README's *Your Green DiSC representative* section is up to date;
   - when the criteria sync opened a pull request: check the upstream changes and merge it;
   - when the [guides](../guides/README.md) changed since the previous review: if you publish them elsewhere, such as your website, update that copy (the item links to the diff of each changed guide);
   - when the [data files](records.md#the-data-files) have rows from records that aren't open (for example, a deleted personal record): decide what to do with them. Usually that means deleting those rows.

   As on members' check-ins, saving a record ticks its item; the representative ticks the rest and closes the check-in when done.

On the **first review**, it also creates the records, as issues: **the group record**, assigned to the representative, and **a personal record for every member** (everyone with the **Write**, **Maintain** or **Admin** role). Later reviews create records only for people who have never had one, such as new members. A closed record is never recreated: close the record of anyone who doesn't need one, and reopen it if they rejoin or it was closed by mistake.

It also **closes the previous cycle**: any of its check-ins still open are closed, then its milestone is closed. The run's summary (open the run under **Actions**) lists what was created and any records with unsaved changes.

If a run fails part-way, run it again with the same date: it only adds what's missing.

## Finishing a review

- Open check-ins in the milestone show who hasn't finished going over their record, the group record and the guides. Ask them to, or save a member's record for them: Maintain and Admin can save anyone's record.
- A check-in a member closed before finishing it is reopened, with a note of what's left. Check-ins closed by the representative (Maintain or Admin) are left closed, so close one that can't be finished, e.g. for a member on leave, yourself.
- The issue search `is:issue label:"unsaved changes"` finds records edited but not saved.
- Open pull requests show suggested changes to the guides.

Once everything on their check-in is done, the representative closes it, and starts the next cycle when it's due. Some groups like to go through the criteria together at a meeting; [Recording evidence](records.md) and the [guides](../guides/README.md) say which criteria each part covers.

Closed milestones, with their check-ins, are the record of past reviews.
