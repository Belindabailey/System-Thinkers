[README.md](https://github.com/user-attachments/files/29448543/README.md)
# The Gel Brain — A Systems-Thinker's Progression

A spinnable 3D map of a line of reasoning. Each particle is one **thought**; each line back to an earlier thought is the **move** that produced it. Press **Replay** and the map grows from a single seed, so you watch a chain of reasoning build itself — and the long, bright edges mark the moments someone stopped *adding* and started *re-seeing*.

Built by [BioStellar LLC](mailto:biostellarllc@gmail.com) as part of the Gel Brain line. Made to be shared: the map runs in any browser, offline, with no account and no key.

---

## The idea in one breath

A pile of thoughts is a library. A **sequence** is a path — and a path is something another mind can walk, replay, and extend. This tool turns a progression into a portable object you can drop in a thread and hand off.

Two things make it more than a pretty cloud:

- **Position carries meaning.** Thoughts are placed by six axes of a thought-space (below), so kindred ideas settle into neighborhoods. Distance is similarity.
- **A long edge is the signature of a reframe.** Grounding steps land near their parent (short, dim edges). A jump in scale or a cross-domain rhyme lands far away (long, pink edges). The geometry makes "this person re-saw the problem here" visible as a bright line instead of a vibe.

---

## Using it

**Move around**
- Drag to rotate. Scroll or use **+ / −** to zoom toward the words.
- Hover a dot to read it; the small dots stay small so the cloud reads as points.
- **Find a thought** — type and hit Enter to fly to any node and light its associations.
- **spin** slider sets the idle rotation.

**Replay the progression**
- **Replay the thinking** grows the map one thought at a time, naming each stage and the parent it came from.
- **spin to each new thought** (checkbox) flies to each arrival; uncheck to let the cloud drift while thoughts pop in.
- **step** slider scrubs the history by hand, forward or back.

**A collaborator that suggests**
- **Find an unmade leap** searches for two thoughts that both run high in spirit (cooperation, or the companion-vs-tool ethic) yet sit in different worlds with no move between them — and draws a glowing dashed line where the edge *isn't* yet.
- **Another** cycles the ranked candidates. **Draft the bridge** pre-fills the writing box with both endpoints so the synthesis you write lands right between them.

**Add a thought**
- Type an idea and place it. Inside Claude, a model reads its meaning and sets it by the six axes; it attaches to its nearest existing thought as parent.

**Make it theirs**
- **Start over** empties the map (with a confirm) so a new mind can grow its own progression from a blank field.
- **Restore the example** brings the demo sequence back in one click. A page refresh also resets to the example.

**Share a sequence**
- **Export** copies the whole progression to the text box and clipboard. **Download .json** saves it.
- **Import** rebuilds a map from pasted text; **Load file** reads a saved `.json`. Replay, stages, and reframe-edges all come back intact — no Claude required to view.

---

## The Claude dependency, plainly

Everything above — spinning, zooming, searching, replay, the suggestion engine, clear/restore, export/import — runs entirely in the browser with **no connection to anything**.

The one exception is **live placement** in *Add a thought*: reading a brand-new thought's meaning uses a model and only works while the file is open **inside Claude**. A shared copy still accepts new thoughts but places them approximately.

So the workflow for a group is: **build live here, share the frozen file there.** Build your sequence in Claude (where placement is by true meaning), export it, and anyone can load and walk it anywhere.

The strongest version pairs the two: the map cheaply spotlights *where* a leap wants to happen; a Claude proposes *what* it might be. The geometry finds the gap; the mind fills it.

---

## The six axes of the thought-space

| Axis | 0.0 | 1.0 |
|---|---|---|
| **grounded** | pure speculation / vision | established fact / science |
| **tension** | no problem | the hard edge, danger, contradiction |
| **relation** | solitary / technical | cooperation, bonding, mutualism |
| **mechanism** | abstract / philosophical | concrete how-it-works detail |
| **scale** | molecular / cellular | civilizational / cosmic |
| **ethic** | tool / extraction / imposed | companion / endowment / sovereign |

A node's color is a blend of its axis weights, so you can read a thought's character at a glance.

---

## The sequence file format

A saved sequence is small JSON. You can hand-edit one or generate them from other tools:

```json
{
  "format": "gelbrain.v1",
  "thoughts": [
    { "t": "the seed thought",        "v": [0.30,0.20,0.40,0.40,0.15,0.50], "p": -1 },
    { "t": "a step grounded nearby",  "v": [0.90,0.10,0.50,0.70,0.10,0.40], "p": 0  },
    { "t": "a reframe, far away",      "v": [0.40,0.20,0.80,0.30,0.25,0.85], "p": 1  }
  ]
}
```

- `t` — the thought's text.
- `v` — its six axis values (`grounded, tension, relation, mechanism, scale, ethic`), each 0.00–1.00.
- `p` — the index of the thought it grew from (`-1` for the root seed). Parents must come *before* their children; the importer repairs anything that doesn't.

The importer also accepts a bare array of `{t, v, p}` objects, and clamps or repairs malformed values rather than failing.

---

## Files in this project

- **The_Gel_Brain_Progression.html** — the shareable progression map described above (the one for the group).
- **The_Gel_Brain_FungalSurgeon.html** — a companion gel mapping a single design space (the fungal-surgeon brainstorm), with live placement and search.
- **The_Gel_Brain_Society.html** — the same, one scale up: the cooperating-civilization design space.

The companion maps share the engine but are snapshots rather than progressions — useful for exploring one problem's neighborhoods. The progression map is the one that records *how the thinking moved*.

---

## A note for systems thinkers

Conclusions hide their own reasoning; a path exposes where it could have forked. Sharing **sequences** rather than scattered thoughts changes what a collaborator — human or Claude — can do: from "here's a related idea" to "here's the leap your own path is pointing at and hasn't taken." That empty space, made visible and specific, is where the audacious move lives.

---

*The Gel Brain — BioStellar LLC, 2026. Share it freely.*
