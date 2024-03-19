A limited export of GitHub metadata for the bitcoin repository.  Layout for
issue 1234:

 * `issues/12xx/1234.json` is the stuff common to issues and PRs, straight from
   the endpoint [`/repos/:owner/:repo/issues/:number`][issue]
 * `issues/12xx/1234-PR.json` exists only for issues that are also PRs, and
   contains the stuff specific to PRs, straight from the endpoint
   [`/repos/:owner/:repo/pulls/:number`][pull]
 * `issues/12xx/1234-comments.json` is all comments, both issue comments and PR
   review comments, in `created_at` order (so, a mixture of the
   [`/repos/:owner/:repo/issues/:number/comments`][comments] and
   [`/repos/:owner/:repo/pulls/:number/comments`][reviews] endpoints). However,
   **review-comments are missing** from the backups. See #6 for more details.

Note that issue descriptions are rendered as the first comment by GitHub's web
interface but are seen as properties of the issues by the GitHub API, and
therefore here too.

A few issues (about 10 in the first ~6000) are missing from the API, and
therefore here too, presumably because they were autodetected as spam by
GitHub.

While the point is mostly to survive GitHub downtime/removal, laanwj suggested
folks may use this while GitHub is up, to view comment edit history.  So,
issues are split into groups of 100 to avoid upsetting GitHub's web interface,
which won't show >1000 files on a page.

This export is produced/updated by [ghrip], an ugly, hasty, unfinished hack.

 [issue]: https://developer.github.com/v3/issues/#get-a-single-issue
 [pull]: https://developer.github.com/v3/pulls/#get-a-single-pull-request
 [comments]: https://developer.github.com/v3/issues/comments/#list-comments-on-an-issue
 [reviews]: https://developer.github.com/v3/pulls/comments/#list-comments-on-a-pull-request
 [ghrip]: https://github.com/zw/ghrip
