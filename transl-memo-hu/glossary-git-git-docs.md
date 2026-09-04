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
