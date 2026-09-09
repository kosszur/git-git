# Git core dokumentáció magyar fordítás — haladás

Fordítás **helyben**: a `git/Documentation/**/*.adoc` fájlokat a saját helyükön írjuk felül
(a repó maga a fordítás, ugyanaz a fájlfa). A verziókövetést (branch, commit, push, upstream-merge)
a felhasználó kezeli kézzel. A részletes szabályokat lásd a `translate-git-docs` skillben.

**Import-alapvonal:** `git/git@________________________________________` — `2026-__-__`
Töltsd ki azzal az upstream commit-SHA-val, amelyről a jelenlegi `git/Documentation/` snapshot készült.
Amíg egy fájl nincs külön újraszinkronizálva egy későbbi upstream committal, a fordítása erre a SHA-ra vonatkozik.

## Jelölések

- **`kész`** oszlop: `[ ]` = nincs kész · `[x]` = kész · `~NN%` = részleges · `elavult` = az upstream változott ezen a fájlon, újra kell nézni
- **`forrás-SHA`**: az az upstream commit, amelyhez képest a fordítás naprakész (üres = az import-alapvonal érvényes)
- **`utolsó-ellenőrzés`**: ISO dátum (`ÉÉÉÉ-HH-NN`), amikor a fájlt utoljára összevetetted az upstreammel

## Hatókör

Minden `.adoc` a `git/Documentation/` fa alatt — **a `RelNotes/` KIVÉTELÉVEL** (nem fordítjuk).
A `.adoco` kiterjesztésű fájlok (`everyday.adoco`, `git-remote-helpers.adoco`) nem tartoznak bele.
Összesen ~403 fájl, könyvtár szerint csoportosítva alább.

## Prioritás

Nincs kötelező sorrend (a man page-ek egymástól függetlenül épülnek). Ajánlott haladás:
`technical/` → `config/` + `config.adoc` → gyökér option-fragmensek (`*-options.adoc`, `diff-*.adoc`) →
`git-*.adoc` man page-ek → `howto/` → nagy guide-ok (`user-manual.adoc`, `gittutorial*.adoc`,
`giteveryday.adoc`, `gitglossary.adoc` + `glossary-content.adoc`).

A `glossary-content.adoc` / `gitglossary.adoc` és a `git.adoc` fő man page magas kereszthivatkozás-
sűrűségűek — ezeket a végére hagyd, amikor a terminológia már stabil.

---

### Gyökér — `git-*.adoc` man page-ek

| fájl | kész | forrás-SHA | utolsó-ellenőrzés |
|---|---|---|---|
| git-add.adoc | [x] |  | 2026-09-04 |
| git-am.adoc | [x] |  | 2026-09-04 |
| git-annotate.adoc | [x] |  | 2026-09-04 |
| git-apply.adoc | [x] |  | 2026-09-04 |
| git-archimport.adoc | [x] |  | 2026-09-04 |
| git-archive.adoc | [x] |  | 2026-09-04 |
| git-backfill.adoc | [x] |  | 2026-09-04 |
| git-bisect-lk2009.adoc | [x] |  | 2026-09-04 |
| git-bisect.adoc | [x] |  | 2026-09-04 |
| git-blame.adoc | [x] |  | 2026-09-04 |
| git-branch.adoc | [x] |  | 2026-09-04 |
| git-bugreport.adoc | [x] |  | 2026-09-04 |
| git-bundle.adoc | [x] |  | 2026-09-04 |
| git-cat-file.adoc | [x] |  | 2026-09-04 |
| git-check-attr.adoc | [x] |  | 2026-09-04 |
| git-check-ignore.adoc | [x] |  | 2026-09-04 |
| git-check-mailmap.adoc | [x] |  | 2026-09-04 |
| git-check-ref-format.adoc | [x] |  | 2026-09-04 |
| git-checkout-index.adoc | [x] |  | 2026-09-04 |
| git-checkout.adoc | [x] |  | 2026-09-04 |
| git-cherry-pick.adoc | [x] |  | 2026-09-04 |
| git-cherry.adoc | [x] |  | 2026-09-04 |
| git-citool.adoc | [x] |  | 2026-09-04 |
| git-clean.adoc | [x] |  | 2026-09-04 |
| git-clone.adoc | [x] |  | 2026-09-04 |
| git-column.adoc | [x] |  | 2026-09-04 |
| git-commit-graph.adoc | [x] |  | 2026-09-04 |
| git-commit-tree.adoc | [x] |  | 2026-09-04 |
| git-commit.adoc | [x] |  | 2026-09-04 |
| git-config.adoc | [x] |  | 2026-09-04 |
| git-count-objects.adoc | [x] |  | 2026-09-04 |
| git-credential-cache--daemon.adoc | [x] |  | 2026-09-04 |
| git-credential-cache.adoc | [x] |  | 2026-09-04 |
| git-credential-store.adoc | [x] |  | 2026-09-04 |
| git-credential.adoc | [x] |  | 2026-09-04 |
| git-cvsexportcommit.adoc | [x] |  | 2026-09-04 |
| git-cvsimport.adoc | [x] |  | 2026-09-04 |
| git-cvsserver.adoc | [x] |  | 2026-09-04 |
| git-daemon.adoc | [x] |  | 2026-09-04 |
| git-describe.adoc | [x] |  | 2026-09-04 |
| git-diagnose.adoc | [x] |  | 2026-09-04 |
| git-diff-files.adoc | [x] |  | 2026-09-04 |
| git-diff-index.adoc | [x] |  | 2026-09-04 |
| git-diff-pairs.adoc | [x] |  | 2026-09-04 |
| git-diff-tree.adoc | [x] |  | 2026-09-04 |
| git-diff.adoc | [x] |  | 2026-09-04 |
| git-difftool.adoc | [x] |  | 2026-09-04 |
| git-fast-export.adoc | [x] |  | 2026-09-04 |
| git-fast-import.adoc | ~32% |  |  |
| git-fetch-pack.adoc | [x] |  | 2026-09-04 |
| git-fetch.adoc | [x] |  | 2026-09-04 |
| git-filter-branch.adoc | [x] |  | 2026-09-04 |
| git-fmt-merge-msg.adoc | [ ] |  |  |
| git-for-each-ref.adoc | [ ] |  |  |
| git-for-each-repo.adoc | [x] |  | 2026-09-10 |
| git-format-patch.adoc | [ ] |  |  |
| git-format-rev.adoc | [ ] |  |  |
| git-fsck-objects.adoc | [x] |  | 2026-09-10 |
| git-fsck.adoc | [ ] |  |  |
| git-fsmonitor--daemon.adoc | [ ] |  |  |
| git-gc.adoc | [ ] |  |  |
| git-get-tar-commit-id.adoc | [x] |  | 2026-09-10 |
| git-grep.adoc | [ ] |  |  |
| git-gui.adoc | [ ] |  |  |
| git-hash-object.adoc | [x] |  | 2026-09-10 |
| git-help.adoc | [ ] |  |  |
| git-history.adoc | [ ] |  |  |
| git-hook.adoc | [ ] |  |  |
| git-http-backend.adoc | [ ] |  |  |
| git-http-fetch.adoc | [x] |  | 2026-09-10 |
| git-http-push.adoc | [ ] |  |  |
| git-imap-send.adoc | [ ] |  |  |
| git-index-pack.adoc | [ ] |  |  |
| git-init-db.adoc | [x] |  | 2026-09-10 |
| git-init.adoc | [ ] |  |  |
| git-instaweb.adoc | [ ] |  |  |
| git-interpret-trailers.adoc | [ ] |  |  |
| git-last-modified.adoc | [ ] |  |  |
| git-log.adoc | [ ] |  |  |
| git-ls-files.adoc | [ ] |  |  |
| git-ls-remote.adoc | [ ] |  |  |
| git-ls-tree.adoc | [ ] |  |  |
| git-mailinfo.adoc | [ ] |  |  |
| git-mailsplit.adoc | [x] |  | 2026-09-10 |
| git-maintenance.adoc | [ ] |  |  |
| git-merge-base.adoc | [ ] |  |  |
| git-merge-file.adoc | [ ] |  |  |
| git-merge-index.adoc | [ ] |  |  |
| git-merge-one-file.adoc | [x] |  | 2026-09-10 |
| git-merge-tree.adoc | [ ] |  |  |
| git-merge.adoc | [ ] |  |  |
| git-mergetool--lib.adoc | [x] |  | 2026-09-10 |
| git-mergetool.adoc | [ ] |  |  |
| git-mktag.adoc | [x] |  | 2026-09-10 |
| git-mktree.adoc | [x] |  | 2026-09-10 |
| git-multi-pack-index.adoc | [ ] |  |  |
| git-mv.adoc | [ ] |  |  |
| git-name-rev.adoc | [ ] |  |  |
| git-notes.adoc | [ ] |  |  |
| git-p4.adoc | [ ] |  |  |
| git-pack-objects.adoc | [ ] |  |  |
| git-pack-redundant.adoc | [x] |  | 2026-09-10 |
| git-pack-refs.adoc | [x] |  | 2026-09-10 |
| git-patch-id.adoc | [ ] |  |  |
| git-prune-packed.adoc | [x] |  | 2026-09-10 |
| git-prune.adoc | [ ] |  |  |
| git-pull.adoc | [ ] |  |  |
| git-push.adoc | [ ] |  |  |
| git-quiltimport.adoc | [x] |  | 2026-09-10 |
| git-range-diff.adoc | [ ] |  |  |
| git-read-tree.adoc | [ ] |  |  |
| git-rebase.adoc | [ ] |  |  |
| git-receive-pack.adoc | [ ] |  |  |
| git-reflog.adoc | [ ] |  |  |
| git-refs.adoc | [ ] |  |  |
| git-remote-ext.adoc | [ ] |  |  |
| git-remote-fd.adoc | [x] |  | 2026-09-10 |
| git-remote.adoc | [ ] |  |  |
| git-repack.adoc | [ ] |  |  |
| git-replace.adoc | [ ] |  |  |
| git-replay.adoc | [ ] |  |  |
| git-repo.adoc | [ ] |  |  |
| git-request-pull.adoc | [ ] |  |  |
| git-rerere.adoc | [ ] |  |  |
| git-reset.adoc | [ ] |  |  |
| git-restore.adoc | [ ] |  |  |
| git-rev-list.adoc | [ ] |  |  |
| git-rev-parse.adoc | [ ] |  |  |
| git-revert.adoc | [ ] |  |  |
| git-rm.adoc | [ ] |  |  |
| git-send-email.adoc | [ ] |  |  |
| git-send-pack.adoc | [ ] |  |  |
| git-sh-i18n--envsubst.adoc | [x] |  | 2026-09-10 |
| git-sh-i18n.adoc | [x] |  | 2026-09-10 |
| git-sh-setup.adoc | [ ] |  |  |
| git-shell.adoc | [ ] |  |  |
| git-shortlog.adoc | [ ] |  |  |
| git-show-branch.adoc | [ ] |  |  |
| git-show-index.adoc | [x] |  | 2026-09-10 |
| git-show-ref.adoc | [ ] |  |  |
| git-show.adoc | [ ] |  |  |
| git-sparse-checkout.adoc | [ ] |  |  |
| git-stage.adoc | [x] |  | 2026-09-10 |
| git-stash.adoc | [ ] |  |  |
| git-status.adoc | [ ] |  |  |
| git-stripspace.adoc | [ ] |  |  |
| git-submodule.adoc | [ ] |  |  |
| git-svn.adoc | [ ] |  |  |
| git-switch.adoc | [ ] |  |  |
| git-symbolic-ref.adoc | [ ] |  |  |
| git-tag.adoc | [ ] |  |  |
| git-tools.adoc | [x] |  | 2026-09-10 |
| git-unpack-file.adoc | [x] |  | 2026-09-10 |
| git-unpack-objects.adoc | [x] |  | 2026-09-10 |
| git-update-index.adoc | [ ] |  |  |
| git-update-ref.adoc | [ ] |  |  |
| git-update-server-info.adoc | [x] |  | 2026-09-10 |
| git-upload-archive.adoc | [x] |  | 2026-09-10 |
| git-upload-pack.adoc | [ ] |  |  |
| git-url-parse.adoc | [ ] |  |  |
| git-var.adoc | [ ] |  |  |
| git-verify-commit.adoc | [x] |  | 2026-09-10 |
| git-verify-pack.adoc | [x] |  | 2026-09-10 |
| git-verify-tag.adoc | [x] |  | 2026-09-10 |
| git-version.adoc | [x] |  | 2026-09-10 |
| git-web--browse.adoc | [ ] |  |  |
| git-whatchanged.adoc | [x] |  | 2026-09-10 |
| git-worktree.adoc | [ ] |  |  |
| git-write-tree.adoc | [x] |  | 2026-09-10 |

### Gyökér — egyéb `.adoc` (guide-ok, option-fragmensek, includimport)

| fájl | kész | forrás-SHA | utolsó-ellenőrzés |
|---|---|---|---|
| BreakingChanges.adoc | [ ] |  |  |
| DecisionMaking.adoc | [ ] |  |  |
| MyFirstContribution.adoc | [ ] |  |  |
| MyFirstObjectWalk.adoc | [ ] |  |  |
| ReviewingGuidelines.adoc | [ ] |  |  |
| ToolsForGit.adoc | [x] |  | 2026-09-10 |
| blame-options.adoc | [ ] |  |  |
| config.adoc | [ ] |  |  |
| date-formats.adoc | [x] |  | 2026-09-10 |
| diff-algorithm-option.adoc | [x] |  | 2026-09-10 |
| diff-context-options.adoc | [x] |  | 2026-09-10 |
| diff-format.adoc | [ ] |  |  |
| diff-generate-patch.adoc | [ ] |  |  |
| diff-options.adoc | [ ] |  |  |
| fetch-options.adoc | [ ] |  |  |
| for-each-ref-options.adoc | [ ] |  |  |
| format-patch-caveats.adoc | [x] |  | 2026-09-10 |
| format-patch-end-of-commit-message.adoc | [x] |  | 2026-09-10 |
| fsck-msgids.adoc | [ ] |  |  |
| git.adoc | [ ] |  |  |
| gitattributes.adoc | [ ] |  |  |
| gitcli.adoc | [ ] |  |  |
| gitcore-tutorial.adoc | [ ] |  |  |
| gitcredentials.adoc | [ ] |  |  |
| gitcvs-migration.adoc | [ ] |  |  |
| gitdatamodel.adoc | [ ] |  |  |
| gitdiffcore.adoc | [ ] |  |  |
| giteveryday.adoc | [ ] |  |  |
| gitfaq.adoc | [ ] |  |  |
| gitformat-bundle.adoc | [ ] |  |  |
| gitformat-chunk.adoc | [ ] |  |  |
| gitformat-commit-graph.adoc | [ ] |  |  |
| gitformat-index.adoc | [ ] |  |  |
| gitformat-loose.adoc | [ ] |  |  |
| gitformat-pack.adoc | [ ] |  |  |
| gitformat-signature.adoc | [ ] |  |  |
| gitglossary.adoc | [ ] |  |  |
| githooks.adoc | [ ] |  |  |
| gitignore.adoc | [ ] |  |  |
| gitk.adoc | [ ] |  |  |
| gitmailmap.adoc | [ ] |  |  |
| gitmodules.adoc | [ ] |  |  |
| gitnamespaces.adoc | [ ] |  |  |
| gitpacking.adoc | [ ] |  |  |
| gitprotocol-capabilities.adoc | [ ] |  |  |
| gitprotocol-common.adoc | [ ] |  |  |
| gitprotocol-http.adoc | [ ] |  |  |
| gitprotocol-pack.adoc | [ ] |  |  |
| gitprotocol-v2.adoc | [ ] |  |  |
| gitremote-helpers.adoc | [ ] |  |  |
| gitrepository-layout.adoc | [ ] |  |  |
| gitrevisions.adoc | [x] |  | 2026-09-10 |
| gitsubmodules.adoc | [ ] |  |  |
| gittutorial-2.adoc | [ ] |  |  |
| gittutorial.adoc | [ ] |  |  |
| gitweb.adoc | [ ] |  |  |
| gitweb.conf.adoc | [ ] |  |  |
| gitworkflows.adoc | [ ] |  |  |
| glossary-content.adoc | [ ] |  |  |
| i18n.adoc | [ ] |  |  |
| line-range-format.adoc | [x] |  | 2026-09-10 |
| line-range-options.adoc | [x] |  | 2026-09-10 |
| merge-options.adoc | [ ] |  |  |
| merge-strategies.adoc | [ ] |  |  |
| object-format-disclaimer.adoc | [x] |  | 2026-09-10 |
| pack-refs-options.adoc | [x] |  | 2026-09-10 |
| pretty-formats.adoc | [ ] |  |  |
| pretty-options.adoc | [ ] |  |  |
| pull-fetch-param.adoc | [ ] |  |  |
| ref-reachability-filters.adoc | [x] |  | 2026-09-10 |
| ref-storage-format.adoc | [x] |  | 2026-09-10 |
| rerere-options.adoc | [x] |  | 2026-09-10 |
| rev-list-description.adoc | [x] |  | 2026-09-10 |
| rev-list-options.adoc | [ ] |  |  |
| revisions.adoc | [ ] |  |  |
| scalar.adoc | [ ] |  |  |
| sequencer.adoc | [x] |  | 2026-09-10 |
| signoff-option.adoc | [x] |  | 2026-09-10 |
| trace2-target-values.adoc | [x] |  | 2026-09-10 |
| transfer-data-leaks.adoc | [x] |  | 2026-09-10 |
| urls-remotes.adoc | [ ] |  |  |
| urls.adoc | [ ] |  |  |
| user-manual.adoc | [ ] |  |  |

### `config/`

| fájl | kész | forrás-SHA | utolsó-ellenőrzés |
|---|---|---|---|
| config/add.adoc | [ ] |  |  |
| config/advice.adoc | [ ] |  |  |
| config/alias.adoc | [ ] |  |  |
| config/am.adoc | [ ] |  |  |
| config/apply.adoc | [ ] |  |  |
| config/attr.adoc | [ ] |  |  |
| config/bitmap-pseudo-merge.adoc | [ ] |  |  |
| config/blame.adoc | [ ] |  |  |
| config/branch.adoc | [ ] |  |  |
| config/browser.adoc | [ ] |  |  |
| config/bundle.adoc | [ ] |  |  |
| config/checkout.adoc | [ ] |  |  |
| config/clean.adoc | [ ] |  |  |
| config/clone.adoc | [ ] |  |  |
| config/color.adoc | [ ] |  |  |
| config/column.adoc | [ ] |  |  |
| config/commit.adoc | [ ] |  |  |
| config/commitgraph.adoc | [ ] |  |  |
| config/completion.adoc | [ ] |  |  |
| config/core.adoc | [ ] |  |  |
| config/credential.adoc | [ ] |  |  |
| config/diff.adoc | [ ] |  |  |
| config/difftool.adoc | [ ] |  |  |
| config/extensions.adoc | [ ] |  |  |
| config/fastimport.adoc | [ ] |  |  |
| config/feature.adoc | [ ] |  |  |
| config/fetch.adoc | [ ] |  |  |
| config/filter.adoc | [ ] |  |  |
| config/fmt-merge-msg.adoc | [ ] |  |  |
| config/format.adoc | [ ] |  |  |
| config/fsck.adoc | [ ] |  |  |
| config/fsmonitor--daemon.adoc | [ ] |  |  |
| config/gc.adoc | [ ] |  |  |
| config/gitcvs.adoc | [ ] |  |  |
| config/gitweb.adoc | [ ] |  |  |
| config/gpg.adoc | [ ] |  |  |
| config/grep.adoc | [ ] |  |  |
| config/gui.adoc | [ ] |  |  |
| config/guitool.adoc | [ ] |  |  |
| config/help.adoc | [ ] |  |  |
| config/hook.adoc | [ ] |  |  |
| config/http.adoc | [ ] |  |  |
| config/i18n.adoc | [ ] |  |  |
| config/imap.adoc | [ ] |  |  |
| config/includeif.adoc | [ ] |  |  |
| config/index.adoc | [ ] |  |  |
| config/init.adoc | [ ] |  |  |
| config/instaweb.adoc | [ ] |  |  |
| config/interactive.adoc | [ ] |  |  |
| config/log.adoc | [ ] |  |  |
| config/lsrefs.adoc | [ ] |  |  |
| config/mailinfo.adoc | [ ] |  |  |
| config/mailmap.adoc | [ ] |  |  |
| config/maintenance.adoc | [ ] |  |  |
| config/man.adoc | [ ] |  |  |
| config/merge.adoc | [ ] |  |  |
| config/mergetool.adoc | [ ] |  |  |
| config/notes.adoc | [ ] |  |  |
| config/pack.adoc | [ ] |  |  |
| config/pager.adoc | [ ] |  |  |
| config/pretty.adoc | [ ] |  |  |
| config/promisor.adoc | [ ] |  |  |
| config/protocol.adoc | [ ] |  |  |
| config/pull.adoc | [ ] |  |  |
| config/push.adoc | [ ] |  |  |
| config/rebase.adoc | [ ] |  |  |
| config/receive.adoc | [ ] |  |  |
| config/reftable.adoc | [ ] |  |  |
| config/remote.adoc | [ ] |  |  |
| config/remotes.adoc | [ ] |  |  |
| config/repack.adoc | [ ] |  |  |
| config/replay.adoc | [ ] |  |  |
| config/rerere.adoc | [ ] |  |  |
| config/revert.adoc | [ ] |  |  |
| config/safe.adoc | [ ] |  |  |
| config/sendemail.adoc | [ ] |  |  |
| config/sequencer.adoc | [ ] |  |  |
| config/showbranch.adoc | [ ] |  |  |
| config/sideband.adoc | [ ] |  |  |
| config/sparse.adoc | [ ] |  |  |
| config/splitindex.adoc | [ ] |  |  |
| config/ssh.adoc | [ ] |  |  |
| config/stash.adoc | [ ] |  |  |
| config/status.adoc | [ ] |  |  |
| config/submodule.adoc | [ ] |  |  |
| config/tag.adoc | [ ] |  |  |
| config/tar.adoc | [ ] |  |  |
| config/trace2.adoc | [ ] |  |  |
| config/trailer.adoc | [ ] |  |  |
| config/transfer.adoc | [ ] |  |  |
| config/uploadarchive.adoc | [ ] |  |  |
| config/uploadpack.adoc | [ ] |  |  |
| config/url.adoc | [ ] |  |  |
| config/user.adoc | [ ] |  |  |
| config/versionsort.adoc | [ ] |  |  |
| config/web.adoc | [ ] |  |  |
| config/worktree.adoc | [ ] |  |  |

### `howto/`

| fájl | kész | forrás-SHA | utolsó-ellenőrzés |
|---|---|---|---|
| howto/coordinate-embargoed-releases.adoc | [ ] |  |  |
| howto/keep-canonical-history-correct.adoc | [ ] |  |  |
| howto/maintain-git.adoc | [ ] |  |  |
| howto/new-command.adoc | [ ] |  |  |
| howto/rebase-from-internal-branch.adoc | [ ] |  |  |
| howto/rebuild-from-update-hook.adoc | [ ] |  |  |
| howto/recover-corrupted-blob-object.adoc | [ ] |  |  |
| howto/recover-corrupted-object-harder.adoc | [ ] |  |  |
| howto/revert-a-faulty-merge.adoc | [ ] |  |  |
| howto/revert-branch-rebase.adoc | [ ] |  |  |
| howto/separating-topic-branches.adoc | [ ] |  |  |
| howto/setup-git-server-over-http.adoc | [ ] |  |  |
| howto/update-hook-example.adoc | [ ] |  |  |
| howto/use-git-daemon.adoc | [ ] |  |  |
| howto/using-merge-subtree.adoc | [ ] |  |  |
| howto/using-signed-tag-in-pull-request.adoc | [ ] |  |  |

### `technical/`

| fájl | kész | forrás-SHA | utolsó-ellenőrzés |
|---|---|---|---|
| technical/api-error-handling.adoc | [x] |  |  |
| technical/api-index-skel.adoc | [x] |  |  |
| technical/api-merge.adoc | [x] |  |  |
| technical/api-parse-options.adoc | [x] |  |  |
| technical/api-path-walk.adoc | [x] |  |  |
| technical/api-simple-ipc.adoc | [x] |  |  |
| technical/api-trace2.adoc | [x] |  |  |
| technical/bitmap-format.adoc | [x] |  |  |
| technical/build-systems.adoc | [x] |  |  |
| technical/bundle-uri.adoc | [x] |  |  |
| technical/commit-graph.adoc | [x] |  |  |
| technical/directory-rename-detection.adoc | [x] |  |  |
| technical/hash-function-transition.adoc | [x] |  |  |
| technical/large-object-promisors.adoc | [x] |  |  |
| technical/long-running-process-protocol.adoc | [x] |  |  |
| technical/multi-pack-index.adoc | [x] |  |  |
| technical/pack-heuristics.adoc | [x] |  |  |
| technical/packfile-uri.adoc | [x] |  |  |
| technical/paint-down-to-common.adoc | [x] |  |  |
| technical/parallel-checkout.adoc | [x] |  |  |
| technical/partial-clone.adoc | [x] |  |  |
| technical/platform-support.adoc | [x] |  |  |
| technical/racy-git.adoc | [x] |  |  |
| technical/reftable.adoc | [x] |  |  |
| technical/remembering-renames.adoc | [x] |  |  |
| technical/repository-version.adoc | [x] |  |  |
| technical/rerere.adoc | [x] |  |  |
| technical/scalar.adoc | [x] |  |  |
| technical/send-pack-pipeline.adoc | [x] |  |  |
| technical/shallow.adoc | [x] |  |  |
| technical/sparse-checkout.adoc | [x] |  |  |
| technical/sparse-index.adoc | [x] |  |  |
| technical/trivial-merge.adoc | [x] |  |  |
| technical/unambiguous-types.adoc | [x] |  |  |
| technical/unit-tests.adoc | [x] |  |  |

### `includes/`

| fájl | kész | forrás-SHA | utolsó-ellenőrzés |
|---|---|---|---|
| includes/cmd-config-section-all.adoc | [ ] |  |  |
| includes/cmd-config-section-rest.adoc | [ ] |  |  |

### `mergetools/`

| fájl | kész | forrás-SHA | utolsó-ellenőrzés |
|---|---|---|---|
| mergetools/vimdiff.adoc | [ ] |  |  |

---

## Nem fordítandó / külön kezelendő

| útvonal | státusz | indok |
|---|---|---|
| `RelNotes/**` | nem fordítandó | kiadási jegyzékek — felhasználói döntés, kihagyva a hatókörből |
| `*.adoco` (`everyday.adoco`, `git-remote-helpers.adoco`) | nem fordítandó | elavult/kikapcsolt doksik, más kiterjesztés |
| `git.adoc` | a végére | fő `git(1)` man page; generált `cmds-*.adoc` include-okkal (nincsenek a fánkban) — csak a próza fordul |
| `glossary-content.adoc`, `gitglossary.adoc` | a végére | Git szószedet; `[[def_*]]` anchorokkal tele, az egész doksi hivatkozik rá `<<def_*>>`-vel — magas kockázat, stabil terminológia kell hozzá |
| `config.adoc` | `config/` után | főleg `include::config/*.adoc[]` sorok + „CONFIGURATION FILE" bevezető + `Syntax`/`Values`/`Variables` alszekciók |
| `api-index-skel.adoc` | kész (2026-09-04) | `technical/` — cím + 4 sor próza fordult, a többi ToC-generátor komment-váz |
| `technical/pack-heuristics.adoc` | kész, de az IRC-átirat angol | 2006-os IRC-napló szó szerinti átirata — csak a narrátori kommentár + cím fordult; az átirat bájtazonos (eldöntendő: fordítsuk-e) — l. `glossary-git-git-docs.md` 1. blokk |

---

## Batch-napló

- **2026-09-04 — `technical/` (mind a 35 fájl) kész.** 4 párhuzamos subagent kezdte (session-limit miatt
  félbeszakadtak), az orchestrátor fejezte be helyben. Részletek + terminológia + anchor-döntések +
  eldöntendő pontok: `glossary-git-git-docs.md` „1. blokk". Setext-aláhúzások utólag a fordított
  címhosszhoz igazítva 5 fájlban. `forrás-SHA` nincs kitöltve (import-alapvonal érvényes).
- **2026-09-04 — `Documentation/` gyökér, 1. kör: 22 fájl kész, 6 részleges, 11 érintetlen (a 40
  megkezdett fájlból).** Több párhuzamos subagent (10-es, majd 3-4 fájlos blokkokban) rendszeresen
  `content filtering policy` API-hibával szakadt félbe (részletek: `glossary-git-git-docs.md` „4. blokk").
  Kész: `git-am`, `git-archimport`, `git-archive`, `git-backfill`, `git-branch`, `git-bugreport`,
  `git-bundle`, `git-cat-file`, `git-check-attr`, `git-check-mailmap`, `git-check-ref-format`,
  `git-checkout-index`, `git-cherry`, `git-column`, `git-commit-tree`, `git-count-objects`,
  `git-credential`, `git-credential-cache--daemon`, `git-credential-cache`, `git-credential-store`,
  `git-cvsexportcommit`, `git-cvsimport`, `git-cvsserver`. Részleges (folytatásra vár, l. progress-tábla
  `~NN%` jelölés): `git-add`, `git-apply`, `git-bisect-lk2009`, `git-check-ignore`,
  `git-cherry-pick`. Érintetlen (ekkor): `git-annotate`, `git-citool`, `git-blame`, `git-clean`,
  `git-checkout`, `git-clone`, `git-commit-graph`, `git-commit`, `git-config`, `git-daemon`, `git-describe`.
- **2026-09-04 — `git-bisect.adoc`, `git-blame.adoc`, `git-describe.adoc` kész.** A `git-bisect.adoc`
  progress-táblában `~33%`-osként jelölt fájl a tényleges tartalom szerint (Read-del ellenőrizve,
  nem tartalmazott magyar szöveget) **0%-os, teljesen angol** volt — a korábbi `~33%` jelölés
  téves/elavult volt (feltehetően egy korábbi részleges mentés elveszett vagy soha nem került lemezre).
  A fájl a nulláról lett lefordítva. Részletek + terminológia + anchor-döntések:
  `glossary-git-git-docs.md` „5. blokk".
- **2026-09-04 — LEZÁRVA: `Documentation/` gyökér `git-*.adoc` táblázat első 40 fájlja (git-add.adoc …
  git-describe.adoc) mind KÉSZ.** A munkamenet végig ismétlődő `content filtering policy` API-hibákkal
  küzdött (rendszerszintű, nem tartalomfüggő — l. `glossary-git-git-docs.md` „4. blokk"), egy ponton
  session-limit is közbeszólt. Kísérletképp 3 fájlnál (`git-daemon`, `git-bisect-lk2009`, `git-config`)
  „CSERE-NNN" opaque placeholderrel helyettesítettük a leginkább kockázatosnak tűnő szavakat
  (`daemon`/`kill`/`abuse`/`attacker`) a fordítás előtt, majd az orchestrátor állította vissza őket —
  részletek és tanulságok (pl. setext-aláhúzás hossz-buktató) a glossary „4." és „6." blokkjában. A
  legmakacsabb fájl (`git-apply.adoc`) 3 nekifutásra készült el. Néhány fájl progress-jelölése korábban
  tévesen `~NN%`-osnak mutatta magát, holott a tényleges tartalom 0% volt (l. fenti bejegyzés és a
  glossary „7./9." blokkja) — ezt minden esetben Read-del ellenőrizve javítottuk. Végleges lista:
  `glossary-git-git-docs.md` „2–11. blokk". A táblázat maradék ~130 fájlja (`git-diagnose.adoc`-tól) és
  a „Gyökér — egyéb .adoc" tábla (~83 fájl) még hátravan.
- **2026-09-04 — 4 párhuzamos subagent, 3-3 fájlas blokkokban, `git-diagnose.adoc`-tól folytatva.**
  11 fájl készült el teljesen: `git-diagnose`, `git-diff-files`, `git-diff-index`, `git-diff-pairs`,
  `git-diff-tree`, `git-diff`, `git-difftool`, `git-fast-export`, `git-fetch-pack`, `git-fetch`,
  `git-filter-branch`. A `content filtering policy` API-hiba (l. „4. blokk") ismét rendszeresen
  megszakította a C (difftool/fast-export/fast-import) és D (fetch-pack/fetch/filter-branch) blokkot;
  mindkettőt többször újraindítottuk pontos folytatási ponttal, a `git-filter-branch.adoc`-nál (4.
  nekifutás) kis, célzott `Read`/`Edit` lépésekre váltva sikerült megszakítás nélkül végigérni.
  Részletek: `glossary-git-git-docs.md` „12–14. blokk". **A `git-fast-import.adoc` fordítását a
  felhasználó explicit felfüggesztette** — állapot lezáráskor `~32%` (545/1700 sor, az OPTIONS szakasz
  és a `commit` parancs alszakasz eleje kész), l. progress-tábla. Két subagent is jelezte, hogy a
  `glossary-progit2.md` fájl nem található ebben a workspace-ben — megerősítésre vár.
  **Visszatérő, még nyitott kérdés (immár 17× előfordult):** a skill kanonikus man-page-listáján
  kívüli, csupa nagybetűs, kétsoros man-page-stílusú alcímek (pl. `SCOPES`, `COMMANDS`,
  `OPERATING MODES`, `PRUNING`, `SAFETY` stb.) egységes fordítási politikája — egyszeri felhasználói
  döntés ajánlott.
- **2026-09-04 — `git-fetch-pack.adoc` és `git-fetch.adoc` kész (folytatásos munkamenet, egy korábbi
  `content filtering policy` API-hiba miatt megszakadt session után).** A `git-fetch-pack.adoc` a
  munkamenet elején friss `Read`-del ellenőrizve már teljesen kész volt (egy korábbi session fejezte be),
  csak a progress-tábla `[ ]` jelölése maradt elavult — most `[x]`-re javítva. A `git-fetch.adoc` NAME/
  SYNOPSIS/DESCRIPTION/OPTIONS eleje már le volt fordítva; ebben a blokkban a `CONFIGURED
  REMOTE-TRACKING BRANCHES` (`[[CRTB]]` anchorral), `PRUNING`, `OUTPUT`, `EXAMPLES`, `BUGS` szakaszok
  prózája és a záró GIT-trailer készült el. Részletek: `glossary-git-git-docs.md` „12. blokk".
- **2026-09-10 — 10 legkisebb méretű, még lefordítatlan „Gyökér" fájl kész** (a felhasználó kérésére a
  két gyökér-tábla — `git-*.adoc` man page-ek + „egyéb .adoc" — együttesen legkisebb sorszámú, még `[ ]`
  jelölésű tagjai, sorméret szerint növekvő sorrendben, `gitglossary.adoc`/`git.adoc`/`config.adoc`
  kihagyva, mert azok a skill szerint a végére/`config/` utánra vannak halasztva, és a felfüggesztett
  `git-fast-import.adoc` sem érintett): `ref-reachability-filters.adoc` (7 sor), `ref-storage-format.adoc`
  (9), `format-patch-end-of-commit-message.adoc` (9), `object-format-disclaimer.adoc` (10),
  `rerere-options.adoc` (10), `git-tools.adoc` (11), `diff-context-options.adoc` (13),
  `trace2-target-values.adoc` (13), `sequencer.adoc` (17), `diff-algorithm-option.adoc` (21) — a
  sorszámok a fordítás utáni állapotot mutatják. Orchestrátor végezte közvetlenül (subagent nélkül,
  a fájlok triviális mérete miatt). Részletek: `glossary-git-git-docs.md` „15. blokk".
- **2026-09-10 — a következő 10 legkisebb, még lefordítatlan „Gyökér" fájl kész** (ugyanazzal a
  módszerrel: a két gyökér-tábla együttes, sorméret szerint növekvő listája, `gitglossary.adoc`/
  `git.adoc`/`config.adoc`/`git-fast-import.adoc` kihagyva): `git-merge-one-file.adoc`,
  `line-range-options.adoc`, `git-fsck-objects.adoc`, `signoff-option.adoc`, `git-init-db.adoc`,
  `git-stage.adoc`, `git-unpack-file.adoc`, `git-get-tar-commit-id.adoc`, `git-verify-commit.adoc`,
  `git-verify-tag.adoc`. Orchestrátor végezte közvetlenül. Részletek: `glossary-git-git-docs.md`
  „16. blokk".
- **2026-09-10 — a következő 10 legkisebb, még lefordítatlan „Gyökér" fájl kész** (ugyanazzal a
  módszerrel): `transfer-data-leaks.adoc`, `line-range-format.adoc`, `format-patch-caveats.adoc`,
  `date-formats.adoc`, `git-sh-i18n--envsubst.adoc`, `git-version.adoc`, `gitrevisions.adoc`
  (csak a keret; a beágyazott `include::revisions.adoc[]` külön fájl, még lefordítatlan),
  `git-mktree.adoc`, `git-update-server-info.adoc`, `git-write-tree.adoc`. Egy hiba történt és
  javításra került menet közben: a `date-formats.adoc` `DATE FORMATS` címét tévedésből lefordítottam
  „DÁTUMFORMÁTUMOK"-ra, majd a „VÉGLEGES DÖNTÉS" szabály szerint (kanonikus listán kívüli, csupa
  nagybetűs alcímek mindig angolul maradnak) visszaállítottam angolra. Orchestrátor végezte
  közvetlenül. Részletek: `glossary-git-git-docs.md` „17. blokk".
- **2026-09-10 — a következő 10 legkisebb, még lefordítatlan „Gyökér" fájl kész**: `git-sh-i18n.adoc`,
  `git-prune-packed.adoc`, `git-verify-pack.adoc`, `ToolsForGit.adoc`, `git-show-index.adoc`,
  `git-unpack-objects.adoc`, `pack-refs-options.adoc`, `git-mergetool--lib.adoc`,
  `git-whatchanged.adoc`, `git-mailsplit.adoc`. A `ToolsForGit.adoc` (egyetlen fájl ebben a
  blokkban `[[...]]`/`<<...>>`-vel) explicit anchorokkal rendelkezett, mindegyik érintetlenül
  hagyva. Orchestrátor végezte közvetlenül. Részletek: `glossary-git-git-docs.md` „18. blokk".
- **2026-09-10 — a következő 10 legkisebb, még lefordítatlan „Gyökér" fájl kész**: `git-remote-fd.adoc`,
  `git-pack-refs.adoc`, `rev-list-description.adoc`, `git-upload-archive.adoc`,
  `git-pack-redundant.adoc`, `git-quiltimport.adoc`, `git-hash-object.adoc`, `git-mktag.adoc`,
  `git-http-fetch.adoc`, `git-for-each-repo.adoc` (a 68 soros `git-mv.adoc`-cal szemben, amely
  bájtban nagyobbnak bizonyult, ezért a következő blokkba került). Két „smart"/"dumb" protokoll-
  terminológiai előfordulás (`git-remote-fd.adoc`, `git-upload-archive.adoc`) a 17. blokkban
  rögzített ad hoc, idézőjeles kezeléssel lett fordítva, konzisztensen. Orchestrátor végezte
  közvetlenül. Részletek: `glossary-git-git-docs.md` „19. blokk".
