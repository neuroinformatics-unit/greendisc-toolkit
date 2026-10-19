# Running reviews

Green DiSC asks for evidence that's kept up to date, not a one-off snapshot. The toolkit organises this as **review cycles**: the period leading up to a review meeting, usually every few months. Each cycle is a GitHub milestone whose due date is the meeting date.

## Starting a cycle

The Green DiSC representative starts each cycle, usually at the end of the previous review meeting:

1. Agree the date of the next review meeting.
2. Go to **Actions → Start Green DiSC review → Run workflow**.
3. Enter the meeting date as `YYYY-MM-DD` (e.g. `2026-12-10`). The cycle is named `Review-<year>-<month>` of that date; type a different name if you prefer, without spaces (GitHub's milestone links break on them, so they're replaced with hyphens).
4. Click **Run workflow**.

Alternatively, with the [GitHub CLI](https://cli.github.com/): `gh workflow run review.yml -f due=2026-12-10` (add `-f name=...` for a different name).

Only people with the **Maintain** or **Admin** role can start a review; for anyone else the run stops with an error and creates nothing.

## What it creates

- **A milestone** for the cycle, due on the meeting date. Its progress bar shows how many check-ins are done.
- **A check-in for each member** who has a personal record, assigned to them:
  - **your personal record:** check everything is up to date, then comment `/save`;
  - **the group record:** check everything is up to date;
  - **the guides:** read them, and suggest anything new or outdated by editing the page on GitHub and choosing to start a pull request.

  Saving your record ticks its line and closes your check-in. Saving an unchanged record counts: it shows the record was looked at.
- **The representative's check-in**, assigned to whoever starts the review. It covers their own record, and also asks them to:
  - review members' changes to the group record and comment `/save` on it;
  - check the guides are up to date, and review members' pull requests;
  - check the README's *Your Green DiSC representative* section and *Where the evidence lives* table;
  - if Green DiSC's criteria changed, check the upstream changes and merge the criteria sync pull request (this item only appears when there is one);
  - go through the evidence for each criterion at the meeting.

  Saving a record ticks its line; the representative ticks the rest and closes the check-in after the meeting.
- **A criteria sync**, run first, which opens a pull request if Green DiSC's criteria changed since the last cycle. Check the linked upstream changes for anything that affects your evidence before merging it. If the sync fails, the review still starts.

It also **closes the previous cycle**: any of its check-ins still open are closed, then its milestone is closed. The run's summary (open the run under **Actions**) lists what was created and any records with unsaved changes.

If a run fails part-way, run it again with the same date: it only adds what's missing.

## Before the meeting

- Open check-ins in the milestone show who hasn't gone over their record yet.
- The issue search `is:issue label:"unsaved changes"` finds records edited but not saved.
- Open pull requests show suggested changes to the guides.

## At the meeting

Go through the criteria one by one: the README's *Where the evidence lives* table says where each one's evidence is, and the representative's check-in links the criteria text. Note anything to follow up as a comment on the representative's check-in. Then the representative closes their check-in, agrees the next meeting date with the group and starts the next cycle.

Closed milestones, with their check-ins, are the record of past reviews.
