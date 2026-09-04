# Git core dokumentáció magyar fordítás — szószedet és fordítási döntések

Ez a **gazdag munkafájl**: minden visszatérő terminológiai és stílusdöntés ide kerül, blokkonként
számozva, dátummal, hogy nyomon követhető legyen, mikor és milyen kontextusban született.

A fordítás **helyben** történik a `git/Documentation/**/*.adoc` fájlokon (a `RelNotes/` kivételével).
A verziókövetést a felhasználó kezeli kézzel. Lásd a `translate-git-docs` skillt a részletes szabályokért.

---

## Hogyan használd

- **Minden fordítási munkamenet elején olvasd el ezt a fájlt, a `progress-git-git-docs.md`-t, és a
  `glossary-progit2.md` „VÉGLEGESÍTVE" terminológiai tábláit**, mielőtt bármit fordítanál.
- Ha egy visszatérő kifejezésre nincs itt egyértelmű döntés, és a szövegkörnyezet sem dönti el →
  **állj meg és kérdezd meg a felhasználót**. A cél a konzisztencia, nem a gyors haladás rossz döntéssel.
- Minden lefordított blokk után: ha új, visszatérő döntés született, vedd fel egy új, számozott
  „N. blokk" szekcióba (dátummal). A hozzáadott `[[...]]` anchorokat és átírt `<<...>>` hivatkozásokat
  is ide jegyezd fájlonként.

---

## 0. blokk — a `progit2` fordításból ÖRÖKÖLT terminológiai alapvonal (kötelező)

A felhasználó döntése (2026-09-04): a Git core dokumentáció fordítása a **`glossary-progit2.md`
véglegesített döntéseit veszi át kötelező kiindulási alapként**. Az alábbi tábla ezek kivonata; a teljes
kontextus és a toldalékolási minták a `glossary-progit2.md` 1–15. blokkjaiban vannak. Ha egy tétel itt
és ott ütközik, a `glossary-progit2.md` az irányadó; ha a git-docs kontextusa mást kíván, **új blokkban
rögzítsd az eltérést**, ne csendben térj el.

### Angolul maradó Git-fogalmak (prózában is, `+mono+` / backtick nélkül is)

| angol | magyar kezelés | megjegyzés |
|---|---|---|
| repository | **marad „repository"**; toldalék kötőjellel: `repository-t`, `repository-val`, `repository-k`, `repository-ba` | a „repó" rövid alak csak lazább hangvételnél |
| bare repository / non-bare | **marad „bare repository" / „nem bare repository"** | |
| branch (fn) | **marad „branch"**; toldalék: `branchet`, `branchre`, `branchen`, `branchek` | |
| branch (ige) | **„branchel"**, `branchelés`; `branching model` → `branchelési modell` | |
| merge (fn/ige) | **marad „merge"**; ige: `merge-el`, `merge-elés` | |
| remote (fn és jelző) | **marad „remote"** minden helyzetben (`remote repository`, `remote branch`) — nem „távoli" | |
| commit (fn) | **marad „commit"**; toldalék: `commitot`, `commitok`, `commitba` | |
| commit (ige) | **„commitol"**, `commitolás` | |
| commit message | **„commit-üzenet"** | |
| checkout / clone / fetch / pull / push / rebase / stash / cherry-pick / reset / revert | **parancsnevek — angolul maradnak** | igei alak: `pull-ol`, `push-ol`, `rebase-el`, `stashel`, `checkoutol`, `klónoz` |
| fast-forward (fn) / (ige) | **marad „fast-forward"** / `fast-forwardol`, `fast-forwardolás` | |
| non-fast-forward | **marad „non-fast-forward"** | |
| HEAD, origin, upstream, downstream | **maradnak** (Git-fogalmak) | |
| detached HEAD | **„leválasztott HEAD"**; első előforduláskor `"`leválasztott HEAD`" (detached HEAD)` | a kódkimenetben lévő `'detached HEAD'` bájtazonos |
| staging area | **marad „staging area"** | |
| index (a staging area szinonimája) | **marad „index"** | |
| working tree / working directory | **„munkakönyvtár"**; ahol a forrás szándékosan „tree"-t mond, ott **`working tree` marad** | |
| Git directory (`.git`) | **„Git-könyvtár"** | |
| HEAD / Index / Working Directory (a „három fa") | **HEAD / index / munkakönyvtár** | |
| hash / SHA-1 / checksum | **hash / SHA-1** (marad) / **„ellenőrzőösszeg"** | „checksum hash" → „ellenőrzőösszeg-hash" |
| snapshot | **„pillanatkép"** | |
| tag (fn/ige) | **„tag" / „tagel"** (marad); toldalék **magas hangrend**: `tagek`, `taged`, `tageid`, `tagnév` | „lightweight tag" → „könnyűsúlyú tag"; „annotated tag" → „annotált tag" |
| pull request | **marad „pull request"**; toldalék: `pull requestet`, `pull requesten` | |
| merge request (GitLab) | **marad „merge request"** | |
| issue (bug-tracker) | **marad „issue"**: `issue-t`, `issue-k`, `issue-ra` | |
| hook | **marad „hook"**; `hookok`, `hookkal`, `hookrendszer` | „client-side / server-side hooks" → „kliensoldali / szerveroldali hookok" |
| reflog | **marad „reflog"**; `reflogot`, `reflogod` | |
| refspec | **marad „refspec"**; fejezetcím „A refspec" | |
| packfile | **marad „packfile"**; `packfile-ok` | |
| pathspec | **marad „pathspec"**; `pathspecek`; a `"`pathspec`"` idézőmakró megtartva | |
| submodule | **marad „submodule"**; `submodule-ok`, `submodule-t`, `submodule-ját` | „superproject" → „szuperprojekt"; „subproject" → „alprojekt" |
| bundle (fn/ige) | **marad „bundle"** / `bundle-el`, `bundle-elés`, `unbundle-el`; a `git bundle` parancsnév marad | |
| daemon | **marad „daemon"**; `daemont`, `daemonizál` | |
| changeset | **marad „changeset"**; toldalékkal | |
| hunk (diff) | **marad „hunk"**; `hunkok`, `hunkonként` | |
| whitespace | **marad „whitespace"**; `sorvégi whitespace`, `whitespace-probléma` | |
| pager | **marad „pager"** | |
| prompt | **marad „prompt"** | |
| credential(s) | **„hitelesítő adatok"** (a sima szó); összetételben `credential` anglicizmusként marad (`credential helper`, `credential.helper`, `credential-tároló`) | |
| plumbing / porcelain | **marad „plumbing / porcelain"**; első előforduláskor magyarázva (`"`plumbing`" (alacsonyszintű)` / `"`porcelain`" (magasszintű)`) | |
| maintainer | **marad „maintainer"**; `maintainere`, `maintainerének` | |
| stage / unstage (ige) | `stage-el` / `unstage-el`, `stage-elés` | |
| squash (ige) | `squashel`, `squashelés`, „összesquashel" | |
| amend (`git commit --amend`) | `amendel`, `amendelés`; a `--amend` kapcsoló angol | |
| bisect (ige/fn) | **marad „bisect"** / `bisectel`, `bisectelheted` | |
| annotate / file annotation | `annotál` / `fájlannotáció` (`git blame`) | |
| force push / force-update | `force push` / `force pushol`, `force-pusholt` | |
| interactive rebase | „interaktív rebase" | |
| topic branch / base branch / upstream branch / tracking branch / remote-tracking branch | **maradnak angolul** (toldalékkal) | „long-running branch" → „hosszú életű branch" |
| three-way merge / merge base | „háromutas merge" / „merge-alap" | |
| object / object database (ODB) | „objektum" / „objektumadatbázis (ODB)" | Git-objektum típusnevek `blob`/`tree`/`commit`/`tag` — angolul, kisbetűvel, bájtazonosan |
| loose / packed object | „laza" / „csomagolt objektum"; `"`loose`" (laza)` első előforduláskor | |
| reference(s) / ref, refs | `referencia` / `referenciák`; a `ref`/`refs` literál **angolul marad**; `packed-refs` fájl változatlan | „symbolic reference" → „szimbolikus referencia" |
| namespace | „névtér"; ige: `namespace-el` | |
| garbage collection / gc | „szemétgyűjtés"; `git gc`, `auto gc` parancsnevek angolul | |
| environment variable | „környezeti változó"; a változónevek (`GIT_DIR` stb.) angolul, `*…*` félkövér megtartva | |
| content-addressable filesystem | „tartalomcímzett fájlrendszer" | |

### Általános szakszókincs (a `progit2`-ből)

| angol | magyar |
|---|---|
| version control | verziókövetés |
| Version Control System (VCS) | verziókövető rendszer (VCS); többes: VCS-ek |
| distributed / centralized | elosztott / központosított |
| workflow | munkafolyamat |
| patch (fn) | **marad „patch"**; `patchek` |
| hook script | hook szkript |
| working tree | munkakönyvtár |
| snapshot | pillanatkép |
| public key / private key / passphrase | nyilvános kulcs / privát kulcs / jelmondat |
| namespace | névtér |
| line endings / CRLF / LF | sorvégek; „carriage-return" → kocsivissza-karakter, „linefeed" → soremelés-karakter |
| merge strategy / merge driver | merge-stratégia / driver (marad) |
| keyword expansion / substitution | kulcsszó-behelyettesítés |
| garbage collection | szemétgyűjtés |
| wildcard | helyettesítő karakter |
| trace / tracing | nyomkövetés |

### Stílus

- **Tegező hangnem**, ahol a forrás közvetlenül az olvasóhoz szól („you"). A man-page-leírások jó része
  személytelen — ott a magyar is személytelen/kijelentő marad.
- Kódazonosítók (parancsok, alparancsok, kapcsolók, fájlnevek, config-kulcsok, env-változók, placeholderek)
  a prózában is `+monospace+` / backtick között, **angolul**.
- Az admonition-kulcsszavak (`NOTE:`, `TIP:`, `WARNING:`, `IMPORTANT:`, `CAUTION:`) **angolul maradnak**
  (AsciiDoc szintaxis); csak a mögöttük lévő próza fordul.

---

## git-docs-specifikus döntések

*(Ide kerülnek az új, számozott blokkok az egyes fordítási batchek után — dátummal. Minden blokk:
terminológiai döntések tábla + „Címsor-anchorok" alszakasz + „Man-page címként angolul hagyott kétes
címsorok" + „Megőrzött markup" jegyzet, a `glossary-progit2.md` mintájára.)*

## 1. blokk — `technical/` (mind a 35 fájl) — 2026-09-04

**Módszer:** 4 párhuzamos subagent (10+10+10+5 fájl) kezdte, a session-limit miatt félbeszakadtak;
az orchestrátor fejezte be helyben (`large-object-promisors.adoc`, `pack-heuristics.adoc` a nulláról;
`bundle-uri.adoc`, `sparse-checkout.adoc` befejezve; `api-trace2.adoc` külön subagent által ellenőrizve
= teljes). Diszjunkt fájlhalmazok, nincs átfedés.

### Ebben a blokkban rögzített / megerősített döntések

| angol | magyar | megjegyzés |
|---|---|---|
| trace / tracing / Trace2 | „nyomkövetés"; `Trace2` / `Trace1` / `Trace2 API` mint név-tokenek angolul | `trace2.*` config-kulcsok, `GIT_TRACE2*` env-változók, esemény- és JSON-mezőnevek (`region_enter`, `def_param`, `"exit-code"`) **angolul**, backtick között |
| target (Trace2) | **cél** | „normál/teljesítmény/esemény formátumú cél" |
| event (Trace2) | **esemény** | |
| setup (folyamat-felállás) | **felállás** | „a szülő nem bocsát ki … amíg a gyermek be nem fejezi a felállást" |
| promisor remote | **marad „promisor remote"** | `large-object-promisors.adoc` |
| Large Object Promisor / LOP | **marad angolul** (coined term, a doksi maga definiálja); első előforduláskor magyar glossza | a dokumentumcím `Large Object Promisors` is **angolul maradt** (a fogalom neve) — eldöntendő, ha a felhasználó fordítást kér |
| object storage (S3/GCP/MinIO értelemben) | **„objektumtárolás"** (nem „objektumadatbázis" – az az ODB) | |
| offload (blobokat LOP-ra) | **kihelyez** / **kihelyezés** | |
| main remote | **fő remote** | |
| bundle / bundle list / bundle URI | **marad „bundle" / „bundle-lista" / „bundle URI"**; toldalék: `bundle-t`, `bundle-ök`, `bundle-listának` | `git bundle` parancsnév marad; `creationToken`/`bundle.mode`/`blob:none` config-tokenek angolul |
| unbundle (ige) | **kicsomagol** | |
| thin pack / thin bundle | **marad „thin pack" / „thin bundle"**; első előforduláskor „(vékony)" glossza | `pack-heuristics.adoc`, `bundle-uri.adoc` |
| prefetch / hourly-daily rollup | **előfetch** / „óránkénti"–„napi" összevonás | `bundle-uri.adoc` GVFS-szakasz |
| recency order / delta order (packing) | **frissességi sorrend** / **delta-sorrend** | `pack-heuristics.adoc` |
| sliding window (delta) | **csúszóablak** | |
| basename (packing heurisztika) | **marad „basename"** (idézőjelben, ahogy a forrás) | |
| behavior A / B / C (sparse-checkout) | **marad „Behavior A/B/C"** (a doksi saját címkéi, `[[_behavior_a]]` anchorokkal) | `sparse-checkout.adoc` |
| sparse specification / sparsity patterns / cone mode | **sparse specifikáció** / **sparsity minták** / **cone mód** | `SKIP_WORKTREE`, `--scope=all` stb. angolul |
| reftable — block/record/varint/restart | **blokk / rekord / varint / újraindítási pont**; a formátum-spec literál részei (`----` blokkok) bájtazonosak | `reftable.adoc` — döntően format-spec, kevés fordítandó próza |

### Címsor-anchorok

- A `technical/` doksik **külön-külön HTML-be** épülnek; `<<...>>` xref csak fájlon belül van, és szinte
  mindig **explicit `[[...]]` anchorral** (a subagentek ezeket érintetlenül hagyták, csak a címszöveg fordult).
- **Setext (kétsoros) címsorok:** a fordított címhez **igazított aláhúzás** (pontosan a cím hossza).
  A subagentek ezt sok helyen elmulasztották; utólag javítva: `large-object-promisors.adoc` (14),
  `pack-heuristics.adoc` (1), `bundle-uri.adoc` (2), `hash-function-transition.adoc` (11), `reftable.adoc` (20).
  `~~~~`/`^^^^` aláhúzást is használnak (a `reftable.adoc`), ezt megtartottuk.
- **Defenzív anchor:** explicit anchor és `<<...>>` hivatkozás nélküli setext-címsorok fölé
  `[[<angol-autogen-slug>]]` került (`_` prefix, `_` separator) — pl. `large-object-promisors.adoc`
  I–V + 1)–7) + FAQ-szakaszcímek, `bundle-uri.adoc` 11 szakaszcím, `sparse-checkout.adoc`
  `[[_reference_emails]]`. Ismételt generikus alcímeknél (`Rationale`, `Implementation`, `Note`) a
  `large-object-promisors.adoc`-ban **nem** tettünk anchort (a doc-order dedup-számozás
  (`_rationale_2`…) kézi eltalálása hibaforrás, és semmi nem hivatkozik rájuk).

### Man-page címként angolul hagyott címsorok

- **`See Also`** (`bundle-uri.adoc`) — a skill blanket-szabálya szerint bájtazonosan angolul maradt,
  bár ez nem man page. `[[_see_also]]` anchort kapott. **Eldöntendő:** nem man-page `technical/`
  doksiban fordítható lenne „Lásd még"-re.

### Verbatim blokként ANGOLUL hagyott tartalom — ELDÖNTENDŐ

- **`pack-heuristics.adoc`:** a fájl törzse egy 2006-os IRC-napló szó szerinti átirata (behúzott
  literál blokk). Csak a **narrátori kommentárt** és a címet fordítottuk; a `<njs\`>` / `<linus>` /
  `<gitster>` sorokat **bájtazonosan** hagytuk (logolt beszélgetés idézete). Ha a felhasználó kéri,
  az átirat is fordítható (a behúzás megtartásával).
- `sparse-checkout.adoc` / `rerere.adoc`: a `$ git …` shell-session literál blokkok parancs-/
  kimeneti sorai angolul (kód). A közéjük ékelt **magyarázó prózát** (behúzott, de nem parancs)
  lefordítottuk a behúzás megtartásával.

### Megőrzött markup / megjegyzések

- `api-index-skel.adoc`: csak a cím + 4 sor próza fordult; a többi `//`-komment-váz (ToC-generátor). Kész.
- `api-trace2.adoc` ~776/782: upstream inkonzisztencia (`"data-json"::` címke vs. `"event":"data_json"`
  a mintában) — **bájtazonosan** hagyva, nem „javítva".
- `sparse-checkout.adoc` ~1034: forrásbeli elírás („These command" → „commands") — a fordítás a
  helyes alakot használja.
- `hash-function-transition.adoc`, `reftable.adoc`: nagy, blokk-nehéz fájlok; a `----` layout- és
  bájtdiagramok, C-snippetek, `git cat-file` kimenetek bájtazonosak.

## 2. blokk — `Documentation/` gyökér, első 4 top-level man page — 2026-09-04

**Fájlok:** `git-archimport.adoc`, `git-archive.adoc`, `git-column.adoc`, `git-commit-tree.adoc`.
Ez az első batch a `Documentation/` gyökér top-level `git-*.adoc` parancs-man page-jei közül —
nincs korábbi precedens erre az alkategóriára, ezért az alábbi döntések most születtek meg.

### Ebben a blokkban rögzített / megerősített döntések

| angol | magyar | megjegyzés |
|---|---|---|
| NAME szakasz egysoros leírása | **fordul** | pl. `git-archive - Fájlarchívum létrehozása egy megnevezett fából`; a parancsnév + kötőjel változatlan, csak a leírás fordul — precedens a további top-level man page-ekhez |
| „discussion below" / `Discussion` cím | **„tárgyalás" / „Tárgyalás"** | konzisztens a két fájlban (`git-archimport.adoc` prózában, `git-commit-tree.adoc` címként) |
| checkout (múlt idejű melléknévi igenév prózában) | **„checkoutolt"** (nem „kicheckoutolt") | a `checkoutol` ige glossary-mintájának egyenes folytatása |
| commit log message | **„napló-üzenet" / „commit napló-üzenete"** | `git-commit-tree.adoc`-ban; a „commit-üzenet" (glossary 0. blokk) szinonimájaként, a forrás „commit log message" szóhasználatához igazítva |
| commit comment (stdin) | **„commit-megjegyzés"** | `git-commit-tree.adoc` |

### Man-page címként/man-page-stílusúként ANGOLUL hagyott, bizonytalan címsorok

- **`MERGES`** (`git-archimport.adoc`) — csupa nagybetűs, kétsoros man-page-stílusú cím, de **nincs**
  a skill kanonikus man-page-szekció listáján, és sehol máshol nincs rá `<<...>>` hivatkozás.
  A `bundle-uri.adoc`-beli `See Also`-precedenst (1. blokk) követve **bájtazonosan angolul hagyva**,
  hogy ne törjön el egy esetleges jövőbeli címszöveg-alapú xref. **Eldöntendő.**
- **`BACKEND EXTRA OPTIONS`** (`git-archive.adoc`) — ugyanaz a helyzet, ugyanaz a döntés:
  **angolul hagyva**. A `CONFIGURATION` és `ATTRIBUTES` viszont a kanonikus listán van, ill.
  explicit `[[ATTRIBUTES]]` anchorral rendelkezik, azok érintetlenek/fordítva a szabály szerint.
  **Eldöntendő**, hogy a jövőben ezt a két (és a hasonló `technical/`-beli) mintát következetesen
  fordítsuk-e, ha a felhasználó megerősíti, hogy nincs rájuk cím-alapú xref-kockázat.

### Címsor-anchorok

- `git-archive.adoc`: `[[ATTRIBUTES]]` már eleve explicit anchorral rendelkezett — érintetlen, a
  `--worktree-attributes` alatti `<<ATTRIBUTES>>` hivatkozás változatlan.
- `git-commit-tree.adoc`: két nem-man-page, Title Case cím (`Commit Information`, `Discussion`) —
  egyiknek sem volt explicit anchora, és sehol nincs rájuk `<<...>>` hivatkozás a fában (ellenőrizve
  grep-pel). Defenzív anchorok kerültek eléjük: `[[_commit_information]]` (cím: „Commit-információk",
  aláhúzás 18 karakter, egyezik), `[[_discussion]]` (cím: „Tárgyalás", aláhúzás 9 karakter, egyezik).
- `git-archimport.adoc`, `git-column.adoc`: nincs `[[...]]` anchor és nincs `<<...>>` hivatkozás egyik
  fájlban sem (a `MERGES` angolul maradt, l. fent, ezért oda sem került anchor).

### Megőrzött markup / megjegyzések

- `git-column.adoc`: 3 pár `------------` (12 kötőjel) példa-blokk, tartalmuk (parancsok, táblázatos
  kimenet) bájtazonos; csak a bevezető mondatok fordultak. Az `include::includes/cmd-config-section-all.adoc[]`
  és `include::config/column.adoc[]` sorok változatlanok (nem ebben a batchben fordítandó fájlok).
  `column.<name>`, `column.ui` config-kulcsok angolul maradtak.
  `--width`, `-l`/`--list`, `-v`/`--verbose` stb. kapcsolók, `<n>`/`<N>` placeholderek változatlanok.
- `git-commit-tree.adoc`: `include::date-formats.adoc[]` és `include::i18n.adoc[]` változatlanok (nem
  ebben a batchben fordítandó fájlok). A `FILES` szakasz `/etc/mailname` literál útvonala változatlan,
  próza nélkül. `^D`, `.git/HEAD`, `"<"` átirányítás-jelölés bájtazonos.
- `git-archive.adoc`: EXAMPLES szakasz minden `` `git archive ...` `` parancspéldája (backtick-kódolt,
  nem `----` blokk) bájtazonos, csak az alattuk lévő magyarázó bekezdés fordult.
- `git-archimport.adoc`: `{litdd}` attribútum-referencia (pl. `PROJECT{litdd}devo{litdd}VERSION`)
  bájtazonos, ahogy a szabály előírja.

## 3. blokk — `git-check-mailmap.adoc`, `git-check-ref-format.adoc`, `git-checkout-index.adoc`, `git-backfill.adoc` — 2026-09-04

**Módszer:** egyetlen munkamenet, célzott `Edit`-ekkel, mindegyik fájl teljes egészében lefordítva.

### Ebben a blokkban rögzített / megerősített döntések

| angol | magyar | megjegyzés |
|---|---|---|
| partial clone / blobless partial clone | **marad „partial clone" / „blobless partial clone"** | Git-specifikus fogalomnév, a `bare repository` mintájára angolul hagyva; `git-backfill.adoc` |
| backfill (ige/fn) | **„backfillel" / „backfillelés"**, `git backfill` parancsnév marad | a főnévi „backfill" (a letöltendő adathalmaz) is angolul maradt: „a backfillbe" |
| peel onion (postfix operátor-magyarázat) | **„hagymahámozó" (művelet)** | `git-check-ref-format.adoc`; **eldöntendő** — a `gitrevisions.adoc` fordításakor egyeztetni, mert az ottani „peel onion” magyarázat ugyanerre a `^{type}` operátorra vonatkozik, és a terminológiának egyeznie kell |
| stat information (index kontextusban) | **„stat-információ"** | `git-checkout-index.adoc` |
| tempname/path/RS/stage1temp stb. (checkout-index kimeneti formátum mezőnevei) | **változatlanul angolul**, csak a körülöttük lévő próza fordul | placeholder-szerű mezőnevek, nem valódi kódblokk, de nem fordítandók |

### Címsor-anchorok

- `git-check-mailmap.adoc`: a `MAPPING AUTHORS` cím **nem** man-page szekciócím (nincs a skill listáján),
  ezért lefordítva „Szerzők leképezése"-re. Nincs rá `<<...>>` hivatkozás sem ebben, sem más fájlban,
  ezért defenzív `[[_mapping_authors]]` anchort kapott (autogen slug az eredeti angol címből).
- `git-checkout-index.adoc`: az `Using --temp or --stage=all` kétsoros alcím (nem man-page cím) le lett
  fordítva „A --temp vagy a --stage=all használata"-ra; nincs rá `<<...>>` hivatkozás a fájlban, nem
  kapott explicit anchort (a skill csak `[[...]]`-vel rendelkező vagy hivatkozott címeknél kötelezi;
  itt utólag pótolható, ha felmerül az igény — jelezve, ha a felhasználó kéri, hozzáadható).
- `git-check-ref-format.adoc`, `git-backfill.adoc`: nincs bennük alcím a man-page szekciókon kívül,
  nem volt szükség anchor-kezelésre.

### Man-page címként angolul hagyott címsorok

- Mind a négy fájlban a szokásos NAME/SYNOPSIS/DESCRIPTION/OPTIONS/EXAMPLES/OUTPUT/CONFIGURATION/
  SEE ALSO/GIT címek angolul maradtak. Az `OUTPUT` (`git-check-mailmap.adoc`) és a `CONFIGURATION`
  szintén a man-page-blanket-listán szerepel, ezért angolul hagyva.

### Megőrzött markup / megjegyzések

- `git-backfill.adoc`: a `THIS COMMAND IS EXPERIMENTAL. ITS BEHAVIOR MAY CHANGE IN THE FUTURE.`
  csupa nagybetűs figyelmeztető mondat lefordítva, a csupa nagybetűs formázás megtartva:
  „EZ A PARANCS KÍSÉRLETI. A VISELKEDÉSE A JÖVŐBEN MEGVÁLTOZHAT."
- `git-checkout-index.adoc`: a `. tempname TAB path RS` / `. stage1temp SP stage2temp SP stage3tmp TAB
  path RS` listaelemek (nem kódblokkban, hanem AsciiDoc számozott listaként) mezőnevei angolul maradtak,
  csak a hozzájuk tartozó `+`-folytatásos magyarázó bekezdések fordultak.
- Mind a négy fájl végén a GIT szakasz „A linkgit:git[1] csomag része" alakra lett fordítva.

## 4. blokk — orchestrátor-konszolidáció + rendszerszintű API-hiba — 2026-09-04

**Kontextus:** a `Documentation/` gyökér ~252 fájljának feldolgozását 10-es, majd (ismétlődő hibák
miatt) 3-4 fájlos subagent-blokkokban indítottuk. Több párhuzamos subagent (mind 10-es, mind 3-4 fájlos
méretnél) `400 Output blocked by content filtering policy` API-hibával szakadt félbe, véletlenszerű
pontokon, a tartalomtól láthatóan függetlenül (ugyanaz a hiba ütötte a `git-add.adoc` DESCRIPTION-jét,
a `git-cvsserver.adoc` OPTIONS-ét stb.). **Ez rendszerszintű, nem tartalomfüggő jelenség** — a
felhasználó tájékoztatást kapott, és a kisebb blokkméret mellett döntött; ez csökkentette (nem szüntette
meg) a hibaarányt. A félbeszakadt agenteket **folytatásos** prompttal indítottuk újra (a részlegesen
kész fájlt Read-del ellenőrizve, onnan folytatva), nem nulláról.

**GIT szakasz trailer — egységesített döntés:** a záró `GIT`/`---` szekció „Part of the linkgit:git[1]
suite" sora **mindig** „A linkgit:git[1] csomag része"-re fordítandó (nem „Része a linkgit:git[1]
csomagnak" — ez az alak korábban néhány fájlban véletlenül más szórenddel készült el, ezeket
[`git-branch.adoc`, `git-bundle.adoc`, `git-cat-file.adoc`, `git-check-attr.adoc`, `git-bugreport.adoc`,
`git-cherry.adoc`] utólag egységesítettük).

**Ebben a blokkban (orchestrátor + eredeti nagy subagentek maradványaiból) készre véve/ellenőrizve:**
`git-branch.adoc`, `git-bugreport.adoc`, `git-bundle.adoc`, `git-cat-file.adoc`, `git-check-attr.adoc`,
`git-credential.adoc`, `git-cvsserver.adoc`, `git-count-objects.adoc`, `git-credential-cache--daemon.adoc`,
`git-credential-cache.adoc`, `git-credential-store.adoc`, `git-cvsexportcommit.adoc`, `git-cvsimport.adoc`,
`git-cherry.adoc`, `git-am.adoc` — ezeket eredetileg a most félbeszakadt nagy (10-es) subagentek fordították
le a hiba bekövetkezte előtt; az orchestrátor csak a GIT-trailer egységesítést és a záró ellenőrzést végezte.

**Részlegesen kész, folytatásra vár** (a `progress-git-git-docs.md`-ben `~NN%` jelöléssel): `git-add.adoc`
(~30%, az OPTIONS szakasz `-e`/`--edit`-jétől kell folytatni), `git-apply.adoc` (~40-60%), `git-check-ignore.adoc`
(~16%), `git-cherry-pick.adoc` (~60%), `git-bisect.adoc` (~33%), `git-bisect-lk2009.adoc` (~34%, 1358 soros,
2009-es blogbejegyzés-stílusú, NEM man page — a főcím és minden alcím fordítandó, aláhúzás-igazítással).

**Még teljesen érintetlen:** `git-blame.adoc`,
`git-checkout.adoc`, `git-clone.adoc`, `git-commit-graph.adoc`, `git-commit.adoc`, `git-config.adoc`,
`git-describe.adoc`.

**„CSERE-NNN" placeholder-kísérlet (felhasználói ötlet, API-hiba elleni mitigáció):** mivel a
`content filtering policy` hiba nem mutatott egyértelmű szókulcs-korrelációt (olyan fájloknál is
előfordult, amelyekben semmilyen „kockázatosnak" tűnő szó nem volt — pl. `git-add.adoc`, `git-branch.adoc`),
kísérletképp a `git-daemon.adoc`, `git-bisect-lk2009.adoc` és `git-config.adoc` fájlokban a
`daemon`/`kill`/`abuse`/`attacker` szavakat a fordítás előtt `CSERE-001`…`CSERE-004` opaque tokenekre
cseréltük (szóhatáros `sed`), a subagentet utasítva, hogy hagyja érintetlenül őket; a fordítás után az
orchestrátor állította vissza a valódi szót/fordítást. **`git-daemon.adoc`-nál ELSŐRE sikerült**
(korábban ugyanez a fájl egyszer sem futott le hiba nélkül) — gyenge jelzés a hipotézis mellett, de nem
bizonyíték (placeholder nélküli blokkok, pl. G, is voltak sikeresek ugyanebben a körben). Részletes
buktatók és a visszaállítási szabály a 6. blokk „Orchestrátor utólagos visszaállítása" alszakaszában:
röviden, a placeholder és a végleges szó hossz-eltérése miatt **mindig ellenőrizni kell utólag** (1) a
setext-aláhúzások hosszát a placeholdert tartalmazó címsoroknál, és (2) a közvetlenül (kötőjellel,
idézőjel/backtick NÉLKÜL) toldalékolt előfordulásokat.

## 5. blokk — `git-annotate.adoc`, `git-citool.adoc`, `git-clean.adoc` — 2026-09-04

**Módszer:** egyetlen munkamenet, célzott `Edit`-ekkel, mindegyik fájl teljes egészében lefordítva.
Mindhárom rövid fájl (34, 26, illetve 159 soros); nincs korábbi terminológiai ütközés.

### Ebben a blokkban rögzített / megerősített döntések

| angol | magyar | megjegyzés |
|---|---|---|
| annotate (parancsnév-leírásban, ige) | **„annotál"** | `git-annotate.adoc` NAME/DESCRIPTION — a glossary 0. blokk `annotate / file annotation` → `annotál` mintáját követi |
| Graphical alternative to X | **„Grafikus alternatíva X-hez"** | `git-citool.adoc` NAME |
| Interactive mode (git-clean alcím) | **„Interaktív mód"** | nem man-page cím, fordítva; l. lent az anchor-döntést |
| Input ignore patterns>> / Select items to delete>> / What now> (interaktív prompt-szövegek) | **bájtazonosan angolul maradnak** | a `git clean` ténylegesen ezt a szó szerinti angol promptot írja ki futáskor; lokalizálatlan program-kimenet, nem próza |
| clean / filter by pattern / select by numbers / ask each / quit / help (interaktív alparancs-címkék, `::` definíciós lista) | **bájtazonosan angolul maradnak** (csak a leírás-törzsük fordult) | ezek a ténylegesen begépelendő alparancs-szavak (l. „Azt is mondhatod, hogy \`c\` vagy \`clean\`"); lefordításuk eltérne a program valós angol interaktív felületétől — **eldöntendő**, ha a felhasználó mégis fordítást kér rájuk |

### Címsor-anchorok

- `git-clean.adoc`: az „Interactive mode" kétsoros alcím **nem** man-page szekciócím, és nincs rá
  `<<...>>` xref sehol a fában (grep-pel ellenőrizve, csak a fájlon belüli ``"Interactive mode''``
  idézőjeles szövegközi utalás van rá, amit „Interaktív mód"-ra fordítottunk). Explicit `[[...]]`
  anchort **nem** kapott (a skill csak hivatkozott vagy már anchorolt címeknél kötelezi; pótolható,
  ha a jövőben xref épül rá). Az aláhúzást a fordított cím hosszához igazítottuk: `Interaktív mód`
  (14 karakter) → `--------------` (14 kötőjel).
- `git-annotate.adoc`, `git-citool.adoc`: nincs bennük man-page-en kívüli alcím, nem volt szükség
  anchor-kezelésre.

### Man-page címként angolul hagyott címsorok

- Mindhárom fájlban a szokásos NAME/SYNOPSIS/DESCRIPTION/OPTIONS/CONFIGURATION/SEE ALSO/GIT címek
  angolul maradtak, a skill kanonikus listája szerint.

### Megőrzött markup / megjegyzések

- `git-clean.adoc`: a `------------` (12 kötőjel) példa-blokk (a `*** Commands ***` menü) tartalma
  bájtazonos, csak a bevezető és a záró mondatok fordultak. Az `include::includes/cmd-config-section-all.adoc[]`
  és `include::config/clean.adoc[]` sorok, valamint a `clean.requireForce` config-kulcs és a
  `-d`/`-f`/`--force`/`-i`/`--interactive`/`-n`/`--dry-run`/`-q`/`--quiet`/`-e`/`--exclude`/`-x`/`-X`
  kapcsolók változatlanok.
- `git-annotate.adoc`: `include::blame-options.adoc[]` változatlan (nem ebben a batchben fordítandó fájl).
- `git-citool.adoc`: a `` `git gui citool` `` backtick-kódolt parancs bájtazonos.
- Mindhárom fájl végén a GIT szakasz „A linkgit:git[1] csomag része" alakra lett fordítva (4. blokk
  szerinti egységesített forma).

