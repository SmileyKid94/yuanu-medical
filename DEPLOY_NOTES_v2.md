# YuanU Medical Concierge — Website v2 Deployment Notes

**Version:** v2 (content update — value proposition + screening narrative)
**Date:** 2026-06-15 (last updated 2026-06-15 22:19, see §1 #5–#7)
**Scope:** Copy revisions on `index.html`, `about.html`, `screening.html`, `patient-support.html` and `endoscopy.html`. **No structural changes, no CSS/JS changes, no new dependencies, no new pages.** Same deployment process as v1.

---

## 1. What changed and why

A medical-doctor colleague reviewing v1 raised a fair point: the site clearly explains *Beijing Friendship Hospital · IMD*, screening packages and endoscopy, but does not explicitly answer the question every prospective patient asks first —

> *"Why should I go through YuanU instead of just emailing the hospital myself?"*

v2 first added that answer in three places (#1–#4 below). After a second review, the same colleague made two further points specifically about the screening page:

1. *Why Beijing* — what international patients are missing isn't basic health checks, it's the **integration** of specialist density, examination breadth and downstream care in one hospital system.
2. *Screening is not a package* — value lives in matching tests to age, sex, family history and existing conditions, with that conversation happening **before** the patient arrives, not on intake morning.

v2 now also addresses these on `screening.html` (#5–#6 below), without removing any factual content from v1.

A third reviewer pass (medical doctors, internal chat 2026-06-15 evening) flagged the word *"escort"* across the English copy: in US/UK colloquial English the word can carry a sex-work connotation, which is not a risk we should tolerate on a medical-coordination website. v2 therefore also rewrites every YuanU-role *"escort"* on `patient-support.html`, `screening.html` and `endoscopy.html` (see #7 below). The Chinese term *"陪同"* carries no such connotation and is unchanged.

### Changes summary

| # | Page | Section | Change |
|---|------|---------|--------|
| 1 | `index.html` | Hero `<h1>` + lede | New tagline + reframed lede ("the bottleneck is not the physician, it is the path to the physician") |
| 2 | `index.html` | **NEW section** between Trust strip and "Who we are" | "Why not just contact the hospital directly?" — three-paragraph answer, bilingual |
| 3 | `index.html` | "Who we are" opening paragraph | Reordered: value statement first, boundary statement second |
| 4 | `about.html` | Hero (above the company-history lede) | Inserted a one-paragraph value statement (italic, teal) before the existing factual lede |
| 5 | `screening.html` | **NEW §4** between "Five typical patient profiles" (§3) and "Reference pricing" (now §6) | "Why come to Beijing for screening" — three pillars (specialist density / examination breadth / downstream care) + closing callout, bilingual |
| 6 | `screening.html` | **NEW §5** immediately after the new §4 | "A screening is not a package — how we design yours" — design principle + concrete examples + pre-screening review scope + closing callout that reframes §6 pricing as "reference points, not products on a shelf", bilingual |
| 7 | `patient-support.html`, `screening.html`, `endoscopy.html` | Multiple inline phrases (English copy only) | Replace the word *"escort"* across all YuanU-role uses with *"support / on-site support / accompanies / companion"*; rewrite the In-Hospital service title (`§03`) and its boundary paragraph on `patient-support.html`. **No structural change, no Chinese change.** Total: 19 string replacements across 3 files |

> **Renumbering on `screening.html`:** as a consequence of #5 and #6, the H2 numbers and eyebrow tags below have been shifted by +2 (no copy changes inside those sections):
> - old §4 *Reference pricing* → now **§6** (eyebrow §4.4 → §4.6, applies to the master pricing block and the 3 SKU-detail blocks)
> - old §5 *6-step flow* → now **§7** (eyebrow §4.5 → §4.7)
> - old §6 *Report handling* → now **§8** (eyebrow §4.6 → §4.8)
> - old §7 *Fees & what's included* → now **§9** (eyebrow §4.7.1 → §4.9.1)
> - old §8 *Screening-specific FAQ* → now **§10** (eyebrow §4.7.2 → §4.9.2)

Nothing else has been touched. Same files, same paths, same `data-lang` switching mechanism.

---

## 2. Final copy (for your reference / proofreading)

### 2.1 `index.html` — Hero

**EN H1**
> The medicine is in Beijing.
> Building the path to it is our work.

**ZH H1**
> 北京的医生在那里。
> 从海外走到那里的那条路，由我们搭。

**EN lede**
> For international patients, the bottleneck of Beijing healthcare is rarely the physician — it is everything between the first inquiry and the consulting room: language, hospital workflow, payment routes, the right department, the right specialist tier, the report afterwards. YuanU is the licensed Beijing company that builds and walks that path with you, in long-term partnership with Beijing Friendship Hospital's International Medical Department (BFH·IMD).

**ZH lede**
> 对海外患者来说，北京医疗的瓶颈很少是医生本身，而是从第一封咨询邮件到诊室之间的一整段路——语言、医院流程、支付路径、对的科室、对的专家级别、检查后的报告衔接。远游是一家在北京持照运营的公司，与北京友谊医院国际医疗部（BFH·IMD）长期协作，把这段路一步一步陪您走通。

### 2.2 `index.html` — NEW section "Why not just contact the hospital directly?"

H2 EN: *Why not just contact the hospital directly?*
H2 ZH: 为什么不直接联系医院？

**Paragraph 1 — EN**
> You can. The hospital exists, the department exists, the email address is public. But hospitals run on hospital time, in Mandarin, and a senior specialist's calendar is not what the front desk manages. What looks like one email is in practice a 6–8 week chain across departments — and most international patients never see where it broke.

**Paragraph 1 — ZH**
> 完全可以。医院在那里，科室在那里，邮箱也是公开的。但医院按医院的节奏、用中文运转，资深专家的档期不在前台手里。看上去是发一封邮件，实际是跨多个部门、6–8 周的协调链——而大多数海外患者根本看不到链条在哪一段断了。

**Paragraph 2 — EN**
> A YuanU coordinator does what the hospital cannot do for you from inside its own walls: triage your records before booking, match them to the right department and the right specialist tier, walk through the day with you in your language, and translate the report afterwards — including the part the doctor did not have time to dictate.

**Paragraph 2 — ZH**
> 远游协调员做的，是医院从内部做不到的那部分：在挂号之前先把您的病历过一遍，匹配到对的科室、对的专家级别；当天用您的语言陪您走完流程；事后把报告翻译给您——包括医生没时间口述的那一部分。

**Closing line (italic, teal accent) — EN**
> *That is the difference between getting an appointment and being correctly placed in a clinical pathway.*

**Closing line — ZH**
> 这就是"挂上一个号"和"被正确放进一条临床路径"的区别。

### 2.3 `index.html` — "Who we are" opening (REWRITTEN)

**EN**
> YuanU exists for one specific reason: international patients who need Beijing-grade specialist care should not have to negotiate with the Chinese hospital system in Chinese. We are a licensed medical coordination service company (medical concierge) based in Beijing, working in long-term partnership with BFH·IMD and other Beijing tertiary hospitals. We do not provide medical care. We make Beijing medicine reachable.

**ZH**
> 远游存在的理由很具体：需要北京级专家诊疗的海外患者，不应该被迫用中文和中国医院系统打交道。我们是一家在北京持照运营的医疗协调服务公司（medical concierge），与北京友谊医院国际医疗部及其他北京三甲医院长期协作。我们不做诊疗，我们让北京医疗对海外患者"够得着"。

The "single dedicated coordinator" italic block immediately following this paragraph is **kept unchanged** from v1.

### 2.4 `about.html` — Hero (one-paragraph insertion)

A new italic teal paragraph is inserted **between the H1 and the existing company-history lede**. The factual paragraph (founded 2006, license No. L-BJ-CJ00262, etc.) is untouched and now becomes the second paragraph.

**EN (new opening paragraph)**
> *YuanU exists for one specific reason: international patients who need Beijing-grade specialist care should not have to negotiate with the Chinese hospital system in Chinese. We do not provide medical care — we make Beijing medicine reachable.*

**ZH (new opening paragraph)**
> *远游存在的理由很具体：需要北京级专家诊疗的海外患者，不应该被迫用中文和中国医院系统打交道。我们不做诊疗——我们让北京医疗对海外患者"够得着"。*

### 2.5 `screening.html` — NEW §4 "Why come to Beijing for screening"

Inserted **between** old §3 *Five typical patient profiles* and old §4 *Reference pricing* (now §6).

H2 EN: *4. Why come to Beijing for screening*
H2 ZH: 4. 为什么来北京做体检
Eyebrow EN: *§ 4.4 · Why Beijing for screening*
Eyebrow ZH: § 4.4 · 为什么来北京体检

**Lede — EN**
> Most patients we work with don't lack basic health checks at home — what they often lack is **fast, integrated access to specialists, advanced examinations, and downstream care, all in one place**. Beijing is one of the few cities in China where that combination sits inside a single hospital system.

**Lede — ZH**
> 大多数海外患者在所在国家做常规体检并不困难。真正缺的是 **专家资源、检查资源与后续医疗资源的就近整合**。北京是国内少数能在同一家医院体系内同时提供这三者的城市。

**Three pillars (3-column grid):**

1. **Specialist density / 专家集中度**
   - EN: BFH·IMD's screening physicians sit in the same hospital as cardiology, gastroenterology, oncology, endocrinology, neurology and dozens of other specialty teams. If a screening finding warrants a specialist follow-up, that consultation often happens within the same trip — not three months later.
   - ZH: BFH·IMD 的体检医师与心血管、消化、肿瘤、内分泌、神经等几十个专科同在一家医院。体检中发现的问题，往往可以在同一次行程内完成专科会诊，而不是几个月后再约。

2. **Examination breadth / 检查可获得性**
   - EN: Tests that take weeks or months to schedule abroad — endoscopy, advanced imaging, sub-specialty ultrasounds, broad laboratory profiles — are typically available within days here, with most items grouped into a single morning.
   - ZH: 在很多国家需要排几周甚至几个月的项目（胃肠镜、特殊影像、亚专科超声、特定实验室套餐），在 BFH·IMD 通常以天为单位排期，多数项目可在同一上午完成。

3. **Downstream care, if it's needed / 如有问题，闭环在同一家医院**
   - EN: If a finding needs further work-up, the same hospital can take you from screening → diagnostic workup → specialist consultation → treatment plan, without re-routing you to a different institution mid-way.
   - ZH: 如果体检中发现异常，从体检 → 进一步检查 → 专科会诊 → 治疗方案，可以在同一家医院体系内顺接，不需要在不同机构之间反复辗转。

**Closing callout (gold left border) — EN**
> *The point isn't that Beijing is the only city that can do this — it's that the integration is unusually tight here, and that's what makes a single-trip screening clinically useful for a patient flying in from abroad.*

**Closing callout — ZH**
> *北京并不是唯一能做这件事的城市，但 **集中度** 在国内少有匹敌——这正是"一次行程完成体检"对海外患者真正有意义的原因。*

### 2.6 `screening.html` — NEW §5 "A screening is not a package — how we design yours"

Inserted **immediately after** the new §4, **before** old §4 (now §6) *Reference pricing*.

H2 EN: *5. A screening is not a package — how we design yours*
H2 ZH: 5. 体检不是买套餐 — 我们如何为您设计方案
Eyebrow EN: *§ 4.5 · How we design your screening*
Eyebrow ZH: § 4.5 · 我们如何为您设计体检方案

**Lede — EN**
> A screening's value isn't measured in how many items it contains. It's measured in **whether the items match your age, sex, family history and existing conditions**. The conversation about which tests you actually need should happen *before* you arrive at the hospital — not on the morning of intake.

**Lede — ZH**
> 体检的价值不是项目越多越好，而是 **这些项目是否匹配您的年龄、性别、家族史与既往病史**。关于"您实际需要做哪些检查"的沟通，应当发生在 *抵达医院之前*，而不是体检当天临时决定。

**2-column body:**

**Left — "A few common examples / 几个常见情境"**
- EN: *Family history of cancer* — targeted oncology screening (specific biomarkers, focused imaging) is more informative than generic add-ons.
- ZH: *有肿瘤家族史*：针对性的肿瘤筛查（特定标志物、相应影像）比泛泛加项更有意义。
- EN: *Hypertension or diabetes* — cardiovascular and cerebrovascular risk assessment is often more useful than additional tumor markers.
- ZH: *高血压或糖尿病*：心脑血管风险评估往往比再加几项肿瘤标志物更有信息量。
- EN: *Women* — depending on age and reproductive history, breast and gynecological screening should be planned, not bundled by default.
- ZH: *女性*：根据年龄与生育史，乳腺与妇科专项检查应当被主动规划，而不是默认套餐里的附加项。
- EN: *Conversely* — some items routinely included in standard packages may carry no clinical value in your case. Removing them is part of the design too.
- ZH: *反过来*：标准套餐里的某些项目，对您可能没有临床价值。把它们去掉，同样是方案设计的一部分。

**Right — "What the pre-screening review covers / 行前沟通的内容"**
Before you travel, YuanU coordinates an asynchronous review of:
- Basic profile — age, sex, current city, planned dates / 基本资料 — 年龄、性别、所在城市、行程时间
- Family history of major conditions (cancer, cardiovascular, metabolic) / 主要疾病的家族史（肿瘤、心血管、代谢性疾病）
- Current medications and known conditions / 当前用药与已知疾病
- Recent lab reports or imaging from your home country, if available / 所在国家近期的实验室报告或影像（如有）

The BFH·IMD physician confirms the final scope on screening day, with this context already on file.

**Closing callout (gold left border) — EN**
> **So how do the prices below fit in?** The packages priced in §6 are *reference points* — useful price ranges anchored on the IMD's standard offerings, not products on a shelf. Your actual screening list is confirmed in conversation with the BFH·IMD physician, taking the pre-screening review into account.

**Closing callout — ZH**
> **那下方的价格是什么？** §6 列出的套餐是 *参考价位段*——基于 IMD 的标准套餐，提供有用的价格区间，但不是货架上的成品。您实际的检查清单，将由 BFH·IMD 接诊医师结合前述行前沟通最终确认。

---


### 2.7 `patient-support.html`, `screening.html`, `endoscopy.html` — "escort" → "support / companion / accompany"

This change is **English-only**. The Chinese term *"陪同"* is unchanged.

**Rationale.** Two physician colleagues reviewing the v2 preview pointed out that the English word *"escort"* — when used as a noun — has a sex-work connotation in US/UK colloquial English. On a medical-coordination website that primarily serves international patients, the word can read as either confusing or off-tone. The fix:

- where *"escort"* described **YuanU's role** (i.e. the coordinator's bilingual on-site presence with the patient) → replaced with *"support"*, *"on-site support"* or *"accompanies"*.
- where *"escort"* described a **clinical hospital requirement** (i.e. "after sedation a responsible adult must be present to take the patient home") → replaced with *"companion"* or *"responsible companion"*. This matches the wording used in current ASGE patient-discharge guidance.

**Most visible change — `patient-support.html` §03**

Old EN heading: `In-Hospital Escort` → **New EN heading: `In-Hospital Support`**

Old EN boundary paragraph:
> *Boundary. We escort you to the consultation-room door; the actual clinical interaction is between the physician and the patient.*

New EN boundary paragraph:
> *Boundary. We accompany you to the consultation-room door. Our role is to help you navigate the healthcare system; medical decisions remain between you and your physician.*

Chinese (unchanged title `院内陪同`; rewritten boundary to mirror EN):
> **边界。**我们陪您到诊室门口。我们的职责是帮您在医疗体系中找到正确路径；医疗决策由您和医师共同做出。

**Other replacements (silent inline copy edits, EN only)**

| File | Old EN | New EN |
|---|---|---|
| `screening.html` (§7 process flow) | bilingual escort throughout | bilingual support throughout |
| `screening.html` (§9 fees) | escort hours | on-site coordination hours |
| `endoscopy.html` (`<meta>` description) | bilingual escort on the day of the procedure | bilingual on-site support on the day of the procedure |
| `endoscopy.html` (lede) | bilingual escort on the day | bilingual on-site support on the day |
| `endoscopy.html` (§3.4 table key) | Escort requirement | Companion requirement |
| `endoscopy.html` (§3.4 sedated row) | an escort is required (the YuanU coordinator can serve as the escort) | a responsible companion is required (the YuanU coordinator can fulfill this role) |
| `endoscopy.html` (§3.4 polypectomy row) | an escort is recommended | a companion is recommended |
| `endoscopy.html` (process flow) | The YuanU coordinator escorts you through check-in… | The YuanU coordinator accompanies you through check-in… |
| `endoscopy.html` (process flow th) | Brief debrief & YuanU-escorted discharge | Brief debrief & YuanU coordinator accompanies you out |
| `endoscopy.html` (process flow td) | The YuanU coordinator escorts you back to your hotel… | The YuanU coordinator accompanies you back to your hotel… |
| `endoscopy.html` (recovery table key) | Escort & activity | Companion & activity |
| `endoscopy.html` (recovery — unsedated) | No escort required | No companion required |
| `endoscopy.html` (recovery — sedated) | Escort required | Companion required |
| `endoscopy.html` (fees paragraph) | escort hours | on-site coordination hours |
| `endoscopy.html` (fees inclusions li) | Pickup + escort on procedure day | Pickup + on-site support on procedure day |
| `endoscopy.html` (fees inclusions li) | Post-procedure escort home / to hotel | Post-procedure accompaniment home / to hotel |

After this pass, `grep -rni "escort" --include="*.html"` returns zero results across the whole site.

---

## 3. What is **not** changed

- All other pages (`why-beijing.html`, `other-services.html`, `faq.html`, `contact.html`, `404.html`).
- On `patient-support.html` and `endoscopy.html`: **only** the English wording listed in §2.7 is touched. All Chinese copy, all section structure, all numbers, all tables, all images and all SKU/price content remain untouched.
- All `<head>` metadata, favicon reference, `data-lang` switching script, CSS variables and design tokens.
- The "Three things we coordinate" cards on `index.html`.
- The "Four facts, not four adjectives" / *为什么是远游* section on `index.html` — these four facts now act as supporting evidence for the new "why not contact the hospital directly" section.
- All factual content inside the renumbered screening sections (§6 pricing tables, §6 SKU detail blocks, §7 6-step flow, §8 report handling, §9 fees, §10 FAQ) — copy is identical to v1, only the section numbers changed.
- Trust strip, 6-step process diagram, contact form (`mailto:` placeholder), `robots.txt` (`Disallow: /` until production domain is bound).

---

## 4. Deployment

**Same as v1 — no new infrastructure required.**

If a v1 build is already pushed to a GitHub repository connected to Vercel:

```bash
unzip yuanumedical_web_v2.zip
cp -r yuanumedical_web/* path/to/your/repo/
cd path/to/your/repo
git add -A
git commit -m "Site v2: value-proposition copy pass + screening narrative (Why Beijing / not a package)"
git push
# Vercel auto-deploys on push
```

If this is a fresh deploy:

```bash
unzip yuanumedical_web_v2.zip
cd yuanumedical_web
git init && git add -A && git commit -m "Site v2"
git remote add origin git@github.com:<org>/<repo>.git
git push -u origin main
# Then: vercel.com/new → Import → Other preset → Deploy
```

No build step. No environment variables. No package.json. Static HTML/CSS/JS only.

---

## 5. Quick local preview before push

```bash
cd yuanumedical_web
python3 -m http.server 8765
# Open http://127.0.0.1:8765/
```

**On the home page (`index.html`)** you should see, top-to-bottom:

1. New hero ("The medicine is in Beijing. Building the path to it is our work.")
2. Trust strip (4 numbers)
3. **NEW** "Why not just contact the hospital directly?" — three paragraphs + italic teal closing line
4. "A licensed coordinator. Not a medical institution." (now opening with the value statement)
5. "Three things we coordinate"
6. "Four facts, not four adjectives" — for-why-YuanU
7. 6-step process
8. Closing CTA

**On the screening page (`screening.html`)** you should see, top-to-bottom:

1. Hero (unchanged)
2. §2 Screenings happen at the IMD — not the general clinic *(unchanged)*
3. §3 Five typical patient profiles, and where to start *(unchanged)*
4. **NEW §4** Why come to Beijing for screening — three pillars + gold callout
5. **NEW §5** A screening is not a package — how we design yours — examples + pre-screening scope + gold callout
6. §6 Reference pricing — 15 SKUs *(was §4, content unchanged, eyebrow now §4.6)*
7. SKU detail blocks: Male / Female (Unmarried) / Female (Married) *(eyebrow now §4.6)*
8. §7 How the screening day works · 6 steps *(was §5)*
9. §8 How we handle your report *(was §6)*
10. §9 Fees & what's included *(was §7)*
11. §10 Screening-specific FAQ *(was §8)*

Section background alternates `s` / `s alt` cleanly across all sections — visually unbroken.

---

## 6. Open items for your review

- [ ] Proofread the EN closing line of the index "Why not contact the hospital directly?" section: *"That is the difference between getting an appointment and being correctly placed in a clinical pathway."* — confirm "clinical pathway" is the wording you want for this audience (vs. "care pathway" / "treatment pathway").
- [ ] Review the new screening §4 / §5 copy for clinical accuracy — particularly the three pillar claims in §4 (specialist density / examination breadth / downstream care) and the four example scenarios in §5 (cancer family history / hypertension+diabetes / women's screening / removing low-value items).
- [ ] Confirm `mailto:` form on `contact.html` is acceptable for the soft-launch period, or schedule the Formspree / Tally migration.
- [ ] Confirm the `robots.txt` switch (`Disallow: /` → `Allow: /` + sitemap) at the moment the production domain `yuanumedical.com` is live.

---

*Owner contact: zhangjianping@yuanu.com*
