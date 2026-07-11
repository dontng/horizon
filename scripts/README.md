# Scripts

This folder contains local workspace commands for managing `study`.

## Why `hgit` exists

The `study/.git` path is occupied by the runtime environment, so the Horizon
checkout uses `.horizon.git` as its Git metadata directory.

Use `scripts/hgit` when you want to run Git commands for Horizon:

```bash
scripts/hgit status
scripts/hgit pull
scripts/hgit push
```

The ignored sibling repositories use normal Git commands:

```bash
git -C english2-daily status
git -C 408-from-44 status
git -C reading status
git -C math2-daily status
```

## Pull everything

Run this from the `study` root:

```bash
scripts/pull-all
```

It pulls Horizon first, then each ignored sibling repository:

- `english2-daily`
- `408-from-44`
- `reading`
- `math2-daily`

The script uses `--ff-only`, so it will stop instead of creating merge commits.
If one repository has local changes or diverged history, fix that repository and
run the command again.
