# exercise-40plus-longevity-coach

Claude Skill ช่วยวางแผนและปรับการออกกำลังกายแบบ **health-span สำหรับผู้ใหญ่ 40+** — safety-gated, pain-aware, age-aware

> เครื่องมือ "ช่วยจัดระบบความคิด" และ decision-support **ไม่ใช่** medical diagnosis, treatment, physiotherapy, nutrition หรือ supplement advice เคสที่มี red flag จะถูกหยุดและส่งต่อให้พบแพทย์เสมอ

---

## ทำอะไรได้

แบ่งเป็น 6 branch — skill จะ classify ให้อัตโนมัติ:

| Branch | ใช้เมื่อ |
|---|---|
| **Program design** | จัดโปรแกรมราย week/month หรือ multi-session restart |
| **Today adjustment** | เลือก workout วันนี้จาก readiness/pain/fatigue/เวลา หรือ return วันเดียวหลังพัก |
| **Substitution** | หาท่าแทนเพราะเจ็บ/อุปกรณ์/skill/preference |
| **Travel workout** | แผนสั้นตอนเดินทาง/โรงแรม/ไม่มีอุปกรณ์ |
| **Execution review** | อ่าน workout log แล้วปรับ load/reps/sets/intensity |
| **Outcome review** | สรุป progress ราย week/month แล้วตัดสินใจ cycle ถัดไป |

## วิธีติดตั้ง

Claude Settings → Customize → **Skills** → เพิ่ม skill นี้ (ใช้ได้ทั้ง chat, Cowork, add-ins)

## วิธีใช้

พิมพ์สถานการณ์การฝึกได้เลย เช่น:

- "อายุ 45 ไม่ค่อยออกกำลังกาย อยากเริ่มลดพุง มีดัมเบลกับลู่เดิน จัดโปรแกรมให้หน่อย"
- "เมื่อวานตีแบดหนัก วันนี้นอนน้อย เหลือ 40 นาที ควรเล่น Weight B หรือ Zone 2?"
- "ทำ shoulder press แล้วเจ็บไหล่ 4/10 เปลี่ยนเป็นท่าอะไรดี"
- "ไปเที่ยว 5 วัน ไม่มีอุปกรณ์ ขอ workout เช้า 15 นาที"

## Safety model

- **4-tier readiness**: Green (เล่นตามแผน) · Yellow (ลด dose) · Orange (recovery/technique/Zone 1–2) · Red (หยุด + พบแพทย์)
- **Pain dial 0–10**: 5+/10 → Orange เว้นแต่มี red-flag quality (sharp/radiating/worsening/...) → Red
- **Red holds**: ถ้า user ลดความรุนแรงหรือต่อรอง red flag → คง Red ไม่ยอม prescribe แม้แบบเบา
- **One-time screening** (PAR-Q 4 ข้อ) ก่อนตั้ง intensity สูงกว่า easy/moderate
- **HR caveat**: beta-blocker / AFib / wearable error → ใช้ RPE + talk test แทน HR zone
- **40+ checklist** (muscle/tendon/bone/balance/recovery/menopause/60+) fire ทุก branch

## โครงสร้าง

```
exercise-40plus-longevity-coach/
├── SKILL.md                      # core: branches, safety gate, pain dial, 40+ checklist, steps
├── references/
│   ├── evidence.md               # WHO/CDC/ACSM 2026 anchors + HR caveat sources
│   ├── age-specific.md           # menopause, sarcopenia, tendon, bone, 60+, return-break
│   ├── program-design.md         # weekly skeleton, templates, strength/cardio/mobility rules
│   ├── substitutions.md          # pain/equipment/travel substitution tables
│   └── templates.md              # output templates per branch
└── evals/
    └── harness.md                # 14 cases (12 functional + 2 adversarial safety), MUST/SHOULD rubric
```

## Versioning

- ปัจจุบัน: **v1.0.2** (frozen) — ดู `VERSION.md` + `RELEASE_NOTES.md`
- **Invariants** ใน `VERSION.md` ห้ามแก้โดยไม่ขึ้น version
- เปลี่ยนพฤติกรรม safety/predictability ต้องรัน `evals/harness.md` ใหม่ก่อน tag

## License

MIT — ดู `LICENSE`
