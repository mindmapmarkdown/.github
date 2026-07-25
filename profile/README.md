# Mindmap Markdown

**A round-trip-stable Markdown profile for human–AI knowledge exchange.**

> 🚧 **Status: Draft.** The specification is being developed in the open.
> Nothing here is stable yet, and that is intentional — we would rather be corrected early.

---

## The problem

Markdown has become the format machines read. Governments, toolchains, and LLM pipelines
are converging on it because it is open, plain, and machine-parsable.

But knowledge is not linear. Once a document has real hierarchical depth,
**a human can no longer see its shape in plain text** — while the same structure is trivially
legible to a person when drawn as a tree.

So we end up with two audiences that need the same knowledge in two different forms:

| | prefers | struggles with |
|---|---|---|
| **Machines** | linear canonical text | ambiguity, undeclared structure |
| **Humans** | visual hierarchy | deep nesting as flat text |

Converting between the two is easy. **Converting back without losing anything is not.**
When an LLM rewrites a document, node identity, human annotations, layout, and review
history are silently destroyed — and there is no standard that treats this as a problem.

## What this is

Mindmap Markdown defines a **canonical Markdown profile** and a **round-trip contract**, so that
the same knowledge can move between a human-facing view and a machine-facing text form
without loss in either direction.

Design constraints we hold ourselves to:

- **It is still Markdown.** A Mindmap Markdown file opens and renders in GitHub, Obsidian, or
  any editor you already use. Adoption cost starts at zero.
- **Semantics in the document, presentation beside it.** Layout and styling live in a sidecar,
  never in the text sent to a model.
- **Conformance is testable.** A specification that cannot be checked is a suggestion.
- **We interoperate rather than compete.** Adapters for existing formats come first.

## Why it is being attempted again

Interchange formats for hierarchical documents are not new. OPML served as the de facto
standard for two decades and taught us three specific lessons:

1. **Round-trip loss was never solved** — styles, links, and attributes vanished between tools.
2. **Governance stalled** — single ownership, no succession, a specification frozen for years.
3. **No standards body adopted it** — it stayed informal and never reached institutional use.

We treat each of those as a design requirement rather than an accident.
And there is now a fourth requirement that did not exist in 2007: **the reader may be a model.**

## Repositories

| Repository | Purpose |
|---|---|
| [`spec`](https://github.com/mindmapmarkdown/spec) | The specification and its normative examples |
| `conformance` | Test suite, runner, and the implementation registry _(coming soon)_ |
| `mindmapmd` | Reference implementation — parser, canonicalizer, bindings _(coming soon)_ |
| `adapters` | Interoperability with OPML, JSON Canvas, and others _(coming soon)_ |

## Getting involved

The specification is at its earliest and most changeable stage, which is the most useful
moment to disagree with it.

- **Read** the draft in [`spec`](https://github.com/mindmapmarkdown/spec)
- **Question or propose** in Discussions
- **Implement** — an independent implementation is the most valuable contribution a
  specification can receive, and the registry is open to anyone

## License

Specification text is licensed under **CC-BY-4.0**. Code is licensed under **Apache-2.0**.

## Contact

- General and specification questions — `spec@mindmapmarkdown.org`
- Security and vulnerability reports — `security@mindmapmarkdown.org`
- Website — [mindmapmarkdown.org](https://mindmapmarkdown.org)

---

<details>
<summary><b>한국어 요약</b></summary>

<br>

**Mindmap Markdown**은 인간과 AI가 같은 지식을 각자의 표현으로 다루기 위한
**왕복 안정(round-trip stable) 마크다운 프로파일**입니다.

마크다운은 기계가 읽는 형식이 되었습니다. 그러나 계층이 깊어지면 사람은 평문에서
구조를 볼 수 없습니다. 같은 구조를 트리로 그리면 즉시 읽히는데도 말입니다.

두 표현 사이의 변환은 쉽습니다. **손실 없이 되돌리는 것이 어렵습니다.**
LLM이 문서를 재작성하는 순간 노드 정체성, 사람이 단 주석, 레이아웃, 검토 이력이
조용히 사라지며, 이를 문제로 다루는 표준은 아직 없습니다.

- 사양 텍스트: CC-BY-4.0 / 코드: Apache-2.0
- 문의: `spec@mindmapmarkdown.org`
- 현재 상태: **Draft** — 공개적으로 다듬는 중입니다

</details>
