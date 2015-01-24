A limited export of GitHub metadata for the bitcoin repository.  Layout for
issue 1234:

 * `issues/12xx/1234.json` is the stuff common to issues and PRs
 * `issues/12xx/1234-PR.json` exists only for issues that are also PRs, and
   contains the stuff specific to PRs
 * `issues/12xx/1234-comments.json` is all comments, both issue comments and PR
   review comments, in `created_at` order

Note that issue descriptions are rendered like a comment by GitHub's site but
are seen as properties of the issues by the GitHub API, and therefore here too.

A few issues (about 10 in the first ~6000) are missing from the API, and
therefore here too, presumably because they were autodetected as spam by
GitHub.

Issues are split into groups of 100 to avoid upsetting GitHub's web interface,
which won't show >1000 files on a page.

This export was produced by [ghrip] [], a work-in-progress.

 [ghrip]: https://github.com/zw/ghrip
