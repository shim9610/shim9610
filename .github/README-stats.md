# README card updates

The profile embeds `profile/stats.svg` and `profile/top-langs.svg`. The cards are
generated with GitHub Readme Stats Action and include accessible private
repositories owned by the account. Forks are excluded by the upstream language
fetcher. AGS Script is hidden from the language card; eight languages are shown.

## Enable daily updates

1. Create a GitHub personal access token that can read the private repositories
   you want included. The action's documented classic-token scopes are `repo`
   and `read:user`. Organization repositories may require SSO authorization.
2. In this repository, open **Settings > Secrets and variables > Actions >
   New repository secret** and save it as **STATS_TOKEN**.
3. Open **Actions > Update README cards > Run workflow**, select `main`, and run.

The workflow refreshes both cards daily at 10:00 Asia/Seoul (01:00 UTC).
It uses the normal workflow token to commit generated images and STATS_TOKEN
only to read statistics. The token never belongs in README URLs or source files.

Without STATS_TOKEN, automatic generation is skipped and the existing cards are
preserved. A rendering or API failure prevents committing either card.

The published cards contain aggregate counts and language percentages. They do
not publish private repository names, source code, or authentication values.
Percentages reflect GitHub's language byte counts, not development time.

Upstream documentation:
https://github.com/stats-organization/github-readme-stats-action
