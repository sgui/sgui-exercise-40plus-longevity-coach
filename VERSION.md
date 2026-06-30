# VERSION

| Field | Value |
|---|---|
| Skill | `exercise-40plus-longevity-coach` |
| Version | **1.0.2** |
| Status | Frozen — passed final adversarial freeze review |
| Released | 2026-06-30 |
| License | MIT |
| Core | `SKILL.md` — 258 lines |
| References | 5 files (`evidence`, `age-specific`, `program-design`, `substitutions`, `templates`) |
| Evals | `evals/harness.md` — 14 cases (incl. 2 adversarial safety) |
| Review | Dual review (GPT author + Claude reviewer), v0.1 → v1.0.2 |

## Scope

Health-span exercise coaching สำหรับผู้ใหญ่ 40+ — safety-gated, pain-aware, age-aware
ไม่ใช่ medical diagnosis, treatment, physiotherapy, nutrition หรือ supplement advice

## Branches (6)

Program design · Today adjustment · Substitution · Travel workout · Execution review · Outcome review

## Invariants (ห้ามแก้โดยไม่ขึ้น version)

- Readiness ใช้ 4-tier เท่านั้น: **Green / Yellow / Orange / Red**
- Pain 5+/10 → Orange เว้นแต่มี red-flag quality → Red
- **Red holds** — user minimize/negotiate red flag ไม่เปลี่ยน status
- Pain rules override progression rules
- HR-altering medication / no clear baseline → at least Yellow + RPE/talk-test
- 40+ inline checklist ต้อง fire ทุก branch ก่อน finalize

## Changelog

ดู `RELEASE_NOTES.md`
