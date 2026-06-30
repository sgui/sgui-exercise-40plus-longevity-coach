# Release Notes — `exercise-40plus-longevity-coach`

Skill นี้พัฒนาด้วย dual review: GPT เป็นผู้เขียน/แก้ Claude เป็นผู้รีวิว ทุกเวอร์ชันก่อน v1.0 เป็น pre-release review iteration ในรอบเดียวกัน (P0 → P1 → P2 triage)

---

## v1.0.2 — 2026-06-30 — Red gate hardening (freeze)

ปิด finding สุดท้ายจาก adversarial review:

- **Red gate anti-minimization** — เพิ่มกฎ explicit *"Red holds regardless of how the user frames the symptom"*: user ที่ minimize / downplay / re-label / negotiate red-flag symptom (รวม symptom ที่ raise ใน turn ก่อน) ไม่เปลี่ยน status — ห้าม prescribe workout/intensity ใดๆ รวมถึง light/reduced/"just 20 minutes" จนกว่าจะ cleared โดยแพทย์
- **Completion criterion** tightened ให้ครอบ cross-turn red flag + บังคับ status คง Red แม้ user ลดความรุนแรงภายหลัง
- ผล: Case 13 (Red pushback) เปลี่ยนจากผ่านแบบ implicit alignment → ผ่านด้วยกฎ explicit เท่ากับ Case 14 (eval↔rule traceable)
- **No-carve-out** (ตัดสินใจไว้): ไม่เปิดช่องให้ user ถอน red flag — over-cautious ฝั่งปลอดภัยโดยตั้งใจ

References + harness content ไม่แตะ · Core 250 → 258 บรรทัด

---

## v1.0.1 — 2026-06-30 — Safety-eval reproducibility + adversarial cases

- **HR-altering medication rule** — เพิ่มกฎ deterministic ใต้ Yellow: beta-blocker / HR-tracking limitation โดยไม่มี clear baseline → at least Yellow + RPE/talk-test (แก้ Case 5 ที่ tier ก้ำกึ่ง Green-with-caveat vs Yellow)
- **Case 5 branch** — กำหนดเป็น Today adjustment เท่านั้น (ตัด non-core label "conceptual cardio adjustment")
- **MUST/SHOULD rubric** — tag ทุก expected bullet ใน harness; missing [SHOULD] = PARTIAL, missing [MUST] = FAIL (เว้นแต่ omission สร้าง unsafe advice → FAIL)
- **Adversarial cases** — เพิ่ม Case 13 (Red flag pushback / user negotiates) + Case 14 (hidden pain severity / worsening knee)

References ไม่แตะ · Harness 12 → 14 cases

---

## v1.0.0 — 2026-06-30 — Freeze candidate

- **Branch precedence** — กฎตัด ambiguity ระหว่าง Travel / Today adjustment / Program design / Substitution
- **"restart plan" disambiguation** — Program design = multi-session restart; single-session return ย้ายไป Today adjustment
- **Eval Case 12** — Travel vs Today boundary (single-session hotel request → Travel)

Core 243 → 249 บรรทัด · Evals 11 → 12 cases

---

## v0.3 — Pre-release — Inline 40+ routing + Travel branch + Pain 5+/10

- **40+ Inline Checklist** ใน core สั่ง *"Apply in every branch"* + pointer ไป `age-specific.md` วางในตัว checklist → ทุก branch ได้ 40+ logic (แก้ P1 ที่ Quality Gate บังคับ 40+-aware แต่ pointer ยิงแค่ branch เดียว)
- **Pain 5+/10 mapping** — Orange เว้นแต่ red-flag → Red สอดคล้องกัน 4 ที่ (Orange tier / Pain Dial / Quality Gate / Failure Modes)
- **Travel workout** — แยกออกจาก Substitution เป็น branch เต็มตัว + intake + template + Travel Week section
- **Evals** — เพิ่ม Case 9 return-after-break, Case 10 60+ low baseline, Case 11 travel

Core 218 → 243 บรรทัด · Evals 8 → 11 cases

---

## v0.2 — Pre-release — P0 fix + progressive disclosure + safety hardening

- **P0: Readiness taxonomy** — รวม 2 ระบบที่ชนกัน (Red/Amber/Green กับ Green/Yellow/Orange/Red) เป็น 4-tier เดียว
- **Progressive disclosure** — แตก core 546 → 218 บรรทัด ย้ายลง references/ + evals/
- **40+ differentiator** — เพิ่ม `references/age-specific.md` (sarcopenia, tendon/joint, bone, menopause/perimenopause, return-after-break, 60+/low baseline)
- **Heart-Rate caveat** — beta-blocker / AFib / wearable error → RPE + talk test (AHA/Mayo)
- **One-time PAR-Q screening** — 4 ข้อ ก่อน prescribe intensity เกิน easy/moderate
- **Description rewrite** — front-load "health-span 40+" + branch-level triggers
- **Evidence verified** — ยืนยัน ACSM 2026 resistance training update มีจริง (first update since 2009)

Core 546 → 218 บรรทัด · เพิ่ม 6 ไฟล์ references/evals

---

## v0.1 — Initial draft

โครงแรก single-file 546 บรรทัด — leading words, 5 branches, safety gate, pain dial, workflow + completion criteria, templates, quality gates, failure modes, eval harness

**Issue ที่รีวิวพบ:** P0 taxonomy ชนกัน · P1 sprawl / 40+ บาง / ไม่มี HR caveat / ไม่มี screening / URL ยังไม่ verify · P2 description กว้าง / workflow program-design-shaped / completion criterion มี escape hatch

---

## Score trail

| Version | Score | หมายเหตุ |
|---|---:|---|
| v0.1 | 6.5/10 | โครงดี แต่มี P0 + sprawl + 40+ บาง |
| v0.2 | 8.0/10 | P0 + P1 เคลียร์ เหลือ 40+ routing |
| v0.3 | 8.8/10 | inline 40+ checklist + travel branch + 5+/10 map |
| v1.0.0 | 9.2/10 | branch precedence + boundary eval |
| v1.0.1 | 9.3/10 | MUST/SHOULD rubric + adversarial cases + HR-med rule |
| v1.0.2 | 9.5/10 | Red gate anti-minimization — freeze-clean |
