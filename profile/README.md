# Mindmap Markdown

**A round-trip-stable Markdown profile for human–AI knowledge exchange.**

> 🚧 **Status: Draft.** The specification is being developed in the open.
> Nothing here is stable yet, and that is intentional — we would rather be corrected early.

---

## The problem

Markdown has become the format machines read. Governments, toolchains, and LLM pipelines are
converging on it because it is open, plain, and machine-parsable.

A document format that has to serve both people and machines needs four properties.
Markdown delivers three of them outright.

| Requirement | Markdown |
|---|---|
| Open standard | ✅ |
| Machine-readable | ✅ |
| AI-readable | ✅ |
| **Human-readable** | **only while the document stays shallow** |

Knowledge is not linear. Once a document has real hierarchical depth, **a human can no longer
see its shape in plain text** — while the same structure is trivially legible when drawn as a tree.

Drawing that tree is easy. **Getting back without losing anything is not.** When an LLM rewrites
a document, node identity, human annotations, layout, and review history are silently destroyed —
and there is no standard that treats this as a problem.

## What this is

Mindmap Markdown defines a **canonical Markdown profile** and a **round-trip contract**, so that
the same knowledge can move between a human-facing view and a machine-facing text form without
loss in either direction.

Design constraints we hold ourselves to:

- **It is still Markdown.** A Mindmap Markdown file opens and renders in GitHub, Obsidian, or any
  editor you already use. Adoption cost starts at zero.
- **Semantics in the document, presentation beside it.** Layout and styling live in a sidecar,
  never in the text sent to a model.
- **Conformance is testable.** A specification that cannot be checked is a suggestion.
- **We interoperate rather than compete.** Adapters for existing formats come first.

## In practice

A Mindmap Markdown document can be rendered to a **single self-contained HTML file** — no server,
no runtime, no installation. Open it and it works, on any machine, offline, years from now.

That viewer carries **two views of the same document**:

| | mindmap | outline |
|---|---|---|
| shows | shape, at a glance | sequence, navigable |
| holds up when | depth is high | node count is high |

This is not decoration. **No single view survives every scale** — plain text loses the shape of a
deep document, and a mindmap of eight hundred nodes is unreadable spaghetti. A format that expects
to be viewed in more than one way is a format whose semantics must live in the document and whose
presentation must live somewhere else. The viewer is evidence for the architecture, not an add-on
to it.

A working viewer exists today in the reference application and is being extracted into the
standard toolchain.

## Why it is being attempted again

Interchange formats for hierarchical documents are not new. **OPML** served as the de facto
standard for two decades and taught us three specific lessons:

1. **Round-trip loss was never solved** — styles, links, and attributes vanished between tools.
2. **Governance stalled** — single ownership, no succession, a specification frozen for years.
3. **No standards body adopted it** — it stayed informal and never reached institutional use.

We treat each of those as a design requirement rather than an accident, and we have written down
how we intend not to repeat the second one — see [`GOVERNANCE.md`](https://github.com/mindmapmarkdown/spec/blob/main/GOVERNANCE.md).

Rendering Markdown as a mindmap is also not new, and is already done well — **markmap** in
particular, which exports standalone interactive HTML and has a genuine ecosystem around it.
What does not yet exist is a *specified* mapping. Which Markdown constructs become which nodes is
currently each tool's own heuristic, so authors adjust their documents to suit a tool rather than
the other way round. And rendering is one-way: nothing comes back.

There is also a requirement that did not exist in 2007: **the reader may be a model.**

## Repositories

| Repository | Purpose |
|---|---|
| [`spec`](https://github.com/mindmapmarkdown/spec) | The specification and its normative examples |
| `conformance` | Test suite, runner, and the implementation registry *(coming soon)* |
| `mindmapmd` | Reference implementation — parser, canonicalizer, bindings *(coming soon)* |
| `adapters` | Interoperability with OPML, JSON Canvas, markmap, and others *(coming soon)* |

## Getting involved

The specification is at its earliest and most changeable stage, which is the most useful moment
to disagree with it.

- **Read** the draft in [`spec`](https://github.com/mindmapmarkdown/spec)
- **Question or propose** in Discussions
- **Implement** — an independent implementation is the most valuable contribution a specification
  can receive, and the registry is open to anyone

## License

Specification text is licensed under **CC-BY-4.0**. Code is licensed under **Apache-2.0**.

## Contact

- General and specification questions — `spec@mindmapmarkdown.org`
- Security and vulnerability reports — `security@mindmapmarkdown.org`
- Website — [mindmapmarkdown.org](https://mindmapmarkdown.org)

---

## 한국어 요약

**Mindmap Markdown**은 인간과 AI가 같은 지식을 각자의 표현으로 다루기 위한
**왕복 안정(round-trip stable) 마크다운 프로파일**입니다.

문서 형식이 사람과 기계를 모두 감당하려면 네 가지가 필요합니다 —
**공개 표준 · 기계 판독 · AI 가독 · 사람 가독.** 마크다운은 앞의 셋을 만족합니다.
**남은 하나는 문서가 얕을 때만 유지됩니다.** 계층이 깊어지면 사람은 평문에서 구조를 볼 수 없습니다.
같은 구조를 트리로 그리면 즉시 읽히는데도 말입니다.

트리로 그리는 것은 쉽습니다. **손실 없이 되돌리는 것이 어렵습니다.**
LLM이 문서를 재작성하는 순간 노드 정체성, 사람이 단 주석, 레이아웃, 검토 이력이 조용히 사라지며,
이를 문제로 다루는 표준은 아직 없습니다.

Mindmap Markdown 문서는 **아무것도 설치할 필요 없는 단일 HTML 파일**로 렌더링되며,
그 뷰어는 **마인드맵과 아웃라인 두 뷰**를 함께 제공합니다.
어떤 단일 뷰도 모든 규모에서 작동하지 않기 때문입니다.

- 사양 텍스트: CC-BY-4.0 / 코드: Apache-2.0
- 문의: `spec@mindmapmarkdown.org`
- 현재 상태: **Draft** — 공개적으로 다듬는 중입니다
