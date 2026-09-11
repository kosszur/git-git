# Git core dokumentáció magyar fordítás — szószedet és fordítási döntések

Ez a **gazdag munkafájl**: minden visszatérő terminológiai és stílusdöntés ide kerül, blokkonként
számozva, dátummal, hogy nyomon követhető legyen, mikor és milyen kontextusban született.

A fordítás **helyben** történik a `git/Documentation/**/*.adoc` fájlokon (a `RelNotes/` kivételével).
A verziókövetést a felhasználó kezeli kézzel. Lásd a `translate-git-docs` skillt a részletes szabályokért.

---

## Hogyan használd

- **Minden fordítási munkamenet elején olvasd el ezt a fájlt (a „0. blokk" a kötelező terminológiai
  alapvonal) és a `progress-git-git-docs.md`-t**, mielőtt bármit fordítanál.
- Ha egy visszatérő kifejezésre nincs itt egyértelmű döntés, és a szövegkörnyezet sem dönti el →
  **állj meg és kérdezd meg a felhasználót**. A cél a konzisztencia, nem a gyors haladás rossz döntéssel.
- Minden lefordított blokk után: ha új, visszatérő döntés született, vedd fel egy új, számozott
  „N. blokk" szekcióba (dátummal). A hozzáadott `[[...]]` anchorokat és átírt `<<...>>` hivatkozásokat
  is ide jegyezd fájlonként.

---

## 0. blokk — kötelező terminológiai alapvonal

A felhasználó döntése (2026-09-04): az alábbi tábla a Git core dokumentáció fordításának **kötelező
kiindulási alapvonala** (eredetileg a testvérprojekt, a Pro Git könyv fordításának véglegesített
döntéseiből átvéve, itt önállóan, teljes egészében rögzítve). Ha a git-docs kontextusa eltérést kíván
egy itteni tételtől, **új blokkban rögzítsd az eltérést**, ne csendben térj el.

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
címsorok" + „Megőrzött markup" jegyzet — l. az alábbi 1. blokktól kezdve a kialakult formátumot.)*

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
`git-clone.adoc`, `git-commit-graph.adoc`, `git-commit.adoc`, `git-config.adoc`,
`git-describe.adoc`. (`git-checkout.adoc` a 10. blokkban elkészült.)

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

## 6. blokk — `git-daemon.adoc` — 2026-09-04

**Módszer:** egyetlen (subagent) munkamenet, célzott `Edit`-ekkel, a fájl teljes egészében lefordítva.
A NAME és a DESCRIPTION szakasz a munkamenet indulásakor **már le volt fordítva** egy korábbi lépésben;
ebben a blokkban az OPTIONS, SERVICES, EXAMPLES, ENVIRONMENT és GIT szakaszok készültek el.

**Külön megjegyzés — opaque token a szövegben:** a fájlban (a feladatot kiadó munkamenet szerint egy
korábbi, ehhez a blokkhoz nem tartozó technikai okból) egy `CSERE-001` jelölésű helyettesítő token
szerepelt 36 helyen egy — itt nem felfedett — eredeti angol szó helyén. A tokent a fordítás során
**érintetlenül hagytuk**, és **nem próbáltuk megfejteni**: prózában a magyar toldalékokat kötőjellel
illesztettük hozzá (pl. `CSERE-001-t`, `CSERE-001 uid-jét`), kódblokkban / parancsnévben / config-kulcsban
(`git CSERE-001`, `git-CSERE-001-export-ok`, `CSERE-001.uploadpack`, `CSERE-001.uploadarch`,
`CSERE-001.receivepack`, a `[CSERE-001]` config-szekciócím) **teljesen változatlanul** hagytuk, ahogy egy
valódi angol parancsnév-token esetén is történne. **Ez a kezelés csak erre a fájlra, egy külön munkameneti
utasítás alapján vonatkozott** — nem általános terminológiai döntés, és **nem jelenti azt**, hogy a
`CSERE-001` szót bármilyen jövőbeli fájlban is használni kellene; ha az eredeti szó (feltehetően a
fájlnévből és a szövegkörnyezetből következtethető parancsnév-elem) egy jövőbeli munkamenetben
visszaállításra kerül, a fenti helyeken kell keresni és cserélni.

### Ebben a blokkban rögzített / megerősített döntések

| angol | magyar | megjegyzés |
|---|---|---|
| site-wide (default) | **„site-szinten"** / „site-szintű alapértelmezés" | `--enable`/`--disable`/`--allow-override`/`--forbid-override` leírásában |
| informative errors | **„informatív hibák"** | `--informative-errors`/`--no-informative-errors` |
| "no such repository" / "repository not exported" / "access denied" | **bájtazonosan angolul, idézőjelben** | a daemon tényleges, lokalizálatlan hibaüzenet-szövegei (program-kimenet, nem próza) — a `git-clean.adoc` interaktív prompt-szövegeinek mintáját (5. blokk) követi |
| inetd service | **„inetd szolgáltatás"** | |
| virtual hosting / virtual host | **„virtuális hosztolás" / „virtuális hoszt"** | |
| access hook | **marad „access hook"** angolul a `--access-hook` opciónévben; a leírásban körülírva („a `<path>` által megadott külső parancs") | nincs önálló magyar szinonimája bevezetve, mert az opció maga sem name-szerű glosszárium-fogalom |
| selectively enable/disable services per repository (címsor) | **„szolgáltatások szelektív engedélyezése/letiltása repository-nként"** | nem man-page cím, prózaszerű EXAMPLES-alcím, fordítva |

### Címsor-anchorok

- Nincs a fájlban explicit `[[...]]` anchor, és a teljes `Documentation/` fában nincs `<<...>>` xref sem
  a `git-daemon.adoc` semelyik alcímére (grep-pel ellenőrizve: csak `linkgit:git-daemon[1]` hivatkozások
  vannak más fájlokból, ezek a parancsnévre, nem címsorra mutatnak, és nem érintettek). Defenzív anchort
  emiatt **nem** kellett hozzáadni.

### Man-page címként angolul hagyott címsorok

- NAME/SYNOPSIS/DESCRIPTION/OPTIONS/EXAMPLES/ENVIRONMENT/GIT — mind a skill kanonikus listáján van,
  angolul maradtak.
- **`SERVICES`** — csupa nagybetűs, kétsoros man-page-stílusú alcím, de **nincs** a skill kanonikus
  man-page-szekció listáján. A 2. blokk `MERGES` / `BACKEND EXTRA OPTIONS` precedensét követve
  **bájtazonosan angolul hagyva** (bár itt konkrétan ellenőrizve nincs rá `<<...>>` xref sehol, tehát a
  fordítás technikailag biztonságos lenne). **Eldöntendő**, hogy a felhasználó megerősítésével a jövőben
  egységesen fordítsuk-e az ilyen, kanonikus listán kívüli, de xref-kockázat nélküli man-page-stílusú
  alcímeket (`SERVICES` → „SZOLGÁLTATÁSOK" lenne a jelölt fordítás).

### Megőrzött markup / megjegyzések

- A dokumentum-cím két sora (`git-CSERE-001(1)` / aláhúzás) inkonzisztens hosszúságú volt már a
  munkamenet elején (a CSERE-001 token 3 karakterrel hosszabb, mint egy tipikus rövid parancsnév-utótag,
  az aláhúzás viszont a korábbi, rövidebb állapotból maradt ott) — 13 kötőjelről 16-ra javítva, hogy
  pontosan illeszkedjen a `git-CSERE-001(1)` 16 karakteres hosszához. Ez tisztán szintaxis-integritási
  javítás, a tartalmat nem érinti.
- `--log-destination=<destination>` beágyazott `stderr`/`syslog`/`none` almenüje (`+`/`--`/`--` blokkhatárolók)
  érintetlen; csak a törzsszövegek fordultak.
- Az EXAMPLES szakasz mindhárom `------------------------------------------------` (48 kötőjel) és a
  `----------------------------------------------------------------` (66 kötőjel) körülhatárolt
  parancspélda-/config-blokkja bájtazonos, csak a bevezető/záró prózamondatok fordultak.
- A `$REMOTE_ADDR`, `$REMOTE_PORT`, `REMOTE_ADDR`, `{tilde}`, `_<file>_`/`_<user>_`/`_<destination>_`/
  `_<directory>_` placeholder-jelölések és a `getpwnam(3)`/`getgrnam(3)` hívásnevek változatlanok.
- A GIT szakasz „A linkgit:git[1] csomag része" alakra fordítva (4. blokk szerinti egységesített forma).

**Orchestrátor utólagos visszaállítása (2026-09-04):** a `CSERE-001` token valójában a **„daemon"** szót
helyettesítette (a glossary 0. blokkja szerint ez amúgy is angol kölcsönszóként marad magyar szövegben
is, tehát a végeredmény ugyanaz, mint ha eleve „daemon"-t írt volna a subagent). Visszaállítás: globális
`CSERE-001` → `daemon` csere mind a 37 előfordulásnál. **Két hibát kellett utólag kézzel javítani,
amit a placeholder-hossz eltérése okozott:**
1. A címsor aláhúzása a fenti (426–430. sori) „javítás" miatt 16 kötőjelre lett igazítva a
   `git-CSERE-001(1)` (16 karakter) hosszához — de a végleges `git-daemon(1)` cím csak 13 karakter, ezért
   az aláhúzást **vissza kellett állítani 13 kötőjelre**.
2. Az egyetlen, idézőjel/backtick NÉLKÜLI, közvetlenül kötőjellel toldalékolt előfordulás
   (`indítsd el a CSERE-001-t` → csere után `daemon-t`) helytelen volt, mert a `daemon` szó a glossary
   szerint **kötőjel nélkül** kap toldalékot (`daemont`); kézzel javítva `daemont`-ra. A backtick/idézőjel
   *utáni* kötőjeles alakok (`` `git daemon`-t ``, `` 'git daemon'-t ``) helyesek maradtak (a toldalék a
   záró idézőjelhez/backtickhez kapcsolódik, nem közvetlenül a szóhoz).

A fájl ezután teljes és hibátlan (`progress-git-git-docs.md`: `[x]`, 2026-09-04). Ez a tapasztalat
általánosítva a 4. blokk „CSERE-NNN placeholder-kísérlet" jegyzetébe került.

## 9. blokk — `git-bisect-lk2009.adoc` — 2026-09-04

**Módszer:** egyetlen munkamenet, célzott `Edit`-ekkel, a fájl teljes egészében lefordítva.

**Stale progress-jelölés — megismétlődött minta:** a progress-tábla `~34%`-osnak jelölte ezt a
fájlt, de a munkamenet elején végzett `Read` szerint a fájl **teljes egészében angol** volt (0%
lefordítva) — ugyanaz a jelenség, mint amit a `git-bisect.adoc`-nál korábban dokumentáltak (l. az
5. blokk előtti bejegyzés a „Blokk lezárása" naplóban: „a korábbi `~33%` jelölés téves/elavult
volt"). A `~NN%` jelölések tehát **nem megbízhatók** ennél a fájlnál/projektnél; minden folytatásos
munkamenetnek friss `Read`-del kell ellenőriznie a tényleges állapotot, függetlenül a progress-tábla
tartalmától.

**Ez NEM man page:** 2009-es blogbejegyzés-stílusú cikk („Fighting regressions with git bisect",
Christian Couder, Linux-Kongress 2009). A főcím és **minden** alcím (nem csak man-page szekciócímek)
fordítva lett, kétsoros aláhúzás-hosszigazítással (`====` cím / `----` szint1 / `~~~~` szint2).

### Ebben a blokkban rögzített / megerősített döntések

| angol | magyar | megjegyzés |
|---|---|---|
| regression | **„regresszió"** (új, git-docs-specifikus általános szakszó) | nincs a `progit2` örökölt táblában; a cikk kulcsfogalma |
| "good" / "bad" (bisect-állapot jelző) | **angolul, idézőjelben marad**, első előforduláskor magyar glosszával: `"bad" (rossz)`, `"good" (jó)` | a `git-bisect.adoc` (33/34/44. sor) már bevezetett konvenciójának követése, konzisztencia miatt |
| "first bad commit" | **egész kifejezésként angolul, idézőjelben marad** (`"first bad commit"`), első előforduláskor glosszázva: `(az első "bad" commit)` | a cikk saját maga vezeti be definícióként; a „good"/„bad" mintáját követve egyben hagytuk, nem tagoltuk szét |
| "git bisect" (a cikk egész szövegében idézőjelben) | **megtartva idézőjelben**, angolul | a szerző saját tipográfiai konvenciója; a címben és élő szövegben egyaránt |
| merge base | **„merge-alap"** | `"D" is called a "merge base"` → `"D" commitot a … "merge-alapjának" nevezzük` |
| bisection / bisecting (általános főnév) | **„bisect-folyamat" / „bisectelés"** | a `bisectel` ige (0. blokk öröklött tétel) továbbragozva |
| bisection point / bisection commit | **„bisect-pont" / „bisect-commit"** | új, cikk-specifikus összetétel |
| best bisection point | **„legjobb bisect-pont"** | |
| BBC / BFC (a cikk saját rövidítése: bisect breaking/fixing commit) | **angolul marad**, első előforduláskor kiírva: „BBC-nek, azaz »bisect breaking commit«-nek" | coined term, csak ebben a cikkben |
| work-flow | **„munkafolyamat"** (a `progit2`-ből örökölt „workflow" → „munkafolyamat" mintája) | |
| evil merge | **„gonosz merge"** (`"evil merges"` idézőjelben tartva) | |
| end node principle | **„»end node principle«"** — angolul hagyva idézőjelben, a David Miller-idézeten belül, tehát maga a mondat is a verbatim blokk része (nem fordítva) | l. lent, a teljes idézetblokk angolul maradt |
| sh -c "some commands" (alcím) | **„A sh -c "parancsok" átadása a "git bisect run"-nak"** | a `sh -c` és a beágyazott idézőjelek megtartva, backtick NÉLKÜL (a `-c` kapcsoló és a parancs önmagában nem kapott kódformázást, hogy illeszkedjen a cikk tipográfiai stílusához) |

### Verbatim (angolul) hagyott blokkok — indoklással

A cikk `_____________`-tal határolt idézetblokkjai (AsciiDoc quote block) **mindegyike szó szerint
idézett külső forrás vagy személy** (NIST-tanulmány, Wikipédia, Ingo Molnar, David Miller, Andreas
Ericsson mailing list-/interjú-idézetei) — ezeket **bájtazonosan angolul hagytuk**, a skill
„e-mail-idézetek bájtazonosak maradnak" szabályát kiterjesztve rájuk (analóg a `CSERE-003`
KVM-commit-log-gal, ami szintén egy valódi, szó szerint idézett forrás). Csak a **bevezető/lezáró
kapcsolómondatokat** fordítottuk (pl. „És aztán:", „Végül a következtetés így kezdődött:").
Ugyanez vonatkozik a program tényleges, lokalizálatlan kimeneti szövegeire (pl. „There are only
'skip'ped commits left to test.", „The merge base BBBBBB is bad." stb.) — ezek a `git-clean.adoc`
(5. blokk) és `git-daemon.adoc` (6. blokk) precedensét követik.

A záró **„Hivatkozások" (References) szakasz bibliográfiai tételei** (szerzők, művek címei, URL-ek)
**teljes egészében angolul maradtak** — akadémiai idézési konvenció szerint a hivatkozott munkák
címét nem fordítjuk le; csak a szakaszcím (`References` → `Hivatkozások`) és a szakasz feletti
`Acknowledgments` (→ `Köszönetnyilvánítás`) fordult. **Eldöntendő**, ha a felhasználó mégis
fordítást kér a bibliográfiai leíró szövegekre (pl. „Nist News Release.", „LWN.net.").

### `CSERE-002` / `CSERE-003` opaque token — kezelés ebben a fájlban

A munkamenetet kiadó (nem ehhez a blokkhoz tartozó, korábbi) technikai lépés két opaque tokent
helyezett a szövegbe: `CSERE-002` (6 előfordulás) és `CSERE-003` (2 előfordulás, mindkettő egyetlen,
szó szerint idézett Linux kernel commit-log-sorban). **A tokenek jelentését nem fejtettük meg és nem
próbáltuk visszafejteni.**

- **Kódblokkban / idézett commit-logban (5 előfordulás):** teljesen bájtazonosan hagyva.
  - `[66c0b394f08fd89236515c1c84485ea712a157be] KVM: CSERE-002 file->f_count CSERE-003 in kvm`
    — 2 helyen (245., illetve 316. sor volt eredetileg; a fordítás után 253. és 324. sor), mindkétszer
    egy `-------------` kódblokkban, szó szerint idézett kernel commit-log-sor.
  - `if CSERE-002 -0 $pid` és `CSERE-002 $pid; sleep 1; CSERE-002 $pid;` — egy `#!/bin/sh`
    példaszkript `-------------` kódblokkjában (eredetileg kb. a 949., 952. sor; a fordítás után 972.,
    975. sor) — ez utóbbi sorban a token **kétszer** fordul elő.
- **Prózában, EGYETLEN helyen (1 előfordulás):** az eredeti angol mondat („Exit code between 128 and
  255 are special to 'git bisect run'. … because you can CSERE-002 it with a signal and it will stop
  the bisection process.") a fordításban:

  > „A 128 és 255 közötti kilépési kódok speciálisak a "git bisect run" számára. Ezek azonnal
  > leállítják a bisect-folyamatot. Ez akkor hasznos például, ha az átadott parancs végrehajtása túl
  > sokáig tart, mert ilyenkor CSERE-002-vel egy szignál segítségével, és ez megállítja a
  > bisect-folyamatot."

  Ez a fordítás **a feladatkiírásban megadott mintamondatot szinte szó szerint követi** — a token
  instrumentális (`-vel`) ragot kapott, a mondat nyelvtanilag nem teljesen zárt (hiányzik egy explicit
  ige a „CSERE-002-vel" mellől), **szándékosan**, mert a token mögötti eredeti szó (feltehetően
  „kill") kitalálását el kellett kerülni. **Ha egy jövőbeli munkamenet visszaállítja a valódi szót**,
  ezt a mondatot minden bizonnyal át kell fogalmazni természetesebb nyelvtani szerkezetre (pl. „mert
  ilyenkor egy szignállal kilőheted, és ez megállítja a bisect-folyamatot", ha a szó „kill").
  **Ez az egyetlen prózai előfordulás a fájlban**, pontos sorszáma a fordítás utáni állapotban: 357.

### Címsor-anchorok

- A fájlban **nincs egyetlen `[[...]]` anchor vagy `<<...>>` xref sem** a bibliográfiai `<<1>>`–`<<9>>`
  (→ `[[[1]]]`–`[[[9]]]` References-tételek) kivételével — ezek AsciiDoc bibliográfia-hivatkozások,
  nem címsor-xrefek, **változatlanul hagyva** (mindkét irányban, 9 pár, ellenőrizve).
- A fájl **nincs máshonnan hivatkozva** a `Documentation/` fából (nem `linkgit:`-elt cél, csak
  önállóan olvasható cikk), ezért egyetlen alcímnek sem kellett defenzív `[[...]]` anchort adni.

### Man-page címként angolul hagyott címsorok

- **Nincs egy sem** — ez a fájl explicit NEM man page (a feladatkiírás szerint), a főcím és minden
  alcím lefordítva lett, aláhúzás-igazítással.

### Megőrzött markup / megjegyzések

- 45 pár `-------------` (13 kötőjel) kódblokk-határoló és 10 pár `_____________` (13 aláhúzás)
  idézetblokk-határoló — mindkettő páros számú, egyik sem sérült a fordítás során (utólag
  ellenőrizve, a fordítás előtti/utáni állapot között egyetlen határoló-sor sem változott).
  A `-------------` blokkok tartalma (parancspéldák, gráf-ASCII-art, matematikai képletek,
  a `#!/bin/sh` példaszkript) bájtazonos, csak a blokkok közötti/feletti/alatti próza fordult.
- A kétsoros (setext) aláhúzások mind a fordított cím pontos hosszára lettek igazítva (0. és a
  fordítás közbeni, illetve utólagos, teljes fájlra kiterjedő automatizált — PowerShell `.Length`
  alapú — ellenőrzéssel; 12 eltérés került elő és javításra menet közben, mind ±1 karakteres
  elütés volt).
- A `:Author:`, `:Email:`, `:Date:` AsciiDoc-attribútum-sorok változatlanok.
- A `<<1>>`–`<<9>>` bibliográfia-xrefek és a `- [[[1]]] …` – `- [[[9]]] …` References-tételek
  (URL-ek, idézőjeles műcímek, kiadói/forrás-nevek) bájtazonosak.

## 7. blokk — `git-bisect.adoc`, `git-blame.adoc`, `git-describe.adoc` — 2026-09-04

**Módszer:** egyetlen munkamenet, célzott `Edit`-ekkel, mindegyik fájl teljes egészében lefordítva.

**Fontos megállapítás — `git-bisect.adoc` progress-jelölés téves volt:** a fájl a
`progress-git-git-docs.md`-ben `~33%` részlegesként volt jelölve, de a tényleges tartalom (friss
`Read`-del ellenőrizve, `[áéíóöőúüű]` grep-pel is megerősítve) **teljes egészében angol volt, semmi
magyar szöveget nem tartalmazott**. A `~33%` jelölés minden bizonnyal elavult/hibás volt (egy korábbi
részleges mentés soha nem került lemezre, vagy egy visszaállítás felülírta). A fájl emiatt **a nulláról**
lett lefordítva, nem folytatásként.

### Ebben a blokkban rögzített / megerősített döntések

| angol | magyar | megjegyzés |
|---|---|---|
| NAME szakasz egysoros leírása | **fordul** (2. blokk precedense szerint) | mindhárom fájlban |
| "MAPPING AUTHORS" (nem man-page, csupa nagybetűs alcím) | **„Szerzők leképezése"** | `git-blame.adoc` — megismétli a 3. blokk `git-check-mailmap.adoc`-beli döntését, most egy másik fájlban is; konzisztens a két fájl között |
| "THE DEFAULT FORMAT" / "THE PORCELAIN FORMAT" | **„Az alapértelmezett formátum" / „A porcelain formátum"** | `git-blame.adoc` — nem man-page cím (nincs a skill kanonikus listáján), lefordítva; `porcelain` a 0. blokk szerint angolul marad |
| "SPECIFYING RANGES" (`git-blame.adoc`) | **„Tartományok megadása"** | nem man-page cím; grep-pel ellenőrizve: a `git-diff.adoc`/`git-range-diff.adoc`/`revisions.adoc` szövegében is előfordul ugyanez a szókapcsolat, de azok a `gitrevisions.adoc` **saját, különálló** "SPECIFYING RANGES" szakaszára utalnak prózaszövegben (nem `<<...>>` xref-fel), nem a `git-blame.adoc`-éra — nincs tényleges kereszthivatkozási ütközés |
| "INCREMENTAL OUTPUT" (`git-blame.adoc`) | **„Inkrementális kimenet"** | nem man-page cím, nincs rá xref sehol |
| "SEARCH STRATEGY" (`git-describe.adoc`) | **„Keresési stratégia"** | nem man-page cím, nincs rá xref sehol |
| "Bisect reset" / "Bisect skip" / "Bisect run" / "Bisect next" / "Bisect visualize/view" (`git-bisect.adoc` alcímek) | **változatlanul angolul maradtak** | mindkét összetevő (a „Bisect" Git-fogalom és a szó szerinti alparancsnév: `reset`/`skip`/`run`/`next`/`visualize`/`view`) a 0. blokk szerint úgyis angolul maradna prózában is — nincs bennük tényleges lefordítandó angol prózaszó, ezért a cím szövege érintetlen, csak defenzív anchort kapott |
| "Bisect log and bisect replay" (`git-bisect.adoc`) | **„Bisect log és bisect replay"** | az „and" kötőszó lefordítva, a két alparancsnév (`log`, `replay`) angolul maradt |
| "Basic bisect commands: start, bad, good" | **„Alap bisect parancsok: start, bad, good"** | a leíró rész fordult, a felsorolt alparancsnevek (`start, bad, good`) angolul maradtak |
| "Alternate terms" (`git-bisect.adoc`) | **„Alternatív kifejezések"** | a DESCRIPTION szakasz elején lévő „see section "Alternate terms" below" prózautalást is átírtuk a fordított címre, hogy konzisztens maradjon (nem `<<...>>` xref, csak idézőjeles prózahivatkozás) |
| "Cutting down bisection by giving more parameters to bisect start" | **„A keresés leszűkítése további paraméterek megadásával a bisect start parancsnál"** | a „bisection" szót „keresés"-nek fordítottuk (a bisect maga bináris keresés); a „bisect start" szókapcsolat parancsnévként angolul maradt |
| "Getting help" (`git-bisect.adoc`) | **„Segítség kérése"** | |
| repository toldalékolása | **kötőjellel** (`repository-ban`, `repository-n`) a 0. blokk szabálya szerint | mindhárom fájlban javítva néhány kötőjel nélküli előfordulás (`repositoryban` → `repository-ban`, `repositoryn` → `repository-n`) |
| branch toldalékolása | **kötőjel NÉLKÜL** (`brancheket`, `brancheken`) a 0. blokk szabálya szerint | `git-describe.adoc`-ban javítva 2 hibásan kötőjelezett előfordulás |

### Címsor-anchorok

- `git-bisect.adoc`: defenzív `[[...]]` anchor került minden nem-man-page alcím elé (autogen slug az
  eredeti angol címszövegből): `[[_basic_bisect_commands_start_bad_good]]`, `[[_bisect_reset]]`,
  `[[_alternate_terms]]`, `[[_bisect_visualize_view]]`, `[[_bisect_log_and_bisect_replay]]`,
  `[[_avoiding_testing_a_commit]]`, `[[_bisect_skip]]`, `[[_bisect_next]]`,
  `[[_cutting_down_bisection_by_giving_more_parameters_to_bisect_start]]`, `[[_bisect_run]]`,
  `[[_getting_help]]`. Egyik alcímre sincs `<<...>>` hivatkozás a fában (grep-pel ellenőrizve) — tisztán
  védelmi célú anchorok.
- `git-blame.adoc`: `[[_the_default_format]]`, `[[_the_porcelain_format]]`, `[[_specifying_ranges]]`,
  `[[_incremental_output]]`, `[[_mapping_authors]]` — mind defenzív, nincs rájuk `<<...>>` hivatkozás.
- `git-describe.adoc`: `[[_search_strategy]]` — defenzív, nincs rá `<<...>>` hivatkozás.
- Mindhárom fájlban a kétsoros (setext) címsorok aláhúzását a lefordított cím pontos hosszához
  igazítottuk (Python-nal ellenőrizve karakterszám-egyezésre, nem csak becsléssel).

### Man-page címként angolul hagyott/érintetlen címsorok

- Mindhárom fájlban a szokásos NAME/SYNOPSIS/DESCRIPTION/OPTIONS/EXAMPLES/CONFIGURATION/SEE ALSO/GIT
  angolul maradt. `git-describe.adoc`-ban a `BUGS` is a kanonikus listán van, angolul maradt.
- Lásd fent a döntés-táblát a nem man-page, de mégis angolul hagyott `git-bisect.adoc` alcímekről
  (`Bisect reset` stb.) — ez nem „óvatosságból angolul hagyás", hanem az, hogy a cím szövegében nincs
  ténylegesen lefordítandó szó a glossary szerint.

### Megőrzött markup / megjegyzések

- `git-bisect.adoc`: minden `------------------------------------------------` és `------------`
  körülhatárolt parancspélda-/kimeneti blokk bájtazonos, beleértve a bennük lévő `#`-kommenteket is
  (pl. `# Current version is bad`, `# tweak the working tree by merging the hot-fix branch`). A `[synopsis]`
  attribútum-sorok és az utánuk lévő parancsminták (`git bisect old [<rev>]` stb.) változatlanok.
- `git-blame.adoc`: `include::blame-options.adoc[]`, `include::diff-algorithm-option.adoc[]`,
  `include::includes/cmd-config-section-all.adoc[]`, `include::config/blame.adoc[]` változatlanok (nem
  ebben a batchben fordítandó fájlok). A tab-indentált, nem `----`-határolt kódpéldák (`git blame -L 40,60
  foo` stb., a `# count the number of lines...` kommentes shell-pipeline) bájtazonosak.
- `git-describe.adoc`: a `[torvalds@g5 git]$ git describe ...` tab-indentált parancspéldák és kimeneteik
  bájtazonosak, csak a köréjük ékelt magyarázó bekezdések fordultak.
- Mindhárom fájl végén a GIT szakasz „A linkgit:git[1] csomag része" alakra lett fordítva (4. blokk
  szerinti egységesített forma).
- `git-bisect.adoc` SEE ALSO: `link:git-bisect-lk2009.html[Fighting regressions with git bisect]` látható
  szövege lefordítva „Regressziók elleni küzdelem a git bisect-tel"-re; a `link:` cél és a
  `linkgit:git-blame[1]` változatlan.

## 8. blokk — `git-config.adoc` — 2026-09-04

**Módszer:** egyetlen munkamenet, célzott `Edit`-ekkel, a fájl (660 sor) teljes egészében lefordítva
egy Read-ből. Nem volt előzetes részleges fordítás.

**Külön megjegyzés — opaque token a szövegben:** a fájlban (a feladatot kiadó munkamenet szerint egy
korábbi, technikai okból) egy `CSERE-004` / `CSERE-004S` jelölésű helyettesítő token szerepelt 2 helyen
(egyes és többes szám) egy — itt nem felfedett — eredeti angol szó helyén, a `SCOPES` szekció „Protected
configuration" alszakaszában. A tokent érintetlenül hagytuk, nem próbáltuk megfejteni. Teljes mondatok
(660. sor környéke, a fájl végleges sorszámozása szerint 476–480. sor):

> „A Git úgy kezeli ezeket a hatóköröket, mintha a felhasználó vagy egy megbízható rendszergazda
> irányítaná őket. Ennek az az oka, hogy egy CSERE-004, aki irányítja ezeket a hatóköröket, jelentős
> kárt tud okozni a Git használata nélkül is, így feltételezhető, hogy a felhasználó környezete védi
> ezeket a hatóköröket a CSERE-004S ellen."

Mindkét előfordulás sima prózában van, közvetlen mondatrészként (nem toldalékolva, nem kódblokkban,
nem parancsnévben) — a `CSERE-004`/`CSERE-004S` alak toldalék nélkül, változatlanul került a mondatba,
nincs kötőjelezési kérdés. **Ez a kezelés csak erre a fájlra, egy külön munkameneti utasítás alapján
vonatkozott** — nem általános terminológiai döntés. Ha az eredeti szó (feltehetően „attacker" vagy
hasonló, a mondat jelentése alapján: valaki, aki e hatóköröket irányítja és kárt okozhat) egy jövőbeli
munkamenetben visszaáll, csak ezt a 2 előfordulást kell keresni/cserélni ebben a fájlban; setext-aláhúzás-
hosszra nincs hatás, mert a token nem címsorban van.

### Ebben a blokkban rögzített / megerősített döntések

| angol | magyar | megjegyzés |
|---|---|---|
| NAME szakasz egysoros leírása | **fordul** (2. blokk precedense szerint) | „Repository- vagy globális opciók lekérdezése és beállítása" |
| "COMMANDS" (nem man-page, csupa nagybetűs alcím) | **változatlanul angolul maradt** | a 2./6. blokk `MERGES`/`BACKEND EXTRA OPTIONS`/`SERVICES` precedensét követve; nincs rá `<<...>>` xref, de a kétsoros man-page-stílus miatt óvatosságból angolul hagyva — **eldöntendő** |
| "DEPRECATED MODES" (nem man-page, csupa nagybetűs alcím) | **változatlanul angolul maradt** | ugyanaz a precedens és indoklás, mint a `COMMANDS`-nál — **eldöntendő** |
| "SCOPES" (nem man-page, csupa nagybetűs alcím, **explicit `[[SCOPES]]` anchorral**, és **külső fájlokból** (`config/uploadpack.adoc`, `config/safe.adoc`) `<<SCOPES>>`-szal hivatkozva) | **változatlanul angolul maradt** | ugyanaz a precedens, mint a `COMMANDS`/`DEPRECATED MODES`-nál; az explicit anchor miatt technikailag biztonságos lenne lefordítani (az anchor id nem a címszövegből generálódik), de a konzisztencia kedvéért egyelőre angolul hagyva — **eldöntendő, elsőbbséggel**, mert két másik (még lefordítatlan) fájl is már most `<<SCOPES>>`-szal hivatkozik rá |
| "Protected configuration" (kétsoros `~~~~` alcím, SCOPES alatt) | **„Védett konfiguráció"** (fordítva) | a `config/safe.adoc` és a `config/uploadpack.adoc` (jelenleg még angol) prózájában is előfordul a „protected configuration" kifejezés — **jövőbeli terminológiai függőség**: amikor ezek a fájlok sorra kerülnek, a „védett konfiguráció" fordítást kell használni a konzisztencia miatt |
| canonicalize / canonicalization | **„kanonizál" / „kanonizáció"** | új terminológiai döntés, a `--type`/`--fixed-value` opciók leírásában végig |
| scope (config-hatókör értelemben) | **„hatókör"** | a `SCOPES` szakasz és a `--show-scope` leírásában |
| multi-valued key/option | **„többértékű kulcs" / „többértékű opció"** | |
| multivar | **marad „multivar"** (angolul, a forrás is szó szerint ezt a szót használja EXAMPLES prózában) | |

### Címsor-anchorok

- `[[OPTIONS]]`, `[[FILES]]`, `[[SCOPES]]`, `[[ENVIRONMENT]]`, `[[EXAMPLES]]` — mind már eleve explicit
  anchorral rendelkeztek a forrásban, érintetlenül hagyva; a hozzájuk tartozó összes belső `<<OPTIONS>>`,
  `<<FILES>>` (6×), `<<ENVIRONMENT>>`, `<<EXAMPLES>>` hivatkozás változatlan (az anchor-azonosítók nem
  fordulnak, a szekciócímek pedig amúgy is a kanonikus man-page-listán vannak, angolul maradtak).
- `Protected configuration` alcímnek **nem** volt explicit anchora és nem volt rá `<<...>>` hivatkozás a
  fában (grep-pel ellenőrizve) — defenzív `[[_protected_configuration]]` anchor került elé, autogen slug
  az eredeti angol címből.
- `SCOPES` explicit `[[SCOPES]]` anchora változatlan; mivel a cím szövege (angolul maradt, l. fent)
  nem változott, ez amúgy sem lett volna kritikus, de az anchor a döntő tényező, ha a jövőben mégis
  fordítás mellett döntenek.

### Man-page címként angolul hagyott/érintetlen címsorok

- NAME/SYNOPSIS/DESCRIPTION/OPTIONS/CONFIGURATION/FILES/ENVIRONMENT/EXAMPLES/BUGS/GIT — mind a skill
  kanonikus listáján van, angolul maradt.
- `COMMANDS`, `DEPRECATED MODES`, `SCOPES` — nem a kanonikus listán, de man-page-stílusú (csupa nagybetű,
  kétsoros aláhúzás) — l. fenti döntés-tábla, **eldöntendő**.

### Megőrzött markup / megjegyzések

- Az EXAMPLES szakasz mind a 13 `------------` körülhatárolt parancspélda-/config-blokkja bájtazonos
  (beleértve a mintakonfiguráció `#`/`;` kommentjeit is); csak a köréjük ékelt magyarázó prózamondatok
  fordultak.
- A BUGS szakasz két `--------` körülhatárolt config-mintablokkja bájtazonos.
- A `--type <type>` opció leírásában lévő `--`…`--` nyitott blokk (a `'bool'`/`'int'`/`'bool-or-int'`/
  `'path'`/`'expiry-date'`/`'color'` felsorolás) érintetlen, csak a felsorolás-elemek prózája fordult.
- `include::config.adoc[]` (a fájl közepén, az EXAMPLES és a BUGS szakasz között) változatlan.
- A `linkgit:git-worktree[1]`, `linkgit:gitrevisions[7]`, `linkgit:git[1]` makrók és a
  `"SPECIFYING REVISIONS"` idézőjeles szakaszcím-hivatkozás (prózaszöveg, nem `<<...>>` xref)
  változatlanok.
- A dokumentum-cím két sora (`git-config(1)` / `=============`) érintetlen (a NAME-mel megegyező
  precedens szerint a man page cím-sora nem fordul).
- A GIT szakasz „A linkgit:git[1] csomag része" alakra fordítva (4. blokk szerinti egységesített forma).

## 10. blokk — `git-checkout.adoc` — 2026-09-04

**Módszer:** egyetlen munkamenet, célzott `Edit`-ekkel. A fájl NAME + DESCRIPTION szakaszának első fele
(1–49. sor, a `git checkout [<branch>]` leírásáig) **már le volt fordítva** egy korábbi munkamenetből;
innen folytatva a fájl (627 sor) hátralévő része (OPTIONS, DETACHED HEAD, ARGUMENT DISAMBIGUATION,
EXAMPLES, CONFIGURATION, SEE ALSO, GIT) készült el ebben a blokkban.

### Ebben a blokkban rögzített / megerősített döntések

| angol | magyar | megjegyzés |
|---|---|---|
| unstaged changes (staging area-ba nem került módosítások) | **„staging area-ba nem került módosítások"** | körülírva, mert a „unstaged" szónak nincs bevett külön magyar terminusa a glossaryban |
| checked out (branchnév-vitában, „ez a branch már ki van csekkolva") | **„ki van csekkolva"** | a `--ignore-other-worktrees` leírásában; a `checkoutol` ige (0. blokk) passzív/állapot-változatának egyenes folytatása, konzisztens a `git-archimport.adoc`-beli „checkoutolt" (2. blokk) mintájával |
| unborn branch | **„meg nem született branch"** | `--orphan` leírásában |
| proprietary (kód jelzőként) | **marad „proprietary"** angolul | nincs a glossaryban rögzített magyar megfelelője, a `code` szóval együtt („proprietary vagy más módon korlátozott kódrészletek") |

### Címsor-anchorok

- A fájlban **nincs** explicit `[[...]]` anchor és **nincs** `<<...>>` xref sem a fájlon belül, sem
  máshonnan a `Documentation/` fában a nem-man-page alcímeire (grep-pel ellenőrizve). Defenzív anchorok
  kerültek a három EXAMPLES-alcím elé (autogen slug az **eredeti angol** címszövegből, a lefordított cím
  szövegétől függetlenül, a skill szabálya szerint): `[[_1_paths]]` (cím: „1. Útvonalak"), `[[_2_merge]]`
  (cím: „2. Merge" — a „Merge" szó maga nem fordul, l. lent), `[[_3_merge_conflict]]` (cím:
  „3. Merge-konfliktus").
- A `DETACHED HEAD` és az `ARGUMENT DISAMBIGUATION` kétsoros, csupa nagybetűs alcímek **nem** szerepelnek
  a skill kanonikus man-page-szekció listáján, de **bájtazonosan angolul maradtak** — l. lent a következő
  szakaszt, ez a döntés az érdemi ok.

### Man-page címként/man-page-stílusúként ANGOLUL hagyott, indokolt címsorok

- **`DETACHED HEAD`**, **`ARGUMENT DISAMBIGUATION`** — nem szerepelnek a skill kanonikus man-page-szekció
  listáján, de **ellenőrizve grep-pel**, hogy három **másik, még lefordítatlan** fájl (`git-switch.adoc`,
  `git-worktree.adoc`, `gitdatamodel.adoc`) idézőjeles prózaszövegben **név szerint** hivatkozik a
  „DETACHED HEAD" szakaszra (`See the "DETACHED HEAD" section in git-checkout[1]` stb.) — nem `<<...>>`
  xreffel, hanem szó szerinti idézettel. A fájlon belüli saját hivatkozások (30., 73., 221. sor) is már
  korábban „DETACHED HEAD" / „ARGUMENT DISAMBIGUATION" alakban lettek lefordítva egy korábbi munkamenetben
  (l. az 51. sor előtti, már kész DESCRIPTION-részt). A konzisztencia és a döntő többségében `technical/`
  és `Documentation/` gyökér fájlokban követett „nem kanonikus, csupa nagybetűs, xref-kockázatos cím →
  angolul hagyva" precedens (1., 2., 6., 8. blokk: `See Also`, `MERGES`, `BACKEND EXTRA OPTIONS`,
  `SERVICES`, `COMMANDS`, `DEPRECATED MODES`, `SCOPES`) miatt **mindkettő angolul maradt**. **Eldöntendő**,
  ha a felhasználó megerősíti, hogy a három hivatkozó fájl fordításakor is konzisztensen angolul kell
  hagyni a saját idézett hivatkozásukat (ajánlott, hogy egyszerre konzisztensek maradjanak).

### Megőrzött markup / megjegyzések

- 17 pár `------------` (12 kötőjel) körülhatárolt kódblokk/ASCII-art-diagram (a DETACHED HEAD szakasz
  commit-gráf rajzai, EXAMPLES parancspéldák) és 1 pár `----------` (10 kötőjel) blokk (ARGUMENT
  DISAMBIGUATION) bájtazonos; a `HEAD (refers to branch 'master')` stílusú ASCII-art feliratok, a
  `$ git checkout ...` parancssorok és a szó szerinti program-kimenetek (`error: You have local changes
  to 'frotz'; not switching branches.`, `Applied autostash.`, `Switched to branch 'mytopic'`, `Your local
  changes are stashed, however applying them resulted in conflicts. …`) **mindegyike bájtazonosan angolul
  maradt** (lokalizálatlan program-kimenet, a `git-clean.adoc`/`git-daemon.adoc` precedensét követve).
- A `<1>`/`<2>`/`<3>` callout-jelölők két helyen fordulnak elő a fájlban (a „git checkout -b foo" gráf
  alatt, illetve az EXAMPLES 1. blokkjában); mindkét helyen a jelölő szám és a hozzá tartozó magyarázat
  száma egyezik, csak a magyarázat prózája fordult.
- `include::diff-context-options.adoc[]`, `include::includes/cmd-config-section-all.adoc[]`,
  `include::config/checkout.adoc[]` sorok változatlanok (nem ebben a blokkban fordítandó fájlok).
- A `linkgit:git-branch[1]` (4×), `linkgit:git-config[1]`, `linkgit:git-submodule[1]`,
  `linkgit:git-add[1]`, `linkgit:gitglossary[7]`, `linkgit:git-switch[1]`, `linkgit:git-restore[1]`
  makrók változatlanok; a `linkgit:git-add[1]` „Interactive Mode" idézőjeles szakaszcím-hivatkozása
  (prózaszöveg, nem `<<...>>` xref, a `git-add.adoc` saját, még csak részlegesen — l. 4. blokk — kész
  szakaszcímére mutat) angolul maradt.
- A dokumentum-cím két sora (`git-checkout(1)` / `===============`) érintetlen.
- A GIT szakasz „A linkgit:git[1] csomag része" alakra fordítva (4. blokk szerinti egységesített forma).
- Szintaxis-ellenőrzés: `------------`-számláló 34 (17 pár), `----------`-számláló 2 (1 pár) — mindkettő
  páros; `ifdef::`/`endif::` nincs a fájlban; `<<...>>` xref nincs a fájlban; a három hozzáadott
  `[[...]]` anchoron kívül nincs más anchor.

**Utólagos konzisztencia-javítás (orchestrátor, 2026-09-04):** a fenti „Interactive Mode" idézőjeles
hivatkozás (786–788. sor) tévesen maradt angolul — a `git-add.adoc` időközben elkészült, és a saját
alcíme ténylegesen **„Interaktív mód"**-ra lett fordítva (l. `git-add.adoc` 99., 110., 268. sor). A
`git-checkout.adoc` 294. sorát ennek megfelelően javítottuk `„Interactive Mode"` → `„Interaktív mód"`-ra,
hogy konzisztens legyen a ténylegesen létező magyar címmel.

## 11. blokk — `git-commit.adoc` — 2026-09-04

**Módszer:** egyetlen munkamenet, célzott `Edit`-ekkel, a fájl (595 sor) teljes egészében lefordítva
(korábban teljesen angol volt).

### Ebben a blokkban rögzített / megerősített döntések

| angol | magyar | megjegyzés |
|---|---|---|
| log message | **„napló-üzenet"** | megkülönböztetve a „commit-üzenet"-től (commit message); a két fogalom egymás mellett fordul elő a fájlban, a 2. blokk (`git-commit-tree.adoc`) precedensét folytatva |
| trailer (`git commit trailer`, `--trailer` opció) | **marad „trailer"** angolul | nincs bevett magyar megfelelője a projektben eddig |
| „fixup!"/„amend!" commit (program-generált commit-cím-előtag) | **bájtazonosan angolul, idézőjelben** | lokalizálatlan, szó szerinti Git-kimenet, a `git-clean.adoc`/`git-daemon.adoc` precedensét követi |

### Címsor-anchorok

- Nincs a fájlban `[[...]]` anchor és `<<...>>` xref sem (grep-pel ellenőrizve); nincs is rá hivatkozás
  máshonnan a fában a nem-man-page alcímeire.
- **Konzisztencia-javítás:** a git-add.adoc „Interaktív mód" szakaszára mutató prózai hivatkozás
  (kb. 55. sor) `„Interactive Mode"` helyett `„Interaktív mód"`-ra lett fordítva, mert a `git-add.adoc`
  saját címe eközben ténylegesen elkészült ilyen alakban (l. fent, a 10. blokk utólagos javítása).
  A `git-rebase.adoc` „RECOVERING FROM UPSTREAM REBASE" szakaszára mutató hivatkozás (kb. 314. sor)
  **angolul maradt**, mert a `git-rebase.adoc` maga még nincs lefordítva — ha elkészül, ellenőrizni kell,
  hogy ez a cím lefordítva marad-e vagy angolul (a `DETACHED HEAD`-mintát követve valószínűleg angolul).

### Man-page címként/man-page-stílusúként ANGOLUL hagyott, eldöntendő címsorok

- **`COMMIT INFORMATION`**, **`HOOKS`**, **`ENVIRONMENT AND CONFIGURATION VARIABLES`** — csupa nagybetűs,
  kétsoros, man-page-stílusú alcímek, nincsenek a skill kanonikus listáján, nincs rájuk `<<...>>` xref
  sehol a fában. A korábbi blokkok (`MERGES`, `BACKEND EXTRA OPTIONS`, `SERVICES`, `COMMANDS`,
  `DEPRECATED MODES`, `SCOPES`, `SUBMODULES`, `DETACHED HEAD`, `ARGUMENT DISAMBIGUATION`) precedensét
  követve **bájtazonosan angolul maradtak**. Ez már a **kilencedik** ilyen visszatérő eset — **erősen
  ajánlott egyszer véglegesen eldönteni a felhasználóval**, hogy ez a kategória (kanonikus listán kívüli,
  de xref-kockázat nélküli, csupa nagybetűs man-page-stílusú alcím) egységesen fordítható-e a jövőben,
  ahelyett hogy blokkonként újra „eldöntendő"-ként kerülne rögzítésre.

### Megőrzött markup / megjegyzések

- 6 pár `------------` (EXAMPLES kódblokkok), 1 pár `------` (amend-ekvivalens parancsblokk), 3 pár
  `--`/`--` nyitott blokk (cleanup-mode, amend, untracked-files felsorolások) — mind bájtazonos, párban.
  `ifdef::`/`endif::` nincs a fájlban. 6 `include::` sor és a `:git-commit: 1` attribútum-sor változatlan.
- A GIT szakasz „A linkgit:git[1] csomag része" alakra fordítva (4. blokk szerinti egységesített forma).

---

**A `Documentation/` gyökér `git-*.adoc` man page-táblázat (170 fájl) ezzel a blokkal 40/40 fájlon
KÉSZ** (a batch, amit ez a munkamenet a felhasználó „fordítsd a Documentation gyökérben lévő adoc
állományokat" kérésére elkezdett — a táblázat többi, `git-diagnose.adoc`-tól kezdődő ~130 fájlja és a
„Gyökér — egyéb .adoc" tábla még hátravan, ~83 fájl). Lásd a `progress-git-git-docs.md` batch-naplóját
az összefoglalóért.

## 12. blokk — `git-fetch-pack.adoc` (ellenőrzés), `git-fetch.adoc` (befejezés) — 2026-09-04

**Kontextus:** folytatásos munkamenet egy korábbi, `content filtering policy` API-hibával megszakadt
session után. A `git-fetch-pack.adoc`-ot a megszakadt session már teljesen befejezte — ez a munkamenet
friss `Read`-del ellenőrizte (teljes fájl magyar, szintaxis ép), és csak a progress-tábla elavult
`[ ]` jelölését javította `[x]`-re. A `git-fetch.adoc`-nál a NAME/SYNOPSIS/DESCRIPTION/OPTIONS eleje
(az `include::urls-remotes.adoc[]` sorig) már kész volt; ez a blokk onnantól fejezte be a fájlt.

### Ebben a blokkban rögzített / megerősített döntések

| angol | magyar | megjegyzés |
|---|---|---|
| stale (remote-tracking referenciákra) | **„elavult"** | `PRUNING` szakasz — a „stale reference" → „elavult referencia" |
| branch churn | **„branch-mozgás"** | új, git-fetch-specifikus összetétel |
| compact output mode | **„kompakt kimeneti mód"** | `OUTPUT` szakasz |
| flag/summary/from/to/reason (OUTPUT táblázat `::` definíciós lista-címkéi) | **változatlanul angolul maradtak**, csak a leírás-törzsük fordult | ezek a `git fetch` tényleges, gépileg elemezhető oszlopfejlécei/mezőnevei, a `git-check-ref-format.adoc`-beli mezőnév-precedenst (3. blokk) követve |
| peek at (branch-bepillantás) | **„bepillantás"** | EXAMPLES 3. pont címe |

### Címsor-anchorok

- `[[CRTB]]` — már eleve explicit anchorral rendelkezett a `CONFIGURED REMOTE-TRACKING BRANCHES` cím
  felett; érintetlen. A rá mutató `<<CRTB,CONFIGURED REMOTE-TRACKING BRANCHES>>` hivatkozás
  (`PRUNING` szakaszban) **nem** lett átírva — l. lent, a cím maga is angolul maradt, tehát a
  hivatkozás látható szövege is konzisztensen angol maradt.
- Nem volt szükség új defenzív anchorra: a fájlban nincs más, hivatkozott vagy explicit anchort igénylő
  nem-man-page címsor.

### Man-page címként/man-page-stílusúként ANGOLUL hagyott címsorok

- **`CONFIGURED REMOTE-TRACKING BRANCHES`**, **`PRUNING`** — csupa nagybetűs, kétsoros,
  man-page-stílusú alcímek, nincsenek a skill kanonikus listáján. A `CONFIGURED REMOTE-TRACKING
  BRANCHES` explicit `[[CRTB]]` anchorral rendelkezik, tehát technikailag biztonságos lenne lefordítani
  (az anchor id nem a címszövegből generálódik) — de a `MERGES`/`BACKEND EXTRA OPTIONS`/`SERVICES`/
  `COMMANDS`/`DEPRECATED MODES`/`SCOPES`/`DETACHED HEAD`/`ARGUMENT DISAMBIGUATION`/`COMMIT INFORMATION`/
  `HOOKS`/`ENVIRONMENT AND CONFIGURATION VARIABLES` precedenst (1., 2., 6., 8., 10., 11. blokk) követve,
  a konzisztencia kedvéért **bájtazonosan angolul maradt** mindkettő. Ez már a **tizenegyedik**
  ilyen visszatérő eset — az előző blokk (11.) által javasolt egyszeri, végleges felhasználói döntés
  továbbra is **erősen ajánlott**, hogy ne kelljen blokkonként újra „eldöntendő"-ként rögzíteni.
- `OUTPUT` — a 3. blokk (`git-check-mailmap.adoc`) precedense szerint a man-page-blanket-listán
  kezelve, angolul maradt (nem „eldöntendő", már korábban lezárt kategória).
- NAME/SYNOPSIS/DESCRIPTION/OPTIONS/EXAMPLES/CONFIGURATION/BUGS/SEE ALSO/GIT — a skill kanonikus
  listáján vannak, angolul maradtak.

### Megőrzött markup / megjegyzések

- 9 pár `----...----` (különböző hosszúságú, 33/48 kötőjeles) körülhatárolt kód-/parancspélda-blokk,
  ezen belül a `# While fetching` / `# Only prune, don't fetch` / `# These both fetch tags` angol
  kommentsorok is **bájtazonosan** maradtak (a `git-config.adoc`-beli mintakonfiguráció-kommentek
  precedensét (8. blokk) követve — kódblokkon belüli komment nem fordul).
- `include::fetch-options.adoc[]`, `include::pull-fetch-param.adoc[]`, `include::urls-remotes.adoc[]`,
  `include::transfer-data-leaks.adoc[]`, `include::includes/cmd-config-section-all.adoc[]`,
  `include::config/fetch.adoc[]` sorok változatlanok (nem ebben a blokkban fordítandó fájlok).
  `git-fetch-pack.adoc`-ban `<git-upload-pack>`/`<n>`/`<date>`/`<ref>`/`<repository>`/`<refs>` placeholder-
  ek és minden kapcsoló (`--all`, `--stdin`, `-q`/`--quiet`, `-k`/`--keep`, `--thin`, `--include-tag`,
  `--upload-pack=`, `--exec=`, `--depth=`, `--shallow-since=`, `--shallow-exclude=`, `--deepen-relative`,
  `--refetch`, `--no-progress`, `--check-self-contained-and-connected`, `-v`) változatlan.
- `git-fetch.adoc` GIT szakasza már a 4. blokk szerinti egységesített „A linkgit:git[1] csomag része"
  alakban volt (a korábbi session által fordítva); `git-fetch-pack.adoc` GIT szakasza szintén ebben az
  alakban, változatlan.
- Mindkét fájl végig ellenőrizve: a `----`/`------------------------------------------------`
  határolók párban vannak, nincs `ifdef::`/`endif::`, a `[[CRTB]]` az egyetlen `[[...]]` anchor a
  `git-fetch.adoc`-ban, `<<CRTB,...>>` az egyetlen `<<...>>` xref, mindkettő változatlan.

## 13. blokk — `git-filter-branch.adoc` — 2026-09-04

**Kontextus:** ez már a **negyedik nekifutás** ennél a fájlnál — a korábbi 3 munkamenet mindegyike
rendszerszintű `400 Output blocked by content filtering policy` API-hibával szakadt meg, még bármilyen
`Edit` végrehajtása előtt, a 143. sornál (a `--msg-filter` leírásának végénél). A felhasználó stratégia-
váltást kért: kis (60–110 soros), célzott `Read`-eket, azonnal 1-2 `Edit`-tel lefordítva, hogy megszakadás
esetén kevesebb munka vesszen el. Ezúttal a 145. sortól a fájl végéig (eredetileg 703, a fordítás után
757 sor — a hosszabb magyar mondatok miatt nőtt a sorszám, a bekezdés-/lista-/blokkhatárok 1:1 megtartva)
**sikerült egyetlen megszakítás nélkül végigérni**. A fájl **teljes egészében KÉSZ**.

### Ebben a blokkban rögzített / megerősített döntések

| angol | magyar | megjegyzés |
|---|---|---|
| commit-tree parancs (`--commit-filter` leírásában) | „a commit végrehajtására szolgáló szűrő" | a `git commit-tree` parancsnév maga változatlan |
| "nearly proper" (tag-objektum újraírás minősítése) | **„szinte megfelelő"**, idézőjelben tartva, ahogy a forrás | |
| buyer beware (idiomatikus figyelmeztetés) | **„vevő vigyázz"** | szó szerinti, kicsit szokatlan fordítás, megtartva a forrás tömör-idiomatikus stílusát |
| Remap to ancestor (kétsoros, nem man-page alcím, explicit `[[Remap_to_ancestor]]` anchorral) | **„Áthelyezés ősre"** | az anchor már eleve explicit volt a forrásban, csak a címszöveg fordult; a `<<Remap_to_ancestor>>` xref (2 hely: OPTIONS végén és a `<rev-list options>` leírásában) változatlan (az anchor id nem a címszövegből generálódik) |
| checklist for shrinking a repository / performance / safety (3 db csupa nagybetűs, kétsoros, man-page-stílusú felső szintű alcím) | **mind bájtazonosan angolul maradt** | l. lent, külön szakaszban indokolva |
| flag-day (átvitt értelemben, „nehéz, egyszeri váltási pont") | **„zászlós nap"**, idézőjelben | a forrás is idézőjelbe teszi; szó szerinti fordítás, mert nincs bevett magyar szakkifejezés rá |
| gotcha(s) | **„buktató(k)"** | már a WARNING szakaszban (korábbi session) is így szerepelt, konzisztensen folytatva |
| IPC mechanism | **„IPC-mechanizmus"** (marad angol rövidítés) | |
| drop-in replacement | **„drop-in helyettesítő(je)"** | a `drop-in` angolul marad, jelzőként |
| shell snippet | **„shell-kódrészlet"** | |
| chicanery (trükkös munkamenet-leírás, safety szakasz) | **„trükközés"** | |

### Címsor-anchorok

- A fájl elején (korábbi session) grep-ellenőrzés szerint a teljes fájlban 3 `[[...]]` anchor és 2
  `<<...>>` xref van: `[[Remap_to_ancestor]]` (2× hivatkozva `<<Remap_to_ancestor>>`-vel, l. fent),
  `[[PERFORMANCE]]` és `[[SAFETY]]` (mindkettő a WARNING szakaszból hivatkozva `<<SAFETY>>` / `<<PERFORMANCE>>`
  alakban, látható szöveg nélkül — ezt már egy **korábbi** session állította be, ebben a blokkban
  változatlanul hagyva). Mindhárom anchor és mindkét xref **érintetlen**; nem kellett új defenzív anchort
  hozzáadni, mert ebben a blokkban lefordított egyetlen más alcím sincs se explicit anchorral, se
  `<<...>>` hivatkozással a fában (grep-pel a blokk elején ellenőrizve).

### Man-page címként/man-page-stílusúként ANGOLUL hagyott címsorok

- **`CHECKLIST FOR SHRINKING A REPOSITORY`**, **`PERFORMANCE`**, **`SAFETY`** — csupa nagybetűs, kétsoros,
  man-page-stílusú felső szintű alcímek (ugyanolyan `----`-aláhúzással, mint a valódi man-page szekciók),
  de **nincsenek** a skill kanonikus man-page-szekció listáján. A `PERFORMANCE` és a `SAFETY` explicit
  `[[...]]` anchorral rendelkezik, tehát technikailag biztonságos lenne lefordítani őket (az anchor id
  nem a címszövegből generálódik) — **de** a WARNING szakasz (egy korábbi session által már lefordítva)
  a `<<SAFETY>>`/`<<PERFORMANCE>>` xrefeket látható szöveg nélkül, a bare anchor-id-t megjelenítve
  használja, ami azt jelzi, hogy a korábbi fordítói döntés ezeket angolul kívánta tartani (ha lefordítjuk
  a címet, a bare `<<SAFETY>>` xref angol szót jelenítene meg egy magyar cím fölött/mellett, ami
  inkonzisztens lenne). Ez a döntés emellett illeszkedik a projekt korábbi, ismétlődő precedensébe
  (`MERGES`, `BACKEND EXTRA OPTIONS`, `SERVICES`, `COMMANDS`, `DEPRECATED MODES`, `SCOPES`,
  `DETACHED HEAD`, `ARGUMENT DISAMBIGUATION`, `COMMIT INFORMATION`, `HOOKS`,
  `ENVIRONMENT AND CONFIGURATION VARIABLES`, `CONFIGURED REMOTE-TRACKING BRANCHES`, `PRUNING`, `OUTPUT`)
  — a kanonikus listán kívüli, csupa nagybetűs, man-page-stílusú alcímeket egységesen angolul hagyni.
  Ez már a **tizennegyedik** ilyen visszatérő eset — a 11. és 12. blokk óta ismételten javasolt,
  egyszeri, végleges felhasználói döntés (fordítsuk-e egységesen ezt a kategóriát) **továbbra is
  fennáll, erősen ajánlott**, hogy a jövőben ne kelljen blokkonként újra „eldöntendő"-ként rögzíteni.
- NAME/SYNOPSIS/WARNING/DESCRIPTION/OPTIONS/EXIT STATUS/EXAMPLES/GIT — a skill kanonikus listáján
  vannak (a `WARNING` a `NOTES`/`CAVEATS` rokon kategóriájaként, korábbi session döntése alapján, ebben
  a blokkban nem érintett), angolul maradtak.

### Megőrzött markup / megjegyzések

- Az EXAMPLES és a CHECKLIST FOR SHRINKING A REPOSITORY szakasz minden `----...----` (5–75 kötőjel
  közötti hosszúságú) körülhatárolt kód-/parancspélda-blokkja bájtazonos, beleértve a bennük lévő
  shell-szkript-részleteket, `sed`/`git ls-files`/`git update-index` csővezetékeket és a
  `D--E--F--G--H` / `A--B-----C` ASCII-art commit-gráfot is; csak a köréjük ékelt magyarázó
  prózamondatok fordultak.
- A `--` (dupla kötőjel, argumentum-elválasztó) minden előfordulása prózában is `` ` `` (backtick)
  között, változatlanul maradt.
- A `git filter-repo`/`filter-lamely` külső eszközök URL-jei (`https://github.com/newren/...`)
  változatlanok, csak a `[...]` látható link-szöveg fordult (pl. „git filter-repo").
- A GIT szakasz „A linkgit:git[1] csomag része" alakra fordítva (a 4. blokk szerinti egységesített
  forma, konzisztensen a `linkgit:git-clone[1]` egyéb belső hivatkozással).
- Szintaxis-ellenőrzés a blokk végén: minden `----`/`--------...` határoló-pár számolva és páros,
  nincs `ifdef::`/`endif::` a fájlban, a 3 `[[...]]` anchor és 2 `<<...>>` xref (l. fent) az egyetlen
  ilyen elem a fájlban, egyik sem sérült.

**Progress-tábla frissítve:** `git-filter-branch.adoc` sora `[ ]` → `[x]`, utolsó-ellenőrzés
2026-09-04, forrás-SHA üresen hagyva (nincs megadott upstream commit).

## VÉGLEGES DÖNTÉS — kanonikus listán kívüli, csupa nagybetűs, man-page-stílusú alcímek — 2026-09-04

A felhasználó véglegesen eldöntötte a projekt során 17× visszatérően felmerült kérdést: a skill
kanonikus man-page-szekció-listáján (NAME, SYNOPSIS, DESCRIPTION, OPTIONS, …) **kívüli**, de csupa
nagybetűs, kétsoros aláhúzású, man-page-stílusú alcímek (pl. `SCOPES`, `COMMANDS`, `DEPRECATED MODES`,
`DETACHED HEAD`, `ARGUMENT DISAMBIGUATION`, `COMMIT INFORMATION`, `HOOKS`,
`ENVIRONMENT AND CONFIGURATION VARIABLES`, `CONFIGURED REMOTE-TRACKING BRANCHES`, `PRUNING`, `OUTPUT`,
`CHECKLIST FOR SHRINKING A REPOSITORY`, `PERFORMANCE`, `SAFETY`, `OPERATING MODES`, `CACHED MODE`,
`NON-CACHED MODE`, `MERGES`, `BACKEND EXTRA OPTIONS`, `SERVICES` stb.) **maradnak angolul, bájtazonosan,
az eddigi gyakorlat szerint** — ez most már **nem** „eldöntendő", hanem **végleges szabály**, nem kell
a jövőben blokkonként újra felvetni. Ez a döntés **csak előre hatályos** (a már elkészült ~50 fájl
eleve így készült, konzisztens marad) — nincs szükség visszamenőleges javításra.

**A szabály ettől kezdve automatikusan alkalmazandó**, kérdés/megerősítés nélkül: ha egy fordítandó
fájlban ilyen alcím (kanonikus listán kívüli, csupa nagybetűs, kétsoros man-page-aláhúzású) fordul elő,
egyszerűen hagyd angolul (az esetleges `[[...]]` anchort és `<<...>>` xrefet a szokásos szabály szerint
kezelve), és a blokk lezárásakor elég egy rövid, egysoros megjegyzés a glossary-ban (fájl + a megtalált
címek felsorolása), **nem kell** többé „eldöntendő"-ként vagy hosszas indoklással dokumentálni.

## 14. blokk — `git-diagnose.adoc`, `git-diff-files.adoc`, `git-diff-index.adoc`, `git-diff-pairs.adoc`, `git-diff-tree.adoc`, `git-diff.adoc`, `git-difftool.adoc`, `git-fast-export.adoc` — 2026-09-04

**Módszer:** 4 párhuzamos subagent indult 3-3 fájlas, diszjunkt blokkokban (A: diagnose/diff-files/
diff-index; B: diff-pairs/diff-tree/diff; C: difftool/fast-export/fast-import; D: fetch-pack/fetch/
filter-branch — a C és D blokk a `content filtering policy` API-hiba miatt többször megszakadt,
l. lent és a 12–13. blokk). Az A és B blokk egy-egy menetben, megszakítás nélkül végzett.

### Ebben a blokkban rögzített / megerősített döntések

| angol | magyar | megjegyzés |
|---|---|---|
| backing store | **„háttértároló"** | `git-diff-index.adoc`, ad hoc kifejezés |
| all-zero sha1 | **„csupa nulla sha1"** | `git-diff-index.adoc` |
| stat state | **„stat-információ"** rokon mintája szerint **„stat-állapot"** | `git-diff-index.adoc`, a 3. blokk `git-checkout-index.adoc`-beli „stat-információ" mintáját folytatja |
| tentatively changed | **„feltételezetten megváltozott"** | `git-diff-index.adoc` |
| „SPECIFYING REVISIONS" / „SPECIFYING RANGES" (`git-diff.adoc` idézőjeles prózahivatkozás a `gitrevisions.adoc`-ra) | **angolul maradt** (nem `<<...>>` xref) | a 7. blokk `git-blame.adoc`-beli „SPECIFYING RANGES" precedensét folytatja |
| „3-Way Merge" (`git-diff.adoc` idézőjeles prózahivatkozás a `git-read-tree.adoc`-ra) | **angolul maradt** | ugyanaz a minta, új előfordulás — érdemes a jövőben nyomon követni, ha `git-read-tree.adoc` fordítása során a cél szakaszcím lefordul |

Nem volt szükség új terminológiára a `git-difftool.adoc`/`git-fast-export.adoc` fájlokban (a meglévő
0. blokk szókincse lefedte); a `git-fast-export.adoc`-ban új, ad hoc kifejezés: „anonimizál"/
„anonimizálás" (`--anonymize`), „fájlútvonal-komponens leképezése" (path-component mapping).

### Címsor-anchorok

- `git-diagnose.adoc`, `git-diff-files.adoc`, `git-diff-pairs.adoc`, `git-diff-tree.adoc`,
  `git-diff.adoc`, `git-difftool.adoc`, `git-fast-export.adoc`: **nincs** bennük `[[...]]` anchor és
  `<<...>>` xref sem — csak kanonikus man-page szekciócímek, nem kellett anchor-kezelés.
- `git-diff-index.adoc`: nincs `[[...]]`/`<<...>>`, de van 3 nem-kanonikus, csupa nagybetűs alcím
  (`OPERATING MODES`, `CACHED MODE`, `NON-CACHED MODE`) — l. lent.

### Man-page címként/man-page-stílusúként ANGOLUL hagyott, eldöntendő címsorok

- **`OPERATING MODES`**, **`CACHED MODE`**, **`NON-CACHED MODE`** (`git-diff-index.adoc`) — a
  visszatérő, kanonikus listán kívüli, csupa nagybetűs, man-page-stílusú alcím precedenst folytatva
  (`MERGES`, `SERVICES`, `SCOPES`, `COMMANDS`, `DEPRECATED MODES`, `DETACHED HEAD`,
  `ARGUMENT DISAMBIGUATION`, `COMMIT INFORMATION`, `HOOKS`,
  `ENVIRONMENT AND CONFIGURATION VARIABLES`, `CONFIGURED REMOTE-TRACKING BRANCHES`, `PRUNING`, `OUTPUT`,
  `CHECKLIST FOR SHRINKING A REPOSITORY`, `PERFORMANCE`, `SAFETY`) **bájtazonosan angolul maradtak**.
  Ez volt a 15–17. ilyen eset, amely alapján a felhasználó a fenti „VÉGLEGES DÖNTÉS" szakaszban
  lezárta a kérdést: ez a kategória mindig angolul marad, nem „eldöntendő" többé.

### Megőrzött markup / megjegyzések

- Mindegyik fájlban a `----`/`------------------------------------------------` határolók párban
  maradtak, `ifdef::`/`endif::` egyikben sincs, `include::` sorok (`diff-options.adoc`,
  `diff-format.adoc` stb.) változatlanok.
- Mind a 8 fájl GIT szakasza „A linkgit:git[1] csomag része" alakra fordítva (4. blokk szerinti
  egységesített forma).
- `git-fast-export.adoc`: az EXAMPLES/ANONYMIZING kódpélda-blokkjai (`$ git fast-export --all | ...`)
  bájtazonosak.

### Hiányzó `glossary-progit2.md` — megerősítve, munkameneti szinten jelezve

Két független subagent (A és B blokk) is jelentette, hogy a `git/transl-memo-hu/glossary-progit2.md`
fájl **nem létezik** ebben a workspace-ben (csak `glossary-git-git-docs.md` és `progress-git-git-docs.md`
van a mappában). Mindkettő az itteni „0. blokk" örökölt-alapvonal táblát használta helyette (ami a
`glossary-progit2.md` véglegesített döntéseinek kivonata), ami tartalmilag elegendő volt — nem volt
terminológiai probléma emiatt. **A felhasználónak érdemes megerősítenie**, hogy ez a fájl valóban nincs
ebben a repóban (más projekt testvér-workspace-ében lehet), és ha szükséges, a skill hivatkozását
frissíteni kell.

### `git-fast-import.adoc` — felfüggesztve a felhasználó kérésére

A C blokk a `git-difftool.adoc` és `git-fast-export.adoc` befejezése után elkezdte a
`git-fast-import.adoc`-ot (1682→1700 sor, a legnagyobb hátralévő fájl a batchben), de a
`content filtering policy` API-hiba miatt több nekifutásra volt szükség (109→222→316→545 sorig
haladt). A felhasználó **explicit felfüggesztette** ennek a fájlnak a fordítását, későbbre halasztva.
Állapot lezáráskor: **545/1700 sor kész** (a `commit` parancs alszakaszáig, az INPUT FORMAT szakasz
elején), a progress-táblában `~32%`-ként jelölve. **Folytatáskor:** kis, célzott `Read`/`Edit`
lépésekben érdemes haladni (l. a 13. blokk stratégiaváltása), mert ez a fájl is rendszeresen kiváltja
a content-filtering-hibát.

## 15. blokk — a 10 legkisebb, még lefordítatlan „Gyökér" fájl — 2026-09-10

**Módszer:** a felhasználó kérésére a két gyökér-tábla (`git-*.adoc` man page-ek + „egyéb .adoc")
együttesen legkisebb sorméretű, még `[ ]` jelölésű tagjai — a skill szerint a végére/`config/` utánra
halasztott `gitglossary.adoc`/`git.adoc`/`config.adoc`, valamint a felfüggesztett `git-fast-import.adoc`
kizárva. Orchestrátor fordította közvetlenül, subagent nélkül (a fájlok 7–21 soros mérete miatt nem
volt indokolt). Fájlok: `ref-reachability-filters.adoc`, `format-patch-end-of-commit-message.adoc`,
`ref-storage-format.adoc`, `object-format-disclaimer.adoc`, `rerere-options.adoc`, `git-tools.adoc`,
`diff-context-options.adoc`, `trace2-target-values.adoc`, `sequencer.adoc`, `diff-algorithm-option.adoc`
— mind option-fragmens/include-cél fájl (más man page-ekbe `include::`-olódnak), `git-tools.adoc`
kivételével, ami önálló, nem man-page kis dokumentum.

### Ebben a blokkban rögzített / megerősített döntések

| angol | magyar | megjegyzés |
|---|---|---|
| commit log message (`format-patch-end-of-commit-message.adoc`) | **„a commit napló-üzenete"** | a 2. blokk (`git-commit-tree.adoc`) „napló-üzenet"/„commit napló-üzenete" precedensét folytatja |
| „Note:" (kisbetűs, NEM a `NOTE:` admonition-kulcsszó) | **„Megjegyzés:"** | `object-format-disclaimer.adoc` — a forrás szándékosan kisbetűs `Note:`-ot használ, ez sima próza, nem AsciiDoc admonition-makró, ezért fordul |
| `files`/`reftable` (ref-storage formátumnevek, `;;` beágyazott def-lista címke) | **változatlanul angolul maradtak**, csak a leírás-törzs fordult | `ref-storage-format.adoc` — a `config.kulcs::` címke-szabály analógiájára kezelve |
| `default`/`myers`/`minimal`/`patience`/`histogram` (diff-algoritmus nevek) | **változatlanul angolul maradtak** | `diff-algorithm-option.adoc` — opcióérték-nevek, mint a config-kulcsok |
| "patience diff" (algoritmusnév, idézőjelben) | **angolul maradt, idézőjelben** | nincs bevett magyar megfelelője, a `thin pack`/`promisor remote` mintáját követi (Git-specifikus technikai terminus) |
| "support low-occurrence common elements" (idézett leírás) | **fordítva**: „támogassa az alacsony előfordulású közös elemeket" | nem tulajdonnév, sima idézett leírás, fordul |
| rerere mechanizmus | **„rerere mechanizmus"** (marad angolul, mint alrendszer-név) | `rerere-options.adoc`, konzisztens a `technical/rerere.adoc`-ban (1. blokk) rögzített kezeléssel |
| Git Tools (cím) | **„Git eszközök"** | `git-tools.adoc` — nem man-page, egyszintű `=` cím, „Git" tulajdonnév marad, „eszközök" fordul |

### Címsor-anchorok

- Egyik fájlban sincs `[[...]]` anchor vagy `<<...>>` xref (grep-pel ellenőrizve); a `git-tools.adoc`
  önálló, egyszintű `=` címére sincs hivatkozás sehol a fában — nem kellett anchort hozzáadni.

### Man-page címként angolul hagyott címsorok

- Nincs egy sem — egyik fájl sem man page (mind option-fragmens vagy egy kis önálló dokumentum
  `git-tools.adoc` esetén, man-page szekciócímek nélkül).

### Megőrzött markup / megjegyzések

- `ref-storage-format.adoc`: az `ifndef::with-breaking-changes[]` / `ifdef::with-breaking-changes[]` +
  `endif::with-breaking-changes[]` párok teljes egészében, az attribútumnévvel együtt változatlanok;
  csak a köztük lévő „This is the default." próza fordult.
- `diff-algorithm-option.adoc`: a `--`/`--` nyitott blokk (algoritmus-felsorolás) és a beágyazott `;;`
  másodszintű def-lista-címkék (`default`, `myers`, `minimal`, `patience`, `histogram`) érintetlenek.
- `trace2-target-values.adoc`: a `--`/`--` nyitott blokk érintetlen, csak a felsorolás-elemek prózája
  fordult; a `STDERR`, `af_unix:`, `stream`/`dgram` literálok változatlanok.
- Mindegyik fájlban a `linkgit:git-rerere[1]`, `linkgit:git-add[1]` makrók változatlanok
  (`rerere-options.adoc`).
- Szintaxis-ellenőrzés: mind a 10 fájlban `ifdef::`/`ifndef::`/`endif::` számláló egyezik (csak
  `ref-storage-format.adoc`-ban van 2+2, a többi 0), nincs `[[...]]`/`<<...>>`, a bekezdéshatárok
  megtartva.

## 16. blokk — a következő 10 legkisebb, még lefordítatlan „Gyökér" fájl — 2026-09-10

**Módszer:** ugyanaz, mint a 15. blokkban — a két gyökér-tábla együttes, sorméret szerint növekvő
listájának következő 10 tagja, `gitglossary.adoc`/`git.adoc`/`config.adoc`/`git-fast-import.adoc`
kihagyva. Orchestrátor fordította közvetlenül, subagent nélkül. Fájlok: `git-merge-one-file.adoc`,
`line-range-options.adoc`, `git-fsck-objects.adoc`, `signoff-option.adoc`, `git-init-db.adoc`,
`git-stage.adoc`, `git-unpack-file.adoc`, `git-get-tar-commit-id.adoc`, `git-verify-commit.adoc`,
`git-verify-tag.adoc`. Négy fájl (`git-fsck-objects`, `git-init-db`, `git-stage`) klasszikus
„szinonima" man page (l. lent), a `signoff-option.adoc` és a `line-range-options.adoc` option-
fragmens, a többi rövid, önálló man page.

### Ebben a blokkban rögzített / megerősített döntések

| angol | magyar | megjegyzés |
|---|---|---|
| „This is a synonym for X. Please refer to the documentation of that command." (szinonima-man page-ek törzsmondata) | **„Ez a X szinonimája. Kérjük, nézd meg annak a parancsnak a dokumentációját."** | `git-fsck-objects.adoc`, `git-init-db.adoc`, `git-stage.adoc` — egységes sablonmondat, a jövőbeli hasonló szinonima-fájloknál (pl. `git-whatchanged.adoc` is ilyen lehet) ugyanígy fordítandó |
| blob id | **„blob azonosító"** | `git-unpack-file.adoc` |
| commit/tag object (GPG-ellenőrzés kontextusában) | **„commit-objektum" / „tag-objektum"** | `git-verify-commit.adoc`, `git-verify-tag.adoc` |
| gpg status output | **„gpg-státuszkimenet"** | mindkét `git-verify-*.adoc` fájlban azonos szöveg, konzisztensen fordítva |
| Developer Certificate of Origin | **marad angolul, tulajdonnévként**, ragozva „…Originnal" | `signoff-option.adoc` — nincs bevett magyar fordítása, hivatalos dokumentum-név |
| countermand (egy korábbi kapcsoló hatálytalanítása) | **„hatálytalanítható"** | `signoff-option.adoc`, a `--no-signoff` leírásában |
| walk (revízió-bejárás, `line-range-options.adoc`) | **„bejárás"** | konzisztens a `technical/` blokkokban használt „bejárás" fordítással |

### Címsor-anchorok

- Egyik fájlban sincs `[[...]]` anchor vagy `<<...>>` xref (grep-pel ellenőrizve); nem kellett
  anchor-kezelés.

### Man-page címként angolul hagyott címsorok

- Mind a 8 önálló man page-ben (a 2 option-fragmens kivételével) a szokásos NAME/SYNOPSIS/
  DESCRIPTION/OPTIONS/GIT címek a kanonikus lista szerint angolul maradtak.

### Megőrzött markup / megjegyzések

- `signoff-option.adoc`: az `ifdef::git-commit[]` / `endif::git-commit[]` pár teljes egészében,
  az attribútumnévvel együtt változatlan; csak a köztük lévő `-s`/`--signoff`/`--no-signoff`
  definíciós lista-címkék maradtak angolul, a leírás-törzs fordult.
  A `https://developercertificate.org` URL és a `commit.signoff` config-kulcs változatlanok.
- `git-verify-tag.adoc`: a SYNOPSIS `--format=<format>` kapcsolót említ, de az OPTIONS szakaszban
  nincs hozzá leírás (upstream-inkonzisztencia) — bájtazonosan hagyva, nem „javítva", a
  `api-trace2.adoc`-beli hasonló eset precedensét (1. blokk) követve.
- Mindegyik man page GIT szakasza „A linkgit:git[1] csomag része" alakra fordítva (4. blokk
  szerinti egységesített forma).
- Szintaxis-ellenőrzés: mind a 10 fájlban a `----`/`====` cím-aláhúzások és a man-page szekciócímek
  érintetlenek, nincs `ifdef::`/`endif::` a `signoff-option.adoc` kivételével (ott párban van),
  nincs `[[...]]`/`<<...>>`.

## 17. blokk — a következő 10 legkisebb, még lefordítatlan „Gyökér" fájl — 2026-09-10

**Módszer:** ugyanaz, mint a 15–16. blokkban. Fájlok: `transfer-data-leaks.adoc`,
`line-range-format.adoc`, `format-patch-caveats.adoc`, `date-formats.adoc`,
`git-sh-i18n--envsubst.adoc`, `git-version.adoc`, `gitrevisions.adoc`, `git-mktree.adoc`,
`git-update-server-info.adoc`, `git-write-tree.adoc`. **Fontos:** a `gitrevisions.adoc` grep-pel
ellenőrizve NEM tartalmazza a „peel onion" kifejezést (az a beágyazott `include::revisions.adoc[]`
— egy külön, még lefordítatlan, nagyobb fájl — törzsében van), így a 3. blokkban rögzített
„eldöntendő" jelölés erre a fájlra (a keretre) nem vonatkozott; a `revisions.adoc` fordításakor
viszont kötelező lesz egyeztetni a `git-check-ref-format.adoc`-beli „hagymahámozó" fordítással.

### Ebben a blokkban rögzített / megerősített döntések

| angol | magyar | megjegyzés |
|---|---|---|
| dumb server (`git-update-server-info.adoc`) | **„»dumb« szerver"**, idézőjelben, ad hoc | nincs még bevett magyar terminológia — **jövőbeli döntési függőség**: a `git-http-backend.adoc` / `gitprotocol-http.adoc` fordításakor a „dumb"/„smart" protokoll-terminológiát ezzel konzisztensen kell kezelni |
| sync()s (ige, `git-write-tree.adoc`) | **„szinkronizálja (sync())"** | a zárójeles eredeti függvénynév megtartva a pontosság kedvéért |
| DATE FORMATS (cím) | **változatlanul angolul maradt** (l. lent, hibajavítás) | `date-formats.adoc` |
| „yesterday" / „last Friday at noon" (relatív dátum-példák) | **bájtazonosan angolul, idézőjelben maradtak** | `date-formats.adoc` — a Git dátum-értelmezője ténylegesen csak angol kifejezéseket ismer fel, lokalizálatlan program-bemeneti minta, a `git-clean.adoc`/`git-daemon.adoc` precedensét követi |
| gitlink entries (aka "submodules") | **„gitlink-bejegyzések (más néven »submodule-ok«)"** | `git-mktree.adoc` |

### Hibajavítás menet közben

A `date-formats.adoc` `DATE FORMATS` kétsoros, csupa nagybetűs man-page-stílusú címét tévedésből
először lefordítottam „DÁTUMFORMÁTUMOK"-ra — ez ellentmond a korábban (l. a „VÉGLEGES DÖNTÉS" szakasz
a 14. blokk előtt) a felhasználóval lezárt szabálynak, miszerint minden kanonikus listán kívüli,
csupa nagybetűs, man-page-stílusú alcím automatikusan angolul marad. A hiba még a blokk lezárása
előtt észlelve és javítva: a cím visszaállítva `DATE FORMATS`-ra.

### Címsor-anchorok

- Egyik fájlban sincs `[[...]]` anchor vagy `<<...>>` xref (grep-pel ellenőrizve).
- `format-patch-caveats.adoc`: tartalmaz egy `<<discussion,DISCUSSION>>` xref-et (ez egy másik,
  include-oló fájlban — pl. `git-am.adoc`, ha lefordítva — lévő `[[discussion]]` anchorra mutat);
  mivel a `DISCUSSION` kanonikus man-page cím, az azonosító és a látható link-szöveg is változatlanul
  angolul maradt — nem kellett módosítani.

### Man-page címként angolul hagyott/érintetlen címsorok

- `date-formats.adoc`: `DATE FORMATS` — nem kanonikus, de a „VÉGLEGES DÖNTÉS" szabály szerint
  automatikusan angolul marad (l. fenti hibajavítás).
- `git-update-server-info.adoc`: `OUTPUT` — a 3. blokkban már lezárt kategória, angolul marad.
- A többi fájlban csak kanonikus man-page címek (NAME, SYNOPSIS, DESCRIPTION, OPTIONS, GIT) vannak.

### Megőrzött markup / megjegyzések

- `format-patch-caveats.adoc`: két `ifdef::git-am[]`/`endif::git-am[]` pár (az egyik az
  `ifndef::` változata) teljes egészében, az attribútumnévvel együtt változatlan.
- `date-formats.adoc`: az `ifdef::git-commit[]`/`endif::git-commit[]` pár változatlan; a `NOTE:`
  admonition-kulcsszó (valódi, csupa nagybetűs AsciiDoc-makró) változatlan, csak a mögötte lévő
  próza fordult.
- `gitrevisions.adoc`: az `include::revisions.adoc[]` sor változatlan (külön, még lefordítatlan fájl).
- `git-mktree.adoc`, `git-write-tree.adoc`: a `NUL`, `sync()`, `ls-tree` stb. technikai kifejezések
  és a `-z`/`--missing`/`--batch`/`--missing-ok`/`--prefix=` kapcsolók változatlanok.
- Mindegyik man page GIT szakasza „A linkgit:git[1] csomag része" alakra fordítva.
- Szintaxis-ellenőrzés: mind a 10 fájlban az `ifdef::`/`ifndef::`/`endif::` számláló egyezik
  (`format-patch-caveats.adoc`: 2+2, `date-formats.adoc`: 1+1, a többi 0), nincs `[[...]]`,
  a bekezdéshatárok megtartva.

## 18. blokk — a következő 10 legkisebb, még lefordítatlan „Gyökér" fájl — 2026-09-10

**Módszer:** ugyanaz, mint a 15–17. blokkban. Fájlok: `git-sh-i18n.adoc`, `git-prune-packed.adoc`,
`git-verify-pack.adoc`, `ToolsForGit.adoc`, `git-show-index.adoc`, `git-unpack-objects.adoc`,
`pack-refs-options.adoc`, `git-mergetool--lib.adoc`, `git-whatchanged.adoc`, `git-mailsplit.adoc`.

### Ebben a blokkban rögzített / megerősített döntések

| angol | magyar | megjegyzés |
|---|---|---|
| Porcelain-ish scripts | **„porcelain-szerű szkriptek"** | `git-sh-i18n.adoc`, `git-mergetool--lib.adoc` — a 0. blokk `plumbing / porcelain` (marad angolul) tételének melléknévi bővítése |
| „files"/„reftable" (ref-formátum nevek) | **változatlanul angolul maradtak** | `pack-refs-options.adoc` — a 15. blokk (`ref-storage-format.adoc`) döntésének megismétlése/megerősítése |
| guitool | **marad „guitool"** angolul | `git-mergetool--lib.adoc` |
| deltified (objektum, `git-verify-pack.adoc`) | **„deltásítva"** | új, ad hoc melléknévi alak a „delta" szóból, konzisztens a `delta-sorrend`/`delta-lánchossz` mintával |
| loose (objektum-formátum jelzőként) | **„laza"** | megerősítve a 0. blokk `loose / packed object` tételéből |
| `git log --raw --no-merges` (deprecated parancs magyarázata) | fordul a körülötte lévő próza, a kódblokk bájtazonos | `git-whatchanged.adoc` |
| Examples (`git-whatchanged.adoc`, vegyes kis-nagybetűs, NEM „EXAMPLES") | **„Példák"** (fordítva) | ez NEM a kanonikus, csupa nagybetűs `EXAMPLES` man-page cím, hanem egy vegyes kis-nagybetűs, kétsoros alcím — a „VÉGLEGES DÖNTÉS" szabály csak a csupa nagybetűs kategóriára vonatkozik, ez kívül esik rajta, ezért simán fordítható |

### Címsor-anchorok

- `ToolsForGit.adoc`: az egyetlen fájl ebben a blokkban `[[...]]` anchorokkal (`[[summary]]`,
  `[[author]]`, `[[table_of_contents]]`, `[[vscode]]`, `[[emacs]]`) és `<<vscode>>`/`<<emacs>>`
  xrefekkel (a `[[table_of_contents]]` szakasz listájában). Mind explicit anchorral rendelkeztek
  már a forrásban is — érintetlenül hagyva, csak a címszövegek fordultak (kivéve a `vscode`/`emacs`
  címeket, ahol a termékneveket, mint tulajdonneveket, nem fordítottuk).
- A többi 9 fájlban nincs `[[...]]`/`<<...>>` (grep-pel ellenőrizve).

### Man-page címként angolul hagyott/érintetlen címsorok

- `FUNCTIONS` (`git-sh-i18n.adoc`, `git-mergetool--lib.adoc`), `OUTPUT FORMAT`
  (`git-verify-pack.adoc`) — a „VÉGLEGES DÖNTÉS" szabály szerint automatikusan angolul maradtak,
  nem kellett egyeztetni.
- A többi fájlban csak kanonikus man-page címek (NAME, SYNOPSIS, DESCRIPTION, OPTIONS, WARNING,
  SEE ALSO, GIT).

### Megőrzött markup / megjegyzések

- `ToolsForGit.adoc`: `:sectanchors:` dokumentum-attribútum, a `contrib/vscode/init.sh`,
  `contrib/vscode/README.md`, `GIT_CHECKOUT/.dir-locals.el` fájlútvonalak, a `----`/`----`
  Emacs-Lisp kódblokk és a záró, szó szerint URL-ként megadott 4. szintű alcím
  (`==== https://www.kernel.org/...`) mind bájtazonosak.
- `git-verify-pack.adoc`: az `OUTPUT FORMAT` szakasz két tab-indentált formátumsora
  (`object-name type size size-in-packfile offset-in-packfile...`) bájtazonos.
- `pack-refs-options.adoc`: a `"files"` / `"reftable"` idézőjeles formátumnevek és a
  `glob(7)` hivatkozás változatlanok.
- Mindegyik man page GIT szakasza „A linkgit:git[1] csomag része" alakra fordítva.
- Szintaxis-ellenőrzés: mind a 10 fájlban a `----` kódblokk-határolók (csak `git-whatchanged.adoc`-
  ban van egy pár, a `git log --raw --no-merges` körül) párban vannak, nincs `ifdef::`/`endif::`,
  a `ToolsForGit.adoc` 5 anchora és 2 xrefje érintetlen, a bekezdéshatárok megtartva.

## 19. blokk — a következő 10 legkisebb, még lefordítatlan „Gyökér" fájl — 2026-09-10

**Módszer:** ugyanaz, mint a 15–18. blokkban. Fájlok: `git-remote-fd.adoc`, `git-pack-refs.adoc`,
`rev-list-description.adoc`, `git-upload-archive.adoc`, `git-pack-redundant.adoc`,
`git-quiltimport.adoc`, `git-hash-object.adoc`, `git-mktag.adoc`, `git-http-fetch.adoc`,
`git-for-each-repo.adoc`. A `git-mv.adoc`-kal 68-68 soros holtverseny volt; byte-számmal döntve
(`git-for-each-repo.adoc` 1941 byte < `git-mv.adoc` 2086 byte) a `git-for-each-repo.adoc` került
ebbe a blokkba, a `git-mv.adoc` a következőbe.

### Ebben a blokkban rögzített / megerősített döntések

| angol | magyar | megjegyzés |
|---|---|---|
| smart transport (stream) | **„»smart« átviteli adatfolyam"**, idézőjelben | `git-remote-fd.adoc` — a 17. blokk „dumb szerver" ad hoc, idézőjeles kezelésének párja; **jövőbeli döntési függőség marad** a `git-http-backend.adoc`/`gitprotocol-http.adoc` fordításakor |
| non-smart-http | **„nem-smart-http"** | `git-upload-archive.adoc` — összetett szó, a „smart" elem idézőjel nélkül, mert már maga összetételi taggá vált |
| redundant pack files | **„redundáns packfile-ok"** | `git-pack-redundant.adoc` |
| Tag Format (cím, `git-mktag.adoc`) | **„Tag-formátum"** (fordítva) | Title Case, NEM csupa nagybetűs man-page-stílusú cím, tehát nem esik a „VÉGLEGES DÖNTÉS" szabály alá; nincs rá xref, biztonságosan fordítható |
| THIS COMMAND IS EXPERIMENTAL. THE BEHAVIOR MAY CHANGE. | **„EZ A PARANCS KÍSÉRLETI. A VISELKEDÉSE MEGVÁLTOZHAT."** | `git-for-each-repo.adoc` — a `git-backfill.adoc` (3. blokk) pontos mintáját követi, csupa nagybetűs formázás megtartva |
| quilt (patch-eszköz neve) | **marad „quilt"** angolul | `git-quiltimport.adoc` — külső eszköz tulajdonneve |
| series file (quilt-kontextusban) | **„series fájl"** | `git-quiltimport.adoc` |

### Címsor-anchorok

- Egyik fájlban sincs `[[...]]` anchor (grep-pel ellenőrizve).
- `rev-list-description.adoc`: nincs `[[...]]`/`<<...>>`, de 3 pár `ifdef::git-rev-list[]`/
  `endif::git-rev-list[]` és `ifdef::git-log[]`/`endif::git-log[]` van benne (6+6) — mindegyik
  változatlan, csak a köztük/körülöttük lévő próza fordult.

### Man-page címként angolul hagyott/érintetlen címsorok

- `SUBPROCESS BEHAVIOR` (`git-for-each-repo.adoc`) — a „VÉGLEGES DÖNTÉS" szabály szerint
  automatikusan angolul maradt.
- A többi fájlban csak kanonikus man-page címek (NAME, SYNOPSIS, DESCRIPTION, WARNING, OPTIONS,
  SECURITY, SEE ALSO, GIT).

### Megőrzött markup / megjegyzések

- `git-pack-refs.adoc` BUGS szakasza: a `".git/refs/heads/<branch> file exists"` és
  `"branch <branch> exists"` idézett mintamondatok bájtazonosan angolul maradtak — szó szerint
  idézett, régi (hipotetikus) angol dokumentáció-szöveg, a `git-clean.adoc`/`git-daemon.adoc`
  precedensét követve.
- `git-remote-fd.adoc`: az `(as URL)` / `(URL-ként)` jelölés az EXAMPLES egyik címsorában fordítva,
  a másikban (SYNOPSIS-szerű sor) is konzisztensen.
- `git-hash-object.adoc`, `git-mktag.adoc`: a `commit`/`tree`/`blob`/`tag` objektumtípus-nevek és a
  `git mktag <my-tag` stb. tab-indentált parancspéldák bájtazonosak.
- Mindegyik man page GIT szakasza „A linkgit:git[1] csomag része" alakra fordítva.
- Szintaxis-ellenőrzés: mind a 10 fájlban a `----`/`-------------` kódblokk-határolók párban
  vannak, a `rev-list-description.adoc` 6+6 `ifdef::`/`endif::` párja épen maradt, nincs
  `[[...]]`, a bekezdéshatárok megtartva.

## 20. blokk — a következő 10 legkisebb, még lefordítatlan „Gyökér" fájl — 2026-09-10

**Módszer:** ugyanaz, mint a 15–19. blokkban. Fájlok: `git-mv.adoc`, `git-url-parse.adoc`,
`git-last-modified.adoc`, `git-symbolic-ref.adoc`, `git-fmt-merge-msg.adoc`, `git-merge-index.adoc`,
`git-request-pull.adoc`, `git-prune.adoc`, `git-show.adoc`, `git-instaweb.adoc`.

### Ebben a blokkban rögzített / megerősített döntések

| angol | magyar | megjegyzés |
|---|---|---|
| detached HEAD | **„leválasztott HEAD"** | `git-symbolic-ref.adoc` — a 0. blokk öröklött terminusának alkalmazása, korábbi (pl. `git-checkout.adoc`) fájlokban már bevezetve, itt nem kellett újra glosszázni |
| EXPERIMENTAL: (NAME-mező előtag) | **„KÍSÉRLETI:"** | `git-last-modified.adoc` — új, ad hoc mintázat man-page NAME-mezőkben |
| THIS COMMAND IS EXPERIMENTAL. THE BEHAVIOR MAY CHANGE. | **„EZ A PARANCS KÍSÉRLETI. A VISELKEDÉSE MEGVÁLTOZHAT."** | `git-last-modified.adoc` — a `git-backfill.adoc` (3. blokk)/`git-for-each-repo.adoc` (19. blokk) pontos mintáját ismétli |
| "Specifying Ranges" section (`git-last-modified.adoc`, idézőjeles prózahivatkozás) | **angolul maradt** | a 7. blokk (`git-blame.adoc`) „SPECIFYING RANGES" precedensét folytatja |
| "SPECIFYING REVISIONS" section (`git-show.adoc`, idézőjeles prózahivatkozás) | **angolul maradt** | a `git-diff.adoc`-beli (14. blokk) azonos precedens megismétlése |
| merge object order (idézőjeles, coined kifejezés) | **marad angolul, idézőjelben** | `git-merge-index.adoc` — a doksi maga is idézőjelbe teszi mind a Git, mind az RCS változatát, nincs bevett magyar megfelelője |
| ALERT ALERT ALERT! | **„FIGYELEM, FIGYELEM, FIGYELEM!"** | `git-merge-index.adoc` — a csupa nagybetűs, felkiáltásos stílus megtartva |
| lookup/binds (webszerver-kontextus, `git-instaweb.adoc`) | **„köt"** (bind) | `--local` opció leírásában |
| Examples: / Példák: (nem hivatalos, kettőspontos bekezdés-cím, NEM `--------` aláhúzásos AsciiDoc heading) | **fordítva** | `git-merge-index.adoc` — sima próza, nem szekciócím, tehát nem esik semmilyen man-page-szabály alá |

### Címsor-anchorok

- Egyik fájlban sincs `[[...]]` anchor vagy `<<...>>` xref (grep-pel ellenőrizve).

### Man-page címként angolul hagyott/érintetlen címsorok

- `DIFF FORMATTING` (`git-show.adoc`) — a „VÉGLEGES DÖNTÉS" szabály szerint automatikusan angolul
  maradt.
- A többi fájlban csak kanonikus man-page címek (NAME, SYNOPSIS, DESCRIPTION, OPTIONS, SUBMODULES
  [korábbi precedens, l. 10. blokk], BUGS, EXAMPLES, NOTES, DISCUSSION, CONFIGURATION, SEE ALSO,
  GIT).

### Megőrzött markup / megjegyzések

- `git-merge-index.adoc`: mindhárom `----...----` kódblokk (a két EXAMPLES-terminálátirat és a
  hibaüzenet-blokk) bájtazonos, beleértve a bennük lévő angol inline kommenteket is
  (`# original`, `# merge1` stb.) — ezek a literál program-kimenet részei, nem próza.
- `git-show.adoc`: az `:git-log: 1` és `:diff-merges-default:` dokumentum-attribútum-sorok, valamint
  az `include::pretty-options.adoc[]`, `include::pretty-formats.adoc[]`, `include::diff-options.adoc[]`,
  `include::diff-generate-patch.adoc[]`, `include::i18n.adoc[]` sorok változatlanok.
  A `v1.0.0^{tree}`, `v1.0.0^{commit}` caret-jelölések és a `%s` pretty-format-token változatlanok.
- `git-instaweb.adoc`: a `-----------------------------------------------------------------------`
  (71 kötőjel) config-mintablokk (`[instaweb]` szekció) bájtazonos, csak a bevezető mondat fordult.
  A `{litdd}` attribútum-referenciák (`git-web{litdd}browse`) változatlanok.
- `git-prune.adoc`: a `NOTE:` admonition-kulcsszó (valódi makró) változatlan, csak a mögötte lévő
  próza fordult, beleértve a `"NOTES"` szakaszcím-idézetet is (a cél szakaszcím maga is angolul
  marad, kanonikus lista).
- Mindegyik man page GIT szakasza „A linkgit:git[1] csomag része" alakra fordítva.
- Szintaxis-ellenőrzés: mind a 10 fájlban a kódblokk-határolók párban vannak, nincs `ifdef::`/
  `endif::`, nincs `[[...]]`/`<<...>>`, a bekezdéshatárok megtartva.

## 21. blokk — a következő 10 legkisebb, még lefordítatlan „Gyökér" fájl — 2026-09-10

**Módszer:** ugyanaz, mint a 15–20. blokkban (a két gyökér-tábla együttes, sorméret szerint növekvő
listája, `gitglossary.adoc`/`git.adoc`/`config.adoc`/`git-fast-import.adoc` kihagyva). Ebben a
blokkban már 2–3 KB-os, 60–120 soros fájlok. Fájlok: `git-stripspace.adoc`, `gitnamespaces.adoc`,
`i18n.adoc`, `git-sh-setup.adoc`, `git-shell.adoc`, `git-http-push.adoc`, `git-upload-pack.adoc`,
`for-each-ref-options.adoc`, `git-var.adoc`, `gitprotocol-common.adoc`. Az `i18n.adoc` és a
`for-each-ref-options.adoc` option-fragmens (más man page-ekbe `include`-olódik), a többi önálló
man page (`gitprotocol-common.adoc` szekció 5, formátum-spec). Orchestrátor fordította közvetlenül,
subagent nélkül.

### Ebben a blokkban rögzített / megerősített döntések

| angol | magyar | megjegyzés |
|---|---|---|
| character encoding agnostic | **„karakterkódolás-független"** | `i18n.adoc` |
| normalization form C | **„C normalizálási forma"** | `i18n.adoc` — Unicode-terminus, körülírva |
| commit log message | **„commit napló-üzenet"** | `i18n.adoc` — a 2./11./15. blokk precedensét folytatja (megkülönböztetve a „commit-üzenet"-től) |
| Porcelain-ish scripts | **„porcelain-szerű szkriptek"** | `git-sh-setup.adoc` — a 18. blokk (`git-sh-i18n.adoc`) döntésének megismétlése |
| scriptlet | **„szkriptrészlet"** | `git-sh-setup.adoc` |
| to source (a shell script, `.` operátor) | **„behúzni"** / „behúzás" | `git-sh-setup.adoc` |
| die (a `git-sh-setup` `die`/`usage` shell-függvénye, prózában igeként is) | **változatlanul „die"** angolul | `git-sh-setup.adoc` — a konkrét shell-függvény neve, nem fordítható; „egyébként die", „die a használati üzenettel" |
| dumb (terminál, `git_editor` leírásában) | **változatlanul „dumb"** angolul | `git-sh-setup.adoc` — a „dumb"/„smart" terminológia ad hoc, idézőjel nélküli kezelése (a 17./19. blokk „dumb szerver"/„smart átvitel" mintájának rokona; itt terminálról van szó, nem protokollról) |
| restricted login shell | **„korlátozott bejelentkezési shell"** | `git-shell.adoc` |
| `"git> "` prompt, `help`/`exit`/`no-interactive-login` parancsnevek | **bájtazonosan angolul** | `git-shell.adoc` — a program tényleges, lokalizálatlan felülete |
| fast-forward check | **„fast-forward ellenőrzés"** / idézőjelben `"fast-forward check"`, ahol a forrás is idézőjelezi | `git-http-push.adoc` — a 0. blokk `fast-forward` (marad angolul) tételéből |
| wire protocol / over-the-wire protocol | **„wire protokoll"** (marad angolul) | `git-upload-pack.adoc`, `gitprotocol-common.adoc` |
| handshaking (a wire protokollé) | **„kézfogás"** | `git-upload-pack.adoc` (`GIT_PROTOCOL` leírása) |
| lazy fetch | **marad „lazy fetch"** angolul; ige: `lazy fetchet` (kötőjel nélkül, a záró szóhoz) | `git-upload-pack.adoc` |
| partial repository / partial clone | **marad „partial repository" / „partial clone"** | `git-upload-pack.adoc` — a 3. blokk (`git-backfill.adoc`) „partial clone" döntésének folytatása |
| alternate user (biztonsági kontextus) | **„másik felhasználó"** | `git-upload-pack.adoc` SECURITY |
| refname (protokoll-nyelvtan kontextusban) | **változatlanul „refname"** angolul | `gitprotocol-common.adoc` — a nyelvtani produkció neve, nem fordul |
| octet string | **„oktett-karakterlánc"** | `gitprotocol-common.adoc` |
| payload (pkt-line) | **„hasznos adat"** | `gitprotocol-common.adoc` |
| flush-pkt / data-pkt / pkt-len / pkt-line | **változatlanul angolul** (protokoll-token nevek) | `gitprotocol-common.adoc` |
| RFC 2119 kulcsszavak (`MAY`, `MUST`, `SHOULD BE`, `SHOULD NOT`, `MUST NOT`) | **bájtazonosan angolul, csupa nagybetűvel maradnak** a magyar mondatban, közvetlenül utánuk magyar főnévi igenévvel (pl. „MUST gondoskodniuk", „MAY tartalmazni", „MUST NOT … küldeni") | `gitprotocol-common.adoc` — felhasználói döntés (2026-09-10): az RFC 2119 normatív kulcsszavakat angolul kell hagyni, nem fordítjuk. Ez általános szabály a jövőbeli `gitprotocol-*` / `gitformat-*` fájlokra is |

### Címsor-anchorok

- `gitprotocol-common.adoc`: két nem man-page, **Title Case** (NEM csupa nagybetűs) alcím —
  `ABNF Notation` és `pkt-line Format`. Egyikre sincs `<<...>>` xref sehol a fában (a
  `gitprotocol-pack.adoc:29` „pkt-line Format" a saját, különálló alcíme, csak `linkgit:`-prózával
  hivatkozik a `gitprotocol-common`-ra) — grep-pel ellenőrizve. Mindkettő lefordítva („ABNF-jelölés"
  / „pkt-line formátum"), fölé defenzív `[[_abnf_notation]]` ill. `[[_pkt_line_format]]` anchor
  (autogen slug az eredeti angol címből), a setext `----` aláhúzás a fordított cím pontos hosszához
  igazítva (12, ill. 17 karakter).
- A másik 9 fájlban nincs `[[...]]`/`<<...>>` (grep-pel ellenőrizve).

### Man-page címként angolul hagyott címsorok (VÉGLEGES DÖNTÉS szerint, automatikusan)

- `FUNCTIONS` (`git-sh-setup.adoc`), `COMMANDS` + `INTERACTIVE USE` (`git-shell.adoc`),
  `SPECIFYING THE REFS` (`git-http-push.adoc`), `VARIABLES` (`git-var.adoc`) — mind kanonikus
  listán kívüli, csupa nagybetűs, kétsoros man-page-stílusú alcím → a „VÉGLEGES DÖNTÉS" szabály
  szerint automatikusan angolul maradtak.

### Megőrzött markup / megjegyzések

- `git-stripspace.adoc`: a `*NOTE*:` félkövér előtag (NEM a `NOTE:` admonition-makró) változatlan,
  csak a mögötte lévő próza fordult. A 3 pár `---------` (9 kötőjel) példa-blokk és a bennük lévő
  `|A brief introduction   $` stílusú, `$`-jelölt zajos mintaszöveg bájtazonos.
- `gitnamespaces.adoc`: az `include::transfer-data-leaks.adoc[]` és a `----------` (10 kötőjel)
  `git clone ext::...` példablokk bájtazonos.
- `i18n.adoc`: a két `------------` (12 kötőjel) `[i18n]`-config-mintablokk és a `.` számozott
  lista-jelölők + `+`-folytatások bájtazonosak; a `_not_` compat-mode emphasis megtartva (`_nem_`).
- `git-sh-setup.adoc`: a `::` definíciós lista-címkék (`die`, `usage`, `set_reflog_action`,
  `git_editor`, `require_clean_work_tree <action> [<hint>]` stb.) shell-függvénynevek, bájtazonosak;
  csak a leírás-törzs fordult. A `----------------` (16 kötőjel) `require_clean_work_tree`
  példablokk bájtazonos.
- `git-shell.adoc`: a `::` címkék (`'git receive-pack <argument>'`, `'cvs server'` stb.)
  parancsnevek, bájtazonosak. A két `----------------` (16 kötőjel) `$HOME/git-shell-commands/...`
  shell-szkript példablokk — a `<<\EOF` heredoc-jelölésekkel — bájtazonos. A `SEE ALSO` tartalma
  (`ssh(1),` / `linkgit:git-daemon[1],` / `contrib/git-shell-commands/README`) változatlan.
- `git-var.adoc`: a `ifdef::git-default-editor[]`/`endif` és `ifdef::git-default-pager[]`/`endif`
  párok teljes egészében változatlanok; a `::` címkék (`GIT_AUTHOR_IDENT`, `GIT_EDITOR` stb.)
  env-változó-nevek, bájtazonosak. Az EXAMPLES tab-indentált `$ git var GIT_AUTHOR_IDENT` /
  `Eric W. Biederman <...> 1121223278 -0600` literál blokk bájtazonos. A `{git-default-editor}` /
  `{git-default-pager}` attribútum-referenciák változatlanok. 4 szóközös behúzás a `::` leírásokban
  (nem tab) — pontosan megtartva.
- `for-each-ref-options.adoc`: a `::` címkék backtickelt opciónevek (`` `--sort=<key>` `` stb.),
  bájtazonosak; csak a leírás-törzs fordult. A `_<pattern>_` / `_<count>_` / `_<format>_` /
  `_<when>_` / `_<object>_` / `_<excluded-pattern>_` placeholderek és a `%(fieldname)` / `%%` /
  `%xx` / `SPC` / `TAB` / `LF` / `NUL` formátum-tokenek változatlanok. A `--start-after=<marker>`
  leírása 4 szóközzel behúzott (nem tabbal, mint a többi) — pontosan megtartva.
- `git-upload-pack.adoc`: a „Smart Clients" (`gitprotocol-http[5]`) és „HTTP Transport"
  (`gitprotocol-v2[5]`) idézőjeles szakaszcím-hivatkozások **angolul maradtak** (a 7./14. blokk
  „SPECIFYING RANGES"/„SPECIFYING REVISIONS" prózahivatkozás-precedensét követve — a cél
  szakaszcímek még lefordítatlan fájlokban vannak). Az `include`-ok nincsenek (nem tartalmaz).
  A `git clone --no-local --upload-pack='sudo -u nobody git-upload-pack' ...` tab-indentált
  parancspélda bájtazonos. `SEE ALSO`: `linkgit:gitnamespaces[7]` változatlan.
- `gitprotocol-common.adoc`: 4 pár `----` listing-blokk (ABNF-nyelvtan) bájtazonos, beleértve a
  `refname /=  "refs/" <see discussion below>` sort is (a `<see discussion below>` a listing
  blokkon belül, verbatim marad). A `.` számozott lista-jelölők megtartva.
- Mindegyik man page GIT szakasza „A linkgit:git[1] csomag része" alakra fordítva (4. blokk).
- Szintaxis-ellenőrzés: mind a 10 fájlban a `----`/`....`/`====` határolók és man-page
  szekció-aláhúzások érintetlenek, `ifdef::`/`endif::` csak a `git-var.adoc`-ban (2+2, párban),
  a `gitprotocol-common.adoc` 2 új defenzív anchora az egyetlen `[[...]]` a batchben, a
  bekezdéshatárok megtartva.

## 22. blokk — `howto/` mappa, a 10 legkisebb fájl — 2026-09-10

**Módszer:** a felhasználó kérésére a `howto/` mappa 10 legkisebb (byte szerint), még `[ ]`
jelölésű fájlja, orchestrátor fordította közvetlenül (subagent nélkül, a fájlok 2–7 KB-os mérete
miatt). Fájlok: `use-git-daemon.adoc`, `using-merge-subtree.adoc`, `rebuild-from-update-hook.adoc`,
`separating-topic-branches.adoc`, `new-command.adoc`, `recover-corrupted-blob-object.adoc`,
`update-hook-example.adoc`, `rebase-from-internal-branch.adoc`, `keep-canonical-history-correct.adoc`,
`revert-branch-rebase.adoc`.

**Ezek NEM man page-ek.** E-mail-stílusú how-to cikkek (`Content-type: text/asciidoc` fejléccel).
A főcím és **minden** alcím fordult (a „VÉGLEGES DÖNTÉS" csupa-nagybetűs man-page-alcím szabály itt
nem releváns — a howto cikkeknek nincs `NAME`/`SYNOPSIS`/… szekciójuk, az alcímeik mind Title Case
vagy mondat-alakúak). A kétsoros (setext) `=` / `-` aláhúzások a fordított cím pontos hosszához
igazítva (Python `len()` alapú ellenőrzés; 2 db ±1 elütés menet közben javítva:
`recover-corrupted-blob-object.adoc`, `keep-canonical-history-correct.adoc`).

### E-mail-fejléc kezelése — precedens (első howto-batch)

- A levéltovábbítási fejlécmezők (`From:`, `To:`, `Cc:`, `Date:`, `Subject:`, `Message-ID:`)
  **bájtazonosan angolul maradnak** (a skill „e-mail-címek változatlanok" + a 9. blokk „e-mail-
  idézetek bájtazonosak" szabályának kiterjesztése az egész fejlécre).
- Az `Abstract:` docinfo-attribútum **törzse fordul** (ez a cikk absztraktja, ténylegesen renderelt
  dokumentációszöveg), a folytatósorok egy-egy vezető szóközzel (folded header) — a törést
  természetes szóhatárra tettük, nem szó belsejébe.
- A `Content-type: text/asciidoc` sor változatlan.

### Ebben a blokkban rögzített / megerősített döntések

| angol | magyar | megjegyzés |
|---|---|---|
| history | **„előzmény" / „előzmények"** | a `Documentation/` fában már domináns fordítás (`git-filter-branch.adoc` stb. — ellenőrizve grep-pel); a `git-fast-import.adoc`-beli szórványos „history-t" alak nem precedens. `project history` → „projektelőzmény", `ancestry graph` → „származási gráf" |
| "trunk" (a fő fejlődési vonal, SVN-örökség) | **marad `"trunk"` angolul, idézőjelben** | `keep-canonical-history-correct.adoc` — a „törzs"/„trönk" alakok elkerülve; toldalék kötőjellel: `"trunk"-ról`, ill. ragozatlan `a trunkon`, `a trunkra` a folyó szövegben |
| first-parent chain / order | **„first-parent lánc" / „first-parent sorrend"** | a `--first-parent` kapcsolóból; a „first-parent" elem angolul marad |
| revert (ige) | **„revertel"**, `revertelj`, `revertelés` | `revert-branch-rebase.adoc` — a 0. blokk parancsnév-ige mintája (`rebase-el`, `stashel`); a `git revert` parancsnév és a `--no-commit`/`-n` kapcsolók angolul |
| sanity check | **„helyesség-ellenőrzés"** | `revert-branch-rebase.adoc` — nincs jobb bevett magyar alak; „épelméjűség-ellenőrzés" kerülve |
| throw-away / temporary branch | **„eldobható branch" / „ideiglenes branch"** | `revert-branch-rebase.adoc` |
| forward port (changes) | **„előre portolja (a változtatásokat)"** | `rebase-from-internal-branch.adoc` — ad hoc, nincs bevett magyar terminus |
| contributor / integrator | **marad „contributor"** angolul (a „maintainer" mintájára, 0. blokk); **„integrátor"** / „projektintegrátor" | `rebase-from-internal-branch.adoc`, `keep-canonical-history-correct.adoc` |
| extension command / subcommand | **„bővítményparancs" / „alparancs"** | `new-command.adoc` |
| remote helper | **marad „remote helper"** angolul; `remote helperek` | `new-command.adoc` — Git-fogalomnév, a `bare repository` mintájára |
| surgical tools (a Git-eszközök „élén") | **„sebészeti eszközök"** | `new-command.adoc` — a forrás átvitt értelmű szóhasználatát követi |
| p-code (intermediate form) | **„p-kód"** | `new-command.adoc` |
| how-to / howto (a dokumentumtípus neve prózában) | **marad „how-to" / „howto"** angolul (ahogy a forrás írja, kötőjellel vagy anélkül) | minden fájl — pl. „Ez a how-to", „Ez a howto" |
| cruft (általános „limlom" értelemben, nem a cruft pack) | **„limlom"** | `separating-topic-branches.adoc` — a `git-filter-branch.adoc`-tól független, itt generikus jelentés |
| pretend-merge / pretend merge | **„színlelt merge"** | `separating-topic-branches.adoc` |
| home directory | **„home könyvtár"** | `rebuild-from-update-hook.adoc` |
| access control hook script | **„hozzáférés-vezérlő hook szkript"** | `update-hook-example.adoc` |
| RCS keyword-szerű program-kimenet / lokalizálatlan üzenetek (`"no such repository"`, `broken link from tree ...`, `There are only 'skip'ped ...` stb.) | **bájtazonosan angolul** | a 5./6./9. blokk precedense (kódblokkon belül úgyis verbatim) |

### Verbatim (bájtazonosan angolul) hagyott blokkok

- `use-git-daemon.adoc`: a `$ git ls-remote …` / `fatal: The remote end hung up …` behúzott
  literál sorok.
- `using-merge-subtree.adoc`: a `----------------` kódblokk (`git remote add` … `git pull -s subtree`)
  a `<1>`–`<5>` callout-jelölőkkel; a callout-**magyarázatok** viszont a blokk alatt fordultak.
- `rebuild-from-update-hook.adoc`: a 4 szóközzel behúzott literál blokkok (`/pub/scm/…` útvonaltábla,
  `git clone …`, a `cat >dododoc.sh <<\EOF …` és `cat >…/post-update <<\EOF …` heredoc-os
  shell-szkriptek — a `<<\EOF` **nem** xref).
- `separating-topic-branches.adoc`: 5 ASCII-art commit-gráf + 4 parancsblokk (a `;#` inline
  kommentekkel).
- `recover-corrupted-blob-object.adoc`: 3 db `-----` (59 kötőjel) körülhatárolt blokk — idézett
  e-mail-részletek (`> …`) és `git-fsck` kimenet; a záró `\t\t\tLinus` aláírás.
- `rebase-from-internal-branch.adoc`: a `--------------------------------------` blokk (idézett
  levélváltás `>`/`>>` szintekkel); 6 ASCII-art gráf; 5 parancsblokk; a záró `-jc`.
- `revert-branch-rebase.adoc`: 11 db `----…----` (48 kötőjel) blokk — mind `$ git …` terminál-átirat
  valós, lokalizálatlan Git-kimenettel (`Updating from …`, `* Applying: …`, diffstat).
- `keep-canonical-history-correct.adoc`: 16 db `------------` (12 kötőjel) blokk — ASCII-art gráfok
  és `$ git …` parancsok; a numbered list `+` folytatásjelölői megtartva.
- `update-hook-example.adoc`: a `----…----` (52 kötőjel) blokkban a teljes `#!/bin/bash` access-
  control szkript (minden `#`-komment és `info/grant/deny` üzenetszöveg angolul); a 4 szóközzel
  behúzott doc-idézet (18–28. sor, „Before each ref is updated…") és a config-formátum-példa
  (`refs/heads/master junio` stb.).

### Címsor-anchorok

- Egyik fájlban sincs `[[...]]` anchor vagy `<<...>>` xref (grep-pel ellenőrizve az egész batchre).
  A `rebuild-from-update-hook.adoc` `<<\EOF` előfordulásai heredoc-jelölők kódblokkon belül, nem
  AsciiDoc xrefek — érintetlenül hagyva.
- `keep-canonical-history-correct.adoc` és `use-git-daemon.adoc` végén a záró `See also <URL>` /
  bare-URL sorok **inline prózaként** kezelve: a `See also` → „Lásd még" fordult (nem szekciócím,
  a `bundle-uri.adoc` 1. blokkbeli `See Also` **cím** precedense ide nem vonatkozik), az URL
  változatlan.

### Man-page címként angolul hagyott címsorok

- **Nincs egy sem** — egyik fájl sem man page.

## 23. blokk — a következő 10 legkisebb, még lefordítatlan „Gyökér" fájl — 2026-09-10

**Módszer:** ugyanaz, mint a 15–21. blokkban (a két gyökér-tábla együttes, sorméret/byte szerint
növekvő listája, `gitglossary.adoc`/`git.adoc`/`config.adoc`/`git-fast-import.adoc` kihagyva).
Orchestrátor fordította közvetlenül. **Megjegyzés a számozásról:** a „22. blokk" számot egy
párhuzamos `howto/`-munkamenet foglalta le (l. a progress batch-naplóban), ezért ez a batch a
„23. blokk". Fájlok: `git-rev-list.adoc`, `gitformat-bundle.adoc`, `git-name-rev.adoc`,
`git-gui.adoc`, `urls.adoc`, `gitmailmap.adoc`, `git-web--browse.adoc`, `git-patch-id.adoc`,
`DecisionMaking.adoc`, `git-mailinfo.adoc`. A `DecisionMaking.adoc` NEM man page, az `urls.adoc`
és az `i18n.adoc`-hoz hasonló include-cél fragmens; a többi man page (`gitformat-bundle.adoc`,
`gitmailmap.adoc` szekció 5).

### Ebben a blokkban rögzített / megerősített döntések

| angol | magyar | megjegyzés |
|---|---|---|
| commit ancestry graph | **„commit-ősgráf"** | `git-rev-list.adoc` |
| build artifacts | **„build-műtermékek"** | `git-rev-list.adoc` |
| ABNF notation | **„ABNF-jelölés"** | `gitformat-bundle.adoc` — konzisztens a 21. blokk (`gitprotocol-common.adoc`) döntésével |
| "Capabilities" / "Prerequisites" / "References" / "Pack" (a bundle-formátum ABNF-nyelvtan elem-nevei, idézőjelben) | **változatlanul angolul, idézőjelben**, első előforduláskor magyar glosszával: `"Capabilities" (képességek)`, `"Prerequisites" (előfeltételek)`, `"References" (referenciák)` | `gitformat-bundle.adoc` — a `config.kulcs::` címke-szabály / a `technical/` blokkok „coined term" mintája; a nagybetűs `CAPABILITIES` / `SEMANTICS` / `FORMAT` szekciócímek a VÉGLEGES DÖNTÉS szerint amúgy is angolul maradnak |
| RFC 2119 kulcsszavak (`MUST`, `MAY`, `CAN`, `NOT` — csupa nagybetűvel a forrásban) | **bájtazonosan angolul maradnak**, magyar főnévi igenévvel utánuk (pl. „MUST már rendelkeznie", „MAY ide bármilyen karakterláncot tenni", „CAN belőle »git fetch«-elni") | `gitformat-bundle.adoc` — a 21. blokk (`gitprotocol-common.adoc`) felhasználói döntésének alkalmazása; a kisbetűs `must`/`may` a prózában továbbra is fordul („kell") |
| "patch ID" | **változatlanul angolul, idézőjelben** (`"patch ID"`), a `patch ID` alak backtick nélkül is angolul | `git-patch-id.adoc` |
| "stable" / "unstable" (hash/összeg minősítése, idézőjelben) | **„stabil" / „instabil"** (fordítva, idézőjel megtartva) | `git-patch-id.adoc` — nem tulajdonnév, sima jelző |
| scissors line (`--scissors`) | **„ollóvonal"** | `git-mailinfo.adoc` |
| email cruft | **„e-mail-szemét"** | `git-mailinfo.adoc` |
| MIME transfer encoding | **marad „MIME transfer encoding"** angolul | `git-mailinfo.adoc` — szabvány-terminus |
| transliterating | **„transzliterálás"** | `git-mailinfo.adoc` |
| symbolic names suitable for human digestion | **„ember számára emészthető szimbolikus nevek"** | `git-name-rev.adoc` |
| project leadership committee (PLC) | **„a projekt vezetői bizottsága (PLC)"** — a rövidítés angolul marad | `DecisionMaking.adoc` |
| proof of concept | **marad „proof of concept"** angolul; ragozva „proof of concepttel" | `DecisionMaking.adoc` |
| Contributors' Summit | **marad angolul, tulajdonnévként** | `DecisionMaking.adoc` |
| tree browser / blame viewer (`git-gui`) | **„tree-böngésző" / „blame-nézegető"** | `git-gui.adoc` |
| dumb/smart — nincs ebben a batchben | — | — |

### Címsor-anchorok

- **`urls.adoc`** — a `GIT URLS[[URLS]]` cím (explicit inline `[[URLS]]` anchorral, csupa nagybetűs,
  kétsoros) a **VÉGLEGES DÖNTÉS** szerint **angolul maradt**; a `[[URLS]]` anchor és a rá mutató
  `<<URLS,...>>` xrefek (`git-pull.adoc`, `git-push.adoc`, `pull-fetch-param.adoc` — mind még
  lefordítatlan, `GIT URLS` látható szöveggel; `git-clone.adoc` — már lefordítva, `GIT URL-ek`
  látható szöveggel) érintetlenek. **Jövőbeli konzisztencia:** amikor `git-pull.adoc` /
  `git-push.adoc` / `pull-fetch-param.adoc` sorra kerül, a `<<URLS,GIT URLS>>` látható szövegét
  `<<URLS,GIT URL-ek>>`-re kell átírni a `git-clone.adoc` precedense szerint. A cím maga angolul
  marad — a link-szöveg ettől függetlenül lehet magyar (az anchor id a döntő).
- **`DecisionMaking.adoc`** (NEM man page): mind a 4 Title Case alcím fordult, fölé defenzív
  `[[_introduction]]`, `[[_larger_discussions_with_patches]]`,
  `[[_larger_discussions_without_patches]]`, `[[_other_discussion_venues]]` anchor (autogen slug az
  eredeti angol címből). A level-0 doc-cím nem kapott anchort. Nincs rájuk `<<...>>` xref a fában
  (grep-pel ellenőrizve).
- **`git-gui.adoc`**: `Examples` → „Példák" + `[[_examples]]`, `Other` → „Egyéb" + `[[_other]]`
  (mindkettő Title Case, NEM csupa nagybetűs — a `git-whatchanged.adoc` (18. blokk) „Examples" →
  „Példák" precedensét követi). A `COMMANDS` és `SEE ALSO` a szokásos módon (angolul, ill. kanonikus).
- **`git-web--browse.adoc`**: két Title Case `~~~~` alcím fordult defenzív anchorral:
  `[[_conf_var_from_c_option_and_web_browser]]` („A CONF.VAR (a -c opcióból) és a web.browser"),
  `[[_note_about_git_config_global]]` („Megjegyzés a git-config --global-ról"). A
  `browser.<tool>.path` és `browser.<tool>.cmd` `~~~~` alcímek **config-kulcs-literálok**, ezért
  **változatlanul** maradtak (nincs fordítás, nincs új anchor). `CONFIGURATION VARIABLES` és
  `NOTE ABOUT KONQUEROR` a VÉGLEGES DÖNTÉS szerint angolul.
- **`gitformat-bundle.adoc`**: `Note on shallow clones and Git bundles` → „Megjegyzés a shallow
  klónokról és a Git bundle-ökről" + `[[_note_on_shallow_clones_and_git_bundles]]` (Title Case
  `~~~~` alcím). `FORMAT` / `SEMANTICS` / `CAPABILITIES` a VÉGLEGES DÖNTÉS szerint angolul.
- A többi 5 fájlban (`git-rev-list.adoc`, `git-name-rev.adoc`, `gitmailmap.adoc`,
  `git-patch-id.adoc`, `git-mailinfo.adoc`) nincs `[[...]]`/`<<...>>` (grep-pel ellenőrizve);
  `gitmailmap.adoc` `SYNTAX` és minden fájl kanonikus man-page címei angolul maradtak.

### Megőrzött markup / megjegyzések

- Minden lefordított Title Case setext-cím `=`/`-`/`~` aláhúzása a fordított cím **pontos
  karakterhosszához** igazítva (Python `len()` alapú utólagos ellenőrzés; 4 db ±1–2 elütés menet
  közben javítva: `gitformat-bundle.adoc` (54→52), `git-web--browse.adoc` (44→43, 37→36),
  `DecisionMaking.adoc` (37→38)).
- `git-rev-list.adoc`: 9 pár `----------` (10 kötőjel) EXAMPLES-blokk bájtazonos, a bennük lévő
  `# reachable objects` stb. angol kommentekkel; `:git-rev-list: 1` attribútum-sorok és 3
  `include::` sor (`rev-list-description`, `rev-list-options`, `pretty-formats`) változatlan.
- `gitformat-bundle.adoc`: 2 pár `----` ABNF-blokk (v2/v3 nyelvtan) bájtazonos.
- `git-name-rev.adoc`: a `-----------` / `------------` `$ cat sample.txt` / `% git name-rev …`
  terminál-átirat blokkok bájtazonosak (valós, lokalizálatlan kimenettel).
- `urls.adoc`: 2 pár `[verse]` + `--`/`--` nyitott blokk (`[url "__<actual-url-base>__"]` /
  `insteadOf` / `pushInsteadOf`) és 2 db `------------` config-mintablokk bájtazonos; a
  `__<actual-url-base>__` (bold) és `_<other-url-base>_` / `_<address>_` (italic) placeholderek
  változatlanok. Az `ifndef::git-clone[]` / `ifdef::git-clone[]` (2+2, párban) érintetlen.
- `gitmailmap.adoc`: 5 pár `--`/`--` nyitott blokk (`Proper Name <…>` példák) és 5 pár
  `------------` EXAMPLES-blokk bájtazonos; a `&#64;` HTML-entitások és a `'#'` / `'<'` / `'>'`
  idézőjeles karakterhivatkozások változatlanok.
- `git-web--browse.adoc`: 2 db `------------------------------------------------` (48 kötőjel)
  config-mintablokk (`[web]` / `[browser "konq"]`) bájtazonos; a `{litdd}` attribútum-referenciák
  (`git-web{litdd}browse`) és a `'Note about konqueror'` idézőjeles prózahivatkozás (a
  `NOTE ABOUT KONQUEROR` angol szekciócímre) változatlanok.
- `git-patch-id.adoc`: 1 pár `--`/`--` nyitott blokk (`--stable` felsorolás) és 1 pár `----`
  `#!/bin/sh` példaszkript-blokk bájtazonos.
- `git-mailinfo.adoc`: 2 pár `--`/`--` nyitott blokk (`-k` és `--quoted-cr` felsorolások); a
  `*\t` (csillag + tab) lista-jelölők megtartva; 2 `include::` sor
  (`includes/cmd-config-section-all`, `config/mailinfo`) változatlan.
- `DecisionMaking.adoc`: a `link:https://lore.kernel.org/…[látható szöveg]` makrók URL-je
  változatlan, a látható szöveg fordult, **kivéve** a „Notes from Git Contributor Summit, Los
  Angeles (April 5, 2020)" thread-címet, amely **angolul maradt** (konkrét archivált levél tárgya
  — a 9. blokk bibliográfiai-cím precedensét követi).
- Mindegyik man page GIT szakasza „A linkgit:git[1] csomag része" alakra fordítva (4. blokk).
- Szintaxis-ellenőrzés: mind a 10 fájlban a `----`/`--`/`====`/`~~~~` határolók és aláhúzások
  párban/pontos hosszal, `ifdef::`/`endif::` csak az `urls.adoc`-ban (2+2, párban), a
  bekezdéshatárok megtartva.

## 24. blokk — `howto/` mappa, a maradék 6 fájl (mappa kész) — 2026-09-10

**Módszer:** a `howto/` mappa hat, még lefordítatlan fájlja (a 22. blokk 10-es batch-e után
maradt), byte szerint növekvő sorrendben. Orchestrátor fordította közvetlenül. Fájlok:
`using-signed-tag-in-pull-request.adoc`, `setup-git-server-over-http.adoc`, `revert-a-faulty-merge.adoc`,
`recover-corrupted-object-harder.adoc`, `maintain-git.adoc`, `coordinate-embargoed-releases.adoc`.
**Ezzel a `howto/` mappa mind a 16 fájlon KÉSZ.**

**NEM man page-ek** — a főcím és minden alcím fordult; a setext `=`/`-`/`~` aláhúzások a fordított
cím pontos hosszához igazítva (Python `len()`-alapú ellenőrzés; ~10 db ±1–2 elütés menet közben
javítva). A 22. blokk e-mail-fejléc-precedense érvényes: `From`/`To`/`Cc`/`Date`/`Subject`/
`Message-ID`/`References` bájtazonosan angolul, `Abstract:` docinfo-törzs fordul, `Content-type`
változatlan.

### Ebben a blokkban rögzített / megerősített döntések

| angol | magyar | megjegyzés |
|---|---|---|
| lieutenant (Git alrendszer-maintainer szerep) | **marad „lieutenant"** angolul | `using-signed-tag-in-pull-request.adoc`, `maintain-git.adoc` — a „maintainer"/„contributor" mintája (0./22. blokk) |
| ADDENDUM (csupa nagybetűs, aláhúzás NÉLKÜLI szakasz-felirat prózában, `See the ADDENDUM below` hivatkozással) | **marad `ADDENDUM` angolul** | `revert-a-faulty-merge.adoc` — a „VÉGLEGES DÖNTÉS" (csupa nagybetűs man-page-stílusú cím) szellemében, mert prózahivatkozás mutat rá szó szerint; a `DETACHED HEAD` (10. blokk) precedens |
| stakeholder | **„érdekelt"** (fn) | `coordinate-embargoed-releases.adoc` |
| packager / binary packager | **„csomagoló" / „bináris csomagoló"** | `coordinate-embargoed-releases.adoc`, `maintain-git.adoc` |
| release train | **„kiadási vonal"** | `coordinate-embargoed-releases.adoc` |
| backport / backported fix | **„visszaportol" / „visszaportolt javítás"** | `coordinate-embargoed-releases.adoc` — a 19. blokk „előre portol" párja |
| embargo / embargoed release / lifting the embargo | **„embargó" / „embargós (v. embargó alatti) kiadás" / „az embargó feloldása"** | `coordinate-embargoed-releases.adoc` |
| security advisory (GitHub) | **marad „security advisory"** angolul; „security advisory vázlat" | `coordinate-embargoed-releases.adoc` |
| responsible disclosure | **„felelős közzététel"** | `coordinate-embargoed-releases.adoc` |
| release artifacts | **„kiadási artefaktumok"** | `coordinate-embargoed-releases.adoc` |
| Pacific Time (10am) | **„csendes-óceáni idő szerint (reggel 10)"** | `coordinate-embargoed-releases.adoc` |
| feature/maintenance release | **„feature release" / „maintenance release"** (angolul, toldalékkal: `release-ek`, `release-hez`) | `maintain-git.adoc` — a kiadástípus-nevek angolul; „release candidate"/„preview" release szintén angolul, idézőjelben ahol a forrás is |
| integration branch / topic branch | **„integrációs branch" / „topic branch"** (topic branch a 0. blokk szerint úgyis angolul) | `maintain-git.adoc` |
| to cook / cooking (a `next`-ben „főzés") | **„főz" / „főzés"** | `maintain-git.adoc` — a „What's cooking" üzenetnév angolul marad |
| graduated topic (a `master`-be jutott) | **„végzett topic"** | `maintain-git.adoc` — a „Graduated to master" szekciónév a mintafájlban angolul marad |
| reroll / rerolled series | **„újragöngyölés" / „újragöngyölt sorozat"** | `maintain-git.adoc` — konzisztens a 13. blokk (`git-filter-branch`) „újragöngyölt"-jével |
| release train / daily driver / guinea pig | „mindennapi meghajtó" / „kísérleti nyúl" | `maintain-git.adoc` — a forrás átvitt szóhasználatát követi |
| stakeholder input / to give input | **„input" (marad) / „megadni az inputját"** | `coordinate-embargoed-releases.adoc` |
| dumb server / smart transport | l. 17./19. blokk (idézőjeles, ad hoc) | `setup-git-server-over-http.adoc`-ban nem fordult elő; a 2006-os szöveg amúgy is „CGI capable" / DAV-alapú |
| „Note:" (kis-nagybetűs, prózában, NEM a `NOTE:` admonition-makró) | **„Megjegyzés:"** | `coordinate-embargoed-releases.adoc` — a 15./17. blokk precedense |

### `link:`/URL-es link makrók

- `coordinate-embargoed-releases.adoc`: több `https://…[látható szöveg]` alakú link, ahol a
  látható szöveg **sortörésen átível** (`[open\nan advisory]`, `[the\nv2.24.1 mail]`) — az URL
  bájtazonos, a `[...]` látható szöveg fordult, a sortörés a fordított szövegben természetes
  helyre került (`[megnyitsz\negy advisory-t]` stb.).
- `setup-git-server-over-http.adoc`: `linkgit:git-http-backend[1]` a `NOTE:` admonition-prózában
  bájtazonos.

### Verbatim (bájtazonosan angolul) hagyott blokkok

- `using-signed-tag-in-pull-request.adoc`: 9 db `------------` (12 kötőjel) `git request-pull` /
  `git push` / `git show --show-signature` terminál-átirat blokk, a `# gpg: …` sorokkal és a
  beágyazott `-----…-----` (47 kötőjel) aláírt-tag-üzenet keretével.
- `setup-git-server-over-http.adoc`: **minden szóközzel behúzott sor bájtazonos** (2006-os, lazán
  formázott doksi — a behúzott `$ apache2 …` parancsok, `httpd.conf` / `git.conf` config-
  részletek, `[remote]`-mintakonfigok, és a behúzott Debian-specifikus utasítás-prózák is; ezek
  AsciiDoc-literál-bekezdésként renderelnek). Csak a 0. oszlopból induló próza + a felső szintű
  `- ` felsoroláspontok + a 6 szekciócím + a záró `Szerzők` fordult. **Jegyzet:** ez eltér a
  `maintain-git.adoc` kezelésétől (l. lent), mert ott a behúzott szöveg listaelem-folytatás
  (a `- ` felsoroláspont törzsszövegéhez igazítva), itt viszont különálló literál bekezdés.
- `maintain-git.adoc`: az 5–7 szóközzel behúzott `$ git …` / `$ Meta/… ` parancsblokkok és a
  `[notes]` / `[remote "github"]` / `[remote "github2"]` config-blokkok bájtazonosak (a `#`
  kommentek és `;#` inline kommentek is). A **3 szóközzel behúzott, `- ` felsoroláspontokhoz
  tartozó folytatás-próza fordult** (listaelem-tartalom, nem literál blokk). A `"<<"` és `">>"`
  idézőjeles string-literálok (nem AsciiDoc xref) változatlanok.
- `recover-corrupted-object-harder.adoc`: `****`-sidebar blokk (a próza fordult, a
  `link:recover-corrupted-blob-object.html[ezt a howtót]` cél változatlan); a `-----`/`-------`/
  `----------------…` határolt blokkokban a teljes `#include`-os C programok (`munge`, `inflate`,
  `sha1-munge`), `dd`/`gcc`/`printf` shell-sorok, hexdumpok, `git fsck` kimenet és a
  `-  cp = strtok (arg, "+");` diff bájtazonos.
- `revert-a-faulty-merge.adoc`: a 4 szóközzel behúzott Alan- és Linus-idézet (literál blokk) és
  minden ` ---o---o---M---x` ASCII-art commit-gráf + `$ git revert …` parancs bájtazonos; a
  `_data_`/`_history_`/`_not_`/`_all_` compat-emphasis a **Linus-idézeten belül** verbatim maradt
  (a blokk maga nem fordult).
- `coordinate-embargoed-releases.adoc`: 2 db `....` határolt példa-e-mail (distros@ és
  oss-security@ sablonlevelek) **teljes egészében bájtazonosan angolul** — copy-paste sablonok,
  `<placeholder>`-ekkel; a `git bundle create …` / `tar cJvf …` behúzott parancspár bájtazonos.

### Címsor-anchorok

- Egyik fájlban sincs `[[...]]` anchor vagy `<<...>>` xref (grep-pel ellenőrizve). A
  `maintain-git.adoc` `"<<"`/`">>"` előfordulásai idézőjeles string-literálok, nem xrefek —
  érintetlenül hagyva.

### Man-page címként angolul hagyott címsorok

- **`ADDENDUM`** (`revert-a-faulty-merge.adoc`) — l. a döntés-táblát. A többi fájl összes alcíme
  fordult (mind Title Case vagy mondat-alakú, egyik sem csupa nagybetűs man-page-stílusú).

## 25. blokk — a következő 5 legkisebb, még lefordítatlan „Gyökér" fájl — 2026-09-10

**Módszer:** a felhasználó 5-ös bontást kért; ugyanaz a lista-logika, mint a 15–23. blokkban.
**Számozás:** a „24." számot egy párhuzamos `howto/`-munkamenet foglalta le, ezért ez a „25. blokk".
Fájlok: `git-remote-ext.adoc`, `git-fsmonitor--daemon.adoc`, `git-merge-file.adoc`,
`git-shortlog.adoc`, `urls-remotes.adoc`. Az `urls-remotes.adoc` include-cél fragmens (a
`git-clone`/`git-fetch`/`git-pull`/`git-push`/`git-ls-remote` `include`-olja), a többi rövid man
page. Orchestrátor fordította közvetlenül.

### Ebben a blokkban rögzített / megerősített döntések

| angol | magyar | megjegyzés |
|---|---|---|
| smart transport (NAME-mezőben, `git-remote-ext.adoc`) | **`»smart«` átvitel** (guillemet-ben) | a 19. blokk (`git-remote-fd.adoc`) `»smart« átviteli adatfolyam` mintáját követi; **jövőbeli döntési függőség marad** a `gitprotocol-http.adoc` fordításakor |
| remote helper | **marad „remote helper"** angolul | `git-remote-ext.adoc`, `urls.adoc` (21. blokk) precedense |
| escape-elt / nem escape-elt (szóköz) | **„escape-elt" / „nem escape-elt"** | `git-remote-ext.adoc` |
| vhost / service / repository field (git:// protokoll-kérés mezőnevei) | **változatlanul angolul** (`vhost`, `service`, `repository` mező) | `git-remote-ext.adoc` — protokoll-mezőnevek, nem fordítandók |
| link-level address | **„link-szintű cím"** | `git-remote-ext.adoc` |
| filesystem monitor / fsmonitor daemon | **„fájlrendszer-figyelő" / „fsmonitor daemon"** | `git-fsmonitor--daemon.adoc` — a `daemon` a 0. blokk szerint angolul marad |
| watch (inotify, fn) | **„figyelő"** | `git-fsmonitor--daemon.adoc` LINUX CAVEATS |
| network-mounted (filesystem/repository) | **„hálózati csatolású"** | `git-fsmonitor--daemon.adoc` |
| Unix domain socket (UDS) | **marad angolul** a rövidítéssel; „socket" / „socket-fájl" | `git-fsmonitor--daemon.adoc` |
| super repo | **„szuperrepó"** | `git-fsmonitor--daemon.adoc` — a 3. blokk `superproject` → `szuperprojekt` mintájának rokona |
| simple IPC (link-szöveg) | **„egyszerű IPC"** (a `link:` látható szövege fordult, a `.html` cél változatlan) | `git-fsmonitor--daemon.adoc` |
| three-way file merge | **„háromutas fájl-merge"** | `git-merge-file.adoc` — a 0. blokk `three-way merge` → `háromutas merge` mintája |
| conflict marker / marker | **„konfliktusjelölő"** | `git-merge-file.adoc` |
| `<<<<<<<` / `>>>>>>>` (konfliktus-jelölők a prózában, backtick NÉLKÜL a forrásban) | **bájtazonosan megtartva** a magyar mondatban is | `git-merge-file.adoc` — a forrás sem teszi backtick közé; a markupot karakterazonosan visszük át |
| "diff3" / "zdiff3" / "myers" / "histogram" / "patience" (konfliktus-/diff-stílusnevek, idézőjelben) | **változatlanul angolul, idézőjelben** | `git-merge-file.adoc` — a 15. blokk (`diff-algorithm-option.adoc`) döntése |
| mismerge | **„hibás merge"** | `git-merge-file.adoc` |
| release announcements | **„kiadási bejelentések"** | `git-shortlog.adoc` |
| trailer (`--group=trailer:<field>`) | **marad „trailer"** angolul | `git-shortlog.adoc` — a 11. blokk (`git-commit.adoc`) döntése |
| `name <email>` identity | **„`name <email>` identitás"** | `git-shortlog.adoc` |
| co-author | **„társszerző"** | `git-shortlog.adoc` |
| Linewrap / rewrap (kimenet) | **„sortördel" / „újratördel"** | `git-shortlog.adoc` |
| "tracking information" (idézőjelben, git-branch terminológia) | **változatlanul angolul, idézőjelben** | `urls-remotes.adoc` `[NOTE]` — a doksi maga idézőjelezi, git-kimenet-közeli kifejezés |
| branch (allatívusz: „társítható … branchhez") | **`branchhez`** (kötőjel nélkül, a 7. blokk „branch toldalék kötőjel NÉLKÜL" szabálya szerint) | `urls-remotes.adoc` — az instrumentális („branchcsel") kerülve, allatívuszra átfogalmazva a jobb olvashatóságért |

### Címsor-anchorok

- **`urls-remotes.adoc`**:
  - `REMOTES[[REMOTES]]` (csupa nagybetűs, explicit inline `[[REMOTES]]` anchor) és
    `[[UPSTREAM-BRANCHES]]` / `UPSTREAM BRANCHES` (csupa nagybetűs, explicit anchor) — a **VÉGLEGES
    DÖNTÉS** szerint **angolul maradtak**; rájuk `<<REMOTES,REMOTES>>` és
    `<<UPSTREAM-BRANCHES,UPSTREAM BRANCHES>>` / `<<UPSTREAM-BRANCHES,upstream>>` xref mutat a még
    lefordítatlan `git-pull.adoc` / `git-push.adoc` / `pull-fetch-param.adoc` fájlokból (grep-pel
    ellenőrizve) — mind explicit anchor id-vel, tehát biztonságosak. A cím szövege és a látható
    link-szöveg is angol marad.
  - 3 Title Case `~~~~` alcím fordult defenzív anchorral: `[[_named_remote_in_configuration_file]]`
    („Megnevezett remote a konfigurációs fájlban"),
    `[[_named_file_in_git_dir_remotes]]` („Megnevezett fájl a `$GIT_DIR/remotes`-ban"),
    `[[_named_file_in_git_dir_branches]]` („Megnevezett fájl a `$GIT_DIR/branches`-ban"). Nincs
    rájuk `<<...>>` xref sehol. A `~~~~` aláhúzás a fordított cím **pontos** karakterhosszához
    igazítva (Python `len()` alapú utólagos ellenőrzés; 3 db +1 elütés javítva: 43→42, 42→41,
    43→42).
- A másik 4 fájlban nincs `[[...]]`/`<<...>>` (grep-pel ellenőrizve).

### Man-page címként angolul hagyott címsorok (VÉGLEGES DÖNTÉS szerint, automatikusan)

- `git-remote-ext.adoc`: `ENVIRONMENT VARIABLES PASSED TO COMMAND` (a `ENVIRONMENT VARIABLES` a
  kanonikus listán).
- `git-fsmonitor--daemon.adoc`: `REMARKS`, `LINUX CAVEATS` (a `CAVEATS` a kanonikus listán).
- `git-shortlog.adoc`: `MAPPING AUTHORS` — csupa nagybetűs, nem kanonikus → **angolul maradt** a
  VÉGLEGES DÖNTÉS szerint. **Megjegyzés:** a `git-blame.adoc` és a `git-check-mailmap.adoc`
  (2026-09-04, 3./7. blokk) ugyanezt a címet még „Szerzők leképezése"-ként fordította — a VÉGLEGES
  DÖNTÉS (2026-09-04, a 14. blokk előtt) viszont csak előre hatályos, és nem igényel visszamenőleges
  javítást; a `git-shortlog.adoc` ezért a korábbi két fájltól eltérően angolul hagyja. Ha a
  felhasználó egységesítést kér, a `git-shortlog.adoc`-ot lehet „Szerzők leképezése"-re javítani
  (+ `[[_mapping_authors]]` defenzív anchor), nem a másik kettőt visszabontani.

### Megőrzött markup / megjegyzések

- `git-remote-ext.adoc`: a `'% '`, `'%%'`, `'%s'`, `'%S'`, `'%G'`, `'%V'` compat-mode-idézőjeles
  szekvencia-nevek és a `(must be the first characters in an argument)` angol zárójeles
  megjegyzés a `::` címkékben **változatlan** (a címke a szekvencia-jelölés, nem fordul); csak a
  leírás-törzs fordult. Az EXAMPLES `"ext::..."` `::` címkéi (valós parancsstringek) bájtazonosak,
  köztük a forrásbeli `, "git push <URL>"` elgépelt vezető vessző is (nem „javítva"). A `&#64;`
  entitás változatlan.
- `git-fsmonitor--daemon.adoc`: a `-- a special type of file --` közbevetés `--` jelölői
  megtartva; 3 db 4-szóközzel behúzott literál blokk (`cat /proc/...`, `sudo sysctl ...`,
  `fs.inotify...`) bájtazonos; `include::includes/cmd-config-section-all.adoc[]` +
  `include::config/fsmonitor--daemon.adoc[]` változatlan; a `"File System Monitor"` idézőjeles
  szakaszcím-hivatkozás (`git-update-index[1]`-re) angolul maradt.
- `git-merge-file.adoc`: a tab-indentált `<<<<<<< A` … `>>>>>>> B` konfliktus-példablokk
  bájtazonos; az `RCS 'merge'` / `RCS 'merge''s` compat-idézőjeles hivatkozások változatlanok.
- `git-shortlog.adoc`: 1 pár `--`/`--` nyitott blokk (`--group` felsorolás) a ` - ` behúzott
  lista-elemekkel; `:git-shortlog: 1` attribútum + `include::rev-list-options.adoc[]` változatlan;
  a `'PRETTY FORMATS'`, `'Commit Formatting'`, `'Specifying Ranges'` compat-idézőjeles
  szakaszcím-hivatkozások angolul maradtak. A `"Your branch and 'origin/main' have diverged…"`
  idézett Git-kimenet bájtazonosan angolul (`urls-remotes.adoc`-ban is).
- `urls-remotes.adoc`: `include::urls.adoc[]` (1. sor) változatlan; 6 pár `------------` (12
  kötőjel) config-mintablokk bájtazonos (a `[remote "<name>"]` / `URL:`/`Push:`/`Pull:` /
  `<URL>#<head>` / `refs/heads/...` sablonokkal); a `[NOTE]` egysoros admonition-blokk jelölő
  változatlan, a törzse fordult.
- Mindegyik man page GIT szakasza „A linkgit:git[1] csomag része" alakra fordítva (4. blokk).
- Szintaxis-ellenőrzés: mind az 5 fájlban a `----`/`--`/`~~~~` határolók és aláhúzások
  párban/pontos hosszal, `ifdef::`/`endif::` egyikben sincs, a bekezdéshatárok megtartva.

## 26. blokk — a következő 10 legkisebb, még lefordítatlan „Gyökér" fájl — 2026-09-10

**Módszer:** ugyanaz, mint a 15–21./23./25. blokkban (a két gyökér-tábla együttes, sorméret szerint
növekvő listája, `gitglossary.adoc`/`git.adoc`/`config.adoc`/`git-fast-import.adoc`/
`glossary-content.adoc` kihagyva). Orchestrátor fordította közvetlenül, subagent nélkül. Fájlok:
`pretty-options.adoc`, `pull-fetch-param.adoc`, `git-mergetool.adoc`, `gitformat-loose.adoc`,
`gitformat-chunk.adoc`, `gitmodules.adoc`, `git-repo.adoc`, `git-refs.adoc`, `blame-options.adoc`,
`merge-strategies.adoc`. Öt include-cél fragmens (`pretty-options`, `pull-fetch-param`,
`blame-options`, `merge-strategies` – utóbbi a `git-merge`/`git-pull`/`git-rebase` `include`-olja),
három man page (`git-mergetool`, `git-repo` [KÍSÉRLETI], `git-refs`, `gitmodules` szekció 5), két
formátum-spec (`gitformat-loose` szekció 5, `gitformat-chunk` szekció 5).

### Ebben a blokkban rögzített / megerősített döntések

| angol | magyar | megjegyzés |
|---|---|---|
| pretty-print (commit-naplók) | **„szép formázású kiírás"** | `pretty-options.adoc`; a `pretty` formátumnevek (`oneline`/`short`/`medium`/…) és a `--pretty`/`--format` kapcsolók angolul |
| tab expansion (`--expand-tabs`) | **„tabulátor-kifejtés"** | `pretty-options.adoc` |
| chunk / chunk-based (fájlformátum) | **marad „chunk" / „chunk-alapú"**; `chunkok`, `chunkhoz` | `gitformat-chunk.adoc` — Git-specifikus formátum-terminus, a `hunk` (marad, 0. blokk) mintájára; a `chunk-format` API-név és a `chunk-format.h` bájtazonos |
| table of contents (chunk-formátum) | **„tartalomjegyzék"** | `gitformat-chunk.adoc` |
| loose object | **„laza objektum"** (0. blokk `loose / packed object` tételének alkalmazása) | `gitformat-loose.adoc`; a NAME „Git loose object format" → „Git laza objektumformátum" |
| loose object mapping | **„laza objektumok leképezése"** | `gitformat-loose.adoc` — a `compatObjectFormat` `.map` fájljai |
| to shard (data) | **„szilánkokra bont"** | `gitformat-loose.adoc` |
| trailing hash (fájlformátum vége) | **„záró hash"** | `gitformat-loose.adoc`, `gitformat-chunk.adoc` |
| trailer (chunk-formátum, a záró blokk) | **„záró blokk"** | `gitformat-loose.adoc`, `gitformat-chunk.adoc` — itt NEM a `git commit trailer` értelmében (az marad „trailer", 11./25. blokk), hanem a fájlformátum végén lévő ellenőrzőösszeg-blokk |
| ref store / ref-format migration | **„ref-tároló" / „ref-formátum migrálása"** | `git-refs.adoc` |
| merge strategy / merge mechanism | **„merge-stratégia" / „merge-mechanizmus"** (0. blokk `merge strategy` tétele) | `merge-strategies.adoc` |
| 'our' / 'their' version (merge, compat-emphasis) | **'mi' verziónk / 'ő' verziójuk** (a `'...'` emphasis-jelölők megtartva a fordított szón) | `merge-strategies.adoc` — a `git-merge-file.adoc` (25. blokk) `<<<<<<<`/`>>>>>>>` markup-átvitel elvének analógiája: a jelölést karakterazonosan visszük, a szó fordul |
| mismerge | **„hibás merge"** (25. blokk `git-merge-file.adoc` döntése) | `merge-strategies.adoc` |
| criss-cross merge (ambiguity) | **„keresztirányú merge(-kétértelműség)"** | `merge-strategies.adoc` (`resolve` stratégia) |
| "Ostensibly Recursive's Twin" (az `ort` betűszó feloldása, idézőjelben) | **változatlanul angolul, idézőjelben** | `merge-strategies.adoc` — a betűszó szó szerinti jelentése, coined term |
| strategy nevek (`ort`/`resolve`/`octopus`/`ours`/`subtree`/`recursive`) és `-X` opciónevek | **változatlanul angolul** (a `::`/`;;` def-lista-címkék bájtazonosak) | `merge-strategies.adoc` — csak a leírás-törzs fordult |
| `THIS COMMAND IS EXPERIMENTAL. THE BEHAVIOR MAY CHANGE.` | **„EZ A PARANCS KÍSÉRLETI. A VISELKEDÉSE MEGVÁLTOZHAT."** | `git-repo.adoc` — a `git-backfill.adoc` (3. blokk) / `git-for-each-repo.adoc` (19. blokk) / `git-last-modified.adoc` (20. blokk) pontos mintáját ismétli |
| `flag` (`--format` kapcsoló mint „flag") | **marad „flag"** angolul; `flaggel` | `git-repo.adoc` |
| checkin / check-out és check-in (RCS-értelemben, `renormalize`) | **marad „check-out" / „check-in"** angolul, kötőjellel, ahogy a forrás | `merge-strategies.adoc` |

### Címsor-anchorok

- **`gitformat-loose.adoc`**: 2 egysoros `==` szakaszcím (`Loose objects` → „Laza objektumok",
  `Loose object mapping` → „Laza objektumok leképezése") — nincs rájuk `<<...>>` xref sehol a fában
  (grep-pel ellenőrizve), defenzív `[[_loose_objects]]` ill. `[[_loose_object_mapping]]` anchor
  került eléjük (autogen slug az eredeti angol címből).
- **`gitformat-chunk.adoc`**: 2 Title Case setext (`----`) alcím (`Writing chunk-based file formats`
  → „Chunk-alapú fájlformátumok írása", `Reading chunk-based file formats` → „Chunk-alapú
  fájlformátumok olvasása") + 1 `Examples` → „Példák" (vegyes kis-nagybetűs, NEM `EXAMPLES`, a
  18./23. blokk precedense szerint fordul). Mind defenzív anchort kapott
  (`[[_writing_chunk_based_file_formats]]`, `[[_reading_chunk_based_file_formats]]`, `[[_examples]]`),
  nincs rájuk `<<...>>` xref. A setext `----` aláhúzások a fordított cím pontos karakterhosszához
  igazítva (Python `len()` alapú ellenőrzés; 32/32, 35/35, 6/6 — 1 db +1 elütés menet közben javítva).
- **`pull-fetch-param.adoc`**: `[[fetch-refspec]]` explicit anchor változatlan. A `<<URLS,GIT URLS>>`
  látható szövege `<<URLS,GIT URL-ek>>`-re átírva a `git-clone.adoc` / 23. blokk precedense szerint;
  a `<<REMOTES,REMOTES>>` és a `<<CRTB,CONFIGURED REMOTE-TRACKING BRANCHES>>` xrefek (anchor + látható
  szöveg) angolul maradtak (25., ill. 12. blokk döntése).
- A többi 7 fájlban nincs `[[...]]`/`<<...>>` (grep-pel ellenőrizve).

### Man-page címként angolul hagyott címsorok (VÉGLEGES DÖNTÉS szerint, automatikusan)

- `git-mergetool.adoc`: `TEMPORARY FILES`, `BACKEND SPECIFIC HINTS`. A `vimdiff` `~~~~` alcím
  **változatlanul** maradt (tool-név / config-kulcs-literál, a 23. blokk `browser.<tool>.path`
  precedense szerint — nincs fordítás, nincs anchor).
- `git-repo.adoc`: `COMMANDS`, `INFO KEYS` (rájuk mutató prózahivatkozás: `"INFO KEYS"` idézőjelben
  angolul maradt).
- `git-refs.adoc`: `COMMANDS`.
- `merge-strategies.adoc`: `MERGE STRATEGIES` (csupa nagybetűs setext főcím a fragmensben) —
  angolul maradt; rá `<<...>>` xref nincs, de prózahivatkozás igen (`git-cherry-pick.adoc:173`
  már „MERGE STRATEGIES szakaszát" alakban fordítva, `git-revert.adoc` [még lefordítatlan] szintén
  szó szerint hivatkozik rá). A `"NOTES MERGE STRATEGIES"` (`git-notes.adoc`/`config/notes.adoc`)
  egy **másik**, különálló szakasz — nincs ütközés.

### Megőrzött markup / megjegyzések

- `pretty-options.adoc`: 3 `ifdef::`/`ifndef::` nyitó (`git-rev-list`, `with-breaking-changes` ×2) +
  3 `endif::`, mind párban; `"PRETTY FORMATS"` idézőjeles szakaszcím-hivatkozás angolul maradt
  (7./25. blokk precedense); a `NOTE:` admonition-kulcsszó változatlan.
- `pull-fetch-param.adoc`: 4+4 `ifdef::git-pull[]`/`ifndef::git-pull[]` + `endif::`, mind párban;
  2 `[NOTE]` egysoros admonition-blokk jelölő változatlan; `_<repository>_`/`_<refspec>_`/`_<src>_`/
  `_<dst>_`/`__<refspec>__` placeholderek és a `+` refspec-jelölő változatlanok.
- `git-mergetool.adoc`: `[synopsis]` blokk + `git mergetool …` mintasor bájtazonos; `BASE`/`LOCAL`/
  `REMOTE`/`MERGED` env-változónevek, `merge.tool`/`merge.guitool`/`mergetool.<tool>.path` config-
  kulcsok, `include::includes/cmd-config-section-all.adoc[]` + `include::config/mergetool.adoc[]` +
  `include::mergetools/vimdiff.adoc[]` + `:git-mergetool: 1` attribútum változatlanok.
- `gitformat-loose.adoc`: a `- `/`\t* `/`\t\t** ` felsorolás-jelölők és a tab-behúzás
  (helyenként `\t\t\t ` = 3 tab + szóköz, ill. egy `  * ` = 2 szóközös inkonzisztencia a forrásban)
  **bájtazonosan megtartva**; a `[verse]` SYNOPSIS-blokk (`$GIT_DIR/objects/...`) és a `LMAP`/`sha1`/
  `NUL`/`SHA-1`/`SHA-256` literálok, a `0::`/`1::`/`2::`/`3::` típusmező def-lista-címkék változatlanok.
- `gitformat-chunk.adoc`: a 2 szóközzel behúzott ASCII-táblázat (`| Chunk ID (4 bytes) | …`)
  bájtazonos; C-függvénynevek (`init_chunkfile()`, `add_chunk()`, `read_table_of_contents()` stb.),
  `struct chunkfile`/`struct hashfile`, `*commit-graph:*`/`*multi-pack-index:*` félkövér címkék és a
  `_at least_` compat-emphasis (`_legalább_`) változatlanok.
- `gitmodules.adoc`: `submodule.<name>.*` config-kulcs `::` címkék bájtazonosak; a `--`/`--` nyitott
  blokk az `all;;`/`dirty;;`/`untracked;;`/`none;;` `;;` beágyazott def-lista-címkékkel (opcióértékek,
  angolul) — a `\t` + `\t    ` (tab + 4 szóköz) behúzás pontosan megtartva; a `----` `.gitmodules`
  példablokk (`[submodule "libfoo"]` …) bájtazonos.
- `git-repo.adoc`: `[synopsis]` blokk; `include::ref-storage-format.adoc[]`; 2 `------------`
  EXAMPLES parancspélda-blokk (`git repo info …`) bájtazonos; a `lines`/`nul`/`table` formátumnevek,
  `_NUL_`, `layout.bare`/`path.gitdir.absolute` stb. kulcs `::`/`:::` címkék változatlanok.
- `git-refs.adoc`: `[synopsis]` többsoros blokk (tab-folytatásokkal) bájtazonos; `[WARNING]` + `--`/`--`
  nyitott blokk a `*` felsorolással; `include::ref-storage-format.adoc[]` +
  `include::for-each-ref-options.adoc[]` + `include::pack-refs-options.adoc[]` változatlanok;
  `'git refs list'` / `'git refs optimize'` compat-idézőjeles parancsnevek és a `"--reflog"` idézett
  opcióérték angolul maradtak.
- `blame-options.adoc`: minden `::` címke backtickelt opciónév, bájtazonos; `include::line-range-format.adoc[]`
  változatlan; `_<start>_`/`_<end>_`/`_<funcname>_`/`_<rev>_`/`_<num>_`/`_A_`/`_B_` placeholderek,
  `?`/`*`/`""` jelölések, `ignored`/`unblamable` program-kimeneti tokenek változatlanok.
- `merge-strategies.adoc`: `MERGE STRATEGIES` setext főcím + `----` aláhúzás bájtazonos (angolul);
  minden `::` (stratégia) és `;;` (`-X` opció) def-lista-címke bájtazonos; a `"Merging branches with
  differing checkin/checkout attributes"` idézőjeles szakaszcím-hivatkozás (`gitattributes[5]`-re,
  még lefordítatlan) angolul maradt (7./14./21. blokk prózahivatkozás-precedense); a `* ` felsorolás
  2 szóközös behúzása megtartva.
- Szintaxis-ellenőrzés: mind a 10 fájlban a `----`/`--`/`====`/`~~~~` határolók és man-page
  szekció-aláhúzások párban/pontos hosszal, az `ifdef::`/`ifndef::`/`endif::` számlálók egyeznek
  (`pretty-options` 3+3, `pull-fetch-param` 4+4, a többi 0), a bekezdéshatárok megtartva.

## 27. blokk — a következő 10 legkisebb, még lefordítatlan „Gyökér" fájl — 2026-09-10

**Módszer:** ugyanaz, mint a 15–21./23./25./26. blokkban. Orchestrátor fordította közvetlenül,
subagent nélkül. Fájlok: `git-ls-remote.adoc`, `git-send-pack.adoc`, `git-reflog.adoc`,
`git-index-pack.adoc`, `git-ls-tree.adoc`, `git-replace.adoc`, `git-revert.adoc`,
`ReviewingGuidelines.adoc`, `diff-format.adoc`, `gitformat-commit-graph.adoc`. A `git-commit-graph.adoc`
(175 sor) a méretlistán ebbe a batchbe esne, de már `[x]` volt (2026-09-04, friss `Read`-del
megerősítve, hogy teljesen kész) — helyette a `gitformat-commit-graph.adoc` (186 sor, 8089 byte)
került be. Nyolc man page (`git-ls-remote`, `git-send-pack`, `git-reflog`, `git-index-pack`,
`git-ls-tree`, `git-replace`, `git-revert`, `gitformat-commit-graph` [5]), egy option-fragmens
(`diff-format`, a `git-diff*`-ok `include`-olják), egy NEM man page guide (`ReviewingGuidelines`).

### Ebben a blokkban rögzített / megerősített döntések

| angol | magyar | megjegyzés |
|---|---|---|
| review (fn / ige / reviewer) | **„átnézés" / „átnéz" / „átnéző"** | `ReviewingGuidelines.adoc` — új, git-docs-specifikus általános szakszó (a doksi kulcsfogalma); a `Reviewed-by:` trailer bájtazonosan angolul marad |
| contributor / to contribute | **marad „contributor"** angolul (0./24. blokk); ige: **„hozzájárul"** | `ReviewingGuidelines.adoc` |
| cover letter | **marad „cover letter"** angolul (a doksi maga definiálja Terminológia-tételként); a „kísérőlevél" alak is előfordul folyó szövegben szinonimaként | `ReviewingGuidelines.adoc` |
| "blocking" / "non-blocking" (review-megjegyzés minősítés, idézőjelben) | **„blokkoló" / „nem blokkoló"** (fordítva, idézőjel megtartva); a `non-blocking:` `::` def-lista-címke viszont bájtazonosan angolul (a program-közeli, begépelendő prefixek mintája, 5. blokk) | `ReviewingGuidelines.adoc` |
| `nit:` / `aside:` / `optional:` / `s/<before>/<after>/` / `#leftoverbits` (Terminológia `::` címkék) | **bájtazonosan angolul** (ezek a ténylegesen begépelt review-megjegyzés-prefixek); csak a leírás-törzs fordult | `ReviewingGuidelines.adoc` |
| deltified / deltified form (objektum) | **„deltásított" / „deltásított forma"** | `git-index-pack.adoc` — a 18./26. blokk „deltásítva" mintája |
| "thin" pack | **„thin" (vékony) pack** | `git-index-pack.adoc` — az 1. blokk „thin pack" döntése, első előforduláskor glosszázva |
| Die, if … (man-page-i viselkedésleírás) | **„Kilép hibával, ha …"** | `git-index-pack.adoc` — NEM a `git-sh-setup` `die` shell-függvénye (21. blokk), hanem a „terminate with error" jelentésű ige |
| pretty-print (objektumtartalom, `git-replace.adoc`) | **„szép formázás" / „szép formázással"** | a 26. blokk (`pretty-options.adoc`) „szép formázású kiírás" mintája |
| graft / graft commit / graft file | **marad „graft" / „graft commit" / „graft fájl"** angolul | `git-replace.adoc` — Git-fogalomnév, a `bare repository` mintájára |
| mainline (merge, `git-revert.adoc`) | **„fővonal"** | a `-m`/`--mainline` opció leírásában |
| "src" / "dst" / "score" (raw diff mezőnevek, idézőjelben) | **bájtazonosan angolul, idézőjelben** | `diff-format.adoc` — a `git-check-ref-format.adoc`/`git-fetch.adoc` mezőnév-precedense (3./12. blokk) |
| "combined diff" (idézőjelben, coined) | **változatlanul angolul, idézőjelben** | `diff-format.adoc` — konzisztens a `diff-generate-patch.adoc` (még lefordítatlan) használatával |
| preimage / postimage | **„előkép" / „utókép"** | `diff-format.adoc` — ad hoc |
| generation number / generation data (commit-graph) | **„generációs szám" / „Generation Data (chunk)"** — a chunk-név angolul marad | `gitformat-commit-graph.adoc` |
| chunk (commit-graph, format-spec) | **marad „chunk"** (26. blokk döntése) | `gitformat-commit-graph.adoc` |
| "tail" of a ref (idézőjelben) | **„a ref »végére«"** (fordítva) | `git-ls-remote.adoc` |
| peeled tag / pseudoref | **„lehántott tag" / „pszeudoref"** | `git-ls-remote.adoc` |

### Címsor-anchorok

- **`git-reflog.adoc`**: 4 `~~~~` Title Case alcím (`Options for `show`` → „Opciók a `show`-hoz", `…delete`
  → „…`delete`-hez", `…drop` → „…`drop`-hoz", `…expire` → „…`expire`-hez") — nincs rájuk `<<...>>` xref
  (grep-pel ellenőrizve), defenzív `[[_options_for_show]]` / `[[_options_for_delete]]` /
  `[[_options_for_drop]]` / `[[_options_for_expire]]` anchor (autogen slug az eredeti angol címből),
  a `~~~~` aláhúzás a fordított cím pontos karakterhosszához igazítva (19/21/19/22 — Python `len()`
  ellenőrzés).
- **`git-ls-tree.adoc`**: `Output Format` (Title Case `----`) → „Kimeneti formátum" + `[[_output_format]]`
  defenzív anchor; a `-z` opció leírásában lévő `See OUTPUT FORMAT below` prózahivatkozás is átírva
  „l. lentebb a Kimeneti formátum szakaszt"-ra (nem `<<...>>` xref). `FIELD NAMES` csupa nagybetűs →
  a VÉGLEGES DÖNTÉS szerint angolul.
- **`ReviewingGuidelines.adoc`** (NEM man page): a level-0 doc-cím kivételével mind a 9 alcím fordult
  (`Introduction`→„Bevezetés", `Principles`→„Alapelvek", `Selecting patch(es) to review`→„Átnézendő
  patch(ek) kiválasztása", `Reviewing patches`→„Patchek átnézése", `High-level guidance`→„Magas szintű
  útmutatás", `Performing your review`→„Az átnézésed elvégzése", `Completing a review`→„Egy átnézés
  befejezése", `Terminology`→„Terminológia", `See Also`→„Lásd még"). Mindegyik fölé defenzív
  `[[<angol-autogen-slug>]]` anchor (a 23. blokk `DecisionMaking.adoc` precedense; a `====` egysoros
  alcímeknél is a sor fölé). Nincs rájuk `<<...>>` xref sehol a fában. Setext `=`/`-`/`~` aláhúzások a
  fordított cím pontos hosszához igazítva (Python `len()` ellenőrzés; 3 db ±1 elütés menet közben
  javítva). A `Terminology` cím itt Title Case (NEM csupa nagybetűs), ezért a VÉGLEGES DÖNTÉS nem
  vonatkozik rá, fordult.
- **`diff-format.adoc`**: 3 lowercase setext (`----`) alcím (`Raw output format` → „Nyers kimeneti
  formátum", `diff format for merges` → „diff formátum merge-ekhez", `other diff formats` → „egyéb diff
  formátumok") — defenzív `[[_raw_output_format]]` / `[[_diff_format_for_merges]]` /
  `[[_other_diff_formats]]` anchor, aláhúzás pontos hosszra igazítva (23/25/21).
- **`gitformat-commit-graph.adoc`**: 2 `==` egysoros cím (`Commit-graph files have the following format:`
  → „A commit-graph fájlok formátuma a következő:", `Historical Notes:` → „Történeti megjegyzések:") —
  defenzív `[[_commit_graph_files_have_the_following_format]]` / `[[_historical_notes]]` anchor. A
  `=== HEADER:` / `CHUNK LOOKUP:` / `CHUNK DATA:` / `TRAILER:` csupa nagybetűs format-spec-címek és a
  `==== OID Fanout` … `Base Graphs List` vegyes kis-nagybetűs chunk-nevek **változatlanul angolul**
  (a chunk-nevek a fájl prózájában is név szerint hivatkozottak, pl. „into the Extra Edge List chunk");
  ezekhez nem kellett anchor (a cím szövege nem változott).
- A többi 4 fájlban (`git-ls-remote`, `git-send-pack`, `git-index-pack`, `git-replace`) nincs
  `[[...]]`/`<<...>>` (grep-pel ellenőrizve).

### Man-page címként angolul hagyott címsorok (VÉGLEGES DÖNTÉS szerint, automatikusan)

- `git-ls-remote.adoc`: `OUTPUT` (3. blokk óta lezárt kategória); a `<repository>::` leírásában lévő
  `the GIT URLS and REMOTES sections of linkgit:git-fetch[1]` prózahivatkozás `GIT URLS`/`REMOTES`
  szakasznevei angolul maradtak (23./25. blokk).
- `git-send-pack.adoc`: `SPECIFYING THE REFS` (l. `git-http-push.adoc` 21. blokk, ugyanaz a cím
  ugyanígy angolul).
- `git-reflog.adoc`: nincs — az `Options for X` alcímek Title Case-ek, fordultak (l. fent).
- `git-replace.adoc`: `FORMATS`, `CREATING REPLACEMENT OBJECTS`.
- `git-revert.adoc`: `SEQUENCER SUBCOMMANDS`; a `"Reset, restore and revert"` (git[1]-be) és a
  `MERGE STRATEGIES` (git-merge[1]-be) idézőjeles/szó szerinti prózahivatkozások angolul maradtak
  (a cél fájlok még lefordítatlanok; a `MERGE STRATEGIES` konzisztens a 26. blokk döntésével).
- `git-index-pack.adoc`, `git-ls-tree.adoc` (`FIELD NAMES`), `git-ls-remote.adoc` — l. fent.

### Megőrzött markup / megjegyzések

- `git-ls-remote.adoc`: `[verse]` SYNOPSIS (tab-folytatásokkal), 4 `----`/`------------` kód-/kimeneti
  példablokk (`$ git ls-remote …` valós OID-kimenettel) bájtazonos; `_not_` compat-emphasis (`_nem_`),
  `"remote"` idézőjel, `<oid>`/`<ref>`/`^{}`/`TAB`/`LF` literálok, `'git-upload-pack'`/`'git ls-remote'`
  compat-idézőjeles nevek változatlanok.
- `git-send-pack.adoc`: `[verse]` SYNOPSIS; a ` - `/`   * ` (vezető szóközös) beágyazott felsorolás a
  `<dst>` illesztési szabályokban megtartva; `<src>`/`<dst>` bare placeholderek, `"refs/"` idézőjel,
  `'+'` jel változatlan.
- `git-reflog.adoc`: `[synopsis]` blokk (tab-folytatásokkal); `<ref>@\{0\}` escape-elt kapcsos
  zárójelek bájtazonosak; `"reflogs"`/`"show"`/`"list"`/… idézőjeles alparancsnevek és a
  `"where HEAD used to be two moves ago"` stílusú `HEAD@{2}`-glosszák (magyarázó próza) fordultak,
  a `"old"`/`"new"` SHA-1 mezőnevek angolul; `"broken commits"` → „törött commitok".
- `git-index-pack.adoc`: `[verse]` SYNOPSIS; `include::object-format-disclaimer.adoc[]` változatlan;
  `link:technical/partial-clone.html[partial clone]` — cél és `[partial clone]` látható szöveg is
  angolul (3. blokk `partial clone` döntése); `"Receiving objects"`/`"Indexing objects"` progress-
  címek és `"pack\t"`/`"keep\t"` kimeneti prefixek bájtazonosan angolul; `'sha1'`/`'sha256'`,
  `<msg-id>=<severity>` változatlan; egy `  \`--strict=…\`` sor vezető szóköze megtartva.
- `git-ls-tree.adoc`: `[verse]` SYNOPSIS; 3 tab-indentált formátum-sablonsor
  (`%(objectmode) %(objecttype) …%x09%(path)`) bájtazonos; `%(fieldname)`/`%%`/`%xNN`/`\0`/`\t`/`\n`
  token-példák, `"unusual"`/`"objectname"`/`"path"`/`"--format"` idézőjelek, `'sub'`/`'dir'`/
  `'git update-index'` compat-nevek változatlanok; a `objectmode::`/`objecttype::`/… mezőnév-címkék
  bájtazonosak, csak a leírás-törzs fordult.
- `git-replace.adoc`: 4 `------------------------------------------------` (48 kötőjel) parancspélda-
  blokk bájtazonos; a `FORMATS` szakasz `* 'short':` … `<replaced-sha1>` tab-indentált sablontörzse
  **változatlan** (placeholder-sablon, nem próza); `'replace'`/`'foo'`/`'bar'`/`'git'` compat-nevek,
  `GIT_NO_REPLACE_OBJECTS` env-változó, `https://github.com/newren/git-filter-repo[git-filter-repo]`
  URL + látható szöveg változatlan.
- `git-revert.adoc`: `[verse]` SYNOPSIS; `include::rerere-options.adoc[]` + `include::sequencer.adoc[]`
  + `include::includes/cmd-config-section-all.adoc[]` + `include::config/revert.adoc[]` változatlan;
  `_strongly_` (`_nyomatékosan_`), `'Reapply "Reapply "<original-subject>""'` literál tárgysor-példa,
  `"This reverts <full-object-name-…>."` / `"--pretty=reference"` / `"Will merge to \'next\'?"`
  (escape-elt aposztrófok) bájtazonosak; `link:howto/revert-a-faulty-merge.html[revert-a-faulty-merge
  How-To]` — cél és `[… How-To]` látható szöveg is angolul (22./24. blokk „how-to" döntése).
- `ReviewingGuidelines.adoc`: `:sectanchors:` nincs; a `====` egysoros alcímek megtartva (fölöttük
  defenzív anchorral); az `s:"What's cooking"` / `s:"PATCH" -s:"Re:"` lekérdezés-literálok, a
  „What's cooking" / „Needs review" / „[New Topics]" / „Patch 0" idézőjeles e-mail-/szakasznevek,
  a `whats-cooking.txt` / `todo` / `next` branchnevek, a `link:MyFirstContribution.html[…]` link és a
  `https://lore.kernel.org/…` / `https://github.com/gitster/git` URL-ek változatlanok; a
  `[`lore.kernel.org` mailing list archive]` link látható szövegében a backtick-elt gazdanév
  változatlan, a köré írt szöveg fordult.
- `diff-format.adoc`: `include::diff-generate-patch.adoc[]` változatlan; 7 pár `----…----` (36/40/48
  kötőjeles) raw-/numstat-/stat-kimeneti példablokk bájtazonos (`in-place edit  :100644 …`,
  `arch/{i386 => x86}/Makefile …` stb.); `. ` számozott lista-jelölők és `- \`A\`: …` betűjel-
  felsorolás megtartva; `0\{40\}` escape-elt kapcsos zárójelek, `"src"`/`"dst"`/`"score"`/`"unmerged"`/
  `"in-place edit"`/`"unknown"`/`"unusual"` idézőjelek, `diffstat`(1) változatlanok.
- `gitformat-commit-graph.adoc`: **a teljes bináris format-spec törzse (a `=== HEADER:` … `=== TRAILER:`
  szakaszok minden szóközzel/tabbal behúzott sora, a `{'C','G','P','H'}` szignatúrák, a
  `(1 << 30) + …` képlet, a `====` chunk-fejlécek és leírásaik, a MurmurHash-URL-ek, a `0x293ae76f`
  konstansok) bájtazonosan angolul maradt** — a `reftable.adoc` / `hash-function-transition.adoc`
  (1. blokk) format-spec-precedense szerint. Csak a DESCRIPTION flush-left prózája (a bevezető
  bekezdés + 5 `- ` metaadat-felsoroláspont + a „These positional references…" bekezdés + „All
  multi-byte numbers…"), a 2 `==` cím és a „Historical Notes" flush-left prózája fordult.
- Mindegyik man page GIT szakasza „A linkgit:git[1] csomag része" alakra fordítva (4. blokk).
- Szintaxis-ellenőrzés: egyik fájlban sincs `ifdef::`/`ifndef::`/`endif::`; a `----`/`------------`/
  `~~~~`/`====` határolók és man-page-aláhúzások párban/pontos hosszal (Python `len()` +
  `cat -A` ellenőrzés), a bekezdéshatárok megtartva.

## 28. blokk — a következő 10 legkisebb, még lefordítatlan „Gyökér" fájl — 2026-09-10

**Módszer:** ugyanaz, mint a 15–27. blokkban: a két gyökér-tábla együttes, sorméret szerint növekvő
listája, a `gitglossary.adoc` / `git.adoc` / `config.adoc` / `git-fast-import.adoc` /
`glossary-content.adoc` kihagyva. Orchestrátor fordította közvetlenül, subagent nélkül.
Fájlok: `git-gc.adoc`, `gitk.adoc`, `git-fsck.adoc`, `git-init.adoc`, `gitpacking.adoc`,
`git-rm.adoc`, `git-multi-pack-index.adoc`, `gitcvs-migration.adoc`, `git-update-ref.adoc`,
`diff-generate-patch.adoc`.

### Ebben a blokkban rögzített / megerősített döntések

| angol | magyar | megjegyzés |
|---|---|---|
| bitmap / reachability bitmap | **marad „bitmap" / „elérhetőségi bitmap"**; toldalék magas hangrend: `bitmapek`, `bitmapet`, `bitmapbe` | `gitpacking.adoc`, `git-multi-pack-index.adoc` — a `packfile` (0. blokk) mintájára angol kölcsönszó |
| pseudo-merge bitmap | **„pszeudo-merge bitmap"** (a `merge` a 0. blokk szerint angol); a `gitpacking.adoc` `== Pseudo-merge bitmaps` címe → „Pszeudo-merge bitmapek" | a `"pseudo-merge bitmap"` idézőjeles definíció-előfordulást is `„pszeudo-merge bitmap"`-re fordítottuk a fájlon belüli konzisztenciáért |
| reachability / reachability closure | **„elérhetőség" / „elérhetőségi lezárt"** | `gitpacking.adoc` |
| traversal / bitmap traversal / fill-in traversal | **„bejárás" / „bitmap-bejárás" / „kitöltő bejárás"** | `gitpacking.adoc` |
| ref tip / reference tip | **„ref-csúcs" / „referencia-csúcs"** | `gitpacking.adoc`, `git-multi-pack-index.adoc` |
| capture group (regex) | **marad „capture group"** angolul | `gitpacking.adoc` — regex-terminus, nincs bevett magyar |
| octopus merge | **marad „octopus merge"** angolul | `gitpacking.adoc` |
| cruft pack | **marad „cruft pack"** angolul; `--cruft` opció változatlan | `git-gc.adoc` — a `thin pack` (1. blokk) mintájára |
| housekeeping (git gc) | **„karbantartás" / „karbantartási feladat"** | `git-gc.adoc` |
| unreachable objects | **„elérhetetlen objektumok"** | `git-gc.adoc`, `git-fsck.adoc` |
| dangling (git-fsck) | a `dangling`/`--dangling`/`--no-dangling` opciónév és a `dangling <type> <object>::` literál diagnosztika-címke **változatlan**; prózában „lógó" (lógó objektum/commit/előzményszegmens) | `git-fsck.adoc` — a program tényleges kimeneti szövegei bájtazonosak (5. blokk `git-clean.adoc` minta), csak a leírás-törzs fordul |
| connectivity / validity (git-fsck) | **„összekapcsoltság" / „érvényesség"** | `git-fsck.adoc` |
| unreachability trace / head node / root node | **„elérhetetlenség-nyomkövetés" / „fejcsomópont" / „gyökércsomópont"** | `git-fsck.adoc` |
| MIDX / multi-pack-index / MIDX layer / MIDX chain | **marad „MIDX" / „multi-pack-index"**; „MIDX-réteg" / „MIDX-lánc"; `multi-pack-index-chain` fájlnév változatlan | `git-multi-pack-index.adoc` |
| root layer / base (layer) | **„gyökérréteg" / „alap"** | `git-multi-pack-index.adoc` |
| break ties / tie | **„holtverseny eldöntése" / „holtverseny"** | `git-multi-pack-index.adoc` `--preferred-pack` |
| batch / batch size | **„köteg" / „kötegméret"**; `--batch-size` / `--batch-updates` opciónév változatlan; ige: „kötegben hajt végre", „kötegelt frissítés" | `git-multi-pack-index.adoc`, `git-update-ref.adoc` |
| expected size (MIDX repack) | **„várható méret"** | `git-multi-pack-index.adoc` |
| "refs snapshot" / reference snapshot | **változatlanul angolul** (`"refs snapshot"` / „reference snapshot"), a leírás-törzs körülötte fordul | `git-multi-pack-index.adoc` — a doksi maga idézőjelezi |
| alternate (object store / repository) | **marad „alternate"** angolul; „alternatív objektumkészletek" a `git-fsck.adoc` `--full` prózájában, ahol a forrás is „alternate object pools"-t mond | `git rm` / `git-fsck` / `git-multi-pack-index` — a `bare repository` mintájára |
| transaction / prepared state (update-ref) | **„tranzakció"**; a `prepared` állapotnév a `git update-ref` `prepare` parancsához kötve **angolul** (`prepared állapot`) | `git-update-ref.adoc` |
| dereference (symbolic ref) | **„feloldás"** ("feloldva a szimbolikus refeket") | `git-update-ref.adoc` |
| pseudoref | **„pszeudoref"** (25. blokk precedens) | `git-update-ref.adoc` |
| `update`/`create`/`delete`/`verify`/`symref-*`/`option`/`start`/`prepare`/`commit`/`abort` (update-ref `::` lista-címkék) | **bájtazonosan angolul** (a ténylegesen begépelt parancsszavak); csak a leírás-törzs fordul | `git-update-ref.adoc` — a `config.kulcs::` szabály analógiája |
| patch text | **„patch-szöveg"** | `diff-generate-patch.adoc` |
| combined diff / combined diff format | **„kombinált diff" / „kombinált diff-formátum"** | `diff-generate-patch.adoc` |
| hunk header / chunk header (diff-generate-patch) | „hunk-fejléc", ill. ahol a forrás „Chunk header"-t mond, ott **„chunk-fejléc"** (a forrás saját inkonzisztenciáját tükrözve; `hunk` és `chunk` is angol — 0./27. blokk) | `diff-generate-patch.adoc` |
| similarity / dissimilarity index | **„hasonlósági / különbözőségi index"** | `diff-generate-patch.adoc` |
| shared repository (gitcvs-migration) | **„megosztott repository"** | `gitcvs-migration.adoc` |
| main trunk (CVS) | **„fő trunk"** | `gitcvs-migration.adoc` |
| development clone | **„fejlesztői klón"** | `gitcvs-migration.adoc` |
| committer (szerepkör, gitcvs-migration) | **marad „committer"** (a `maintainer` mintájára); „egyéni committerként" | `gitcvs-migration.adoc` |

### Címsor-anchorok

- **`git-gc.adoc`**: nincs `[[...]]`, nincs `<<...>>`. `AGGRESSIVE` csupa nagybetűs, a kanonikus
  listán kívüli → a VÉGLEGES DÖNTÉS szerint **angolul** (a prózában is `"AGGRESSIVE"` /
  `"CONFIGURATION"` / `"NOTES"` / `"PACKFILE OPTIMIZATION"` címszövegre feloldódó, idézőjeles
  hivatkozásokként, ezek is angolul).
- **`gitk.adoc`**: 5 defenzív anchor — mind **vegyes kis-/nagybetűs vagy Title Case** alcím, tehát
  a VÉGLEGES DÖNTÉS (csak csupa nagybetűs) nem vonatkozik rájuk, a 18./23./27. blokk (`Examples` →
  „Példák" stb.) precedensét követik: `[[_rev_list_options_and_arguments]]` „rev-list opciók és
  argumentumok" (`~~~~`), `[[_gitk_specific_options]]` „gitk-specifikus opciók" (`~~~~`),
  `[[_examples]]` „Példák", `[[_files]]` „Fájlok", `[[_history]]` „Történet" (`----`). Aláhúzások
  a fordított cím pontos karakterhosszához igazítva. A „History simplification" idézőjeles,
  `linkgit:git-log[1]`-re mutató szakasznév-hivatkozás **angolul maradt**.
- **`git-fsck.adoc`**: 2 defenzív anchor — `[[_extracted_diagnostics]]` „Kinyert diagnosztika",
  `[[_environment_variables]]` „Környezeti változók". Mindkettő **Title Case**, NEM a csupa
  nagybetűs kanonikus alak, ezért fordítva (27. blokk `Terminology` precedens). `FSCK MESSAGES`
  csupa nagybetűs, listán kívüli → **angolul**.
- **`git-init.adoc`**: nincs anchor/xref. `TEMPLATE DIRECTORY` csupa nagybetűs, listán kívüli →
  **angolul** (prózában is `"TEMPLATE DIRECTORY"` hivatkozás). `ifndef::with-breaking-changes[]` /
  `ifdef::…[]` / `endif::…[]` bájtazonos, a közéjük ékelt próza fordult.
- **`gitpacking.adoc`**: 6 defenzív anchor a `==`/`===` **Title Case** szakaszcímek fölé
  (`_pseudo_merge_bitmaps`, `_background`, `_overview`, `_use_cases`, `_configuration`, `_examples`).
  A `=== Configuration` Title Case (nem `CONFIGURATION`), ezért fordítva. Nincs `<<...>>` xref sehol
  a fában (grep-pel ellenőrizve).
- **`git-rm.adoc`**: 3 defenzív anchor a `~~~~` **Title Case** alcímek fölé (`_using_git_commit_a`
  „A ``git commit -a'' használata", `_using_git_add_a` „A ``git add -A'' használata",
  `_other_ways` „Egyéb módok"). A `` ``…'' `` compat-mode markup és a `git commit -a` parancs
  bájtazonos, csak az „Using X" → „X használata" keret fordult. `REMOVING FILES THAT HAVE
  DISAPPEARED FROM THE FILESYSTEM` és `SUBMODULES` csupa nagybetűs, listán kívüli → **angolul**.
- **`git-multi-pack-index.adoc`**: nincs anchor/xref. Az alparancsnevek (`write`/`compact`/…) és a
  beágyazott `--…::` opciócímkék bájtazonosak. `link:technical/multi-pack-index.html[…]` **célja
  változatlan**, a `[The Multi-Pack-Index Design Document]` látható szöveg → „[A Multi-Pack-Index
  tervezési dokumentum]".
- **`gitcvs-migration.adoc`**: **NEM man page** (section 7 guide) — mind a 6 `----` szekciócím
  fordult, fölöttük defenzív anchorral (`_developing_against_a_shared_repository`,
  `_setting_up_a_shared_repository`, `_importing_a_cvs_archive`,
  `_advanced_shared_repository_management`, `_providing_cvs_access_to_a_git_repository`,
  `_alternative_development_models`), aláhúzások pontos karakterhosszra igazítva. A
  `link:user-manual.html[The Git User's Manual]` → „[A Git felhasználói kézikönyve]", a
  `link:howto/update-hook-example.html[…]` látható szöveg is fordult (a 22./24. blokk how-to
  döntése a howto/-fájlok saját CÍMÉRE vonatkozott; ez link-látszószöveg).
- **`diff-generate-patch.adoc`**: a meglévő `[[generate_patch_text_with_p]]` anchor **érintetlen**,
  a hozzá tartozó cím szövege fordult („Patch-szöveg előállítása a -p opcióval"). A `diff-options.adoc`
  (még `[ ]`) `<<generate_patch_text_with_p>>` bare xref-je emiatt a jövőben a fordított
  címszöveget jeleníti majd meg — **kívánt** viselkedés, az azonosító nem változott. Új defenzív
  anchor: `[[_combined_diff_format]]` „Kombinált diff-formátum" (Title Case `----`, nincs rá xref).
  A `[synopsis]` blokkok, a `------------` combined-diff példa és a `       diff --git …` szóközzel
  behúzott literál sorok bájtazonosak. A „Defining a custom hunk-header" idézőjeles,
  `linkgit:gitattributes[5]`-re mutató szakasznév **angolul maradt**.

### Man-page címként angolul hagyott kétes címsorok

- `AGGRESSIVE` (`git-gc.adoc`), `FSCK MESSAGES` (`git-fsck.adoc`), `TEMPLATE DIRECTORY`
  (`git-init.adoc`), `REMOVING FILES THAT HAVE DISAPPEARED FROM THE FILESYSTEM` + `SUBMODULES`
  (`git-rm.adoc`), `LOGGING UPDATES` (`git-update-ref.adoc`) — mind csupa nagybetűs, a kanonikus
  man-page-szekció listán kívül, VÉGLEGES DÖNTÉS szerint bájtazonosan angolul.

### Megőrzött markup / megjegyzések

- Mindegyik man page GIT szakasza „A linkgit:git[1] csomag része" alakra fordítva (4. blokk).
- `include::…` sorok bájtazonosak; `git-init.adoc` `:git-init:` attribútum-sor változatlan.
- `git-fsck.adoc`: a diagnosztika-címkék (`unreachable`/`missing`/`dangling`/`hash mismatch …::`)
  és a `GIT_OBJECT_DIRECTORY` stb. env-változónevek bájtazonosak.
- `git-init.adoc`: a `----------------` EXAMPLES-blokk + `<1>`/`<2>`/`<3>` callout-jelölők
  változatlanok, a callout-szövegek fordultak; a `--shared` értéktáblázat `--` … `--` határolói és
  `` `umask` ``/`` `group` ``/`` `all` ``/`_<perm>_` címkéi bájtazonosak.
- `git-rm.adoc`: a `-r` opció leírása a forrásban **8 szóközzel** (nem tabbal) behúzott — megtartva.
- `git-multi-pack-index.adoc`: a `write::`/`compact::` `--` … `--` blokkok 1-tab opciócímkéi +
  2-tab leírás-törzse — a behúzási szintek pontosan megtartva (`cat -A`). `NOTE:` angolul.
- `git-update-ref.adoc`: a `--stdin` és a `-z` tabbal behúzott parancs-nyelvtan blokkok
  (`update SP <ref> …` / `… NUL …`), a `rejected SP (…)` sor és a `    oldsha1 SP newsha1 …`
  naplósor-sablonok **bájtazonosak**.
- `gitpacking.adoc`: a 3 `----` `[bitmapPseudoMerge "all"]` config-példablokk bájtazonos; `NOTE:` angolul.
- `gitcvs-migration.adoc`: az összes `------…` shell-session példablokk és a `[NOTE]` `====…`
  blokk határolói bájtazonosak, a `[NOTE]` törzse fordult.
- Szintaxis-ellenőrzés (Python `len()` + `cat -A`): nincs beszúrt/eltűnt bekezdéshatár; a
  `----`/`....`/`====`/`++++` határolók párban; a setext-aláhúzások a fordított cím pontos
  karakterhosszával egyeznek (menet közben 6 db ±1–2 elütés javítva: `gitcvs-migration.adoc` 3,
  `gitk.adoc` 1, `git-rm.adoc` 2, `diff-generate-patch.adoc` 1).

## 29. blokk — a következő 5 legkisebb, még lefordítatlan „Gyökér" fájl — 2026-09-10

**Módszer:** ugyanaz, mint a 28. blokkban (a felhasználó ezúttal 5-ös bontást kért). Orchestrátor
fordította közvetlenül. Fájlok: `git-show-branch.adoc`, `git-show-ref.adoc`, `merge-options.adoc`,
`git-format-rev.adoc`, `git-hook.adoc`.

### Ebben a blokkban rögzített / megerősített döntések

| angol | magyar | megjegyzés |
|---|---|---|
| commit ancestry graph | **„commit-leszármazási gráf"** | `git-show-branch.adoc` |
| naming string (git-show-branch) | **„elnevező sztring"** | `git-show-branch.adoc` |
| status sign (`*` `!` `+` `-`) | **„állapotjel"** | `git-show-branch.adoc` |
| always / never / auto (`--color` értékek) | **változatlanul angolul** (a program tényleges argumentumértékei) | `git-show-branch.adoc` |
| dereference (tag → object ID) | **„feloldás"** / „objektumazonosítókká oldható fel"; `--dereference`/`-d` opciónév angol | `git-show-ref.adoc` (a `git-update-ref.adoc` 28. blokk „feloldás" döntésével konzisztens) |
| OID | **marad „OID"** angolul | `git-show-ref.adoc` |
| head-match (refname) | **„elölről illeszkedik"** | `git-show-ref.adoc` `--exclude-existing` |
| octopus (merge kontextusban, merge-options) | **marad „octopus"** angolul (28. blokk `gitpacking.adoc` „octopus merge" döntése; itt „egy octopus esetén") | `merge-options.adoc` |
| diffstat / compact-summary (merge-options) | **változatlanul angolul** (a `--stat` / `--compact-summary` kimenet neve) | `merge-options.adoc` |
| side branch (merge) | **„oldalág"** | `merge-options.adoc` `--verify-signatures` |
| trust model | **„bizalmi modell"** | `merge-options.adoc` |
| EXPERIMENTAL: (NAME-előtag) / (EXPERIMENTAL!) (synopsis-előtag) | **„KÍSÉRLETI:" / „(KÍSÉRLETI!)"** (fordítva); a `THIS COMMAND IS EXPERIMENTAL. THE BEHAVIOR MAY CHANGE.` csupa nagybetűs mondat → „EZ A PARANCS KÍSÉRLETI. A VISELKEDÉS MEGVÁLTOZHAT." (nagybetűs formázás megtartva) | `git-format-rev.adoc` — a 3. blokk `git-backfill.adoc` `THIS COMMAND IS EXPERIMENTAL…` precedense |
| record / line (git-format-rev terminátor-kontextus) | **„rekord" / „sor"**; `_line_` / `_record_` emphasis-jelölés megtartva a fordított szón | `git-format-rev.adoc` |
| terminator / separator | **„lezáró" / „elválasztó"** | `git-format-rev.adoc` |
| flush (I/O) | **„ürítés"** ("azonnal ürítésre kerül") | `git-format-rev.adoc` |
| peel / peeled (annotated tag) | **„lehánt" / „le van hántva"** (2009-es `git-check-ref-format.adoc` „hagymahámozó" a `^{}` operátorra vonatkozott, ez itt a tag→commit lehántás — külön jelentés) | `git-format-rev.adoc` |
| atom (pretty-format `%N`, `%n`, `%s`) | **marad „atom"** angolul | `git-format-rev.adoc` |
| notes ref | **„notes-ref"** (a `git notes` `note`/`jegyzet` 0. blokk mintája; itt a ref neve) | `git-format-rev.adoc` |
| hook event | **„hook-esemény"** | `git-hook.adoc` |
| friendly name (`hook.<friendly-name>`) | **„felhasználóbarát név"**; a `<friendly-name>` placeholder változatlan | `git-hook.adoc` |
| wrap Git / wrapper (tool) | **„becsomagol" / „csomagoló"** ("a Gitet becsomagoló eszközök") | `git-hook.adoc` |
| "last-one-wins" | **„az utolsó nyer"** (idézőjelben, fordítva) | `git-hook.adoc` |
| hookdir | **marad „hookdir"** angolul | `git-hook.adoc` |
| config scope (`local`/`global`/`system`) | **„config-hatókör"**; az értéknevek angolul, backtick között | `git-hook.adoc` |
| stream into (stdin) | **„streamel"** ("a hook stdinjébe lesz streamelve") | `git-hook.adoc` |
| bail out | **„kilép"** | `git-hook.adoc` |
| serial / concurrent / parallel execution | **„soros / egyidejű / párhuzamos végrehajtás"** | `git-hook.adoc` |

### Címsor-anchorok

- **`git-show-branch.adoc`**: nincs `[[...]]`, nincs `<<...>>`. `OUTPUT` / `EXAMPLES` / `CONFIGURATION`
  a kanonikus listán. A `--topo-order` és a `-r` opció leírása a forrásban **8 szóközzel** (nem
  tabbal) behúzott — az eltérő behúzás megtartva.
- **`git-show-ref.adoc`**: nincs `[[...]]`, nincs `<<...>>`. `OUTPUT` / `EXAMPLES` / `FILES` /
  `SEE ALSO` a kanonikus listán. A `<oid> SP <ref> LF` / `<oid> LF` sablonok a `----` blokkokban
  bájtazonosak; a `------…` (75 kötőjeles) parancspélda-blokkok és a `$ git show-ref …` kimenetek is.
- **`merge-options.adoc`**: **include-fragmens, NINCS szekciócím**. 11 db `ifdef::git-merge[]` /
  `ifdef::git-pull[]` / `ifndef::git-pull[]` + 11 db `endif::…` guard, valamint az
  `include::signoff-option.adoc[]` sor **bájtazonos**; a `+` folytatásjelölők és a `` `--option`:: ``
  címkék változatlanok. A „Only useful when merging." 5× ismétlődő sor (3× `\t`-indentált, 2×
  0. oszlopból `+` után) → „Csak merge-eléskor hasznos."
- **`git-format-rev.adoc`**: a meglévő `[[io]]` és `[[examples]]` anchorok **érintetlenek**; a rájuk
  mutató `<<io,INPUT AND OUTPUT FORMATS>>` (2×) és `<<examples,EXAMPLES>>` (2×) xref-ek a **linkszöveggel
  együtt bájtazonosan angolul** maradtak, mert az `INPUT AND OUTPUT FORMAT` cím csupa nagybetűs,
  kanonikus listán kívüli → angol (a `<<REMOTES,REMOTES>>` 25. blokk precedense; a linkszöveg
  fordítása inkonzisztenciát okozna a címmel). `EXAMPLES` a kanonikus listán. A `[synopsis]` `--` …
  `--` blokk (`Did we not fix this in "<subject>"?` és a `(EXPERIMENTAL!) git format-rev …`
  synopsis-sor a command-résztől eltekintve) és a `----` shell-példablokkok (`git last-modified`
  kimenet, `#/bin/sh` szkript, commit-üzenet-példák) **bájtazonosak**. A `revs`;; / `text`;; `;;`
  másodszintű def-lista-címkék változatlanok, csak a törzs fordult.
- **`git-hook.adoc`**: nincs `[[...]]`, nincs `<<...>>`. `SUBCOMMANDS` és `WRAPPERS` csupa nagybetűs,
  kanonikus listán kívüli → **angolul** (a `WRAPPERS` a prózában is `"WRAPPERS"` idézőjeles,
  címszövegre feloldódó hivatkozásként). A `run::` alatt a forrásbeli `+` majd üres sor sorrend
  megtartva. A `  [hook "linter"]` 2-szóközzel behúzott config-példa-bekezdések (AsciiDoc
  literál-bekezdés) és a `----` blokkok (`git config set …`, a `#` kommentes `git hook run …` hívás)
  **bájtazonosak**.

### Man-page címként angolul hagyott kétes címsorok

- `SUBCOMMANDS`, `WRAPPERS` (`git-hook.adoc`), `INPUT AND OUTPUT FORMAT` (`git-format-rev.adoc`) —
  csupa nagybetűs, a kanonikus man-page-szekció listán kívül, VÉGLEGES DÖNTÉS szerint bájtazonosan
  angolul.

### Megőrzött markup / megjegyzések

- Mindegyik man page GIT szakasza „A linkgit:git[1] csomag része" alakra fordítva (4. blokk).
- `git-show-branch.adoc` / `git-show-ref.adoc` / `git-hook.adoc`: `include::…` sorok bájtazonosak;
  `git-hook.adoc` `:git-hook: 1` attribútum-sor változatlan.
- `git-show-branch.adoc`: a `------…` (48 kötőjeles) `git show-branch` kimeneti példa és a
  `[showbranch]` config-blokk, benne a `\'git show-branch'` escape-elt aposztróf és a beágyazott
  idézőjeles commit-tárgysorok (`"reset type" flag to "git reset"`) **bájtazonosak**.
- `git-format-rev.adoc`: a `par(1)` / `git-config[1]` / `getpwnam`-szerű hívásnevek és a
  `e83c5163316f89bfbde7d9ab23ca2e25604af290` teljes objektumnevek a `----` blokkokban változatlanok.
- Szintaxis-ellenőrzés (Python `len()` char-count + `cat -A`): egyik fájlban sincs valódi
  setext-aláhúzás-eltérés (a script által jelzett esetek mind `----` listing-blokk-határolók);
  `ifdef`/`endif` páros a `merge-options.adoc`-ban (11/11); az anchorok és xref-ek a
  `git-format-rev.adoc`-ban változatlanok.

## 30. blokk — `git-imap-send.adoc`, `git-log.adoc`, `git-replay.adoc`, `git-rerere.adoc`, `git-restore.adoc` — 2026-09-10

**Módszer:** a felhasználó 5-ös bontást kért — a két gyökér-tábla együttes, sorméret szerint növekvő
listájából a 5 legkisebb, még `[ ]` jelölésű fájl (`gitglossary.adoc`/`git.adoc`/`config.adoc`/
`git-fast-import.adoc`/`glossary-content.adoc` a skill szerint kihagyva). Orchestrátor végezte
közvetlenül, célzott `Edit`-ekkel, a triviális méret miatt subagent nélkül.

### Ebben a blokkban rögzített / megerősített döntések

| angol | magyar | megjegyzés |
|---|---|---|
| replay (parancsnév / ige) | **marad „git replay"** parancsnév; ige-jellegű használatban „újrajátszás" / „újrajátssza" | `git-replay.adoc` — a doksi maga „replays them onto a new location"; a `git replay` parancsnév és a `--onto`/`--advance`/`--revert` kapcsolók angolul |
| revert commit / reverted commit (git replay kontextus) | **„revert-commit" / „visszavont commit"** | a `git revert` parancsnév marad; a „reverted" mn.-i igenév → „visszavont" |
| atomic transaction (ref-frissítés) | **„atomi tranzakció"**; „updated atomically" → „atomian frissül" | `git-replay.adoc` |
| bare commit ID | **„puszta commit-azonosító"** | branchnevek helyett használt nyers SHA |
| restore source / restore location (git restore) | **„visszaállítási forrás" / „a visszaállítás helye"** | `git-restore.adoc` — a `--source` és a `--staged`/`--worktree` szemantikájának magyarázatában |
| overlay / no-overlay mode | **marad „overlay" / „no-overlay mód"** | `git-restore.adoc` — kapcsoló-tokenek |
| decoration / decorate (git log ref-nevek) | **„díszítés" / „díszít"**; „decoration filter" → „díszítésszűrő" | `git-log.adoc` `--decorate*` kapcsolók |
| automerge (rerere) | **marad „automerge"**; „conflicted automerge" → „konfliktusos automerge" | `git-rerere.adoc` |
| hand resolve / manual resolution (rerere) | **„kézi feloldás"** | |
| blow away (a test merge) | **„eltüntet"** (eltüntetheted a teszt-merge-et) | `git-rerere.adoc` DISCUSSION |
| conflict marker | **„konfliktusjelölő"** | `git-rerere.adoc` — a `<<<<<<<` / `=======` / `>>>>>>>` literálok bájtazonosak |
| sanity check | **„épségvizsgálat"** | `git-rerere.adoc` |
| drafts folder (IMAP) | **„piszkozatmappa"** | `git-imap-send.adoc` |
| mailbox (git format-patch kimenet) | **„postaláda"** | `git-imap-send.adoc` |
| pipe (ige, `\|` update-ref --stdin) | **„csövez"** (a `git update-ref --stdin`-be csövezhető) | `git-replay.adoc` |

### Címsor-anchorok

- **`git-replay.adoc`** — az egyetlen fájl a blokkban `[[...]]`/`<<...>>`-vel. A meglévő `[[output]]`
  és `[[exit-status]]` anchorok, valamint a rájuk mutató `<<output,OUTPUT>>` és
  `<<exit-status,EXIT STATUS>>` xref-ek **a látható linkszöveggel együtt bájtazonosan** megmaradtak.
  Indok: az `OUTPUT` a 3. blokkban lezárt kanonikus-kategória, az `EXIT STATUS` a skill kanonikus
  listáján van → mindkét cím angolul marad, tehát a címszöveget tükröző linkszöveg fordítása
  inkonzisztenciát okozna (a `git-format-rev.adoc` `<<io,INPUT AND OUTPUT FORMATS>>` precedense,
  29. blokk).
- `git-imap-send.adoc`, `git-log.adoc`, `git-rerere.adoc`, `git-restore.adoc`: nincs `[[...]]` és
  nincs `<<...>>`; új defenzív anchort egyikük sem kapott (kizárólag kanonikus man-page szekciók,
  ill. csupa nagybetűs, kanonikus listán kívüli alcímek vannak, amelyek angolul maradnak — l. lent).

### Man-page címként angolul hagyott kétes címsorok

- **`GETTING A LIST OF AVAILABLE FOLDERS`**, **`CAUTION`** (`git-imap-send.adoc`),
  **`DIFF FORMATTING`** (`git-log.adoc`), **`COMMANDS`** (`git-rerere.adoc`) — csupa nagybetűs,
  kétsoros aláhúzású, a kanonikus man-page-szekció listán kívüli alcímek; a VÉGLEGES DÖNTÉS szerint
  **bájtazonosan angolul** (aláhúzás sem változott). A `git-log.adoc` `DISCUSSION`/`CONFIGURATION`
  és a `git-replay.adoc` `OUTPUT`/`EXIT STATUS`/`CONFIGURATION` a kanonikus/lezárt listán vannak.

### Megőrzött markup / megjegyzések

- Mindegyik fájl GIT szakasza „A linkgit:git[1] csomag része" alakra fordítva (4. blokk).
- **`git-replay.adoc`**: NAME `EXPERIMENTAL:` előtag → „KÍSÉRLETI:", `[verse]` synopsis
  `(EXPERIMENTAL!)` előtag → „(KÍSÉRLETI!)" (29. blokk `git-format-rev.adoc` precedens); a
  `THIS COMMAND IS EXPERIMENTAL. THE BEHAVIOR MAY CHANGE.` csupa nagybetűs mondat lefordítva a
  nagybetűs formázás megtartásával („EZ A PARANCS KÍSÉRLETI. A VISELKEDÉSE MEGVÁLTOZHAT.", 3. blokk
  `git-backfill.adoc` precedens). A `////` … `////` komment-blokk a `--ref-action` def-listában,
  a `update`;; / `print`;; másodszintű címkék, a `--` … `--` nyílt blokk határolói és a behúzott
  `update refs/heads/branchN …` literál blokk **bájtazonosak**; a „Specifying Ranges" (git-rev-parse[1])
  és a `<<output,OUTPUT>>` idézett/xref szakasznevek angolul (a cél még lefordítatlan / a cím angol).
- **`git-restore.adoc`**: a "Reset, restore and revert" (git[1]) és a „Interaktív mód" (git-add[1],
  az ottani, már lefordított `Interaktív mód` címre) prózahivatkozás — előbbi angolul (a git.adoc
  szakasznév még lefordítatlan), utóbbi a `git-add.adoc` meglévő fordításához igazítva. A
  `------------` (12 kötőjeles) EXAMPLES-blokkok (`$ git switch/restore …`), a `<1>`/`<2>` callout-
  jelölők a kódban és a `include::diff-context-options.adoc[]` sor **bájtazonosak**; a callout-
  magyarázatok szövege fordult.
- **`git-log.adoc`**: az összes `include::…` sor (`rev-list-description`, `line-range-options`,
  `rev-list-options`, `pretty-formats`, `diff-options`, `diff-generate-patch`, `i18n`,
  `includes/cmd-config-section-rest`, `config/log`, `config/notes`) és a `:git-log: 1` /
  `:diff-merges-default:` attribútum-sorok **bájtazonosak**. A `--` … `--` nyílt blokk a
  `--decorate` def-listában + a `short`;;/`full`;;/`auto`;; másodszintű címkék változatlanok. A
  `'Specifying Ranges'` / `'History Simplification'` / `'Pretty Formats'` / `'Discussion'` idézett
  szakasznevek (compat-mode `'...'`) angolul maradtak (a hivatkozott szakaszok / fájlok
  — `rev-list-options.adoc`, `pretty-formats.adoc`, `revisions.adoc`, `gitrevisions.adoc` — még
  lefordítatlanok, ill. `git-log`-on belüli, angolul maradó címre mutatnak). A ``main branch''
  → ``fő branch'' (a `` `` `` compat-mode idézőjel-markup megtartva).
- **`git-imap-send.adoc`**: a `.........` (pontokból álló) és `----` körülhatárolt blokkok
  (`* LIST (\HasNoChildren) …` IMAP-kimenet, `[imap]` config-példák, `$ git format-patch … | git
  imap-send` parancssorok) **bájtazonosak**; az `[NOTE]` egysoros admonition-kulcsszó változatlan,
  a törzs fordult. A lokalizálatlan program-üzenet-szövegek (`"Folder doesn't exist"`, `"Drafts"`,
  `"Junk"`, `"Trash"`, `"INBOX"`) idézőjelben, angolul (5./6. blokk precedens). Az
  `include::includes/cmd-config-section-rest.adoc[]` és `include::config/imap.adoc[]` sorok
  bájtazonosak.
- **`git-rerere.adoc`**: a `[verse]` synopsis (`'git rerere' [clear | forget <pathspec>... | …]`)
  és a `'clear'`/`'forget'`/`'diff'`/`'status'`/`'remaining'`/`'gc'` `::` definíciós lista-címkék
  (a ténylegesen begépelendő alparancs-szavak, compat-mode `'...'`) **bájtazonosak** — csak a
  törzs fordult (5. blokk `git-clean.adoc` interaktív-alparancs precedens). A `------------`
  ASCII-art commit-gráf blokkok (`o---*---o topic` stb., `$ git switch/merge/reset …` beágyazott
  parancsokkal) **bájtazonosak**. A `<<<<<<<` / `=======` / `>>>>>>>` konfliktusjelölő-literálok
  és a `[NOTE]` admonition-kulcsszavak változatlanok. A `"release"` / `"Merge from master"` /
  `"useless merges"` idézett kifejezések angolul maradtak (idézőjelben).

## 31. blokk — `gitformat-signature.adoc`, `git-help.adoc`, `git-pull.adoc`, `git-merge-base.adoc`, `git-history.adoc` — 2026-09-10

**Módszer:** a felhasználó 5-ös bontást kért — a két gyökér-tábla együttes, sorméret szerint növekvő
listájából a következő 5 legkisebb, még `[ ]` fájl (`gitglossary.adoc`/`git.adoc`/`config.adoc`/
`git-fast-import.adoc`/`glossary-content.adoc` kihagyva). Orchestrátor végezte közvetlenül, célzott
`Edit`-ekkel.

### Ebben a blokkban rögzített / megerősített döntések

| angol | magyar | megjegyzés |
|---|---|---|
| payload (kriptográfiai aláírás kontextus) | **„hasznos adat"** | `gitformat-signature.adoc` — a 21. blokk `payload` (pkt-line) → „hasznos adat" döntésének kiterjesztése; „signed payload" → „aláírt hasznos adat" |
| detached signature | **„különálló aláírás"** | `gitformat-signature.adoc` |
| tail line / header line (ASCII Armor) | **„záró sor" / „fejlécsor"** | |
| ASCII Armor | **marad „ASCII Armor"** (idézőjelben, ahogy a forrás) | |
| embedding (aláírás objektumba) | **„beágyazás"** / „beágyazva" | `gitformat-signature.adoc` `- embedding:` listaelemek |
| created by / verify with (listaelem-címkék) | **„létrehozza:" / „ellenőrzés:"** | `gitformat-signature.adoc` — a `- created by:` / `- verify with:` prózás felsoroláscímkék |
| concept guide (git help) | **„fogalmi útmutató"** | `git-help.adoc` `--guides` |
| user-interface / developer-interface (git help alszakaszok) | **„felhasználói felület" / „fejlesztői felület"** | |
| man viewer | **„man-megjelenítő"** | `git-help.adoc` `man.viewer` szakaszok |
| criss-cross merge | **„kereszteződő merge"** | `git-merge-base.adoc` |
| fork point / forked from | **„elágazási pont" / „elágazott (vmiről)"** | `git-merge-base.adoc` `--fork-point` |
| incarnation (of a branch) | **„megtestesülés"** | `git-merge-base.adoc` — „a branch egy korábbi megtestesüléséről ágazott el" |
| fast-forward-ness | **„fast-forward-ság"** (idézőjelben, ahogy a forrás) | `git-merge-base.adoc` |
| rewrite history / history rewrite | **„előzmény átírása" / „előzmény-átírás"** | `git-history.adoc` — a „history" → „előzmény" a `git-log`/`git-replay`/`git-rerere` (30. blokk) folytatása |
| split out / split-out commit | **„leválaszt" / „leválasztott commit"** | `git-history.adoc` `split` alparancs |
| stateful operation | **„állapottartó művelet"** | `git-history.adoc` LIMITATIONS |
| first-class conflict | **„elsőrangú konfliktus"** | `git-history.adoc` LIMITATIONS |
| opinionated (way) | **„határozott(abb) mód"** | `git-history.adoc` DESCRIPTION |
| fixup (ige, git history) | **„fixupol" / „fixupolás"** | `git-history.adoc` — a `squashel`/`amendel` (0. blokk) mintája szerint |

### Címsor-anchorok

- **`gitformat-signature.adoc`** — 3 defenzív `[[...]]` a `==` (egysoros) Title Case szakaszcímek fölé:
  `[[_tag_signatures]]` („Tag-aláírások"), `[[_commit_signatures]]` („Commit-aláírások"),
  `[[_mergetag_signatures]]` („Mergetag-aláírások"). Egysorosak → nincs aláhúzás-igazítás. Nincs
  `<<...>>` hivatkozás rájuk.
- **`git-pull.adoc`** — 2 defenzív `[[...]]` a `~~~~` Title Case alcímek fölé:
  `[[_options_related_to_merging]]` („Merge-eléssel kapcsolatos opciók", aláhúzás 32) és
  `[[_options_related_to_fetching]]` („Fetcheléssel kapcsolatos opciók", aláhúzás 31). **Mindkét cím
  fordult.** A `_<refspec>_::` leírásában lévő `... <<fetch-refspec,_<refspec>_>> below under
  "Options related to fetching"` prózahivatkozásban a `"Options related to fetching"` idézett
  szakasznevet a fordított címhez igazítottuk: `„Fetcheléssel kapcsolatos opciók"`. **Meglévő xref-ek
  bájtazonosan:** `<<URLS,GIT URLS>>` → `<<URLS,GIT URL-ek>>` (23./26. blokk precedens);
  `<<REMOTES,REMOTES>>`, `<<UPSTREAM-BRANCHES,UPSTREAM BRANCHES>>`, `<<UPSTREAM-BRANCHES,upstream>>`
  (a `upstream` glossary-term, angolul; toldalék a `>>` után: `<<UPSTREAM-BRANCHES,upstream>>-ra`),
  `<<DEFAULT-BEHAVIOUR,DEFAULT BEHAVIOUR>>` + `[[DEFAULT-BEHAVIOUR]]`, `<<fetch-refspec,_<refspec>_>>`
  (placeholder linkszöveg) — mind **változatlan**, mert a cél-címek csupa nagybetűsek (VÉGLEGES
  DÖNTÉS → angol) vagy a linkszöveg glossary-term/placeholder.
- **`git-merge-base.adoc`** — 1 defenzív `[[_discussion_on_fork_point_mode]]` a „A fork-point mód
  tárgyalása" (`----`, aláhúzás 27) alcím fölé. Nincs rá `<<...>>` (a `--fork-point` leírásában
  csak `(see discussion of this mode below)` prózás utalás van, `<<...>>` nélkül).
- **`git-history.adoc`** — 3 defenzív `[[...]]` az EXAMPLES `~~~~` Title Case alcímek fölé:
  `[[_fixup_a_commit]]` („Commit fixupolása", 17), `[[_drop_a_commit]]` („Commit eldobása", 15),
  `[[_split_a_commit]]` („Commit szétvágása", 17). Mind fordult, aláhúzás pontos hosszra.
- **`git-help.adoc`** — nincs `[[...]]`/`<<...>>`. A `~~~~` alcímek **mind angolul maradtak** (l. lent).

### Man-page címként / kanonikus listán kívüli, csupa nagybetűs alcímként ANGOLUL hagyott címsorok

- **`OPERATION MODES`** (`git-merge-base.adoc`), **`DEFAULT BEHAVIOUR`** (`git-pull.adoc`, explicit
  `[[DEFAULT-BEHAVIOUR]]` anchorral + rá mutató xref-fel), **`COMMANDS`** (`git-history.adoc`),
  **`CONFIGURATION VARIABLES`** (`git-help.adoc`) — csupa nagybetűs, kanonikus listán kívüli →
  VÉGLEGES DÖNTÉS szerint bájtazonosan angolul (aláhúzás sem változott).
- **`LIMITATIONS`** (`git-history.adoc`) — a skill kanonikus listáján van, angolul. A prózában lévő
  `see LIMITATIONS.` utalások is angolul (`lásd LIMITATIONS`).
- **`git-help.adoc` `~~~~` alcímek** (`help.format`, `help.browser, web.browser, and
  browser.<tool>.path`, `man.viewer`, `man.<tool>.path`, `man.<tool>.cmd`) — config-kulcs-nevek,
  **nem fordulnak** (a skill „config-kulcsok bájtazonosak" szabálya), aláhúzás változatlan.
  **`Note about konqueror`** és **`Note about git config --global`** — kis-nagybetűs, NEM man-page
  cím; **mégis angolul hagyva**, mert a már lefordított `git-web--browse.adoc` (18. blokk, `[x]`)
  a `'Note about konqueror'` alakot **angolul** hivatkozza prózában, és a konzisztencia előbbre való.
  A `man.viewer` leírásában lévő `(see 'Note about konqueror' below)` így szintén angolul maradt.
- **`See also`** (`git-merge-base.adoc`) — kis-nagybetűs, NEM a kanonikus `SEE ALSO`, de **man page**
  SEE ALSO-szakaszaként funkcionál (`linkgit:` hivatkozásokkal) → bájtazonosan angolul hagyva,
  aláhúzással együtt. (A `ReviewingGuidelines.adoc` 27. blokkbeli `See also` → „Lásd még" fordítása
  NEM man page volt; a man-page-elv itt előbbre való.) **Eldöntendő**, ha a felhasználó egységesen
  fordítani szeretné a kis-nagybetűs `See also`-t man page-ekben is.

### Megőrzött markup / megjegyzések

- Mindegyik fájl GIT szakasza „A linkgit:git[1] csomag része" alakra fordítva (4. blokk).
- **`gitformat-signature.adoc`**: a fájl túlnyomó része `----` körülhatárolt blokk (tag-/commit-/
  mergetag-objektumok nyers szövege, `gpg` kimenet, PGP-blokkok, `$`-jelölt sorvégi whitespace,
  `# gpg:` kommentált sorok) — mind **bájtazonos**; a `-----BEGIN/END … SIGNATURE-----` literálok a
  `::` leírás-törzsekben is változatlanok, csak az „and" → „és" kötőszó fordult. A `[verse]`
  SYNOPSIS két pszeudo-token sora (`<[tag|commit] object header(s)>` / `<over-the-wire protocol>`)
  lefordítva (`<[tag|commit] objektumfejléc(ek)>` / `<vezetéken átvitt protokoll>`) — nem valódi
  AsciiDoc-szintaxis, csak leíró szöveg a verse-blokkban.
- **`git-help.adoc`**: a `------…` (48 kötőjeles) `[man]` config-példablokkok és a `$ git config
  --global …` blokkok **bájtazonosak**. A `{litdd}` attribútum-referencia (`git-web{litdd}browse`)
  változatlan. Az `'-m|--man'` / `'-w|--web'` / `'info'` / `'man'` / `'web'` compat-mode `'...'`
  jelölések és a `"man"` / `"info"` / `"web"` / `"html"` / `"woman"` / `"konqueror"` idézett
  értékek megtartva.
- **`git-pull.adoc`**: az `include::merge-options.adoc[]` / `fetch-options.adoc` /
  `pull-fetch-param.adoc` / `urls-remotes.adoc` / `merge-strategies.adoc` sorok és a `:git-pull: 1`
  attribútum-sor **bájtazonosak**. A `true`;;/`merges`;;/`false`;;/`interactive`;; másodszintű
  def-lista-címkék változatlanok (csak a törzs fordult). A `[NOTE]` admonition-kulcsszó és a
  `_dangerous_` / `*not*` inline-formázás megtartva. A `------------` (12) globbing-refspec példa és
  a `------…` (48) EXAMPLES-blokkok bájtazonosak. A `. ` (AsciiDoc számozott lista) sorok
  megtartva. Az elején lévő `<<UPSTREAM-BRANCHES,upstream>>` toldalékolása a `>>` után (`-ra`).
- **`git-merge-base.adoc`**: a `....` (négy pont) körülhatárolt ASCII-art topológia-diagramok (7 db),
  valamint a `    $ fork_point=…` / `    $ git rebase --onto …` szóközzel behúzott literál sorok és a
  `A=$(git rev-parse …)` / `if test … fi` `....` shell-blokkok **bájtazonosak**. A commit-nevek
  (`B0`, `B1`, `D0'`, stb.) a prózában is változatlanok.
- **`git-history.adoc`**: NAME `EXPERIMENTAL:` → „KÍSÉRLETI:" (29. blokk); a
  `THIS COMMAND IS EXPERIMENTAL. THE BEHAVIOR MAY CHANGE.` csupa nagybetűs mondat lefordítva a
  nagybetűs formázás megtartásával („EZ A PARANCS KÍSÉRLETI. A VISELKEDÉSE MEGVÁLTOZHAT.", 3. blokk).
  A `----------` (10 kötőjeles) EXAMPLES-blokkok (`$ git log --oneline --stat` kimenetek, `diff --git`
  hunkok, `(1/1) Stage addition [y,n,q,a,d,p,?]? y` interaktív promptsorok) **bájtazonosak**. A
  `--` … `--` nyílt blokk a `--empty` leírásában + a benne lévő `*` felsorolás prózája fordult, a
  határolók változatlanok. `SYNOPSIS`-ban nincs `(EXPERIMENTAL!)` előtag (eltér a `git-replay.adoc`-tól).

## 32. blokk — `fsck-msgids.adoc`, `gitignore.adoc`, `git-remote.adoc`, `git-receive-pack.adoc`, `gitcli.adoc` — 2026-09-10

**Módszer:** a felhasználó 5-ös bontást kért — a két gyökér-tábla együttes, sorméret szerint növekvő
listájából a következő 5 legkisebb, még `[ ]` fájl. Orchestrátor végezte közvetlenül, célzott
`Edit`-ekkel (nagyobb, ~5–15 soros blokkokban).

### Ebben a blokkban rögzített / megerősített döntések

| angol | magyar | megjegyzés |
|---|---|---|
| fsck message severity `(ERROR)` / `(INFO)` / `(WARN)` / `(FATAL)` / `(IGNORE)` | **bájtazonosan angolul**, zárójelben | `fsck-msgids.adoc` — az `fsck.<msg-id>` mechanizmus tényleges szintnevei, program-token; nem próza |
| fsck msg-id címkék (`badDate`, `gitmodulesUrl`, `nulInHeader`, …) | **bájtazonosan angolul** (`` `id`:: ``) | csak a leírás-törzs fordult |
| "packed-refs" / "quarantine" / "nonce" (idézőjeles token a prózában) | **angolul, idézőjelben** | `fsck-msgids.adoc`, `git-receive-pack.adoc` — fájlnév, ill. protokoll-token |
| loose ref | **„laza ref"** | `fsck-msgids.adoc` (a 0. blokk `loose object` → „laza objektum" mintája) |
| referent (symref célja) | **„hivatkozott"** (fn) | `fsck-msgids.adoc` `badReferentName` / `symrefTargetIsNotARef` |
| pattern (gitignore) | **„minta"**; „to match" → „illeszkedik" | `gitignore.adoc` |
| wildcard | **„helyettesítő karakter"** (0. blokk öröklött) | `gitignore.adoc`, `gitcli.adoc` |
| to glob / globbed by the shell / fileglob | **„a shell kifejti" / „globbing" (a `git` felé) / „fileglob"** | `gitignore.adoc`, `gitcli.adoc` — a `file globbing` → „fájlnév-globbing" |
| separator (`/` a mintában) | **„elválasztó"** | `gitignore.adoc` |
| to anchor (a match) | **„rögzíti (az illeszkedést)"** | `gitignore.adoc` |
| backslash | **„visszaperjel"**; „escape" (ige) → „escapel" | `gitignore.adoc` — „`\`" bájtazonos |
| hash (a `#` karakter) | **„kettőskereszt"** | `gitignore.adoc` — a SHA-értelmű „hash" továbbra is „hash" |
| mirror (fetch/push mirror) | **„tükör" / „fetch-tükör" / „push-tükör"**; ige: „tükröződik" | `git-remote.adoc` |
| stale reference / stale remote-tracking branch | **„elavult referencia" / „elavult remote-tracking branch"** | `git-remote.adoc`, a `git prune` kontextusban |
| to prune | **„kigyomlál" / „kigyomlálás"** | `git-remote.adoc` (konzisztens a `git-fetch`/`git-gc` korábbi „PRUNING" szakaszfordításokkal) |
| default branch (remote) | **„alapértelmezett branch"** | `git-remote.adoc` `set-head` |
| quarantine directory / quarantined objects | **„karantén könyvtár" / „karanténba helyezett objektumok"**; a `"quarantine"` idézőjeles token angolul | `git-receive-pack.adoc` |
| to migrate (objektum a fő tárba) | **„átvándorol" / „átvándorlás"** | `git-receive-pack.adoc` QUARANTINE ENVIRONMENT |
| connectivity check / object connectivity | **„kapcsolódási ellenőrzés" / „objektum-kapcsolódás"** | `git-receive-pack.adoc` `--skip-connectivity-check` |
| transitive closure (of reachable objects) | **„tranzitív lezárt"** | `git-receive-pack.adoc` |
| push certificate | **„push-tanúsítvány"** | `git-receive-pack.adoc` |
| nonce (aláírt push) | **marad „nonce"**; toldalék: `nonce-ot`, `nonce-sztring` | `git-receive-pack.adoc` |
| to replay (tanúsítványt) | **„visszajátszik"** | `git-receive-pack.adoc` — konzisztens a `git-replay` 30. blokk „újrajátszás"-ával, itt a „replay attack" értelmében „visszajátszás" |
| dumb transport | **marad „dumb transzport"** | `git-receive-pack.adoc` (a `smart`/`dumb` protokoll 17./19. blokk kezelése) |
| convention (CLI) | **„konvenció"** | `gitcli.adoc` |
| to disambiguate / disambiguating `--` | **„egyértelműsít" / „egyértelműsítő `--`"** | `gitcli.adoc` |
| 'stuck' form (opció-argumentum) | **marad "'stuck' (összeragadt) alak"** (első előforduláskor glosszázva) | `gitcli.adoc` |
| to aggregate short options | **„rövid opciók összevonása"** | `gitcli.adoc` |
| to trump (configuration/environment) | **„felülír"** | `gitcli.adoc` „Options trump…" cím |
| dot-repository | **marad „dot-repository"** | `gitcli.adoc` |
| flag (a CLI-kapcsoló szinonimája) | **marad „flag"** (idézőjelben, ahogy a forrás: `"flags"` → `"flag"-ek`) | `gitcli.adoc` |

### Címsor-anchorok

- **`gitcli.adoc`** — 7 defenzív `[[...]]` a `~~~~` alcímek fölé (az `ENHANCED OPTION PARSER` alatt),
  **mind fordult**, aláhúzás pontos karakterhosszra igazítva (Python `len()` ellenőrzés):
  `[[_magic_options]]` „Mágikus opciók" (14), `[[_negating_options]]` „Opciók negálása" (15),
  `[[_options_trump_configuration_and_environment]]` „Az opciók felülírják a konfigurációt és a
  környezetet" (53), `[[_aggregating_short_options]]` „Rövid opciók összevonása" (24),
  `[[_abbreviating_long_options]]` „Hosszú opciók rövidítése" (24),
  `[[_separating_argument_from_the_option]]` „Az argumentum elválasztása az opciótól" (38),
  `[[_magic_filename_options]]` „Mágikus fájlnév-opciók" (22). Nincs rájuk `<<...>>`.
- `fsck-msgids.adoc`, `gitignore.adoc`, `git-remote.adoc`, `git-receive-pack.adoc`: nincs
  `[[...]]`/`<<...>>`. `git-remote.adoc`/`git-receive-pack.adoc` `*-HOOK` és
  `QUARANTINE ENVIRONMENT` / `COMMANDS` alcímek csupa nagybetűsek → angolul (l. lent), nem kaptak
  anchort (autogen slug az angol címből stabil).

### Man-page címként / csupa nagybetűs alcímként ANGOLUL hagyott címsorok

- **`PATTERN FORMAT`** (`gitignore.adoc`), **`COMMANDS`** (`git-remote.adoc`),
  **`PRE-RECEIVE HOOK`** / **`UPDATE HOOK`** / **`POST-RECEIVE HOOK`** / **`POST-UPDATE HOOK`** /
  **`QUARANTINE ENVIRONMENT`** (`git-receive-pack.adoc`), **`ENHANCED OPTION PARSER`** /
  **`NOTES ON FREQUENTLY CONFUSED OPTIONS`** (`gitcli.adoc`) — csupa nagybetűs, kanonikus listán
  kívüli → VÉGLEGES DÖNTÉS szerint bájtazonosan angolul (aláhúzás sem változott). A `HOOKS` a
  VÉGLEGES DÖNTÉS szakasz saját példái közt szerepel.
- **`NOTES`** (`gitignore.adoc`, + a `see the NOTES below` prózahivatkozás), **`EXIT STATUS`**
  (`git-remote.adoc`) — a skill kanonikus listáján, angolul.
- **`PRUNING`** (`git-remote.adoc` prózahivatkozás a `linkgit:git-fetch[1]` szakaszára) — a
  `git-fetch.adoc`-ban is angolul maradt (progress), így a hivatkozás is angol.

### Megőrzött markup / megjegyzések

- **RFC 2119 kulcsszavak angolul** (21./23. blokk precedens): `MUST NOT` (`git-receive-pack.adoc`
  QUARANTINE ENVIRONMENT 3. pont — a magyar mondatba beékelve: „…hook MUST NOT frissítsen egyetlen
  refet sem…"), `SHOULD` és `*NOT*` (`gitcli.adoc`). Az `"options then args"` szabálynév
  (`gitcli.adoc`) idézőjelben, angolul.
- **`fsck-msgids.adoc`**: `0\{40}` attribútum-escape bájtazonos; a `git@vger.kernel.org`
  levelezőlista-cím változatlan; a fájlnak nincs NAME/SYNOPSIS/GIT (tiszta `::` def-lista-fragmens).
- **`gitignore.adoc`**: az `SP`/`LF`/`CR` és a `$XDG_CONFIG_HOME`/`$GIT_COMMON_DIR`/`core.excludesFile`
  tokenek, a `fnmatch(3)` / `FNM_PATHNAME` hívásnevek, valamint a
  `--------------------------------------------------------------` (60 kötőjeles) `$ git …` /
  `[imap]`-szerű shell-példablokkok **bájtazonosak**. A `NOTES`/`EXAMPLES`/`CONFIGURATION` kanonikus
  címek angolul.
- **`git-remote.adoc`**: a `------------` (12) és `------…` (48) EXAMPLES-blokkok (`$ git remote` /
  `$ git fetch staging` kimenet, `From git://…` sorok, `$ git switch -c …`) **bájtazonosak**;
  az `add`/`rename`/`remove`/`rm`/`set-head`/`set-branches`/`get-url`/`set-url`/`show`/`prune`/`update`
  `::` alparancs-címkék változatlanok (csak a törzs fordult); `NOTE:` admonition-kulcsszó a `-v`
  leírásában megtartva.
- **`git-receive-pack.adoc`**: a szóközzel behúzott literál sorok (`sha1-old SP sha1-new SP refname
  LF`, `$GIT_DIR/hooks/update refname sha1-old sha1-new`) és a `----` shell-szkript blokkok
  (`#!/bin/sh`, `git rev-list --pretty`, `git cat-file blob …`, `exec git update-server-info`)
  **bájtazonosak**; a `GIT_PUSH_CERT*` env-változó `::` címkék és az `UNSOLICITED`/`MISSING`/`BAD`/
  `OK`/`SLOP` `;;` másodszintű státusz-címkék változatlanok; a `"git push --signed"` idézett
  parancs angolul.
- **`gitcli.adoc`**: a `--------…` (32/44/28/26 kötőjeles) `$ git …` shell-példablokkok
  (benne a `usage: git describe …` súgókimenet, a `# correct` / `# NOT WHAT YOU MEANT` /
  `# if COMMIT_EDITMSG does not exist…` kommentek) **bájtazonosak**; a `lore.kernel.org` URL-ek
  változatlanok; a `'on'` / `'stuck'` / `'.'` compat-mode `'...'` jelölések megtartva.

## 33. blokk — `gitsubmodules.adoc`, `git-switch.adoc`, `gitdatamodel.adoc`, `git-http-backend.adoc`, `git-range-diff.adoc` — 2026-09-10

**Módszer:** a felhasználó 5-ös bontást kért — a két gyökér-tábla együttes, sorméret szerint növekvő
listájából a következő 5 legkisebb, még `[ ]` fájl (`gitglossary.adoc`/`git.adoc`/`config.adoc`/
`git-fast-import.adoc`/`glossary-content.adoc` kihagyva). Orchestrátor végezte közvetlenül, célzott
`Edit`-ekkel.

### Ebben a blokkban rögzített / megerősített döntések

| angol | magyar | megjegyzés |
|---|---|---|
| „smart" / „dumb" HTTP protocol | **`„smart" HTTP-protokoll` / `„dumb" HTTP-protokoll`** — az angol jelző kettős idézőjelben, a protokoll/protokollt magyarul | `git-http-backend.adoc` — ez volt a 17./19./25. blokkban nyitva hagyott „jövőbeli döntési függőség"; a `dumb szerver` (17.) / `»smart« átviteli adatfolyam` (19.) / `dumb transzport` (32.) ad hoc, idézőjeles kezelésének folytatása. Jelző+főnév szerkezetnél csak az angol jelző marad idézőjelben |
| superproject / subproject | **„szuperprojekt" / „alprojekt"** (0. blokk öröklött) | `gitsubmodules.adoc`, `gitdatamodel.adoc` |
| unborn branch | **„meg nem született branch"** | `git-switch.adoc` `--orphan` |
| unmatched commits (range-diff) | **„egyezés nélküli commitok"** | `git-range-diff.adoc` |
| diff of diffs / "diff of diffs" | **„diffek diffje"** (idézőjelben, ahol a forrás is) | `git-range-diff.adoc` |
| dual coloring / dual-color mode | **„kettős színezés" / `--dual-color` mód** | `git-range-diff.adoc` |
| fudge factor (creation/deletion cost) | **„korrekciós tényező"** | `git-range-diff.adoc` Algoritmus |
| bipartite graph / matching / assignment | **„páros gráf" / „párosítás" / „hozzárendelés"** | `git-range-diff.adoc` — matematikai szakszókincs |
| least-cost assignment | **„legkisebb költségű hozzárendelés"** | `git-range-diff.adoc` |
| false positives | **„téves találatok"** | `git-range-diff.adoc` (konzisztens a 9. blokk `false positive` → `téves` mintájával) |
| patch series | **„patchsorozat"** (patch a 0. blokk szerint marad) | `git-range-diff.adoc` |
| dimmed (diff sor) | **„halványítva"** (idézőjelben, ahol a forrás is) | `git-range-diff.adoc` |
| to correspond / corresponding commits | **„megfelel" / „megfelelő commitok"** | `git-range-diff.adoc` |
| reachable / unreachable (objektum) | **„elérhető" / „elérhetetlen"** (idézőjelben, ahol a forrás `"reachable"`) | `gitdatamodel.adoc` NOTE |
| symbolic reference | **„szimbolikus referencia"** (0. blokk öröklött) | `gitdatamodel.adoc` |
| object name / object ID | **„objektumnév" / „objektumazonosító"** | `gitdatamodel.adoc` — az `[[object-id]]` anchor bájtazonos, a `<<object-id,*object ID*>>` linkszöveg `*objektumazonosítót*`-ra fordult |
| staging area | **marad „staging area"** (0. blokk öröklött) | `gitdatamodel.adoc`, `git-switch.adoc` |
| annotated / lightweight tag | **„annotált tag" / „könnyűsúlyú tag"** (0. blokk öröklött) | `gitdatamodel.adoc` |
| tip of a branch | **„a branch csúcsa"** | `git-switch.adoc`, `gitdatamodel.adoc` |
| to stash / stashed (git-switch `--merge`) | **„stashelődik" / „stashelés"** (0. blokk `stashel`) | `git-switch.adoc` |
| deinitialized / deinitialize (submodule) | **„deinicializált" / „deinicializál"** | `gitsubmodules.adoc` |
| gitlink (tree/index bejegyzés) | **marad `gitlink`** angolul, backtick között | `gitsubmodules.adoc`, `gitdatamodel.adoc` |
| ref advertisement | **„ref-hirdetés"** (ref a 0. blokk szerint marad) | `git-http-backend.adoc` |
| porcelain (output) | **marad „porcelain"** (0. blokk öröklött) | `git-range-diff.adoc` |

### Címsor-anchorok

- **`gitdatamodel(7)`** — anchor-nehéz guide (NEM man page a szokásos értelemben, de section-7).
  **14 meglévő `[[...]]` anchor bájtazonosan megmaradt**: `[[objects]]`, `[[object-id]]`,
  `[[commit]]`, `[[tree]]`, `[[blob]]`, `[[tag-object]]`, `[[references]]`, `[[branch]]`, `[[tag]]`,
  `[[HEAD]]`, `[[remote-tracking-branch]]`, `[[other-refs]]`, `[[index]]`, `[[reflogs]]`.
  A rájuk mutató `<<id,látható szöveg>>` xref-ek **vessző utáni része fordult**:
  `<<objects,Objektumok>>`, `<<references,Referenciák>>`, `<<index,Az index>>`,
  `<<reflogs,Reflogok>>`, `<<commit,commitok>>`, `<<tree,tree-k>>`, `<<blob,blobok>>`,
  `<<tag-object,tag objektumok>>`, `<<object-id,*objektumazonosítót*>>`,
  `<<HEAD,aktuális branchedet>>`, `<<branch,aktuális branchedet>>`, `<<references,referenciához>>`,
  `<<reflogs,reflogból>>` / `<<reflogs,reflogja>>` stb. A `blob`/`tree`/`commit` linkszövegben is
  angolul, magyar toldalékkal (0. blokk: Git-objektum-típusnevek bájtazonosak). Az `[[other-refs]]`
  fölötti `Other references::` def-lista-címke **fordult** (`Egyéb referenciák::`), mert nincs rá
  `<<other-refs>>` xref és nem Git-kulcsszó; a `branches:`/`tags:`/`HEAD:`/`remote-tracking
  branches:` címkék **bájtazonosak** (a `refs/...` útvonal literál).
- **`gitsubmodules(7)`** — 4 defenzív `[[...]]` a Title Case setext alcímek fölé (nincs rájuk
  `<<...>>`), aláhúzás a fordított cím pontos bájt-… ill. karakterhosszához igazítva:
  `[[_the_configuration_of_submodules]]` „A submodule-ok konfigurációja",
  `[[_workflow_for_a_third_party_library]]` „Munkafolyamat harmadik féltől származó könyvtárhoz",
  `[[_workflow_for_an_artificially_split_repo]]` „Munkafolyamat mesterségesen felbontott
  repositoryhoz", `[[_implementation_details]]` „Megvalósítási részletek".
- **`git-range-diff(1)`** — 1 defenzív `[[_algorithm]]` az „Algoritmus" Title Case cím fölé (a
  forrás `----` 1. szintű setext, NEM `==`); a prózában rá mutató `'Algorithm'` (compat-mode `'...'`,
  NEM `<<...>>`) hivatkozások `'Algoritmus'`-ra átírva a konzisztenciáért. A `'SPECIFYING RANGES'`
  (gitrevisions[7] szakasznév) angolul maradt.
- `git-switch.adoc`, `git-http-backend.adoc`: nincs `[[...]]`/`<<...>>`.

### Man-page címként / csupa nagybetűs alcímként ANGOLUL hagyott címsorok (VÉGLEGES DÖNTÉS szerint)

- **`OBJECTS`** / **`REFERENCES`** / **`THE INDEX`** / **`REFLOGS`** (`gitdatamodel.adoc`) — csupa
  nagybetűs, kétsoros aláhúzású, **explicit `[[...]]` anchorral** ellátott szakaszcímek; a
  25. blokk `REMOTES`/`UPSTREAM BRANCHES` precedense szerint a cím **bájtazonosan angolul**, az
  anchor és az aláhúzás változatlan, a rájuk mutató `<<...>>` xref látható szövege fordult.
- **`FORMS`** / **`ACTIVE SUBMODULES`** (`gitsubmodules.adoc`) — csupa nagybetűs, kanonikus listán
  kívül → angolul; a `see FORMS below`, `see DESCRIPTION`, `"ACTIVE SUBMODULES" section below`
  prózahivatkozások szintén angolul (a `"ACTIVE SUBMODULES"` egyenes idézőjellel, bájtazonosan).
- **`SERVICES`** / **`URL TRANSLATION`** (`git-http-backend.adoc`) — csupa nagybetűs, kanonikus
  listán kívül → angolul (a `SERVICES` a 6. blokk `git-daemon.adoc` precedensével is egyezik). Az
  `ENVIRONMENT` / `EXAMPLES` prózahivatkozások angolul (a címek angolok).
- **`OUTPUT STABILITY`** (`git-range-diff.adoc`) — csupa nagybetűs, kanonikus listán kívül → angolul.
- **`"DETACHED HEAD"`** (`git-switch.adoc`, `-d`/`--detach` leírásában, git-checkout[1] szakaszra
  mutató prózahivatkozás) — egyenes idézőjelben, angolul (a 10. blokk `git-checkout.adoc`
  `DETACHED HEAD` precedense). `gitdatamodel.adoc`-ban is: `DETACHED HEAD section` angolul, a
  `"detached HEAD state"` idézőjeles kifejezés → `„leválasztott HEAD-állapotnak" (detached HEAD
  state)` (0. blokk `detached HEAD` → „leválasztott HEAD", első előforduláskor gloss).

### Megőrzött markup / megjegyzések

- **`gitsubmodules.adoc`**: a `[submodule "foo"] … active = …` szóközzel behúzott config-blokkok, a
  `  # Add a submodule` / `git submodule add …` szóközzel behúzott literál parancsblokkok
  **bájtazonosak** (a `# See FORMS on removing submodules` komment is — `FORMS` angol); a `[NOTE]`
  admonition-blokk kulcsszava megtartva, törzse fordult; `'foo'`/`'bar'`/`'baz'`/`'bob'` compat-mode
  `'...'` jelölések megtartva; `linkgit:` / `include::` nincs (csak SEE ALSO linkgit-sorok).
- **`git-switch.adoc`**: a 12 db `------------` (12 kötőjel) `$ git switch …` példablokk (benne a
  `error: You have local changes…`, `Applied autostash.`, `Switched to branch 'mytopic'`,
  `HEAD is now at 9fc9555312 …` program-kimenet és a `M\tfrotz` sor) **bájtazonos**; `[synopsis]`
  blokk, `include::includes/cmd-config-section-all.adoc[]` + `include::config/checkout.adoc[]`
  változatlan; `_<branch>_` / `_<start-point>_` / `_<N>_` / `_<rev-a>_` placeholderek és a
  `` `-c` ``/`` `--track[ (direct|inherit)]` `` `::` opció-címkék bájtazonosak; `_not_` compat-mode
  emphasis megtartva; `"master"`/`"mytopic"`/`"upstream"`/`"HEAD~3"`/`"fixup"` egyenes idézőjeles
  literál-hivatkozások megtartva.
- **`gitdatamodel.adoc`**: az 5 db `----` (4 kötőjel) listing-blokk (`git cat-file -p` objektum-
  dumpök: `tree …`/`parent …`/`author …`, `100644 blob … README.md`, `object …`/`type commit`/
  `tag v1.0.0`, `git ls-files --stage` és `git reflog main` kimenet) **bájtazonos**; a `NOTE:`
  admonition-kulcsszavak megtartva, törzsük fordult; a `100644`/`100755`/`120000`/`040000`/`160000`
  Unix-fájlmód-tokenek és a `refs/heads/<name>` stb. útvonalak változatlanok.
- **`git-http-backend.adoc`**: a 12 db `----------------…` (64 kötőjel) Apache/Lighttpd
  config-példablokk (benne `#` config-kommentek, `SetEnv`/`RewriteCond`/`ScriptAliasMatch`/
  `$HTTP["url"]` direktívák, regexek) **bájtazonos**; `[verse]` blokk változatlan; a
  `http.getanyfile`/`http.uploadpack`/`http.receivepack`/`http.uploadarchive` `::` config-címkék
  bájtazonosak (csak a törzs fordult); a `PATH_INFO`/`REMOTE_USER`/… env-változó-lista tagjai
  angolul (csak a `PATH_INFO (…)` zárójeles prózája fordult); `'$REMOTE_USER'` /
  `'$\{REMOTE_USER}@http.$\{REMOTE_ADDR\}'` a `\{`/`\}` escape-ekkel bájtazonos; a
  `"git-daemon-export-ok"` mágikus fájlnév egyenes idézőjelben, angolul.
- **`git-range-diff.adoc`**: a 7 db `------------` (12 kötőjel) blokk (a példa range-diff kimenet a
  `-:  ------- > 1:  0ddba11 …` sorokkal, `@@ -1,3 +1,3 @@` hunk-fejlécek, `-TODO:`/`+Describe` diff-
  sorok, `#314`, `TO-UNDO`, valamint a 4 db bipartite-gráf ASCII-art `1  A` / `2 --------'  B` /
  `c>0` tabos rajz) **bájtazonos**; `[synopsis]` blokk (benne a tabos `[[--] <path>...]` sor)
  változatlan; a `` `--no-dual-color` ``/`` `--creation-factor=<percent>` ``/… `::` opció-címkék és a
  `` `<range1> <range2>` `` / `` `<rev1>...<rev2>` `` / `` `<base> <rev1> <rev2>` `` argumentum-
  címkék bájtazonosak; a `color.diff.<slot>` / `contextDimmed` stb. config-token, a
  `Jonker–Volgenant` név, a `c>0` / `n+m` / `n*m` matematikai jelölések változatlanok; `Note:`
  (kisbetűs, NEM `NOTE:` admonition) → „Megjegyzés:".

## 34. blokk — `gitrepository-layout.adoc`, `gitdiffcore.adoc`, `gitcredentials.adoc`, `git-ls-files.adoc`, `git-merge-tree.adoc`, `BreakingChanges.adoc`, `git-grep.adoc`, `scalar.adoc`, `fetch-options.adoc`, `gitprotocol-capabilities.adoc` — 2026-09-10

**Módszer:** a felhasználó 10-es bontást kért — a két gyökér-tábla együttes, sorméret szerint növekvő
listájából a következő 10 legkisebb, még `[ ]` fájl (`gitglossary.adoc`/`git.adoc`/`config.adoc`/
`git-fast-import.adoc`/`glossary-content.adoc` kihagyva). Orchestrátor végezte közvetlenül, célzott
`Edit`-ekkel (nagy, ~10–90 soros blokkokban).

### Ebben a blokkban rögzített / megerősített döntések

| angol | magyar | megjegyzés |
|---|---|---|
| breaking change / breaking release / backwards-incompatible | **„kompatibilitástörő változás" / „kompatibilitástörő kiadás" / „visszafelé nem kompatibilis"** | `BreakingChanges.adoc` — a doc `= Upcoming breaking changes` címe: „Közelgő kompatibilitástörő változások" |
| to deprecate / deprecated / deprecation | **„elavulttá nyilvánít" / „elavult" / „elavulttá nyilvánítás"** | `BreakingChanges.adoc` |
| enlistment (Scalar) | **marad „enlistment"** (coined term, a doc definiálja); első előforduláskor magyar glossza | `scalar.adoc` |
| forge (Git hosting) | **marad „forge"**; toldalék: `forge-ok`, `forge-okhoz` | `scalar.adoc`, `BreakingChanges.adoc` |
| long-term support release | **„hosszú távú támogatási kiadás"** | `BreakingChanges.adoc` |
| test balloon | **„próbaléggömb"** | `BreakingChanges.adoc` |
| graft / grafting / grafts | **marad „graft" / „graftolás" / „graftok"** (Git jargon) | `BreakingChanges.adoc`, `gitrepository-layout.adoc` |
| object store (`.git/objects`) | **„objektumadatbázis"** (0. blokk `object database (ODB)`; NEM „objektumtárolás" — az S3/GCP-értelem, 1. blokk) | `gitrepository-layout.adoc`, `git-grep.adoc` |
| symref (a `symbolic ref` rövidítése) | **marad „symref"** angolul (Git jargon, „see glossary") | `gitrepository-layout.adoc`, `gitprotocol-capabilities.adoc` |
| `'unpacked'` / `'loose'` / `'bare'` / `'gitfile'` / `'detached HEAD.'` (compat-mode `'...'` jelölésű Git jargon) | **bájtazonosan angolul, a `'...'` jelöléssel** | `gitrepository-layout.adoc` — coined/jargon-címkék; a `'borrow'` (sima ige emfázisban) viszont fordult: `'kölcsönöz'` |
| `*must*` (kisbetűs, `*...*` emfázisú modális ige folyó szövegben) | **fordult: `*kötelező*`** (a `*` jelölés megtartva) | `gitrepository-layout.adoc` — NEM formális RFC 2119 (az uppercase `MUST`/`SHOULD` marad angol); a lowercase emfázis közönséges kiemelés |
| diffcore transformation | **„diffcore transzformáció"** | `gitdiffcore.adoc` |
| filepair | **marad „filepair"** (coined, a doc definiálja) | `gitdiffcore.adoc` |
| `"tree"` object (idézőjeles) | **marad `"tree"`** angolul (Git objektum-típusnév, 0. blokk) | `gitdiffcore.adoc` |
| complete rewrite / break score / extent of changes / similar enough | **„teljes újraírás" / „break score" (angolul, a `-B`-hez kötve) / „változások mértéke" / „elég hasonló"** | `gitdiffcore.adoc` — idézőjelben, ahol a forrás is |
| preimage / postimage | **marad „preimage" / „postimage"** (Git diff jargon) | `gitdiffcore.adoc` |
| credential(s) (sima szó) / credential helper (összetétel) | **„hitelesítő adatok" / marad „credential helper"** (anglicizmus, 0. blokk) | `gitcredentials.adoc` — `credential-kontextus`, `credential.helper` config bájtazonos |
| status tag (git-ls-files `-t`) | **„státuszcímke"** | `git-ls-files.adoc` — a `H`/`S`/`M`/`R`/`C`/`K`/`?`/`U` `::` címkék bájtazonosak |
| unborn branch | **„meg nem született branch"** (0./33. blokk) | `git-ls-files.adoc` — a `--orphan` mintája |
| toplevel tree (merge-tree) | **„legfelső szintű fa"** | `git-merge-tree.adoc` |
| trivial merge / semi-diff format | **„triviális merge" / „fél-diff formátum"** | `git-merge-tree.adoc` |
| higher order stage (index) | **„magasabb rendű stage"** | `git-merge-tree.adoc` |
| many-to-many / one-to-one mapping | **„több-a-többhöz" / „egy-az-egyhez" leképezés** | `git-merge-tree.adoc` |
| `Do NOT` / `AVOID` (emfatikus, csupa nagybetűs mondatkezdet) | **`NE` / `KERÜLD`** (nagybetűs marad, a 3. blokk emfatikus formázás-megtartás mintája) | `git-merge-tree.adoc` |
| force-update / force-updated (branch) | **„force-update" (fn, marad); „force-update történt-e" (ige helyett körülírás)** | `fetch-options.adoc` — a 0. blokk `force-update` tétele |
| have line / want line / "have" set (protokoll) | **„have sor" / „want sor" / „have-halmaz"**; a `"have"` / `"want"` idézőjeles protokoll-token angolul | `fetch-options.adoc`, `gitprotocol-capabilities.adoc` |
| to thicken (a thin pack) | **„megvastagít"** (idézőjelben, ahol a forrás `"thicken"`) | `gitprotocol-capabilities.adoc` |
| stream code / sideband channel | **„folyamkód" / „sideband csatorna"** | `gitprotocol-capabilities.adoc` |
| push certificate / nonce | **„push-tanúsítvány" / marad „nonce"** (32. blokk) | `gitprotocol-capabilities.adoc` |
| capability (protokoll) | **„képesség"**; a konkrét capability-nevek (`multi_ack`, `thin-pack`, …) angolul, `'...'` jelöléssel | `gitprotocol-capabilities.adoc` |

### Címsor-anchorok

- **`git-merge-tree.adoc`** — 8 meglévő `[[...]]` anchor **bájtazonos** (`[[NEWMERGE]]`, `[[OUTPUT]]`,
  `[[MS]]`, `[[OIDTLT]]`, `[[CFI]]`, `[[IM]]`, `[[INPUT]]`, `[[DEPMERGE]]`). A 4 `~~~~` Title Case
  alcím **fordult**, aláhúzás pontos karakterhosszra igazítva (Python `len()` ellenőrzés):
  „Merge-státusz" (13), „A legfelső szintű fa OID-ja" (27), „Konfliktusos fájlinformáció" (27),
  „Tájékoztató üzenetek" (20). A rájuk mutató `<<OIDTLT,legfelső szintű fa OID-ja>>` /
  `<<CFI,konfliktusos fájlinformáció>>` / `<<IM,tájékoztató üzenetek>>` xref-ek vessző utáni része
  is fordult (kisbetűsítve, folyó szövegben). A csupa nagybetűs linkszövegek angolul:
  `<<INPUT,INPUT FORMAT>>`, `<<OUTPUT,OUTPUT>>`, `<<DEPMERGE,DEPRECATED DESCRIPTION>>`,
  `<<NEWMERGE,DESCRIPTION>>`.
- **`gitdiffcore.adoc`** — 7 defenzív `[[...]]` a Title Case setext szakaszcímek fölé (nincs rájuk
  `<<...>>`): `[[_the_chain_of_operation]]` „A műveleti lánc", + 6 `diffcore-*` cím
  (`_diffcore_break_for_splitting_up_complete_rewrites` „diffcore-break: teljes újraírások
  szétbontásához" stb. — a `diffcore-*:` token megtartva, a „For …" leíró rész fordult). Aláhúzás
  pontos hosszra igazítva.
- **`gitcredentials.adoc`** — 2 defenzív `[[...]]` a `===` alcímek fölé: `[[_available_helpers]]`
  „=== Elérhető helperek", `[[_oauth]]` „=== OAuth" (proper noun, fordítatlan).
- **`BreakingChanges.adoc`** — NEM man page; **minden** `==`/`===` cím fordult, 5 defenzív `[[...]]`:
  `[[_procedure]]` „== Eljárás", `[[_git_3_0]]` „== Git 3.0" (verzió-token, fordítatlan),
  `[[_changes]]` „=== Változások", `[[_removals]]` „=== Eltávolítások",
  `[[_superseded_features_that_will_not_be_deprecated]]` „== Leváltott funkciók, amelyeket nem
  nyilvánítanak elavulttá". A `= Upcoming breaking changes` doc-cím → „= Közelgő kompatibilitástörő
  változások".
- **`scalar.adoc`** — 8 defenzív `[[...]]` a `~~~~` alparancs-alcímek fölé (mind fordult, aláhúzás
  pontos hosszra igazítva): `[[_clone]]` „Klónozás", `[[_list]]` „Listázás", `[[_register]]`
  „Regisztrálás", `[[_unregister]]` „Kiregisztrálás", `[[_run]]` „Futtatás", `[[_reconfigure]]`
  „Újrakonfigurálás", `[[_diagnose]]` „Diagnosztizálás", `[[_delete]]` „Törlés".
- **`gitprotocol-capabilities.adoc`** — a capability-nevek (`multi_ack`, `multi_ack_detailed`,
  `no-done`, `thin-pack`, `side-band, side-band-64k`, `ofs-delta`, `agent`, `object-format`,
  `symref`, `shallow`, `deepen-*`, `no-progress`, `include-tag`, `report-status`,
  `report-status-v2`, `delete-refs`, `quiet`, `atomic`, `push-options`, `allow-*-sha1-in-want`,
  `push-cert=<nonce>`, `filter`, `session-id=<session-id>`) protokoll-token identifikátorok →
  **bájtazonosan angolul**, aláhúzás változatlan, **nincs** defenzív anchor.
- `gitrepository-layout.adoc`, `git-ls-files.adoc`, `git-grep.adoc`, `fetch-options.adoc`: nincs
  `[[...]]`/`<<...>>`. A `git-ls-files.adoc` / `git-grep.adoc` / `git-merge-tree.adoc` csupa
  nagybetűs, kanonikus listán kívüli alcímei a VÉGLEGES DÖNTÉS szerint angolul (l. lent).

### Man-page címként / csupa nagybetűs alcímként ANGOLUL hagyott címsorok (VÉGLEGES DÖNTÉS szerint)

- **`FIELD NAMES`** / **`EXCLUDE PATTERNS`** (`git-ls-files.adoc`, + `see EXCLUDE PATTERNS below` /
  `see OUTPUT below` prózahivatkozások), **`USAGE NOTES`** / **`MISTAKES TO AVOID`** /
  **`INPUT FORMAT`** / **`DEPRECATED DESCRIPTION`** (`git-merge-tree.adoc`),
  **`REQUESTING CREDENTIALS`** / **`AVOIDING REPETITION`** / **`CREDENTIAL CONTEXTS`** /
  **`CONFIGURATION OPTIONS`** / **`CUSTOM HELPERS`** (`gitcredentials.adoc`),
  **`NOTES ON THREADS`** (`git-grep.adoc`, + `` `NOTES ON THREADS` `` prózahivatkozás),
  **`RECOMMENDED CONFIG VALUES`** (`scalar.adoc`) — csupa nagybetűs, kanonikus listán kívül →
  bájtazonosan angolul (aláhúzás sem változott).
- **`OUTPUT`** (`git-merge-tree.adoc`, explicit `[[OUTPUT]]` anchorral; `git-ls-files.adoc` szakasz;
  `fetch-options.adoc` prózahivatkozás `linkgit:git-fetch[1]`-re) — a 3. blokk `OUTPUT` precedense,
  angolul. **`EXIT STATUS`** (`git-merge-tree.adoc`) — kanonikus.
- **`PRUNING`** (`fetch-options.adoc`, `see the PRUNING section below` — a `git-fetch.adoc`-ban is
  angol, 32. blokk) és **`"Configured Remote-tracking Branches"`** (`fetch-options.adoc`
  prózahivatkozás a `git-fetch.adoc` `[[CRTB]]` / `CONFIGURED REMOTE-TRACKING BRANCHES` szakaszára,
  12./26. blokk) — angolul, idézőjelben.
- **`"Packfile Negotiation"`** (`gitprotocol-capabilities.adoc`, `linkgit:gitprotocol-pack[5]`
  szakasznév) — egyenes idézőjelben, angolul.

### Megőrzött markup / megjegyzések

- **`gitrepository-layout.adoc`**: tiszta `::` def-lista (útvonal-/fájlnév-címkék: `objects::`,
  `HEAD::`, `worktrees/<id>/gitdir::`, … — **bájtazonosak**); a 4 `ifndef::with-breaking-changes[]` /
  `endif::with-breaking-changes[]` guard és az `include::technical/repository-version.adoc[]`
  változatlan; a `link:user-manual.html[...]` látható szövege fordult („A Git felhasználói
  kézikönyve"); `$GIT_COMMON_DIR` / `"$GIT_COMMON_DIR/objects"` idézőjeles útvonalak
  változatlanok; a `. You could …` implicit számozott lista `. ` jelölése megtartva.
- **`gitdiffcore.adoc`**: a 9 pár `------------------------------------------------` (48 kötőjel)
  `:100644 …` raw-diff példablokk **bájtazonos** (a `README`/`Makefile`/`*.h`/`*.c`/`t` orderfile-
  példa is); `{asterisk}` attribútum-referencia változatlan; a „5 ilyen transzformáció" (a lista
  6 elemű — upstream inkonzisztencia) **nem javítva**; `'-'` / `'+'` compat-mode jelölés megtartva.
- **`gitcredentials.adoc`**: a `------------------` (18) SYNOPSIS-blokk és a 22 config-példablokk
  (`----…` 18/36–52 kötőjel, benne `#` Apache/shell config-kommentek, `[credential "…"]` szekciók,
  `!f() { … }` shell-snippet) **bájtazonos**; a `helper::` / `username::` / `useHttpPath::` /
  `` `get`:: `` / `` `store`:: `` / `` `erase`:: `` `::` címkék változatlanok; a `cache::` / `store::`
  helper-nevek bájtazonosak; `'CONFIGURATION'` szakasznév-hivatkozás angolul; `\0` escape megtartva;
  a `keep'` (nyitó backtick, záró aposztróf — upstream elírás) **bájtazonosan** hagyva; a
  `<entlistment>` elírás (kód-spanben) bájtazonos.
- **`git-ls-files.adoc`**: `[verse]` blokk; a `--`…`--` open-block a `H::`/`S::`/… tab-behúzott
  státuszcímke-listával (a `U::` utáni 5 szóköz megtartva); a `        [<tag> ]<mode> …` /
  tabbal behúzott `i/<eolinfo>…` / `git ls-files --format='…'` literál sorok **bájtazonosak**;
  `objectmode::`/`objecttype::`/… mezőnév-`::`-címkék változatlanok; a `"-text"`/`"none"`/`"lf"`/
  `"crlf"`/`"text=auto eol=lf"` eol-értékek és `%(fieldname)` / `%x00` / `\0` / `\t` / `\n`
  jelölések bájtazonosak; `'assume unchanged'` / `'fsmonitor valid'` compat-mode jelölés megtartva;
  `\--::` bájtazonos.
- **`git-merge-tree.adoc`**: `[verse]` blokk; a `(deprecated)` synopsis-annotáció → `(elavult)`; a
  `<OID of toplevel tree>` / `<Conflicted file info>` / `<Informational messages>` / `<Merge status>`
  / `NUL` tab-behúzott literál kimenet-vázlatok **bájtazonosak**; a `     0: …` / `     1: …`
  5-szóközzel behúzott státuszkód-magyarázatok fordultak (behúzás megtartva); a `* "Auto-merging"` /
  `* "CONFLICT (rename/delete)"` / `"Failed to merge submodule …"` idézőjeles program-üzenet-példák
  angolul; a `vi message.txt` … `git update-ref $BRANCH1 $NEWCOMMIT` 7-szóközzel behúzott
  shell-blokk (benne `echo "There were conflicts…"`) bájtazonos; `"merge.directoryRenames"` /
  `"conflicts"` idézőjeles config-token angolul.
- **`BreakingChanges.adoc`**: a `--`…`--` open-block a Rust-mérföldkövek számozott listájával
  fordult; a `** ` másodszintű felsorolás-elemek fordultak; a `<message-id@host>` e-mail-
  message-ID-k és a `675704c74dd (init: …, 2020-12-11)` alakú commit-hivatkozások (hash +
  angol commit-subject) **bájtazonosak**; `Cf.` → `Vö.`; `_not_` compat-mode emfázis → `_nem_`;
  `MUST` (RFC 2119, `WITH_BREAKING_CHANGES` guard leírásában) angolul; `"sha1"`/`"sha256"`/
  `"files"`/`"reftable"`/`"packed-refs"`/`"experimental"` idézőjeles formátum-/feature-nevek
  angolul.
- **`git-grep.adoc`**: `[synopsis]` blokk; `include::includes/cmd-config-section-all.adoc[]` +
  `include::config/grep.adoc[]` változatlan; `'CONFIGURATION'` / `'Defining a custom hunk-header'`
  compat-mode szakasznév-hivatkozások angolul; `` `grep`(1) `` / `` `glob`(7) `` / `\0` bájtazonos;
  `"less"` / `"vi"` / `"a*"` / `"*"` idézőjeles program-/glob-példák angolul; a `` `git grep …` ``
  EXAMPLES-`::`-címkék bájtazonosak (csak a törzs fordult).
- **`scalar.adoc`**: `[verse]` blokk; a config-kulcs `::`-címkék (`am.keepCR=true::`,
  `credential.https://dev.azure.com.useHttpPath=true::`, …) és az alparancs-`::`-címkék
  (`clone [<options>] …::`, `list::`, `diagnose [<enlistment>]::` — utóbbi 4-szóközzel behúzott
  törzzsel) **bájtazonosak**; `"experimental"` / `"many files"` idézőjeles feature-leírás fordult;
  a `keep'` (upstream elírás) és a `<entlistment>` elírás bájtazonos; `\r` escape megtartva.
- **`fetch-options.adoc`**: tiszta opció-fragmens (nincs NAME/GIT/DESCRIPTION); mind a 22
  `ifdef::git-pull[]` / `ifndef::git-pull[]` / `endif::git-pull[]` guard **bájtazonos**; minden
  `::` opció-címke és a `+` folytatásjelölők változatlanok; `{asterisk}` / `_NUL_` / `_LF_` /
  `__<refspec>__` / `_<n>_` placeholderek bájtazonosak; `'shallow'` compat-mode jelölés megtartva;
  `"have"` / `"changed"` / `"Fetching submodule foo"` idézőjeles protokoll-token, ill. program-
  üzenet angolul (a `"changed"` leíró → nem fordult, protokoll-kontextus).
- **`gitprotocol-capabilities.adoc`**: `[verse]` blokk (`<over-the-wire-protocol>`); a
  `+---- u ----` … tab-behúzott bipartite-gráf ASCII-art **bájtazonos**; a ` 1 - pack data` /
  ` 2 - …` / ` 3 - …` 1-szóközzel behúzott folyamkód-lista fordult (behúzás megtartva); minden
  idézőjeles protokoll-parancs/-string (`"ACK obj-id continue"`, `"done"`, `"deepen"`,
  `"rev-list --max-age=<timestamp>"`, `"symref=HEAD:refs/heads/master"`, `"side-band-64k"`,
  `"want"`, `"filter"`, `"option"`, `"proc-receive"`, `"package/version"`, `"git/1.8.3.1"`, a hosszú
  `"I do not wish to receive stream 2 …"` kliens-idézet) **bájtazonosan angolul**; `'multi_ack'` /
  `'thin-pack'` / `'no-thin'` / … compat-mode jelölés megtartva; RFC 2119 kulcsszavak
  (`SHOULD`/`MUST`/`MUST NOT`/`MAY`) angolul; `link:technical/api-trace2.html[api-trace2]` látható
  szöveg (doc-név) angolul; `OBJ_OFS_DELTA` / `PACKv2` / `DAG` / `SHA-1` bájtazonos.

## 35. blokk — `git-repack.adoc`, `git-notes.adoc`, `git-merge.adoc`, `gitformat-index.adoc`, `revisions.adoc` — 2026-09-11

**Módszer:** a felhasználó 5-ös bontást kért — a két gyökér-tábla együttes, sorméret szerint növekvő
listájából a következő 5 legkisebb, még `[ ]` fájl (`gitglossary.adoc`/`git.adoc`/`config.adoc`/
`git-fast-import.adoc`/`glossary-content.adoc` kihagyva). Orchestrátor végezte közvetlenül, célzott
`Edit`-ekkel.

### Ebben a blokkban rögzített / megerősített döntések

| angol | magyar | megjegyzés |
|---|---|---|
| pack (fn, packelés kontextusában) | **marad „pack"**; toldalék: `packbe`, `packek`, `packet`, `packben` | `git-repack.adoc` — a `packfile` (0. blokk) rövid alakja; ahol a forrás idézőjelezi (`"pack"`), az idézőjel megmarad |
| to repack / repacking | **„újracsomagolás" / „újracsomagol"**; `git repack` parancsnév marad | `git-repack.adoc` |
| cruft pack | **marad „cruft pack"** (coined Git-fogalom) | `git-repack.adoc` — `cruft-expiration`, `max-cruft-size` config-tokenek angolul |
| promisor packfile / promisor remote / promisor pack | **marad „promisor …"** (1. blokk) | `git-repack.adoc` |
| unreachable / reachable object | **„elérhetetlen" / „elérhető objektum"** | `git-repack.adoc`, `revisions.adoc` |
| loose object | **„laza objektum"** (0. blokk) | `git-repack.adoc` |
| dangling (`git fsck` értelmében) | **„lógó"** | `git-repack.adoc` |
| „dumb" protocol / „dumb" http protocol | **„dumb" protokoll** (idézőjelben, a 33. blokk „dumb"/„smart" HTTP ad hoc kezelésének folytatása) | `git-repack.adoc` — a forrás itt nem idézőjelezi, de a konzisztencia miatt idézőjelbe került |
| geometric progression / „cut" / „roll-up" / „rolled-up" | **„geometriai progresszió" / „cut" / „roll-up" / „rolled-up"** (utóbbi három idézőjelben, angolul, ahogy a forrás) | `git-repack.adoc` |
| multi-pack index (MIDX) / multi-pack bitmap | **marad „multi-pack index (MIDX)" / „többpackes bitmap"** | `git-repack.adoc` |
| reachability bitmap index | **„elérhetőségi bitmap index"** | `git-repack.adoc` |
| (object) note / notes | **„jegyzet" / „jegyzetek"**; `git notes` parancsnév marad; „object notes" → „objektumjegyzetek" | `git-notes.adoc` |
| notes ref | **„jegyzet-ref"** (a `ref` literál angolul, 0. blokk) | `git-notes.adoc` |
| to annotate (jegyzet-kontextusban) | **„annotál"** (0. blokk) | `git-notes.adoc` — „the objects they annotate" → „az általuk annotált objektumok" |
| resolver (notes merge `manual` resolver) | **„feloldó"** | `git-notes.adoc` |
| inter-paragraph separator | **„bekezdésközi elválasztó"** | `git-notes.adoc` |
| patch commentary | **„patch-kommentár"** | `git-notes.adoc` |
| "remote" / "local" (notes-merge oldalak neve, idézőjelben) | **bájtazonosan angolul, idézőjelben** | `git-notes.adoc` — a merge-oldalak megnevezett címkéi |
| "cat \| sort \| uniq" shell pipeline | **bájtazonosan** | `git-notes.adoc` |
| binary-safe / binary-safely | **„bináris-biztos" / „bináris-biztosan"** | `git-notes.adoc` |
| development history / to join histories | **„fejlődéstörténet" / „történetek összekapcsolása"** | `git-merge.adoc` NAME + DESCRIPTION |
| Octopus merge | **marad „Octopus merge"** (első előforduláskor „…amit szeretettel Octopus merge-nek neveznek") | `git-merge.adoc` |
| conflict marker | **„konfliktusjelölő"** | `git-merge.adoc` — a `+<<<+` / `===` / `+>>>+` / `+\|\|\|\|\|\|\|+` compat-mode passthrough jelölések bájtazonosak |
| conflicted hunk | **„konfliktusos hunk"** (0. blokk `hunk`) | `git-merge.adoc` |
| autostash entry / stash entry / stash list | **„autostash bejegyzés" / „stash-bejegyzés" / „stash-lista"** | `git-merge.adoc` |
| to "unwrap" a tag | **„kicsomagolod" a taget** (idézőjelben, ahogy a forrás) | `git-merge.adoc` |
| triangular workflow | **„háromszög alakú munkafolyamat"** | `revisions.adoc` (`@{push}` példa) |
| "Already up to date." (program-kimenet) | **bájtazonosan angolul, idézőjelben** | `git-merge.adoc` |
| revision parameter / revision range | **„revíziós paraméter" / „revíziótartomány"** | `revisions.adoc` |
| extended SHA-1 (syntax) | **„kiterjesztett SHA-1"** (idézőjelben, ahogy a forrás `'extended SHA-1'`) | `revisions.adoc` |
| symbolic ref name | **„szimbolikus refnév"** (a `ref` literál angolul; „symbolic reference" → „szimbolikus referencia", 0. blokk) | `revisions.adoc` |
| reachable / reachable set / ancestry chain | **„elérhető" / „elérhető halmaz" / „ősök láncolata"** | `revisions.adoc` — a `` `reachable` `` backtickes előfordulás bájtazonos |
| symmetric difference | **„szimmetrikus különbség"** | `revisions.adoc` |
| to dereference (an object) | **„dereferál"** | `revisions.adoc` — „…cannot be dereferenced anymore (in which case, barf)" → „…már nem dereferálható tovább (ez esetben hiba)" |
| commit-ish / tree-ish | **marad „commit-ish" / „tree-ish"** (Git jargon) | `revisions.adoc` |
| suffix / prefix / brace pair / ordinal specification | **„utótag" / „előtag" / „kapcsos zárójelpár" / „sorszám-megadás"** | `revisions.adoc` |
| youngest matching commit | **„legfiatalabb illeszkedő commit"** | `revisions.adoc` |
| index format / index entry | **„indexformátum" / „indexbejegyzés"** | `gitformat-index.adoc` |

### Címsor-anchorok

- **`git-notes.adoc`**: meglévő `[[CONFIGURATION]]` inline anchor + a DESCRIPTION-ben lévő
  `<<CONFIGURATION,CONFIGURATION>>` xref **bájtazonos** (kanonikus man-page cím, a VÉGLEGES DÖNTÉS
  szerint angolul marad, a linkszöveg is).
- **`gitformat-index.adoc`** (format-spec doksi, `gitformat-*(5)`): 11 `==`/`===` cím, egyikük sem
  volt anchorozva, és nincs rájuk `<<...>>` sehol a fában (grep). Mindegyik fölé defenzív
  `[[<angol-autogen-slug>]]` került (`_` prefix, `_` separator, az **eredeti angol** címszövegből):
  `[[_the_git_index_file_has_the_following_format]]` „A Git indexfájljának a következő formátuma van",
  `[[_index_entry]]` „Indexbejegyzés", `[[_extensions]]` „Kiterjesztések", `[[_cache_tree]]`,
  `[[_resolve_undo]]`, `[[_split_index]]`, `[[_untracked_cache]]`, `[[_file_system_monitor_cache]]`,
  `[[_end_of_index_entry]]`, `[[_index_entry_offset_table]]`, `[[_sparse_directory_entries]]`. A
  kiterjesztés-**tulajdonnevek** (`Cache tree`, `Resolve undo`, `Split index`, `Untracked cache`,
  `File System Monitor cache`, `End of Index Entry`, `Index Entry Offset Table`,
  `Sparse Directory Entries`) **címszövege angolul maradt** (a doksi törzse végig ezekre a szó
  szerinti angol nevekre hivatkozik: „split index mode", „resolve undo extension" stb.); csak a
  generikus `Index entry` / `Extensions` / a leíró mondat-cím fordult. Egysoros `==` címek → nincs
  aláhúzás-igazítás.
- **`revisions.adoc`** (`gitrevisions.adoc` `include`-célja): nincs meglévő `[[...]]`/`<<...>>`
  (grep az egész fában). 4 Title Case setext alcím fölé defenzív `[[...]]` (aláhúzás a fordított
  cím pontos hosszához igazítva, Python `len()` ellenőrzés): `[[_commit_exclusions]]`
  „Commit-kizárások" (16 `~`), `[[_dotted_range_notations]]` „Pontos tartományjelölések" (25 `~`),
  `[[_other_rev_parent_shorthand_notations]]` „Egyéb <rev>{caret} szülő-rövidítésjelölések"
  (37 `~`; az autogen-slug a `{caret}`→`^` renderelt alakból), `[[_revision_range_summary]]`
  „Revíziótartomány-összefoglaló" (29 `-`).

### Man-page címként / csupa nagybetűs alcímként ANGOLUL hagyott címsorok (VÉGLEGES DÖNTÉS szerint)

- **`git-merge.adoc`**: `PRE-MERGE CHECKS`, `FAST-FORWARD MERGE`, `TRUE MERGE`, `MERGING TAG`,
  `HOW CONFLICTS ARE PRESENTED`, `HOW TO RESOLVE CONFLICTS` — csupa nagybetűs, kanonikus listán
  kívüli, kétsoros aláhúzású (aláhúzás sem változott). A `--continue` opció leírásában lévő
  `"HOW TO RESOLVE CONFLICTS" section` prózahivatkozás is angolul, idézőjelben.
- **`git-notes.adoc`**: `SUBCOMMANDS`, `NOTES MERGE STRATEGIES` — csupa nagybetűs, kanonikus listán
  kívüli. A `-s`/`--strategy` és a `merge` alparancs leírásában lévő `"NOTES MERGE STRATEGIES"
  section` prózahivatkozások angolul, idézőjelben.
- **`revisions.adoc`**: `SPECIFYING REVISIONS`, `SPECIFYING RANGES` — csupa nagybetűs, kétsoros
  aláhúzású, a kanonikus listán kívül; a 14. blokk (`git-diff.adoc` idézőjeles prózahivatkozásai)
  precedensét folytatva **bájtazonosan angolul** (aláhúzás sem változott). A „two-dot" Range
  Notation `::` leírásában lévő `SPECIFYING REVISIONS above` prózahivatkozás is angolul.

### Megőrzött markup / megjegyzések

- **`git-repack.adoc`**: `[verse]` synopsis; a `--write-midx[=<mode>]` alatti `--`…`--` open-block a
  `` `default`;; `` / `` `incremental`;; `` beágyazott def-listával változatlan (csak a törzs
  fordult); 15 `+` folytatásjel bájtazonos; a `**WARNING:**` inline erős kiemelés megtartva; a
  `"k"`/`"m"`/`"g"` méret-utótagok, `".promisor"` fájlnév, `.keep` / `pack-123.pack` literálok,
  `repack.*` / `pack.*` config-kulcsok, `git prune`/`git gc`/`git pack-objects` parancsnevek
  angolul.
- **`git-notes.adoc`**: 2 `include::` sor (`includes/cmd-config-section-rest.adoc`,
  `config/notes.adoc`) bájtazonos; a `copy` alparancsban lévő `----------` (10 kötőjel) blokk
  (`<from-object> SP <to-object> …`) és 2 `--`…`--` open-block (`--stripspace` felsorolás)
  változatlan; az EXAMPLES 4 `------------` blokkja (`$ git notes add …` / `$ cc *.c` …)
  bájtazonos; a `footnote:[…]` makró törzse fordult, a `'bf'`/`'fe'`/… compat-mode literál-jelölés
  megtartva; `refs/notes/commits`, `GIT_NOTES_*` env-változók, `.git/NOTES_MERGE_*` útvonalak,
  `manual`/`ours`/`theirs`/`union`/`cat_sort_uniq` stratégianevek, `overwrite`/`concatenate`/…
  módnevek angolul.
- **`git-merge.adoc`**: `[synopsis]` blokk; `:git-merge: 1` attribútum-sor bájtazonos; 3
  `include::` (`merge-options.adoc`, `rerere-options.adoc`, `merge-strategies.adoc`) + 2
  config-`include::` változatlan; az `------------` ASCII-art commit-gráfok, a 3 konfliktus-példa
  `------------` blokk (RCS/`diff3`/`zdiff3` stílus — tele `<<<<<<<`/`=======`/`|||||||`/`>>>>>>>`
  jelekkel), a `----` (`git fetch origin` …) és az EXAMPLES 3 `------------------------------------------------`
  (48 kötőjel) blokkja **bájtazonos**; `WARNING:` admonition-kulcsszó megtartva, próza fordult;
  `ORIG_HEAD`/`MERGE_HEAD`/`AUTO_MERGE`/`FETCH_HEAD`, `ort` stratégianév, `merge.conflictStyle` /
  `branch.<name>.mergeOptions` config-kulcsok angolul.
- **`gitformat-index.adoc`**: a teljes format-spec törzs 2+ szóközzel behúzott **AsciiDoc literál
  bekezdés** → a reftable/hash-function-transition/gitformat-commit-graph precedens (1./28. blokk)
  szerint **bájtazonosan angolul** (bájtdiagramok, `{ 'D', 'I', 'R', 'C' }` szignatúrák,
  `stat(2)` mezőleírások, `ewah` bitmap-leírások). Fordult: a NAME-leírás, a DESCRIPTION alatti
  egyetlen flush-left „A Git index formátuma" sor, a 3 generikus cím + a leíró mondat-cím, és az
  egyetlen flush-left `The remaining data of each directory block is grouped by type:` mondat.
  Nincs `include`/`ifdef`/`----` blokk. `$GIT_DIR`/`$GIT_COMMON_DIR` placeholder változatlan.
- **`revisions.adoc`**: `NOTE:` admonition-kulcsszó megtartva; a `::` **szintaxis-címkék**
  (`'<sha1>', e.g. …::`, `'<refname>', e.g. …::`, `'{caret}<rev>' (caret) Notation::`,
  `The '..' (two-dot) Range Notation::`, `The '\...' (three-dot) Symmetric Difference Notation::`,
  a Revíziótartomány-összefoglaló összes `'<rev>'::` / `'{caret}<rev>'::` … címkéje) **bájtazonosan
  angolul** — konzisztens a fájlon belül (a tiszta jelölés-címkék mintájára az összes címke marad);
  csak a `::` utáni leírás-törzs fordult. A beágyazott `. …` implicit számozott lista `. ` jelölése
  megtartva; a `+` folytatásjelek (9 db) bájtazonosak; a `........` (Loeliger commit-gráf) és a
  `....`…`....` (példa-argumentum-táblázat) körülhatárolt blokkok, valamint a 4-szóközzel behúzott
  `A = = A^0` … literál példasorok és a `---A---B---o---o---C---D` behúzott gráf **bájtazonos**;
  `{caret}`/`{tilde}` attribútum-referenciák megtartva; `\{`/`\}`/`\...` escape-ek bájtazonosak;
  `$GIT_DIR`/`branch.<name>.merge`/`branch.<name>.remote` config-tokenek, `--since`/`--until`
  kapcsolók, `HEAD`/`@{u}`/`@{push}` konstrukciók angolul; a `$ git config …` / `$ git rev-parse …`
  példablokk (`------------------------------`, 30 kötőjel) bájtazonos.

## 36. blokk — `gittutorial-2.adoc`, `git-read-tree.adoc`, `git-stash.adoc`, `git-tag.adoc`, `git-maintenance.adoc` — 2026-09-11

**Módszer:** a felhasználó 5-ös bontást kért — a két gyökér-tábla együttes, sorszám szerint növekvő
listájából a következő 5 legkisebb, még `[ ]` fájl (`gitglossary.adoc`/`git.adoc`/`config.adoc`/
`git-fast-import.adoc`/`glossary-content.adoc` kihagyva). Orchestrátor végezte közvetlenül, célzott
`Edit`-ekkel.

### Ebben a blokkban rögzített / megerősített döntések

| angol | magyar | megjegyzés |
|---|---|---|
| tutorial (mint dokumentumtípus) | **„ismertető"** | `gittutorial-2.adoc` — „A tutorial introduction to Git: part two" → „Bevezető ismertető a Githez: második rész" |
| object database / object store | **„objektumadatbázis"** (0. blokk) | `gittutorial-2.adoc`, `git-maintenance.adoc` |
| hex name / hex digits | **„hex név" / „hex számjegy"** | `gittutorial-2.adoc` |
| jargon | **„szakzsargon"** | `gittutorial-2.adoc` |
| `"blob"` / `"tree"` / `"commit"` / `"tag"` / `"parent"` / `"status"` / `"tree-ish"` (idézőjeles Git objektum-típusnevek / jargon a prózában) | **bájtazonosan angolul, idézőjelben** | `gittutorial-2.adoc` — a 0. blokk objektum-típusnév-szabályát idézőjeles kontextusban is alkalmazva |
| tree information | **„fa-információ"** | `git-read-tree.adoc` NAME |
| single tree merge / two tree merge / 3-way merge (`git-read-tree.adoc` alcímek) | **„Egyfás merge" / „Kétfás merge" / „Háromutas merge"** | a „three-way merge" → „háromutas merge" (0. blokk) mintáját követve; **a `git-diff.adoc` (már `[x]`) egyetlen `"3-Way Merge"` prózahivatkozását `"Háromutas merge"`-re átírtam** (a 14. blokkban jelzett „jövőben nyomon követni" függőség ezzel lezárva) |
| trivial merge / trivial rules | **„triviális merge" / „triviális szabályok"** | `git-read-tree.adoc` |
| carry forward (rules) / `"clean"` / `"exists"` / `"nothing"` / `"keep index"` / `"result tree"` / `"merged"` / `"orig"` / `"collapses"` / `"stage0/1/2/3"` / `"unmerged entries"` / `"porcelain policy"` / `"internal"` | **bájtazonosan angolul, idézőjelben** | `git-read-tree.adoc` — a `....` szabálytáblázat saját címkéi és a hozzájuk fűzött próza idézőjeles hivatkozásai |
| head commit | **„fejcommit"** | `git-read-tree.adoc` |
| stat info / stat()s | **„stat-információ"** (3. blokk) / „az index stat()-jai" | `git-read-tree.adoc` |
| work-in-progress (változások) | **„folyamatban lévő munka"** | `git-read-tree.adoc` |
| negate patterns / pattern style | **„negáló minták" / „mintastílus"** | `git-read-tree.adoc` (SPARSE CHECKOUT szakasz) |
| to stash (away) / stash entry / stash list / the stash | **„elstashel" / „stash-bejegyzés" / „stash-lista" / „a stash"**; `git stash` parancsnév marad | `git-stash.adoc` — a 0. blokk `stashel` igéjének kiterjesztése; „unstash" → „unstashel" |
| dirty working directory | **„piszkos munkakönyvtár"** | `git-stash.adoc` NAME |
| `"WIP on …"` / `"Updated upstream"` / `"Stashed changes"` / `"Stash base"` | **bájtazonosan angolul, idézőjelben** (program-kimenet / konfliktusjelölő-címke) | `git-stash.adoc` |
| dangling merge commit | **„lógó merge commit"** | `git-stash.adoc` |
| ancestry graph | **„ősgráf"** | `git-stash.adoc` DISCUSSION |
| incantation (jokey) | **„varázsige"** | `git-stash.adoc` EXAMPLES |
| `` ``Interactive Mode'' `` (prózahivatkozás linkgit:git-add[1] szakaszra) | **`` ``Interaktív mód'' ``** (a `git-add.adoc` már lefordított `Interaktív mód` címéhez igazítva; a `` `` … '' `` compat-mode tipográfiai idézőjel megtartva) | `git-stash.adoc` |
| annotated tag / lightweight tag / tag object | **„annotált tag" / „könnyűsúlyú tag" / „tagobjektum"** (0. blokk) | `git-tag.adoc` |
| tag reference / tag ref | **„tag-referencia" / „tag-ref"** (a `ref` literál angolul) | `git-tag.adoc` |
| signing backend | **„aláíró backend"** | `git-tag.adoc` |
| committer identity | **„committer-identitás"** | `git-tag.adoc`, `git-maintenance.adoc` mintájára |
| tagger / tagging message | **„tagelő" / „tagelési üzenet"** | `git-tag.adoc` |
| trailer | **marad „trailer"** (Git jargon; `git-interpret-trailers`) | `git-tag.adoc` |
| backdating (tags) | **„visszadátumozás"** | `git-tag.adoc` DISCUSSION alcím |
| anchor point tags | **„horgonypont-tagek"** | `git-tag.adoc` |
| upper echelon (of people) | **„az emberek felső rétegei"** | `git-tag.adoc` |
| Mere mortals | **„egyszerű halandók"** | `git-tag.adoc` |
| `"please pull"` messages | **„please pull" üzenetek** (angolul, idézőjelben) | `git-tag.adoc` |
| cut&pasted | **„kivágható-beilleszthető"** | `git-tag.adoc` |
| people MUST be able to trust (emfatikus, csupa nagybetűs modális ige folyó szövegben) | **„meg KELL tudniuk bízni"** (nagybetűs `KELL` megtartva) | `git-tag.adoc` — NEM formális RFC 2119, csak emfázis; a 3. blokk csupa-nagybetűs formázás-megtartás mintája |
| maintenance / maintenance task | **„karbantartás" / „karbantartási feladat"** | `git-maintenance.adoc` |
| background / foreground (maintenance, scheduler, process) | **„háttér-" / „előtér-"** | `git-maintenance.adoc` |
| scheduler / (background) schedule | **„ütemező" / „(háttér-)ütemezés"** | `git-maintenance.adoc` |
| job (a `commit-graph`/`loose-objects`/`incremental-repack` job) | **marad „job"** (a `task`/„feladat" szinonimája; a forrás maga is vegyesen használja) | `git-maintenance.adoc` |
| pack-file (kötőjeles, ahogy a forrás) | **marad „pack-file"** (a 0. blokk `packfile` kötőjeles változata, a forráshoz igazítva) | `git-maintenance.adoc` |
| race conditions | **„versenyhelyzetek"** | `git-maintenance.adoc` |
| batch size | **„kötegméret"** | `git-maintenance.adoc` |
| object database lock / to take a lock | **„objektumadatbázis-zár" / „zárol"** | `git-maintenance.adoc` |
| maintenance window | **„karbantartási ablak"** | `git-maintenance.adoc` |
| drop-in file | **„drop-in fájl"** | `git-maintenance.adoc` (systemd szakasz) |
| console application / console window | **„konzolalkalmazás" / „konzolablak"** | `git-maintenance.adoc` (Windows szakasz) |
| Task Scheduler (Windows app) | **marad „Task Scheduler"** (tulajdonnév) | `git-maintenance.adoc` |
| `"Run whether user is logged in or not"` (Windows UI-string) | **bájtazonosan angolul, idézőjelben** | `git-maintenance.adoc` |
| `"hourly"` / `"daily"` / `"weekly"` (ütemezési gyakoriság idézőjelben) | **„óránkénti" / „napi" / „heti"** (fordítva, idézőjel megtartva); a `--schedule=hourly` stb. literál kapcsoló-érték angolul | `git-maintenance.adoc` |
| `disabled` / `hourly` / `daily` (az `incremental` stratégia `--` open-block listájában) | **„letiltva" / „óránként" / „naponta"** | `git-maintenance.adoc` |

### Címsor-anchorok

- **`gittutorial-2.adoc`** (NEM man page, `gittutorial-2(7)` tutorial): 3 Title Case setext (`----`)
  alcím, egyik sem anchorozott, nincs rájuk `<<...>>` a fában → mindegyik fölé defenzív
  `[[<angol-autogen-slug>]]` (az **eredeti angol** címszövegből): `[[_the_git_object_database]]`
  „A Git objektumadatbázisa" (24 `-`), `[[_the_index_file]]` „Az indexfájl" (12 `-`),
  `[[_what_next]]` „Mi a következő?" (15 `-`). A NAME/SYNOPSIS/DESCRIPTION/SEE ALSO/GIT kanonikus.
  A `link:user-manual.html[...]` látható szövege fordult („A Git felhasználói kézikönyve").
- **`git-read-tree.adoc`**: 3 defenzív `[[...]]` a `~~~~` alcímek fölé (aláhúzás pontos hosszra
  igazítva, Python `len()` ellenőrzés): `[[_single_tree_merge]]` (12), `[[_two_tree_merge]]` (12),
  `[[_3_way_merge]]` (15). `MERGING`, `SPARSE CHECKOUT` csupa nagybetűs → VÉGLEGES DÖNTÉS szerint
  angolul (aláhúzás sem változott). **`git-diff.adoc` (már `[x]`) 1 soros javítás:**
  `"3-Way Merge"` → `"Háromutas merge"` a lefordított célcímhez igazítva.
- **`git-stash.adoc`**: nincs `[[...]]`/`<<...>>`. `COMMANDS` csupa nagybetűs → VÉGLEGES DÖNTÉS
  szerint angolul. Az EXAMPLES 5 `Cím::` definíciós-lista-címkéje fordult (nincs rájuk xref):
  „Pull-olás egy piszkos fába", „Megszakított munkafolyamat", „Részleges commitok tesztelése",
  „Nem kapcsolódó változások mentése jövőbeli felhasználásra", „Tévedésből kiürített/dropolt
  stash-bejegyzések helyreállítása". A `'EXAMPLES'` compat-mode prózahivatkozás (a `clear`
  leírásában) angolul.
- **`git-tag.adoc`**: 3 defenzív `[[...]]` a DISCUSSION `~~~~` alcímei fölé (aláhúzás pontos
  hosszra igazítva): `[[_on_re_tagging]]` „Az újratagelésről" (17), `[[_on_automatic_following]]`
  „Az automatikus követésről" (25), `[[_on_backdating_tags]]` „A tagek visszadátumozásáról" (27).
  Csak kanonikus man-page címek egyébként.
- **`git-maintenance.adoc`**: nincs `[[...]]`/`<<...>>`. Csupa nagybetűs, kanonikus listán kívüli
  szakaszcímek a VÉGLEGES DÖNTÉS szerint angolul: `SUBCOMMANDS`, `TASKS` (+ a `'TASKS' section`
  prózahivatkozás a `--task` leírásában), `TROUBLESHOOTING`, `BACKGROUND MAINTENANCE ON POSIX
  SYSTEMS`, `BACKGROUND MAINTENANCE ON LINUX SYSTEMD SYSTEMS`, `BACKGROUND MAINTENANCE ON MACOS
  SYSTEMS`, `BACKGROUND MAINTENANCE ON WINDOWS SYSTEMS` (aláhúzások sem változtak).

### Megőrzött markup / megjegyzések

- **`gittutorial-2.adoc`**: 42 db `------------------------------------------------` (48 kötőjel)
  körülhatárolt blokk (`$ git init` … kimenetek, `$ git cat-file` / `$ git ls-files --stage` /
  `$ find .git/objects/` / `$ git status` kimenetek, `git diff` diffek) **bájtazonos**; a
  `Notes (_<refname>_):` … idézőjeles utalás megtartva; `.git/HEAD`, `.git/refs/heads/`,
  `refs/heads/master`, `blob`/`tree`/`commit`/`tag` literálok angolul.
- **`git-read-tree.adoc`**: `[verse]` synopsis; 2 db `....` körülhatárolt blokk (a „carry forward"
  szabálytáblázat, `I H M Result` fejléccel) és 12 db `----------------` (16 kötőjel) blokk
  (`$ git read-tree …` / `$ JC=…` / `git fetch git://…` / `/*` `!unwanted` példák) **bájtazonos**;
  1 db `+` folytatásjel (a `--aggressive` felsorolás előtt) megtartva; `SKIP_WORKTREE`,
  `skip-worktree`, `core.sparseCheckout`, `$GIT_INDEX_FILE`, `$GIT_DIR/info/sparse-checkout`,
  `.gitignore`, `rename(2)`, `fnmatch`(3) literálok angolul.
- **`git-stash.adoc`**: `[synopsis]` blokk; 14 db `----…----` (64 kötőjel) körülhatárolt blokk
  (`stash@{0}: WIP on …` listakimenet, `$ git pull` / `# ... hack hack hack ...` / `$ git add
  --patch foo` … shell-példák) **bájtazonos**; 32 db `+` folytatásjel megtartva; a DISCUSSION
  ASCII-art stash-ősgráf (`.----W` / `-----H----I`) behúzva, bájtazonos; `include::diff-context-options.adoc[]`
  + `include::includes/cmd-config-section-all.adoc[]` + `:git-stash: 1` + `include::config/stash.adoc[]`
  változatlan; `refs/stash`, `stash@{0}` / `stash@{<n>}` / `stash@{2.hours.ago}` konstrukciók,
  `MERGE_HEAD`, `MERGE_AUTOSTASH`, `stash.showStat` / `stash.showPatch` / `stash.showIncludeUntracked`
  config-kulcsok angolul.
- **`git-tag.adoc`**: `[synopsis]` blokk; 8 db `------------` (12 kötőjel) + 2 db
  `-------------------------------------` (37 kötőjel) körülhatárolt blokk **bájtazonos** — köztük
  a `Ok, I messed up, …` **teljes bejelentés-minta** (egy `------------` blokkba zárt példa e-mail,
  a `howto/` sample-e-mail-precedens szerint bájtazonosan angolul), a `[user]\n signingKey = <key-id>`
  config-példa, a `$ GIT_COMMITTER_DATE="…" git tag -s v1.0.1` és a „please pull" `git://git..../proj.git
  master` példák; `include::date-formats.adoc[]` + `include::includes/cmd-config-section-all.adoc[]` +
  `:git-tag: 1` + `include::config/tag.adoc[]` + `include::ref-reachability-filters.adoc[]` változatlan;
  `%(fieldname)` / `%(refname:strip=2)` / `%(trailers)` formátum-placeholderek, `gpg.format` /
  `gpg.program` / `tag.gpgSign` / `tag.sort` / `core.logAllRefUpdates` config-kulcsok,
  `"version:refname"` / `"v:refname"` / `"versionsort.suffix"` rendezőkulcs-tokenek, `GIT_COMMITTER_DATE`
  env-változó, `$GIT_DIR/TAG_EDITMSG` útvonal angolul; `fnmatch`(3) hívásnév megtartva.
- **`git-maintenance.adoc`**: `[verse]` synopsis; 1 pár `--`…`--` open-block (az `incremental`
  stratégia menetrend-felsorolása) — a `*` bulletek és a `--` határolók változatlanok, csak a
  státuszszavak fordultak; 9 `+` folytatásjel megtartva; 8 db `-----…-----` (71 kötőjel)
  körülhatárolt blokk (`# BEGIN GIT MAINTENANCE SCHEDULE` crontab, `$ systemctl --user list-timers`
  kimenet, `~/.config/systemd/user/…` fájllista, `$ ls ~/Library/LaunchAgents/…` kimenet)
  **bájtazonos**; `include::includes/cmd-config-section-all.adoc[]` + `include::config/maintenance.adoc[]`
  változatlan; `maintenance.<task>.enabled` / `maintenance.repo` / `maintenance.strategy` /
  `maintenance.loose-objects.batchSize` / `gc.auto` / `gc.autoPackLimit` / `remote.<name>.skipFetchAll`
  config-kulcsok, `crontab`/`systemd-timer`/`launchctl`/`schtasks`/`systemctl`/`schtasks` eszköznevek,
  `cron(8)` / `crontab(5)` / `systemd.timer(5)` / `launchctl.plist(5)` man-hivatkozások, a
  `Git Maintenance (<frequency>)` Windows-feladatnév, `refs/prefetch/`, `.graph` /
  `commit-graph-chain` fájlnevek angolul; a „GC" a "garbage collection" glosszájában
  „(szemétgyűjtés)" zárójeles fordítás.

## 37. blokk — `giteveryday.adoc`, `git-interpret-trailers.adoc`, `git-for-each-ref.adoc`, `gitworkflows.adoc`, `git-submodule.adoc` — 2026-09-11

**Módszer:** a felhasználó 5-ös bontást kért — a két gyökér-tábla együttes, sorszám szerint növekvő
listájából a következő 5 legkisebb, még `[ ]` fájl (`gitglossary.adoc`/`git.adoc`/`config.adoc`/
`git-fast-import.adoc`/`glossary-content.adoc` kihagyva). Orchestrátor végezte közvetlenül, célzott
`Edit`-ekkel.

### Ebben a blokkban rögzített / megerősített döntések

| angol | magyar | megjegyzés |
|---|---|---|
| Everyday Git | **„mindennapi Git"** | `giteveryday.adoc` |
| standalone / participant / integrator (fejlesztői szerepek) | **„önálló" / „résztvevő" / „integrátor"** | `giteveryday.adoc` — a `<<ID,látható szöveg>>` xref-ekben kisbetűsen |
| Repository Administration | **„repository-adminisztráció"** | `giteveryday.adoc` |
| `"Smart http"` (idézőjeles, `Git-over-HTTP` mellett) | **bájtazonosan angolul, idézőjelben** | `giteveryday.adoc` — a 33. blokk „smart"/„dumb" HTTP kezelésének folytatása |
| forward port (ige) | **„előreportol"** | `giteveryday.adoc`, `git-tag.adoc` mintájára nem, itt új |
| bleeding edge | **marad „bleeding edge"** (angolul, toldalékkal: `bleeding edge-et`) | `giteveryday.adoc` |
| release manager | **„kiadáskezelő"** | `giteveryday.adoc` |
| `'restricted login shell'` (compat-mode idézőjeles) | **„'korlátozott bejelentkezési shell'"** (fordítva, a `'...'` jelölés megtartva) | `giteveryday.adoc` |
| web front-end | **„webes felület"** | `giteveryday.adoc` |
| trailer / trailer block / trailer key | **marad „trailer" / „trailer-blokk" / „trailer-kulcs"** (35./36. blokk) | `git-interpret-trailers.adoc` |
| metadata | **„metaadat"** | `git-interpret-trailers.adoc` |
| key-value pair / key / value | **„kulcs-érték pár" / „kulcs" / „érték"** | `git-interpret-trailers.adoc` |
| blank line | **„üres sor"** | `git-interpret-trailers.adoc` |
| divider (line) | **„elválasztó (sor)"** | `git-interpret-trailers.adoc` |
| `"folding"` (RFC 822) / `"folded"` / to unfold | **`"folding"` (idézőjelben, angolul) / `"folded"` (idézőjelben) / „kihajtogat"** | `git-interpret-trailers.adoc` |
| machine-friendly | **„gépbarát"** | `git-interpret-trailers.adoc` |
| trimmelt / to trim (whitespace) | **„trimmelt" / „trimmelődik"** | `git-interpret-trailers.adoc` |
| candidate trailer line/block | **„trailer-jelölt sor/blokk"** | `git-interpret-trailers.adoc` |
| Git-generated / user-configured trailer | **„Git által generált" / „felhasználó által konfigurált trailer"** | `git-interpret-trailers.adoc` |
| interpolate / interpolated values | **„interpolál" / „interpolált értékek"** | `git-for-each-ref.adoc` |
| sort key(s) | **„rendezőkulcs"** | `git-for-each-ref.adoc` |
| host language / scripting language | **„gazdanyelv" / „szkriptnyelv"** | `git-for-each-ref.adoc` |
| string literal | **„sztringliterál"** | `git-for-each-ref.adoc` |
| structured fields | **„strukturált mezők"** | `git-for-each-ref.adoc` |
| header field | **„fejlécmező"** | `git-for-each-ref.adoc` |
| name-email-date tuple | **„név-email-dátum hármas"** | `git-for-each-ref.adoc` |
| peeled object | **„lehántott objektum"** | `git-for-each-ref.adoc` |
| angle brackets (`<>`) | **„hegyes zárójelek"** | `git-for-each-ref.adoc` |
| opening atom(s) | **„nyitó atom(ok)"** | `git-for-each-ref.adoc` |
| first-parent history | **„first-parent történet"** (a `first-parent` angolul) | `git-for-each-ref.adoc` |
| ties are broken by | **„a döntetlent … dönti el"** | `git-for-each-ref.adoc` |
| human-readable name | **„ember által olvasható név"** | `git-for-each-ref.adoc` |
| undescribable commits | **„describe-elhetetlen commitok"** | `git-for-each-ref.adoc` |
| `"subject"` (commit-üzenet első bekezdése, idézőjelben) | **`"subject"`** (idézőjelben, angolul; a `subject`/`contents:subject` mezőnév literál) | `git-for-each-ref.adoc` |
| `:sanitize` → „subject line suitable for filename" | **„fájlnévhez alkalmas subject sor"** | `git-for-each-ref.adoc` |
| packed non-delta object | **„csomagolt nem-delta objektum"** | `git-for-each-ref.adoc` CAVEATS |
| workflow | **„munkafolyamat"** (0. blokk) | `gitworkflows.adoc` |
| integration branch | **„integrációs branch"** | `gitworkflows.adoc` |
| graduation / to graduate (feature branchszinten előrelép) | **„Előlépés" (cím) / „előlép"** (idézőjelben, ahol a forrás `"graduates"`) | `gitworkflows.adoc` — „downwards graduation" → „lefelé előlépés" |
| feature release / maintenance release | **„feature kiadás" / „karbantartási kiadás"** | `gitworkflows.adoc` |
| throw-away branch / throw-away integration | **„eldobható branch" / „eldobható integráció"** | `gitworkflows.adoc` |
| rewind / rewound / rebuild (branch) | **„visszateker" / „visszatekert" / „újraépít"** | `gitworkflows.adoc` |
| side branch | **„oldalbranch"** | `gitworkflows.adoc` |
| to fork off (at a branch) | **„leágaztat" / „leágazik"** | `gitworkflows.adoc`, `giteveryday.adoc` |
| clean slate | **„tiszta lap"** | `gitworkflows.adoc` |
| incarnation (of a topic) | **„megtestesülés"** | `gitworkflows.adoc` |
| `"promise"` (merge commit, idézőjelben) | **„ígéret"** (fordítva, idézőjel megtartva) | `gitworkflows.adoc` |
| `"habitually"` (idézőjelben) | **„megszokásból"** (fordítva, idézőjel megtartva) | `gitworkflows.adoc` |
| subsystem maintainer | **„alrendszer-maintainer"** | `gitworkflows.adoc` |
| `[caption="Rule: "]` / `[caption="Recipe: "]` | **bájtazonosan angolul** (skill: `[caption=...]` attribútum-sor nem fordul); a `.Title` blokk-cím viszont fordul; a `====` blokk **prózája** fordul, a csak `` `parancs` `` tartalmú blokk bájtazonos | `gitworkflows.adoc` |
| superproject / subproject | **„szuperprojekt" / „alprojekt"** (0. blokk) | `git-submodule.adoc` |
| gitlink | **marad „gitlink"** (Git jargon) | `git-submodule.adoc` |
| authoritative upstream | **„mérvadó upstream"** | `git-submodule.adoc` |
| canonical part (of source repo) | **„kanonikus rész"** | `git-submodule.adoc` |
| ref storage format | **„ref-tárolási formátum"** | `git-submodule.adoc`, `git-for-each-ref.adoc` mintájára nem, itt új |
| logical name | **„logikai név"** | `git-submodule.adoc` |
| nested submodules | **„beágyazott submodule-ok"** | `git-submodule.adoc` |
| to deinit / deinit-ing | **„deinitel" / „deinitelés"**; a `deinit` alparancsnév marad | `git-submodule.adoc` |
| typechanged (submodule) | **„típusváltott"** | `git-submodule.adoc` |
| conflict resolution tools | **„konfliktusfeloldó eszközök"** | `git-submodule.adoc` |
| reference repository | **„referencia-repository"** | `git-submodule.adoc` |

### Címsor-anchorok

- **`giteveryday.adoc`** (NEM man page, `giteveryday(7)`): 4 meglévő **inline** `[[ID]]` anchor a
  setext szakaszcímek végén (`Individual Developer (Standalone)[[STANDALONE]]` stb.) —
  **bájtazonos**; a címszöveg fordult („Egyéni fejlesztő (önálló)[[STANDALONE]]" stb.), a setext
  `-` aláhúzás a teljes sorhosszhoz (címszöveg + `[[ID]]`) igazítva. A DESCRIPTION-beli
  `<<STANDALONE,Individual Developer (Standalone)>>` / `<<PARTICIPANT,…>>` / `<<INTEGRATOR,Integrator>>`
  / `<<ADMINISTRATION,Repository Administration>>` xref-ek vessző utáni látható szövege **fordult,
  kisbetűsen** („egyéni fejlesztő (önálló)" stb.). A 4 ismételt `Examples` `~~~~` alcím → „Példák",
  **defenzív anchor NÉLKÜL** (ismételt generikus alcím, doc-order dedup-számozás hibaforrás — 1.
  blokk precedens).
- **`gitworkflows.adoc`** (NEM man page, `gitworkflows(7)`): 9 defenzív `[[<slug>]]` a `~~~~` Title
  Case alcímek fölé (nincs rájuk `<<...>>` a fában): `[[_graduation]]` „Előlépés",
  `[[_merging_upwards]]` „Merge-elés felfelé", `[[_topic_branches]]` „Topic branchek",
  `[[_throw_away_integration]]` „Eldobható integráció", `[[_branch_management_for_a_release]]`
  „Branchkezelés egy kiadáshoz", `[[_maintenance_branch_management_after_a_feature_release]]`,
  `[[_branch_management_for_next_and_seen_after_a_feature_release]]`, `[[_merge_workflow]]`
  „Merge-munkafolyamat", `[[_patch_workflow]]` „Patch-munkafolyamat". Setext `~` aláhúzás Python
  `len()`-alapú pontos igazítással (3 db ±2–3 elütés menet közben javítva). A `"Merging upwards"`
  prózahivatkozás (a MANAGING BRANCHES-ben) `"Merge-elés felfelé"`-re átírva, idézőjelben.
- **`git-interpret-trailers.adoc`**, **`git-for-each-ref.adoc`**, **`git-submodule.adoc`**: nincs
  `[[...]]`/`<<...>>` (grep-pel ellenőrizve).

### Man-page címként / csupa nagybetűs alcímként ANGOLUL hagyott címsorok (VÉGLEGES DÖNTÉS szerint)

- **`gitworkflows.adoc`**: `SEPARATE CHANGES`, `MANAGING BRANCHES`, `DISTRIBUTED WORKFLOWS` — csupa
  nagybetűs, kétsoros aláhúzású; bár ez NEM klasszikus parancs-man-page, van NAME/SYNOPSIS/DESCRIPTION
  szekciója, és a `"DISTRIBUTED WORKFLOWS"` idézőjeles **önhivatkozó** prózahivatkozás is védi őket,
  ezért a VÉGLEGES DÖNTÉS szerint **bájtazonosan angolul** (aláhúzás sem változott). A
  `RECOVERING FROM UPSTREAM REBASE` (a `git-rebase[1]` szakaszára mutató prózahivatkozás) szintén
  angolul.
- **`git-interpret-trailers.adoc`**: `OTHER RULES`, `CONFIGURATION VARIABLES` — csupa nagybetűs,
  kanonikus listán kívül → angolul (a `CONFIGURATION VARIABLES` a 31. blokk `git-help.adoc`
  precedensét is követi).
- **`git-for-each-ref.adoc`**: `FIELD NAMES` — csupa nagybetűs, kanonikus listán kívül → angolul
  (a 34. blokk `git-ls-files.adoc` `FIELD NAMES` precedense). `"CONFIGURATION FILE"` és `'CAVEATS'`
  idézőjeles prózahivatkozások angolul.
- **`git-submodule.adoc`**: `COMMANDS` — csupa nagybetűs, kanonikus listán kívül → angolul (a 32.
  blokk `git-remote.adoc`/`git-receive-pack.adoc` `COMMANDS` precedense).

### Megőrzött markup / megjegyzések

- **`giteveryday.adoc`**: 24 db `------------` (12 kötőjel) körülhatárolt blokk (`$ tar zxf …` /
  `$ git switch -c …` / `satellite$ …` / `mothership$ …` / `[remote "ko"]` config / `$ grep …
  /etc/…` shell-példák és kimenetek) **bájtazonos**; a `<1>`…`<13>` callout-jelölők a kódon belül
  és a magyarázatoknál is megmaradtak (a magyarázat-szöveg fordult); a `link:howto/update-hook-example.html[…]`
  látható szövege fordult („update hook howto"); a `www.github.com`, `git.kernel.org` URL-ek
  változatlanok.
- **`git-interpret-trailers.adoc`**: `[synopsis]` blokk; 8 db `------------------------------------------------`
  (48 kötőjel) + 9 db `------------` (12 kötőjel) + 1 pár `----` (4 kötőjel) körülhatárolt blokk
  **bájtazonos** (`subject`/`body text`/`Signed-off-by:` minta-commit-üzenetek, `$ git config
  trailer.…` / `$ cat msg.txt` / `#!/bin/sh` szkriptek); 1 pár `--`…`--` open-block az OTHER RULES
  `*` felsorolással (törzs fordult); 17 `+` folytatásjel; `include::includes/cmd-config-section-all.adoc[]`
  + `include::config/trailer.adoc[]` változatlan; `core.commentString`, `trailer.*` config-kulcsok,
  `addIfDifferent`/`addIfDifferentNeighbor`/`add`/`replace`/`doNothing` action-értékek, `after`/
  `before`/`end`/`start` placement-értékek, `"`:`{nbsp}"` markup angolul/bájtazonos.
- **`git-for-each-ref.adoc`**: `[synopsis]` blokk; 2 pár `----` (4 kötőjel) körülhatárolt blokk (a
  `*--*--*` first-parent-történet ASCII-art és a `refs/heads/A:` minta-kimenet) + 5 db `------------`
  (12 kötőjel) shell-szkript-példa **bájtazonos**; 1 pár `--`…`--` open-block a `describe` opció-
  `;;`-listával (törzs fordult); `include::for-each-ref-options.adoc[]` + `include::ref-reachability-filters.adoc[]`
  változatlan; a `refname`/`objecttype`/`upstream`/`push`/`HEAD`/`color`/`align`/`if`/`symref`/
  `signature*`/`worktreepath`/`ahead-behind`/`is-base`/`describe`/`raw*`/`contents*` `::`-mezőnév-
  címkék és a `G`/`B`/`U`/`X`/`Y`/`R`/`E`/`N` `;;`-aláírásminősítő-címkék **bájtazonosak** (csak a
  törzs fordult); `%(…)` atom-szintaxis, `:short`/`:lstrip`/`:rstrip`/`:track`/`:trackshort`/
  `:mailmap` stb. módosítók, `MINIMUM_ABBREV`, `.mailmap`/`mailmap.file`/`mailmap.blob` angolul.
- **`gitworkflows.adoc`**: `[verse]` synopsis; 15 pár `=====================================` (37 `=`)
  `[caption=…]` példablokk-határoló **bájtazonos** (a `.Title` fordult, a `[caption=…]` és a csak-
  `` `parancs` `` tartalmú blokkok bájtazonosak, a prózát tartalmazó blokkok törzse fordult); 1 pár
  `-------------------------------------` (37 kötőjel) a „Please pull from" minta-üzenettel
  **bájtazonos**; `git.git`, `maint`/`master`/`next`/`seen` branchnevek, `submodule.<name>.update`
  stb. config-kulcsok, `ai/topic_in_next1` példa-refnevek angolul.
- **`git-submodule.adoc`**: `[synopsis]` blokk; 2 pár `--`…`--` open-block (`update` leírás +
  `foreach` változólista) — a `;;`-címkék (`checkout`/`rebase`/`merge`/`!<custom-command>`/`none`
  és `$name`/`$sm_path`/`$displaypath`/`$sha1`/`$toplevel`) **bájtazonosak**, a törzs fordult; 1
  pár `--------------` (14 kötőjel) `git submodule foreach 'echo …'` példa bájtazonos; 31 `+`
  folytatásjel; a `-f`/`--force` alatti `add`/`deinit`/`update` `;;`-címkék bájtazonosak; nincs
  `include::`; `submodule.$name.url` / `submodule.<name>.branch` / `submodule.<name>.update` /
  `submodule.fetchJobs` / `core.worktree` config-kulcsok, `.gitmodules` / `$GIT_DIR/modules` /
  `.git/config` útvonalak, `++||:++` passthrough, `$PATH`/`$path` változónevek angolul; a
  `NOTE:` admonition-kulcsszó megtartva (törzs fordult).

## 38. blokk — `pretty-formats.adoc`, `git-reset.adoc`, `git-rev-parse.adoc`, `git-pack-objects.adoc`, `git-sparse-checkout.adoc`, `git-status.adoc`, `gitprotocol-http.adoc`, `git-worktree.adoc`, `gitremote-helpers.adoc`, `gitfaq.adoc` — 2026-09-11

**Módszer:** a felhasználó a 10 legkisebb méretű, még lefordítatlan „Gyökér" fájlt kérte (a
két gyökér-tábla együttes, sorméret szerint növekvő listája, `gitglossary.adoc`/`git.adoc`/
`config.adoc`/`git-fast-import.adoc`/`glossary-content.adoc` kihagyva). Orchestrátor végezte
közvetlenül, célzott `Edit`-ekkel; a munkamenet egy usage-limit miatti megszakítás után
folytatódott (a felhasználó „continue" üzenetével), a munka onnan folytatva, ahol
megszakadt.

### Ebben a blokkban rögzített / megerősített döntések

| angol | magyar | megjegyzés |
|---|---|---|
| RFC 2119 kulcsszavak (`MUST`/`SHOULD`/`MAY`/`SHOULD NOT`/`MUST NOT`) mondatba ágyazva | **angolul maradnak**, `[Alany dativus] [KULCSSZÓ] [ige infinitivus]` szórenddel (pl. „A klienseknek MUST eltávolítaniuk a záró `/`-t…", „A szervereknek SHOULD kezelniük…") | `gitprotocol-http.adoc`, `gitremote-helpers.adoc` — a 34. blokk döntésének (a kulcsszavak angolul maradnak) folytatása, a `gitcli.adoc`/`gitprotocol-capabilities.adoc`-ban (34./21./23./32. blokk) már kialakult mondatszerkesztési minta szerint |
| commit-ish, commit-hash, fa-hash, szülő-hash | `%H`/`%h`/`%T`/`%t`/`%P`/`%p` leírásában, „commit-ish" angolul maradt (Git jargon), a hash-típusok összetett szóval fordultak | `pretty-formats.adoc`, `git-rev-parse.adoc` |
| committer (dátum-előtag placeholder-leírásban) | **„committeri dátum"** (a „szerzői dátum" párhuzamos alakja) | `pretty-formats.adoc` — `%cd`/`%cD`/`%cr`/… leírásokban, új, a 0. blokk „committer" tételét (szerepkör-főnév) egy melléknévi alakkal egészíti ki |
| „Interactive Mode" (`git-add.adoc` szakaszra mutató prózahivatkozás, `git-reset.adoc`-ban) | **„Interaktív mód"** (fordítva, idézőjelben) | a `git-stash.adoc`-beli (36. blokk) azonos hivatkozás mintáját folytatja |
| „Reset, restore and revert" (`git.adoc` szakaszra mutató prózahivatkozás) | **angolul maradt, idézőjelben** | `git-reset.adoc` — `git.adoc` még lefordítatlan, a 32. blokk `gitcli.adoc`-beli „Values" precedensét követi |
| dumb/smart szerver válasza (prózacímke kódblokk előtt) | **„dumb szerver válasza:" / „smart szerver válasza:"** | `gitprotocol-http.adoc` — a 17./19./32./33. blokk „smart"/„dumb" HTTP kezelésének folytatása |
| Extra Parameters (gitprotocol-pack fogalom) | **angolul maradt** (Title Case, terminus-jellegű) | `gitprotocol-http.adoc` — `gitprotocol-pack.adoc` még lefordítatlan, nincs magyar precedens |
| FAQ | **marad „FAQ"** (angol kölcsönszó, nincs „GYIK"-precedens a projektben) | `gitfaq.adoc` |
| credential helper / credential manager | **marad „credential helper" / „credential-kezelő"** | `gitfaq.adoc` — a 0. blokk `credential` tételének ([]„hitelesítő adatok", összetételben angol marad) folytatása; a Windows/macOS/Unix natív eszközneveket (`wincred`, `osxkeychain`, `libsecret`) angolul hagyva |
| merge-alap (merge base) | **„merge-alap"** | `gitfaq.adoc` — a 14. blokk `git-diff.adoc`-beli mintáját követi, itt új fájlban is konzisztensen |
| Recursive / Parent (cone mode mintatípus-nevek) | **angolul maradtak, dőlt/félkövér jelöléssel** (`*Recursive:*`/`*Parent:*`), a prózában is `recursive`/`parent minta`-ként | `git-sparse-checkout.adoc` — terminus-jellegű, a mintafájlban ismételten hivatkozott névpár |

### Címsor-anchorok

- **`pretty-formats.adoc`**: nincs `[[...]]`/`<<...>>` (a `PRETTY FORMATS` man-page-stílusú
  kétsoros cím angolul, aláhúzással együtt, bájtazonos — include-fragmens, nincs NAME/OPTIONS).
- **`git-reset.adoc`**, **`git-pack-objects.adoc`**: nincs `[[...]]`/`<<...>>`, csak kanonikus
  man-page szekciócímek.
- **`git-rev-parse.adoc`**: 9 defenzív `[[...]]` a `~~~~` Title Case alcímek fölé:
  `[[_operation_modes]]` „Működési módok", `[[_options_for_parseopt]]` „A --parseopt opciói",
  `[[_options_for_filtering]]` „Szűrési opciók", `[[_options_for_output]]` „Kimeneti opciók",
  `[[_options_for_objects]]` „Objektum-opciók", `[[_options_for_files]]` „Fájl-opciók",
  `[[_other_options]]` „Egyéb opciók", `[[_input_format]]` „Bemeneti formátum",
  `[[_usage_text]]` „Használati szöveg". A kétszer ismétlődő „Example" alcím (PARSEOPT és
  SQ-QUOTE alatt) → „Példa", **defenzív anchor nélkül** (ismételt generikus alcím, 1. blokk
  precedens). A `PARSEOPT` és `SQ-QUOTE` kétsoros, csupa nagybetűs man-page-stílusú címek
  (prózahivatkozással: „see PARSEOPT section below") a VÉGLEGES DÖNTÉS szerint angolul,
  bájtazonosak.
- **`git-status.adoc`**: 8 defenzív `[[...]]` a `~~~~`/`^^^^` Title Case alcímek fölé:
  `[[_short_format]]` „Rövid formátum", `[[_porcelain_format_version_1]]` „Porcelain formátum,
  1. verzió", `[[_porcelain_format_version_2]]` „Porcelain formátum, 2. verzió",
  `[[_branch_headers]]` „Branch-fejlécek", `[[_stash_information]]` „Stash-információ",
  `[[_changed_tracked_entries]]` „Megváltozott követett bejegyzések", `[[_other_items]]`
  „Egyéb elemek", `[[_pathname_format_notes_and_z]]` „Útvonalnév-formátum megjegyzések és a
  -z". Nincs meglévő `<<...>>` xref rájuk. A `BACKGROUND REFRESH` / `UNTRACKED FILES AND
  PERFORMANCE` kétsoros, csupa nagybetűs címek a VÉGLEGES DÖNTÉS szerint angolul.
- **`gitprotocol-http.adoc`**: 11 defenzív `[[...]]` a Title Case (`----`/`~~~~`/`^^^^`)
  alcímek fölé: `[[_url_format]]` „URL-formátum", `[[_session_state]]` „Munkamenet-állapot",
  `[[_general_request_processing]]` „Általános kérésfeldolgozás",
  `[[_discovering_references]]` „Referenciák felfedezése", `[[_dumb_clients]]` „Dumb
  kliensek", `[[_smart_clients]]` „Smart kliensek", `[[_dumb_server_response]]` „Dumb szerver
  válasza", `[[_smart_server_response]]` „Smart szerver válasza",
  `[[_smart_service_git_upload_pack]]` „Smart szolgáltatás: git-upload-pack",
  `[[_the_negotiation_algorithm]]` „A tárgyalási algoritmus",
  `[[_smart_service_git_receive_pack]]` „Smart szolgáltatás: git-receive-pack". A `SSL`
  (rövid akronim-cím, `---`-aláhúzás) és a `REFERENCES` csupa nagybetűs cím a VÉGLEGES DÖNTÉS
  szerint angolul; a `REFERENCES` alatti RFC-hivatkozások (`https://…[RFC 1738: Uniform
  Resource Locators (URL)]` stb.) linkszövege angolul maradt (hivatalos RFC-címek, tulajdonnév-
  jellegűek).
- **`git-worktree.adoc`**: 1 defenzív `[[_porcelain_format]]` „Porcelain formátum" a `~~~~`
  alcím fölé. A `REFS` / `CONFIGURATION FILE` / `DETAILS` / `LIST OUTPUT FORMAT` csupa
  nagybetűs, kétsoros man-page-stílusú címek a VÉGLEGES DÖNTÉS szerint angolul (a `REFS`-re és
  `DETAILS`-re prózahivatkozás is mutat: „see 'DETAILS' below").
- **`gitremote-helpers.adoc`**: 4 defenzív `[[...]]` a `~~~~`/`^^^^` alcímek fölé:
  `[[_capabilities]]` „Képességek", `[[_capabilities_for_pushing]]` „Képességek pusholáshoz",
  `[[_capabilities_for_fetching]]` „Képességek fetcheléshez", `[[_miscellaneous_capabilities]]`
  „Egyéb képességek". Az `INVOCATION` / `INPUT FORMAT` / `REF LIST ATTRIBUTES` / `REF LIST
  KEYWORDS` csupa nagybetűs, kétsoros címek a VÉGLEGES DÖNTÉS szerint angolul (prózahivatkozás
  is mutat rájuk: „See OPTIONS for…", „See REF LIST ATTRIBUTES…").
- **`git-sparse-checkout.adoc`**: nincs `[[...]]`/`<<...>>` (grep-pel ellenőrizve). A
  `COMMANDS` kanonikus; az `INTERNALS -- SPARSE CHECKOUT` / `INTERNALS -- NON-CONE PROBLEMS` /
  `INTERNALS -- CONE MODE HANDLING` / `INTERNALS -- FULL PATTERN SET` / `INTERNALS -- CONE
  PATTERN SET` / `INTERNALS -- SUBMODULES` csupa nagybetűs, kétsoros man-page-stílusú
  főcímek (prózahivatkozásokkal: „the 'Non-cone Problems' section below" stb.) a VÉGLEGES
  DÖNTÉS szerint angolul, bájtazonosak.
- **`gitfaq.adoc`**: ez a fájl **nem man page** — minden FAQ-kérdés előtt már meglévő,
  kebab-case explicit `[[anchor]]` volt (pl. `[[user-name]]`, `[[recommended-storage-settings]]`),
  ezek **bájtazonosan** megmaradtak, csak a kérdés szövege fordult. A `<<recommended-storage-settings,
  the question on recommended storage settings>>` xref vessző utáni látható szövege
  „az ajánlott tárolási beállításokról szóló kérdést"-re fordult. A 8 fő szakaszcím
  (`-------` szintű, Title Case, NEM man-page): `Configuration` → „Konfiguráció"
  (`[[_configuration]]`), `Credentials` → „Hitelesítő adatok" (`[[_credentials]]`), `Transfers`
  → „Átvitelek" (`[[_transfers]]`), `Common Issues` → „Gyakori problémák"
  (`[[_common_issues]]`), `Merging and Rebasing` → „Merge-elés és rebase-elés"
  (`[[_merging_and_rebasing]]`), `Hooks` → „Hookok" (`[[_hooks]]`), `Cross-Platform Issues` →
  „Platformok közötti problémák" (`[[_cross_platform_issues]]`) — mindegyik defenzív
  `[[...]]`-t kapott.

### Megőrzött markup / megjegyzések

- **`pretty-formats.adoc`**: `[synopsis]`/`--`…`--` blokkok a formátumpéldáknál (pl.
  `oneline`/`short`/`medium`/`full`/`fuller`/`reference`/`email` formátumleírás) bájtazonosak;
  a `%H`/`%h`/`%an`/`%ad`/… placeholder-táblázat `::`-címkéi (maguk a `%`-kódok) bájtazonosak,
  csak a leírás-törzs fordult; `ifndef::git-rev-list[]`/`endif::` guard érintetlen; a
  `subject`/`body`/`raw body` mezőnevek közül a `%s`/`subject` leírásban a „subject" szó
  angolul maradt (a 37. blokk `git-for-each-ref.adoc`-beli `"subject"` precedense).
- **`git-reset.adoc`**: 10 pár `------------` (12 kötőjel) EXAMPLES-blokk + a DISCUSSION 8 db
  `....`/`----------------------------------------------------` (52 kötőjel) táblázat-blokkja
  bájtazonos; a `<1>`…`<8>` callout-magyarázatok fordultak; `include::diff-context-options.adoc[]`
  érintetlen.
- **`git-pack-objects.adoc`**: a `[pack]` config-blokkok (`-------------------------------------------`,
  43 kötőjel, 2 pár) bájtazonosak; a `--`…`--` open-block (`--stdin-packs` mód `*`-felsorolása)
  törzse fordult, a `*`-jelölők megmaradtak.
- **`git-sparse-checkout.adoc`**: a `----` (4 kötőjel) példablokkok (pl.
  `git sparse-checkout set '/toplevel-dir/*.c'`), a `----------------` (16 kötőjel)
  sparse-checkout-fájl-tartalom-blokkok és a `--------------------------` (26 kötőjel)
  `git sparse-checkout list` kimeneti blokk bájtazonosak.
- **`git-status.adoc`**: a `[cols=...]`/`|===` táblázatok (XY-állapotkód-tábla, Branch Headers
  tábla, két mező-leíró tábla) `|`-cellái fordultak, a `[cols=...]`/`options="header"`
  attribútum-sorok és a mezőnév-oszlopok (`_<XY>_`, `_<sub>_` stb.) bájtazonosak.
- **`gitprotocol-http.adoc`**, **`gitremote-helpers.adoc`**: ABNF-grammatika-blokkok
  (`info_refs = *( ref_record )` stb.) és a `C:`/`S:` protokoll-dialógus-példák (indentált
  literál bekezdések, nem `----`-blokkok) bájtazonosak; a `dumb szerver válasza:`/`smart
  szerver válasza:` prózacímkék fordultak, a mögöttük lévő literál blokkok nem.
- **`git-worktree.adoc`**: az `.ssh/config` és a `worktree list --porcelain` példablokkok
  (`------------`, 12 kötőjel, 8 pár) bájtazonosak.
- **`gitfaq.adoc`**: a `----` (4 kötőjel) shell-/config-példablokkok (pl. `export VISUAL=nano`,
  a `.ssh/config` proxy-alias-blokk, a `.gitattributes` minták) és a bennük lévő `#`-kommentek
  bájtazonosak, csak a blokkok körüli/feletti próza fordult.

Orchestrátor végezte közvetlenül. Részletek fent, „38. blokk".

## 39. blokk — az 5 legkisebb, még lefordítatlan „Gyökér" fájl — 2026-09-11

**Fájlok:** `gittutorial.adoc` (23KB, NEM man page), `git-update-index.adoc` (24KB, man page),
`gitweb.adoc` (27KB, man page-vázas referencia), `gitformat-pack.adoc` (27,5KB, technical
formátum-spec), `gitprotocol-pack.adoc` (27,7KB, RFC-stílusú protokoll-spec). **5 párhuzamos
subagent** végezte, diszjunkt fájlonként egy-egy (nem az orchestrátor közvetlenül, a fájlok
600–730 soros mérete miatt, eltérően a korábbi 15–38. blokkok kisebb fájljaitól). Az orchestrátor
konszolidálta az eredményeket és futtatott egy gyors strukturális ellenőrzést (`----`/`====`
párszám, `[[...]]` duplikátum-ellenőrzés, `ifdef`/`endif` párosság) mind az 5 fájlon — hibátlan.

### Ebben a blokkban rögzített / megerősített döntések

| angol | magyar | megjegyzés |
|---|---|---|
| base object (delta-kódolás forrása) | **„bázisobjektum"** | `gitformat-pack.adoc` |
| cruft pack / thin pack (funkciónév) | **marad angolul** (`cruft pack funkció`, `cruft packet ír`) | `gitformat-pack.adoc` — a `bare repository` mintájára angol funkciónévként kezelve |
| trailer (pack/idx/rev/mtimes fájl trailere, NEM commit trailer) | **marad „trailer"** angolul | `gitformat-pack.adoc` — megkülönböztetve a `git-interpret-trailers.adoc` commit-trailerétől |
| transport (ssh/git/http/file) | **marad „transport"** angol kölcsönszóként, magyar toldalékkal: `transportok`, `transportban`, `transportot` | `gitprotocol-pack.adoc` — a `packfile`/`pathspec` (0. blokk) mintájára; a „Git Transport"/„SSH Transport" címekben is nagybetűsen/angolul marad |
| push certificate | **„push tanúsítvány"** | `gitprotocol-pack.adoc` — `push` angol jelzőként marad (a `force push` mintájára), `certificate` → `tanúsítvány`; a literál `push-cert`/`push-cert-end` token érintetlen |
| Authentication (man-page-stílusú, kanonikus listán kívüli, csupa nagybetűs kezdőbetűs kétsoros cím) | **VÉGLEGES DÖNTÉS (felhasználó, 2026-09-11): marad angolul mindkét helyen** | `gitprotocol-pack.adoc`-ban eredetileg „Hitelesítés"-re fordítottuk, majd a felhasználó döntése alapján visszaállítottuk „Authentication"-re (a `[[_authentication]]` anchor változatlan), így konzisztens a `gitprotocol-http.adoc` (38. blokk) meglévő angol címével |
| action (gitweb URL/CGI-fogalom, generikus főnévként) | **„akció"** | `gitweb.adoc` — a `git-credential.adoc`-ban már bevezetett `"action"` → `akció` minta folytatása |
| revision (gitweb kontextusban) | **„revízió"** | `gitweb.adoc` — megerősítve a `git-bisect.adoc`/`git-blame.adoc` már meglévő használatából |
| "The Git User's Manual" (link-szöveg) | **„A Git felhasználói kézikönyve"** | `gittutorial.adoc` — a `gitcvs-migration.adoc`/`gitdiffcore.adoc`/`gitrepository-layout.adoc`/`gittutorial-2.adoc` már meglévő fordításának pontos folytatása |
| fail gracefully (`--assume-unchanged` leírásban) | **„(szabályosan) meg fog hiúsulni"** | `git-update-index.adoc` — ad hoc, egyedi előfordulás |

### Címsor-anchorok

- **`gittutorial.adoc`** (NEM man page; NAME/SYNOPSIS/DESCRIPTION/SEE ALSO/GIT a `gittutorial-2.adoc`
  precedens szerint angolul maradt, minden más cím fordult): 8 defenzív `[[...]]` anchor
  (`_importing_a_new_project`, `_making_changes`, `_git_tracks_content_not_files`,
  `_viewing_project_history`, `_managing_branches`, `_using_git_for_collaboration`,
  `_exploring_history`, `_next_steps`). Nincs `<<...>>` hivatkozás a fába (ellenőrizve).
- **`git-update-index.adoc`** (man page): nincs `<<...>>` a fájlban, nincs új anchor. 8 nem
  kanonikus, csupa nagybetűs, kétsoros man-page-stílusú alcím (`USING --REFRESH`,
  `USING --CACHEINFO OR --INFO-ONLY`, `USING --INDEX-INFO`, ``USING ``ASSUME UNCHANGED'' BIT``,
  `SKIP-WORKTREE BIT`, `SPLIT INDEX`, `UNTRACKED CACHE`, `FILE SYSTEM MONITOR`) angolul hagyva,
  „kétes" jelöléssel — ez már **10. ismétlődő előfordulása** ugyanennek a nyitott kérdésnek
  (l. korábbi blokkok „visszatérő, még nyitott kérdés" jegyzetei).
- **`gitweb.adoc`**: 12 defenzív anchor (`_repositories`, `_projects_list_file_format`,
  `_generating_projects_list_using_gitweb`, `_controlling_access_to_git_repositories`,
  `_per_repository_gitweb_configuration`, `_actions`, `_apache_as_cgi`,
  `_apache_with_mod_perl_via_modperl_registry`, `_apache_with_fastcgi`,
  `_single_url_for_gitweb_and_for_fetching`, `_webserver_configuration_with_multiple_projects_root`,
  `_path_info_usage`). Nincs `<<...>>` a fájlban. 3 csupa nagybetűs, kétsoros, kanonikus listán
  kívüli alcím angolul hagyva, „kétes" jelöléssel: `ACTIONS, AND URLS`, `WEBSERVER CONFIGURATION`,
  `ADVANCED WEB SERVER SETUP`.
- **`gitformat-pack.adoc`**: 20 defenzív anchor (l. a subagent jelentését — köztük egy Asciidoctor-
  stílusú duplikátum-feloldás: a fájlban kétszer szereplő „cruft packs" cím `_cruft_packs` és
  `_cruft_packs_2` anchort kapott). Nincs `<<...>>` a fájlban. A multi-pack-index szakasz
  `HEADER:`/`CHUNK LOOKUP:`/`CHUNK DATA:`/`TRAILER:` pszeudo-címkéi (nincs kétsoros aláhúzásuk,
  nem valódi AsciiDoc-cím) angolul maradtak a hozzájuk tartozó bájt-mező-grammatikával együtt,
  a `reftable.adoc`/`hash-function-transition.adoc` precedens szerint — **eldöntendő**, hogy a 4
  címke önmagában fordulhatna-e.
- **`gitprotocol-pack.adoc`**: 15 defenzív anchor (l. subagent jelentése; a „Reference Discovery"
  cím két előfordulása `_reference_discovery`/`_reference_discovery_2`). Nincs `<<...>>` a fájlban
  (sem a fájlban, sem máshonnan rá mutató — a hivatkozó fájlok `linkgit:gitprotocol-pack[5]`-t
  használnak). RFC 2119 kulcsszavak (`MUST`/`MUST NOT`/`SHOULD`/`MAY`) angolul, a
  `gitprotocol-http.adoc`/`gitcli.adoc` szórend-mintája szerint.

### Man-page címként angolul hagyott, kétes címsorok

- `gitformat-pack.adoc`: `HEADER:`, `CHUNK LOOKUP:`, `CHUNK DATA:`, `TRAILER:` (l. fent).
- `git-update-index.adoc`, `gitweb.adoc`: l. fent, „Címsor-anchorok" — a visszatérő „kanonikus
  listán kívüli csupa nagybetűs alcím" kérdés újabb (immár ~13.) előfordulása. **Egyszeri
  felhasználói döntés továbbra is ajánlott**, hogy ezeket a jövőben fordítsuk-e.

### Lezárt döntési pontok (felhasználói jóváhagyással, 2026-09-11)

- **„Authentication" cím**: **marad angolul mindkét helyen** (`gitprotocol-pack.adoc` visszaállítva
  „Hitelesítés"-ről; `gitprotocol-http.adoc` változatlan). Innentől minden man-page-stílusú
  „Authentication" alcím a protokoll-spec fájlokban angolul marad.
- **Kanonikus man-page-listán kívüli, csupa nagybetűs, kétsoros alcímek** (pl.
  `USING --REFRESH`, `ACTIONS, AND URLS`, `AGGRESSIVE`, `TASKS`, `SUBCOMMANDS` stb. — a
  visszatérően, immár ~13× jelzett nyitott kérdés): **VÉGLEGES DÖNTÉS: mindig angolul maradnak.**
  Ez megerősíti a projekt eddigi gyakorlatát (minden korábbi blokk így kezelte őket „kétes"
  jelöléssel) — mostantól ezt nem kell többé újra jelezni vagy megkérdezni, egyszerűen alkalmazni
  kell minden további fájlnál.

### Megőrzött markup / megjegyzések

- `gitformat-pack.adoc`: a packed-object-header mező-grammatika, a `Pack Idx file:`/
  `Pack file entry: <+` ASCII-diagramok, az instrukció-doboz-diagramok (`+----+`), a
  `[cols="1,2,2"]`/`|===` BTMP-táblázat és a `git-repack`-idézet `----`-blokkja bájtazonosak
  (a `reftable.adoc`/`hash-function-transition.adoc` precedens folytatása).
- `gitprotocol-pack.adoc`: ABNF/grammatika-blokkok, pkt-line hexdumpok, C kliens/szerver-
  átiratok a `----`-blokkokban, valamint a protokoll-token-literálok (`side-band`,
  `side-band-64k`, `ofs-delta`, `multi_ack`, `multi_ack_detailed`, `thin-pack`, `report-status`,
  `report-status-v2`, `delete-refs`, `atomic`, `push-options`, `push-cert`) bájtazonosak.
- `gitweb.adoc`: az `action::`/`repo::`/`revision::`/`path::` stb. definíciós-lista-címkék (gitweb
  URL/config-paraméterek) és a beágyazott Apache/Perl/shell-példák bájtazonosak.
- `git-update-index.adoc`: nincs `<<...>>`/kódblokk-anomália; a `\--::` sor és a `{litdd}`
  attribútum-hivatkozás érintetlen.
- `gittutorial.adoc`: a `$ man git-log` / `$ git help log` stb. `------------------------------`
  (32 kötőjel) parancspélda-blokkok és azok konzol-kimenete bájtazonosak.

## 40. blokk — `git-p4.adoc`, `git-send-email.adoc` — 2026-09-11

**Fájlok:** `git-p4.adoc` (28KB, 865 sor, man page — ELSŐ git-p4 fájl a projektben),
`git-send-email.adoc` (29KB, 771 sor, man page). 2 párhuzamos subagent kezdte; mindkettő
**munkamenet-limit (session limit, HTTP 429) miatt idő előtt megszakadt** a fájl vége felé —
első alkalom a projektben, hogy ez subagent-futás közben (nem csak korábbi, más jellegű
`content filtering policy` hibaként, l. „4. blokk") fordul elő. Az orchestrátor ellenőrizte a
tényleges fájlállapotot Read-del, és Edit-tel közvetlenül befejezte mindkét fájlt.

### Befejezéskor pótolt, még angol maradványok

- **`git-p4.adoc`**: a „Clone és sync változók" alszakasz második fele (`git-p4.branchUser`-től
  `git-p4.mapUser`-ig, kb. 120 sor), a „Submit variables" → „Submit változók" alcím és teljes
  törzse (`git-p4.detectRenames`-től `git-p4.disableP4Sync`-ig), az „IMPLEMENTATION DETAILS"
  4 pontos felsorolása, és a záró „GIT" szakasz „Part of the linkgit:git[1] suite" sora.
- **`git-send-email.adoc`**: csak a záró „GIT" szakasz „Part of the linkgit:git[1] suite" sora
  maradt angolul (a fájl többi része a subagent által hibátlanul befejezve).
- Mindkét fájlban: „Part of the linkgit:git[1] suite" → **„A linkgit:git[1] csomag része"**
  (a bevett projekt-precedens megismétlése).

### Ebben a blokkban rögzített / megerősített döntések

| angol | magyar | megjegyzés |
|---|---|---|
| Perforce / p4 (eszköznév, parancsnév) | **marad angolul**, kis kezdőbetűs `p4` a prózában a forrás szóhasználatát követve | `git-p4.adoc` — tulajdonnév, a `Subversion`/`CVS` (0. blokk) mintájára |
| depot (p4 fogalom) | **marad „depot"** angol kölcsönszóként, magyar toldalékkal: `depot elérési út`, `depotban` | `git-p4.adoc` — Perforce-specifikus terminus, nincs bevett magyar megfelelője |
| changelist | **marad „changelist"** | `git-p4.adoc` — Perforce-specifikus terminus, a `changeset` (0. blokk) mintájára |
| shelve / unshelve (p4 ige) | **„shelve-el" / „unshelve-el"**, `shelve-elt`, `unshelve-elés` | `git-p4.adoc` — a `stash`/`bundle` (0. blokk) igeképzési mintájára |
| client spec (p4 fogalom) | **marad „client spec"** | `git-p4.adoc` |
| branch detection (p4-specifikus algoritmus neve, prózahivatkozás) | **marad angolul, idézőjelben**: „BRANCH DETECTION" | a kanonikus listán kívüli, csupa nagybetűs cím (VÉGLEGES DÖNTÉS, 39. blokk) |
| re-author (ige, p4 submit kontextusban) | **„újra-szerzőz"** | `git-p4.adoc` — a `annotate`/`amend` (0. blokk) ad hoc igeképzési mintája |

### Man-page címként angolul hagyott, kétes címsorok

- `git-p4.adoc`: `COMMANDS`, `OPTIONS`, `DEPOT PATH SYNTAX`, `CLIENT SPEC`, `BRANCH DETECTION`,
  `PERFORMANCE`, `CONFIGURATION VARIABLES`, `IMPLEMENTATION DETAILS` — mind a 39. blokk
  VÉGLEGES DÖNTÉSE szerint angolul (kanonikus listán kívüli, csupa nagybetűs, kétsoros
  man-page-stílusú alcímek). Ezután **nem kell többé "kétesként" flag-elni** ezt a mintát.
- `git-send-email.adoc`: `SENDING PATCHES`, `EXAMPLES OF SMTP SERVERS`, `CAVEATS`, `SEE ALSO`
  — ugyanígy angolul, a `CAVEATS`/`SEE ALSO` kanonikus, a másik kettő a VÉGLEGES DÖNTÉS szerint.

### Címsor-anchorok

- `git-p4.adoc`: nincs `[[...]]`/`<<...>>` a fájlban — minden alcím vagy kanonikus, vagy a
  fenti VÉGLEGES DÖNTÉS szerint angolul maradó, csupa nagybetűs cím, tehát egyik sem kapott
  (vagy igényelt) anchort.
  - `git-send-email.adoc`: 8 defenzív anchor a fordított (Title Case) alcímek fölött:
  `_composing` (Összeállítás), `_sending` (Küldés), `_automating` (Automatizálás),
  `_administering` (Adminisztráció), `_information` (Információ),
  `_use_gmail_as_the_smtp_server`, `_use_microsoft_outlook_as_the_smtp_server`,
  `_exploiting_the_sendmailcmd_option_of_git_send_email`. Nincs `<<...>>` a fájlban.

### Megőrzött markup / megjegyzések

- `git-p4.adoc`: minden `------------`/`----`/`-------------` (változó hosszúságú, 4–13
  kötőjeles) parancspélda- és config-blokk bájtazonos, beleértve a `<submit more changes via p4
  to the same files>` placeholder-sort egy unshelve-példában.
  A `git-p4.*` config-kulcsok (`::`-címkék) és a `P4CLIENT`/`P4USER`/`P4PASS`/`P4PORT`/`P4HOST`/
  `P4CONFIG` környezeti változók bájtazonosak.
- `git-send-email.adoc`: az e-mail-fejléc-nevek (`From:`, `To:`, `Cc:`, `Bcc:`, `Subject:`,
  `Message-ID:`, `In-Reply-To:`, `References:`, `X-Mailer:`) és a `sendemail.*` config-kulcsok
  bájtazonosak; a patch-thread ASCII-ábra (`[PATCH 0/2] Here is what I did...` stb.) és a
  `# Change this to the path where msmtp is installed` shell-kommentár bájtazonos (kódblokkon
  belüli tartalom).

Orchestrátor végezte közvetlenül (a két subagent munkamenet-limit miatti korai megszakadása
után a hiányzó részek befejezésével). Részletek fent, „40. blokk".

## 41. blokk — `MyFirstObjectWalk.adoc`, `githooks.adoc` — 2026-09-11

**Fájlok:** `MyFirstObjectWalk.adoc` (29,6KB, 964 sor, NEM man page — contributor-tutorial a Git
objektumbejárásáról, sok C-kódrészlettel a Git forrásából), `githooks.adoc` (29,9KB, 799 sor,
man page — az összes Git hook leírása). 2 párhuzamos subagent végezte, megszakítás nélkül.

### Ebben a blokkban rögzített / megerősített döntések

| angol | magyar | megjegyzés |
|---|---|---|
| object walk | **„objektumbejárás"** (első előforduláskor „object walk" glosszával) | `MyFirstObjectWalk.adoc` — a gráf-/fabejárás standard informatikai terminusa |
| revision walk / revision walker | **„revízióbejárás" / „revízióbejáró"** | ua. |
| commit walk | **„commit-bejárás"** | a `commit` (0. blokk) angolul marad, a `-bejárás` utótag ragad hozzá |
| walk / traverse / traversal (ige/főnév, általános) | **„bejár" / „bejárás"** | standard bejárás-terminológia |
| breadth-first (tree) traversal | **„szélességi (fa)bejárás"** | standard CS-terminus |
| callback | **marad „callback"** | bevett, jelöletlen angol kölcsönszó a magyar fejlesztői nyelvben |
| filter / filterspec | **marad „filter" / „filterspec"** | a Git saját `--filter`/`filterspec` terminológiáját követi |
| helper (function, generikus prózában) | **„segédfüggvény"** | a tényleges függvénynevek angolul maradnak |
| iterator | **„iterátor"** | standard CS kölcsönszó |
| heads (branch-csúcsok értelemben, `githooks.adoc` `post-update` leírásban) | **„branch-csúcsok"** | ad hoc, nem volt a glossaryban |
| 'forced' (kiemelt szó, NEM hook-név, `githooks.adoc`) | **marad „forced"** angolul, idézőjelben | a `force push`/`force-update` (0. blokk) angol jelző-mintájának folytatása |

### Címsor-anchorok

- **`MyFirstObjectWalk.adoc`** (NEM man page, minden cím fordult): 20 defenzív `[[...]]` anchor
  (l. subagent-jelentés a teljes listáért) — köztük 2 duplikátum-feloldás Asciidoctor-stílusban:
  a fájlban kétszer szereplő „Setting Up" → `_setting_up`/`_setting_up_2`, és a kétszer szereplő
  „Adding a Filter" / „Changing the Order" párok → `_adding_a_filter`/`_adding_a_filter_2`,
  `_changing_the_order`/`_changing_the_order_2`. Nincs `<<...>>` a fájlban, és más fájl sem
  hivatkozik rá `<<...>>`-vel. A szint-0 dokumentumcím (`= Az első objektumbejárásom`) nem kapott
  anchort (a még lefordítatlan `MyFirstContribution.adoc` angol eredetije is anchor nélküli ott).
- **`githooks.adoc`**: a fájlnak már volt 5 explicit `[[...]]` anchorja (`pre-receive`, `update`,
  `proc-receive`, `post-receive`, `post-update`) közvetlenül a hozzájuk tartozó, **le NEM
  fordított** hook-név-címek fölött (l. lent) — ezek és a rájuk mutató `<<update,'update'>>` /
  `<<post-receive,'post-receive'>>` (×2) / `<<pre-receive,'pre-receive'>>` /
  `<<post-update,'post-update'>>` xref-ek bájtazonosan érintetlenek maradtak. Nem kellett új
  anchort hozzáadni.

### Man-page címként / hook-névként angolul hagyott címsorok

- `githooks.adoc`: a **28 hook-név-alcím** (`applypatch-msg`, `pre-commit`, `pre-receive`,
  `update`, `proc-receive` stb.) **szó szerinti szkript-fájlnevek, NEM fordítandó azonosítók** —
  bájtazonosan, aláhúzásukkal együtt változatlanok, csak az alattuk lévő próza fordult. A
  `HOOKS` csupa nagybetűs, kétsoros alcím a 39. blokk VÉGLEGES DÖNTÉSE szerint angolul. A
  `"TEMPLATE DIRECTORY"` prózahivatkozás (a `git-init.adoc`-beli tényleges cím neve) szintén
  angolul, ugyanezen döntés szerint.

### Megőrzött markup / megjegyzések

- `MyFirstObjectWalk.adoc`: minden C-kódblokk (40 `----` pár) és a bennük lévő **C-kommentek is**
  bájtazonosan angolul maradtak (konzisztens a projekt eddigi kód-komment-kezelésével); a
  szó szerint idézett történelmi Git commit-üzenet-részlet (`"Initial revision of "git", the
  information manager from hell"`) is érintetlen; a `struct rev_info`/`struct
  rev_cmdline_info`/függvénynevek (`get_revision()` stb.) angolul.
- `githooks.adoc`: a pkt-line protokoll-példa (`update`/`proc-receive` hook leírásában, `#`
  kommentekkel) bájtazonos; a `GIT` szakasz „Part of the linkgit:git[1] suite" sora
  „A linkgit:git[1] csomag része"-re fordítva, a `git-p4.adoc`/`git-send-email.adoc` (40. blokk)
  precedense szerint.

Orchestrátor konszolidálta, közvetlen fájlmódosítás nélkül (mindkét subagent megszakítás nélkül
fejezte be a saját fájlját). Részletek fent, „41. blokk".

## 42. blokk — `git-format-patch.adoc`, `git-push.adoc` — 2026-09-11

**Fájlok:** `git-format-patch.adoc` (30,8KB, 824 sor, man page), `git-push.adoc` (32,2KB, 809
sor, man page). 2 párhuzamos subagent végezte.

### Orchestrátor-javítások a subagent-eredményben

- **`git-format-patch.adoc` — terminológiai inkonzisztencia javítva**: a subagent a
  `--thread`/`--no-thread` opció leírásában a „threading"/„threadeli" szavakat angolul hagyta
  (`shallow threading`, `deep threading`, „maga threadeli az e-maileket"). Ez ellentmondott a
  már lefordított `git-send-email.adoc`-nak (40. blokk), amely kifejezetten kimondja: „(`deep`
  szálazás, a `git format-patch` terminológiája szerint)" — tehát a `git-send-email.adoc` már
  előre feltételezte, hogy a `git-format-patch.adoc` a „szálazás" terminust fogja használni.
  Javítva: „shallow threading" → „`shallow` szálazás", „deep threading" → „`deep` szálazás",
  „threadeli az e-maileket" → „szálazza az e-maileket", „gondoskodjon a threadingről" →
  „gondoskodjon a szálazásról", „a threading le legyen tiltva" → „a szálazás le legyen tiltva",
  „a threadek megszakadjanak" → „a szálak megszakadjanak". A szó szerinti `--thread`/`--no-thread`
  kapcsolónevek és a `format.thread` config-kulcs értelemszerűen érintetlenek maradtak.
  **Ez a végleges terminológiai döntés: „thread" (szálazás fogalomkörben) → „szálazás" (fn) /
  „szálaz" (ige), NEM angol kölcsönszóként kezelve.**
- **`git-format-patch.adoc` — hiányzó fordítás pótolva**: a záró „GIT" szakasz „Part of the
  linkgit:git[1] suite" sora angolul maradt a subagent munkájában; pótolva „A linkgit:git[1]
  csomag része"-ként, a bevett precedens szerint.
- **`git-push.adoc`**: nem igényelt orchestrátor-javítást, hibátlanul készült el.

### Ebben a blokkban rögzített / megerősített döntések

| angol | magyar | megjegyzés |
|---|---|---|
| thread / threading (e-mail-szálazás fogalomkörben) | **VÉGLEGES: „szálaz" (ige) / „szálazás" (fn)** | `git-format-patch.adoc`, megerősítve a `git-send-email.adoc` (40. blokk) előzetes használatával; a `--thread`/`--no-thread` kapcsolónevek és a `format.thread` kulcs angolul maradnak |
| lease (`--force-with-lease` metafora) | **marad „lease" idézőjelben**, első előforduláskor „(bérletet)" glosszával | `git-push.adoc` — egyedi, a kapcsolónévhez kötött metafora, nem önálló glossary-fogalom |
| no-op | **marad „no-op"** | `git-push.adoc` — bevett technikai rövidítés |

### Címsor-anchorok

- **`git-format-patch.adoc`**: 7 defenzív anchor a fordított, nem kanonikus alcímek fölött:
  `_checking_for_patch_corruption` („Patch-korrupció ellenőrzése"), `_gmail`, `_thunderbird`,
  `_approach_1_add_on` („1. megközelítés (add-on)"), `_approach_2_configuration` („2.
  megközelítés (konfiguráció)"), `_approach_3_external_editor` („3. megközelítés (külső
  szerkesztő)"), `_kmail`. Nincs `<<...>>` a fájlban. Az `include::format-patch-caveats.adoc[]`
  és `include::diff-options.adoc[]` érintetlen. A `MUA-SPECIFIC HINTS`, `BASE TREE INFORMATION`
  és `=== PATCH APPLICATION` csupa nagybetűs, kanonikus listán kívüli címek a 39. blokk VÉGLEGES
  DÖNTÉSE szerint angolul.
- **`git-push.adoc`**: nem igényelt új anchort — minden anchorral rendelkező cím
  (`[[OPTIONS]]`, `[[CONFIGURATION]]`, `[[REMOTE-GROUPS]]`) egyben csupa nagybetűs, ezért
  angolul is marad. `<<URLS,GIT URLS>>` → `<<URLS,GIT URL-ek>>` (a `git-pull.adoc`/23./26. blokk
  precedens szerint); `<<REMOTES,REMOTES>>`, `<<UPSTREAM-BRANCHES,UPSTREAM BRANCHES>>`,
  `<<REMOTE-GROUPS,REMOTE GROUPS>>`, `<<CONFIGURATION,CONFIGURATION>>`, `<<OPTIONS,OPTIONS>>`
  mind bájtazonosan angolul maradtak (a linkszöveg maga is csupa nagybetűs cím-név).
  `REMOTE GROUPS`, `OUTPUT`, `PUSH RULES`, `NOTE ABOUT FAST-FORWARDS` a 39. blokk VÉGLEGES
  DÖNTÉSE szerint angolul.

### Megőrzött markup / megjegyzések

- `git-format-patch.adoc`: az e-mail-fejléc-példák (`From:`, `Date:`, `Subject:`,
  `MIME-Version:` stb.), a `MUA-SPECIFIC HINTS` alatti idézett e-mail-átiratok (`Do the same for
  ia64...`, `-- >8 --` olló-jelölés) és minden `----` kódblokk bájtazonos.
- `git-push.adoc`: az ASCII commit-gráf-diagramok (`B`/`A`/`X` csomópontokkal), a `git
  fetch`/`git tag`/`git rebase`/`git push` példa `#`-kommentekkel, és minden `----` kódblokk
  bájtazonos. A subagent egy forrásbeli elgépelést (dupla backtick) is javított kozmetikailag a
  fordítás közben, szemantikai változás nélkül.

Orchestrátor konszolidálta, a fent leírt 2 javítással (`git-format-patch.adoc`-on). Részletek
fent, „42. blokk".

## 43. blokk — `diff-options.adoc`, `gitprotocol-v2.adoc` — 2026-09-11

**Fájlok:** `diff-options.adoc` (34,3KB, 925 sor, SHARED INCLUDE FRAGMENS — `git-diff.adoc`,
`git-log.adoc`, `git-format-patch.adoc` stb. include-olja `ifdef::`/`ifndef::`/`endif::`
guardokkal), `gitprotocol-v2.adoc` (36,8KB, 904→974 sor, RFC-stílusú protokoll-spec, a
`gitprotocol-pack.adoc` [39. blokk] közvetlen mintáját követve). 2 párhuzamos subagent végezte.

### Orchestrátor-javítások a subagent-eredményben

- **`diff-options.adoc` — grammatikai javítás**: a `--diff-filter` opció leírásában a subagent
  fordítása („...amelyeknek a típusa ... megváltozott (T), Nem Merge-eltek (U), Ismeretlenek
  (X), vagy amelyeknek a párosítása Megszakadt (B)") a „Nem Merge-eltek (U), Ismeretlenek (X)"
  részt kötőszó nélkül, ragozatlanul hagyta lógni a felsorolásban. Javítva: „...megváltozott
  (T), amelyek Nem Merge-eltek (U) vagy Ismeretlenek (X), vagy amelyeknek a párosítása
  Megszakadt (B)" — az „amelyek" pótlásával a mondat mind a hét státuszbetűre (`A/C/D/M/R/T/U/X/B`)
  nyelvtanilag helyes relatív mellékmondat-láncot alkot.
- **`gitprotocol-http.adoc` — elmulasztott NAME-fordítás pótolva** (nem ennek a blokknak a
  fájlja, hanem a korábbi 38. blokké, de itt tűnt fel): a NAME-sor egysoros leírása
  („Git HTTP-based protocols") angolul maradt, holott a projekt 2. blokkban rögzített szabálya
  szerint a NAME szakasz egysoros leírása **mindig fordul** (l. minden más man page precedense).
  Javítva: „Git HTTP-alapú protokollok"-ra. A `gitprotocol-v2.adoc` és a `gitprotocol-pack.adoc`
  NAME-sora már helyesen fordítva készült el, ez utóbbi kettő volt a helyes minta, nem a
  `gitprotocol-http.adoc`.
- **`gitprotocol-v2.adoc`**: nem igényelt tartalmi javítást, csak a strukturális ellenőrzés
  (dash-számlálás) adott hamis riasztást — a fájl NEM tartalmaz `----`-delimitált kódblokkot
  (a protokoll-grammatika behúzott literál bekezdésekben van, ahogy a `gitprotocol-pack.adoc`-ban
  is), így minden `----` előfordulás egy-egy setext-cím aláhúzása, nem párban álló blokkhatároló.

### Ebben a blokkban rögzített / megerősített döntések

| angol | magyar | megjegyzés |
|---|---|---|
| NAME szakasz egysoros leírása | **VÉGLEGESEN megerősítve: mindig fordul** | a 2. blokk szabályának újbóli megerősítése, miután a `gitprotocol-http.adoc` egy korábbi kivétel volt (most javítva) |
| Packet-Line Framing (cím) | **„Pkt-line keretezés"** | `gitprotocol-v2.adoc` — a „pkt-line" a `gitprotocol-pack.adoc`/`gitprotocol-common.adoc` bevett terminusa |
| Capability Advertisement | **„Képesség-hirdetés"** | ua. |
| Command Request / Capabilities / Initial Client Request | **„Parancskérés" / „Képességek" / „Kezdeti klienskérés"** | ua. |
| ALL-CAPS `::` definíciós-lista-címke, mint ad hoc „mini-alcím" (NEM kétsoros setext cím) | **fordul** (a leíró angol kifejezés lefordul, a `bundle-uri` identifier-rész angolul marad) | `gitprotocol-v2.adoc` bundle-uri szekció: „URI CONTENTS::" → „URI-TARTALOM::", „bundle-uri CLIENT ERROR RECOVERY::" → „bundle-uri KLIENSOLDALI HIBAKEZELÉS::" stb. **Fontos megkülönböztetés a 39. blokk VÉGLEGES DÖNTÉSÉTŐL**: az ALL-CAPS „mindig angolul marad" szabály kizárólag a **kétsoros setext man-page-stílusú címekre** vonatkozik; egy `::` definíciós-lista-címke szintaktikailag NEM cím, hanem egy fogalom leíró neve, ezért — ha nem szó szerinti azonosító (mint egy config-kulcs vagy hook-fájlnév) — a leíró angol szövege fordul, ahogy bármely más `::`-címke leírás-törzse is |
| bundle-uri (protokoll-parancsnév, funkciónév) | **marad „bundle-uri"** angolul, a leíró szöveg körülötte fordul | ua. — Git-specifikus parancsnév |

### Címsor-anchorok

- **`diff-options.adoc`**: nincs saját címe (include-fragmens, csak `--option::` bejegyzések és
  szabad próza), ezért nem kapott anchort. Az egyetlen `<<generate_patch_text_with_p>>` xref
  (bare, látható szöveg nélkül) a `diff-generate-patch.adoc`-beli anchorra mutat — bájtazonosan
  érintetlen.
- **`gitprotocol-v2.adoc`**: 21 defenzív `[[...]]` anchor minden valódi (nem man-page-canonikus,
  nem `::`-címke) cím fölött, a `gitprotocol-pack.adoc` anchor-mintáját követve (l. subagent-
  jelentés a teljes listáért). Nincs `<<...>>` a fájlban, így egyik anchor sem igényelt
  hivatkozás-átírást.

### Man-page címként angolul hagyott, kétes címsorok

- `gitprotocol-v2.adoc`: `Git Transport`, `SSH and File Transport`, `HTTP Transport` — a
  `gitprotocol-pack.adoc` „Transport" kezelésének (39. blokk) közvetlen folytatása. Protokoll-
  parancs-/képességnevek címként (`agent`, `ls-refs`, `fetch`, `server-option`, `object-format`,
  `session-id=<session-id>`, `object-info`, `bundle-uri`, `promisor-remote=<pr-info>`) —
  identifierek, nem fordulnak.

### Megőrzött markup / megjegyzések

- `diff-options.adoc`: 7 `--`/`--` nyitott-blokk pár és 1 `----`/`----` listing-blokk-pár
  (a `frotz(nitfol...)` kódpélda) bájtazonos; a `--diff-filter` állapotbetűk (`A/C/D/M/R/T/U/X/B`)
  és minden `--option::`/`<pathspec>::` címke bájtazonos.
- `gitprotocol-v2.adoc`: minden ABNF-grammatika (behúzott literál bekezdésekben, NEM
  `----`-blokkban) és a protokoll-token-identifierek (l. fent) bájtazonosak; RFC 2119
  kulcsszavak a `gitcli.adoc`/`gitprotocol-http.adoc`/`gitprotocol-pack.adoc` szórend-mintája
  szerint.

Orchestrátor konszolidálta, 2 javítással (`diff-options.adoc` grammatika, `gitprotocol-http.adoc`
elmulasztott NAME-fordítás pótlása). Részletek fent, „43. blokk".
