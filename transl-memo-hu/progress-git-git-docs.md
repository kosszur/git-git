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
| git-fmt-merge-msg.adoc | [x] |  | 2026-09-10 |
| git-for-each-ref.adoc | [x] |  | 2026-09-11 |
| git-for-each-repo.adoc | [x] |  | 2026-09-10 |
| git-format-patch.adoc | [x] |  | 2026-09-11 |
| git-format-rev.adoc | [x] |  | 2026-09-10 |
| git-fsck-objects.adoc | [x] |  | 2026-09-10 |
| git-fsck.adoc | [x] |  | 2026-09-10 |
| git-fsmonitor--daemon.adoc | [x] |  | 2026-09-10 |
| git-gc.adoc | [x] |  | 2026-09-10 |
| git-get-tar-commit-id.adoc | [x] |  | 2026-09-10 |
| git-grep.adoc | [x] |  | 2026-09-10 |
| git-gui.adoc | [x] |  | 2026-09-10 |
| git-hash-object.adoc | [x] |  | 2026-09-10 |
| git-help.adoc | [x] |  | 2026-09-10 |
| git-history.adoc | [x] |  | 2026-09-10 |
| git-hook.adoc | [x] |  | 2026-09-10 |
| git-http-backend.adoc | [x] |  | 2026-09-10 |
| git-http-fetch.adoc | [x] |  | 2026-09-10 |
| git-http-push.adoc | [x] |  | 2026-09-10 |
| git-imap-send.adoc | [x] |  | 2026-09-10 |
| git-index-pack.adoc | [x] |  | 2026-09-10 |
| git-init-db.adoc | [x] |  | 2026-09-10 |
| git-init.adoc | [x] |  | 2026-09-10 |
| git-instaweb.adoc | [x] |  | 2026-09-10 |
| git-interpret-trailers.adoc | [x] |  | 2026-09-11 |
| git-last-modified.adoc | [x] |  | 2026-09-10 |
| git-log.adoc | [x] |  | 2026-09-10 |
| git-ls-files.adoc | [x] |  | 2026-09-10 |
| git-ls-remote.adoc | [x] |  | 2026-09-10 |
| git-ls-tree.adoc | [x] |  | 2026-09-10 |
| git-mailinfo.adoc | [x] |  | 2026-09-10 |
| git-mailsplit.adoc | [x] |  | 2026-09-10 |
| git-maintenance.adoc | [x] |  | 2026-09-11 |
| git-merge-base.adoc | [x] |  | 2026-09-10 |
| git-merge-file.adoc | [x] |  | 2026-09-10 |
| git-merge-index.adoc | [x] |  | 2026-09-10 |
| git-merge-one-file.adoc | [x] |  | 2026-09-10 |
| git-merge-tree.adoc | [x] |  | 2026-09-10 |
| git-merge.adoc | [x] |  | 2026-09-11 |
| git-mergetool--lib.adoc | [x] |  | 2026-09-10 |
| git-mergetool.adoc | [x] |  | 2026-09-10 |
| git-mktag.adoc | [x] |  | 2026-09-10 |
| git-mktree.adoc | [x] |  | 2026-09-10 |
| git-multi-pack-index.adoc | [x] |  | 2026-09-10 |
| git-mv.adoc | [x] |  | 2026-09-10 |
| git-name-rev.adoc | [x] |  | 2026-09-10 |
| git-notes.adoc | [x] |  | 2026-09-11 |
| git-p4.adoc | [x] |  | 2026-09-11 |
| git-pack-objects.adoc | [x] |  | 2026-09-11 |
| git-pack-redundant.adoc | [x] |  | 2026-09-10 |
| git-pack-refs.adoc | [x] |  | 2026-09-10 |
| git-patch-id.adoc | [x] |  | 2026-09-10 |
| git-prune-packed.adoc | [x] |  | 2026-09-10 |
| git-prune.adoc | [x] |  | 2026-09-10 |
| git-pull.adoc | [x] |  | 2026-09-10 |
| git-push.adoc | [x] |  | 2026-09-11 |
| git-quiltimport.adoc | [x] |  | 2026-09-10 |
| git-range-diff.adoc | [x] |  | 2026-09-10 |
| git-read-tree.adoc | [x] |  | 2026-09-11 |
| git-rebase.adoc | [x] |  | 2026-09-11 |
| git-receive-pack.adoc | [x] |  | 2026-09-10 |
| git-reflog.adoc | [x] |  | 2026-09-10 |
| git-refs.adoc | [x] |  | 2026-09-10 |
| git-remote-ext.adoc | [x] |  | 2026-09-10 |
| git-remote-fd.adoc | [x] |  | 2026-09-10 |
| git-remote.adoc | [x] |  | 2026-09-10 |
| git-repack.adoc | [x] |  | 2026-09-11 |
| git-replace.adoc | [x] |  | 2026-09-10 |
| git-replay.adoc | [x] |  | 2026-09-10 |
| git-repo.adoc | [x] |  | 2026-09-10 |
| git-request-pull.adoc | [x] |  | 2026-09-10 |
| git-rerere.adoc | [x] |  | 2026-09-10 |
| git-reset.adoc | [x] |  | 2026-09-11 |
| git-restore.adoc | [x] |  | 2026-09-10 |
| git-rev-list.adoc | [x] |  | 2026-09-10 |
| git-rev-parse.adoc | [x] |  | 2026-09-11 |
| git-revert.adoc | [x] |  | 2026-09-10 |
| git-rm.adoc | [x] |  | 2026-09-10 |
| git-send-email.adoc | [x] |  | 2026-09-11 |
| git-send-pack.adoc | [x] |  | 2026-09-10 |
| git-sh-i18n--envsubst.adoc | [x] |  | 2026-09-10 |
| git-sh-i18n.adoc | [x] |  | 2026-09-10 |
| git-sh-setup.adoc | [x] |  | 2026-09-10 |
| git-shell.adoc | [x] |  | 2026-09-10 |
| git-shortlog.adoc | [x] |  | 2026-09-10 |
| git-show-branch.adoc | [x] |  | 2026-09-10 |
| git-show-index.adoc | [x] |  | 2026-09-10 |
| git-show-ref.adoc | [x] |  | 2026-09-10 |
| git-show.adoc | [x] |  | 2026-09-10 |
| git-sparse-checkout.adoc | [x] |  | 2026-09-11 |
| git-stage.adoc | [x] |  | 2026-09-10 |
| git-stash.adoc | [x] |  | 2026-09-11 |
| git-status.adoc | [x] |  | 2026-09-11 |
| git-stripspace.adoc | [x] |  | 2026-09-10 |
| git-submodule.adoc | [x] |  | 2026-09-11 |
| git-svn.adoc | [x] |  | 2026-09-11 |
| git-switch.adoc | [x] |  | 2026-09-10 |
| git-symbolic-ref.adoc | [x] |  | 2026-09-10 |
| git-tag.adoc | [x] |  | 2026-09-11 |
| git-tools.adoc | [x] |  | 2026-09-10 |
| git-unpack-file.adoc | [x] |  | 2026-09-10 |
| git-unpack-objects.adoc | [x] |  | 2026-09-10 |
| git-update-index.adoc | [x] |  | 2026-09-11 |
| git-update-ref.adoc | [x] |  | 2026-09-10 |
| git-update-server-info.adoc | [x] |  | 2026-09-10 |
| git-upload-archive.adoc | [x] |  | 2026-09-10 |
| git-upload-pack.adoc | [x] |  | 2026-09-10 |
| git-url-parse.adoc | [x] |  | 2026-09-10 |
| git-var.adoc | [x] |  | 2026-09-10 |
| git-verify-commit.adoc | [x] |  | 2026-09-10 |
| git-verify-pack.adoc | [x] |  | 2026-09-10 |
| git-verify-tag.adoc | [x] |  | 2026-09-10 |
| git-version.adoc | [x] |  | 2026-09-10 |
| git-web--browse.adoc | [x] |  | 2026-09-10 |
| git-whatchanged.adoc | [x] |  | 2026-09-10 |
| git-worktree.adoc | [x] |  | 2026-09-11 |
| git-write-tree.adoc | [x] |  | 2026-09-10 |

### Gyökér — egyéb `.adoc` (guide-ok, option-fragmensek, includimport)

| fájl | kész | forrás-SHA | utolsó-ellenőrzés |
|---|---|---|---|
| BreakingChanges.adoc | [x] |  | 2026-09-10 |
| DecisionMaking.adoc | [x] |  | 2026-09-10 |
| MyFirstContribution.adoc | [ ] |  |  |
| MyFirstObjectWalk.adoc | [x] |  | 2026-09-11 |
| ReviewingGuidelines.adoc | [x] |  | 2026-09-10 |
| ToolsForGit.adoc | [x] |  | 2026-09-10 |
| blame-options.adoc | [x] |  | 2026-09-10 |
| config.adoc | [ ] |  |  |
| date-formats.adoc | [x] |  | 2026-09-10 |
| diff-algorithm-option.adoc | [x] |  | 2026-09-10 |
| diff-context-options.adoc | [x] |  | 2026-09-10 |
| diff-format.adoc | [x] |  | 2026-09-10 |
| diff-generate-patch.adoc | [x] |  | 2026-09-10 |
| diff-options.adoc | [x] |  | 2026-09-11 |
| fetch-options.adoc | [x] |  | 2026-09-10 |
| for-each-ref-options.adoc | [x] |  | 2026-09-10 |
| format-patch-caveats.adoc | [x] |  | 2026-09-10 |
| format-patch-end-of-commit-message.adoc | [x] |  | 2026-09-10 |
| fsck-msgids.adoc | [x] |  | 2026-09-10 |
| git.adoc | [ ] |  |  |
| gitattributes.adoc | [x] |  | 2026-09-11 |
| gitcli.adoc | [x] |  | 2026-09-10 |
| gitcore-tutorial.adoc | [ ] |  |  |
| gitcredentials.adoc | [x] |  | 2026-09-10 |
| gitcvs-migration.adoc | [x] |  | 2026-09-10 |
| gitdatamodel.adoc | [x] |  | 2026-09-10 |
| gitdiffcore.adoc | [x] |  | 2026-09-10 |
| giteveryday.adoc | [x] |  | 2026-09-11 |
| gitfaq.adoc | [x] |  | 2026-09-11 |
| gitformat-bundle.adoc | [x] |  | 2026-09-10 |
| gitformat-chunk.adoc | [x] |  | 2026-09-10 |
| gitformat-commit-graph.adoc | [x] |  | 2026-09-10 |
| gitformat-index.adoc | [x] |  | 2026-09-11 |
| gitformat-loose.adoc | [x] |  | 2026-09-10 |
| gitformat-pack.adoc | [x] |  | 2026-09-11 |
| gitformat-signature.adoc | [x] |  | 2026-09-10 |
| gitglossary.adoc | [ ] |  |  |
| githooks.adoc | [x] |  | 2026-09-11 |
| gitignore.adoc | [x] |  | 2026-09-10 |
| gitk.adoc | [x] |  | 2026-09-10 |
| gitmailmap.adoc | [x] |  | 2026-09-10 |
| gitmodules.adoc | [x] |  | 2026-09-10 |
| gitnamespaces.adoc | [x] |  | 2026-09-10 |
| gitpacking.adoc | [x] |  | 2026-09-10 |
| gitprotocol-capabilities.adoc | [x] |  | 2026-09-10 |
| gitprotocol-common.adoc | [x] |  | 2026-09-10 |
| gitprotocol-http.adoc | [x] |  | 2026-09-11 (NAME-sor utólag javítva 2026-09-11) |
| gitprotocol-pack.adoc | [x] |  | 2026-09-11 |
| gitprotocol-v2.adoc | [x] |  | 2026-09-11 |
| gitremote-helpers.adoc | [x] |  | 2026-09-11 |
| gitrepository-layout.adoc | [x] |  | 2026-09-10 |
| gitrevisions.adoc | [x] |  | 2026-09-10 |
| gitsubmodules.adoc | [x] |  | 2026-09-10 |
| gittutorial-2.adoc | [x] |  | 2026-09-11 |
| gittutorial.adoc | [x] |  | 2026-09-11 |
| gitweb.adoc | [x] |  | 2026-09-11 |
| gitweb.conf.adoc | [x] |  | 2026-09-11 |
| gitworkflows.adoc | [x] |  | 2026-09-11 |
| glossary-content.adoc | [ ] |  |  |
| i18n.adoc | [x] |  | 2026-09-10 |
| line-range-format.adoc | [x] |  | 2026-09-10 |
| line-range-options.adoc | [x] |  | 2026-09-10 |
| merge-options.adoc | [x] |  | 2026-09-10 |
| merge-strategies.adoc | [x] |  | 2026-09-10 |
| object-format-disclaimer.adoc | [x] |  | 2026-09-10 |
| pack-refs-options.adoc | [x] |  | 2026-09-10 |
| pretty-formats.adoc | [x] |  | 2026-09-11 |
| pretty-options.adoc | [x] |  | 2026-09-10 |
| pull-fetch-param.adoc | [x] |  | 2026-09-10 |
| ref-reachability-filters.adoc | [x] |  | 2026-09-10 |
| ref-storage-format.adoc | [x] |  | 2026-09-10 |
| rerere-options.adoc | [x] |  | 2026-09-10 |
| rev-list-description.adoc | [x] |  | 2026-09-10 |
| rev-list-options.adoc | [ ] |  |  |
| revisions.adoc | [x] |  | 2026-09-11 |
| scalar.adoc | [x] |  | 2026-09-10 |
| sequencer.adoc | [x] |  | 2026-09-10 |
| signoff-option.adoc | [x] |  | 2026-09-10 |
| trace2-target-values.adoc | [x] |  | 2026-09-10 |
| transfer-data-leaks.adoc | [x] |  | 2026-09-10 |
| urls-remotes.adoc | [x] |  | 2026-09-10 |
| urls.adoc | [x] |  | 2026-09-10 |
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
| howto/coordinate-embargoed-releases.adoc | [x] |  | 2026-09-10 |
| howto/keep-canonical-history-correct.adoc | [x] |  | 2026-09-10 |
| howto/maintain-git.adoc | [x] |  | 2026-09-10 |
| howto/new-command.adoc | [x] |  | 2026-09-10 |
| howto/rebase-from-internal-branch.adoc | [x] |  | 2026-09-10 |
| howto/rebuild-from-update-hook.adoc | [x] |  | 2026-09-10 |
| howto/recover-corrupted-blob-object.adoc | [x] |  | 2026-09-10 |
| howto/recover-corrupted-object-harder.adoc | [x] |  | 2026-09-10 |
| howto/revert-a-faulty-merge.adoc | [x] |  | 2026-09-10 |
| howto/revert-branch-rebase.adoc | [x] |  | 2026-09-10 |
| howto/separating-topic-branches.adoc | [x] |  | 2026-09-10 |
| howto/setup-git-server-over-http.adoc | [x] |  | 2026-09-10 |
| howto/update-hook-example.adoc | [x] |  | 2026-09-10 |
| howto/use-git-daemon.adoc | [x] |  | 2026-09-10 |
| howto/using-merge-subtree.adoc | [x] |  | 2026-09-10 |
| howto/using-signed-tag-in-pull-request.adoc | [x] |  | 2026-09-10 |

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
- **2026-09-10 — a következő 10 legkisebb, még lefordítatlan „Gyökér" fájl kész**: `git-mv.adoc`,
  `git-url-parse.adoc`, `git-last-modified.adoc`, `git-symbolic-ref.adoc`, `git-fmt-merge-msg.adoc`,
  `git-merge-index.adoc`, `git-request-pull.adoc`, `git-prune.adoc`, `git-show.adoc`,
  `git-instaweb.adoc`. Orchestrátor végezte közvetlenül. Részletek: `glossary-git-git-docs.md`
  „20. blokk".
- **2026-09-10 — a következő 10 legkisebb, még lefordítatlan „Gyökér" fájl kész** (ugyanazzal a
  módszerrel; ebben a blokkban már 2–3 KB-os, 60–120 soros fájlok): `git-stripspace.adoc`,
  `gitnamespaces.adoc`, `i18n.adoc`, `git-sh-setup.adoc`, `git-shell.adoc`, `git-http-push.adoc`,
  `git-upload-pack.adoc`, `for-each-ref-options.adoc`, `git-var.adoc`, `gitprotocol-common.adoc`.
  A `gitprotocol-common.adoc` volt az egyetlen fájl `[[...]]` anchor-kezeléssel (2 defenzív anchor
  a nem man-page, Title Case alcímek fölé). Orchestrátor végezte közvetlenül. Részletek:
  `glossary-git-git-docs.md` „21. blokk".
- **2026-09-10 — a következő 10 legkisebb, még lefordítatlan „Gyökér" fájl kész** (ugyanazzal a
  módszerrel): `git-rev-list.adoc`, `gitformat-bundle.adoc`, `git-name-rev.adoc`, `git-gui.adoc`,
  `urls.adoc`, `gitmailmap.adoc`, `git-web--browse.adoc`, `git-patch-id.adoc`, `DecisionMaking.adoc`,
  `git-mailinfo.adoc`. A `DecisionMaking.adoc` NEM man page (minden Title Case címsor fordult, 4
  defenzív anchorral); a `git-gui.adoc` (2 anchor: `_examples`, `_other`), a `git-web--browse.adoc`
  (2 anchor) és a `gitformat-bundle.adoc` (1 anchor) Title Case `~~~~`/`----` alcímei is fordultak,
  aláhúzás pontos hosszra igazítva. Az `urls.adoc` `GIT URLS` címe (explicit `[[URLS]]` anchorral,
  csupa nagybetűs) a VÉGLEGES DÖNTÉS szerint angolul maradt — a `git-clone.adoc` már meglévő
  `<<URLS,GIT URL-ek>>` látható link-szövege ettől független, elfogadott választás. RFC 2119
  kulcsszavak (`MUST`/`MAY`/`CAN`/`NOT`) a `gitformat-bundle.adoc`-ban angolul maradtak (21. blokk
  döntése). Orchestrátor végezte közvetlenül. Részletek: `glossary-git-git-docs.md` „23. blokk"
  (a „22. blokk" számot egy párhuzamos `howto/`-munkamenet foglalta le).
- **2026-09-10 — `howto/` mappa: a 10 legkisebb méretű, még lefordítatlan fájl kész** (a felhasználó
  kérésére, sorméret/byte szerint növekvő sorrendben): `use-git-daemon.adoc`, `using-merge-subtree.adoc`,
  `rebuild-from-update-hook.adoc`, `separating-topic-branches.adoc`, `new-command.adoc`,
  `recover-corrupted-blob-object.adoc`, `update-hook-example.adoc`, `rebase-from-internal-branch.adoc`,
  `keep-canonical-history-correct.adoc`, `revert-branch-rebase.adoc`. Ezek NEM man page-ek (e-mail-
  stílusú how-to cikkek), ezért a főcím és minden alcím fordult, setext-aláhúzás a fordított
  címhosszhoz igazítva (2 db ±1 elütés menet közben javítva). Az e-mail-fejléc (`From`/`To`/`Cc`/
  `Date`/`Subject`/`Message-ID`) bájtazonosan angolul maradt, az `Abstract:` docinfo-attribútum
  törzse fordult. A `-----`/`------------` körülhatárolt blokkok (parancspéldák, kimenetek,
  ASCII-art commit-gráfok, `#!/bin/bash` szkriptek, idézett e-mail-részletek, IRC-/doc-idézetek)
  és a szóközzel behúzott literál blokkok mind bájtazonosak. Egyik fájlban sincs `[[...]]`/`<<...>>`
  (a `rebuild-from-update-hook.adoc`-beli `<<\EOF` heredoc-jelölés kódblokkban van, nem xref).
  Orchestrátor végezte közvetlenül. Részletek: `glossary-git-git-docs.md` „22. blokk". A `howto/`
  mappából még 6 fájl hátravan (`coordinate-embargoed-releases`, `maintain-git`,
  `recover-corrupted-object-harder`, `revert-a-faulty-merge`, `setup-git-server-over-http`,
  `using-signed-tag-in-pull-request`).
- **2026-09-10 — `howto/` mappa: a maradék 6 fájl kész — a MAPPA MIND A 16 FÁJLON KÉSZ**:
  `using-signed-tag-in-pull-request.adoc`, `setup-git-server-over-http.adoc`, `revert-a-faulty-merge.adoc`,
  `recover-corrupted-object-harder.adoc`, `maintain-git.adoc` (595 sor, a mappa legnagyobb fájla),
  `coordinate-embargoed-releases.adoc`. NEM man page-ek; a főcím és minden alcím fordult, setext-
  aláhúzások a fordított címhosszhoz igazítva (~10 db ±1–2 elütés menet közben javítva). Verbatim
  angolul maradt: a `....` példa-e-mailek (`coordinate-embargoed-releases.adoc`), a C programok /
  shell-parancsok / hexdumpok / `git fsck` kimenet (`recover-corrupted-object-harder.adoc`), az
  ASCII-art commit-gráfok + Alan/Linus-idézet (`revert-a-faulty-merge.adoc`), a `$ git …` /
  `[config]` blokkok (`maintain-git.adoc`), és — kivételként — a `setup-git-server-over-http.adoc`
  **összes szóközzel behúzott sora** (2006-os, lazán formázott doksi: a behúzott tartalom
  AsciiDoc-literál-bekezdésként renderel, ezért bájtazonos maradt; csak a 0. oszlopból induló
  próza + felső szintű `- ` pontok + 6 szekciócím fordult). Egyik fájlban sincs `[[...]]`/`<<...>>`.
  Orchestrátor végezte közvetlenül. Részletek: `glossary-git-git-docs.md` „24. blokk" (a „23."
  számot egy párhuzamos „Gyökér"-munkamenet foglalta le).
- **2026-09-10 — a következő 5 legkisebb, még lefordítatlan „Gyökér" fájl kész** (a felhasználó
  5-ös bontást kért): `git-remote-ext.adoc`, `git-fsmonitor--daemon.adoc`, `git-merge-file.adoc`,
  `git-shortlog.adoc`, `urls-remotes.adoc`. Az `urls-remotes.adoc` include-cél fragmens
  (`git-clone`/`git-fetch`/`git-pull`/`git-push`/`git-ls-remote` `include`-olja): a `REMOTES` és
  `UPSTREAM BRANCHES` explicit `[[...]]` anchorral rendelkező, csupa nagybetűs címei a VÉGLEGES
  DÖNTÉS szerint angolul maradtak (rájuk `<<REMOTES,REMOTES>>` / `<<UPSTREAM-BRANCHES,...>>` xref
  mutat még lefordítatlan fájlokból), a 3 Title Case `~~~~` alcím viszont fordult, defenzív
  anchorral. `git-shortlog.adoc` `MAPPING AUTHORS` a VÉGLEGES DÖNTÉS szerint angolul maradt (a
  2026-09-04-i `git-blame.adoc`/`git-check-mailmap.adoc` „Szerzők leképezése" fordítás korábbi,
  a döntés csak előre hatályos). Orchestrátor végezte közvetlenül. Részletek:
  `glossary-git-git-docs.md` „25. blokk".
- **2026-09-10 — a következő 10 legkisebb, még lefordítatlan „Gyökér" fájl kész** (ugyanazzal a
  módszerrel: a két gyökér-tábla együttes, sorméret szerint növekvő listája, `gitglossary.adoc`/
  `git.adoc`/`config.adoc`/`git-fast-import.adoc`/`glossary-content.adoc` kihagyva): `pretty-options.adoc`,
  `pull-fetch-param.adoc`, `git-mergetool.adoc`, `gitformat-loose.adoc`, `gitformat-chunk.adoc`,
  `gitmodules.adoc`, `git-repo.adoc`, `git-refs.adoc`, `blame-options.adoc`, `merge-strategies.adoc`.
  A `gitformat-loose.adoc` (2 db `==` szakasz) és a `gitformat-chunk.adoc` (2 Title Case setext
  alcím + 1 „Examples" → „Példák") defenzív `[[...]]` anchort kapott. A `merge-strategies.adoc`
  `MERGE STRATEGIES` csupa nagybetűs setext-címe a VÉGLEGES DÖNTÉS szerint angolul maradt
  (konzisztensen a `git-cherry-pick.adoc` már meglévő „MERGE STRATEGIES szakaszát" fordításával).
  A `pull-fetch-param.adoc` `<<URLS,GIT URLS>>` látható szövegét `<<URLS,GIT URL-ek>>`-re írtuk át
  (a `git-clone.adoc` precedense, 23. blokk), a `<<REMOTES,REMOTES>>` és
  `<<CRTB,CONFIGURED REMOTE-TRACKING BRANCHES>>` angolul maradt. Orchestrátor végezte közvetlenül.
  Részletek: `glossary-git-git-docs.md` „26. blokk".
- **2026-09-10 — a következő 10 legkisebb, még lefordítatlan „Gyökér" fájl kész** (ugyanazzal a
  módszerrel; `gitglossary.adoc`/`git.adoc`/`config.adoc`/`git-fast-import.adoc`/`glossary-content.adoc`
  kihagyva): `git-ls-remote.adoc`, `git-send-pack.adoc`, `git-reflog.adoc`, `git-index-pack.adoc`,
  `git-ls-tree.adoc`, `git-replace.adoc`, `git-revert.adoc`, `ReviewingGuidelines.adoc`,
  `diff-format.adoc`, `gitformat-commit-graph.adoc`. A `git-commit-graph.adoc` (175 sor) a
  méretlistán ide esne, de már `[x]` (2026-09-04) — helyette a `gitformat-commit-graph.adoc` (186
  sor) került be. Defenzív `[[...]]` anchorok: `git-reflog.adoc` (4 db, „Opciók a `show`-hoz" stb.
  `~~~~` alcímek), `git-ls-tree.adoc` (`[[_output_format]]`), `git-revert.adoc` (0),
  `ReviewingGuidelines.adoc` (9 db, NEM man page — minden cím fordult), `diff-format.adoc` (3 db),
  `gitformat-commit-graph.adoc` (2 db `==` cím; a bináris format-spec törzse a
  reftable/hash-function-transition precedens szerint bájtazonosan angolul maradt). `SPECIFYING
  THE REFS` (`git-send-pack.adoc`), `MERGE STRATEGIES` (prózahivatkozás a `git-revert.adoc`-ban),
  `FIELD NAMES` (`git-ls-tree.adoc`) a VÉGLEGES DÖNTÉS szerint angolul. Orchestrátor végezte
  közvetlenül. Részletek: `glossary-git-git-docs.md` „27. blokk".
- **2026-09-10 — a következő 10 legkisebb, még lefordítatlan „Gyökér" fájl kész** (ugyanazzal a
  módszerrel: a két gyökér-tábla együttes, sorméret szerint növekvő listája, `gitglossary.adoc`/
  `git.adoc`/`config.adoc`/`git-fast-import.adoc`/`glossary-content.adoc` kihagyva): `git-gc.adoc`,
  `gitk.adoc`, `git-fsck.adoc`, `git-init.adoc`, `gitpacking.adoc`, `git-rm.adoc`,
  `git-multi-pack-index.adoc`, `gitcvs-migration.adoc`, `git-update-ref.adoc`,
  `diff-generate-patch.adoc`. Defenzív `[[...]]` anchorok: `gitk.adoc` (5 — mind vegyes
  kis-/nagybetűs vagy Title Case alcím: `_rev_list_options_and_arguments`, `_gitk_specific_options`,
  `_examples`, `_files`, `_history`), `git-fsck.adoc` (2 — `_extracted_diagnostics`,
  `_environment_variables`, mindkettő Title Case, NEM a csupa nagybetűs kanonikus alak),
  `gitpacking.adoc` (6 — `==`/`===` Title Case szakaszcímek), `git-rm.adoc` (3 — `~~~~` Title Case
  alcímek: `_using_git_commit_a`, `_using_git_add_a`, `_other_ways`), `gitcvs-migration.adoc` (6 —
  ez NEM man page, minden `----` szekciócím fordult), `diff-generate-patch.adoc` (1 új:
  `_combined_diff_format`; a meglévő `[[generate_patch_text_with_p]]` érintetlen, a hozzá tartozó
  cím szövege fordult — a `diff-options.adoc`-beli `<<generate_patch_text_with_p>>` xref emiatt a
  jövőben a fordított címszöveget jeleníti majd meg, ami kívánt). Csupa nagybetűs, kanonikus listán
  kívüli alcímek a VÉGLEGES DÖNTÉS szerint angolul: `AGGRESSIVE` (`git-gc.adoc`), `FSCK MESSAGES`
  (`git-fsck.adoc`), `TEMPLATE DIRECTORY` (`git-init.adoc`), `REMOVING FILES THAT HAVE DISAPPEARED
  FROM THE FILESYSTEM` / `SUBMODULES` (`git-rm.adoc`), `LOGGING UPDATES` (`git-update-ref.adoc`).
  Orchestrátor végezte közvetlenül. Részletek: `glossary-git-git-docs.md` „28. blokk".
- **2026-09-10 — a következő 5 legkisebb, még lefordítatlan „Gyökér" fájl kész** (a felhasználó
  5-ös bontást kért; ugyanaz a módszer, mint a 28. blokkban): `git-show-branch.adoc`,
  `git-show-ref.adoc`, `merge-options.adoc`, `git-format-rev.adoc`, `git-hook.adoc`. Anchor-kezelés:
  csak a `git-format-rev.adoc` érintett — a meglévő `[[io]]` és `[[examples]]` anchorok, valamint a
  rájuk mutató `<<io,INPUT AND OUTPUT FORMATS>>` és `<<examples,EXAMPLES>>` xref-ek (linkszöveggel
  együtt) **bájtazonosan** megmaradtak, mert a hozzájuk tartozó csupa nagybetűs címek angolul
  maradnak (a `<<REMOTES,REMOTES>>` 25. blokk precedense). A `merge-options.adoc` include-fragmens,
  csupa `ifdef::git-merge[]` / `ifdef::git-pull[]` / `ifndef::git-pull[]` / `endif::…` guard +
  `include::signoff-option.adoc[]` — mind bájtazonos, csak a `::` leírás-törzsek fordultak. Csupa
  nagybetűs, kanonikus listán kívüli alcímek angolul: `SUBCOMMANDS` / `WRAPPERS` (`git-hook.adoc`),
  `INPUT AND OUTPUT FORMAT` (`git-format-rev.adoc`). `git-format-rev.adoc` NAME `EXPERIMENTAL:`
  előtag → „KÍSÉRLETI:", a `(EXPERIMENTAL!)` synopsis-előtag → „(KÍSÉRLETI!)", a `THIS COMMAND IS
  EXPERIMENTAL…` csupa nagybetűs mondat lefordítva a nagybetűs formázás megtartásával (3. blokk
  precedens). Orchestrátor végezte közvetlenül. Részletek: `glossary-git-git-docs.md` „29. blokk".
- **2026-09-10 — a következő 5 legkisebb, még lefordítatlan „Gyökér" fájl kész** (a felhasználó
  5-ös bontást kért; a két gyökér-tábla együttes, sorméret szerint növekvő listája,
  `gitglossary.adoc`/`git.adoc`/`config.adoc`/`git-fast-import.adoc`/`glossary-content.adoc` kihagyva):
  `git-imap-send.adoc`, `git-log.adoc`, `git-replay.adoc`, `git-rerere.adoc`, `git-restore.adoc`.
  Egyik fájlban sem kellett új `[[...]]` anchort adni. A `git-replay.adoc` meglévő `[[output]]` és
  `[[exit-status]]` anchorjai + a rájuk mutató `<<output,OUTPUT>>` és `<<exit-status,EXIT STATUS>>`
  xref-ek (linkszöveggel együtt) **bájtazonosan** megmaradtak (az `OUTPUT` a 3. blokkban, az
  `EXIT STATUS` a kanonikus listán zárt kategória → a címek angolul maradnak, a 29. blokk
  `git-format-rev.adoc` precedense). Csupa nagybetűs, kanonikus listán kívüli alcímek a VÉGLEGES
  DÖNTÉS szerint angolul: `GETTING A LIST OF AVAILABLE FOLDERS`, `CAUTION` (`git-imap-send.adoc`),
  `DIFF FORMATTING` (`git-log.adoc`), `COMMANDS` (`git-rerere.adoc`). `git-replay.adoc` NAME
  `EXPERIMENTAL:` előtag → „KÍSÉRLETI:", `(EXPERIMENTAL!)` synopsis-előtag → „(KÍSÉRLETI!)", a
  `THIS COMMAND IS EXPERIMENTAL. THE BEHAVIOR MAY CHANGE.` csupa nagybetűs mondat lefordítva a
  nagybetűs formázás megtartásával (3./29. blokk precedens). Orchestrátor végezte közvetlenül.
  Részletek: `glossary-git-git-docs.md` „30. blokk".
- **2026-09-10 — a következő 5 legkisebb, még lefordítatlan „Gyökér" fájl kész** (a felhasználó
  5-ös bontást kért; ugyanaz a módszer): `gitformat-signature.adoc`, `git-help.adoc`, `git-pull.adoc`,
  `git-merge-base.adoc`, `git-history.adoc`. Defenzív `[[...]]` anchorok: `gitformat-signature.adoc`
  (3 — `==` Title Case szakaszcímek: `_tag_signatures`, `_commit_signatures`, `_mergetag_signatures`),
  `git-pull.adoc` (2 — `~~~~` Title Case alcímek: `_options_related_to_merging`,
  `_options_related_to_fetching`, mindkettő fordult; a rájuk mutató prózahivatkozás
  `"Options related to fetching"` → `„Fetcheléssel kapcsolatos opciók"` konzisztensen átírva),
  `git-merge-base.adoc` (1 — `_discussion_on_fork_point_mode`, „A fork-point mód tárgyalása"),
  `git-history.adoc` (3 — EXAMPLES `~~~~` Title Case alcímek: `_fixup_a_commit`, `_drop_a_commit`,
  `_split_a_commit`, mind fordult). `git-pull.adoc` xref-kezelés: `<<URLS,GIT URLS>>` →
  `<<URLS,GIT URL-ek>>` (23./26. blokk precedens), `<<REMOTES,REMOTES>>`,
  `<<UPSTREAM-BRANCHES,UPSTREAM BRANCHES>>`, `<<UPSTREAM-BRANCHES,upstream>>`,
  `<<DEFAULT-BEHAVIOUR,DEFAULT BEHAVIOUR>>` + `[[DEFAULT-BEHAVIOUR]]`, `<<fetch-refspec,_<refspec>_>>`
  **bájtazonos** (csupa nagybetűs / glossary-term / placeholder linkszöveg). Csupa nagybetűs,
  kanonikus listán kívüli alcímek a VÉGLEGES DÖNTÉS szerint angolul: `OPERATION MODES`
  (`git-merge-base.adoc`), `DEFAULT BEHAVIOUR` (`git-pull.adoc`), `COMMANDS` (`git-history.adoc`),
  `CONFIGURATION VARIABLES` + a `~~~~` config-kulcs-alcímek + `Note about konqueror` /
  `Note about git config --global` (`git-help.adoc` — a `Note about konqueror` a már lefordított
  `git-web--browse.adoc` `'Note about konqueror'` prózahivatkozásának precedense miatt marad angol);
  `LIMITATIONS` (`git-history.adoc`, kanonikus). `git-merge-base.adoc` `See also` (kis-nagybetűs,
  NEM a kanonikus `SEE ALSO`) — man page lévén bájtazonosan angolul hagyva (a `git-web--browse.adoc`
  precedens ellenére, amely NEM man page volt). NAME `EXPERIMENTAL:` → „KÍSÉRLETI:" és a
  `THIS COMMAND IS EXPERIMENTAL…` mondat nagybetűsen lefordítva (`git-history.adoc`, 3./29. blokk).
  Orchestrátor végezte közvetlenül. Részletek: `glossary-git-git-docs.md` „31. blokk".
- **2026-09-10 — a következő 5 legkisebb, még lefordítatlan „Gyökér" fájl kész** (a felhasználó
  5-ös bontást kért; ugyanaz a módszer): `fsck-msgids.adoc`, `gitignore.adoc`, `git-remote.adoc`,
  `git-receive-pack.adoc`, `gitcli.adoc`. Defenzív `[[...]]` anchorok: `gitcli.adoc` (7 — az
  `ENHANCED OPTION PARSER` alatti `~~~~` Title/sentence case alcímek: `_magic_options`,
  `_negating_options`, `_options_trump_configuration_and_environment`, `_aggregating_short_options`,
  `_abbreviating_long_options`, `_separating_argument_from_the_option`, `_magic_filename_options` —
  mind fordult, aláhúzás pontos hosszra igazítva). A többi 4 fájlban nincs `[[...]]`/`<<...>>`.
  `fsck-msgids.adoc` include-fragmens: a `` `msgid`:: `` címkék (`badDate`, `gitmodulesUrl`, …) és a
  `(ERROR)`/`(INFO)`/`(WARN)`/`(FATAL)`/`(IGNORE)` szintjelzők **bájtazonosak**, csak a leírás-törzs
  fordult; `0\{40}` attribútum-escape változatlan; nincs NAME/GIT. Csupa nagybetűs, kanonikus listán
  kívüli alcímek a VÉGLEGES DÖNTÉS szerint angolul: `PATTERN FORMAT` (`gitignore.adoc`),
  `COMMANDS`/`QUARANTINE ENVIRONMENT`/`PRE-RECEIVE HOOK`/`UPDATE HOOK`/`POST-RECEIVE HOOK`/
  `POST-UPDATE HOOK` (`git-remote.adoc`, `git-receive-pack.adoc`), `ENHANCED OPTION PARSER`/
  `NOTES ON FREQUENTLY CONFUSED OPTIONS` (`gitcli.adoc`); `NOTES` (`gitignore.adoc`) és
  `EXIT STATUS` (`git-remote.adoc`) kanonikus. `git-remote.adoc` `PRUNING` prózahivatkozás
  (git-fetch[1] szakaszra) angolul. RFC 2119 kulcsszavak angolul: `MUST NOT` (`git-receive-pack.adoc`),
  `SHOULD` / `*NOT*` (`gitcli.adoc`) — 21./23. blokk precedens. `gitcli.adoc` `"Values"`
  (git-config[1] szakasznév) angolul (a `config.adoc` még lefordítatlan). Orchestrátor végezte
  közvetlenül. Részletek: `glossary-git-git-docs.md` „32. blokk".
- **2026-09-10 — a következő 5 legkisebb, még lefordítatlan „Gyökér" fájl kész** (a felhasználó
  5-ös bontást kért; a két gyökér-tábla együttes, sorméret szerint növekvő listája,
  `gitglossary.adoc`/`git.adoc`/`config.adoc`/`git-fast-import.adoc`/`glossary-content.adoc` kihagyva):
  `gitsubmodules.adoc`, `git-switch.adoc`, `gitdatamodel.adoc`, `git-http-backend.adoc`,
  `git-range-diff.adoc`. A `gitdatamodel.adoc` volt a batch anchor-nehéz fájlja: 14 meglévő
  `[[...]]` anchor (`[[objects]]`, `[[commit]]`, `[[def]]`-szerű `[[object-id]]`, `[[branch]]`,
  `[[HEAD]]` stb.) **mind bájtazonosan** megmaradt; a rájuk mutató `<<id,látható szöveg>>` xref-ek
  vessző utáni része fordult (`<<objects,Objektumok>>`, `<<commit,commitok>>`, `<<HEAD,aktuális
  branchedet>>` stb.), a Git-objektum-típusnevek (`blob`/`tree`/`commit`/`tag`) a linkszövegben is
  angolul maradtak (magyar toldalékkal). A `gitdatamodel.adoc` `OBJECTS`/`REFERENCES`/`THE INDEX`/
  `REFLOGS` csupa nagybetűs, explicit anchorral ellátott szakaszcímei a VÉGLEGES DÖNTÉS szerint
  **angolul** maradtak (a 25. blokk `REMOTES`/`UPSTREAM BRANCHES` precedense). Defenzív `[[...]]`
  anchorok: `gitsubmodules.adoc` (4 — Title Case setext alcímek: `_the_configuration_of_submodules`,
  `_workflow_for_a_third_party_library`, `_workflow_for_an_artificially_split_repo`,
  `_implementation_details`), `git-range-diff.adoc` (1 — `[[_algorithm]]` az „Algoritmus" Title Case
  cím fölé; a prózában rá mutató `'Algorithm'` compat-mode hivatkozások `'Algoritmus'`-ra átírva).
  Csupa nagybetűs, kanonikus listán kívüli alcímek a VÉGLEGES DÖNTÉS szerint angolul: `FORMS` /
  `ACTIVE SUBMODULES` (`gitsubmodules.adoc`, + a `see FORMS below` / `"ACTIVE SUBMODULES" section`
  prózahivatkozások angolul), `SERVICES` / `URL TRANSLATION` (`git-http-backend.adoc`),
  `OUTPUT STABILITY` (`git-range-diff.adoc`). A `git-switch.adoc` `"DETACHED HEAD"` prózahivatkozása
  (git-checkout[1] szakaszra) angolul, idézőjelben. **smart/dumb protokoll-terminológia** eldöntve
  (`git-http-backend.adoc` volt a nyitott döntési függőség): `„smart" HTTP-protokoll` /
  `„dumb" HTTP-protokoll` — az angol jelző kettős idézőjelben, a 17./19./32. blokk ad hoc
  kezelésének folytatása. Orchestrátor végezte közvetlenül. Részletek:
  `glossary-git-git-docs.md` „33. blokk".
- **2026-09-10 — a következő 10 legkisebb, még lefordítatlan „Gyökér" fájl kész** (a felhasználó
  10-es bontást kért; a két gyökér-tábla együttes, sorméret szerint növekvő listája,
  `gitglossary.adoc`/`git.adoc`/`config.adoc`/`git-fast-import.adoc`/`glossary-content.adoc` kihagyva):
  `gitrepository-layout.adoc`, `gitdiffcore.adoc`, `gitcredentials.adoc`, `git-ls-files.adoc`,
  `git-merge-tree.adoc`, `BreakingChanges.adoc`, `git-grep.adoc`, `scalar.adoc`, `fetch-options.adoc`,
  `gitprotocol-capabilities.adoc`. Anchor-kezelés: `git-merge-tree.adoc` 8 meglévő `[[...]]` anchorja
  (`[[NEWMERGE]]`, `[[OUTPUT]]`, `[[MS]]`, `[[OIDTLT]]`, `[[CFI]]`, `[[IM]]`, `[[INPUT]]`,
  `[[DEPMERGE]]`) **bájtazonosan** megmaradt; a `~~~~` Title Case alcímek (`Merge status`,
  `OID of toplevel tree`, `Conflicted file info`, `Informational messages`) fordultak
  (aláhúzás pontos hosszra igazítva), a rájuk mutató `<<OIDTLT,...>>` / `<<CFI,...>>` / `<<IM,...>>`
  xref-ek vessző utáni része is fordult; a csupa nagybetűs `<<INPUT,INPUT FORMAT>>`,
  `<<OUTPUT,OUTPUT>>`, `<<DEPMERGE,DEPRECATED DESCRIPTION>>`, `<<NEWMERGE,DESCRIPTION>>` linkszöveg
  angolul maradt (VÉGLEGES DÖNTÉS). Defenzív `[[...]]` anchorok: `gitdiffcore.adoc` (7 — a Title
  Case setext szakaszcímek fölé: `_the_chain_of_operation` + 6 `diffcore-*` cím),
  `gitcredentials.adoc` (2 — `_available_helpers`, `_oauth` a `===` alcímek fölé),
  `BreakingChanges.adoc` (5 — NEM man page, minden `==`/`===` cím fordult: `_procedure`,
  `_git_3_0`, `_changes`, `_removals`, `_superseded_features_that_will_not_be_deprecated`),
  `scalar.adoc` (8 — a `~~~~` alparancs-alcímek fölé: `_clone`, `_list`, `_register`,
  `_unregister`, `_run`, `_reconfigure`, `_diagnose`, `_delete`). A `gitprotocol-capabilities.adoc`
  képességnév-alcímei (`multi_ack`, `thin-pack`, `side-band, side-band-64k`, …) protokoll-token
  identifikátorok → bájtazonosan angolul, aláhúzás változatlan, nincs defenzív anchor.
  Csupa nagybetűs, kanonikus listán kívüli alcímek a VÉGLEGES DÖNTÉS szerint angolul:
  `FIELD NAMES` / `EXCLUDE PATTERNS` (`git-ls-files.adoc`), `USAGE NOTES` / `MISTAKES TO AVOID` /
  `INPUT FORMAT` / `DEPRECATED DESCRIPTION` (`git-merge-tree.adoc`), `REQUESTING CREDENTIALS` /
  `AVOIDING REPETITION` / `CREDENTIAL CONTEXTS` / `CONFIGURATION OPTIONS` / `CUSTOM HELPERS`
  (`gitcredentials.adoc`), `NOTES ON THREADS` (`git-grep.adoc`), `RECOMMENDED CONFIG VALUES`
  (`scalar.adoc`). RFC 2119 kulcsszavak (`MUST`/`MUST NOT`/`SHOULD`/`MAY`) angolul
  (`gitprotocol-capabilities.adoc`, `BreakingChanges.adoc`). `PRUNING` / `OUTPUT` /
  `\"Configured Remote-tracking Branches\"` prózahivatkozások (`fetch-options.adoc`) angolul.
  A `fetch-options.adoc` include-fragmens: mind a 22 `ifdef/ifndef/endif::git-pull[]` guard és
  minden `::` opció-címke bájtazonos, nincs NAME/GIT. Orchestrátor végezte közvetlenül. Részletek:
  `glossary-git-git-docs.md` „34. blokk".
- **2026-09-11 — az 5 legkisebb méretű, még lefordítatlan „Gyökér" fájl kész** (a felhasználó
  5-ös bontást kért; a két gyökér-tábla együttes, sorméret szerint növekvő listája,
  `gitglossary.adoc`/`git.adoc`/`config.adoc`/`git-fast-import.adoc`/`glossary-content.adoc` kihagyva):
  `git-repack.adoc` (367 sor), `git-notes.adoc` (397), `git-merge.adoc` (412),
  `gitformat-index.adoc` (424), `revisions.adoc` (424, a `gitrevisions.adoc` `include`-célja).
  Anchor-kezelés: `git-notes.adoc` meglévő `[[CONFIGURATION]]` anchorja + a `<<CONFIGURATION,CONFIGURATION>>`
  xref **bájtazonos** (kanonikus cím, angolul marad). `gitformat-index.adoc` (11 db `==`/`===` cím,
  format-spec doksi) és `revisions.adoc` (4 Title Case setext alcím) defenzív `[[...]]` anchorokat
  kapott — l. `glossary-git-git-docs.md` „35. blokk". A `gitformat-index.adoc` 2 szóközzel behúzott
  literál format-spec törzse a reftable/hash-function-transition precedens szerint bájtazonosan
  angolul maradt (csak a címek + 2 flush-left mondat fordult). A `revisions.adoc` `::` szintaxis-
  címkéi (`'<sha1>', e.g. …::`, `The '..' (two-dot) Range Notation::` stb.), a Loeliger-ábra és a
  `....`/behúzott példablokkok bájtazonosak. Csupa nagybetűs, kanonikus listán kívüli címek a
  VÉGLEGES DÖNTÉS szerint angolul: `SPECIFYING REVISIONS` / `SPECIFYING RANGES` (`revisions.adoc`,
  + a `SPECIFYING REVISIONS` prózahivatkozás), `PRE-MERGE CHECKS` / `FAST-FORWARD MERGE` /
  `TRUE MERGE` / `MERGING TAG` / `HOW CONFLICTS ARE PRESENTED` / `HOW TO RESOLVE CONFLICTS`
  (`git-merge.adoc`, + a `"HOW TO RESOLVE CONFLICTS"` prózahivatkozás), `SUBCOMMANDS` /
  `NOTES MERGE STRATEGIES` (`git-notes.adoc`, + a `"NOTES MERGE STRATEGIES"` prózahivatkozások).
  Orchestrátor végezte közvetlenül. Részletek: `glossary-git-git-docs.md` „35. blokk".
- **2026-09-11 — a következő 5 legkisebb, még lefordítatlan „Gyökér" fájl kész** (a felhasználó
  5-ös bontást kért; a két gyökér-tábla együttes, sorszám szerint növekvő listája,
  `gitglossary.adoc`/`git.adoc`/`config.adoc`/`git-fast-import.adoc`/`glossary-content.adoc` kihagyva):
  `gittutorial-2.adoc` (436 sor, NEM man page), `git-read-tree.adoc` (438), `git-stash.adoc` (440),
  `git-tag.adoc` (443), `git-maintenance.adoc` (448). Defenzív `[[...]]` anchorok: `gittutorial-2.adoc`
  (3 — `_the_git_object_database`, `_the_index_file`, `_what_next`), `git-read-tree.adoc` (3 — a
  `~~~~` alcímek fölé: `_single_tree_merge` „Egyfás merge", `_two_tree_merge` „Kétfás merge",
  `_3_way_merge` „Háromutas merge"), `git-tag.adoc` (3 — a DISCUSSION `~~~~` alcímei fölé:
  `_on_re_tagging`, `_on_automatic_following`, `_on_backdating_tags`). A `git-diff.adoc` (már `[x]`)
  egyetlen prózahivatkozása `"3-Way Merge"` → `"Háromutas merge"`-re átírva a `git-read-tree.adoc`
  lefordított címéhez igazítva (a 14. blokkban jelzett jövőbeli függőség lezárva). `git-stash.adoc`:
  nincs anchor; az EXAMPLES `Cím::` definíciós-lista-címkéi (pl. `Pulling into a dirty tree::`)
  fordultak; a `` ``Interactive Mode'' `` (linkgit:git-add[1] szakaszra) prózahivatkozás
  `` ``Interaktív mód'' ``-ra átírva (a `git-add.adoc` már lefordított címéhez igazítva).
  `git-maintenance.adoc`: nincs anchor; a `TASKS`/`SUBCOMMANDS`/`TROUBLESHOOTING`/`BACKGROUND
  MAINTENANCE ON … SYSTEMS` csupa nagybetűs szakaszcímek a VÉGLEGES DÖNTÉS szerint angolul; a
  crontab/systemd/launchctl/`schtasks` kimeneti blokkok (`-----…` 71 kötőjel) bájtazonosak; a
  Windows UI-string `"Run whether user is logged in or not"` angolul. Csupa nagybetűs, kanonikus
  listán kívüli címek angolul: `SUBCOMMANDS`/`TASKS` (`git-read-tree.adoc` `MERGING`/`SPARSE
  CHECKOUT`; `git-stash.adoc` `COMMANDS`; `git-tag.adoc` csak kanonikus). Orchestrátor végezte
  közvetlenül. Részletek: `glossary-git-git-docs.md` „36. blokk".
- **2026-09-11 — a következő 5 legkisebb, még lefordítatlan „Gyökér" fájl kész** (a felhasználó
  5-ös bontást kért; a két gyökér-tábla együttes, sorszám szerint növekvő listája,
  `gitglossary.adoc`/`git.adoc`/`config.adoc`/`git-fast-import.adoc`/`glossary-content.adoc` kihagyva):
  `giteveryday.adoc` (455 sor, NEM man page), `git-interpret-trailers.adoc` (458),
  `git-for-each-ref.adoc` (476), `gitworkflows.adoc` (479, NEM man page), `git-submodule.adoc` (485).
  Anchor-kezelés: `giteveryday.adoc` — 4 meglévő inline `[[STANDALONE]]`/`[[PARTICIPANT]]`/
  `[[INTEGRATOR]]`/`[[ADMINISTRATION]]` anchor **bájtazonos**; a hozzájuk tartozó címszöveg és a
  rájuk mutató `<<STANDALONE,Individual Developer (Standalone)>>` stb. xref-ek vessző utáni
  látható szövege fordult (kisbetűsen: „egyéni fejlesztő (önálló)" stb.); a 4 ismételt `Examples`
  `~~~~` alcím → „Példák", **defenzív anchor nélkül** (a doc-order dedup-számozás hibaforrás, 1.
  blokk precedens). `gitworkflows.adoc` — 9 defenzív `[[...]]` a `~~~~` Title Case alcímek fölé
  (`_graduation`, `_merging_upwards`, `_topic_branches`, `_throw_away_integration`,
  `_branch_management_for_a_release`, `_maintenance_branch_management_after_a_feature_release`,
  `_branch_management_for_next_and_seen_after_a_feature_release`, `_merge_workflow`,
  `_patch_workflow`), aláhúzás pontos hosszra igazítva. `git-interpret-trailers.adoc` /
  `git-for-each-ref.adoc` / `git-submodule.adoc` — nincs `[[...]]`/`<<...>>`. Csupa nagybetűs,
  kanonikus listán kívüli címek a VÉGLEGES DÖNTÉS szerint angolul: `SEPARATE CHANGES` /
  `MANAGING BRANCHES` / `DISTRIBUTED WORKFLOWS` (`gitworkflows.adoc`, + a `"DISTRIBUTED WORKFLOWS"`
  prózahivatkozás), `OTHER RULES` / `CONFIGURATION VARIABLES` (`git-interpret-trailers.adoc`),
  `FIELD NAMES` (`git-for-each-ref.adoc`), `COMMANDS` (`git-submodule.adoc`). A `.Title` blokk-
  címek és a `[caption="Rule: "]`/`[caption="Recipe: "]` attribútum-sorok: a `.Title` fordult, a
  `[caption=...]` bájtazonos (skill-szabály). A `====` „Rule/Recipe" blokkokban a **prózát**
  lefordítottam, a csak `` `parancsot` `` tartalmazó blokkokat bájtazonosan hagytam. Orchestrátor
  végezte közvetlenül. Részletek: `glossary-git-git-docs.md` „37. blokk".
- **2026-09-11 — a 10 legkisebb méretű, még lefordítatlan „Gyökér" fájl kész** (a felhasználó
  kérésére; a két gyökér-tábla együttes, sorméret szerint növekvő listája,
  `gitglossary.adoc`/`git.adoc`/`config.adoc`/`git-fast-import.adoc`/`glossary-content.adoc`
  kihagyva): `pretty-formats.adoc` (422 sor, include-fragmens), `git-reset.adoc` (512),
  `git-rev-parse.adoc` (517), `git-pack-objects.adoc` (525), `git-sparse-checkout.adoc` (530),
  `git-status.adoc` (537), `gitprotocol-http.adoc` (544, RFC-stílusú protokoll-spec),
  `git-worktree.adoc` (546), `gitremote-helpers.adoc` (562, protokoll-spec), `gitfaq.adoc` (578,
  FAQ-formátum, meglévő explicit `[[...]]` anchorokkal minden kérdés előtt). Orchestrátor végezte
  közvetlenül, célzott `Edit`-ekkel, egy usage-limit miatti megszakítás után folytatva. RFC 2119
  kulcsszavak (`MUST`/`SHOULD`/`MAY`/`SHOULD NOT`/`MUST NOT`) angolul maradtak
  `gitprotocol-http.adoc`-ban és `gitremote-helpers.adoc`-ban (34. blokk precedens), a
  `gitcli.adoc`/`gitprotocol-capabilities.adoc` mintáját követve: `[Alany dativus] [KULCSSZÓ]
  [ige infinitivus]` szórenddel (pl. „A klienseknek MUST eltávolítaniuk…"). „FAQ" angolul maradt
  `gitfaq.adoc`-ban (bevett kölcsönszó, nincs korábbi „GYIK"-precedens). Defenzív `[[...]]` anchorok
  a Title Case alcímekhez: `git-rev-parse.adoc` (9), `git-status.adoc` (8), `gitprotocol-http.adoc`
  (11), `gitremote-helpers.adoc` (4), `gitfaq.adoc` (a 8 fő szakaszcím fölé, a meglévő
  kérdésenkénti anchorok mellett). Man-page-stílusú, kanonikus listán kívüli, csupa nagybetűs
  címek a VÉGLEGES DÖNTÉS szerint angolul: `DELTA ISLANDS` (`git-pack-objects.adoc`), `REFS` /
  `CONFIGURATION FILE` / `DETAILS` / `LIST OUTPUT FORMAT` (`git-worktree.adoc`), `INVOCATION` /
  `INPUT FORMAT` / `REF LIST ATTRIBUTES` / `REF LIST KEYWORDS` (`gitremote-helpers.adoc`),
  `COMMANDS` (`git-sparse-checkout.adoc`), `BACKGROUND REFRESH` / `UNTRACKED FILES AND
  PERFORMANCE` (`git-status.adoc`), a kétsoros „THIS COMMAND IS EXPERIMENTAL…" mondat
  nagybetűsen lefordítva (`git-sparse-checkout.adoc`, 3./29. blokk precedens). Részletek:
  `glossary-git-git-docs.md` „38. blokk".
- **2026-09-11 — az 5 legkisebb méretű, még lefordítatlan „Gyökér" fájl kész** (a felhasználó
  kérésére; a két gyökér-tábla együttes, bájtméret szerint növekvő listája, `gitglossary.adoc`/
  `git.adoc`/`config.adoc`/`git-fast-import.adoc`/`glossary-content.adoc` kihagyva — ezek a
  skill/progress szerint a végére, ill. a `config/` mappa utánra vannak halasztva): `gittutorial.adoc`
  (23KB, NEM man page), `git-update-index.adoc` (24KB, man page), `gitweb.adoc` (27KB, man page-
  vázas referencia), `gitformat-pack.adoc` (27,5KB, technical formátum-spec), `gitprotocol-pack.adoc`
  (27,7KB, RFC-stílusú protokoll-spec). 5 párhuzamos subagent végezte, diszjunkt fájlonként egy-egy
  (nem az orchestrátor közvetlenül, a fájlok 600–730 soros mérete miatt); az orchestrátor
  konszolidálta az eredményeket és futtatott egy gyors strukturális ellenőrzést (`----`/`====`
  párszám, `[[...]]` duplikátum-ellenőrzés, `ifdef`/`endif` párosság) mind az 5 fájlon —
  hibátlan. Nyitva maradt döntési kérdés: az „Authentication" cím ellentmondása
  (`gitprotocol-pack.adoc`-ban lefordítva „Hitelesítés"-re, a korábban kész `gitprotocol-http.adoc`-
  ban angolul hagyva) — l. `glossary-git-git-docs.md` „39. blokk". Részletek: „39. blokk".
- **2026-09-11 — a felhasználó lezárta a két nyitott döntést**: (1) „Authentication" marad
  angolul mindkét helyen — a `gitprotocol-pack.adoc` visszaállítva „Hitelesítés"-ről
  „Authentication"-re; (2) a kanonikus man-page-listán kívüli, csupa nagybetűs, kétsoros
  alcímek **véglegesen angolul maradnak** (a projekt eddigi gyakorlatának megerősítése,
  mostantól nem kell újra jelezni). Mindkettő rögzítve: `glossary-git-git-docs.md` „39. blokk"
  (frissítve).
- **2026-09-11 — a következő 2 legkisebb, még lefordítatlan „Gyökér" fájl kész** (a felhasználó
  kérésére; a két gyökér-tábla együttes, bájtméret szerint növekvő listája): `git-p4.adoc` (28KB,
  865 sor, man page), `git-send-email.adoc` (29KB, 771 sor, man page). 2 párhuzamos subagent
  kezdte, de mindkettő **munkamenet-limit (session limit, HTTP 429) miatt idő előtt megszakadt**
  a fájl vége felé; az orchestrátor ellenőrizte a tényleges fájlállapotot és Read/Edit-tel
  befejezte mindkettőt (`git-p4.adoc`-ban a „Clone és sync változók" alszakasz második fele
  [`branchUser`-től `mapUser`-ig], a „Submit változók" alszakasz és az „IMPLEMENTATION DETAILS"
  felsorolás, valamint mindkét fájl záró „GIT"/"Part of the linkgit:git[1] suite" sora volt még
  angolul — utóbbi „A linkgit:git[1] csomag része"-ként fordítva, a bevett precedens szerint).
  Strukturális ellenőrzés (`----`/`====` párszám, `[[...]]` duplikátum, reziduális angol szöveg
  heurisztikus grep) mindkét fájlon hibátlan (a fennmaradó angol találatok mind kódblokkon
  belüli, szándékosan érintetlen tartalom: egy `<submit more changes...>` placeholder-sor és egy
  `# Change this to...` shell-kommentár). Ez az első `git-p4.adoc` fájl a projektben, néhány
  Perforce-specifikus terminológiai döntéssel. Részletek: `glossary-git-git-docs.md` „40. blokk".
- **2026-09-11 — a következő 2 legkisebb, még lefordítatlan „Gyökér" fájl kész** (a felhasználó
  kérésére; a két gyökér-tábla együttes, bájtméret szerint növekvő listája): `MyFirstObjectWalk.adoc`
  (29,6KB, 964 sor, NEM man page — contributor-tutorial a Git objektumbejárásáról),
  `githooks.adoc` (29,9KB, 799 sor, man page — az összes Git hook leírása). 2 párhuzamos subagent
  végezte, ezúttal megszakítás nélkül. Strukturális ellenőrzés (`----`/`====` párszám, `[[...]]`
  duplikátum, reziduális angol szöveg heurisztikus grep) mindkét fájlon hibátlan (a fennmaradó
  angol találatok mind kódblokkon/C-kommenten/protokoll-pszeudokód-kommenten belüli, szándékosan
  érintetlen tartalom, ill. egy szó szerint idézett történelmi Git commit-üzenet).
  Részletek: `glossary-git-git-docs.md` „41. blokk".
- **2026-09-11 — a következő 2 legkisebb, még lefordítatlan „Gyökér" fájl kész** (a felhasználó
  kérésére): `git-format-patch.adoc` (30,8KB, 824 sor, man page), `git-push.adoc` (32,2KB, 809
  sor, man page). 2 párhuzamos subagent végezte. Az orchestrátor javított egy terminológiai
  inkonzisztenciát (`git-format-patch.adoc` „threading"/„threadeli" → „szálazás"/„szálazza", hogy
  megegyezzen a `git-send-email.adoc`-ban [40. blokk] már rögzített „szálazás" terminussal, amely
  kifejezetten a `git format-patch` szóhasználatára hivatkozott) és pótolta a záró „GIT"/"Part of
  the linkgit:git[1] suite" sor fordítását, amit a subagent kihagyott. A `git-push.adoc`
  megszakítás és hiba nélkül, hibátlanul készült el, a `<<URLS,GIT URLS>>` → `<<URLS,GIT
  URL-ek>>` és a `<<REMOTES,...>>`/`<<UPSTREAM-BRANCHES,...>>`/`<<REMOTE-GROUPS,...>>`
  bájtazonos-hagyási precedenst követve. Részletek: `glossary-git-git-docs.md` „42. blokk".
- **2026-09-11 — a következő 2 legkisebb, még lefordítatlan „Gyökér" fájl kész** (a felhasználó
  kérésére): `diff-options.adoc` (34,3KB, 925 sor, include-fragmens, sok `ifdef`/`ifndef`/`endif`
  guarddal — git-diff.adoc/git-log.adoc/git-format-patch.adoc-ba include-olva), `gitprotocol-v2.adoc`
  (36,8KB, 904→974 sor, RFC-stílusú protokoll-spec, a `gitprotocol-pack.adoc` mintáját követve).
  2 párhuzamos subagent végezte. A `diff-options.adoc` guard-számai (13 `ifdef` + 19 `ifndef` +
  32 `endif`) fordítás előtt és után egyeztek — nincs törött include. Az orchestrátor egy
  grammatikai pontatlanságot javított a `--diff-filter` leírásában („Nem Merge-eltek (U),
  Ismeretlenek (X)" hiányzó „amelyek" kötőszóval lógott a mondatban). A `gitprotocol-v2.adoc`
  strukturálisan hibátlan volt; emellett észrevettük, hogy a korábban (38. blokk) kész
  `gitprotocol-http.adoc` NAME-sora tévesen angolul maradt („Git HTTP-based protocols") a
  projekt „NAME egysoros leírása mindig fordul" konvenciója (2. blokk) ellenére — most javítva
  „Git HTTP-alapú protokollok"-ra. Részletek: `glossary-git-git-docs.md` „43. blokk".
- **2026-09-11 — a következő 2 legkisebb, még lefordítatlan „Gyökér" fájl kész** (a felhasználó
  kérésére): `gitweb.conf.adoc` (42KB, 983 sor, man page — a gitweb konfigurációs fájl referenciája,
  a `gitweb.adoc` [39. blokk] terminológiáját követve), `git-svn.adoc` (46,4KB, 1176→1238 sor,
  man page — a legnagyobb fájl eddig ebben a batch-sorozatban, a Subversion↔Git híd, a `git-p4.adoc`
  [40. blokk] a legközelebbi mintafájl). 2 párhuzamos subagent végezte, megszakítás nélkül,
  orchestrátor-javítás nem volt szükséges egyik fájlon sem. Strukturális ellenőrzés (kötőjel-/
  aláhúzás-számlálás, anchor-duplikátum, reziduális angol szöveg heurisztikus grep) mindkét
  fájlon hibátlan. Részletek: `glossary-git-git-docs.md` „44. blokk".
- **2026-09-11 — a következő 2 legkisebb, még lefordítatlan „Gyökér" fájl kész** (a felhasználó
  kérésére): `git-rebase.adoc` (47,4KB, 1289→1354 sor, man page), `gitattributes.adoc` (50,6KB,
  1385→1484 sor, man page — eddig a legnagyobb fájl ebben a batch-sorozatban). 2 párhuzamos
  subagent végezte. Az orchestrátor javított egy apró terminológiai következetlenséget
  (`git-rebase.adoc`: az „Easy Case" `::`-definíciós-címke „Egyszerű eset"-re fordult, míg a
  hozzá tartozó `[[_the_easy_case]]` cím és egy NOTE-glossza „könnyű eset"-et használt — a
  címkét „Könnyű eset"-re javítva az egységesség kedvéért). A `gitattributes.adoc` (23 defenzív
  anchorral, sok új terminológiával: checkin/checkout igeként, clean/smudge filter, hunk-fejléc,
  konfliktusjelölő) strukturálisan hibátlanul készült el. Részletek: `glossary-git-git-docs.md`
  „45. blokk".
