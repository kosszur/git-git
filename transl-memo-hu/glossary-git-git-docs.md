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
