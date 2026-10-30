# Publishing a split, by host

Find the host with `git remote get-url origin`. "Not verified" means the behavior wasn't checked when this was written: assume the conservative option, and check your host's documentation.

| Host | How to publish a split | After a lower part merges | Mermaid in descriptions |
|---|---|---|---|
| GitHub | Stacked pull requests (`gh stack`), or PRs chained by base branch | Dependent PRs are retargeted when the merged base branch is deleted | Rendered |
| GitLab | Merge requests chained by target branch | Dependent MRs are retargeted automatically if the merged MR deletes its source branch. Limits apply, and forks aren't supported | Rendered |
| Bitbucket Cloud | Pull requests chained by destination branch | Not verified. Retarget by hand | Not rendered natively. Use a numbered list |
| Azure DevOps | Pull requests chained by target branch | Not verified. Retarget by hand | Rendered (2024 and later) |
| Gerrit | One change per commit. A series of commits pushed together becomes a relation chain | Not needed: each change is reviewed and submitted in order | Plain text. Use a numbered list |
| Anything else | One PR with one commit per idea. Ask the reviewer to go commit by commit | Not needed | Check the host |

## Chained PRs (no native stacks)

1. Push each part to its own branch, each based on the one below it.
2. Open each PR against the branch below it, not the main branch.
3. Start each description with "Part N of M" and link the parts both ways.
4. Merge from the bottom. Retarget the next PR to the main branch if the host doesn't do it.
5. After a lower part changes, rebase the parts above it and say so in a comment.

## Sources

- GitLab retargeting: [gitlab-org/gitlab#320902](https://gitlab.com/gitlab-org/gitlab/-/issues/320902), [!53710](https://gitlab.com/gitlab-org/gitlab/-/merge_requests/53710).
- Azure DevOps Mermaid: [Sprint 246 release notes](https://learn.microsoft.com/en-us/azure/devops/release-notes/2024/sprint-246-update).
- Bitbucket Cloud: no native Mermaid found; third-party extensions exist.
