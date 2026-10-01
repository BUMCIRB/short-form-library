# Review pass 1: structure, links, terminology, references, contradictions, mechanics

**Source reviewed:** `dc0d637b-BMC_BUMC_IRB_Site_First_Draft.html`, a single bundle that embeds every page as JSON. It contains **112 pages**, not 118 (the bundle's own banner also says 112). Pages were extracted to individual files and analyzed from the public `<main>` content only; the "Reviewer notes" sections were excluded from text analysis but are flagged below. External URLs were inventoried, not fetched. HTML was not edited.

**Site structure (from the bundle's nav data):** Home + 5 hubs. Before You Submit (51 pages), Consent, HIPAA & Recruitment (12), Post-Approval (6), Guidance (26), About the IRB (11). Only the Home page sits outside a hub. 234,000 words of public text in total; the median page is about 1,900 words, and six pages exceed 4,000 (longest: Example_Expedited_Interview_Study at 12,665).

**iRIS:** zero occurrences anywhere in the public text, the decision-tool logic, or the reviewer notes.

---

## 1. Internal links

Scripted check of every `href` in all 112 pages (7,219 anchors; 4,805 internal links, 1,514 of them with `#fragment`; 134 distinct `.html` targets, of which 112 are site pages and 22 are external `.html` URLs). The Review Path Decision Tool's links live in its JSON logic block and inline scripts; those were extracted and tested too.

| Check | Result |
|---|---|
| Internal links to a file not in the set | **0** |
| Links whose `#fragment` has no matching `id` on the target page | **0** |
| Body-content links from a page to itself (without a fragment) | **0** |
| Same target linked more than once inside a single section | **21** (table below) |
| Internal link stubs written as bracketed text, not hyperlinks | **45** `[…, new site URL]` on the five INSPIR task pages and Student_Trainee_Research (see §6); these are effectively missing links |

### 1a. Duplicated links within one section

| Page | Location | Link texts | Target | Suggested fix |
|---|---|---|---|---|
| Expedited_Tip_Sheets_Index | section menu / index list | "Blood draws" and "2" both link | Expedited_Tip_2 | Intentional (number + name) but the bare numeral is a poor link target; link the whole row once |
| Expedited_Tip_Sheets_Index | same | "Noninvasive specimens" / "3" | Expedited_Tip_3 | same |
| Expedited_Tip_Sheets_Index | same | "Noninvasive procedures" / "4" | Expedited_Tip_4 | same |
| Timelines_and_JIT | How long review takes | "IRB Review Times" ×2 | IRB_Review_Times | keep one |
| Consent_Language_Bank | Use and Sharing of Your Health Information | "HIPAA Waiver Questions: Sample Answers" ×2 | HIPAA_Waiver_Sample_Answers | keep one |
| Templates_Forms_Library | Consent forms and information sheets | "Translating study documents" ×2 | Limited_English_Proficiency#translation | keep one |
| Templates_Forms_Library | Consent forms and information sheets | "Choosing a consent template" ×2 | Consent_Templates#which-template | keep one |
| Templates_Forms_Library | Parental permission and assent | "Forms for children's research" ×2 | Research_Involving_Children#forms | keep one |
| Templates_Forms_Library | HIPAA | "Case Reports and Case Series" ×2 | Case_Reports | keep one |
| Templates_Forms_Library | Other forms and references | "Adults lacking capacity" ×2 | Special_Populations#capacity | keep one |
| Short_Form_Consent_Process | Before the consent discussion | "interpreter" / "interpreter rules" | Limited_English_Proficiency#interpreters | keep one |
| Glossary_A_to_Z | I | "Do I Need IRB Review?" ×2 | Do_I_Need_IRB_Review#definitions | keep one |
| Announcements | Announcements (main list) | "Ancillary Reviews and Sign-Offs" ×3 | Ancillary_Reviews_Sign_Offs | three separate items link the same page; fine if each is a distinct announcement, otherwise merge |
| Announcements | Announcements | "Reporting and Monitoring" ×2 | Reporting_and_Monitoring | as above |
| Announcements | Announcements | "Exempt Research" ×2 | Exempt_Research | as above |
| Announcements | Does it need IRB review? | "Do I Need IRB Review?" ×2 | Do_I_Need_IRB_Review | as above |
| Announcements | Does it need IRB review? | "Working with Other Institutions" ×2 | Working_with_Other_Institutions | as above |
| Announcements | Consent | "Obtaining Consent" ×2 | Obtaining_Consent | as above |
| Announcements | Recruitment, screening, and payment | "Recruitment and Screening" ×2 | Recruitment_and_Screening | as above |
| Announcements | After approval | "Reporting and Monitoring" ×2 | Reporting_and_Monitoring | as above |
| Announcements | ClinicalTrials.gov | "ClinicalTrials.gov Requirements" ×2 | ClinicalTrials_gov | as above |

### 1b. Pages with the fewest inbound links (reachability)

| Page | Inbound links from other pages | Note |
|---|---|---|
| For_Research_Participants_ES | 3 | Reached only from the English participants page, Home, and the About hub. Not in the section menu. Decide whether Spanish should appear in the global nav. |
| INSPIR_Task_Checkins_Reports_Closing | 4 | A core post-approval task page with fewer inbound links than any tip sheet. Link it from Continuing_Review_and_Closing, Reporting_and_Monitoring, FAQ, and Start_Here. |
| Example_Expedited_Interview_Study | 8 | Fine for an example page. |
| INSPIR_Task_Records_and_Training | 9 | Link from Training_Requirements and Study_Team_Members. |

### 1c. External link inventory (not tested)

1,021 external hrefs. Hosts: bumc.bu.edu 463 · bu.edu 334 · ecfr.gov 91 · wwwapp.bumc.bu.edu 66 (PI home-institution lookup and similar app pages) · fda.gov 31 · inspir.bu.edu 34 · mymedia.bu.edu 28 · grants.nih.gov 27 · hhs.gov 26 · bmc.org 23 · regardd.org 12 · govinfo.gov 9 · malegislature.gov 6 · others ≤5 each (smartirb.org, clinicaltrials.gov, aahrpp.org, citiprogram.org, redcap.bumc.bu.edu, va.gov, etc.). The 463 bumc.bu.edu links include the current IRB site, which will presumably be retired; plan a redirect map. The 32 HRPP policy links that carry a `#section` anchor (e.g. `hrpp-policies-procedures/#6.6.4`) depend on the policies page keeping those anchors; verify they resolve.

---

## 2. Terminology

Exact-string variant extraction across the public text of all 112 pages. Full tables with counts and page locations are in **Appendix A**. The items below are where variation will confuse a non-regulatory reader or make the site hard to search.

| Term family | Variants found (count) | Issue | Suggested standard |
|---|---|---|---|
| **HRPP citation label** | "HRPP 6.6.4" style (335 on 78 pages) · "section 6.6.4" (53) · "HRPP Policy 6.6.4" (34, concentrated on Expedited_and_Full_Board_Review, Exempt_Research, Amendments) · "HRPP section 6.6.4" (32) · "Section 6.6.4" (26) · "HRPP Section 6.6.4" (16) · "HRPP policy 6.6.4" (7) · "HRPP policy section" (3) · "policy 6.6.4" (2) · "Policies 2.1.2 and 10.2.4.1" and ranges "10.2.1.1 to 10.2.1.3" in several forms · "section6.6.4" (no space, 6 in the decision tool) | Ten-plus spellings for one thing. Readers cannot tell "Section 6.6.4" (of what?) from an INSPIR section. | Pick one, e.g. **"HRPP 6.6.4"** linked to the anchor, and never a bare "Section N" or "Policy N". |
| **HRPP program name** | "HRPP Policies and Procedures" (99) · "HRPP policy" (68) · "HRPP Policies" (10) · "HRPP policies" (8) · "Human Research Protection Program" (9) · "Human Research Protection Program**s**" (2, Glossary and Policies_and_Regulations) | Casing drift; one plural error. | "HRPP Policies and Procedures" as the document title; "HRPP policy" lower-case in prose; expand HRPP once per page. |
| **Our IRB's name** | "BMC/BUMC IRB" (171 incl. "the") · "BMC/BUMC Institutional Review Board" (Home H1) · "Boston Medical Center and BU Medical Campus IRB" (every page's co-brand strip; Example_Exempt_Chart_Review) · "Boston Medical Center and Boston University Medical Campus IRB" (VA_Research, Contact_and_About, Consent_Language_Bank) · "Boston Medical Center and Boston University Medical Campus Institutional Review Board" (FAQ) | Three long forms. | One long form on first mention (match the co-brand strip), "BMC/BUMC IRB" thereafter. |
| **Charles River Campus IRB** | "Charles River Campus IRB" (9 pages) · "BU Charles River Campus IRB" (5) · "CRC IRB" (6) | Readers off campus will not know CRC. | "BU Charles River Campus IRB (CRC IRB)" on first mention, "CRC IRB" after. |
| **INSPIR** | "INSPIR" (806) · "INSPIR II" (5: INSPIR_Task_Records_and_Training ×4, INSPIR_Task_Change_Approved_Study ×1) · "inspir.bu.edu" (2, URLs, fine) · iRIS **0** | "INSPIR II" appears only in source citations ("INSPIR II Instructions for Investigators"); harmless if that is the document's title, confusing if it leaks into prose. | Keep "INSPIR" everywhere; keep "INSPIR II" only inside a quoted document title. |
| **Full board / convened** | "full board" (74) · "Full Board Review" (34) · "Full Board" (18) · "Full board" (18) · "full board review" (14) · "Full board review" (5) · "full-board" (1) · "convened IRB" (17) · "convened meeting" (17) · "convened board" (11) · "convened review" (5) · "Convened board" (4) · "convened board review" (3) · "convened IRB meeting" (3) · "Convened IRB" (3) · "Convened review" (2) · "convened" alone (6) | Two names for the same review level, each in many casings. | Lower-case "full board review" in prose (the HRPP uses "convened"; say once that they mean the same). Capitalize only INSPIR labels. |
| **Risk level** | "minimal risk" (128) · "Minimal risk" (41) · "minimal-risk" (27, hyphenated adjective) · "greater than minimal risk" (37) · "Greater than minimal risk" (9) · "**more than** minimal risk" (21 on 12 pages; 8 on Special_Populations) · "greater-than-minimal-risk" (1) | "more than minimal risk" and "greater than minimal risk" read as two categories. | "greater than minimal risk" everywhere (regulatory phrase). Hyphenate only as a modifier. |
| **NHSR** | "Not Human Subjects Research" (23) · "not human subjects research" (26) · "Not human subjects research" (11) · "Not Human Subject Research" (7, singular: this is the actual INSPIR option label) · "NHSR" (82) | The INSPIR label is singular; prose is plural. | Quote the INSPIR label exactly, in quotes, when naming the option; use "not human subjects research (NHSR)" in prose. |
| **Status check-in** | "status check-in" (41) · "Status Check-In" (14) · "Status check-in" (8) · "check-in" (28) · "Status Check-In Report" (Announcements, Ceding_Review) · "Continuing Review Submission Form (status check-in)" (INSPIR task table) | A reader cannot tell whether "Status Check-In Report" is a form, a status, or a task. | Lower-case "status check-in" in prose; give the INSPIR form's exact label once in the task page. |
| **Closing a study** | "Closure Report" (29) · "Final/Closure Report" (Continuing_Review) · "Study Closure" (2) · "closure report" (1) · "Closeout" (4) / "closeout" (2) / "close-out" (1) · "final report" (4: Start_Here, Exempt_Research, Working_with_Other_Institutions, FAQ) | Five names for one submission. | Use the INSPIR form name once, then "closure report". Drop "final report" and "closeout". |
| **Continuing review form** | "Continuing Review Form" (6, INSPIR_Task_Checkins) · "Continuing Review Submission Form" (same page's table) · "continuing review (a progress report)" (Continuing_Review) · "Progress Report" (Expedited_Tip_9 ×4, Humanitarian_Use_Devices) | Which is the INSPIR label? | Confirm the label in INSPIR and use it once per page; "progress report" only when quoting the HRPP or FDA. |
| **Reportable events form** | "Reportable Events and New Information form" (17) · "… (RENI) form" (4) · "… Form" (3) · "RENI" (32) · "Reportable Event" (1, Humanitarian_Use_Devices) | Mostly consistent; RENI used before expansion on some pages (see pass 2). | Expand on first use per page. |
| **Supervising PI** | "Supervising PI" (71) · "Supervising Principal Investigator" (INSPIR question label) · "Faculty Sponsor" (3, always as "formerly") | Fine. INSPIR still shows "formerly known as Faculty Sponsor"; keep the bridge for one more year. | none |
| **Study team roles** | "Study Personnel" (54) / "study personnel" (46) · "Study Team Members" (11) / "study team member(s)" (11) · "study staff" (28) / "Study staff" (5) · "research staff" (11) / "Research Staff" (11) · "Research Support Staff" (13, the INSPIR role) · "Key Personnel" (7, INSPIR tab) | Role names and generic nouns are interchanged. | Generic: "study team". INSPIR role names capitalized exactly as INSPIR shows them ("Research Support Staff", "Study Contact", "Administrative Assistant"). |
| **Reliance** | "reviewing IRB" (54) · "IRB of record" (29) · "Reviewing Institution" (4) / "Relying Institution" (5) · "reliance agreement" (33) · "IRB Authorization Agreement" (7) / "Authorization Agreement" (7) / "IAA" (7) · "SMART IRB" (19, consistent) · "cede/ceding/ceded review" in 11 casings | Acceptable set, but "reviewing IRB" and "IRB of record" alternate on the same pages (Ceding_Review, Glossary). | Define both once in Ceding_Review and Glossary; prefer "reviewing IRB" elsewhere. |
| **Participant vs subject** | "participant(s)" 691 · "subject(s)" 317 · "human subject(s)" 206 · "volunteer(s)" 8 | "subjects" clusters on INSPIR_Task_Change (13), For_Board_Members (13), Amendments (9), Continuing_Review (8), Reporting_and_Monitoring (8). | "participant" in prose; "human subjects research" as the term of art; "subject" only when quoting policy or INSPIR. |
| **Electronic consent** | "eConsent" (10) · "e-consent" (9) · "electronic consent" (8) · "e-Consent" (3) | Four spellings. | one |
| **Training** | "CITI" (65) · "Medical Campus CITI" (7) · "human subjects training" (18) · "human subjects protection training" (5) · "Human Subjects Protection training" (1) · "HSP" (tags) · "GCP" (60) / "Good Clinical Practice" (12) | OK if expanded on first use. | "human subjects protection training (through CITI)" first mention; "GCP" after one expansion. |
| **Contacts** | "(617) 358-5372" (33) vs "617-358-5372" (5: Consent_Language_Bank ×2, Informed_Consent_Overview, Consent_Templates, Templates_Forms_Library) · "HIPAA@bu.edu" (4) vs "hipaa@bu.edu" (3) · "DUA.MTARequest@bmc.org" (3) vs "DUA.MTArequest@bmc.org" (1) · "CTO@bmc.org" vs "cto@bmc.org" · interpreter line "(617) 414-5549" vs "617-414-5549" | Format drift. The Example study's "617-555-0142" is a fictional number (fine). | One phone format; lower-case email addresses. |
| **Offices** | "Clinical Research Resources Office" (54) / "CRRO" (138) · "Clinical Trial Office" (42) / "CTO" (19) · "Office of Human Research Affairs" (5) / "OHRA" (27) · "Privacy Officer" (21) / "Privacy Office" (9) · "Information Security" / "BUMC Information Security" | CRRO and OHRA are used far more often as acronyms than as names; many pages never expand them (pass 2 flags per page). | Expand on first use per page. |

---

## 3. Policy and regulatory references

**893 references** extracted (Appendix B lists every one with page, section, exact text, and surrounding context, for spot-checking against the current HRPP Policies and Procedures). Correctness was not judged.

| Type | Count |
|---|---|
| HRPP citations in running text ("HRPP 6.6.4", "HRPP Policy 10.2.4.1", etc.) | 418 |
| Bare "Section N" / "Policy N" citations with no "HRPP" | 40 |
| HRPP hyperlinks with a `#section` anchor | 32 |
| Federal regulations (45 CFR 46, 21 CFR 50/56/312/812, 42 CFR 11 and Part 2, 45 CFR 160/164, §-only cites) | 239 |
| Exempt / expedited category numbers | 51 |
| Massachusetts law (M.G.L., CMR) | 17 |
| Named guidance and other (Common Rule, Belmont, FDA/OHRP/NIH guidance and notices, GINA, FERPA, Cures Act, SACHRP, AAHRPP) | 96 |

**Spot-check priorities (highest risk of being stale or wrong):**

| Page | Location | Reference text | Why spot-check |
|---|---|---|---|
| IRB_Home; Paying_Participants; Responding_to_Stipulations; Limited_English_Proficiency; Short_Form_Consent_Process; Announcements | various | Citations that carry a revision date: "HRPP 7.2.2.2, revised July 20, 2026"; "HRPP 7.2.2.11, revised September 16, 2026"; "HRPP 7.4.6, revised July 2026"; "HRPP 8.4.5.2, revised May 26, 2026"; "HRPP 8.1.3.4 and 7.2.2.6.5 … September 16, 2026" | Five dated cites; the Home announcement bar says "Updated HRPP policies took effect September 16, 2026." Confirm each section number survived the September revision. |
| Responding_to_Stipulations | How long you have to respond | "HRPP 7.4.6, revised July 2026": reminders at 60 days, 6 months, 15 months; administrative closure at 18 months | New rule; confirm numbers. |
| Continuing_Review_and_Closing; INSPIR_Task_Checkins | Restarting a lapsed study; table | "HRPP 6.6.2.1.5.1", "HRPP 10.4.1.4", "HRPP 6.6.6" | Deep section numbers most likely to shift after renumbering. |
| Reporting_and_Monitoring; Announcements | tables | Ranges like "HRPP Policies 11.2.1 to 11.2.4, 11.3, …" (one cite lists 9 sections) | Ranges hide individual misses. |
| Exempt tip sheets (13 pages) | Details | "Sections 10.2.2.4.1.x" and local categories 9–13 "(HRPP 10.2.2.4.1.3)" | Repeated from one template; one error would replicate 13 times. |
| Expedited_Tip_2/3/4 | Details | "Local categories 10 to 12 (HRPP 10.2.2.4.1.3) … (HRPP 2.1.2)" | Same cite used for exempt local categories elsewhere; check it is the right section for expedited local categories. |
| Data_Retention; Data_Security | tables | "BMC policy #39.04.455", "BU policy #FA-002", "HRPP 6.6.7.1 and 8.3.3" | Institutional policy numbers outside the HRPP. |
| ClinicalTrials_gov; Announcements | results posting | "42 CFR 11.64"; "HRPP 6.6.9" 10-month results deadline | Local rule stricter than federal; confirm. |
| All 40 bare "Section N" cites | see Appendix B rows marked "section"/"Section" | e.g. "section 2.3.3.1", "Section 6.2.3" | Ambiguous (HRPP? INSPIR?). Convert to the standard label. |

---

## 4. Cross-page contradictions and misalignments

Checked by extracting every statement with a number, deadline, contact, form name, or meeting schedule, grouping by topic, and reading the groups. Consistent across all pages (no action): two boards meet every three weeks on Thursdays with the agenda locked the Friday before; office hours Monday to Friday 9:00 a.m. to 4:30 p.m.; continuing review due at least 4 weeks before expiration; status check-ins every 3 years; 7-calendar-day reporting deadline; 7-year record retention; $2,000 IRS threshold; case reports of more than three patients are research; three short-form uses per language then a translation, with the 30-day rule only for greater-than-minimal-risk studies; 30-day appeal window.

| # | Pages | Location | Issue | Suggested fix |
|---|---|---|---|---|
| 1 | Data_Retention · Data_Security_for_Researchers · Chart_Review · Example_Exempt_Chart_Review · Example_Expedited_Interview_Study · Before_and_After_Examples | master code / Destruction of Identifiers | **Master code retention is stated three different ways.** Data_Retention presents "Keep it 7 years" and "Destroy it early" as open options under a `[PENDING DECISION]`; Data_Security says "being clarified … analysts currently give opposite instructions"; but Chart_Review states as a rule "when you will destroy the master code … as a milestone … while keeping study records for at least 7 years", and Data_Retention's own intro says "plan to remove identifiers, such as the master code, as early as your study design allows." The two example applications carry `[PENDING DECISION]` tags in their model answers. | Decide, then state the rule in one sentence on Data_Retention and have every other page link to it. Until then, Chart_Review and the Data_Retention intro should hedge the same way Data_Security does. |
| 2 | Responding_to_Stipulations · Expedited_and_Full_Board_Review · For_Board_Members | How long you have to respond; outcomes table; "There is no deadline." | **"No deadline" vs an 18-month administrative closure.** Responding_to_Stipulations says "Answering stipulations or a deferral has no deadline in the policy" and, two paragraphs later, that the IRB closes the submission after 18 months (HRPP 7.4.6, revised July 2026) with reminders at 60 days, 6 and 15 months. Expedited_and_Full_Board_Review and For_Board_Members repeat "no deadline" without the closure rule. | Replace "no deadline" everywhere with: "There is no response deadline, but INSPIR reminds you at 60 days, 6 months and 15 months, and the IRB closes an unanswered submission at 18 months." |
| 3 | Timelines_and_JIT · Expedited_and_Full_Board_Review · Responding_to_Stipulations · IRB_Review_Times | intro vs planning advice | **Full board timeline: 71 days vs four to five months.** Timelines_and_JIT opens with Q1 2026 medians (32 / 43 / 71 days) and only later says to plan on four to five months and that the 71-day figure rests on four reviews. The other three pages lead with "plan on four to five months". A skimmer leaves Timelines_and_JIT with 71 days. | Lead Timelines_and_JIT with the planning figure; move the medians into the table with the caveat beside them. |
| 4 | Chart_Review · Review_Path_Decision_Tool_v3 · INSPIR_Task_Choose_Review_Path · Do_I_Need_IRB_Review · INSPIR_Task_Access_and_New_Study | Review Path Determination option 3 | **Is the "chart review" review path live?** Chart_Review flags "[NOT IN SEPT 2026 PRINTOUTS; CONFIRM: no chart review path was printed, and a revision is in progress]" and INSPIR_Task_Choose_Review_Path flags "the chart review application is not in the Sept 2026 printouts", yet the decision tool, Do_I_Need_IRB_Review and the new-study task page present option 3 ("The only research activities … involve chart reviews with no subject interaction") as a current choice with its own application sections. | Confirm in INSPIR; either describe the option identically on all five pages or remove it from the tool until the revision lands. |
| 5 | Study_Team_Members · Student_Trainee_Research | PI eligibility | **Dental school exception missing from the student page.** Study_Team_Members: "At the Goldman School of Dental Medicine, only faculty may be PI." Student_Trainee_Research ("Who can be PI") and Study_Team_Members' own roles table say any student or trainee may be PI with a Supervising PI, with no exception. | Add the GSDM sentence to Student_Trainee_Research and to the roles table. |
| 6 | Training_Requirements · Drugs_and_Devices · Clinical_Trials · Glossary_A_to_Z · Study_Team_Members | renewal rules | **Renewal stated as settled on four pages and as pending on the fifth.** Training_Requirements: "both are currently renewed every three years" plus seven `[PENDING DECISION: HSP refresher]` tags and "Wording of renewal and expiration rules held pending the HRPP Advisory Committee's decision on Section 6.2.3." Drugs_and_Devices ("renewed every three years (HRPP 6.2.3)"), Clinical_Trials, Glossary state the three-year rule flatly. | Once the committee decides, update Training_Requirements first and make the other four pages link to it instead of restating the interval. |
| 7 | Amendments · Study_Team_Members · Continuing_Review_and_Closing · INSPIR_Task_Change_Approved_Study | change of PI | **PI-change requirements differ by page.** Study_Team_Members requires "the new PI's signed acknowledgement of PI responsibilities (a PDF of an acknowledging email also works)" and new consent forms; Amendments' table and the INSPIR task page describe the same change without the acknowledgement. Continuing_Review mentions the form only. | State the attachment requirement wherever the PI-change form is named, or on the task page only with the others linking there. |
| 8 | Continuing_Review_and_Closing · INSPIR_Task_Checkins_Reports_Closing | reminders | Continuing_Review lists exact continuing-review reminders (7, 6, 5, 2 weeks, 1 day) but for status check-ins says "1 year and 2 years after approval, and again before the due date [UNVERIFIED: how many days]". The task page gives no reminder schedule. | Confirm the check-in reminder schedule and state it once. |
| 9 | Timelines_and_JIT · FAQ | Just-in-Time contact | Timelines_and_JIT: "email the IRB Director at medirb@bu.edu [CONFIRM: medirb or the Director's own address]". FAQ: "email medirb@bu.edu with your INSPIR study number and the date" (no Director). | Resolve the tag; make both pages say the same address and the same attachments. |
| 10 | Amendments · Exempt_Research | exempt amendment triggers | Lists match in substance, but Exempt_Research adds "If you receive external funding after your determination, tell the IRB within 14 days"; Amendments lists "funding" with no 14-day rule. | Add the 14-day rule to Amendments or link to Exempt_Research. |
| 11 | Continuing_Review_and_Closing (table row) | Exempt determination before January 21, 2019 | "Continuing review form (short exempt version) · Every 3 years (the determination has an expiration date)"; everywhere else the site says pre-2019 exempt determinations have an expiration date but gives no interval. | Confirm the interval for legacy exempt studies and make Exempt_Research and Announcements match. |
| 12 | Student_Trainee_Research · Obtaining_Consent | who may obtain consent | Student page: "Residents and fellows do not count as licensed independent practitioners (LIPs) for consent unless fully licensed and members of the Medical-Dental Staff; see Obtaining Consent." Obtaining_Consent never uses "licensed independent practitioner" or "LIP". | Add the LIP rule to Obtaining_Consent or change the cross-reference. |
| 13 | Continuing_Review_and_Closing · INSPIR_Task_Checkins_Reports_Closing | Final/Closure Report steps vs table | **Does the PI sign the closure report?** Continuing_Review: "The PI must approve and sign off before the IRB receives it." Task page: "A Final/Closure Report … do[es] not need the PI's signature under IRB policy, so any team member with edit access can submit." | Pick one; the task page's own table ("No, but the PI should review it") suggests the policy answer. |
| 14 | INSPIR_Task_Change_Approved_Study · INSPIR_Task_Checkins_Reports_Closing | Contact Information Change Request | Same question for contact-info changes: one page says no PI signature; the other's step list ends with "Signoff and Submit or Notify PI for Signoff". | Align the step list with the rule. |
| 15 | Recruitment_and_Screening · Amendments | materials finalized after approval | Recruitment_and_Screening: use the Recruitment Materials Submission Form. Amendments: "If materials were still in draft at initial review, submit the final versions as an amendment." | State the rule once: which form for new promotional materials vs materials that were drafts at approval. |
| 16 | FAQ · Working_with_Other_Institutions | adding people after approval | FAQ: "Adding or removing study staff, on any study, goes through an Internal Study Personnel Changes form." Working_with_Other_Institutions: adding any external investigator or site requires a Change Request and Amendments form, even under an existing reliance agreement. | Add "internal (BMC/BU)" to the FAQ answer and link to the external rule. |
| 17 | Chart_Review · INSPIR_Task_Choose_Review_Path · Do_I_Need_IRB_Review · Review_Path_Decision_Tool_v3 | de-identified or coded data with no key | Chart_Review: for an honest-broker data set with no identifiers, "submit a Not Human Subjects Research request." Choose_Review_Path: submit only if the data include a HIPAA identifier, "otherwise submit only if you want a determination letter." Do_I_Need says "No (submit if you want a letter)"; the decision tool says "Submit an NHSR request so the IRB can confirm." | Decide whether an NHSR submission is required or optional for key-less coded/de-identified data, then say the same thing on all four pages. |
| 18 | Consent_Templates · Limited_English_Proficiency | short form for expected languages | Consent_Templates: "If you expect only a few, the IRB may approve the short form instead." LEP page: the short form "is only for people whose language you did not expect to encounter", and requesting it for an expected language is a common stipulation. | Make Consent_Templates match the LEP page. |
| 19 | Obtaining_Consent · Example_Exempt_Chart_Review | consent for chart reviews | Obtaining_Consent's quick reference pairs every chart review with a "waiver of consent, plus a HIPAA waiver"; the exempt chart review example (correctly) requests only a HIPAA waiver. | Add "non-exempt" to the Obtaining_Consent row. |
| 20 | Consent_Templates · Consent_Language_Bank · Templates_Forms_Library | template version/date | Payment language "updated on September 16, 2026" but the Adult Consent Form Template is still listed as "1.14, May 8, 2026" and the Language Bank says it matches 1.14. | Bump the version/date or explain. |
| 21 | Data_Security_for_Researchers · Mandated_Reporting_and_Safety_Plans · Remote_Decentralized_Research | HRPP 9.7.2 | The same citation supports two different rules (Certificates of Confidentiality on Data_Security; mandated reporters on the other two). | One of them is wrong; check both. |
| 22 | Start_Here · Drugs_and_Devices · ClinicalTrials_gov · Review_Path_Decision_Tool_v3 | when a separate protocol is required (HRPP 7.2.2.20) | Four wordings: "drug, biologic, device, or surgical intervention; multi-site or NIH-funded; or must post results" (Start_Here, Drugs_and_Devices) vs "medical or surgical clinical trials, multi-site, NIH-funded, and any study required to post results" (ClinicalTrials_gov) vs the decision tool, which omits the results-posting trigger. | One sentence, quoted from the policy, reused on all four. |
| 23 | Drugs_and_Devices · ClinicalTrials_gov · Drug_Device_Decision_Guide | PI-initiated trials; NSR devices | Drugs_and_Devices omits the IRB Director waiver of the CRRO consultation that ClinicalTrials_gov describes (HRPP 6.2.1.2); the Decision Guide omits the "FDA decides the study is NSR" path that Drugs_and_Devices gives. | Align. |
| 24 | Expedited_Tip_8 · Expedited_Tip_9 · INSPIR_Task_Checkins | continuing review form name | "Continuing Review Submission Form" (Tip 8, task page) vs "Progress Report" (Tip 9, four times). | Use the INSPIR label. |
| 25 | Study_Team_Members · INSPIR_Task_Access_and_New_Study · Preparing_a_Complete_Submission · Student_Trainee_Research | Study Contact's second role; GSDM PI rule | Study_Team_Members lists five roles a Study Contact may also hold, including Administrative Assistant; the new-study task page names only "Additional Investigator or Research Staff". Preparing_a_Complete_Submission and Study_Team_Members both carry the dental-school faculty-only rule; Student_Trainee_Research does not (see item 5). | Align the role list and add the GSDM rule to the student page. |
| 26 | Announcements · Policies_and_Regulations | where changes are announced; CRC personnel rule | Announcements: changes are announced "on this page, in the CR Times newsletter, and … by email". Policies_and_Regulations: "in the CR Times newsletter, on the OHRA website, in INSPIR and, when needed, by email." Announcements says CRC faculty, staff and students join through a regular personnel change (HRPP 2.5.2.1); Policies says the policy text covers students only, "in practice also faculty and staff". | One list of channels; one statement of the CRC rule that matches the policy text. |
| 27 | For_Research_Participants_ES · For_Research_Participants | contact section | Spanish page promises "le responderemos en español"; the English page makes no such promise and the Spanish page has no link back to English. | Decide whether to promise Spanish replies; add the language toggle. |

---

## 5. Mechanical

### 5a. Site-level

| Page(s) | Location | Issue | Suggested fix |
|---|---|---|---|
| all 112 | `<title>` | Every title tag is a working title: 92 end in "(DRAFT v1) \| BMC/BUMC IRB", 20 in "… Draft v1", the Spanish page in "(BORRADOR v1, español)". | Set `<title>` to the H1 plus " \| BMC/BUMC IRB" at build. |
| 20 pages: IRB_Home, the 5 hubs, the 5 INSPIR_Task pages, Amendments, Continuing_Review_and_Closing, Reporting_and_Monitoring, Informed_Consent_Overview, Consent_Templates, Consent_Language_Bank, Templates_Forms_Library, Example_Amendment_and_Stipulation_Response, Review_Path_Decision_Tool_v3 | page shell | Two template families. These 20 use the older shell (serif body, `.chapters` "On this page" nav, "/"-separated breadcrumbs, `.meta` line, `[Table]`/`[Callout]` component labels) while 92 use the newer `.masthead` shell (section menu with nested TOC, `.metabar`, `[wp]` labels). | Re-export the 20 in the current template before handing to the WordPress build. |
| 15 pages: IRB_Home, 5 hubs, 5 INSPIR_Task pages, Amendments, Continuing_Review_and_Closing, Reporting_and_Monitoring, Example_Amendment_and_Stipulation_Response | bottom of page | A `<section class="review">` "Reviewer notes" block is still in the HTML, with round-by-round edit logs and staff names. The 92 newer pages have had it stripped. | Strip before build. |
| Review_Path_Decision_Tool_v3 | whole page | Different shell again: no co-brand strip, section menu, breadcrumb, "Last reviewed" or page-owner line; the H1 sits outside `<main>`; filename lacks the `_DRAFT_v1` convention; `<title>` differs from nav title. Needs JavaScript (noscript fallback present). | Wrap in the standard shell; add metabar. |
| For_Research_Participants_ES | metabar | No "Last reviewed" line (the only content page without one besides the tool). | Add. |
| 32 pages | boilerplate paragraph | "The Clinical Research Resources Office (CRRO) offers tools, templates, and training for BMC and BU Medical Campus study teams." appears verbatim on 32 pages; 13 exempt tip sheets share two identical paragraphs; 9 expedited tip sheets share three; 7 exempt tips share a prisoners paragraph. | Make these reusable blocks in WordPress so one edit propagates. |
| Example_Expedited_Interview_Study; HIPAA_Waiver_Sample_Answers | "Questions" | H2 with a single 7-word line. | Fold into the footer contact line. |
| Application_Section_Tips; Eligibility_and_Study_Design; Example_Amendment_and_Stipulation_Response; Paying_Participants | — | "TBD", "H-XXXXX", "$xxx" are quoted examples or fictional IDs, not placeholders (false positives of the scan). | none |

### 5b. Duplicate or near-duplicate pages

No two pages are duplicates. The closest pairs are template siblings: Exempt_Tip_3-1 ↔ 3-2 (25% shared 8-word shingles), Expedited_Tip_2 ↔ 4 (19%), Expedited_Tip_8 ↔ 9 (18%), Exempt_Tip_2-2 ↔ 3-2 (18%). Hub_Before_You_Submit and IRB_Home share the "Why submissions come back" list. Contact_and_About and Staff_Directory both carry the full contact block (email, phone, hours). FAQ and Glossary restate rules that live on topic pages (board schedule, QI criteria, short form, $2,000 threshold); each restatement is a future drift point.

### 5c. Open items still visible in the page text

The bundle's own banner says bracketed tags are open items. Counts from the public text, excluding the Consent_Language_Bank's deliberate fill-in brackets such as `[name]` and `[phone number]`:

| Marker | Count | Meaning in the draft |
|---|---|---|
| Red `[chk]` tags | 113 | INSPIR steps/labels to confirm against the live system (mostly the 5 INSPIR task pages: 62) |
| Yellow `[ck]` tags | 271 | Lower-priority confirms; 252 on the INSPIR task pages |
| Purple `[unv]` tags | 229 | Unverified facts |
| `[UNVERIFIED: …]` bracket text | 123 | |
| `[CHECK IN INSPIR: …]` | 77 | |
| `[…, new site URL]` link stubs | 45 | Unbuilt links on INSPIR_Task pages and Student_Trainee_Research |
| `[CHECK: …]` | 33 | |
| `[PENDING DECISION: …]` | 32 | HSP refresher (10), master code (5+), others |
| `[PENDING: …]` / `[PENDING]` | 22 | |
| `[NOT IN SEPT 2026 PRINTOUTS; CONFIRM: …]` | 9 | Chart_Review (6), Preparing_a_Complete_Submission, others |
| `class="planned"` / `pend` / `pending` / `unverified` spans | 115 | Mostly Short_Form_Consent_Process (22), Exempt_Research (14), Expedited_and_Full_Board_Review (15), Social_Media (15), Chart_Review (14) |

Pages with the most open items: INSPIR_Task_Access_and_New_Study (107), INSPIR_Task_Checkins_Reports_Closing (95), INSPIR_Task_Change_Approved_Study (94), INSPIR_Task_Records_and_Training (90), Responding_to_Stipulations (32), Short_Form_Consent_Process (29), Chart_Review (28), Paying_Participants (26), Data_Security_for_Researchers (21), Training_Requirements (20), FAQ (20), Example_Expedited_Interview_Study (20). The full per-page list with the text of each tag is **Appendix C**.

Decisions that block more than one page: HSP refresher interval (Training_Requirements ×10, plus the four pages in §4 item 6); master code retention (§4 item 1, six pages); the chart review review path (§4 item 4, five pages); whether the Initial Review Submission Form asks for home institution (Application_Section_Tips, Preparing_a_Complete_Submission); the INSPIR exempt application redesign (Exempt_Research and all 13 exempt tip sheets carry "[CHECK IN INSPIR: redesign pending; confirm names]").

### 5d. Headings that don't match content

Collected during the page-by-page read in pass 2 (full addenda at the end of review-pass2.md). Items 13 to 27 in §4 were promoted from these addenda; the remaining within-batch conflicts are kept here.

**Batch 1**

*Headings vs content:*
- Exempt_Tip_4 · "What to attach and what your information sheet needs" · the body says "With no contact, there is no information sheet."
  - Start_Here · "Common first-time stipulations and how to avoid them" · the list names five stipulations; only one bullet ("Download a fresh copy each time") says how to avoid one.
  - Review_Path_Decision_Tool_v3 · no H1 in the extracted text; the page opens with "This tool needs JavaScript."

*Within-batch conflicts not already in §4:*
- Coded data without the key, not on the source study. Do_I_Need_IRB_Review quick guide: "Coded data, no HIPAA identifiers, you are not on the source study | No (submit if you want a letter) | NHSR". Review_Path_Decision_Tool /results/R_NHSR_CODED/why: "Coded data you can never link back to people, received under a written agreement that you will never get the key, is usually not human subjects research for your team. Submit an NHSR request so the IRB can confirm." One says no submission is needed, the other says submit.
  - When a separate protocol is required. Start_Here: "You must attach one for a clinical trial with a drug, biologic, device, or surgical intervention; a multi-site or NIH-funded clinical trial; or a study that must post results on ClinicalTrials.gov (HRPP Policy 7.2.2.20)." Review_Path_Decision_Tool /nonexemptAttach[0] and /results/R_FDA/attach[0]: "all medical or surgical clinical trials, multi-site clinical trials, and NIH-funded clinical trials." The tool omits the ClinicalTrials.gov results-posting trigger.
  - Who signs for a deceased patient's case report. Case_Reports: "Authorization from the personal representative: the executor or administrator of the estate". Review_Path_Decision_Tool /results/R_CASE_REPORT/steps[0]: "their legally authorized representative (for a patient who has died, the executor or administrator of the estate)". Different terms for the same person (personal representative is the HIPAA term; legally authorized representative is a consent term).
  - Reasons local categories 9 to 13 are unavailable. Exempt_Research lists five, including "The sponsor or funder requires the Common Rule." Exempt_Tip_Sheets_Index: "Categories 9 to 13 are also not available for FDA-regulated studies, studies where another institution relies on our IRB, or studies using data from a substance use disorder clinic." The index omits the sponsor-requires-Common-Rule exclusion.

*Other mechanical:*
- Placeholder brackets a reader would see: Case_Reports (Journal consent forms) "[UNVERIFIED: confirm with the Privacy Office …]"; Exempt_Research (mapping table, category 4 row) "[NOT IN SEPT 2026 PRINTOUTS; CONFIRM: …]", (What to submit) "[CHECK IN INSPIR: the exempt application is being redesigned …]", (Collaborators at other institutions) "[UNVERIFIED]"; Exempt_Tip_1 "[UNVERIFIED: no local FERPA guidance …]" and "[CHECK IN INSPIR: redesign pending; confirm names]"; Exempt_Tip_2-1, 2-2, 3-1, 3-2 each carry "[CHECK IN INSPIR: redesign pending; confirm names]" and "[CHECK IN INSPIR: confirm when this question appears]"; Exempt_Tip_4 "[CHECK IN INSPIR: category 4 shows sub-options …]" and "[CHECK IN INSPIR: redesign pending; confirm names]". IRB_Home shows "[Icon: person with a compass]" and "[Icon: checklist]" in the text extract; confirm these are alt text, not visible copy.
  - Duplicated content: the five-bullet "Why submissions come back" list on IRB_Home is repeated word for word as "Common first-time stipulations" on Start_Here (Start_Here adds one sentence to bullet 3).
  - Repeated sentence: Start_Here uses "The edges can be blurry" twice within the same section (paragraph and collapsible).
  - Stray spaces before punctuation from link extraction: IRB_Home "CRC IRB ." and "IRB Alignment ."; Do_I_Need_IRB_Review "the other IRB has agreed , or"; Exempt_Research and tip sheets "(also in Spanish );".
  - Exempt_Research mapping table: the "7 and 8" row has three cells in a four-column table.
  - Exempt_Research related links label "Chart Review Research" where every other page calls the page "Chart Review and Secondary Use of Existing Data".
  - Review_Path_Decision_Tool: questions 4, 14, 15, 17, 20, 23 and 24 show only one option label (or none) in the extracted logic text; confirm the No/other options have label text.
  - Review_Path_Decision_Tool: /results/R_FULL_BOARD/steps[2] and /results/R_NONEXEMPT/steps[2] are identical 58-word strings; the six /methodRules/*[0]/why prisoner strings are identical too (fine if generated from one source, otherwise consolidate).

**Batch 2**

*Headings vs content:*
Exempt_Tip_13 · "Deception, capacity, and retention" · the body covers deception and retention only; capacity (adults who can consent for themselves) is never discussed under that heading. Expedited_Tip_1 · "Does your study fit?" table cell "Board device determination." · a label, not a condition or outcome a reader can act on. Otherwise none found.

*Within-batch conflicts not already in §4:*
Expedited_Tip_6 checklist says the exemption for recorded adult interviews is "Exempt category 2." while its own Examples row says "Likely exempt category 2.2" and Related links point to "Exempt Category 2.2" (same page, two labels for the same destination). Expedited_Tip_Sheets_Index describes local categories 10 to 12 as for studies "with no external funding and no federal oversight," while Expedited_Tip_2, _3 and _4 define them as "no external funding of any kind ... not FDA-regulated" and Expedited_and_Full_Board_Review adds "no sponsor requirement to follow the Common Rule"; three different phrasings of one eligibility test. Exempt_Tip_13 says unfunded adult MRI and blood draw studies were reviewed "as exempt category 13 or as expedited, usually expedited" while Expedited_Tip_2 and _4 say "usually been reviewed as expedited, sometimes as exempt category 13"; same meaning, reversed emphasis. No numeric, deadline, or contact conflicts found.

*Other mechanical:*
- Visible placeholder brackets in running text on every exempt sheet (5, 6, 9, 10, 11, 12, 13): "[CHECK IN INSPIR: redesign pending; confirm names]" and "[CHECK IN INSPIR: confirm when this question appears]".
  - Exempt_Tip_13 Examples table: "[UNVERIFIED: contrast and medical clearance details not confirmed]" visible in a table cell.
  - Expedited_and_Full_Board_Review: "[CHECK: meeting time and Zoom format]" and "[CRRO link to be confirmed]" visible in running text.
  - Expedited_Tip_5: "[CHECK IN INSPIR: confirm section names]" visible.
  - Exempt_Tip_9, "Records only, or more?": stray two-word fragment "Prisoners only incidentally." in the middle of a paragraph.
  - Expedited_Tip_5, "Application sections that matter": fragment "If you use the full application." stands as its own sentence.
  - Exempt_Tip_12, "It does not fit when": two bullets both say prisoners are excluded ("The children are prisoners..." and "Prisoners are included...").
  - Exempt_Tip_11, "It does not fit when": two near-duplicate bullets ("The institution already made the change and you only analyze records (chart review, usually 9)." and "The only research activity is a chart review.").
  - Expedited_Tip_1 states the nonsignificant-risk convened-meeting rule (HRPP 12.2.4.1) three times (checklist, What to attach, Devices row).
  - Duplicated boilerplate across pages: the 39 to 57 word "built from the Exempt Information Sheet Template ... and a study contact" sentence appears on Exempt_Tip_5, _6, _11, _13 (and a variant on _12); the 42-word "Local categories 10 to 12 ... not FDA-regulated." paragraph appears verbatim on Expedited_Tip_2, _3, _4; the "Unfunded adult studies" paragraph appears near-verbatim on Expedited_Tip_2 and _4 and Exempt_Tip_13.
  - Expedited_and_Full_Board_Review intro: 3 in 4 full board studies at 87 days versus 3 in 4 expedited at 101 days reads as "full board is faster"; the caveat (four reviews) follows but a skimmer will miss it.
  - Expedited_Tip_1 Examples row "Testing whether a new app diagnoses depression" points to "the IND/IDE decision guide" while Related links name it "Does My Study Need an IND or IDE?"; same target, different label.

**Batch 3**

*Headings vs content:*
- Application_Section_Tips · "## Tips by application question" > "PI home institution: is this a BMC or a BU study?" · the section itself says "The September 2026 Study Application has no question for it."
  - Expedited_Tip_8 and Expedited_Tip_9 · "> Application sections that matter" · the rows name submission forms (Continuing Review Submission Form; Progress Report form) and "Study documents", not application sections.
  - Expedited_Tip_8 and Expedited_Tip_9 · "> Minimal risk reminder" · the block (including the HRPP 10.2.2.4.1.1 privacy sentence) is copied from the new-study tip sheets; these two categories are continuing-review only and the "What to attach" text does not mention it.

*Within-batch conflicts not already in §4:*
- Continuing review form name: Expedited_Tip_8 says "Leaving the study status out of date in the Continuing Review Submission Form." Expedited_Tip_9 says "Studies approved with an expiration date still need a Progress Report before it lapses" and "The Progress Report and current study documents, as for category 8."
  - Goldman School rule: Preparing_a_Complete_Submission says a trainee PI "needs a Supervising PI who is BMC or BU faculty or staff (at the Goldman School of Dental Medicine, faculty only)." Study_Team_Members says "At the Goldman School of Dental Medicine, only faculty may be PI." Student_Trainee_Research describes Goldman routing but neither restriction.
  - Whether to submit an NHSR request for de-identified data: Chart_Review says of an honest-broker data set with no identifiers "The IRB makes this determination, so submit a Not Human Subjects Research request." INSPIR_Task_Choose_Review_Path says "You must submit if your data include any HIPAA identifier ... otherwise submit only if you want a determination letter."
  - Study Contact's required second role: Study_Team_Members says the person "must also be listed as the PI, a Co-Investigator or Research Support Staff member, the Supervising PI, or an Administrative Assistant." INSPIR_Task_Access_and_New_Study says "a Study Contact must also have a role such as Additional Investigator or Research Staff" (Administrative Assistant not mentioned).

*Other mechanical:*
- Visible drafting brackets in reader-facing text (approximate counts): Chart_Review 9 (five "[NOT IN SEPT 2026 PRINTOUTS; CONFIRM...]", "[PLANNED TASK PAGE]", "[UNVERIFIED...]", "[PENDING DECISION...]", footer "[PENDING]"); Preparing_a_Complete_Submission 6; Application_Section_Tips 6; Eligibility_and_Study_Design 2; Ancillary_Reviews_Sign_Offs 3 (incl. footer "[PENDING]"); Study_Team_Members 5 (the "Visiting scholars and observers" table cell is nothing but a placeholder); Training_Requirements 10 (eight "[PENDING DECISION: HSP refresher]" plus two "[UNVERIFIED]"); Student_Trainee_Research 7 (incl. "[replace with article URL on the new CR Times site]" in Related links); INSPIR_Task_Access_and_New_Study 14 (seven "[new site URL]" tags, the final Related links line is entirely bracketed, five "[UNVERIFIED]", two "[CHECK IN INSPIR]"); INSPIR_Task_Choose_Review_Path 6 (three "[new site URL]", three "[CHECK IN INSPIR]"); Responding_to_Stipulations 7; Timelines_and_JIT 6 (four "[CONFIRM...]", two "[UNVERIFIED]"); Expedited_Tip_9 1 (inside the table).
  - Stray "confirm" token at the end of every numbered step in INSPIR_Task_Access_and_New_Study and in Responding_to_Stipulations (also after "See How to check the status of a submission (PDF) .").
  - "Alt text: ..." paragraphs render as running text in INSPIR_Task_Access_and_New_Study and Responding_to_Stipulations; check they are attached to images, not body copy.
  - Fragments: Expedited_Tip_7 "What to attach" first sentence has no verb; Study_Team_Members Charles River table cell and Training_Requirements Charles River bullet both start "For minimal-risk studies ..., added ..." with no subject; Application_Section_Tips "Where each topic appears" table row "PI home institution" has two cells where every other row has three.
  - Duplicated text: the Charles River Campus global-reliance paragraph appears nearly verbatim on Preparing_a_Complete_Submission, Study_Team_Members, Training_Requirements, and Student_Trainee_Research; the "Minimal risk reminder" block is identical on Tips 7, 8, 9; INSPIR_Task_Choose_Review_Path "If you change your answer" says the same thing in two consecutive paragraphs; Timelines_and_JIT restates "no deadlines / reviewed in order received" in the intro, the callout, "Asking for priority review", and the amendments FAQ, and the three-week/Friday-agenda-lock rule twice; Responding_to_Stipulations repeats the 30-day appeal rule in the outcomes table and in "If you disagree".
  - Link targets: the same Charles River reliance topic points to three differently named pages ("Collaborating with BU Charles River Campus" on Study_Team_Members, "Working with Other Institutions" on Student_Trainee_Research, "Student and Trainee Research" on Training_Requirements). Responding_to_Stipulations table row "5. Eligibility criteria" links to Preparing a Complete Submission although this batch has a dedicated Eligibility page.
  - INSPIR_Task_Access_and_New_Study and INSPIR_Task_Choose_Review_Path lack the "Last reviewed / Page owner" footer every other page carries.

**Batch 4**

*Headings vs content:*
- Example_NHSR_and_QI_Requests · intro says Example 3 is a "QI" project that "turns out to be research and needs a full application" · the Example 3 body says it "may fit exempt category 13" and lists exempt as the first option, so "full application" is wrong or overstated.
  - Example_Amendment_and_Stipulation_Response · "What does not need an amendment" · the first sentence under it says "every change needs IRB approval before you make it"; the list is of changes that use a different form, not changes that need nothing.

*Within-batch conflicts not already in §4:*
- Short form for expected languages: Consent_Templates says "If you expect only a few, the IRB may approve the short form instead; explain why in your application." · Limited_English_Proficiency says "The short form is only for people whose language you did not expect to encounter." and lists "Requesting the short form for Spanish or Haitian Creole, or another language you expect to enroll" as a stipulation.
  - Template version versus payment update: Consent_Templates ("The Payment language in the non-exempt consent templates was updated on September 16, 2026") and Consent_Language_Bank (same date) · Templates_Forms_Library lists the Adult Consent Form Template as "1.14, May 8, 2026" and the Language Bank says it matches "Version 1.14, 5/8/2026". A September 2026 wording change should carry a newer version or date.
  - Consent for chart reviews: Obtaining_Consent quick reference "Chart review; contact not practicable | No consent | Waiver of consent, plus a HIPAA waiver for PHI" · Example_Exempt_Chart_Review requests only a HIPAA waiver ("Consent | None; no one is contacted, so there is no information sheet") because the study is exempt. The Obtaining Consent row needs "non-exempt" or a note that exempt chart reviews need no consent waiver.
  - Where interpreters are mandatory: Limited_English_Proficiency says BMC Interpreter Services is required "during a BMC medical encounter or in BMC clinical space" · Example_Expedited_Interview_Study says "in a private room in the EPCC, which is BMC space, so the consent discussion is conducted through BMC Interpreter Services" and Example_Amendment says ECHC "is outside BMC space". "BMC space" and "BMC clinical space" are not the same test; a BMC research office falls between them.
  - Template color code: Consent_Templates says every template uses red, blue, and black text · Consent_Language_Bank entry 29 says "Delete the purple header from the template once you pick the version."
  - Internal recruitment materials: Example_Exempt_Survey says "an internal list does not need" communications review · Example_Expedited_Interview_Study says "for a flyer used only inside BMC spaces not open to the public, check with Communications/Marketing first". Different materials, but a reader cannot tell when internal-only use is exempt from review.

*Other mechanical:*
- Visible editorial brackets in running text: Before_and_After ("[PENDING DECISION]", "[CHECK IN INSPIR: whether revisions must be uploaded as a new version of the same document]"); Example_NHSR_and_QI ("[CHECK IN INSPIR: ...]" x2, "[UNVERIFIED: ...]" x2); Example_Exempt_Survey ("[CONFIRM: preferred answer for employee-only studies]", "[CHECK IN INSPIR: whether the rest of the HIPAA questions still display after a No]"); Example_Exempt_Chart_Review (a full "[CHECK IN INSPIR: the chart review application is being revised ...]" paragraph on the first screen, "[PENDING DECISION ...]", "[UNVERIFIED ...]", footer "HIPAA sample text reviewed by the BMC Privacy Office: [PENDING]"); Example_Expedited_Interview_Study ("[CHECK: confirm with an analyst ...]", "[UNVERIFIED ...]" x3, "[PENDING DECISION ...]", "[CHECK IN INSPIR: the printouts do not show the Initial Review Submission Form]", footer "Example reviewed by an IRB analyst: [PENDING]"); Example_Pediatric_Study ("[CHECK IN INSPIR ...]" x2, "[UNVERIFIED ...]" x2); Example_Amendment ("[CHECK IN INSPIR: Amendment Description label]", "[CHECK IN INSPIR: how a study team detaches a duplicate document ...]"); Consent_Templates ("[CONFIRM with Director]" in the template table); Consent_Language_Bank (entry 13 opens with "[UNVERIFIED: ... Do not publish this entry until confirmed ...]", "[confirm]" in entry 27, "[confirm local wording with the template owner]" in entry 32); Templates_Forms_Library ("[CHECK: still current?]" x5, "[PENDING: the legally authorized representative wording in 8 languages awaits Interpreter Services review]", "[CHECK WITH JAMIE: offer and wording]"); Obtaining_Consent ("[CHECK IN INSPIR: confirm the "Approved Consent" study-workspace tab label on screen]", "[CHECK: whether BMC requires a consent note in Epic ...]", "[UNVERIFIED: whether the COVID-era remote witness-signature process is still accepted]"); Limited_English_Proficiency ("[UNVERIFIED ...]" x4).
  - Example_Pediatric_Study · Recruitment procedures · the sentence "Flyers posted publicly or off campus need review by a communications office first; the office depends on the PI's home institution." is website guidance sitting inside the sample application answer.
  - Before_and_After · Quick reference table · the "Consent template language" and "Clean documents" rows have three cells where the table has four columns (the Exempt application column is missing).
  - Consent_Language_Bank · the sentence "Non-exempt study, no signature (waiver of documentation), but uses PHI: request an alteration of HIPAA authorization ..." appears verbatim twice (section intro and entry 28 "Do not use when").
  - Limited_English_Proficiency · "Excluding people who cannot read is a separate question with its own rules; see Informed Consent Overview (limited- and non-readers)." · the limited- and non-reader rules are on Obtaining Informed Consent ("Participants who need extra steps"); the Overview only links there. Wrong page referenced.
  - Example_Amendment_and_Stipulation_Response and Hub_Consent_HIPAA_Recruitment have no "Last reviewed / Page owner" footer line; every other page in the batch has one.

**Batch 5**

*Headings vs content:*
- Continuing_Review_and_Closing · "What reviewers look for and possible outcomes" · the third paragraph is the short form three-use translation rule, not a reviewer criterion or outcome.
  - INSPIR_Task_Change_Approved_Study and INSPIR_Task_Checkins_Reports_Closing · "## Before you start" is immediately followed by "### Before you start" with no text between (empty duplicate heading).
  - Hub_Guidance · subtitle "Topic guidance for specific kinds of studies" · the page also covers participant populations, data and technology, and collaboration; the next line already says so.
  - Hub_Guidance · Related links "Remote and telehealth research" · the card on the same page is titled "Remote and Decentralized Research".

*Within-batch conflicts not already in §4:*
- PI sign-off on the Final/Closure Report. Continuing_Review_and_Closing (five-step box covering the Final/Closure Report Form): "Choose Signoff and Submit if you are the PI, or Notify PI for Signoff. The PI must approve and sign off before the IRB receives it." vs INSPIR_Task_Checkins_Reports_Closing: "A Final/Closure Report, a Recruitment Materials Submission Form, and a Contact Information Change Request Form do not need the PI's signature under IRB policy, so any team member with edit access can submit them".
  - What to submit for recruitment materials finalized after approval. Recruitment_and_Screening: "Materials not ready yet? You may submit them after approval. Use the Recruitment Materials Submission Form when the only change is new promotional materials" vs Amendments: "If materials were still in draft at initial review, submit the final versions as an amendment."
  - Contact Information Change Request sign-off. INSPIR_Task_Change_Approved_Study: "Contact Information Change Requests and promotional-recruitment-only submissions do not need the PI's signature." vs INSPIR_Task_Checkins_Reports_Closing (Change contact information steps): "Select Save Form , then on the Form has been Completed page select Signoff and Submit or Notify PI for Signoff ." (the same page's table says "No (PI should review)").

*Other mechanical:*
- Visible placeholder brackets in running text: Short_Form_Consent_Process ([CHECK IN INSPIR…], two [UNVERIFIED…], [UPLOAD PENDING…]); HIPAA_in_Research (three [UNVERIFIED…], "[confirm the local mechanism with the Privacy Office]", "[PENDING]"); HIPAA_Waiver_Sample_Answers ([UNVERIFIED…], "[PENDING]"); Certificates_of_Confidentiality ("[UNVERIFIED: who signs for BU]"); Recruitment_and_Screening (two [UNVERIFIED…], two [CHECK IN INSPIR…], "[PENDING]"); Paying_Participants (six [PENDING DECISION…], seven [UNVERIFIED…], "[PENDING]"); Continuing_Review_and_Closing (three [CHECK IN INSPIR…], one of them inside the heading "…in five steps [CHECK IN INSPIR]", three [UNVERIFIED…]); Reporting_and_Monitoring ("[UNVERIFIED: which form]", "[Responsibilities of the PI, new site URL]"); Amendments ("[Continuing Review page, new site URL] · [Monitoring, Reporting and Noncompliance page, new site URL] · [Cede Review page, new site URL]"); the three INSPIR_Task pages ("[new site URL]" 8, 10 and 7 times; [CHECK IN INSPIR…] 6, 8 and 5 times; INSPIR_Task_Records also "[CHECK ON CITI…]" and four [UNVERIFIED…]).
  - Duplicated paragraphs across pages: the Boston HealthNet text ("Most health centers are not engaged in research; if one is, it needs a reliance agreement with the BMC/BUMC IRB (contact medirb@bu.edu )") appears in both Recruitment_and_Screening and Amendments; the "Missed status check-ins" text (minor vs major deviation) appears verbatim in Continuing_Review_and_Closing and in INSPIR_Task_Checkins "Avoid common problems"; "When the first question is answered No by mistake, the rest of the section is left blank and the IRB has to send the application back." appears verbatim in both HIPAA pages.
  - Continuing_Review_and_Closing: "(RENI)" is expanded twice in the same section; "If research happened after expiration, also submit a Reportable Events and New Information (RENI) form." repeats the "Restarting a lapsed study" bullet two paragraphs above.
  - Certificates_of_Confidentiality: same-page inconsistency on who applies for a discretionary Certificate (table "which you request through BU"; text "you, the researcher, start the request with BU; the IRB office does not apply for you"; INSPIR option "the PI is responsible for applying to NIH").
  - Paying_Participants: "The Adult Consent Form Template and Parent Permission Form Template include the Payment section and the $2,000 tax sentence. Go to the Templates and Forms Library" ends without a period; the Where payment information goes table says the INSPIR question "says 'reimbursed'" for payment, which readers will read as an error without more context.
  - Recruitment_and_Screening: "Its (?) help icon explains how to check." renders as a stray "(?)".
  - Reporting_and_Monitoring: "Here, the HRPP Director reports within 21 days" uses "Here" with no referent; "(revised 9/16/26)" date format differs from "September 16, 2026" used on Recruitment_and_Screening and Paying_Participants.
  - INSPIR_Task_Records_and_Training: internal note visible in a Sources line ("checked against the live policy 2026-09-25"). INSPIR_Task_Change_Approved_Study: "Alt text:" paragraphs appear in the body text.

**Batch 6**

*Headings vs content:*
- Special_Populations · H1 "Pregnancy, Adults Lacking Capacity, and Prisoners" · the page also covers students, trainees, employees, disadvantaged people, and people with limited English proficiency, and every other page in the batch links to it as "Special Populations".
  - ClinicalTrials_gov · "Getting a PRS account and help" · the last paragraph is the CRRO consultation requirement (HRPP 6.2.1.2), which has nothing to do with PRS accounts.
  - Mandated_Reporting_and_Safety_Plans · "Mandated reporting in Massachusetts" · ends with advice on what to tell parents about adolescents' pregnancy test results, which is not mandated reporting.
  - Deception_Incomplete_Disclosure · no "## Guidance" heading; the collapsibles begin directly under the intro, unlike every sibling page.

*Within-batch conflicts not already in §4:*
- Master code interim rule. Data_Security: "Until then, give both a destruction milestone for the master code and your plan to keep records 7 years." Data_Retention: "Until this is decided, state in your application which approach you will take and why." One tells applicants to plan destruction; the other lets them choose either reading.
  - HRPP 9.7.2 cited for two different rules. Data_Security: "A Certificate of Confidentiality "provides protection against most compelled disclosure…" (HRPP 9.7.2)." Mandated_Reporting (and the quote on Remote_Decentralized_Research): "Is run by mandated reporters in places where abuse could be seen… (HRPP 9.7.2)". One citation is likely wrong.
  - What happens after the IRB rejects an NSR claim. Drugs_and_Devices: "cannot start until the FDA approves an IDE or decides the study is NSR." Drug_Device_Decision_Guide: "the study cannot start until the FDA approves an IDE ( 21 CFR 812.66 )." The guide omits the FDA-decides-NSR path.
  - Separate protocol rule (both cite HRPP 7.2.2.20). Drugs_and_Devices: "A separate protocol is required for drug, biologic, device, and surgical trials, any multi-site or NIH-funded trial, and any study that must post results on ClinicalTrials.gov". ClinicalTrials_gov: "Initial submissions of medical or surgical clinical trials, multi-site clinical trials, NIH-funded clinical trials, and any study required to post results". "Medical" and "drug, biologic, device" are not the same scope.
  - CRRO consultation. Drugs_and_Devices: "PI-initiated trials need a CRRO consultation before submission (HRPP 6.2.1.2)." ClinicalTrials_gov: "PI-initiated clinical trials also consult the Clinical Research Resources Office (CRRO) before submission, or obtain a waiver of this requirement from the IRB Director (HRPP 6.2.1.2)". The Drugs page omits the waiver.

*Other mechanical:*
- Visible placeholder brackets in running text: Drugs_and_Devices 2, Radiation 5 (incl. footer "[PENDING]"), Expanded_Access 8, Humanitarian_Use_Devices 3, ClinicalTrials_gov 4 (incl. "[FORM STILL ASKS ABOUT NIH-FUNDED BESH; SEE REVIEWER NOTES]" mid-paragraph), Genetics 3, Surveys 4, Remote 4, Deception 1 ("[CONFIRM]"), Children 3, Special_Populations 7, Mandated_Reporting 1, Data_Security 12, Data_Retention 6. Drug_Device_Decision_Guide has none.
  - Data_Security "Texting, email, and calls with participants" and Data_Retention "The master code and the 7-year rule" each open with an instruction to replace the whole section before publication.
  - Radiation: "(21 CFR 361.1)" is cited twice in the same sentence.
  - Radiation "MRI" paragraph and Special_Populations "Research-only MRI" paragraph are near-verbatim duplicates (HRPP 9.4.8); keep in sync or cross-link.
  - Drug_Device_Decision_Guide repeats the Drugs_and_Devices 69-word INSPIR navigation sentence and the "IRB does not make FDA determinations" block almost verbatim.
  - Expanded_Access: "One emergency use of a product at BMC/BUMC without prior review." is a sentence fragment used as a run-in heading.
  - Mandated_Reporting: the HRPP 9.9 quote is rendered as one sentence with "; and" joins instead of the policy's list.
  - Surveys: "Go to the Templates and Forms Library" has no end punctuation; the focus-group quote uses a curly apostrophe ("can’t") while the rest of the page uses straight quotes.
  - Link-title inconsistencies across the batch: Special_Populations "Paying Participants" vs "Paying Research Participants" elsewhere; Special_Populations "e-Consent and Remote Consent" vs Remote page's "Remote and electronic consent"; Children related links "Pregnant Persons, Fetuses, and Neonates" and "Adults with Diminished Decision-Making Capacity" do not match the Special_Populations page title; Data_Retention "See also Closing a study" vs "Continuing Review and Closing a Study".
  - Children intro: "(see below)" with no section named.

**Batch 7**

*Headings vs content:*
Ceding Review · "Steps and timeline" · the list is unnumbered bullets, yet the next paragraph refers to "step 5", and the only timing figure is the 10-day pickup target. FAQ · "Can a participant be in my study and another study at the same time, and can I recruit at newly added BMC sites?" · two unrelated questions under one heading; a reader scanning for site additions will not find it. Glossary · "Federalwide Assurance (FWA)" entry links to Contact the IRB and Get Help, but that page sends readers to Policies, Regulations, and Accreditation for the FWA numbers.

*Within-batch conflicts not already in §4:*
FAQ ("Do I need an amendment…"): "Adding or removing study staff, on any study, goes through an Internal Study Personnel Changes form before they start." vs Working with Other Institutions: "Adding any external investigator or site after approval requires an amendment (Change Request and Amendments form), even if their institution already has a reliance agreement with us." The FAQ's "on any study" does not carve out external investigators. Working with Other Institutions lists "Creating your INSPIR cede application (PDF) [2019 guide; confirm it matches current INSPIR]" as a resource, while Ceding Review says "the 2019 "Creating Your INSPIR Cede Application" PDF is out of date; replace with a task page." Community-Engaged Research sends readers to "The Boston HealthNet Research Subcommittee"; Working with Other Institutions and FAQ send them to "the health center research liaison" / "the Boston HealthNet research liaison" (different named contacts, same purpose). Glossary "Short form" adds "a grace period applies this first year" to the three-use rule; FAQ states the rule without it.

*Other mechanical:*
- Visible reviewer brackets in running text: Data Sharing (3), AI in Research (10, including one in the first paragraph and "[PENDING]" in the footer), Social Media (footer "[PENDING]"), Working with Other Institutions (3), VA Research (1), Ceding Review (2), Community-Engaged Research (2), International Research (6), Conflict of Interest (3 plus footer), Contact and About (7), Staff Directory (3, inside the tables), Ask the IRB (5), FAQ (10).
  - Broken sentences built around a placeholder: FAQ, "To stop contact for all BMC research, [CONFIRM: whether BMC keeps a research contact opt-out list and how patients use it] ." and Ask the IRB table cell "A written answer by the [PENDING DECISION] target". Ask the IRB also names a staff member in a placeholder: "[PLANNED: … destination pending Lauren]".
  - Data Sharing related link cites "sections 7.2.2.7.2.2, 7.2.2.16.4…" (garbled section number).
  - Community-Engaged Research: the HRPP 9.8.1 quotation has lost its list formatting ("; and The type…", "; and When children…").
  - Duplicated paragraphs: the board-schedule text ("Two boards each meet every three weeks on Thursdays… round or two of pre-review… agenda has space…") appears twice in the FAQ, again on Contact and About, and in the Glossary "Convened board" entry. Contact and About says the office is remote twice in the first screen and repeats the Teams/Zoom meeting detail in the intro box and under Meet with the IRB. International Research repeats "See Working with Other Institutions" twice in one paragraph. Staff Directory and Contact and About both carry "office administration and review coordination [CHECK wording]".
  - Glossary acronym table: the first 13 rows (AAHRPP through VA, R&D) are out of alphabetical order before the list restarts at CRC. "Training (CITI)" entry prints the link text twice.
  - Email address differs in case: "DUA.MTARequest@bmc.org" (Data Sharing) vs "DUA.MTArequest@bmc.org" (Working with Other Institutions).
  - VA Research: "If more than one row fits, both IRBs review." sits above the table caption "Which IRB reviews your study" as an orphaned lead-in.
  - Social Media: the "Required" and "Best practice" labels run straight into sentence text in the extract ("Required Approval before use."); confirm they render as badges.

**Batch 8**

*Headings vs content:*
- IRB_Committees · "Conflicts of interest for board members" · ends with an unrelated paragraph ("Current board members. Reviewer templates and training materials are on For Board Reviewers.") that belongs under Join the IRB or a members section.
  - IRB_Review_Times · "Where the time goes" · the section has no data in the text, only a description of a chart ("Each bar is a separate median… Each bar is labeled with its phase and value"); the same happens under "Quarterly trend" ("Each line is labeled at its end and uses a different marker and line style"). If the graphics are missing or the page is read aloud, these are empty sections.
  - Policies_and_Regulations · "Recent policy changes (December 2025 to September 2026)" · the table caption says "HRPP policy changes in the last 12 months", but the range covers 10 months and omits the Sept 23, 2025 and Oct 2025 items that Announcements lists.
  - Policies_and_Regulations · "Standard operating procedures" · first sentence says internal instructions are not posted, second says OHRA publishes SOPs; the heading promises SOPs the first sentence denies.
  - Announcements · "Does it need IRB review?" · contains the NHSR personnel bullet, which is about who to list, not whether review is needed.

*Within-batch conflicts not already in §4:*
- Where older policy changes live: Announcements "Older policy changes are listed on Policies, Regulations, and Accreditation ." vs Policies_and_Regulations, which lists only Dec 2025 to Sept 2026 and sends readers to "Section 15" of the HRPP for everything else.
  - Where changes are announced: Announcements "We announce changes in three places: on this page, in the CR Times newsletter , and, for changes that affect open studies, by email to study teams." vs Policies_and_Regulations "We announce changes in the CR Times newsletter , on the OHRA website, in INSPIR and, when needed, by email." (INSPIR and the OHRA website appear on one page, this page on the other).
  - Dec 22, 2025 change scope: Announcements "Charles River Campus faculty, staff and students are added to a BMC/BUMC study through a regular personnel change (HRPP 2.5.2.1)." vs Policies_and_Regulations "Charles River Campus students (in practice also faculty and staff; see Working with Other Institutions) join BMC/BUMC studies through a regular personnel change" (Policies says the policy text covers students only; Announcements presents faculty and staff as policy).
  - Agenda lock exceptions: IRB_Committees "With rare exceptions, the agenda is locked the Friday before the Thursday meeting" and For_Board_Members "The agenda is locked the Friday before the Thursday meeting, except rarely" vs IRB_Review_Times "the agenda is locked the Friday before" (no exception). Minor.
  - Sept 16, 2026 routing citation: Announcements "(HRPP 7.3.2, 7.3.3)" vs Policies_and_Regulations "7.3.3" only. Minor.
  - Contact page for Spanish readers: For_Research_Participants_ES promises "le responderemos en español"; For_Research_Participants makes no such promise.

*Other mechanical:*
- Visible placeholder brackets in running text: Announcements ([PENDING: launch date] x2, [UNVERIFIED: date], [CHECK IN INSPIR: where these questions appear], [CHECK: whether BMC South follows the same date], [PLANNED], [PENDING: go-live date], [PENDING: Advisory Committee approval and dates], [PENDING: date], [PENDING: Lauren: RSS/email options]); IRB_Committees ([CHECK: confirm this is the office's preference], [CHECK: meeting time and Zoom format], [CHECK: current hours and meeting frequency], [CHECK: current recruiting priorities], [PENDING DECISION: keep public, or move to a members-only location]); For_Board_Members ([PLANNED: internal link behind login]); For_Research_Participants ([CHECK: what the IRB approval stamp…], [UNVERIFIED: confirm wording with the BMC Clinical Trial Office], [UNVERIFIED: OHRA community page uses ccr@bmc.org…]); For_Research_Participants_ES (the same three brackets, in English, on a Spanish page); Policies_and_Regulations ([CHECK against OHRP] x2, [CHECK: letters need reissue], [CHECK IN INSPIR: wording of the questions…], a bare [CHECK] after the SOP sentence).
  - For_Board_Members · intro opens with a verbless fragment ("How BMC/BUMC IRB board members review research, and what they check before they vote.") and the next sentence's "it" has no antecedent.
  - IRB_Committees · refers to "For Board Reviewers" in the Conflicts section but to "For IRB Board Members (and What Reviewers Look For)" in Related pages; same page, two names.
  - For_Research_Participants · Contact the IRB section ends with a bare "medirb@bu.edu" after the 911 sentence (orphaned fragment).
  - For_Research_Participants_ES · "Comuníquese con el IRB" is an H3 while every other section is H2; the section is a bare fragment ("(617) 358-5372 (puede dejar un mensaje de voz a cualquier hora) medirb@bu.edu"); the page has no "English" link back to the English version although the English page links to it.
  - IRB_Review_Times · "See what you can do to speed things up" appears in two consecutive intro paragraphs (duplicated link); the "Institutional routing" bullet describes ancillary routing as happening "at the same time" as IRB review, then says the Q1 2026 figures predate "the change to concurrent routing", so the description does not match the numbers it explains; "Q1" means a calendar quarter in the review-time tables and a survey question in the satisfaction table on the same page; the satisfaction section ends with an unsigned signature line ("IRB Director, BMC/BUMC IRB") after "Thanks to everyone who took the time to respond."
  - Page-name drift across the batch: "Paying Research Participants" (Announcements) vs "Paying Participants" (For_Board_Members, Policies_and_Regulations); "Choose your review path" (Announcements) vs "Choose your review path in INSPIR" (IRB_Review_Times); "Ancillary Reviews and Sign-Offs" (Announcements) vs "Ancillary Reviews and Sign-offs" (IRB_Review_Times).


---

## Appendix A. Terminology variants: every exact form found, with counts and locations

Counts are occurrences in public page text (nav menus excluded). "where" lists up to eight pages with per-page counts; page names drop the `_DRAFT_v1.html` suffix. Patterns are case-sensitive, so casing variants are separate rows. In the "Policy section label forms" table, numbers are normalized to N.

### IRB names
| variant | total | pages | where (top 8) |
|---|---|---|---|
| the IRB | 757 | 108 | FAQ (29), Review_Path_Decision_Tool_v3 (28), Continuing_Review_and_Closing (28), Limited_English_Proficiency (24), INSPIR_Task_Checkins_Reports_Closing (23), Short_Form_Consent_Process (20), Drugs_and_Devices (19), Research_Involving_Children (18) |
| the BMC/BUMC IRB | 127 | 59 | Working_with_Other_Institutions (12), Review_Path_Decision_Tool_v3 (11), Ceding_Review (6), International_Research (6), Study_Team_Members (5), HIPAA_in_Research (5), Amendments (5), Do_I_Need_IRB_Review (3) |
| BMC/BUMC IRB | 44 | 28 | Ceding_Review (4), Contact_and_About (4), Review_Path_Decision_Tool_v3 (3), HIPAA_in_Research (3), VA_Research (3), Working_with_Other_Institutions (2), Glossary_A_to_Z (2), Announcements (2) |
| and the IRB | 36 | 26 | Expanded_Access_Emergency_Use (3), Expedited_and_Full_Board_Review (2), Chart_Review (2), INSPIR_Task_Access_and_New_Study (2), Responding_to_Stipulations (2), HIPAA_in_Research (2), Humanitarian_Use_Devices (2), Working_with_Other_Institutions (2) |
| and IRB | 14 | 10 | Contact_and_About (3), Consent_Language_Bank (2), Social_Media_Internet_Research (2), Exempt_Research (1), Study_Team_Members (1), Templates_Forms_Library (1), Data_Sharing (1), International_Research (1) |
| the Charles River Campus IRB | 5 | 4 | Review_Path_Decision_Tool_v3 (2), Study_Team_Members (1), Student_Trainee_Research (1), Social_Media_Internet_Research (1) |
| Charles River Campus IRB | 4 | 4 | Study_Team_Members (1), Student_Trainee_Research (1), Contact_and_About (1), Policies_and_Regulations (1) |
| BU Charles River Campus IRB | 3 | 3 | Ceding_Review (1), Ask_the_IRB (1), Policies_and_Regulations (1) |
| the CRC IRB | 2 | 2 | IRB_Home (1), INSPIR_Task_Change_Approved_Study (1) |
| and the CRC IRB | 2 | 2 | Training_Requirements (1), Social_Media_Internet_Research (1) |
| CRC IRB | 2 | 2 | INSPIR_Task_Change_Approved_Study (1), Working_with_Other_Institutions (1) |
| and the BMC/BUMC IRB | 2 | 2 | Expanded_Access_Emergency_Use (1), Ceding_Review (1) |
| Boston Medical Center and Boston University Medical Campus IRB | 2 | 2 | VA_Research (1), Contact_and_About (1) |
| the BU Charles River Campus IRB | 2 | 2 | Contact_and_About (1), FAQ (1) |
| the Boston Medical Center and BU Medical Campus IRB | 1 | 1 | Example_Exempt_Chart_Review (1) |
| the Boston Medical Center and Boston University Medical Campus IRB | 1 | 1 | Consent_Language_Bank (1) |

### IRB names (full form)
| variant | total | pages | where (top 8) |
|---|---|---|---|
| BUMC Institutional Review Board | 1 | 1 | IRB_Home (1) |
| Boston Medical Center and Boston University Medical Campus Institutional Review Board | 1 | 1 | FAQ (1) |

### HRPP program name
| variant | total | pages | where (top 8) |
|---|---|---|---|
| HRPP | 134 | 39 | Expedited_and_Full_Board_Review (16), Exempt_Research (10), Study_Team_Members (10), Ceding_Review (9), Amendments (8), Working_with_Other_Institutions (8), Application_Section_Tips (7), Continuing_Review_and_Closing (7) |
| HRPP Policies and Procedures | 99 | 82 | INSPIR_Task_Records_and_Training (4), Do_I_Need_IRB_Review (2), Training_Requirements (2), Example_Pediatric_Study (2), Consent_Templates (2), Short_Form_Consent_Process (2), Certificates_of_Confidentiality (2), Radiation_in_Research (2) |
| HRPP policy | 68 | 29 | Glossary_A_to_Z (14), Paying_Participants (5), Surveys_Interviews_Focus_Groups (5), Data_Security_for_Researchers (5), Data_Retention (5), Obtaining_Consent (4), Community_Engaged_Research (4), Preparing_a_Complete_Submission (2) |
| HRPP Policies | 10 | 8 | VA_Research (2), Contact_and_About (2), IRB_Home (1), Hub_Post_Approval (1), Hub_Guidance (1), Announcements (1), For_Board_Members (1), Policies_and_Regulations (1) |
| Human Research Protection Program | 9 | 5 | Policies_and_Regulations (3), Example_Expedited_Interview_Study (2), Consent_Language_Bank (2), Glossary_A_to_Z (1), Contact_and_About (1) |
| HRPP policies | 8 | 6 | Policies_and_Regulations (3), Consent_Templates (1), Reporting_and_Monitoring (1), ClinicalTrials_gov (1), International_Research (1), Glossary_A_to_Z (1) |
| Human Research Protection Programs | 2 | 2 | Glossary_A_to_Z (1), Policies_and_Regulations (1) |

### Policy section label forms (number→N)
| variant | total | pages | where (top 8) |
|---|---|---|---|
| HRPP N | 335 | 78 | Special_Populations (25), For_Board_Members (23), Announcements (21), Drugs_and_Devices (15), Student_Trainee_Research (12), Responding_to_Stipulations (12), Research_Involving_Children (11), Humanitarian_Use_Devices (10) |
| section N | 53 | 24 | Policies_and_Regulations (7), Paying_Participants (4), Surveys_Interviews_Focus_Groups (4), Community_Engaged_Research (4), Application_Section_Tips (3), Example_Pediatric_Study (3), ClinicalTrials_gov (3), Genetics_Biospecimens_Repositories (3) |
| HRPP Policy N | 34 | 7 | Expedited_and_Full_Board_Review (13), Exempt_Research (8), Amendments (8), INSPIR_Task_Change_Approved_Study (2), Start_Here_New_Researchers (1), Expedited_Tip_8 (1), Example_Amendment_and_Stipulation_Response (1) |
| HRPP section N | 32 | 8 | Study_Team_Members (9), Working_with_Other_Institutions (6), Ceding_Review (5), Application_Section_Tips (4), International_Research (4), Community_Engaged_Research (2), Clinical_Trials (1), VA_Research (1) |
| Section N | 26 | 19 | INSPIR_Task_Records_and_Training (3), Glossary_A_to_Z (3), Training_Requirements (2), Consent_Templates (2), Radiation_in_Research (2), Do_I_Need_IRB_Review (1), Exempt_Tip_5 (1), Exempt_Tip_6 (1) |
| HRPP N, N | 18 | 7 | Announcements (7), Reporting_and_Monitoring (3), INSPIR_Task_Checkins_Reports_Closing (3), For_Board_Members (2), Consent_Language_Bank (1), Special_Populations (1), IRB_Committees (1) |
| HRPP Section N | 16 | 8 | Do_I_Need_IRB_Review (5), Review_Path_Decision_Tool_v3 (3), Example_NHSR_and_QI_Requests (2), Glossary_A_to_Z (2), Quality_Improvement_or_Research (1), Special_Populations (1), Mandated_Reporting_and_Safety_Plans (1), Conflict_of_Interest (1) |
| Sections N | 11 | 11 | Exempt_Tip_1 (1), Exempt_Tip_2-1 (1), Exempt_Tip_2-2 (1), Exempt_Tip_3-1 (1), Exempt_Tip_3-2 (1), Exempt_Tip_4 (1), Expedited_Tip_1 (1), Expedited_Tip_5 (1) |
| HRPP N and N | 8 | 7 | For_Board_Members (2), Start_Here_New_Researchers (1), Example_Expedited_Interview_Study (1), Amendments (1), Research_Involving_Children (1), Data_Retention (1), Social_Media_Internet_Research (1) |
| HRPP N, N, N | 8 | 3 | Continuing_Review_and_Closing (5), INSPIR_Task_Checkins_Reports_Closing (2), Announcements (1) |
| Sections N, N | 7 | 7 | Exempt_Tip_9 (1), Exempt_Tip_11 (1), Exempt_Tip_12 (1), Exempt_Tip_13 (1), Expedited_Tip_2 (1), Expedited_Tip_3 (1), Expedited_Tip_4 (1) |
| HRPP policy N | 7 | 4 | Continuing_Review_and_Closing (3), Deception_Incomplete_Disclosure (2), Paying_Participants (1), Social_Media_Internet_Research (1) |
| sectionN | 6 | 1 | Review_Path_Decision_Tool_v3 (6) |
| HRPP N, N, N, N | 4 | 2 | Reporting_and_Monitoring (2), Announcements (2) |
| HRPP N to N | 4 | 3 | INSPIR_Task_Change_Approved_Study (2), Special_Populations (1), For_Board_Members (1) |
| HRPP Policies N and N | 3 | 2 | Expedited_and_Full_Board_Review (2), Exempt_Research (1) |
| Sections N and N | 3 | 3 | Exempt_Tip_10 (1), INSPIR_Task_Records_and_Training (1), Contact_and_About (1) |
| HRPP policy section N | 3 | 2 | Obtaining_Consent (2), Preparing_a_Complete_Submission (1) |
| Sections N, N, N | 2 | 2 | Exempt_Research (1), Mandated_Reporting_and_Safety_Plans (1) |
| HRPP N, N to N, N | 2 | 2 | Continuing_Review_and_Closing (1), Reporting_and_Monitoring (1) |
| policy N | 2 | 2 | Continuing_Review_and_Closing (1), Conflict_of_Interest (1) |
| HRPP Policies N | 2 | 1 | IRB_Committees (2) |
| Sections N, N, N, N, N, N | 1 | 1 | Do_I_Need_IRB_Review (1) |
| HRPP Policy N and N | 1 | 1 | Exempt_Research (1) |
| HRPP Policies N to N | 1 | 1 | Expedited_and_Full_Board_Review (1) |
| Sections N, N, N, N, N | 1 | 1 | Expedited_and_Full_Board_Review (1) |
| HRPP Policies N, N, N, N, N | 1 | 1 | Continuing_Review_and_Closing (1) |
| HRPP N, N, N, N, N, N | 1 | 1 | Continuing_Review_and_Closing (1) |
| HRPP policy N and N | 1 | 1 | Continuing_Review_and_Closing (1) |
| HRPP Policies N to N, N, N, N, N, N, N, N | 1 | 1 | Reporting_and_Monitoring (1) |
| HRPP Section N, N | 1 | 1 | Reporting_and_Monitoring (1) |
| policy N-N-N | 1 | 1 | INSPIR_Task_Records_and_Training (1) |
| HRPP N-N | 1 | 1 | Working_with_Other_Institutions (1) |
| HRPP N-N, N | 1 | 1 | Announcements (1) |
| Sections N, N and N | 1 | 1 | For_Board_Members (1) |

### INSPIR
| variant | total | pages | where (top 8) |
|---|---|---|---|
| INSPIR | 806 | 105 | INSPIR_Task_Access_and_New_Study (52), INSPIR_Task_Checkins_Reports_Closing (44), INSPIR_Task_Records_and_Training (35), INSPIR_Task_Change_Approved_Study (32), Continuing_Review_and_Closing (27), Responding_to_Stipulations (25), FAQ (23), Review_Path_Decision_Tool_v3 (20) |
| INSPIR II | 5 | 2 | INSPIR_Task_Records_and_Training (4), INSPIR_Task_Change_Approved_Study (1) |
| inspir | 3 | 3 | Start_Here_New_Researchers (1), INSPIR_Task_Access_and_New_Study (1), Glossary_A_to_Z (1) |

### Review types
| variant | total | pages | where (top 8) |
|---|---|---|---|
| minimal risk | 128 | 47 | Expedited_and_Full_Board_Review (11), Expedited_Tip_9 (11), Review_Path_Decision_Tool_v3 (9), Example_Expedited_Interview_Study (9), FAQ (6), Expedited_Tip_Sheets_Index (4), Expedited_Tip_1 (4), Expedited_Tip_7 (4) |
| expedited | 115 | 52 | Expedited_and_Full_Board_Review (16), Review_Path_Decision_Tool_v3 (11), Do_I_Need_IRB_Review (7), Responding_to_Stipulations (4), For_Board_Members (4), IRB_Review_Times (4), Exempt_Tip_2-2 (3), Exempt_Tip_9 (3) |
| Expedited | 100 | 42 | Do_I_Need_IRB_Review (6), Expedited_and_Full_Board_Review (6), Review_Path_Decision_Tool_v3 (5), Consent_Templates (5), Expedited_Tip_2 (4), Expedited_Tip_4 (4), IRB_Review_Times (4), Expedited_Tip_1 (3) |
| full board | 74 | 34 | Expedited_and_Full_Board_Review (9), Review_Path_Decision_Tool_v3 (7), Expedited_Tip_4 (5), Expedited_Tip_2 (4), IRB_Committees (4), Expedited_Tip_8 (3), Responding_to_Stipulations (3), INSPIR_Task_Checkins_Reports_Closing (3) |
| Minimal risk | 41 | 26 | Exempt_Tip_13 (3), Expedited_Tip_7 (3), Review_Path_Decision_Tool_v3 (2), Exempt_Research (2), Expedited_and_Full_Board_Review (2), Expedited_Tip_1 (2), Expedited_Tip_2 (2), Expedited_Tip_3 (2) |
| greater than minimal risk | 37 | 19 | Review_Path_Decision_Tool_v3 (5), Consent_Language_Bank (5), Expedited_and_Full_Board_Review (3), Application_Section_Tips (3), Do_I_Need_IRB_Review (2), Example_Pediatric_Study (2), Limited_English_Proficiency (2), Short_Form_Consent_Process (2) |
| expedited review | 35 | 21 | Exempt_Research (6), Expedited_and_Full_Board_Review (6), Amendments (3), Review_Path_Decision_Tool_v3 (2), Continuing_Review_and_Closing (2), Exempt_Tip_3-2 (1), Exempt_Tip_5 (1), Exempt_Tip_10 (1) |
| Full Board Review | 34 | 22 | IRB_Committees (3), Expedited_Tip_1 (2), Expedited_Tip_2 (2), Expedited_Tip_3 (2), Expedited_Tip_4 (2), Expedited_Tip_5 (2), Expedited_Tip_6 (2), Expedited_Tip_7 (2) |
| minimal-risk | 27 | 14 | Do_I_Need_IRB_Review (5), Working_with_Other_Institutions (3), Glossary_A_to_Z (3), Student_Trainee_Research (2), Amendments (2), INSPIR_Task_Change_Approved_Study (2), Ceding_Review (2), Announcements (2) |
| Initial Review | 25 | 10 | INSPIR_Task_Access_and_New_Study (8), Preparing_a_Complete_Submission (3), Before_and_After_Examples (3), Example_Expedited_Interview_Study (3), Application_Section_Tips (2), INSPIR_Task_Records_and_Training (2), Recruitment_and_Screening (1), Radiation_in_Research (1) |
| more than minimal risk | 21 | 12 | Special_Populations (8), Expedited_and_Full_Board_Review (2), Obtaining_Consent (2), Quality_Improvement_or_Research (1), Exempt_Research (1), Exempt_Tip_13 (1), Chart_Review (1), Application_Section_Tips (1) |
| exempt determination | 18 | 14 | Exempt_Research (2), Continuing_Review_and_Closing (2), Working_with_Other_Institutions (2), FAQ (2), Start_Here_New_Researchers (1), Do_I_Need_IRB_Review (1), Exempt_Tip_1 (1), Ancillary_Reviews_Sign_Offs (1) |
| Full Board | 18 | 12 | Consent_Templates (5), INSPIR_Task_Choose_Review_Path (2), Research_Involving_Children (2), Do_I_Need_IRB_Review (1), Review_Path_Decision_Tool_v3 (1), Expedited_and_Full_Board_Review (1), Expedited_Tip_Sheets_Index (1), Study_Team_Members (1) |
| Full board | 18 | 9 | IRB_Review_Times (4), Expedited_Tip_7 (3), Expedited_Tip_9 (3), Expedited_and_Full_Board_Review (2), Timelines_and_JIT (2), Expedited_Tip_1 (1), Expedited_Tip_8 (1), Responding_to_Stipulations (1) |
| convened IRB | 17 | 9 | Continuing_Review_and_Closing (5), Humanitarian_Use_Devices (3), Drugs_and_Devices (2), Drug_Device_Decision_Guide (2), Review_Path_Decision_Tool_v3 (1), Expedited_and_Full_Board_Review (1), Expedited_Tip_8 (1), Expanded_Access_Emergency_Use (1) |
| convened meeting | 17 | 9 | Expedited_and_Full_Board_Review (4), Expedited_Tip_1 (4), Expedited_Tip_9 (2), Drugs_and_Devices (2), Humanitarian_Use_Devices (1), Special_Populations (1), Conflict_of_Interest (1), Glossary_A_to_Z (1) |
| full board review | 14 | 9 | Review_Path_Decision_Tool_v3 (5), Expedited_and_Full_Board_Review (2), Start_Here_New_Researchers (1), Exempt_Tip_6 (1), INSPIR_Task_Choose_Review_Path (1), Timelines_and_JIT (1), Contact_and_About (1), FAQ (1) |
| Expedited review | 13 | 9 | Exempt_Tip_12 (3), Expedited_and_Full_Board_Review (3), Review_Path_Decision_Tool_v3 (1), Exempt_Tip_13 (1), Expedited_Tip_Sheets_Index (1), INSPIR_Task_Choose_Review_Path (1), Example_Expedited_Interview_Study (1), Amendments (1) |
| convened board | 11 | 5 | Responding_to_Stipulations (6), Do_I_Need_IRB_Review (2), Hub_Before_You_Submit (1), Eligibility_and_Study_Design (1), Radiation_in_Research (1) |
| limited IRB review | 10 | 4 | Exempt_Research (4), Continuing_Review_and_Closing (3), INSPIR_Task_Checkins_Reports_Closing (2), Do_I_Need_IRB_Review (1) |
| exempt review | 9 | 8 | Do_I_Need_IRB_Review (2), Hub_Before_You_Submit (1), Review_Path_Decision_Tool_v3 (1), Exempt_Research (1), Timelines_and_JIT (1), Drug_Device_Decision_Guide (1), Conflict_of_Interest (1), IRB_Review_Times (1) |
| Greater than minimal risk | 9 | 7 | Consent_Language_Bank (2), Limited_English_Proficiency (2), Review_Path_Decision_Tool_v3 (1), Expedited_and_Full_Board_Review (1), Expedited_Tip_7 (1), Research_Involving_Children (1), Ceding_Review (1) |
| initial review | 7 | 7 | Example_Exempt_Survey (1), Amendments (1), Continuing_Review_and_Closing (1), Surveys_Interviews_Focus_Groups (1), Research_Involving_Children (1), Ceding_Review (1), Contact_and_About (1) |
| convened | 6 | 6 | Responding_to_Stipulations (1), Timelines_and_JIT (1), Reporting_and_Monitoring (1), Humanitarian_Use_Devices (1), Contact_and_About (1), IRB_Committees (1) |
| Full board review | 5 | 4 | Expedited_and_Full_Board_Review (2), Review_Path_Decision_Tool_v3 (1), Responding_to_Stipulations (1), IRB_Review_Times (1) |
| Limited IRB review | 5 | 4 | Exempt_Research (2), Exempt_Tip_2-2 (1), Exempt_Tip_3-2 (1), Glossary_A_to_Z (1) |
| convened review | 5 | 5 | Timelines_and_JIT (1), Amendments (1), Genetics_Biospecimens_Repositories (1), Staff_Directory (1), For_Board_Members (1) |
| Convened board | 4 | 3 | Do_I_Need_IRB_Review (2), Responding_to_Stipulations (1), Glossary_A_to_Z (1) |
| convened board review | 3 | 2 | Do_I_Need_IRB_Review (2), Exempt_Research (1) |
| Minimal Risk | 3 | 3 | Do_I_Need_IRB_Review (1), Exempt_Research (1), Exempt_Tip_13 (1) |
| Exempt determination | 3 | 2 | Continuing_Review_and_Closing (2), Responding_to_Stipulations (1) |
| Administrative review | 3 | 1 | Amendments (3) |
| convened IRB meeting | 3 | 3 | Amendments (1), Glossary_A_to_Z (1), For_Board_Members (1) |
| Convened IRB | 3 | 1 | Research_Involving_Children (3) |
| Convened review | 2 | 1 | IRB_Committees (2) |
| Full Board review | 1 | 1 | INSPIR_Task_Access_and_New_Study (1) |
| greater-than-minimal-risk | 1 | 1 | Obtaining_Consent (1) |
| full-board | 1 | 1 | Continuing_Review_and_Closing (1) |
| convened IRB review | 1 | 1 | Genetics_Biospecimens_Repositories (1) |
| convened board meeting | 1 | 1 | Special_Populations (1) |
| Initial review | 1 | 1 | Contact_and_About (1) |
| Minimal-risk | 1 | 1 | Announcements (1) |

### NHSR
| variant | total | pages | where (top 8) |
|---|---|---|---|
| NHSR | 82 | 19 | Review_Path_Decision_Tool_v3 (19), Do_I_Need_IRB_Review (18), Example_NHSR_and_QI_Requests (17), Quality_Improvement_or_Research (5), Glossary_A_to_Z (4), INSPIR_Task_Choose_Review_Path (3), Exempt_Tip_10 (2), FAQ (2) |
| not engaged | 30 | 16 | Working_with_Other_Institutions (7), Review_Path_Decision_Tool_v3 (5), Community_Engaged_Research (3), Start_Here_New_Researchers (2), Glossary_A_to_Z (2), Do_I_Need_IRB_Review (1), Study_Team_Members (1), Training_Requirements (1) |
| not research | 30 | 13 | Example_NHSR_and_QI_Requests (6), Review_Path_Decision_Tool_v3 (4), Quality_Improvement_or_Research (3), Case_Reports (3), Do_I_Need_IRB_Review (2), Drugs_and_Devices (2), Expanded_Access_Emergency_Use (2), Humanitarian_Use_Devices (2) |
| not human subjects research | 26 | 11 | Review_Path_Decision_Tool_v3 (6), FAQ (6), Start_Here_New_Researchers (3), Example_NHSR_and_QI_Requests (2), Genetics_Biospecimens_Repositories (2), Ask_the_IRB (2), Do_I_Need_IRB_Review (1), Exempt_Tip_10 (1) |
| Not Human Subjects Research | 23 | 14 | INSPIR_Task_Checkins_Reports_Closing (4), Continuing_Review_and_Closing (3), Glossary_A_to_Z (3), Chart_Review (2), Responding_to_Stipulations (2), Do_I_Need_IRB_Review (1), Review_Path_Decision_Tool_v3 (1), Application_Section_Tips (1) |
| Not Engaged | 22 | 10 | INSPIR_Task_Checkins_Reports_Closing (5), Do_I_Need_IRB_Review (4), Continuing_Review_and_Closing (3), Review_Path_Decision_Tool_v3 (2), Responding_to_Stipulations (2), Working_with_Other_Institutions (2), HIPAA_in_Research (1), Amendments (1) |
| Not human subjects research | 11 | 6 | Review_Path_Decision_Tool_v3 (4), Do_I_Need_IRB_Review (2), FAQ (2), Chart_Review (1), HIPAA_in_Research (1), Ask_the_IRB (1) |
| Not Human Subject Research | 7 | 6 | INSPIR_Task_Choose_Review_Path (2), Quality_Improvement_or_Research (1), Review_Path_Decision_Tool_v3 (1), INSPIR_Task_Access_and_New_Study (1), Example_NHSR_and_QI_Requests (1), Example_Exempt_Survey (1) |

### Submission/form names
| variant | total | pages | where (top 8) |
|---|---|---|---|
| amendment | 155 | 48 | Example_Amendment_and_Stipulation_Response (27), Amendments (18), INSPIR_Task_Change_Approved_Study (15), FAQ (8), Reporting_and_Monitoring (5), Announcements (5), Example_Expedited_Interview_Study (4), Limited_English_Proficiency (4) |
| Review Path Determination | 84 | 27 | Review_Path_Decision_Tool_v3 (14), INSPIR_Task_Choose_Review_Path (13), Do_I_Need_IRB_Review (7), INSPIR_Task_Access_and_New_Study (7), Example_NHSR_and_QI_Requests (5), Hub_Before_You_Submit (3), Exempt_Research (3), Example_Exempt_Chart_Review (3) |
| continuing review | 62 | 17 | Continuing_Review_and_Closing (16), INSPIR_Task_Checkins_Reports_Closing (15), Reporting_and_Monitoring (7), Expedited_and_Full_Board_Review (4), Expedited_Tip_9 (3), FAQ (3), Expedited_Tip_8 (2), Glossary_A_to_Z (2) |
| Continuing Review | 46 | 18 | INSPIR_Task_Checkins_Reports_Closing (13), Continuing_Review_and_Closing (6), Glossary_A_to_Z (5), Expedited_Tip_8 (3), Announcements (3), Exempt_Research (2), Data_Retention (2), Ceding_Review (2) |
| status check-in | 41 | 12 | Continuing_Review_and_Closing (14), INSPIR_Task_Checkins_Reports_Closing (9), Reporting_and_Monitoring (5), Exempt_Research (2), Expedited_and_Full_Board_Review (2), Short_Form_Consent_Process (2), FAQ (2), Start_Here_New_Researchers (1) |
| Study Application | 34 | 12 | INSPIR_Task_Change_Approved_Study (9), INSPIR_Task_Access_and_New_Study (7), Example_Expedited_Interview_Study (3), INSPIR_Task_Checkins_Reports_Closing (3), Preparing_a_Complete_Submission (2), Study_Team_Members (2), INSPIR_Task_Choose_Review_Path (2), Example_Amendment_and_Stipulation_Response (2) |
| Just-in-Time | 32 | 15 | Timelines_and_JIT (7), FAQ (5), Responding_to_Stipulations (3), IRB_Review_Times (3), Hub_Before_You_Submit (2), Clinical_Trials (2), Announcements (2), Start_Here_New_Researchers (1) |
| Closure Report | 29 | 7 | INSPIR_Task_Checkins_Reports_Closing (13), Continuing_Review_and_Closing (9), Data_Retention (2), Glossary_A_to_Z (2), INSPIR_Task_Change_Approved_Study (1), INSPIR_Task_Records_and_Training (1), Ceding_Review (1) |
| check-in | 28 | 9 | Continuing_Review_and_Closing (11), INSPIR_Task_Checkins_Reports_Closing (8), Exempt_Research (2), Example_NHSR_and_QI_Requests (2), Before_and_After_Examples (1), Example_Pediatric_Study (1), Hub_Post_Approval (1), Reporting_and_Monitoring (1) |
| Internal Study Personnel Changes form | 24 | 12 | Amendments (5), Study_Team_Members (3), Student_Trainee_Research (3), Example_Amendment_and_Stipulation_Response (3), Start_Here_New_Researchers (2), FAQ (2), Training_Requirements (1), Hub_Post_Approval (1) |
| Amendment | 24 | 10 | Example_Amendment_and_Stipulation_Response (8), Amendments (4), INSPIR_Task_Change_Approved_Study (4), Contact_and_About (2), Examples_and_Samples (1), Expanded_Access_Emergency_Use (1), Research_Involving_Children (1), Glossary_A_to_Z (1) |
| Change Request and Amendments form | 21 | 9 | Amendments (7), Example_Amendment_and_Stipulation_Response (3), Continuing_Review_and_Closing (3), INSPIR_Task_Change_Approved_Study (2), INSPIR_Task_Checkins_Reports_Closing (2), Study_Team_Members (1), INSPIR_Task_Access_and_New_Study (1), Working_with_Other_Institutions (1) |
| unanticipated problem | 15 | 7 | Reporting_and_Monitoring (7), INSPIR_Task_Checkins_Reports_Closing (2), FAQ (2), Templates_Forms_Library (1), Social_Media_Internet_Research (1), Ceding_Review (1), Ask_the_IRB (1) |
| Status Check-In | 14 | 7 | Continuing_Review_and_Closing (4), Announcements (3), INSPIR_Task_Checkins_Reports_Closing (2), Ceding_Review (2), Exempt_Research (1), Example_Amendment_and_Stipulation_Response (1), Amendments (1) |
| Change Request and Amendments | 13 | 4 | INSPIR_Task_Change_Approved_Study (9), Amendments (2), INSPIR_Task_Checkins_Reports_Closing (1), INSPIR_Task_Records_and_Training (1) |
| Recruitment Materials Submission Form | 11 | 5 | INSPIR_Task_Checkins_Reports_Closing (6), Amendments (2), Example_Amendment_and_Stipulation_Response (1), Recruitment_and_Screening (1), INSPIR_Task_Change_Approved_Study (1) |
| Contact Information Change Request Form | 10 | 4 | INSPIR_Task_Checkins_Reports_Closing (5), Amendments (2), INSPIR_Task_Change_Approved_Study (2), Example_Amendment_and_Stipulation_Response (1) |
| Internal Study Personnel Changes | 10 | 4 | INSPIR_Task_Change_Approved_Study (5), Amendments (3), INSPIR_Task_Checkins_Reports_Closing (1), INSPIR_Task_Records_and_Training (1) |
| Status check-in | 8 | 2 | Continuing_Review_and_Closing (7), Glossary_A_to_Z (1) |
| progress report | 6 | 5 | Humanitarian_Use_Devices (2), Short_Form_Consent_Process (1), Continuing_Review_and_Closing (1), Data_Sharing (1), Glossary_A_to_Z (1) |
| Protocol Exception Form | 6 | 3 | INSPIR_Task_Checkins_Reports_Closing (3), Amendments (2), INSPIR_Task_Change_Approved_Study (1) |
| Continuing Review Form | 6 | 1 | INSPIR_Task_Checkins_Reports_Closing (6) |
| Progress Report | 5 | 2 | Expedited_Tip_9 (4), INSPIR_Task_Checkins_Reports_Closing (1) |
| JIT | 5 | 1 | Timelines_and_JIT (5) |
| final report | 4 | 4 | Start_Here_New_Researchers (1), Exempt_Research (1), Working_with_Other_Institutions (1), FAQ (1) |
| Closeout | 4 | 2 | Continuing_Review_and_Closing (2), Data_Retention (2) |
| Protocol Exception form | 4 | 2 | Reporting_and_Monitoring (3), INSPIR_Task_Checkins_Reports_Closing (1) |
| Unanticipated problem | 3 | 2 | Glossary_A_to_Z (2), Reporting_and_Monitoring (1) |
| Protocol Exception | 3 | 2 | INSPIR_Task_Change_Approved_Study (2), INSPIR_Task_Checkins_Reports_Closing (1) |
| Unanticipated Problem | 3 | 1 | INSPIR_Task_Checkins_Reports_Closing (3) |
| closeout | 2 | 2 | Start_Here_New_Researchers (1), Continuing_Review_and_Closing (1) |
| QI determination | 2 | 2 | Examples_and_Samples (1), Example_NHSR_and_QI_Requests (1) |
| Study Closure | 2 | 2 | Continuing_Review_and_Closing (1), INSPIR_Task_Checkins_Reports_Closing (1) |
| Protocol Deviation | 2 | 2 | Reporting_and_Monitoring (1), INSPIR_Task_Checkins_Reports_Closing (1) |
| NHSR determination | 1 | 1 | Do_I_Need_IRB_Review (1) |
| personnel change form | 1 | 1 | INSPIR_Task_Change_Approved_Study (1) |
| Contact Information Change Request | 1 | 1 | INSPIR_Task_Change_Approved_Study (1) |
| Reportable Event | 1 | 1 | Humanitarian_Use_Devices (1) |
| close-out | 1 | 1 | Data_Retention (1) |
| closure report | 1 | 1 | Contact_and_About (1) |

### Study team roles
| variant | total | pages | where (top 8) |
|---|---|---|---|
| Supervising PI | 71 | 17 | Student_Trainee_Research (17), Study_Team_Members (13), INSPIR_Task_Change_Approved_Study (7), Preparing_a_Complete_Submission (5), Example_Exempt_Survey (5), FAQ (5), Continuing_Review_and_Closing (4), INSPIR_Task_Access_and_New_Study (3) |
| Study Personnel | 54 | 14 | INSPIR_Task_Change_Approved_Study (18), Amendments (8), INSPIR_Task_Access_and_New_Study (5), INSPIR_Task_Records_and_Training (4), Study_Team_Members (3), Student_Trainee_Research (3), Example_Amendment_and_Stipulation_Response (3), Start_Here_New_Researchers (2) |
| study personnel | 46 | 20 | INSPIR_Task_Change_Approved_Study (9), Study_Team_Members (8), Amendments (5), Student_Trainee_Research (3), Review_Path_Decision_Tool_v3 (2), Training_Requirements (2), INSPIR_Task_Access_and_New_Study (2), Working_with_Other_Institutions (2) |
| Principal Investigator | 36 | 17 | Student_Trainee_Research (5), Example_Expedited_Interview_Study (5), Application_Section_Tips (4), Study_Team_Members (4), INSPIR_Task_Change_Approved_Study (3), Training_Requirements (2), INSPIR_Task_Access_and_New_Study (2), Data_Retention (2) |
| Study Contact | 31 | 11 | Study_Team_Members (8), INSPIR_Task_Change_Approved_Study (7), INSPIR_Task_Access_and_New_Study (5), Example_Exempt_Survey (2), Example_Expedited_Interview_Study (2), INSPIR_Task_Checkins_Reports_Closing (2), Student_Trainee_Research (1), Example_Exempt_Chart_Review (1) |
| study staff | 28 | 16 | Example_Expedited_Interview_Study (8), Example_Exempt_Chart_Review (5), Limited_English_Proficiency (2), Start_Here_New_Researchers (1), Expedited_Tip_5 (1), Example_Exempt_Survey (1), Example_Pediatric_Study (1), Example_Amendment_and_Stipulation_Response (1) |
| study coordinator | 26 | 3 | Example_Expedited_Interview_Study (21), Before_and_After_Examples (4), Example_Amendment_and_Stipulation_Response (1) |
| study contact | 17 | 15 | Student_Trainee_Research (2), Responding_to_Stipulations (2), Exempt_Tip_1 (1), Exempt_Tip_2-1 (1), Exempt_Tip_2-2 (1), Exempt_Tip_3-1 (1), Exempt_Tip_3-2 (1), Exempt_Tip_5 (1) |
| Administrative Assistant | 17 | 8 | INSPIR_Task_Change_Approved_Study (6), Study_Team_Members (5), Training_Requirements (1), Example_Exempt_Survey (1), Example_Amendment_and_Stipulation_Response (1), Amendments (1), Contact_and_About (1), Staff_Directory (1) |
| co-investigator | 15 | 11 | Student_Trainee_Research (2), Example_Exempt_Survey (2), Example_Expedited_Interview_Study (2), Recruitment_and_Screening (2), Application_Section_Tips (1), INSPIR_Task_Access_and_New_Study (1), Reporting_and_Monitoring (1), INSPIR_Task_Change_Approved_Study (1) |
| Study Team Members | 11 | 9 | Preparing_a_Complete_Submission (3), Hub_Before_You_Submit (1), Start_Here_New_Researchers (1), Study_Team_Members (1), Example_Exempt_Survey (1), Example_Exempt_Chart_Review (1), Example_Expedited_Interview_Study (1), VA_Research (1) |
| research staff | 11 | 8 | Start_Here_New_Researchers (2), Training_Requirements (2), Mandated_Reporting_and_Safety_Plans (2), Application_Section_Tips (1), Study_Team_Members (1), INSPIR_Task_Change_Approved_Study (1), Community_Engaged_Research (1), Policies_and_Regulations (1) |
| Research Staff | 11 | 5 | Example_Expedited_Interview_Study (4), Study_Team_Members (2), Example_Exempt_Survey (2), Example_Exempt_Chart_Review (2), INSPIR_Task_Access_and_New_Study (1) |
| Study personnel | 10 | 8 | Preparing_a_Complete_Submission (2), Example_Exempt_Chart_Review (2), Example_Exempt_Survey (1), Example_Expedited_Interview_Study (1), Example_Amendment_and_Stipulation_Response (1), Amendments (1), Glossary_A_to_Z (1), FAQ (1) |
| Co-Investigator | 9 | 5 | Example_Exempt_Survey (3), Study_Team_Members (2), Example_Exempt_Chart_Review (2), Example_Expedited_Interview_Study (1), INSPIR_Task_Change_Approved_Study (1) |
| Key Personnel | 7 | 3 | INSPIR_Task_Change_Approved_Study (5), Example_Amendment_and_Stipulation_Response (1), Amendments (1) |
| study team member | 6 | 4 | Example_Expedited_Interview_Study (2), Limited_English_Proficiency (2), Before_and_After_Examples (1), INSPIR_Task_Records_and_Training (1) |
| principal investigator | 5 | 5 | IRB_Home (1), Limited_English_Proficiency (1), Short_Form_Consent_Process (1), Glossary_A_to_Z (1), IRB_Review_Times (1) |
| study team members | 5 | 3 | Application_Section_Tips (2), Amendments (2), Example_Amendment_and_Stipulation_Response (1) |
| Study staff | 5 | 3 | Example_Expedited_Interview_Study (3), Example_Exempt_Chart_Review (1), HIPAA_Waiver_Sample_Answers (1) |
| Co-Investigators | 3 | 1 | Study_Team_Members (3) |
| Faculty Sponsor | 3 | 3 | Student_Trainee_Research (1), INSPIR_Task_Change_Approved_Study (1), Glossary_A_to_Z (1) |
| co-investigators | 1 | 1 | Application_Section_Tips (1) |
| Co-investigator | 1 | 1 | Example_Expedited_Interview_Study (1) |
| key personnel | 1 | 1 | Conflict_of_Interest (1) |

### Reliance terms
| variant | total | pages | where (top 8) |
|---|---|---|---|
| reviewing IRB | 54 | 17 | Ceding_Review (25), Continuing_Review_and_Closing (4), Review_Path_Decision_Tool_v3 (3), Conflict_of_Interest (3), Amendments (2), Reporting_and_Monitoring (2), INSPIR_Task_Checkins_Reports_Closing (2), Working_with_Other_Institutions (2) |
| ceded | 34 | 19 | INSPIR_Task_Checkins_Reports_Closing (5), Amendments (3), Working_with_Other_Institutions (3), Limited_English_Proficiency (2), Continuing_Review_and_Closing (2), INSPIR_Task_Change_Approved_Study (2), Ceding_Review (2), Glossary_A_to_Z (2) |
| reliance agreement | 33 | 18 | Working_with_Other_Institutions (9), Study_Team_Members (3), Glossary_A_to_Z (3), Student_Trainee_Research (2), Amendments (2), Community_Engaged_Research (2), Review_Path_Decision_Tool_v3 (1), Exempt_Research (1) |
| IRB of record | 29 | 16 | Ceding_Review (5), Glossary_A_to_Z (5), Working_with_Other_Institutions (4), Review_Path_Decision_Tool_v3 (3), Exempt_Research (1), Eligibility_and_Study_Design (1), Training_Requirements (1), INSPIR_Task_Choose_Review_Path (1) |
| single IRB | 22 | 9 | Working_with_Other_Institutions (10), Review_Path_Decision_Tool_v3 (3), Ceding_Review (3), Do_I_Need_IRB_Review (1), Expedited_Tip_Sheets_Index (1), Consent_Templates (1), VA_Research (1), Contact_and_About (1) |
| SMART IRB | 19 | 6 | Ceding_Review (9), Glossary_A_to_Z (4), Working_with_Other_Institutions (3), Do_I_Need_IRB_Review (1), Review_Path_Decision_Tool_v3 (1), Study_Team_Members (1) |
| Ceding Review | 19 | 16 | Clinical_Trials (2), Conflict_of_Interest (2), IRB_Review_Times (2), Review_Path_Decision_Tool_v3 (1), Eligibility_and_Study_Design (1), Ancillary_Reviews_Sign_Offs (1), INSPIR_Task_Choose_Review_Path (1), Timelines_and_JIT (1) |
| Ceded | 12 | 10 | Continuing_Review_and_Closing (3), Eligibility_and_Study_Design (1), Ancillary_Reviews_Sign_Offs (1), Study_Team_Members (1), Limited_English_Proficiency (1), Short_Form_Consent_Process (1), HIPAA_in_Research (1), Radiation_in_Research (1) |
| cede review | 8 | 4 | Do_I_Need_IRB_Review (3), Ceding_Review (3), Application_Section_Tips (1), Working_with_Other_Institutions (1) |
| Authorization Agreement | 7 | 7 | Review_Path_Decision_Tool_v3 (1), Study_Team_Members (1), INSPIR_Task_Choose_Review_Path (1), Example_Exempt_Survey (1), Example_Expedited_Interview_Study (1), Working_with_Other_Institutions (1), Ceding_Review (1) |
| IAA | 7 | 4 | Review_Path_Decision_Tool_v3 (3), Glossary_A_to_Z (2), Study_Team_Members (1), Working_with_Other_Institutions (1) |
| IRB Authorization Agreement | 7 | 5 | Study_Team_Members (2), Glossary_A_to_Z (2), Example_Expedited_Interview_Study (1), Working_with_Other_Institutions (1), Conflict_of_Interest (1) |
| Cede review | 5 | 5 | Do_I_Need_IRB_Review (1), Review_Path_Decision_Tool_v3 (1), INSPIR_Task_Choose_Review_Path (1), Hub_Guidance (1), Glossary_A_to_Z (1) |
| Relying Institution | 5 | 5 | Review_Path_Decision_Tool_v3 (1), INSPIR_Task_Choose_Review_Path (1), Working_with_Other_Institutions (1), Ceding_Review (1), Community_Engaged_Research (1) |
| global reliance agreement | 4 | 4 | IRB_Home (1), Student_Trainee_Research (1), INSPIR_Task_Change_Approved_Study (1), Ceding_Review (1) |
| Reviewing Institution | 4 | 4 | Review_Path_Decision_Tool_v3 (1), INSPIR_Task_Choose_Review_Path (1), Working_with_Other_Institutions (1), Ceding_Review (1) |
| Ceded review | 4 | 1 | IRB_Review_Times (4) |
| ceding review | 3 | 3 | Hub_Before_You_Submit (1), Hub_Post_Approval (1), Hub_Guidance (1) |
| ceded review | 3 | 3 | INSPIR_Task_Access_and_New_Study (1), Contact_and_About (1), Staff_Directory (1) |
| Cede Review | 2 | 2 | Amendments (1), Ceding_Review (1) |
| Global Reliance Agreement | 1 | 1 | INSPIR_Task_Change_Approved_Study (1) |
| Ceding review | 1 | 1 | Working_with_Other_Institutions (1) |
| Reviewing IRB | 1 | 1 | Ceding_Review (1) |
| Ceded Review | 1 | 1 | Ceding_Review (1) |
| Global reliance agreement | 1 | 1 | Glossary_A_to_Z (1) |
| relying institution | 1 | 1 | Glossary_A_to_Z (1) |
| Reliance agreement | 1 | 1 | Glossary_A_to_Z (1) |
| Single IRB | 1 | 1 | Glossary_A_to_Z (1) |

### Contacts (email/phone)
| variant | total | pages | where (top 8) |
|---|---|---|---|
| medirb@bu.edu | 236 | 108 | Review_Path_Decision_Tool_v3 (14), Contact_and_About (12), Staff_Directory (10), FAQ (9), Working_with_Other_Institutions (6), INSPIR_Task_Access_and_New_Study (5), INSPIR_Task_Records_and_Training (5), Expanded_Access_Emergency_Use (5) |
| (617) 358-5372 | 33 | 16 | Contact_and_About (6), INSPIR_Task_Checkins_Reports_Closing (3), For_Research_Participants (3), For_Research_Participants_ES (3), INSPIR_Task_Access_and_New_Study (2), Amendments (2), INSPIR_Task_Change_Approved_Study (2), INSPIR_Task_Records_and_Training (2) |
| DG-privacyofficer@bmc.org | 12 | 9 | Case_Reports (2), Example_Expedited_Interview_Study (2), Consent_Language_Bank (2), Review_Path_Decision_Tool_v3 (1), Ancillary_Reviews_Sign_Offs (1), HIPAA_in_Research (1), Reporting_and_Monitoring (1), Data_Security_for_Researchers (1) |
| bumcinfosec@bu.edu | 8 | 5 | Data_Security_for_Researchers (3), AI_in_Research (2), Ancillary_Reviews_Sign_Offs (1), Remote_Decentralized_Research (1), Social_Media_Internet_Research (1) |
| 617-358-5372 | 5 | 4 | Consent_Language_Bank (2), Informed_Consent_Overview (1), Consent_Templates (1), Templates_Forms_Library (1) |
| 617-555-0142 | 4 | 1 | Example_Expedited_Interview_Study (4) |
| HIPAA@bu.edu | 4 | 4 | HIPAA_in_Research (1), Reporting_and_Monitoring (1), Data_Security_for_Researchers (1), Social_Media_Internet_Research (1) |
| ithelp@bu.edu | 4 | 4 | HIPAA_in_Research (1), Reporting_and_Monitoring (1), Data_Security_for_Researchers (1), Social_Media_Internet_Research (1) |
| hipaa@bu.edu | 3 | 2 | Case_Reports (2), Review_Path_Decision_Tool_v3 (1) |
| cdw@bmc.org | 3 | 2 | Chart_Review (2), Example_Exempt_Chart_Review (1) |
| DUA.MTARequest@bmc.org | 3 | 3 | Chart_Review (1), Data_Security_for_Researchers (1), Data_Sharing (1) |
| CTO@bmc.org | 3 | 2 | Paying_Participants (2), Expanded_Access_Emergency_Use (1) |
| irb@bu.edu | 3 | 3 | Social_Media_Internet_Research (1), Contact_and_About (1), Ask_the_IRB (1) |
| rchelp@bu.edu | 2 | 2 | Obtaining_Consent (1), Data_Security_for_Researchers (1) |
| IPS@bmc.org | 2 | 2 | Drugs_and_Devices (1), Expanded_Access_Emergency_Use (1) |
| COI-Compliance@bmc.org | 2 | 1 | Conflict_of_Interest (2) |
| coi@bu.edu | 2 | 1 | Conflict_of_Interest (2) |
| (617) 414-5549 | 2 | 2 | For_Research_Participants (1), For_Research_Participants_ES (1) |
| crn@bmc.org | 2 | 2 | For_Research_Participants (1), For_Research_Participants_ES (1) |
| ccr@bmc.org | 2 | 2 | For_Research_Participants (1), For_Research_Participants_ES (1) |
| jdoe@bu.edu | 1 | 1 | INSPIR_Task_Access_and_New_Study (1) |
| 617-638-5914 | 1 | 1 | INSPIR_Task_Access_and_New_Study (1) |
| cto@bmc.org | 1 | 1 | Example_Exempt_Survey (1) |
| 617-414-5549 | 1 | 1 | Limited_English_Proficiency (1) |
| bumchelp@bu.edu | 1 | 1 | Data_Security_for_Researchers (1) |
| DUA.MTArequest@bmc.org | 1 | 1 | Working_with_Other_Institutions (1) |
| export@bu.edu | 1 | 1 | International_Research (1) |
| 617-353-2595 | 1 | 1 | Conflict_of_Interest (1) |
| crro@bu.edu | 1 | 1 | Contact_and_About (1) |
| jcm57@bu.edu | 1 | 1 | Staff_Directory (1) |
| (617) 358-6557 | 1 | 1 | Staff_Directory (1) |
| lint@bu.edu | 1 | 1 | Staff_Directory (1) |
| (617) 358-5302 | 1 | 1 | Staff_Directory (1) |
| marktes@bu.edu | 1 | 1 | Staff_Directory (1) |
| (617) 358-5365 | 1 | 1 | Staff_Directory (1) |
| cvswain@bu.edu | 1 | 1 | Staff_Directory (1) |
| (617) 358-6556 | 1 | 1 | Staff_Directory (1) |
| kmott42@bu.edu | 1 | 1 | Staff_Directory (1) |
| (617) 358-6558 | 1 | 1 | Staff_Directory (1) |
| ttulloch@bu.edu | 1 | 1 | Staff_Directory (1) |
| (617) 358-0828 | 1 | 1 | Staff_Directory (1) |
| jerrylu@bu.edu | 1 | 1 | Staff_Directory (1) |
| (617) 358-7384 | 1 | 1 | Staff_Directory (1) |
| vtorresl@bu.edu | 1 | 1 | Staff_Directory (1) |
| (617) 358-5301 | 1 | 1 | Staff_Directory (1) |
| roz@bu.edu | 1 | 1 | Staff_Directory (1) |
| (617) 358-5329 | 1 | 1 | Staff_Directory (1) |
| kkhattar@bu.edu | 1 | 1 | Staff_Directory (1) |
| (617) 358-5351 | 1 | 1 | Staff_Directory (1) |
| temile8@bu.edu | 1 | 1 | Staff_Directory (1) |
| crtimes@bu.edu | 1 | 1 | Announcements (1) |

### Training terms
| variant | total | pages | where (top 8) |
|---|---|---|---|
| CITI | 65 | 9 | Training_Requirements (32), INSPIR_Task_Records_and_Training (20), Start_Here_New_Researchers (5), VA_Research (2), Glossary_A_to_Z (2), Working_with_Other_Institutions (1), Ceding_Review (1), Community_Engaged_Research (1) |
| GCP | 60 | 17 | Training_Requirements (19), Consent_Language_Bank (8), Start_Here_New_Researchers (6), INSPIR_Task_Records_and_Training (6), Clinical_Trials (3), Informed_Consent_Overview (2), Amendments (2), Drugs_and_Devices (2) |
| human subjects training | 18 | 11 | Training_Requirements (4), INSPIR_Task_Access_and_New_Study (2), Example_Exempt_Survey (2), INSPIR_Task_Records_and_Training (2), International_Research (2), Timelines_and_JIT (1), Example_Expedited_Interview_Study (1), Surveys_Interviews_Focus_Groups (1) |
| Good Clinical Practice | 12 | 9 | Training_Requirements (2), INSPIR_Task_Records_and_Training (2), Glossary_A_to_Z (2), Start_Here_New_Researchers (1), Study_Team_Members (1), Amendments (1), Clinical_Trials (1), Drugs_and_Devices (1) |
| Medical Campus CITI | 7 | 5 | Working_with_Other_Institutions (3), Study_Team_Members (1), Training_Requirements (1), Amendments (1), Ceding_Review (1) |
| human subjects protection training | 5 | 5 | Preparing_a_Complete_Submission (1), Study_Team_Members (1), Training_Requirements (1), VA_Research (1), Community_Engaged_Research (1) |
| CITI Program | 5 | 2 | INSPIR_Task_Records_and_Training (4), Training_Requirements (1) |
| Human Subjects Protection training | 1 | 1 | Amendments (1) |

### Subject vs participant
| variant | total | pages | where (top 8) |
|---|---|---|---|
| participants | 384 | 76 | Consent_Language_Bank (24), Example_Expedited_Interview_Study (21), Remote_Decentralized_Research (18), Deception_Incomplete_Disclosure (16), AI_in_Research (13), FAQ (13), Exempt_Research (12), Example_Amendment_and_Stipulation_Response (12) |
| participant | 219 | 49 | Example_Expedited_Interview_Study (21), Limited_English_Proficiency (20), Short_Form_Consent_Process (17), Consent_Templates (12), Special_Populations (10), FAQ (9), Paying_Participants (8), Remote_Decentralized_Research (8) |
| subjects | 175 | 51 | Example_Expedited_Interview_Study (16), INSPIR_Task_Change_Approved_Study (13), For_Board_Members (13), Amendments (9), Continuing_Review_and_Closing (8), Reporting_and_Monitoring (8), Example_Exempt_Survey (6), INSPIR_Task_Checkins_Reports_Closing (6) |
| human subjects | 134 | 46 | Review_Path_Decision_Tool_v3 (14), Do_I_Need_IRB_Review (13), FAQ (11), Glossary_A_to_Z (6), Chart_Review (5), Training_Requirements (5), Student_Trainee_Research (5), Timelines_and_JIT (5) |
| Participants | 88 | 35 | Example_Expedited_Interview_Study (11), Before_and_After_Examples (7), Consent_Language_Bank (7), Community_Engaged_Research (7), Obtaining_Consent (5), Example_Amendment_and_Stipulation_Response (4), Exempt_Tip_3-1 (3), Informed_Consent_Overview (3) |
| subject | 84 | 32 | Reporting_and_Monitoring (14), INSPIR_Task_Checkins_Reports_Closing (11), Consent_Templates (7), Continuing_Review_and_Closing (4), Glossary_A_to_Z (4), Example_Exempt_Chart_Review (3), Example_Expedited_Interview_Study (3), Consent_Language_Bank (3) |
| Human Subjects | 45 | 25 | INSPIR_Task_Checkins_Reports_Closing (4), Continuing_Review_and_Closing (3), Remote_Decentralized_Research (3), Glossary_A_to_Z (3), Do_I_Need_IRB_Review (2), Review_Path_Decision_Tool_v3 (2), Chart_Review (2), Ancillary_Reviews_Sign_Offs (2) |
| Subjects | 42 | 25 | Example_Expedited_Interview_Study (8), Before_and_After_Examples (4), Example_Exempt_Survey (4), Obtaining_Consent (3), Eligibility_and_Study_Design (2), Recruitment_and_Screening (2), Exempt_Tip_1 (1), Exempt_Tip_2-1 (1) |
| Research Participants | 28 | 19 | Before_and_After_Examples (2), Example_Exempt_Survey (2), Example_Expedited_Interview_Study (2), Consent_Language_Bank (2), Recruitment_and_Screening (2), Surveys_Interviews_Focus_Groups (2), Remote_Decentralized_Research (2), Research_Involving_Children (2) |
| Subject | 16 | 8 | Consent_Language_Bank (5), Example_Pediatric_Study (4), Example_Expedited_Interview_Study (2), Example_Exempt_Survey (1), Example_Exempt_Chart_Review (1), Consent_Templates (1), Paying_Participants (1), INSPIR_Task_Checkins_Reports_Closing (1) |
| Human Subject | 12 | 9 | Paying_Participants (3), INSPIR_Task_Choose_Review_Path (2), Do_I_Need_IRB_Review (1), Quality_Improvement_or_Research (1), Review_Path_Decision_Tool_v3 (1), Exempt_Research (1), INSPIR_Task_Access_and_New_Study (1), Example_NHSR_and_QI_Requests (1) |
| Participant | 10 | 9 | Limited_English_Proficiency (2), Eligibility_and_Study_Design (1), Consent_Templates (1), Obtaining_Consent (1), HIPAA_in_Research (1), Continuing_Review_and_Closing (1), Hub_Guidance (1), Data_Security_for_Researchers (1) |
| Human subjects | 9 | 7 | Hub_Before_You_Submit (2), Training_Requirements (2), Start_Here_New_Researchers (1), Do_I_Need_IRB_Review (1), Student_Trainee_Research (1), Example_Pediatric_Study (1), Glossary_A_to_Z (1) |
| research participants | 7 | 5 | Contact_and_About (2), FAQ (2), Paying_Participants (1), Data_Security_for_Researchers (1), IRB_Committees (1) |
| research subjects | 6 | 6 | Study_Team_Members (1), Example_Exempt_Survey (1), Example_Exempt_Chart_Review (1), Example_Expedited_Interview_Study (1), Special_Populations (1), Data_Security_for_Researchers (1) |
| volunteers | 5 | 5 | Exempt_Tip_13 (1), Expedited_Tip_2 (1), Surveys_Interviews_Focus_Groups (1), Contact_and_About (1), For_Research_Participants (1) |
| research participant | 5 | 4 | Contact_and_About (2), Recruitment_and_Screening (1), Ask_the_IRB (1), For_Research_Participants (1) |
| Human subject | 3 | 3 | Start_Here_New_Researchers (1), Do_I_Need_IRB_Review (1), Glossary_A_to_Z (1) |
| human subject | 3 | 3 | Drugs_and_Devices (1), Glossary_A_to_Z (1), Policies_and_Regulations (1) |
| study volunteer | 2 | 2 | IRB_Home (1), Hub_About_the_IRB (1) |
| Research Subjects | 2 | 2 | Paying_Participants (1), Announcements (1) |
| Research Subject | 2 | 1 | For_Research_Participants (2) |
| research subject | 1 | 1 | Consent_Language_Bank (1) |
| volunteer | 1 | 1 | Working_with_Other_Institutions (1) |

### Consent/HIPAA terms
| variant | total | pages | where (top 8) |
|---|---|---|---|
| consent form | 396 | 73 | Example_Expedited_Interview_Study (29), Example_Amendment_and_Stipulation_Response (26), Before_and_After_Examples (25), Consent_Language_Bank (22), Limited_English_Proficiency (20), INSPIR_Task_Change_Approved_Study (14), For_Research_Participants (13), Short_Form_Consent_Process (11) |
| assent | 125 | 23 | Example_Pediatric_Study (37), Research_Involving_Children (32), Exempt_Tip_12 (10), Consent_Templates (10), Templates_Forms_Library (9), Examples_and_Samples (3), Special_Populations (3), Exempt_Research (2) |
| short form | 107 | 12 | Short_Form_Consent_Process (54), Limited_English_Proficiency (33), Example_Expedited_Interview_Study (3), Hub_Consent_HIPAA_Recruitment (3), Consent_Templates (3), FAQ (3), Obtaining_Consent (2), Continuing_Review_and_Closing (2) |
| Consent Form | 91 | 34 | Consent_Language_Bank (34), Consent_Templates (12), Research_Involving_Children (4), Example_Expedited_Interview_Study (3), Example_Pediatric_Study (3), Templates_Forms_Library (3), INSPIR_Task_Access_and_New_Study (2), Before_and_After_Examples (2) |
| Information Sheet | 86 | 30 | Consent_Language_Bank (16), Example_Exempt_Survey (9), Review_Path_Decision_Tool_v3 (8), Consent_Templates (7), Exempt_Research (6), Expedited_Tip_7 (3), Templates_Forms_Library (3), Surveys_Interviews_Focus_Groups (3) |
| HIPAA authorization | 77 | 32 | Example_Expedited_Interview_Study (9), Consent_Language_Bank (9), Consent_Templates (6), Case_Reports (5), HIPAA_in_Research (4), Do_I_Need_IRB_Review (3), Review_Path_Decision_Tool_v3 (3), Before_and_After_Examples (3) |
| information sheet | 66 | 29 | Example_Exempt_Survey (10), Review_Path_Decision_Tool_v3 (7), Obtaining_Consent (4), Exempt_Research (3), Exempt_Tip_2-1 (3), Exempt_Tip_13 (3), Before_and_After_Examples (3), Deception_Incomplete_Disclosure (3) |
| HIPAA waiver | 36 | 18 | Chart_Review (8), Example_Expedited_Interview_Study (5), Before_and_After_Examples (3), HIPAA_in_Research (3), Review_Path_Decision_Tool_v3 (2), Expedited_Tip_5 (2), Example_Exempt_Chart_Review (2), Hub_Before_You_Submit (1) |
| Limited English Proficiency | 32 | 21 | Example_Expedited_Interview_Study (3), Community_Engaged_Research (3), Announcements (3), Eligibility_and_Study_Design (2), Example_Amendment_and_Stipulation_Response (2), Short_Form_Consent_Process (2), Special_Populations (2), International_Research (2) |
| HIPAA Waiver | 28 | 17 | Before_and_After_Examples (4), Example_Exempt_Chart_Review (4), Examples_and_Samples (2), Example_Expedited_Interview_Study (2), Consent_Language_Bank (2), Templates_Forms_Library (2), HIPAA_in_Research (2), Review_Path_Decision_Tool_v3 (1) |
| Consent form | 24 | 14 | Example_Amendment_and_Stipulation_Response (4), Paying_Participants (3), Before_and_After_Examples (2), Consent_Language_Bank (2), ClinicalTrials_gov (2), Research_Involving_Children (2), Ceding_Review (2), Example_Expedited_Interview_Study (1) |
| parental permission | 23 | 15 | Research_Involving_Children (8), Example_Pediatric_Study (2), Exempt_Research (1), Exempt_Tip_12 (1), Preparing_a_Complete_Submission (1), Hub_Consent_HIPAA_Recruitment (1), Informed_Consent_Overview (1), Consent_Templates (1) |
| limited English proficiency | 20 | 13 | Limited_English_Proficiency (5), Eligibility_and_Study_Design (2), Example_Expedited_Interview_Study (2), Consent_Templates (2), Example_Amendment_and_Stipulation_Response (1), Informed_Consent_Overview (1), Templates_Forms_Library (1), Obtaining_Consent (1) |
| Short Form Consent | 16 | 11 | Consent_Templates (3), Limited_English_Proficiency (3), For_Board_Members (2), Example_Expedited_Interview_Study (1), Hub_Consent_HIPAA_Recruitment (1), Informed_Consent_Overview (1), Consent_Language_Bank (1), Obtaining_Consent (1) |
| waiver of HIPAA authorization | 14 | 10 | Review_Path_Decision_Tool_v3 (3), Example_Expedited_Interview_Study (2), FAQ (2), Chart_Review (1), Examples_and_Samples (1), Example_NHSR_and_QI_Requests (1), Example_Exempt_Chart_Review (1), Recruitment_and_Screening (1) |
| consent document | 12 | 9 | Expedited_Tip_7 (2), Paying_Participants (2), Surveys_Interviews_Focus_Groups (2), Exempt_Research (1), Exempt_Tip_13 (1), Hub_Consent_HIPAA_Recruitment (1), Consent_Templates (1), Glossary_A_to_Z (1) |
| Short form | 12 | 5 | Limited_English_Proficiency (6), Short_Form_Consent_Process (3), Example_Expedited_Interview_Study (1), Templates_Forms_Library (1), Glossary_A_to_Z (1) |
| Assent | 11 | 6 | Example_Pediatric_Study (4), Special_Populations (2), Glossary_A_to_Z (2), Examples_and_Samples (1), Research_Involving_Children (1), For_Board_Members (1) |
| HIPAA Authorization | 10 | 5 | Review_Path_Decision_Tool_v3 (4), Case_Reports (2), Templates_Forms_Library (2), Example_NHSR_and_QI_Requests (1), Example_Expedited_Interview_Study (1) |
| eConsent | 10 | 4 | Obtaining_Consent (4), Announcements (3), Templates_Forms_Library (2), Remote_Decentralized_Research (1) |
| waiver of authorization | 10 | 5 | HIPAA_in_Research (5), Recruitment_and_Screening (2), HIPAA_Waiver_Sample_Answers (1), Glossary_A_to_Z (1), FAQ (1) |
| waiver of consent | 9 | 7 | Deception_Incomplete_Disclosure (2), Research_Involving_Children (2), Expedited_Tip_5 (1), Example_NHSR_and_QI_Requests (1), Recruitment_and_Screening (1), Glossary_A_to_Z (1), FAQ (1) |
| alteration of consent | 9 | 8 | Obtaining_Consent (2), Expedited_Tip_6 (1), Expedited_Tip_7 (1), Consent_Templates (1), Deception_Incomplete_Disclosure (1), AI_in_Research (1), Social_Media_Internet_Research (1), Glossary_A_to_Z (1) |
| e-consent | 9 | 3 | Obtaining_Consent (7), Drugs_and_Devices (1), FAQ (1) |
| Parental permission | 8 | 8 | Do_I_Need_IRB_Review (1), Exempt_Research (1), Exempt_Tip_12 (1), Example_Pediatric_Study (1), Templates_Forms_Library (1), Research_Involving_Children (1), Glossary_A_to_Z (1), FAQ (1) |
| electronic consent | 8 | 5 | Remote_Decentralized_Research (4), Informed_Consent_Overview (1), Consent_Templates (1), Obtaining_Consent (1), FAQ (1) |
| waiver of documentation | 7 | 4 | Expedited_Tip_7 (3), Consent_Language_Bank (2), Obtaining_Consent (1), Glossary_A_to_Z (1) |
| Limited English proficiency | 5 | 4 | Glossary_A_to_Z (2), Example_Expedited_Interview_Study (1), Announcements (1), Policies_and_Regulations (1) |
| short form consent | 5 | 3 | Short_Form_Consent_Process (3), FAQ (1), Announcements (1) |
| verbal consent | 4 | 4 | Expedited_Tip_7 (1), Expanded_Access_Emergency_Use (1), FAQ (1), Policies_and_Regulations (1) |
| Waiver of Documentation | 4 | 3 | Example_Expedited_Interview_Study (2), Example_Pediatric_Study (1), For_Board_Members (1) |
| e-Consent | 3 | 3 | Exempt_Research (1), Special_Populations (1), Glossary_A_to_Z (1) |
| Short form consent | 3 | 3 | Templates_Forms_Library (1), Announcements (1), Policies_and_Regulations (1) |
| Waiver of consent | 3 | 2 | Glossary_A_to_Z (2), Obtaining_Consent (1) |
| Verbal consent | 3 | 3 | Obtaining_Consent (1), Surveys_Interviews_Focus_Groups (1), FAQ (1) |
| LEP | 3 | 2 | Glossary_A_to_Z (2), Ceding_Review (1) |
| waiver of informed consent | 2 | 2 | Chart_Review (1), HIPAA_in_Research (1) |
| Waiver of HIPAA authorization | 2 | 2 | Example_Exempt_Chart_Review (1), Glossary_A_to_Z (1) |
| Alteration of Consent | 2 | 1 | Example_Expedited_Interview_Study (2) |
| limited English Proficiency | 2 | 1 | Example_Expedited_Interview_Study (2) |
| Alteration of consent | 2 | 2 | Obtaining_Consent (1), Glossary_A_to_Z (1) |
| Electronic consent | 2 | 2 | Obtaining_Consent (1), Announcements (1) |
| waiver of documentation of consent | 2 | 2 | Obtaining_Consent (1), FAQ (1) |
| Waiver of documentation of consent | 2 | 2 | Obtaining_Consent (1), Glossary_A_to_Z (1) |
| Waiver of authorization | 2 | 2 | HIPAA_in_Research (1), Recruitment_and_Screening (1) |
| Short Form | 2 | 1 | Continuing_Review_and_Closing (2) |
| Information sheet | 1 | 1 | Example_Exempt_Survey (1) |
| Waiver of documentation | 1 | 1 | Obtaining_Consent (1) |
| alteration of informed consent | 1 | 1 | Deception_Incomplete_Disclosure (1) |
| Verbal Consent | 1 | 1 | For_Board_Members (1) |

### Office / unit names
| variant | total | pages | where (top 8) |
|---|---|---|---|
| CRRO | 138 | 37 | Clinical_Trials (9), Training_Requirements (7), Obtaining_Consent (7), Drugs_and_Devices (7), Reporting_and_Monitoring (6), Drug_Device_Decision_Guide (6), Start_Here_New_Researchers (5), Preparing_a_Complete_Submission (5) |
| Clinical Research Resources Office | 54 | 35 | Preparing_a_Complete_Submission (3), Training_Requirements (3), Clinical_Trials (3), Drugs_and_Devices (3), Drug_Device_Decision_Guide (3), Contact_and_About (3), Application_Section_Tips (2), Eligibility_and_Study_Design (2) |
| Boston HealthNet | 48 | 15 | Working_with_Other_Institutions (11), Community_Engaged_Research (8), Example_Amendment_and_Stipulation_Response (6), Study_Team_Members (3), Recruitment_and_Screening (3), Glossary_A_to_Z (3), Chart_Review (2), Training_Requirements (2) |
| Clinical Trial Office | 42 | 22 | Paying_Participants (6), Consent_Language_Bank (5), Preparing_a_Complete_Submission (3), Drugs_and_Devices (3), Expanded_Access_Emergency_Use (3), Ceding_Review (3), Expedited_and_Full_Board_Review (2), Ancillary_Reviews_Sign_Offs (2) |
| OHRA | 27 | 12 | Training_Requirements (7), ClinicalTrials_gov (6), Policies_and_Regulations (3), Application_Section_Tips (2), Glossary_A_to_Z (2), Start_Here_New_Researchers (1), Preparing_a_Complete_Submission (1), INSPIR_Task_Records_and_Training (1) |
| Privacy Officer | 21 | 8 | Case_Reports (6), Example_Expedited_Interview_Study (3), Consent_Language_Bank (3), Review_Path_Decision_Tool_v3 (2), HIPAA_in_Research (2), Data_Security_for_Researchers (2), Social_Media_Internet_Research (2), Ancillary_Reviews_Sign_Offs (1) |
| CTO | 19 | 5 | Paying_Participants (11), Clinical_Trials (4), Ancillary_Reviews_Sign_Offs (2), Expanded_Access_Emergency_Use (1), Glossary_A_to_Z (1) |
| Information Security | 16 | 5 | AI_in_Research (5), Social_Media_Internet_Research (4), Remote_Decentralized_Research (3), Data_Security_for_Researchers (3), Ancillary_Reviews_Sign_Offs (1) |
| Privacy Office | 9 | 6 | HIPAA_in_Research (3), Data_Security_for_Researchers (2), Case_Reports (1), Example_Exempt_Chart_Review (1), HIPAA_Waiver_Sample_Answers (1), Data_Retention (1) |
| Institutional Biosafety Committee | 9 | 7 | Ancillary_Reviews_Sign_Offs (2), IRB_Review_Times (2), Preparing_a_Complete_Submission (1), INSPIR_Task_Access_and_New_Study (1), Timelines_and_JIT (1), Reporting_and_Monitoring (1), Glossary_A_to_Z (1) |
| Office of Research | 9 | 7 | Conflict_of_Interest (3), Short_Form_Consent_Process (1), Data_Retention (1), Data_Sharing (1), Community_Engaged_Research (1), Announcements (1), Policies_and_Regulations (1) |
| Office of Sponsored Programs | 7 | 3 | Consent_Language_Bank (5), Drugs_and_Devices (1), Ceding_Review (1) |
| IBC | 6 | 2 | Ancillary_Reviews_Sign_Offs (5), Glossary_A_to_Z (1) |
| Radiation Safety Committee | 6 | 3 | Radiation_in_Research (4), Consent_Templates (1), Consent_Language_Bank (1) |
| Office of Human Research Affairs | 5 | 4 | Policies_and_Regulations (2), Start_Here_New_Researchers (1), ClinicalTrials_gov (1), Glossary_A_to_Z (1) |
| Research Compliance | 5 | 2 | Conflict_of_Interest (3), International_Research (2) |
| Research Operations | 2 | 1 | Paying_Participants (2) |
| Sponsored Programs | 1 | 1 | Ancillary_Reviews_Sign_Offs (1) |
| Cancer Center | 1 | 1 | Ancillary_Reviews_Sign_Offs (1) |
| Investigational Drug Service | 1 | 1 | IRB_Review_Times (1) |

---

## Appendix B. Policy and regulatory references: every occurrence

893 rows. "Location" is the nearest preceding heading in the page. Rows tagged "[link]" are hyperlinks to the HRPP policies page with a section anchor. Context is ±70 characters of surrounding text. Correctness not judged.

| # | Page | Location (section) | Exact reference text | Context |
|---|---|---|---|---|
| 1 | IRB_Home | Is this the right IRB for my study? | HRPP 7.2.2.2 | …ome institution, because some special routing sign-offs depend on it (HRPP 7.2.2.2, revised July 20, 2026). Not sure which yours is? Look up a PI's ho… |
| 2 | Hub_Before_You_Submit | Training Requirements | GCP | …roval. Check who to list ### Training Requirements Human subjects and GCP training your team needs before approval. Check training requirements… |
| 3 | Start_Here_New_Researchers | Your first 90 days at a glance | GCP | … access \| \| Weeks 1 to 2 \| 3. Complete required training in CITI (and GCP if you work on clinical trials) \| Training Requirements for Study Tea… |
| 4 | Start_Here_New_Researchers | First things first: do you need IRB review? | 45 CFR 46.102 | …hat looks like research needs IRB oversight. Under the federal rules (45 CFR 46.102), a project needs IRB review when it is both research and involves… |
| 5 | Start_Here_New_Researchers | Week 1: get set up | GCP | …MC HIPAA and Research Data Security course. - Good Clinical Practice (GCP) training is required for everyone involved in the conduct of clinica… |
| 6 | Start_Here_New_Researchers | Weeks 2 to 6: plan your study | HRPP Policy 7.2.2.20 | …nical trial; or a study that must post results on ClinicalTrials.gov (HRPP Policy 7.2.2.20). See When a separate protocol is required . ## Submit and … |
| 7 | Start_Here_New_Researchers | After approval: your ongoing responsibilities | HRPP 6.6.3.2 and 6.6.5.2 | …ossible, and no later than 7 calendar days after learning about them (HRPP 6.6.3.2 and 6.6.5.2). See Reporting Problems . - Keeping approval current. … |
| 8 | Start_Here_New_Researchers | How to reach us | GCP | …tals training : The starting course for new research staff (satisfies GCP). - PI Role training : The starting course for new PIs (satisfies GCP… |
| 9 | Do_I_Need_IRB_Review | Quality improvement or research? | [link] HRPP Section 10.2.5.2.2 → 10.2.5.2.2 | …(hyperlink to HRPP policies page anchor)… |
| 10 | Do_I_Need_IRB_Review | Quick guide | Exempt category 11 | …letter. \| \| A QI project you also want to analyze as research \| Yes \| Exempt category 11 if there is no external funding; otherwise expedited \| \… |
| 11 | Do_I_Need_IRB_Review | Quick guide | Exempt category 12 | … \| Exempt, category 2 \| \| Surveys or interviews with children \| Yes \| Exempt category 12 without external funding; otherwise expedited \| \| Othe… |
| 12 | Do_I_Need_IRB_Review | Quick guide | Exempt category 13 | …research blood draw, a cheek swab, or text-message reminders) \| Yes \| Exempt category 13 without external funding; otherwise expedited \| \| Researc… |
| 13 | Do_I_Need_IRB_Review | Guidance | 45 CFR 46.102 | … both research and involves human subjects. The federal regulations ( 45 CFR 46.102 ) define them this way: (l) Research means a systematic investigat… |
| 14 | Do_I_Need_IRB_Review | Guidance | HRPP Section 13 | …hose results will be submitted to or held for inspection by, the FDA (HRPP Section 13; 21 CFR 50.3 ). It always needs IRB review, even when it uses le… |
| 15 | Do_I_Need_IRB_Review | Guidance | 21 CFR 50.3 | … be submitted to or held for inspection by, the FDA (HRPP Section 13; 21 CFR 50.3 ). It always needs IRB review, even when it uses leftover or de-iden… |
| 16 | Do_I_Need_IRB_Review | Guidance | 45 CFR 46.102(j) | …formance of routine physical or psychological examinations or tests" (45 CFR 46.102(j)). > Quality improvement or research? A quality improvement (QI)… |
| 17 | Do_I_Need_IRB_Review | Guidance | HRPP Section 10.2.5.2.2 | …roject does not need IRB review if it meets every BMC QI criterion in HRPP Section 10.2.5.2.2 . If it misses any criterion, submit it; unfunded QI pro… |
| 18 | Do_I_Need_IRB_Review | Guidance | HRPP Section 10.2.5.2.3 | …ries with more than three patients is research and must be submitted (HRPP Section 10.2.5.2.3). Authorization templates, who reviews them, and what to… |
| 19 | Do_I_Need_IRB_Review | How to request an NHSR determination in INSPIR | HRPP Section 10.2.4.2 | …ting HIPAA authorization. Exempt categories used by the BMC/BUMC IRB (HRPP Section 10.2.4.2) \| Category \| Covers \| Watch for \| \| 1 \| Normal educ… |
| 20 | Do_I_Need_IRB_Review | When categories 9 to 13 are not available | Common Rule | …FDA-regulated clinical investigation, has a sponsor that requires the Common Rule, or has BMC/BUMC serving as the IRB for an external site. They also … |
| 21 | Do_I_Need_IRB_Review | When categories 9 to 13 are not available | HRPP Section 2.4 | …btain identifiable private information or specimens for the research (HRPP Section 2.4). It is not engaged if, for example, your team only tells peopl… |
| 22 | Do_I_Need_IRB_Review | Related links | Sections 2.1.2, 2.4, 10.2.2, 10.2.4, 10.2.5, 10.2.6 | …ormation Sheet) - Amendments - BMC/BUMC HRPP Policies and Procedures (Sections 2.1.2, 2.4, 10.2.2, 10.2.4, 10.2.5, 10.2.6) - 45 CFR 46.104, federal ex… |
| 23 | Do_I_Need_IRB_Review | Related links | 45 CFR 46.104 | …nd Procedures (Sections 2.1.2, 2.4, 10.2.2, 10.2.4, 10.2.5, 10.2.6) - 45 CFR 46.104, federal exempt categories (eCFR) - What is "Exempt" Human Subject… |
| 24 | Quality_Improvement_or_Research | Self-check: the BMC QI checklist | [link] HRPP Section 10.2.5.2.2 → 10.2.5.2.2 | …(hyperlink to HRPP policies page anchor)… |
| 25 | Quality_Improvement_or_Research | Self-check: the BMC QI checklist | HRPP Section 10.2.5.2.2 | …is the BMC QI IRB Checklist (Word) , which follows the QI criteria in HRPP Section 10.2.5.2.2 . Answer both parts. Part 1: for QI, every answer must b… |
| 26 | Quality_Improvement_or_Research | Self-check: the BMC QI checklist | Part 2 | …akes place, with staff or patients of BMC or the BU dental clinics? \| Part 2: for QI, every answer must be No (any Yes means submit to the IRB) \| … |
| 27 | Quality_Improvement_or_Research | What your answers mean | Part 2 | …wers \| What it means \| What to do \| \| All Yes in Part 1 and all No in Part 2 \| QI, not research \| No IRB submission. Keep all PHI on HIPAA-compl… |
| 28 | Quality_Improvement_or_Research | More detail | HRPP 10.2.4.2.2.2 | …t of a substance use disorder clinic), it may fit exempt category 11 (HRPP 10.2.4.2.2.2). Category 11 needs abbreviated consent from people, including… |
| 29 | Quality_Improvement_or_Research | More detail | HRPP 10.2.4.3 | …ups, or training, but not from patients affected by the intervention (HRPP 10.2.4.3). Otherwise see Do I Need IRB Review? > Publishing and presenting … |
| 30 | Quality_Improvement_or_Research | More detail | HRPP 10.2.5.2.2 | …ly supervised by the Institutional Review Board per their policies." (HRPP 10.2.5.2.2) With an NHSR letter, never say the IRB "approved" the project o… |
| 31 | Quality_Improvement_or_Research | More detail | HRPP 10.2.5.4 | …letter, never say the IRB "approved" the project or "waived consent" (HRPP 10.2.5.4). > Common reasons for stipulations - Answering "not research" in … |
| 32 | Quality_Improvement_or_Research | Related links | Exempt category 11 | … - Examples: NHSR and QI Requests - INSPIR: choose your review path - Exempt category 11 tip sheet - Exempt Research - Exempt Category Tip Sheets - Re… |
| 33 | Case_Reports | Case Reports and Case Series | HRPP 10.2.5.2.3 | …tients is research and must be submitted to the IRB before you start (HRPP 10.2.5.2.3). No IRB review does not mean no HIPAA. For one to three patient… |
| 34 | Case_Reports | Quick guide | HRPP 10.2.5.2.3 | …designed to contribute to generalizable knowledge, which is research (HRPP 10.2.5.2.3). Know your number before you write. If you might include more t… |
| 35 | Review_Path_Decision_Tool_v3.html | [Decision tool logic text: questions, options, outcomes] | Equivalent Protections Exempt categories | …study does not have external funding and fits into one or more of the Equivalent Protections Exempt categories. - (/section41/none/text) None of the a… |
| 36 | Review_Path_Decision_Tool_v3.html | [Decision tool logic text: questions, options, outcomes] | 45 CFR 164.514(b) | …and town names, medical record numbers, and the other items listed in 45 CFR 164.514(b). Data can contain HIPAA identifiers even when you cannot ident… |
| 37 | Review_Path_Decision_Tool_v3.html | [Decision tool logic text: questions, options, outcomes] | HRPP 10.2.4.2.1.2 and 10.2.4.2.2.2 | … not a focus - (/questions[11]/options[1]/note/text) BMC/BUMC policy (HRPP 10.2.4.2.1.2 and 10.2.4.2.2.2) lets research that only incidentally include… |
| 38 | Review_Path_Decision_Tool_v3.html | [Decision tool logic text: questions, options, outcomes] | HRPP 10.2.4.2.2.2 | …er13[0]/why) Category 13 cannot include prisoners, even incidentally (HRPP 10.2.4.2.2.2). - (/methodRules/other13[1]/why) Category 13 is only for adul… |
| 39 | Review_Path_Decision_Tool_v3.html | [Decision tool logic text: questions, options, outcomes] | HRPP Section 2.1.2 | …Rules/other13[4]/why) Something will be billed through clinical care; HRPP Section 2.1.2 lists use of clinical services as a reason categories 9 to 13… |
| 40 | Review_Path_Decision_Tool_v3.html | [Decision tool logic text: questions, options, outcomes] | HRPP Section 10.2.5.2.2 | …mprovement or quality assurance project that meets every criterion in HRPP Section 10.2.5.2.2 is not research and does not need IRB review. - (/result… |
| 41 | Review_Path_Decision_Tool_v3.html | [Decision tool logic text: questions, options, outcomes] | HRPP Section 10.2.5.2.3 | …/why) A case report describing one to three patients is not research (HRPP Section 10.2.5.2.3). A case series of four or more patients is research and… |
| 42 | Review_Path_Decision_Tool_v3.html | [Decision tool logic text: questions, options, outcomes] | 21 CFR 56.104(c) | …ps[0]) Submit this report within 5 working days of the emergency use (21 CFR 56.104(c); HRPP 7.2.2.21). Any later use of the product at BMC/BUMC needs… |
| 43 | Review_Path_Decision_Tool_v3.html | [Decision tool logic text: questions, options, outcomes] | HRPP 7.2.2.21 | … report within 5 working days of the emergency use (21 CFR 56.104(c); HRPP 7.2.2.21). Any later use of the product at BMC/BUMC needs IRB review first.… |
| 44 | Review_Path_Decision_Tool_v3.html | [Decision tool logic text: questions, options, outcomes] | 21 CFR 312.310 | …ication for an FDA approved Individual patient (single use) IND under 21 CFR 312.310?" - (/results/R_SPIND/why) An individual patient IND is not a Rev… |
| 45 | Review_Path_Decision_Tool_v3.html | [Decision tool logic text: questions, options, outcomes] | 21 CFR 814 | …Is this application for an FDA approved Humanitarian Use Device under 21 CFR 814?" - (/results/R_HUD/why) A Humanitarian Use Device is not a Review Pa… |
| 46 | Review_Path_Decision_Tool_v3.html | [Decision tool logic text: questions, options, outcomes] | AAHRPP | …RB qualifies. Greater than minimal risk research needs an IRB that is AAHRPP-accredited (or in the process); for minimal risk research, SMART IRB … |
| 47 | Exempt_Research | Exempt Research | HRPP Policy 10.2.4.3 | …ny vulnerable participants, costs to participants, and payment plans (HRPP Policy 10.2.4.3). New exempt submissions are usually quick: counting from t… |
| 48 | Exempt_Research | Guidance | 45 CFR 46.104(d)(6) and 21 | … evaluation or consumer acceptance study that meets the conditions in 45 CFR 46.104(d)(6) and 21 CFR 56.104(d). - Every research activity involving pe… |
| 49 | Exempt_Research | Guidance | 56.104(d) | …nce study that meets the conditions in 45 CFR 46.104(d)(6) and 21 CFR 56.104(d). - Every research activity involving people fits one or more exempt c… |
| 50 | Exempt_Research | Guidance | Common Rule | …wo sets of exempt categories. Categories 1 to 6 come from the federal Common Rule ( 45 CFR 46.104(d) ) and can be used with any funding. Categories 9 … |
| 51 | Exempt_Research | Guidance | 45 CFR 46.104(d) | …mpt categories. Categories 1 to 6 come from the federal Common Rule ( 45 CFR 46.104(d) ) and can be used with any funding. Categories 9 to 13 are loca… |
| 52 | Exempt_Research | Guidance | HRPP Policy 2.1.2 and 10.2.4.2.2.2 | …eated for research with no external funding and no federal oversight (HRPP Policy 2.1.2 and 10.2.4.2.2.2). INSPIR limits categories 9 to 13 to studies… |
| 53 | Exempt_Research | Guidance | HRPP 10.2.4.2.1.2 and 10.2.4.2.2.2 | …Rule categories as long as every activity fits within those two sets (HRPP 10.2.4.2.1.2 and 10.2.4.2.2.2). Exempt categories used by the BMC/BUMC IRB … |
| 54 | Exempt_Research | Guidance | HRPP Policy 10.2.4.2 | …a checklist and examples: see Exempt Category Tip Sheets . Full text: HRPP Policy 10.2.4.2 . > When local categories 9 to 13 are not available Categor… |
| 55 | Exempt_Research | Guidance | HRPP Policy 2.1.2 | …s" to research that has no external funding and no federal oversight (HRPP Policy 2.1.2). They cannot be used when: - The study has any external fundi… |
| 56 | Exempt_Research | Guidance | HRPP Policies 2.1.2 and 10.2.4.1 | … study may need to move to a federal category or to expedited review (HRPP Policies 2.1.2 and 10.2.4.1). > How INSPIR category numbers relate to the f… |
| 57 | Exempt_Research | Guidance | 45 CFR 46.104(d)(1) | …d their source \| INSPIR number \| Source \| \| 1, 5, 6 \| Same as federal 45 CFR 46.104(d)(1), (d)(5), and (d)(6) \| \| 2.1 \| Federal (d)(2)(i): inf… |
| 58 | Exempt_Research | Guidance | HRPP Policy 10.2.4.2.2.2 | …eans now. \| \| 9 to 13 \| Local categories with no federal counterpart (HRPP Policy 10.2.4.2.2.2). \| > Limited IRB review Categories 2.2 and 3.2 nee… |
| 59 | Exempt_Research | Guidance | HRPP Policy 10.2.4.4 | … the privacy and confidentiality answers already in your application (HRPP Policy 10.2.4.4). Describe: - What identifiers you collect and why, includi… |
| 60 | Exempt_Research | Guidance | HRPP 10.2.4.2.1.2 | …opulation and only incidentally includes people who are incarcerated (HRPP 10.2.4.2.1.2). Of the local categories, 9, 10, and 11 can include prisoners… |
| 61 | Exempt_Research | Guidance | HRPP 10.2.4.2.2.2 | …identally in the same way; 12 and 13 cannot include prisoners at all (HRPP 10.2.4.2.2.2). Data about people collected while they were incarcerated may… |
| 62 | Exempt_Research | Guidance | HRPP Policy 10.2.4.3 | …on with participants, BMC/BUMC policy requires "abbreviated consent" (HRPP Policy 10.2.4.3). It must tell people: - that this is research and that tak… |
| 63 | Exempt_Research | Guidance | Equivalent Protections Exempt categories | …study does not have external funding and fits into one or more of the Equivalent Protections Exempt categories."), then click "Save and Continue to Ne… |
| 64 | Exempt_Research | Guidance | HRPP Policy 7.2.2.19 | …rmed only from the current printouts] Your submission should include (HRPP Policy 7.2.2.19): - Every exempt category that applies. Category 13 usually… |
| 65 | Exempt_Research | Guidance | HRPP Policy 10.2.4.1 | …tion or new kind of procedure, or new relying sites or investigators (HRPP Policy 10.2.4.1). Smaller changes need no amendment; describe them at your … |
| 66 | Exempt_Research | Related links | Sections 2.1.2, 7.2.2.19, 10.2.4 | … Close an Exempt Study (PDF) - BMC/BUMC HRPP Policies and Procedures (Sections 2.1.2, 7.2.2.19, 10.2.4) - 45 CFR 46.104, federal exempt categories (eC… |
| 67 | Exempt_Research | Related links | 45 CFR 46.104 | …UMC HRPP Policies and Procedures (Sections 2.1.2, 7.2.2.19, 10.2.4) - 45 CFR 46.104, federal exempt categories (eCFR) - What is "Exempt" Human Subject… |
| 68 | Exempt_Tip_1 |  | Exempt Category 1 | …# Exempt Category 1: Educational Research Category 1 covers research on ordinary teaching… |
| 69 | Exempt_Tip_1 | It does not fit when | HRPP 10.2.4.2.1.2 and 10.2.4.2.2.2 | …d local categories 9, 10, and 11) can include prisoners incidentally (HRPP 10.2.4.2.1.2 and 10.2.4.2.2.2). ## Examples Studies that fit category 1, an… |
| 70 | Exempt_Tip_1 | Details | HRPP 10.2.4.3 | …reviated consent information and a simple way to opt their child out (HRPP 10.2.4.3). You can adapt the Parent Permission Exempt Information Sheet (Wo… |
| 71 | Exempt_Tip_1 | Details | FERPA | …Schools may have their own approval process for student records under FERPA. [UNVERIFIED: no local FERPA guidance; confirm whether to mention it]… |
| 72 | Exempt_Tip_1 | Related links | Sections 10.2.4.2.1.2 and 10.2.4.3 | …Surveys, Interviews, and Focus Groups - HRPP Policies and Procedures (Sections 10.2.4.2.1.2 and 10.2.4.3) Was this page helpful? Yes / No. Tell us wha… |
| 73 | Exempt_Tip_2-1 |  | Exempt Category 2.1 | …# Exempt Category 2.1: Anonymous surveys/interviews/focus groups Category 2.1 covers resear… |
| 74 | Exempt_Tip_2-1 | It does not fit when | HRPP 10.2.4.2.1.2 and 10.2.4.2.2.2 | …d local categories 9, 10, and 11) can include prisoners incidentally (HRPP 10.2.4.2.1.2 and 10.2.4.2.2.2). ## Examples Studies that fit category 2.1, … |
| 75 | Exempt_Tip_2-1 | Related links | Sections 10.2.4.2.1.2 and 10.2.4.3 | …sheet - Data Security for Researchers - HRPP Policies and Procedures (Sections 10.2.4.2.1.2 and 10.2.4.3) Was this page helpful? Yes / No. Tell us wha… |
| 76 | Exempt_Tip_2-2 |  | Exempt Category 2.2 | …# Exempt Category 2.2: Identifiable surveys/interviews/focus groups Category 2.2 covers the… |
| 77 | Exempt_Tip_2-2 | It does not fit when | HRPP 10.2.4.2.1.2 and 10.2.4.2.2.2 | …d local categories 9, 10, and 11) can include prisoners incidentally (HRPP 10.2.4.2.1.2 and 10.2.4.2.2.2). ## Examples Studies that fit category 2.2, … |
| 78 | Exempt_Tip_2-2 | Details | HRPP 10.2.4.4 | …dentiality protections from your Privacy and Confidentiality answers (HRPP 10.2.4.4); you do not request it separately. Name the identifiers and why y… |
| 79 | Exempt_Tip_2-2 | Related links | Sections 10.2.4.2.1.2, 10.2.4.3 and 10.2.4.4 | …ory 2.1 tip sheet - HIPAA in Research - HRPP Policies and Procedures (Sections 10.2.4.2.1.2, 10.2.4.3 and 10.2.4.4) Was this page helpful? Yes / No. T… |
| 80 | Exempt_Tip_3-1 |  | Exempt Category 3.1 | …# Exempt Category 3.1: Anonymous behavioral research Category 3.1 covers short, harmless be… |
| 81 | Exempt_Tip_3-1 | It does not fit when | HRPP 10.2.4.2.1.2 and 10.2.4.2.2.2 | …d local categories 9, 10, and 11) can include prisoners incidentally (HRPP 10.2.4.2.1.2 and 10.2.4.2.2.2). ## Examples Studies that fit category 3.1, … |
| 82 | Exempt_Tip_3-1 | Details | HRPP 10.2.4.3 | …ing they may be misled about the purpose, and be debriefed afterward (HRPP 10.2.4.3). See Deception and Incomplete Disclosure . > What to attach and w… |
| 83 | Exempt_Tip_3-1 | Related links | Sections 10.2.4.2.1.2 and 10.2.4.3 | …- Deception and Incomplete Disclosure - HRPP Policies and Procedures (Sections 10.2.4.2.1.2 and 10.2.4.3) Was this page helpful? Yes / No. Tell us wha… |
| 84 | Exempt_Tip_3-2 |  | Exempt Category 3.2 | …# Exempt Category 3.2: Identifiable behavioral research Category 3.2 covers the same short,… |
| 85 | Exempt_Tip_3-2 | It does not fit when | HRPP 10.2.4.2.1.2 and 10.2.4.2.2.2 | …d local categories 9, 10, and 11) can include prisoners incidentally (HRPP 10.2.4.2.1.2 and 10.2.4.2.2.2). ## Examples Studies that fit category 3.2, … |
| 86 | Exempt_Tip_3-2 | Details | HRPP 10.2.4.4 | …nated reviewer confirms your privacy and confidentiality protections (HRPP 10.2.4.4) using your Privacy and Confidentiality answers: what you record, … |
| 87 | Exempt_Tip_3-2 | Details | HRPP 10.2.4.3 | …may be unaware of or misled about the purpose, and must be debriefed (HRPP 10.2.4.3). See Deception and Incomplete Disclosure . > What to attach and w… |
| 88 | Exempt_Tip_3-2 | Related links | Sections 10.2.4.2.1.2, 10.2.4.3 and 10.2.4.4 | …sheet - Data Security for Researchers - HRPP Policies and Procedures (Sections 10.2.4.2.1.2, 10.2.4.3 and 10.2.4.4) Was this page helpful? Yes / No. T… |
| 89 | Exempt_Tip_4 |  | Exempt Category 4 | …# Exempt Category 4: Anonymous secondary use of data/specimens Category 4 covers research… |
| 90 | Exempt_Tip_4 | It fits when | HRPP 10.2.4.2.1.2 | …ader population. Research that focuses on prisoners cannot be exempt (HRPP 10.2.4.2.1.2). ### It does not fit when - You keep a list of record numbers… |
| 91 | Exempt_Tip_4 | Related links | Sections 10.2.4.2.1.2 and 8.5.2.2 | …AA in Research - Category 9 tip sheet - HRPP Policies and Procedures (Sections 10.2.4.2.1.2 and 8.5.2.2) Was this page helpful? Yes / No. Tell us what… |
| 92 | Exempt_Tip_5 |  | Exempt Category 5 | …# Exempt Category 5: Federal research Category 5 covers research and demonstration projec… |
| 93 | Exempt_Tip_5 | It does not fit when | HRPP 10.2.4.2.1.2 and 10.2.4.2.2.2 | …d local categories 9, 10, and 11) can include prisoners incidentally (HRPP 10.2.4.2.1.2 and 10.2.4.2.2.2). ## Examples Studies that fit category 5, an… |
| 94 | Exempt_Tip_5 | Related links | Section 10.2.4.2.1.2 | …ew? - INSPIR: choose your review path - HRPP Policies and Procedures (Section 10.2.4.2.1.2) Was this page helpful? Yes / No. Tell us what was missing.… |
| 95 | Exempt_Tip_6 |  | Exempt Category 6 | …# Exempt Category 6: Food research Category 6 covers taste and food quality evaluations a… |
| 96 | Exempt_Tip_6 | It does not fit when | HRPP 10.2.4.2.1.2 and 10.2.4.2.2.2 | …d local categories 9, 10, and 11) can include prisoners incidentally (HRPP 10.2.4.2.1.2 and 10.2.4.2.2.2). ## Examples Studies that fit category 6, an… |
| 97 | Exempt_Tip_6 | Related links | Section 10.2.4.2.1.2 | … your review path - Drugs and Devices - HRPP Policies and Procedures (Section 10.2.4.2.1.2) Was this page helpful? Yes / No. Tell us what was missing.… |
| 98 | Exempt_Tip_9 |  | Exempt Category 9 | …# Exempt Category 9: Identifiable use of non-research data/specimens Category 9 is a loca… |
| 99 | Exempt_Tip_9 | Examples | 42 CFR Part 2 | … 4 if you record no identifiers and keep no key, otherwise expedited. 42 CFR Part 2 rules also apply. \| Common mistake. Treating the HIPAA section as… |
| 100 | Exempt_Tip_9 | Related links | Sections 2.1.2, 10.2.4.2.2.2 and 10.2.4.3 | … - HIPAA in Research - Data Retention - HRPP Policies and Procedures (Sections 2.1.2, 10.2.4.2.2.2 and 10.2.4.3) Was this page helpful? Yes / No. Tell… |
| 101 | Exempt_Tip_10 |  | Exempt Category 10 | …# Exempt Category 10: Identifiable use of existing research data/specimens Category 10 is … |
| 102 | Exempt_Tip_10 | It does not fit when | HRPP 10.2.4.2.2.2 | …nly incidentally, when the research is aimed at a broader population (HRPP 10.2.4.2.2.2). ## Examples Studies that fit category 10, and near misses \|… |
| 103 | Exempt_Tip_10 | Related links | Sections 2.1.2 and 10.2.4.2.2.2 | …etics, Biospecimens, and Repositories - HRPP Policies and Procedures (Sections 2.1.2 and 10.2.4.2.2.2) Was this page helpful? Yes / No. Tell us what w… |
| 104 | Exempt_Tip_11 |  | Exempt Category 11 | …# Exempt Category 11: Quality Improvement research Category 11 is a local category for a q… |
| 105 | Exempt_Tip_11 | It does not fit when | HRPP 10.2.4.2.2.2 | …cidentally, when the change is aimed at a broader patient population (HRPP 10.2.4.2.2.2). ## Examples Studies that fit category 11, and near misses \|… |
| 106 | Exempt_Tip_11 | Details | HRPP 10.2.4.3 | … staff in research interviews, focus groups, surveys, or training do (HRPP 10.2.4.3). If a QI survey is required, make research use of answers optiona… |
| 107 | Exempt_Tip_11 | Related links | Sections 2.1.2, 10.2.4.2.2.2 and 10.2.4.3 | …ew and Secondary Use of Existing Data - HRPP Policies and Procedures (Sections 2.1.2, 10.2.4.2.2.2 and 10.2.4.3) Was this page helpful? Yes / No. Tell… |
| 108 | Exempt_Tip_12 |  | Exempt Category 12 | …# Exempt Category 12: Surveys/interviews with children Category 12 is a local category for… |
| 109 | Exempt_Tip_12 | It does not fit when | HRPP 10.2.4.2.2.2 | … Prisoners are included. Category 12 cannot include prisoners at all (HRPP 10.2.4.2.2.2). ## Examples Studies that fit category 12, and near misses \|… |
| 110 | Exempt_Tip_12 | Related links | Sections 2.1.2, 10.2.4.2.2.2 and 10.2.4.3 | …dited; includes model assent scripts) - HRPP Policies and Procedures (Sections 2.1.2, 10.2.4.2.2.2 and 10.2.4.3) Was this page helpful? Yes / No. Tell… |
| 111 | Exempt_Tip_13 |  | Exempt Category 13 | …# Exempt Category 13: Minimal Risk Research with Adults Category 13 is a local catch-all f… |
| 112 | Exempt_Tip_13 | It does not fit when | HRPP 10.2.4.2.2.2 | …selves. Category 13 also cannot include prisoners, even incidentally (HRPP 10.2.4.2.2.2). - The study has external funding: use a federal category if … |
| 113 | Exempt_Tip_13 | Examples | Expedited Category 2 | …eviewed as exempt category 13 or as expedited, usually expedited (see Expedited Category 2 (blood draws) and Expedited Category 4 (noninvasive procedu… |
| 114 | Exempt_Tip_13 | Examples | Expedited Category 4 | …edited, usually expedited (see Expedited Category 2 (blood draws) and Expedited Category 4 (noninvasive procedures such as MRI) ). Exempt category 13 … |
| 115 | Exempt_Tip_13 | Examples | Exempt category 13 | …aws) and Expedited Category 4 (noninvasive procedures such as MRI) ). Exempt category 13 is now available for more of them and will be used more often… |
| 116 | Exempt_Tip_13 | Details | HRPP 10.2.4.3 | …on Deception must be disclosed in advance and followed by debriefing (HRPP 10.2.4.3). Keeping data or samples for extra use is allowed: answer the Sam… |
| 117 | Exempt_Tip_13 | Related links | Sections 2.1.2, 10.2.4.2.2.2 and 10.2.4.3 | …g Consent - Recruitment and Screening - HRPP Policies and Procedures (Sections 2.1.2, 10.2.4.2.2.2 and 10.2.4.3) Was this page helpful? Yes / No. Tell… |
| 118 | Expedited_and_Full_Board_Review | Guidance | 45 CFR 46.110 | …ate no more than one year out; continuing review before it \| Sources: 45 CFR 46.110; HRPP Policies 10.2 to 10.4. > What minimal risk means "Minimal r… |
| 119 | Expedited_and_Full_Board_Review | Guidance | HRPP Policies 10.2 to 10.4 | …n one year out; continuing review before it \| Sources: 45 CFR 46.110; HRPP Policies 10.2 to 10.4. > What minimal risk means "Minimal risk means that … |
| 120 | Expedited_and_Full_Board_Review | Guidance | 45 CFR 46.102(j) | …rmance of routine physical or psychological examinations or tests." ( 45 CFR 46.102(j) ) The IRB weighs the risks your research adds, not the risks of… |
| 121 | Expedited_and_Full_Board_Review | Guidance | HRPP Policy 10.2.2.4.1.1 | …inimal risk only if your protections bring that risk down to minimal (HRPP Policy 10.2.2.4.1.1). Being on the expedited list does not make an activity… |
| 122 | Expedited_and_Full_Board_Review | Guidance | Common Rule | …g grants; not FDA-regulated; and no sponsor requirement to follow the Common Rule; see HRPP Policy 2.1.2 for the full list) can also be expedited for … |
| 123 | Expedited_and_Full_Board_Review | Guidance | HRPP Policy 2.1.2 | …-regulated; and no sponsor requirement to follow the Common Rule; see HRPP Policy 2.1.2 for the full list) can also be expedited for draws through an … |
| 124 | Expedited_and_Full_Board_Review | Guidance | HRPP Policy 10.2.2.4.1.3 | … procedure, and one research x-ray of no more than 0.1 mSv in adults (HRPP Policy 10.2.2.4.1.3). For these studies the category 2 volume limits still … |
| 125 | Expedited_and_Full_Board_Review | Guidance | HRPP Policy 9.3.4 | …representative must be present at a convened meeting for that review (HRPP Policy 9.3.4). - The expedited reviewer refers it to the board for more exp… |
| 126 | Expedited_and_Full_Board_Review | Guidance | HRPP Policy 10.2.1.6 | …hose only purpose is to set up a repository may also go to the board (HRPP Policy 10.2.1.6). > How expedited review works After IRB staff check that y… |
| 127 | Expedited_and_Full_Board_Review | Guidance | HRPP Policy 10.2.2.1 | … experienced, based on board service, training, and mentored reviews (HRPP Policy 10.2.2.1). The reviewer applies the same approval criteria the board… |
| 128 | Expedited_and_Full_Board_Review | Guidance | HRPP Policy 7.3.3 | …nical Engineering, are routed to them at the same time as IRB review (HRPP Policy 7.3.3), and the IRB needs their sign-off before approval. > Board me… |
| 129 | Expedited_and_Full_Board_Review | Guidance | HRPP Policies 3.1 and 10.2.1.7 | … consent templates, and does not routinely review individual studies (HRPP Policies 3.1 and 10.2.1.7). Each panel includes scientists, at least one no… |
| 130 | Expedited_and_Full_Board_Review | Guidance | HRPP Policy 5.2 | … on Thursdays. The IRB Director sets the schedule each academic year (HRPP Policy 5.2). [CHECK: meeting time and Zoom format] No submission deadlines.… |
| 131 | Expedited_and_Full_Board_Review | Guidance | HRPP Policy 10.2.1.2 | …an investigator-initiated trial that has not had outside peer review (HRPP Policy 10.2.1.2). The IRB often invites the PI, and sometimes other team me… |
| 132 | Expedited_and_Full_Board_Review | Guidance | HRPP Policy 5.5 | … will be asked to leave before the board's final discussion and vote (HRPP Policy 5.5). Members with a conflict of interest also leave. If you have no… |
| 133 | Expedited_and_Full_Board_Review | Guidance | HRPP Policy 10.5.1 | … receive the decision in INSPIR within 5 working days of the meeting (HRPP Policy 10.5.1). > Possible outcomes Board decisions and what you do next \|… |
| 134 | Expedited_and_Full_Board_Review | Guidance | HRPP 10.3.2.3 | …h no deadline in the policy. The study returns to a convened meeting (HRPP 10.3.2.3). \| \| Disapproved \| Problems so serious the study must be redes… |
| 135 | Expedited_and_Full_Board_Review | Guidance | HRPP Policies 10.3.2.3 and 10.3.2.4 | …g through INSPIR, and you may ask to appear before the IRB. \| Source: HRPP Policies 10.3.2.3 and 10.3.2.4. If the IRB suspends or terminates approval… |
| 136 | Expedited_and_Full_Board_Review | Guidance | HRPP 11.5 | …ates approval, you may appeal in writing to the Chair within 30 days (HRPP 11.5). For how to answer stipulations and how long you have, see Respondin… |
| 137 | Expedited_and_Full_Board_Review | Guidance | HRPP Policy 10.4.1.4 | …can usually move to no expiration date at its next continuing review (HRPP Policy 10.4.1.4). The board may set a shorter period for a study with an ex… |
| 138 | Expedited_and_Full_Board_Review | Guidance | HRPP Policy 10.4.1 | …example for Phase I trials, gene transfer, or higher-risk procedures (HRPP Policy 10.4.1). For what to submit and when, see Continuing review, status … |
| 139 | Expedited_and_Full_Board_Review | Guidance | HRPP 12.2.4.1 | …he IRB decides at a convened meeting whether to accept the NSR claim (HRPP 12.2.4.1). The IRB does not make FDA determinations; only the FDA does. A s… |
| 140 | Expedited_and_Full_Board_Review | Related links | 45 CFR 46.110 | …BUMC HRPP Policies and Procedures (Sections 3, 5, 10.2, 10.3, 10.4) - 45 CFR 46.110, expedited review (eCFR) - Categories of research that may be revi… |
| 141 | Expedited_Tip_1 |  | Expedited Category 1 | …# Expedited Category 1: Drugs and devices Category 1 covers minimal risk studies of drugs th… |
| 142 | Expedited_Tip_1 | Expedited Category 1: Drugs and devices | HRPP 10.2.2.4.1.2 | …cation. See Expedited and Full Board Review . The category text. From HRPP 10.2.2.4.1.2 and the 1998 federal list (63 FR 60364): "Clinical studies of … |
| 143 | Expedited_Tip_1 | Expedited Category 1: Drugs and devices | 21 CFR Part 312 | … Research on drugs for which an investigational new drug application (21 CFR Part 312) is not required. (Note: Research on marketed drugs that signifi… |
| 144 | Expedited_Tip_1 | Expedited Category 1: Drugs and devices | 21 CFR Part 812 | …evices for which (i) an investigational device exemption application (21 CFR Part 812) is not required; or (ii) the medical device is cleared/approved… |
| 145 | Expedited_Tip_1 | Does your study fit? | 21 CFR 812.2(c) | …dy does not make it riskier. The device is exempt from the IDE rules (21 CFR 812.2(c)), for example because it is cleared or approved and used within … |
| 146 | Expedited_Tip_1 | Does your study fit? | HRPP 12.2.4.1 | …iated IDE). The board makes that determination at a convened meeting (HRPP 12.2.4.1). \| ## Examples Studies that fit category 1, and near misses \| S… |
| 147 | Expedited_Tip_1 | Details | 45 CFR 46.102(j) | …ormance of routine physical or psychological examinations or tests." (45 CFR 46.102(j)) Being on the list does not make an activity minimal risk; the … |
| 148 | Expedited_Tip_1 | Details | HRPP 10.2.2.4.1.1 | …harm them, your privacy protections must reduce that risk to minimal (HRPP 10.2.2.4.1.1). > What to attach Drugs: package insert and your IND exemptio… |
| 149 | Expedited_Tip_1 | Details | HRPP 12.2.4.1 | …fication; the IRB decides at a convened meeting whether to accept it, HRPP 12.2.4.1.) Also a protocol if required ( Protocol Template (Word) ), a cons… |
| 150 | Expedited_Tip_1 | Related links | Sections 10.2.2.4.1.1 and 10.2.2.4.1.2 | …d an IND or IDE? - ClinicalTrials.gov - HRPP Policies and Procedures (Sections 10.2.2.4.1.1 and 10.2.2.4.1.2) Was this page helpful? Yes / No. Tell us… |
| 151 | Expedited_Tip_2 |  | Expedited Category 2 | …# Expedited Category 2: Blood draws Category 2 covers research blood drawn by finger, heel, … |
| 152 | Expedited_Tip_2 | Expedited Category 2: Blood draws | HRPP 10.2.2.4.1.2 | …cation. See Expedited and Full Board Review . The category text. From HRPP 10.2.2.4.1.2 and the 1998 federal list (63 FR 60364): "Collection of blood … |
| 153 | Expedited_Tip_2 | Examples | Exempt category 13 | … usually been reviewed as expedited, sometimes as exempt category 13. Exempt category 13 is now available for more of these studies and will be used m… |
| 154 | Expedited_Tip_2 | Examples | Exempt Category 13 | … available for more of these studies and will be used more often; see Exempt Category 13 and Expedited Category 4 (noninvasive procedures such as MRI)… |
| 155 | Expedited_Tip_2 | Examples | Expedited Category 4 | …these studies and will be used more often; see Exempt Category 13 and Expedited Category 4 (noninvasive procedures such as MRI) . The IRB decides the … |
| 156 | Expedited_Tip_2 | Details | 45 CFR 46.102(j) | …ormance of routine physical or psychological examinations or tests." (45 CFR 46.102(j)) Being on the list does not make an activity minimal risk; the … |
| 157 | Expedited_Tip_2 | Details | HRPP 10.2.2.4.1.1 | …harm them, your privacy protections must reduce that risk to minimal (HRPP 10.2.2.4.1.1). > Local category 10 (studies without external funding or fed… |
| 158 | Expedited_Tip_2 | Details | HRPP 10.2.2.4.1.3 | …out external funding or federal oversight) Local categories 10 to 12 (HRPP 10.2.2.4.1.3) apply only to minimal risk studies eligible for equivalent pr… |
| 159 | Expedited_Tip_2 | Details | HRPP 2.1.2 | …ply only to minimal risk studies eligible for equivalent protections (HRPP 2.1.2): no external funding of any kind (federal, foundation, industry, or … |
| 160 | Expedited_Tip_2 | Related links | Sections 2.1.2, 10.2.2.4.1.2 and 10.2.2.4.1.3 | …itories - Research Involving Children - HRPP Policies and Procedures (Sections 2.1.2, 10.2.2.4.1.2 and 10.2.2.4.1.3) Was this page helpful? Yes / No. … |
| 161 | Expedited_Tip_3 |  | Expedited Category 3 | …# Expedited Category 3: Noninvasive specimens Category 3 covers new specimens collected for … |
| 162 | Expedited_Tip_3 | Expedited Category 3: Noninvasive specimens | HRPP 10.2.2.4.1.2 | …cation. See Expedited and Full Board Review . The category text. From HRPP 10.2.2.4.1.2 and the 1998 federal list (63 FR 60364): "Prospective collecti… |
| 163 | Expedited_Tip_3 | Details | 45 CFR 46.102(j) | …ormance of routine physical or psychological examinations or tests." (45 CFR 46.102(j)) Being on the list does not make an activity minimal risk; the … |
| 164 | Expedited_Tip_3 | Details | HRPP 10.2.2.4.1.1 | …harm them, your privacy protections must reduce that risk to minimal (HRPP 10.2.2.4.1.1). > Local category 11 (studies without external funding or fed… |
| 165 | Expedited_Tip_3 | Details | HRPP 10.2.2.4.1.3 | …out external funding or federal oversight) Local categories 10 to 12 (HRPP 10.2.2.4.1.3) apply only to minimal risk studies eligible for equivalent pr… |
| 166 | Expedited_Tip_3 | Details | HRPP 2.1.2 | …ply only to minimal risk studies eligible for equivalent protections (HRPP 2.1.2): no external funding of any kind (federal, foundation, industry, or … |
| 167 | Expedited_Tip_3 | Related links | Sections 2.1.2, 10.2.2.4.1.2 and 10.2.2.4.1.3 | …ew and Secondary Use of Existing Data - HRPP Policies and Procedures (Sections 2.1.2, 10.2.2.4.1.2 and 10.2.2.4.1.3) Was this page helpful? Yes / No. … |
| 168 | Expedited_Tip_4 |  | Expedited Category 4 | …# Expedited Category 4: Noninvasive procedures Category 4 covers data from routine, noninvas… |
| 169 | Expedited_Tip_4 | Expedited Category 4: Noninvasive procedures | HRPP 10.2.2.4.1.2 | …cation. See Expedited and Full Board Review . The category text. From HRPP 10.2.2.4.1.2 and the 1998 federal list (63 FR 60364): "Collection of data t… |
| 170 | Expedited_Tip_4 | Examples | Exempt category 13 | … usually been reviewed as expedited, sometimes as exempt category 13. Exempt category 13 is now available for more of these studies and will be used m… |
| 171 | Expedited_Tip_4 | Examples | Exempt Category 13 | … available for more of these studies and will be used more often; see Exempt Category 13 and Expedited Category 2 (blood draws) . The IRB decides the … |
| 172 | Expedited_Tip_4 | Examples | Expedited Category 2 | …these studies and will be used more often; see Exempt Category 13 and Expedited Category 2 (blood draws) . The IRB decides the path from your applicat… |
| 173 | Expedited_Tip_4 | Details | 45 CFR 46.102(j) | …ormance of routine physical or psychological examinations or tests." (45 CFR 46.102(j)) Being on the list does not make an activity minimal risk; the … |
| 174 | Expedited_Tip_4 | Details | HRPP 10.2.2.4.1.1 | …harm them, your privacy protections must reduce that risk to minimal (HRPP 10.2.2.4.1.1). > Local category 12 and research radiation Local categories … |
| 175 | Expedited_Tip_4 | Details | HRPP 10.2.2.4.1.3 | …> Local category 12 and research radiation Local categories 10 to 12 (HRPP 10.2.2.4.1.3) apply only to minimal risk studies eligible for equivalent pr… |
| 176 | Expedited_Tip_4 | Details | HRPP 2.1.2 | …ply only to minimal risk studies eligible for equivalent protections (HRPP 2.1.2): no external funding of any kind (federal, foundation, industry, or … |
| 177 | Expedited_Tip_4 | Related links | Sections 2.1.2, 10.2.2.4.1.2 and 10.2.2.4.1.3 | …ch with Drugs, Biologics, and Devices - HRPP Policies and Procedures (Sections 2.1.2, 10.2.2.4.1.2 and 10.2.2.4.1.3) Was this page helpful? Yes / No. … |
| 178 | Expedited_Tip_5 |  | Expedited Category 5 | …# Expedited Category 5: Existing records and specimens Category 5 covers research on data, r… |
| 179 | Expedited_Tip_5 | Expedited Category 5: Existing records and specimens | HRPP 10.2.2.4.1.2 | …cation. See Expedited and Full Board Review . The category text. From HRPP 10.2.2.4.1.2 and the 1998 federal list (63 FR 60364): "Research involving m… |
| 180 | Expedited_Tip_5 | Does your study fit? | Exempt category 4 | …cted, usually with a HIPAA waiver. \| No identifiers or code recorded. Exempt category 4. Identifiable, no outside funding, and eligible. Exempt local… |
| 181 | Expedited_Tip_5 | Examples | Part 2 | …ligible for exempt 9 (anonymous extraction may fit exempt 4); federal Part 2 rules also apply. \| \| Unfunded review that records no identifiers and… |
| 182 | Expedited_Tip_5 | Examples | Exempt category 4 | …Unfunded review that records no identifiers and keeps no code. \| No \| Exempt category 4. \| \| Unfunded identifiable chart review. \| No \| Usually … |
| 183 | Expedited_Tip_5 | Details | 45 CFR 46.102(j) | …ormance of routine physical or psychological examinations or tests." (45 CFR 46.102(j)) Being on the list does not make an activity minimal risk; the … |
| 184 | Expedited_Tip_5 | Details | HRPP 10.2.2.4.1.1 | …harm them, your privacy protections must reduce that risk to minimal (HRPP 10.2.2.4.1.1). > What to attach The list of data variables (or attach it in… |
| 185 | Expedited_Tip_5 | Related links | Sections 10.2.2.4.1.2 and 10.2.4.2 | …IPAA Waiver Questions: Sample Answers - HRPP Policies and Procedures (Sections 10.2.2.4.1.2 and 10.2.4.2) Was this page helpful? Yes / No. Tell us wha… |
| 186 | Expedited_Tip_6 |  | Expedited Category 6 | …# Expedited Category 6: Recordings Category 6 covers data from voice, video, digital, or ima… |
| 187 | Expedited_Tip_6 | Expedited Category 6: Recordings | HRPP 10.2.2.4.1.2 | …cation. See Expedited and Full Board Review . The category text. From HRPP 10.2.2.4.1.2 and the 1998 federal list (63 FR 60364): "Collection of data f… |
| 188 | Expedited_Tip_6 | Does your study fit? | Exempt category 2 | …whole study is recorded interviews with adults that fit an exemption. Exempt category 2. \| ## Examples Studies that fit category 6, and near misses \… |
| 189 | Expedited_Tip_6 | Details | 45 CFR 46.102(j) | …ormance of routine physical or psychological examinations or tests." (45 CFR 46.102(j)) Being on the list does not make an activity minimal risk; the … |
| 190 | Expedited_Tip_6 | Details | HRPP 10.2.2.4.1.1 | …harm them, your privacy protections must reduce that risk to minimal (HRPP 10.2.2.4.1.1). > What to attach Interview or focus group guides and any pho… |
| 191 | Expedited_Tip_6 | Related links | Exempt Category 2.2 | …rveys, Interviews, and Focus Groups - Data Security for Researchers - Exempt Category 2.2 - HRPP Policies and Procedures (Section 10.2.2.4.1.2) Was th… |
| 192 | Expedited_Tip_6 | Related links | Section 10.2.2.4.1.2 | …for Researchers - Exempt Category 2.2 - HRPP Policies and Procedures (Section 10.2.2.4.1.2) Was this page helpful? Yes / No. Tell us what was missing.… |
| 193 | Expedited_Tip_7 |  | Expedited Category 7 | …# Expedited Category 7: Behavioral and social research Category 7 covers minimal risk behavi… |
| 194 | Expedited_Tip_7 | Expedited Category 7: Behavioral and social research | HRPP 10.2.2.4.1.2 | …cation. See Expedited and Full Board Review . The category text. From HRPP 10.2.2.4.1.2 and the 1998 federal list (63 FR 60364): "Research on individu… |
| 195 | Expedited_Tip_7 | Examples | Exempt category 2.1 | …e intervention. \| \| An anonymous online survey of adult staff. \| No \| Exempt category 2.1. \| \| A new psychotherapy tested in people with recent … |
| 196 | Expedited_Tip_7 | Details | 45 CFR 46.102(j) | …ormance of routine physical or psychological examinations or tests." (45 CFR 46.102(j)) Being on the list does not make an activity minimal risk; the … |
| 197 | Expedited_Tip_7 | Details | HRPP 10.2.2.4.1.1 | …harm them, your privacy protections must reduce that risk to minimal (HRPP 10.2.2.4.1.1). > What to attach Every survey, interview guide, focus group … |
| 198 | Expedited_Tip_7 | Related links | Sections 10.2.2.4.1.1 and 10.2.2.4.1.2 | …tegory Tip Sheets - Obtaining Consent - HRPP Policies and Procedures (Sections 10.2.2.4.1.1 and 10.2.2.4.1.2) Was this page helpful? Yes / No. Tell us… |
| 199 | Expedited_Tip_8 |  | Expedited Category 8 | …# Expedited Category 8: Continuing review of board-approved research Category 8 is used only… |
| 200 | Expedited_Tip_8 | Expedited Category 8: Continuing review of board-approved re | HRPP 10.2.2.4.3.1 | …cation. See Expedited and Full Board Review . The category text. From HRPP 10.2.2.4.3.1 and the 1998 federal list (63 FR 60364): "Continuing review of… |
| 201 | Expedited_Tip_8 | Examples | HRPP Policy 10.4.1 | … every 3 years instead of yearly renewal, unless it is FDA-regulated (HRPP Policy 10.4.1). \| \| A board-approved trial still enrolling. \| No \| Full… |
| 202 | Expedited_Tip_8 | Details | 45 CFR 46.102(j) | …ormance of routine physical or psychological examinations or tests." (45 CFR 46.102(j)) Being on the list does not make an activity minimal risk; the … |
| 203 | Expedited_Tip_8 | Details | HRPP 10.2.2.4.1.1 | …harm them, your privacy protections must reduce that risk to minimal (HRPP 10.2.2.4.1.1). > What to attach The Continuing Review Submission Form, the … |
| 204 | Expedited_Tip_8 | Details | HRPP 10.2.2.4.3.1 | …ion Form, the current consent form, and anything the report asks for. HRPP 10.2.2.4.3.1 says the reviewer receives the study status, enrollment, monit… |
| 205 | Expedited_Tip_8 | Related links | Sections 10.2.2.4.3.1 and 10.4.1 | …tus check-ins, and closing your study - HRPP Policies and Procedures (Sections 10.2.2.4.3.1 and 10.4.1) Was this page helpful? Yes / No. Tell us what … |
| 206 | Expedited_Tip_9 |  | Expedited Category 9 | …# Expedited Category 9: Continuing review of other minimal risk research Category 9 is used … |
| 207 | Expedited_Tip_9 | Expedited Category 9: Continuing review of other minimal ris | HRPP 10.2.2.4.3.1 | …cation. See Expedited and Full Board Review . The category text. From HRPP 10.2.2.4.3.1 and the 1998 federal list (63 FR 60364): "Continuing review of… |
| 208 | Expedited_Tip_9 | Examples | HRPP 10.2.1.6 | … the board reviewed because it was a registry set up as a repository (HRPP 10.2.1.6), with the minimal risk finding in the minutes. \| Yes \| No IND o… |
| 209 | Expedited_Tip_9 | Examples | HRPP 9.3.4 | …w stays at a convened meeting with a prisoner representative present (HRPP 9.3.4). \| Common mistake. Assuming a minimal risk study reviewed by the bo… |
| 210 | Expedited_Tip_9 | Details | 45 CFR 46.102(j) | …ormance of routine physical or psychological examinations or tests." (45 CFR 46.102(j)) Being on the list does not make an activity minimal risk; the … |
| 211 | Expedited_Tip_9 | Details | HRPP 10.2.2.4.1.1 | …harm them, your privacy protections must reduce that risk to minimal (HRPP 10.2.2.4.1.1). > What to attach The Progress Report and current study docum… |
| 212 | Expedited_Tip_9 | Related links | Sections 10.2.2.4.3.1 and 10.4.1 | …dy - IRB Committees and Board Members - HRPP Policies and Procedures (Sections 10.2.2.4.3.1 and 10.4.1) Was this page helpful? Yes / No. Tell us what … |
| 213 | Chart_Review | Guidance | Exempt Category 9 | … activity, is submitted through the exempt option and category 9 (see Exempt Category 9 ). Where the data came from and whether you can identify peopl… |
| 214 | Chart_Review |  | Exempt category 4 | …research, so its data must still come through research channels. #### Exempt category 4 (federal) The criterion most chart reviews rely on is 45 CFR 4… |
| 215 | Chart_Review | Exempt category 4 (federal) | 45 CFR 46.104(d)(4)(ii) | …empt category 4 (federal) The criterion most chart reviews rely on is 45 CFR 46.104(d)(4)(ii) : Information, which may include information about biosp… |
| 216 | Chart_Review | Exempt category 4 (federal) | HRPP 10.2.4.2.1.2 | …is BMC workforce; it still requires the IRB to review a HIPAA waiver (HRPP 10.2.4.2.1.2). #### Local exempt category 9 (no external funding) For minim… |
| 217 | Chart_Review | Local exempt category 9 (no external funding) | HRPP 10.2.4.2.2.2 | …al oversight, BMC and BUMC use " equivalent protections " categories. HRPP 10.2.4.2.2.2 lists: (9) Research involving the study of materials (data, do… |
| 218 | Chart_Review |  | Expedited category 5 | … any external funding (federal, foundation, industry, or other). #### Expedited category 5 Chart reviews that keep identifiers and do not qualify for … |
| 219 | Chart_Review | Expedited category 5 | HRPP 10.2.2.4.1.2 | … exemption are usually approved under expedited category 5, listed in HRPP 10.2.2.4.1.2 as: Research involving materials (data, documents, records, or… |
| 220 | Chart_Review | When it needs more | HRPP 6.6.7.1 | … 7 years after the study ends, or longer if your sponsor requires it (HRPP 6.6.7.1). [PENDING DECISION: master code retention; see Data Security page]… |
| 221 | Chart_Review | When it needs more | HRPP 8.5.2.1 | …a data use agreement with the data holder rather than a HIPAA waiver (HRPP 8.5.2.1). If you pull the records yourself, you still need the waiver. Limi… |
| 222 | Chart_Review | When it needs more | 42 CFR Part 2 | …ords with extra protections Substance use disorder treatment records (42 CFR Part 2). Records identifying someone as a patient of a federally assisted… |
| 223 | Chart_Review | When it needs more | Part 2 | …studies cannot use the local exempt categories, and the IRB will send Part 2 forms for the study team and the program. The application's checkbox … |
| 224 | Chart_Review | When it needs more | M.G.L. c. 111 | … HIV testing status: both whether a person was tested and the result (M.G.L. c. 111, s. 70F). Without written consent, only BMC workforce members on y… |
| 225 | Chart_Review | When it needs more | HRPP 10.2.5.2.3 | …rmation cannot identify anyone. More than three patients is research (HRPP 10.2.5.2.3). See Case Reports and Case Series for templates. > Common reaso… |
| 226 | Preparing_a_Complete_Submission | Required training | GCP | …ds current human subjects protection training before you submit, plus GCP for clinical trials and institutional SOP training when the study inv… |
| 227 | Preparing_a_Complete_Submission | Special routing (ancillary reviews) | HRPP 7.3.3 | …artment Chair or Section Chief signs, at the same time as IRB review (HRPP 7.3.3). You do not add these signers yourself. Their sign-off means they kn… |
| 228 | Preparing_a_Complete_Submission | Questions | HRPP 6.2.1.2 | … consultation : Required first step for PI-initiated clinical trials (HRPP 6.2.1.2); enter the consult date in your application. Any study team can as… |
| 229 | Application_Section_Tips | What your home institution controls | HRPP 7.2.2.2 | …on is named in consent and HIPAA language, and which sign-offs apply. HRPP 7.2.2.2 notes that for special routing, "applicability may vary by home ins… |
| 230 | Application_Section_Tips | Common mistakes | HRPP 9.6 | … if you justify it and explain how you will protect their identities (HRPP 9.6). The same question's second list asks whether you will target BMC Re… |
| 231 | Application_Section_Tips | What reviewers look for | HRPP 7.2.2.2 | …nce colleagues can recognize each other's answers. - Correct routing: HRPP 7.2.2.2 routes a study to the BMC Chief Medical Officer "if the study targe… |
| 232 | Application_Section_Tips | What reviewers look for | HRPP 7.2.2.15 | … what is monitored, by whom, how often, and who reports what to whom (HRPP 7.2.2.15 lists the required parts). - Reporting timelines that match IRB po… |
| 233 | Application_Section_Tips | What reviewers look for | HRPP 6.6.3.2 | …ays after the investigator or research staff learns of the incident" (HRPP 6.6.3.2), and a summary of other adverse events "at the time of the continu… |
| 234 | Application_Section_Tips | What reviewers look for | HRPP 6.6.3.4 | …e events "at the time of the continuing review and at study closure" (HRPP 6.6.3.4). - For studies with other sites, how sites will share safety infor… |
| 235 | Eligibility_and_Study_Design | Guidance | 45 CFR 46.111(a)(1) | …in relation to what the study may teach. The first federal criterion, 45 CFR 46.111(a)(1) , reads: Risks to subjects are minimized: (i) By using proce… |
| 236 | Eligibility_and_Study_Design | Who reviews the science | HRPP 7.3.2 | …quate expertise and that the study is appropriate for the department (HRPP 7.3.2). - The IRB. Reviewers consider design, sample size, and analysis in … |
| 237 | Eligibility_and_Study_Design | Who reviews the science | HRPP 10.2.1.2 | … also get a biostatistician's review before the convened board meets (HRPP 10.2.1.2). - Ceded studies. The IRB of record does the scientific review (H… |
| 238 | Eligibility_and_Study_Design | Who reviews the science | HRPP 2.5.3.2 | ….1.2). - Ceded studies. The IRB of record does the scientific review (HRPP 2.5.3.2). See Ceding Review to Another IRB . > Writing eligibility criteria… |
| 239 | Eligibility_and_Study_Design | Can you reach it? | HRPP 7.2.2.14.5 | …inical trials must give quantitative feasibility data and its source (HRPP 7.2.2.14.5). The BMC Clinical Data Warehouse for Research (CDW-R) can help … |
| 240 | Eligibility_and_Study_Design | Related links | 45 CFR 46.111 | …(sections 7.2.2.10, 7.2.2.13, 7.2.2.14, 10.1.1.1, and 10.1.1.2.4.2) - 45 CFR 46.111, criteria for IRB approval (eCFR) Was this page helpful? Yes / No.… |
| 241 | Ancillary_Reviews_Sign_Offs | Guidance | HRPP 1.1.2 | …ervisor. BMC Brighton and BMC South are covered by the BMC/BUMC HRPP (HRPP 1.1.2), and routing can differ by the PI's home institution. Email medirb@b… |
| 242 | Ancillary_Reviews_Sign_Offs | Guidance | HRPP 7.3.2 | …t, INSPIR sends your study to your Department Chair or Section Chief (HRPP 7.3.2). After they sign, it goes to the IRB and, at the same time, to any s… |
| 243 | Ancillary_Reviews_Sign_Offs | Guidance | HRPP 7.3.3 | …oes to the IRB and, at the same time, to any special routing offices (HRPP 7.3.3). The IRB confirms all required sign-offs before approval or an exemp… |
| 244 | Training_Requirements | Training Requirements for Study Teams | GCP | …. People working on clinical trials also need Good Clinical Practice (GCP) training. Both are completed online through CITI, and both are curre… |
| 245 | Training_Requirements | Training Requirements for Study Teams | Section 6.2.3 | …every three years. [PENDING DECISION: HSP refresher] The rules are in Section 6.2.3 of the HRPP Policies and Procedures ; CITI instructions are on the… |
| 246 | Training_Requirements | Quick reference | GCP | …itial certification [UNVERIFIED: renewal] \| \| Good Clinical Practice (GCP) \| Everyone involved in the conduct of a clinical trial covered by th… |
| 247 | Training_Requirements | Guidance | GCP | …ort note. Step-by-step instructions: Initial Certification (OHRA) . > GCP for clinical trials GCP training is required for everyone involved in… |
| 248 | Training_Requirements | Questions | GCP | …: Five-session course for research staff; completing it satisfies the GCP requirement for 3 years. - The Principal Investigator Role training :… |
| 249 | Training_Requirements | Related links | Section 6.2.3 | …piration rules held pending the HRPP Advisory Committee's decision on Section 6.2.3.… |
| 250 | Student_Trainee_Research | Guidance | HRPP 6.1.3.2 | …ing your own students \| ## Guidance > Class and course projects Under HRPP 6.1.3.2, a course project does not need IRB review only if all of these ar… |
| 251 | Student_Trainee_Research | Guidance | HRPP 6.2.2 | … staff, or a student or trainee with a Supervising PI from BMC or BU (HRPP 6.2.2). The Supervising PI must be someone eligible to be a PI in their own… |
| 252 | Student_Trainee_Research | Guidance | HRPP 6.1.3.4 | …meone eligible to be a PI in their own right. Two setups are allowed (HRPP 6.1.3.4): - The student or trainee is the PI and the mentor is the Supervis… |
| 253 | Student_Trainee_Research | Guidance | HRPP 6.6.6 | …s; a lapsed study held by the PI or Supervising PI stops a new study (HRPP 6.6.6). See Continuing Review and Closing Your Study . If you and your ment… |
| 254 | Student_Trainee_Research | Guidance | HRPP 7.2.2.2 | …IR routes it for sign-off from the Goldman School of Dental Medicine (HRPP 7.2.2.2). Studies that recruit dental students as subjects are routed to th… |
| 255 | Student_Trainee_Research | Guidance | HRPP 6.1.3.3 | … a BMC or BU requirement, or your Supervising PI is from BMC or BUMC (HRPP 6.1.3.3). > Residents and fellows A resident- or fellow-led study needs a S… |
| 256 | Student_Trainee_Research | Guidance | HRPP 6.2.3 | …ents and trainees need the same training as everyone else on a study (HRPP 6.2.3): - Human subjects protection, GCP for clinical trials, and BMC SOP t… |
| 257 | Student_Trainee_Research | Guidance | GCP | …s everyone else on a study (HRPP 6.2.3): - Human subjects protection, GCP for clinical trials, and BMC SOP training when the study involves BMC… |
| 258 | Student_Trainee_Research | Guidance | HRPP 9.6 | …ressure to join research run by those who grade or supervise them, so HRPP 9.6 requires extra protections when you target students, trainees, or emp… |
| 259 | Student_Trainee_Research | Guidance | HRPP 10.2.5.3 | …e IRB, because it does not describe specific human subjects research (HRPP 10.2.5.3). Each trainee's project that involves human subjects must be appr… |
| 260 | Student_Trainee_Research | Guidance | HRPP 2.1.2 | …udy cannot use the BMC/BUMC equivalent protections exempt categories (HRPP 2.1.2); see Exempt Research . No trainee work may begin until the trainee's… |
| 261 | INSPIR_Task_Access_and_New_Study | How INSPIR's branching works | Equivalent Protections Exempt category | …arch activities are chart reviews; the study fits a federal Exempt or Equivalent Protections Exempt category; or none of the above, needing Expedited … |
| 262 | INSPIR_Task_Access_and_New_Study | Mac | HRPP 7.3.2 | …for sign-off. Your Department Chair or Section Chief signs off first (HRPP 7.3.2). After they sign, these offices sign off at the same time the IRB re… |
| 263 | INSPIR_Task_Access_and_New_Study | Mac | HRPP 7.3.3 | …, these offices sign off at the same time the IRB reviews your study (HRPP 7.3.3). A Special Routing sign-off is not that office's approval; some comm… |
| 264 | INSPIR_Task_Choose_Review_Path | The five Review Path Determination options | Equivalent Protections Exempt categories | …study does not have external funding and fits into one or more of the Equivalent Protections Exempt categories." \| Minimal risk, not FDA-regulated, f… |
| 265 | Responding_to_Stipulations | BMC/BUMC IRB | [link] HRPP 10.3.2.2 → 10.3.2.2 | …(hyperlink to HRPP policies page anchor)… |
| 266 | Responding_to_Stipulations | The steps of review | [link] HRPP 10.2.4.4 → 10.2.4.4 | …(hyperlink to HRPP policies page anchor)… |
| 267 | Responding_to_Stipulations | The steps of review | [link] HRPP 10.2.2.2 → 10.2.2.2 | …(hyperlink to HRPP policies page anchor)… |
| 268 | Responding_to_Stipulations | The steps of review | [link] HRPP 10.2.1.2 → 10.2.1.2 | …(hyperlink to HRPP policies page anchor)… |
| 269 | Responding_to_Stipulations | The steps of review | [link] HRPP 10.5.1 → 10.5.1 | …(hyperlink to HRPP policies page anchor)… |
| 270 | Responding_to_Stipulations | Review outcomes and what they mean | [link] HRPP 10.3.2.2 → 10.3.2.2 | …(hyperlink to HRPP policies page anchor)… |
| 271 | Responding_to_Stipulations | Review outcomes and what they mean | [link] HRPP 10.3.2.3 → 10.3.2.3 | …(hyperlink to HRPP policies page anchor)… |
| 272 | Responding_to_Stipulations | Review outcomes and what they mean | [link] HRPP 10.3.2.4 → 10.3.2.4 | …(hyperlink to HRPP policies page anchor)… |
| 273 | Responding_to_Stipulations | How long you have to respond | [link] HRPP 7.4.6 → 7.4.6 | …(hyperlink to HRPP policies page anchor)… |
| 274 | Responding_to_Stipulations | Responding to IRB Stipulations | HRPP 10.3.2.2 | …licy states: "Conditional approval is not approval of a submission" ( HRPP 10.3.2.2 ). Make the change where it belongs. An answer typed only in the r… |
| 275 | Responding_to_Stipulations | What happens after you submit | HRPP 7.3.2 | …ns off, the submission goes to the Department Chair or Section Chief (HRPP 7.3.2). After they sign, it goes to the IRB, and any special routing office… |
| 276 | Responding_to_Stipulations | What happens after you submit | HRPP 7.3.3 | … any special routing offices sign off at the same time as IRB review (HRPP 7.3.3). The IRB confirms every sign-off before approval. See Ancillary Revi… |
| 277 | Responding_to_Stipulations | What happens after you submit | HRPP 10.2.4.4 | …he determination; some exempt categories also go to an IRB reviewer ( HRPP 10.2.4.4 ). - Expedited: an experienced IRB member (an expedited reviewer) … |
| 278 | Responding_to_Stipulations | What happens after you submit | HRPP 10.2.2.2 | … but cannot disapprove; they may send a study to the convened board ( HRPP 10.2.2.2 ). - Convened board (full board): the study is assigned to primary… |
| 279 | Responding_to_Stipulations | What happens after you submit | HRPP 10.2.1.2 | …nd secondary reviewers and discussed and voted on at an IRB meeting ( HRPP 10.2.1.2 ). There are no submission deadlines; the study goes on the next a… |
| 280 | Responding_to_Stipulations | What happens after you submit | HRPP 10.5.1 | …s its decision through INSPIR within 5 working days of the decision ( HRPP 10.5.1 ). If changes are needed, you receive a Review Response task with th… |
| 281 | Responding_to_Stipulations | What happens after you submit | HRPP 10.3.2.2 | …r an expedited reviewer can then approve, or return it to the board ( HRPP 10.3.2.2 ). \| \| Changes required by an expedited reviewer \| The reviewer… |
| 282 | Responding_to_Stipulations | What happens after you submit | HRPP 10.3.2.3 | …e. \| Respond point by point. The full board reviews the study again ( HRPP 10.3.2.3 ). \| \| Disapproved (convened board only) \| The study has probl… |
| 283 | Responding_to_Stipulations | What happens after you submit | HRPP 10.3.2.4 | …in writing through INSPIR, and you may ask to appear before the IRB ( HRPP 10.3.2.4 ). \| \| Withdrawn or administratively closed \| You withdrew the … |
| 284 | Responding_to_Stipulations | How to respond so it doesn't come back | HRPP 11.5 | …writing to the Chair within 30 days and ask to appear before the IRB (HRPP 11.5). > How long you have to respond Respond as soon as you can; your stu… |
| 285 | Responding_to_Stipulations | How to respond so it doesn't come back | HRPP 7.4.6 | …til you do. BMC/BUMC policy sets reminders and a final closure date ( HRPP 7.4.6 , revised July 2026): - INSPIR sends reminders to the PI and study co… |
| 286 | Timelines_and_JIT | Grant deadlines and NIH Just-in-Time | 45 CFR 46.118 | …IRB approves it and your institution sends the certification to NIH ( 45 CFR 46.118 ). Ask your grants office how to flag this. [UNVERIFIED: BMC/BU gr… |
| 287 | Example_NHSR_and_QI_Requests | Related links | [link] HRPP Policies and Procedures, Section 10.2.5 (QI, case reports) → 10.2.5.2.2 | …(hyperlink to HRPP policies page anchor)… |
| 288 | Example_NHSR_and_QI_Requests | How to use these examples | HRPP Section 10.2.5.2.2 | …I report asks for a letter. Why it is QI. It meets every criterion in HRPP Section 10.2.5.2.2: it improves a local process against an accepted standar… |
| 289 | Example_NHSR_and_QI_Requests | How to use these examples | 45 CFR 164.501, 164.506 | …lth care operation, so no research authorization or waiver is needed (45 CFR 164.501, 164.506). The BMC QI IRB Checklist still requires all PHI to sta… |
| 290 | Example_NHSR_and_QI_Requests | How to use these examples | Exempt category 11 | … of HIPAA authorization. See Waivers of Consent and Documentation . - Exempt category 11 (QI also analyzed as research) is unlikely to fit: it applies… |
| 291 | Example_NHSR_and_QI_Requests | How to use these examples | HRPP 10.2.4.2.2.2 | …of the change, and patients can easily be asked about text reminders (HRPP 10.2.4.2.2.2(11)). - A randomized comparison of interventions with a health… |
| 292 | Example_NHSR_and_QI_Requests | How to use these examples | HRPP Section 10.2.5.2.3 | …e patients is a case series, which is research and must be submitted (HRPP Section 10.2.5.2.3). HIPAA still applies. Get a signed HIPAA authorization … |
| 293 | Example_NHSR_and_QI_Requests | Related links | Section 10.2.5 | …- HIPAA in Research - Exempt Research - HRPP Policies and Procedures, Section 10.2.5 (QI, case reports) - Quality Improvement/Quality Assurance Projec… |
| 294 | Example_Exempt_Survey | Review Path Determination | Equivalent Protections Exempt categories | …study does not have external funding and fits into one or more of the Equivalent Protections Exempt categories." Why this works: the study only involv… |
| 295 | Example_Exempt_Survey | Study Attachments | HRPP 7.2.2.14.6 | … review, but final versions must be approved by amendment before use (HRPP 7.2.2.14.6); recruitment materials must be final. For an anonymous survey, … |
| 296 | Example_Exempt_Chart_Review | Which path this example uses | 46.104(d)(4)(ii) | …ions. Why category 9 and not category 4: INSPIR's category 4 (federal 46.104(d)(4)(ii)) requires that information be recorded so that people cannot be… |
| 297 | Example_Exempt_Chart_Review | External funding | HRPP 2.1.2 | …the study counts as federally funded and cannot use local category 9 (HRPP 2.1.2). Ask the IRB if you are unsure whether your project is covered by th… |
| 298 | Example_Exempt_Chart_Review | Other sites relying on the BMC/BUMC IRB | HRPP 10.2.4.2.2.2 | …categories cannot be used when another institution relies on our IRB (HRPP 10.2.4.2.2.2). #### Substance use disorder program records Question: "Does … |
| 299 | Example_Exempt_Chart_Review | Part c. When identifiers will be destroyed | HRPP 6.6.7.1 | … to patients, will be kept for at least 7 years after the study ends (HRPP 6.6.7.1) and then destroyed. Why this works: it names a milestone rather th… |
| 300 | Example_Exempt_Chart_Review | Destroying identifiers | HRPP 6.6.7.1 | … to patients, will be kept for at least 7 years after the study ends (HRPP 6.6.7.1) and then destroyed. Why this works: same milestone and same steps … |
| 301 | Example_Expedited_Interview_Study | Example Application: Expedited Interview Study | 45 CFR 46.110 | …y Test (English). \| \| Review path \| Expedited categories 5, 6, and 7 (45 CFR 46.110), minimal risk, single site (BMC), not a clinical trial. Funded… |
| 302 | Example_Expedited_Interview_Study | Study personnel | HRPP 2.4 | …ay approach them, which does not make them part of the research team (HRPP 2.4). The list each clinician receives names only that clinician's own pa… |
| 303 | Example_Expedited_Interview_Study | Review Path Determination | 45 CFR 46.110 | …ategories, and it is reviewed under expedited categories 5, 6, and 7 (45 CFR 46.110). If your study has no external funding, check whether it fits an … |
| 304 | Example_Expedited_Interview_Study | Study Summary | HRPP 7.2.2.16.4 | …th all identifiers removed and no key is not retention for extra use (HRPP 7.2.2.16.4). \| \| Genetics; Nursing Department \| No \|  \| Common mistake… |
| 305 | Example_Expedited_Interview_Study | Consent process for screening | HRPP 8.1.3.4 and 7.2.2.6.5 | …ing Agreement fits because screening involves no clinical procedures (HRPP 8.1.3.4 and 7.2.2.6.5, revised September 16, 2026: full consent is needed f… |
| 306 | Example_Expedited_Interview_Study | Non-English Language Consent Forms | HRPP 8.4.5.3 | … decides who may interpret based on the study's risks and procedures (HRPP 8.4.5.3), and minors may not interpret. See Including Participants with Lim… |
| 307 | Example_Pediatric_Study | The fictional study | 45 CFR 46.404 | …e follow-up survey. \| \| Risk category \| No greater than minimal risk (45 CFR 46.404). We ask the IRB to find that one parent's permission is suffic… |
| 308 | Example_Pediatric_Study | The fictional study | 45 CFR 46.408(b) | …). We ask the IRB to find that one parent's permission is sufficient (45 CFR 46.408(b)). \| \| Funding and review path \| Funded by an NIH grant, so t… |
| 309 | Example_Pediatric_Study | The fictional study | HRPP 2.1.2 | …ailable (it covers only studies eligible for equivalent protections , HRPP 2.1.2). The federal exemptions do not cover surveys or interviews with chil… |
| 310 | Example_Pediatric_Study | The fictional study | 45 CFR 46.104(b)(3) | … federal exemptions do not cover surveys or interviews with children (45 CFR 46.104(b)(3)). Reviewed by the expedited procedure, categories 6 and 7. I… |
| 311 | Example_Pediatric_Study | The fictional study | Exempt Category 12 | …6 and 7. If your study has no external funding, check whether it fits Exempt Category 12 first. \| \| Form \| Parent Consent and Permission Form Templ… |
| 312 | Example_Pediatric_Study | The application, section by section | 45 CFR 46.404 | …sachusetts law. We believe the study is no greater than minimal risk (45 CFR 46.404): the survey and interview ask about sleep, screen use, routines a… |
| 313 | Example_Pediatric_Study | The application, section by section | 45 CFR 46.408(b) | …t. We ask the IRB to find that one parent's permission is sufficient (45 CFR 46.408(b)), and we will obtain the assent of each teen, as described in t… |
| 314 | Example_Pediatric_Study | The application, section by section | M.G.L. c. 119 | …lect, trained staff will follow Massachusetts mandated reporting law (M.G.L. c. 119, section 51A). If a teen says they are thinking about hurting them… |
| 315 | Example_Pediatric_Study | The application, section by section | HRPP 9.2.4.3 | …t form signed by the child needs a justification in your application (HRPP 9.2.4.3). > Release of identifiable data and Payment Example answer, Releas… |
| 316 | Example_Pediatric_Study | The parent consent and permission form: key sections | HRPP 9.2.4.2 | …ur child for their own consent before they answer it. Why this works. HRPP 9.2.4.2 says parental permission no longer covers a participant who turns 1… |
| 317 | Example_Pediatric_Study | Model assent scripts | 45 CFR 46.402(b) | …out 350 words. The federal rule says failure to object is not assent (45 CFR 46.402(b)), so the script asks for a clear yes. One reviewer asked a stud… |
| 318 | Example_Pediatric_Study | How a teen who turns 18 is handled | 45 CFR 46.116(f) | …ot collect more data from them. We ask the IRB to waive consent under 45 CFR 46.116(f) so we can keep using the data collected before age 18 from part… |
| 319 | Example_Pediatric_Study | Consistency check | 46.404 | …ons ("Minors") \| Overview \| (implied) \| Eligibility \| \| Minimal risk (46.404); one parent's permission \| Protections question; minors questions … |
| 320 | Example_Amendment_and_Stipulation_Response | Step 1: sort your changes first | [link] HRPP 8.4.5.1 → 8.4.5.1 | …(hyperlink to HRPP policies page anchor)… |
| 321 | Example_Amendment_and_Stipulation_Response | Step 1: sort your changes first | [link] HRPP 7.4.1.2 → 7.4.1.2 | …(hyperlink to HRPP policies page anchor)… |
| 322 | Example_Amendment_and_Stipulation_Response | Step 3: give a re-consent plan | [link] HRPP 7.4.1.2 → 7.4.1.2 | …(hyperlink to HRPP policies page anchor)… |
| 323 | Example_Amendment_and_Stipulation_Response | Step 3: give a re-consent plan | [link] HRPP 10.2.2.4.2.1 → 10.2.2.4.2.1 | …(hyperlink to HRPP policies page anchor)… |
| 324 | Example_Amendment_and_Stipulation_Response | Step 4: attach the right documents, the right way | [link] HRPP 7.4.1.2 → 7.4.1.2 | …(hyperlink to HRPP policies page anchor)… |
| 325 | Example_Amendment_and_Stipulation_Response | Related links | [link] HRPP Policy 7.4.1: requirements for amendment submissions → 7.4.1 | …(hyperlink to HRPP policies page anchor)… |
| 326 | Example_Amendment_and_Stipulation_Response | Step 1: sort your changes first | HRPP 8.4.5.1 | …ons are submitted after that, with a Translator Qualifications Form ( HRPP 8.4.5.1 ). See the follow-up amendment . \| \| Add two BMC research assista… |
| 327 | Example_Amendment_and_Stipulation_Response | Step 1: sort your changes first | HRPP 7.4.1.2 | …endment, and a description of any plans for re-consenting subjects" ( HRPP 7.4.1.2 ). The example below covers all four. ### Step 2: write the Amendme… |
| 328 | Example_Amendment_and_Stipulation_Response | Step 3: give a re-consent plan | HRPP 7.4.1.2 | …ys so in the outcome letter, but your amendment must propose a plan ( HRPP 7.4.1.2 ). Re-consent is expected when a change could affect whether people… |
| 329 | Example_Amendment_and_Stipulation_Response | Step 3: give a re-consent plan | HRPP 10.2.2.4.2.1 | …tay in the study or could appreciably affect their experience in it ( HRPP 10.2.2.4.2.1 ). \| What the team wrote \| Why it works \| \| Re-consent is … |
| 330 | Example_Amendment_and_Stipulation_Response | Step 4: attach the right documents, the right way | HRPP 7.4.1.2 | … upload a copy that tracks each change against the approved version ( HRPP 7.4.1.2 ). - Set the version date to the day you upload each revision. Comm… |
| 331 | Example_Amendment_and_Stipulation_Response | Related links | HRPP Policy 7.4.1 | …Complete Submission - Participants with Limited English Proficiency - HRPP Policy 7.4.1: requirements for amendment submissions - Avoiding and Respond… |
| 332 | Informed_Consent_Overview | What informed consent is | Common Rule | …loaded template for your review path. ## What informed consent is The Common Rule ( 45 CFR 46.116(a) ) sets general requirements that apply to every c… |
| 333 | Informed_Consent_Overview | What informed consent is | 45 CFR 46.116(a) | …e for your review path. ## What informed consent is The Common Rule ( 45 CFR 46.116(a) ) sets general requirements that apply to every consent, writte… |
| 334 | Informed_Consent_Overview | What informed consent is | 45 CFR 46.116(a)(4) | …er to participate, and an opportunity to discuss that information." - 45 CFR 46.116(a)(4) ## Required elements The federal rules list the information … |
| 335 | Informed_Consent_Overview | Required elements | 21 CFR 50.25 | …d when it applies (additional elements). FDA-regulated studies follow 21 CFR 50.25 , which is nearly the same. Exempt studies do not need every elemen… |
| 336 | Informed_Consent_Overview | Required elements | 45 CFR 46.116(b) | …eed every element; see consent in exempt research . > Basic elements (45 CFR 46.116(b); 21 CFR 50.25(a)) - That the study is research; its purpose; ho… |
| 337 | Informed_Consent_Overview | Required elements | 21 CFR 50.25(a) | … see consent in exempt research . > Basic elements (45 CFR 46.116(b); 21 CFR 50.25(a)) - That the study is research; its purpose; how long participati… |
| 338 | Informed_Consent_Overview | Required elements | Common Rule | …the person may stop at any time without penalty or loss of benefits - Common Rule only: whether identifiable information or biospecimens, with identif… |
| 339 | Informed_Consent_Overview | Required elements | 45 CFR 46.116(c) | …or shared for future research > Additional elements, when they apply (45 CFR 46.116(c); 21 CFR 50.25(b) and (c)) - Risks that cannot yet be foreseen, … |
| 340 | Informed_Consent_Overview | Required elements | 21 CFR 50.25(b) | …re research > Additional elements, when they apply (45 CFR 46.116(c); 21 CFR 50.25(b) and (c)) - Risks that cannot yet be foreseen, including to an em… |
| 341 | Informed_Consent_Overview | Required elements | 21 CFR 50.25(c) | …pplicable clinical trials: the required ClinicalTrials.gov statement (21 CFR 50.25(c)) For genetic results and future use, see Genetics, Biospecimens,… |
| 342 | Informed_Consent_Overview | Required elements | 45 CFR 46.116(d) | …Biospecimens, and Repositories . BMC/BUMC does not use broad consent (45 CFR 46.116(d)); to keep data or samples for future research, use the future-u… |
| 343 | Informed_Consent_Overview | Required elements | HRPP 8.2 | …the future-use section of the consent template. > BMC/BUMC additions (HRPP 8.2) - Drug and device studies: a statement that data collected before wi… |
| 344 | Informed_Consent_Overview | Required elements | GCP | …fore withdrawal stay in the study database. - Studies that follow ICH-GCP: the additional ICH-GCP elements. - A statement that the participant'… |
| 345 | Consent_Templates | Which template do I use? | Exempt category 12 | …est a waiver or alteration of authorization in the HIPAA section. \| \| Exempt category 12 (surveys or interviews with children), and a parent gives p… |
| 346 | Consent_Templates | Which template do I use? | Exempt category 1 | …est a waiver or alteration of authorization in the HIPAA section. \| \| Exempt category 1 (normal educational practices) with children in schools \| A… |
| 347 | Consent_Templates | Writing each section | Genetic Information Nondiscrimination Act | …ion box on genetics. It includes language about both federal law (the Genetic Information Nondiscrimination Act) and Massachusetts law. If you plan to… |
| 348 | Consent_Templates | Special situations | HRPP 9.2.4.3 | …t form signed by the child needs a justification in your application (HRPP 9.2.4.3). The IRB decides whether permission from one or both parents is ne… |
| 349 | Consent_Templates | Sponsor and external IRB consent forms | Genetic Information Nondiscrimination Act | …nizations with access to the information. - If the form discusses the Genetic Information Nondiscrimination Act and the research takes place in Massac… |
| 350 | Consent_Templates | The rules behind the templates | 45 CFR 46.116(a)(3) | …standable to the subject or the legally authorized representative." - 45 CFR 46.116(a)(3) "Informed consent must begin with a concise and focused pres… |
| 351 | Consent_Templates | The rules behind the templates | 45 CFR 46.116(a)(5)(i) | …ns why one might or might not want to participate in the research." - 45 CFR 46.116(a)(5)(i) FDA-regulated research has the same understandable-langua… |
| 352 | Consent_Templates | The rules behind the templates | 21 CFR 50.20 | …egulated research has the same understandable-language requirement in 21 CFR 50.20 . The Overview section at the start of our templates is where the k… |
| 353 | Consent_Templates | The rules behind the templates | Section 10.2.4.3 | …P Policies and Procedures , Section 8 (Consent and Authorization) and Section 10.2.4.3 (Protection of Participants in Exempt Research). Questions abou… |
| 354 | Consent_Language_Bank | Index of paragraphs | GCP | … \| The total number matters to the decision to join (required for ICH-GCP studies) \| \| What Will Happen \| 4. Whole genome sequencing \| You will… |
| 355 | Consent_Language_Bank | Index of paragraphs | 21 CFR 50.25(c) | …entiality \| 27. ClinicalTrials.gov \| Applicable clinical trials under 21 CFR 50.25(c): FDA-regulated drug or biologic trials other than phase 1, and… |
| 356 | Consent_Language_Bank | Language | GCP | …red, not optional, if your protocol says the consent form follows ICH-GCP. Do not use when The number would not help the decision and the study… |
| 357 | Consent_Language_Bank | Language | Genetic Information Nondiscrimination Act | …ng, not the federal-only version, when a sponsor's form discusses the Genetic Information Nondiscrimination Act and the research takes place in Massac… |
| 358 | Consent_Language_Bank | Language | GINA | …ral laws, particularly the Genetic Information Nondiscrimination Act (GINA), generally make it illegal for health insurance companies, group hea… |
| 359 | Consent_Language_Bank | Language | 45 CFR 46.116(b)(9)(i) | …e v1.14 and Exempt Information Sheet Template v1.11, Confidentiality; 45 CFR 46.116(b)(9)(i)-(ii). > 26. NIH genomic database Use when Genetic and hea… |
| 360 | Consent_Language_Bank | Language | 21 CFR 50.25(c) | …alTrials.gov Use when The study is an applicable clinical trial under 21 CFR 50.25(c), meaning an FDA-regulated drug or biologic trial other than phas… |
| 361 | Consent_Language_Bank | Language | HRPP 8.2.1.2, 8.2.2 | …mplate v1.14, Subject's Rights; ICH-GCP rule from Special Directions; HRPP 8.2.1.2, 8.2.2. > 33. Questions and IRB contact Use when Every full consent… |
| 362 | Obtaining_Consent | Guidance | Part 11 | …gned, returned, and copied \| \| FDA-regulated, electronic signatures \| Part 11 compliant e-consent \| The platform and how you verify identity \| \|… |
| 363 | Obtaining_Consent | Licensed independent practitioner (LIP) requirement | 45 CFR 46.116(a)(2) | …ects participants. The IRB decides. > Where, when, and time to decide 45 CFR 46.116(a)(2) states: An investigator shall seek informed consent only und… |
| 364 | Obtaining_Consent | Platforms | 21 CFR Part 11 | …gn Life Sciences , offered by BMC for FDA-regulated studies that need 21 CFR Part 11 compliance. Request it through BMC ServiceNow (Research Technolog… |
| 365 | Obtaining_Consent | FDA-regulated studies:  | 21 CFR Part 11 | …ness-signature process is still accepted] #### FDA-regulated studies: 21 CFR Part 11 If your study involves a drug or device, or its data will go to t… |
| 366 | Obtaining_Consent | FDA-regulated studies: 21 CFR Part 11 | 21 CFR Part 11 | …u use for study records or signatures, including e-consent, must meet 21 CFR Part 11 . The PI is responsible for compliance when the system is managed… |
| 367 | Obtaining_Consent | FDA-regulated studies: 21 CFR Part 11 | Part 11 | …rocedures, training, and validation. A standard REDCap project is not Part 11 compliant; use BMC's DocuSign Life Sciences, or complete the BU REDCa… |
| 368 | Obtaining_Consent | FDA-regulated studies: 21 CFR Part 11 | 21 CFR 11.200(a)(1) | …l confirm the signer's identity, and how the signature is made. Under 21 CFR 11.200(a)(1), an electronic signature that is not biometric must use at l… |
| 369 | Obtaining_Consent | FDA-regulated studies: 21 CFR Part 11 | 45 CFR 46.117(c) | …oups. The IRB must approve a waiver of documentation of consent under 45 CFR 46.117(c) , which requires one of the following: - The study is no more t… |
| 370 | Obtaining_Consent | FDA-regulated studies: 21 CFR Part 11 | 21 CFR 56.109(c)(1) | …FDA-regulated studies, only the minimal risk criterion is available ( 21 CFR 56.109(c)(1) ). > Waiving or altering consent A waiver means participants… |
| 371 | Obtaining_Consent | FDA-regulated studies: 21 CFR Part 11 | 45 CFR 46.116(f)(3) | …n-exempt study. Either way, your study must meet all five criteria in 45 CFR 46.116(f)(3): (i) The research involves no more than minimal risk to the … |
| 372 | Obtaining_Consent | FDA-regulated studies: 21 CFR Part 11 | 21 CFR 50.22 | …p. FDA-regulated minimal risk studies can use the same criteria under 21 CFR 50.22 . Three waivers that are often confused \| Waiver \| What it lets y… |
| 373 | Obtaining_Consent | FDA-regulated studies: 21 CFR Part 11 | 45 CFR 46.116(f) | …nt \| Asking for consent at all, or giving some required information \| 45 CFR 46.116(f) \| \| Waiver of documentation of consent \| The signature onl… |
| 374 | Obtaining_Consent | FDA-regulated studies: 21 CFR Part 11 | 45 CFR 164.512(i) | …on of HIPAA authorization \| A signed HIPAA authorization to use PHI \| 45 CFR 164.512(i); see HIPAA in Research \| Each is granted separately; a stud… |
| 375 | Obtaining_Consent | FDA-regulated studies: 21 CFR Part 11 | 45 CFR 46.116(d) | …d separately; a study may need one, two, or all three. Broad consent (45 CFR 46.116(d)) is not used by the BMC/BUMC IRB. To keep data or samples for f… |
| 376 | Obtaining_Consent | Related links | 45 CFR 46.116 | …ies and Procedures (sections 7.2.2.12, 8.1 to 8.4, 9.2.4.2, 12.4.7) - 45 CFR 46.116, general requirements for informed consent (eCFR) - 45 CFR 46.117,… |
| 377 | Obtaining_Consent | Related links | 45 CFR 46.117 | …) - 45 CFR 46.116, general requirements for informed consent (eCFR) - 45 CFR 46.117, documentation of informed consent (eCFR) - 21 CFR Part 50, FDA in… |
| 378 | Obtaining_Consent | Related links | 21 CFR Part 50 | …nt (eCFR) - 45 CFR 46.117, documentation of informed consent (eCFR) - 21 CFR Part 50, FDA informed consent rules (eCFR) - FDA and OHRP guidance: Use o… |
| 379 | Obtaining_Consent | Related links | OHRP guidance: Use of Electronic Informed Consent, Questions and Answers | … (eCFR) - 21 CFR Part 50, FDA informed consent rules (eCFR) - FDA and OHRP guidance: Use of Electronic Informed Consent, Questions and Answers (Decemb… |
| 380 | Limited_English_Proficiency | Including Participants with Limited English Proficiency | HRPP 8.4.5.2 | …ubmit a full translation within 30 days of any short form enrollment (HRPP 8.4.5.2, revised May 26, 2026) \| ## Guidance > What your application must … |
| 381 | Limited_English_Proficiency | Guidance | HRPP 8.4.5.3 | … decides who may interpret based on the study's risks and procedures (HRPP 8.4.5.3). Minors may not interpret. A study team member who is fluent in th… |
| 382 | Limited_English_Proficiency | Guidance | HRPP 8.4.5.2 | …reter ID number on the witness signature line instead of a signature (HRPP 8.4.5.2). If you use a separate English summary instead of the full consent… |
| 383 | Limited_English_Proficiency | Related links | 45 CFR 46.117 | …cies and Procedures (sections 7.2.2.12.6 and 8.4.5 through 8.4.5.3) - 45 CFR 46.117, documentation of informed consent, including the short form (eCFR… |
| 384 | Short_Form_Consent_Process | Before the consent discussion | HRPP 8.4.5.3 | … decides who may interpret based on the study's risks and procedures (HRPP 8.4.5.3); see the interpreter rules . Minors may not interpret. - Arrange a… |
| 385 | Short_Form_Consent_Process | During the consent discussion | HRPP 8.4.5.2 | …terpreter ID number on the witness signature line instead of signing (HRPP 8.4.5.2). #### After the consent discussion - Give the participant copies o… |
| 386 | Short_Form_Consent_Process | After the consent discussion | Section 8.4.5.2 | … unless otherwise approved by the IRB." HRPP Policies and Procedures, Section 8.4.5.2 (revised May 26, 2026) Translation triggers (HRPP 8.4.5.2) \| Tr… |
| 387 | Short_Form_Consent_Process | After the consent discussion | HRPP 8.4.5.2 | …cedures, Section 8.4.5.2 (revised May 26, 2026) Translation triggers (HRPP 8.4.5.2) \| Trigger \| Applies to \| What you must do \| \| Three uses of t… |
| 388 | Short_Form_Consent_Process | Related links | 45 CFR 46.117(b)(2) | … and Procedures (sections 7.2.2.12.6, 8.4.5.2, 8.4.5.3, and 10.1.2) - 45 CFR 46.117(b)(2), short form documentation (eCFR) - 21 CFR 50.27(b)(2), short… |
| 389 | Short_Form_Consent_Process | Related links | 21 CFR 50.27(b)(2) | … and 10.1.2) - 45 CFR 46.117(b)(2), short form documentation (eCFR) - 21 CFR 50.27(b)(2), short form documentation for FDA-regulated studies (eCFR) - … |
| 390 | HIPAA_in_Research | Guidance | 45 CFR 164.512(i)(2)(ii) | …your answers show that the study meets all of the federal criteria in 45 CFR 164.512(i)(2)(ii) : (A) The use or disclosure of protected health informa… |
| 391 | HIPAA_in_Research | More than one waiver | 45 CFR 164.514(b) | …arately. - De-identified (HIPAA): either all 18 identifiers listed in 45 CFR 164.514(b) are removed (the "Safe Harbor" method) and there is no actual … |
| 392 | HIPAA_in_Research | Identifiers people often miss | HRPP 2.5.3.2 | …ns the review of HIPAA waivers for BMC or BU PHI to the BMC/BUMC IRB (HRPP 2.5.3.2). Answer the HIPAA Compliance questions in your cede application; t… |
| 393 | HIPAA_in_Research | Identifiers people often miss | Common Rule | …n about people who have died is not human subjects research under the Common Rule, but HIPAA still applies for 50 years after death. The data holder n… |
| 394 | HIPAA_in_Research | Identifiers people often miss | 42 CFR Part 2 | … substance use disorder programs have additional federal protections (42 CFR Part 2) beyond HIPAA. Tell the IRB if your study uses them. Case reports.… |
| 395 | HIPAA_in_Research | Related links | 45 CFR 164.512 | ….2.2.3 and 8.5) - BU HIPAA and Health Information Privacy Resources - 45 CFR 164.512, including research uses of PHI (eCFR) - 45 CFR 164.514, de-ident… |
| 396 | HIPAA_in_Research | Related links | 45 CFR 164.514 | …y Resources - 45 CFR 164.512, including research uses of PHI (eCFR) - 45 CFR 164.514, de-identification and limited data sets (eCFR) - HHS guidance on… |
| 397 | HIPAA_Waiver_Sample_Answers | Question by question | 45 CFR 164.512(i)(2)(ii) | …and attestation answers map onto the criteria the IRB must find under 45 CFR 164.512(i)(2)(ii) : the protection answer to (A)(1), the destruction answ… |
| 398 | Certificates_of_Confidentiality | What a Certificate does not stop | Section 10.3.2.2 | … is not automatically granted a CoC, a condition of IRB approval (see Section 10.3.2.2) will be obtaining a CoC." You would then apply after condition… |
| 399 | Recruitment_and_Screening | Guidance | HRPP 7.2.2.6.3 | …h Limited English Proficiency . > What recruitment materials must say HRPP 7.2.2.6.3 lists what materials should include, as it applies to the type of… |
| 400 | Recruitment_and_Screening | Opt-out letters and MyChart messages | HRPP 9.6 | … are generally approvable. - Students, trainees, and employees. Under HRPP 9.6, "Students, trainees, or employees should not be targeted for recruit… |
| 401 | Recruitment_and_Screening | Opt-out letters and MyChart messages | HRPP 7.2.2.6.4 | …th centers must document their approval before research begins there (HRPP 7.2.2.6.4). Boston HealthNet community health centers are separate institut… |
| 402 | Recruitment_and_Screening | Opt-out letters and MyChart messages | HRPP 7.2.2.6.2 | …or referring patients, and may not accept bonuses tied to enrollment (HRPP 7.2.2.6.2). - Social media, websites, and recruitment companies. Submit the… |
| 403 | Recruitment_and_Screening | Opt-out letters and MyChart messages | HRPP 8.1.3.4 | …form. If it involves asking the person questions or doing procedures, HRPP 8.1.3.4 requires a screening consent process. What you need depends on what… |
| 404 | Recruitment_and_Screening | What the application must say about screening | HRPP 7.2.2.6.5 | …PP 8.1.3.4). #### What the application must say about screening Under HRPP 7.2.2.6.5, describe: - How screening works, and attach every screening scri… |
| 405 | Recruitment_and_Screening | Related links | FDA guidance: Recruiting Study Subjects | …licies and Procedures (sections 7.2.2.6, 7.4.1.4, 8.1.3.4, and 9.6) - FDA guidance: Recruiting Study Subjects - Surveys, Interviews, and Focus Groups … |
| 406 | Paying_Participants | Guidance | HRPP 7.2.2.11 | … IRS reporting whether the payment is made by Candex or by gift card (HRPP 7.2.2.11, revised September 16, 2026). The Payment language in the non-exem… |
| 407 | Paying_Participants | Guidance | M.G.L. c. 271 | …ce, and limits raffles to certain permitted nonprofit organizations ( M.G.L. c. 271, section 7A ). For other legal questions, ask your home institutio… |
| 408 | Paying_Participants | Related links | FDA guidance: Payment and Reimbursement to Research Subjects | …ect Payments policy - Candex: how participants receive a BU payment - FDA guidance: Payment and Reimbursement to Research Subjects - Social Media and … |
| 409 | Amendments | Do I need an amendment? | [link] HRPP Policy 6.6.4 → 6.6.4 | …(hyperlink to HRPP policies page anchor)… |
| 410 | Amendments | Do I need an amendment? | [link] HRPP Policy 10.2.4.1 → 10.2.4.1 | …(hyperlink to HRPP policies page anchor)… |
| 411 | Amendments | Do I need an amendment? | [link] HRPP Policy 6.1.1 → 6.1.1 | …(hyperlink to HRPP policies page anchor)… |
| 412 | Amendments | Do I need an amendment? | [link] HRPP Policy 10.2.3.1.2 → 10.2.3.1.2 | …(hyperlink to HRPP policies page anchor)… |
| 413 | Amendments | How amendments are reviewed | [link] HRPP Policy 10.2.2.4.2.1 → 10.2.2.4.2.1 | …(hyperlink to HRPP policies page anchor)… |
| 414 | Amendments | How amendments are reviewed | [link] HRPP Policy 10.2.7.1 → 10.2.7.1 | …(hyperlink to HRPP policies page anchor)… |
| 415 | Amendments | Changes made to protect subjects right away | [link] HRPP Policy 6.6.5.2 → 6.6.5.2 | …(hyperlink to HRPP policies page anchor)… |
| 416 | Amendments | Related links | [link] HRPP Policy 7.4.1: requirements for amendment submissions → 7.4.1 | …(hyperlink to HRPP policies page anchor)… |
| 417 | Amendments | Do I need an amendment? | HRPP Policy 6.6.4 | …uitment methods, or editing a consent form, need IRB approval first ( HRPP Policy 6.6.4 ). New or revised surveys, interview guides, and recruitment m… |
| 418 | Amendments | Do I need an amendment? | HRPP Policy 10.2.4.1 | …licy lists changes that call for an amendment, including changes to ( HRPP Policy 10.2.4.1 ): - privacy and confidentiality protections - funding - re… |
| 419 | Amendments | Do I need an amendment? | HRPP Policy 6.1.1 | …one with an Internal Study Personnel Changes form, not an amendment ( HRPP Policy 6.1.1 ). > Studies ceded to an external IRB Your reviewing IRB appro… |
| 420 | Amendments | Do I need an amendment? | HRPP Policy 10.2.3.1.2 | …policy, or institution-specific consent language. The full list is in HRPP Policy 10.2.3.1.2 . Changes to BMC/BU study personnel use the Internal Stud… |
| 421 | Amendments | How amendments are reviewed | HRPP Policy 10.2.2.4.2.1 | …changed, still fits entirely within the expedited review categories ( HRPP Policy 10.2.2.4.2.1 ). Other amendments go to a convened IRB meeting (HRPP … |
| 422 | Amendments | How amendments are reviewed | HRPP 10.2.1.3 and 10.2.2.4.2.1 | …Policy 10.2.2.4.2.1 ). Other amendments go to a convened IRB meeting (HRPP 10.2.1.3 and 10.2.2.4.2.1; 45 CFR 46.108(b) and 46.110(b)(1)(ii)). Personne… |
| 423 | Amendments | How amendments are reviewed | 45 CFR 46.108(b) and 46.110(b)(1)(ii) | …ndments go to a convened IRB meeting (HRPP 10.2.1.3 and 10.2.2.4.2.1; 45 CFR 46.108(b) and 46.110(b)(1)(ii)). Personnel changes are reviewed administr… |
| 424 | Amendments | How amendments are reviewed | HRPP Policy 10.2.7.1 | … Supervising PI on a non-exempt study goes through expedited review ( HRPP Policy 10.2.7.1 ). > Will I need to re-consent current subjects? If your ch… |
| 425 | Amendments | Study personnel | GCP | … training is required for all such personnel; Good Clinical Practice (GCP) training is also required for clinical trials. See required training… |
| 426 | Amendments | Changes made to protect subjects right away | HRPP Policy 6.6.5.2 | …ible and no later than 7 calendar days after you become aware of it ( HRPP Policy 6.6.5.2 ). If the change will stay in place, also submit a Change Re… |
| 427 | Amendments | Changes made to protect subjects right away | 45 CFR 46.108(a)(3)(iii) | …Amendments form. This exception comes from the federal regulations at 45 CFR 46.108(a)(3)(iii) and, for FDA-regulated research, 21 CFR 56.108(a)(4) . … |
| 428 | Amendments | Changes made to protect subjects right away | 21 CFR 56.108(a)(4) | …ulations at 45 CFR 46.108(a)(3)(iii) and, for FDA-regulated research, 21 CFR 56.108(a)(4) . ## Tips to avoid a returned submission - Explain why, not … |
| 429 | Amendments | Related links | HRPP Policy 7.4.1 | …by-step instructions) - Example of a well-written amendment request - HRPP Policy 7.4.1: requirements for amendment submissions - The 3 Ps: Submitting… |
| 430 | Continuing_Review_and_Closing | Related links | [link] HRPP policy 6.6.2: Continuing reviews and status check-ins → 6.6.2 | …(hyperlink to HRPP policies page anchor)… |
| 431 | Continuing_Review_and_Closing | Related links | [link] HRPP policy 6.6.6: Study closure → 6.6.6 | …(hyperlink to HRPP policies page anchor)… |
| 432 | Continuing_Review_and_Closing | Related links | [link] 6.6.7: Maintaining research records → 6.6.7 | …(hyperlink to HRPP policies page anchor)… |
| 433 | Continuing_Review_and_Closing | Related links | [link] HRPP policy 7.4.3 and 7.4.4: What progress, status check-in, and final reports m → 7.4.3 | …(hyperlink to HRPP policies page anchor)… |
| 434 | Continuing_Review_and_Closing | Related links | [link] HRPP policy 10.4.1: Review intervals and expiration dates → 10.4.1 | …(hyperlink to HRPP policies page anchor)… |
| 435 | Continuing_Review_and_Closing | Which applies to my study? | Common Rule | … by the convened IRB and for FDA-regulated studies. Since the revised Common Rule took effect on January 21, 2019, many minimal risk studies no longer… |
| 436 | Continuing_Review_and_Closing | Which applies to my study? | HRPP Policies 6.6.2, 10.2.4.1, 10.4.1.1, 10.4.1.4, 10.4.1.5 | …dies so the IRB knows the study is still running as approved. Source: HRPP Policies 6.6.2, 10.2.4.1, 10.4.1.1, 10.4.1.4, 10.4.1.5. \| Your study \| Wh… |
| 437 | Continuing_Review_and_Closing | When is it due, and when will I be reminded? | HRPP 6.6.2.1.2, 6.6.2.1.4, 6.6.2.2, 10.4.1.1, 10.4.1.4.3, 10.4.1.5 | …te on your own calendar when you receive your outcome letter. Source: HRPP 6.6.2.1.2, 6.6.2.1.4, 6.6.2.2, 10.4.1.1, 10.4.1.4.3, 10.4.1.5. ## What the … |
| 438 | Continuing_Review_and_Closing | What the form asks | HRPP 7.4.3.1, 6.6.3.2, 6.6.5.2 | … Information form within 7 calendar days of learning of them. Source: HRPP 7.4.3.1, 6.6.3.2, 6.6.5.2. > Status check-in (studies without an expiration… |
| 439 | Continuing_Review_and_Closing | Ceded studies | HRPP 7.4.3.2, 2.5.4, 6.6.5.2 | …ges on a Change Request and Amendments form. See Amendments . Source: HRPP 7.4.3.2, 2.5.4, 6.6.5.2. ## How the IRB reviews it Status check-ins are rev… |
| 440 | Continuing_Review_and_Closing | How the IRB reviews it | HRPP 10.1.2, 10.2.7.4.1 to 10.2.7.4.3, 8.4.5 | …ation now. Progress reports and check-ins ask for your count. Source: HRPP 10.1.2, 10.2.7.4.1 to 10.2.7.4.3, 8.4.5. ## If approval lapses or a check-i… |
| 441 | Continuing_Review_and_Closing | Missed status check-ins | HRPP 6.6.2.1.5.1 to 6.6.2.1.5.4, 6.6.2.2, 6.6.5.2, 6.6.6 | …o submit a Reportable Events and New Information (RENI) form. Source: HRPP 6.6.2.1.5.1 to 6.6.2.1.5.4, 6.6.2.2, 6.6.5.2, 6.6.6; CR Times, March 2024. … |
| 442 | Continuing_Review_and_Closing | Closing your study | HRPP 6.6.6, 7.4.4, 2.5.4 | … or if you or the sponsor end it before the planned end date. Source: HRPP 6.6.6, 7.4.4, 2.5.4; INSPIR instructions "How To Close an Exempt Study" and… |
| 443 | Continuing_Review_and_Closing | Closing your study | HRPP 10.2.7.2 | …ect on the date you submit a properly completed Final/Closure Report (HRPP 10.2.7.2: the date the IRB received the properly completed form), and the c… |
| 444 | Continuing_Review_and_Closing | Closing your study | HRPP 6.6.8 | … Administrator. See also the BU faculty departure checklist . Source: HRPP 6.6.8. ## After closure - Keep your records. Keep all study records, includ… |
| 445 | Continuing_Review_and_Closing | After closure | HRPP 6.6.6, 6.6.7.1, 6.6.7.2 | …t Your Study: Proper Closeout for IRB and IT (February 2026). Source: HRPP 6.6.6, 6.6.7.1, 6.6.7.2; CR Times, June/July 2022. ## How to submit in INSP… |
| 446 | Continuing_Review_and_Closing | Avoiding common problems | HRPP 7.4.6 | … the IRB returned it, the IRB administratively closes the submission (HRPP 7.4.6): an initial review is withdrawn and the study closed; a continuing r… |
| 447 | Continuing_Review_and_Closing | Avoiding common problems | HRPP 6.6.5.3, 6.6.6, 10.1.2 | …dments form, not only in the check-in. Source: IRB review experience; HRPP 6.6.5.3, 6.6.6, 10.1.2. Tools from CRRO The Clinical Research Resources Off… |
| 448 | Reporting_and_Monitoring | What to report and when | HRPP Policies 6.6.3.2 to 6.6.3.5, 6.6.4.1, 6.6.4.3, 6.6.5.2, 6.6.5.3, 7.4.3, 7.4.5, 9.3.1 | … If another IRB does, see If another IRB reviews your study . Source: HRPP Policies 6.6.3.2 to 6.6.3.5, 6.6.4.1, 6.6.4.3, 6.6.5.2, 6.6.5.3, 7.4.3, 7.4… |
| 449 | Reporting_and_Monitoring | Is it an unanticipated problem? | HRPP Section 13, 6.6.3.4 | …t goes on a RENI only if it also meets the three tests above. Source: HRPP Section 13, 6.6.3.4. ## Deviations and protocol exceptions A deviation is a… |
| 450 | Reporting_and_Monitoring | Deviations and protocol exceptions | 21 CFR Part 11 | …linicalTrials.gov registration, updating, or results posting, or with 21 CFR Part 11 requirements that are the PI's responsibility - Anyone working on… |
| 451 | Reporting_and_Monitoring | Deviations and protocol exceptions | GCP | … - Anyone working on the study without the required human subjects or GCP training - Willful misconduct, or noncompliance with law or policy th… |
| 452 | Reporting_and_Monitoring | Deviations and protocol exceptions | HRPP 6.6.5.2 | …apse in approval with no research during the lapse, is minor. Source: HRPP 6.6.5.2 (revised 9/16/26), 6.6.5.3. ### Protocol exceptions: ask first A pr… |
| 453 | Reporting_and_Monitoring | Protocol exceptions: ask first | HRPP 6.6.4.1, 6.6.4.3, 7.4.2, 10.2.2.4.2.2 | …ubject, act, then report it on a RENI within 7 calendar days. Source: HRPP 6.6.4.1, 6.6.4.3, 7.4.2, 10.2.2.4.2.2; CR Times, January 2025. ## How to re… |
| 454 | Reporting_and_Monitoring | How to report | HRPP 7.4.5 | …ou. Source: CAPA template (version 2, 5/13/2022); CR Times, May 2022; HRPP 7.4.5. ## What happens after you report Depending on seriousness, IRB staff… |
| 455 | Reporting_and_Monitoring | What happens after you report | 45 CFR 46.108(a)(4) | …nsions or terminations to institutional officials and to OHRP or FDA (45 CFR 46.108(a)(4); 21 CFR 56.108(b)). Here, the HRPP Director reports within 2… |
| 456 | Reporting_and_Monitoring | What happens after you report | 21 CFR 56.108(b) | …s to institutional officials and to OHRP or FDA (45 CFR 46.108(a)(4); 21 CFR 56.108(b)). Here, the HRPP Director reports within 21 days of the IRB's d… |
| 457 | Reporting_and_Monitoring | What happens after you report | HRPP 10.7, 11.4.2 to 11.4.5, 11.5 | …on, the PI may appeal in writing to the Chair within 30 days. Source: HRPP 10.7, 11.4.2 to 11.4.5, 11.5. ## Quality assurance reviews and audits The H… |
| 458 | Reporting_and_Monitoring | Quality assurance reviews and audits | HRPP 11.3.2, 11.3.8, 11.3.9, 11.3.11 | …If FDA plans to inspect your study, notify the CRRO promptly. Source: HRPP 11.3.2, 11.3.8, 11.3.9, 11.3.11. ## If another IRB reviews your study Follo… |
| 459 | Reporting_and_Monitoring | If another IRB reviews your study | HRPP 2.5.4 | …roblems from all sites. See Working with Other Institutions . Source: HRPP 2.5.4 (revised 9/16/26), 6.6.3.2. ## Privacy incidents and lost data Unauth… |
| 460 | Reporting_and_Monitoring | Privacy incidents and lost data | HRPP 6.6.5.2, 11.4.3.3 | …ch. See Data Security for Researchers and HIPAA in Research . Source: HRPP 6.6.5.2, 11.4.3.3. ## Planning for safety monitoring Your application needs… |
| 461 | Reporting_and_Monitoring | Planning for safety monitoring | HRPP 7.2.2.15, 10.1.1.2.3 | …netic results, see Genetics, Biospecimens, and Repositories . Source: HRPP 7.2.2.15, 10.1.1.2.3. ## FDA-regulated studies Drug studies: report any ser… |
| 462 | Reporting_and_Monitoring | FDA-regulated studies | 21 CFR 312.64(b) | …the sponsor immediately, whether or not you think the drug caused it (21 CFR 312.64(b)); report other adverse events as the protocol requires. Device … |
| 463 | Reporting_and_Monitoring | FDA-regulated studies | 21 CFR 812.150(a) | … a RENI within 7 calendar days; FDA's outer limit is 10 working days, 21 CFR 812.150(a)). If you hold the IND or IDE, you are also the sponsor: you re… |
| 464 | Reporting_and_Monitoring | FDA-regulated studies | 21 CFR 312.32 | … days, or 7 for unexpected fatal or life-threatening reactions, under 21 CFR 312.32; for devices, 812.150(b)) and must complete CRRO sponsor-investiga… |
| 465 | Reporting_and_Monitoring | FDA-regulated studies | 812.150(b) | …atal or life-threatening reactions, under 21 CFR 312.32; for devices, 812.150(b)) and must complete CRRO sponsor-investigator training. Source: HRPP 6… |
| 466 | Reporting_and_Monitoring | FDA-regulated studies | HRPP 6.2.3.1, 6.6.3.1 | …150(b)) and must complete CRRO sponsor-investigator training. Source: HRPP 6.2.3.1, 6.6.3.1; 21 CFR 312.32(c). ## Avoiding common problems - Keep mini… |
| 467 | Reporting_and_Monitoring | FDA-regulated studies | 21 CFR 312.32(c) | …te CRRO sponsor-investigator training. Source: HRPP 6.2.3.1, 6.6.3.1; 21 CFR 312.32(c). ## Avoiding common problems - Keep minimal risk plans simple. … |
| 468 | INSPIR_Task_Change_Approved_Study | Related links | [link] HRPP Policy 7.4.1: requirements for amendment submissions → 7.4.1 | …(hyperlink to HRPP policies page anchor)… |
| 469 | INSPIR_Task_Change_Approved_Study | Attach documents and submit | HRPP Policy 7.4.1.2 | …nt (PDF, file dated November 2023); tracked-protocol requirement from HRPP Policy 7.4.1.2. ## Change study personnel Everyone who will have contact wi… |
| 470 | INSPIR_Task_Change_Approved_Study | If you are changing the PI or Supervising PI | HRPP 6.6.8 | …heets) to show the new PI, even if no new subjects will be consented (HRPP 6.6.8). ### If you are adding or removing people - In Personnel to be added… |
| 471 | INSPIR_Task_Change_Approved_Study | If you are adding or removing people | GCP | …Check both statements: everyone added has current training (including GCP if required), and those responsible for the design, conduct, or repor… |
| 472 | INSPIR_Task_Change_Approved_Study | Add BU Charles River Campus people | HRPP 2.5.2.1 to 2.5.2.3 | …ugh a regular personnel change. Under the global reliance agreements (HRPP 2.5.2.1 to 2.5.2.3), they do not make a separate CRC IRB submission, and no… |
| 473 | INSPIR_Task_Change_Approved_Study | Related links | HRPP Policy 7.4.1 | …otocol Exception Form (PDF) - Required training for study personnel - HRPP Policy 7.4.1: requirements for amendment submissions - Contact the IRB: med… |
| 474 | INSPIR_Task_Checkins_Reports_Closing | Continuing review and status check-ins | HRPP 7.4.3 | …ontinuing Review Form (Progress Report) (PDF, file dated March 2025); HRPP 7.4.3. Alt text: INSPIR Continuing Review Form Selection page. A header sho… |
| 475 | INSPIR_Task_Checkins_Reports_Closing | Continuing review and status check-ins | HRPP 6.6.2.1.5.1 | …nds and all research must stop, even if your response is in progress (HRPP 6.6.2.1.5.1). If a review response is still unanswered 18 months after the … |
| 476 | INSPIR_Task_Checkins_Reports_Closing | Continuing review and status check-ins | HRPP 7.4.6 | … the IRB returned it, the IRB administratively closes the submission (HRPP 7.4.6); INSPIR sends reminders at 60 days, 6 months, and 15 months. Source:… |
| 477 | INSPIR_Task_Checkins_Reports_Closing | Close a study | HRPP 10.2.7.2 | …sure takes effect on the date you submit a properly completed report (HRPP 10.2.7.2). Do not use the Continuing Review Submission Form to close a stud… |
| 478 | INSPIR_Task_Checkins_Reports_Closing | Close a study | HRPP 7.4.4, 10.2.7.2 | …Create and Submit a Final/Closure Report (PDF, file dated June 2025); HRPP 7.4.4, 10.2.7.2. > Close an exempt, Not Human Subjects Research, or Not Eng… |
| 479 | INSPIR_Task_Checkins_Reports_Closing | Close a study | HRPP 6.6.6, 7.4.3.2 | …ources: How To Close an Exempt Study (PDF, file dated November 2023); HRPP 6.6.6, 7.4.3.2. ## Report an event or request an exception For what counts … |
| 480 | INSPIR_Task_Checkins_Reports_Closing | Report an event or request an exception | HRPP 6.6.3.3, 7.3.1, 7.4.5 | …able Events and New Information Form (PDF, file dated November 2023); HRPP 6.6.3.3, 7.3.1, 7.4.5. > Request a protocol exception A protocol exception … |
| 481 | INSPIR_Task_Checkins_Reports_Closing | Report an event or request an exception | HRPP 6.6.4.1, 7.4.2, 10.2.2.4.2.2 | …and Submit a Protocol Exception Form (PDF, file dated November 2023); HRPP 6.6.4.1, 7.4.2, 10.2.2.4.2.2; Be Exception-al (CR Times, January 2025) . ##… |
| 482 | INSPIR_Task_Checkins_Reports_Closing | Recruitment materials and contact information | HRPP 7.3.1, 7.4.1.4 | …ecruitment Materials Submission Form (PDF, file dated November 2023); HRPP 7.3.1, 7.4.1.4. > Change contact information on approved materials Use the … |
| 483 | INSPIR_Task_Checkins_Reports_Closing | Recruitment materials and contact information | HRPP 7.4.1.3 | …Contact Information Change Request Form (PDF, file dated March 2026); HRPP 7.4.1.3; A New Pathway in INSPIR to Change Contact Information (CR Times, D… |
| 484 | INSPIR_Task_Records_and_Training | Where do I find... | Part 11 | … Records \| Get your CITI certificate \| \| The INSPIR software vendor's Part 11 statement (PDF, 2013) \| The software vendor's statement (PDF) \| INS… |
| 485 | INSPIR_Task_Records_and_Training | Approval letters and approved documents | Section 8.3.2 | … used to obtain consent from subjects." HRPP Policies and Procedures, Section 8.3.2, Consent Validation When a study is approved, INSPIR validates the… |
| 486 | INSPIR_Task_Records_and_Training | When you add someone to a study | GCP | … requires Good Clinical Practice training, also check that there is a GCP row with a Status of Active . [CHECK IN INSPIR: the guide text says "… |
| 487 | INSPIR_Task_Records_and_Training | INSPIR and FDA  | Part 11 | …e and Completion Report (PDF, file dated May 2019). ## INSPIR and FDA Part 11: the vendor's statement Sponsors and monitors of FDA-regulated studie… |
| 488 | INSPIR_Task_Records_and_Training | INSPIR and FDA Part 11: the vendor's statement | 21 CFR Part 11 | …PIR meets FDA rules for electronic records and electronic signatures (21 CFR Part 11). The company that makes the INSPIR software has published a stat… |
| 489 | INSPIR_Task_Records_and_Training | INSPIR and FDA Part 11: the vendor's statement | Part 11 | …ds or signatures in another BMC or BU system, you are responsible for Part 11 compliance for that system; see HRPP Policies and Procedures, Section… |
| 490 | INSPIR_Task_Records_and_Training | INSPIR and FDA Part 11: the vendor's statement | Section 12.4.7 | …Part 11 compliance for that system; see HRPP Policies and Procedures, Section 12.4.7, and Drugs and Devices [new site URL] . [UNVERIFIED: confirm the … |
| 491 | INSPIR_Task_Records_and_Training | Related links | Sections 8.3.2 and 12.4.7 | …ng to IRB Stipulations [new site URL] - HRPP Policies and Procedures (Sections 8.3.2 and 12.4.7) - Contact the IRB: medirb@bu.edu , (617) 358-5372 Was… |
| 492 | Clinical_Trials | Clinical Trials at BMC/BUMC: Where to Start | HRPP 6.6.9 | …t is registered on ClinicalTrials.gov and the IRB has the NCT number (HRPP 6.6.9). Register early so registration does not hold up your approval. ## I… |
| 493 | Clinical_Trials | Is my study a clinical trial? | GCP | …e definition BMC/BUMC uses (HRPP section 13). It drives registration, GCP training, and the CRRO consultation. \| \| NIH \| Similar to ICMJE. For … |
| 494 | Clinical_Trials | The path for a trial at BMC/BUMC | HRPP 6.2.1.2 | …; this order avoids delays. - Consult the CRRO (PI-initiated trials). HRPP 6.2.1.2 requires a CRRO consultation as the first step for trials initiated… |
| 495 | Clinical_Trials | The path for a trial at BMC/BUMC | HRPP 7.2.2.20 | …hat must post results on ClinicalTrials.gov need a separate protocol (HRPP 7.2.2.20). Start from the BMC/BUMC protocol template. See Preparing a Compl… |
| 496 | Clinical_Trials | The path for a trial at BMC/BUMC | GCP | …, and other signers. See Ancillary Reviews and Sign-Offs . - Complete GCP training. Everyone who conducts the trial needs current Good Clinical… |
| 497 | Drugs_and_Devices | Guidance | 21 CFR 50 and 56 | …. ## Guidance > Is my study FDA-regulated? FDA's human subject rules (21 CFR 50 and 56) apply to any "clinical investigation" of a drug, biologic, dev… |
| 498 | Drugs_and_Devices | Guidance | 21 CFR 50.3(c) | … biologic, device, or other FDA-regulated product, whoever funds it ( 21 CFR 50.3(c) ). Your study is FDA-regulated if any of these is true: - It test… |
| 499 | Drugs_and_Devices | Guidance | 21 CFR 312.2(d) | …not research. Off-label treatment in ordinary practice needs no IND ( 21 CFR 312.2(d) ). Studying that use does. > Drugs and biologics: IND or exempti… |
| 500 | Drugs_and_Devices | IND exemption criteria | 21 CFR 312.2(b)(1) | …or each criterion, with evidence. \| #### IND exemption criteria Under 21 CFR 312.2(b)(1) , a study of a lawfully marketed drug is exempt only if all … |
| 501 | Drugs_and_Devices | IND exemption criteria | § 312.7 | …The investigation is conducted in compliance with the requirements of § 312.7. Criterion (iii) decides most requests. For each drug, compare your d… |
| 502 | Drugs_and_Devices | IND exemption criteria | HRPP 12.1.3 | …nclear, the IRB may consult the FDA or ask you for FDA documentation (HRPP 12.1.3). > Devices: IDE, exemption, or non-significant risk A study of an u… |
| 503 | Drugs_and_Devices | IND exemption criteria | HRPP 12.2.3 | … or an approved device used for a new indication, needs one of these (HRPP 12.2.3): - An FDA-approved IDE, required for significant risk devices. Give… |
| 504 | Drugs_and_Devices | IND exemption criteria | 21 CFR 812.2(c) | …isk devices. Give the IDE number and holder. - An IDE exemption under 21 CFR 812.2(c) , such as a device used per its cleared or approved labeling, ce… |
| 505 | Drugs_and_Devices | IND exemption criteria | HRPP 12.2.4.1 | …accepts your claim that the device, as used, is non-significant risk (HRPP 12.2.4.1). #### Significant or non-significant risk? Under 21 CFR 812.3(m) … |
| 506 | Drugs_and_Devices | Significant or non-significant risk? | 21 CFR 812.3(m) | …risk (HRPP 12.2.4.1). #### Significant or non-significant risk? Under 21 CFR 812.3(m) , a significant risk device is one that is an implant, supports … |
| 507 | Drugs_and_Devices | Significant or non-significant risk? | HRPP 12.2.4.1 | …e IRB decides at a convened meeting whether to accept your NSR claim (HRPP 12.2.4.1). If the IRB does not accept it and considers the study significan… |
| 508 | Drugs_and_Devices | Significant or non-significant risk? | 21 CFR 812.150(b)(9) | …u (or the sponsor) must report that to the FDA within 5 working days (21 CFR 812.150(b)(9)) and cannot start until the FDA approves an IDE or decides … |
| 509 | Drugs_and_Devices | Significant or non-significant risk? | 21 CFR 812.66 | …dy is NSR. If unsure, you can ask the FDA for a risk determination. ( 21 CFR 812.66 ). If the IRB grants an abbreviated IDE and no company is the spon… |
| 510 | Drugs_and_Devices | Significant or non-significant risk? | 21 CFR 812.2(b) | …ny is the sponsor, the PI is the sponsor and attests to the duties in 21 CFR 812.2(b), explained in the guidance for abbreviated IDE requirements (PDF… |
| 511 | Drugs_and_Devices | Significant or non-significant risk? | HRPP 7.2.2.8.2 | …s not used for diagnosis without confirmation by an established test (HRPP 7.2.2.8.2). Simple venipuncture, and leftover samples from specimens alread… |
| 512 | Drugs_and_Devices | Significant or non-significant risk? | 21 CFR 812.3(k) | … specimens already collected for clinical care, count as noninvasive (21 CFR 812.3(k)). Cleared or approved devices used as labeled are IDE exempt but… |
| 513 | Drugs_and_Devices | Significant or non-significant risk? | 21 CFR 814.3 | … condition affecting no more than 8,000 people in the U.S. per year ( 21 CFR 814.3 ), and may be used only where an IRB has approved its use. Submit a… |
| 514 | Drugs_and_Devices | Significant or non-significant risk? | 21 CFR 814 | …Is this application for an FDA approved Humanitarian Use Device under 21 CFR 814?"; the application then shows the Devices section and the "IRB Approv… |
| 515 | Drugs_and_Devices | Significant or non-significant risk? | 21 CFR 814.124(a) | …) with the patient's identification, the date of use, and the reason (21 CFR 814.124(a); HRPP 12.4.4), and request non-emergency off-label use as a pr… |
| 516 | Drugs_and_Devices | Significant or non-significant risk? | HRPP 12.4.4 | …s identification, the date of use, and the reason (21 CFR 814.124(a); HRPP 12.4.4), and request non-emergency off-label use as a protocol exception (H… |
| 517 | Drugs_and_Devices | Significant or non-significant risk? | HRPP 12.4.5 | ….4), and request non-emergency off-label use as a protocol exception (HRPP 12.4.5). For step-by-step instructions, see Humanitarian Use Devices . > Tr… |
| 518 | Drugs_and_Devices | Significant or non-significant risk? | 21 CFR 56.104(c) | …al), and report the use to the IRB in writing within 5 working days ( 21 CFR 56.104(c) ) by submitting an Emergency Use report in INSPIR. Follow the g… |
| 519 | Drugs_and_Devices | Significant or non-significant risk? | HRPP 12.3.3 | …ss the emergency exception criteria are met and certified in writing (HRPP 12.3.3). Emergency use of devices follows similar rules (HRPP 12.3.2). For … |
| 520 | Drugs_and_Devices | Significant or non-significant risk? | HRPP 12.3.2 | …riting (HRPP 12.3.3). Emergency use of devices follows similar rules (HRPP 12.3.2). For step-by-step instructions, see Expanded Access and Emergency U… |
| 521 | Drugs_and_Devices | Significant or non-significant risk? | HRPP 8.1.3.7 | …, benefits, and alternatives unless the IRB approves another process (HRPP 8.1.3.7). - Costs and Compensation for Injury. Use the consent template lan… |
| 522 | Drugs_and_Devices | Significant or non-significant risk? | HRPP 6.2.1.2 | …ials. PI-initiated trials need a CRRO consultation before submission (HRPP 6.2.1.2). A separate protocol is required for drug, biologic, device, and s… |
| 523 | Drugs_and_Devices | Significant or non-significant risk? | HRPP 7.2.2.20 | …ed trial, and any study that must post results on ClinicalTrials.gov (HRPP 7.2.2.20). The whole team needs Good Clinical Practice (GCP) training, rene… |
| 524 | Drugs_and_Devices | Significant or non-significant risk? | GCP | …als.gov (HRPP 7.2.2.20). The whole team needs Good Clinical Practice (GCP) training, renewed every three years (HRPP 6.2.3). The trial must be … |
| 525 | Drugs_and_Devices | Significant or non-significant risk? | HRPP 6.2.3 | …eds Good Clinical Practice (GCP) training, renewed every three years (HRPP 6.2.3). The trial must be registered on ClinicalTrials.gov before final app… |
| 526 | Drugs_and_Devices | Significant or non-significant risk? | HRPP 6.6.9 | …trial must be registered on ClinicalTrials.gov before final approval (HRPP 6.6.9). See ClinicalTrials.gov Registration and Consent Posting . - Electro… |
| 527 | Drugs_and_Devices | Significant or non-significant risk? | 21 CFR Part 11 | …. - Electronic records and signatures, including e-consent, must meet 21 CFR Part 11 (HRPP 12.4.7). See BU REDCap's Part 11 process and training and O… |
| 528 | Drugs_and_Devices | Significant or non-significant risk? | HRPP 12.4.7 | …ecords and signatures, including e-consent, must meet 21 CFR Part 11 (HRPP 12.4.7). See BU REDCap's Part 11 process and training and Obtaining Consent… |
| 529 | Drugs_and_Devices | Significant or non-significant risk? | Part 11 | …ng e-consent, must meet 21 CFR Part 11 (HRPP 12.4.7). See BU REDCap's Part 11 process and training and Obtaining Consent . - Commercial IRBs. BMC/B… |
| 530 | Drugs_and_Devices | Significant or non-significant risk? | 312.2(b)(1) | …ndence. \| \| IND exemption request \| Drug-by-drug justification of the 312.2(b)(1) criteria, with references. \| \| Every device study \| Device bro… |
| 531 | Drugs_and_Devices | Questions | FDA guidance | …fore IRB approval if you hold the IND or IDE; the page also lists key FDA guidance. - CRRO consultation : CRRO helps sponsor-investigators with initia… |
| 532 | Drug_Device_Decision_Guide | Guidance | 21 CFR 312.2(d) | …ff-label treatment in practice needs no IND; studying that use does ( 21 CFR 312.2(d) ). > Drug and biologic steps (IND) Work through the steps for ev… |
| 533 | Drug_Device_Decision_Guide | Guidance | 21 CFR 312.2 | …only make a research procedure possible. Does this drug need an IND? (21 CFR 312.2) \| Step \| Question \| If yes \| If no \| \| Drug step 1 \| Does t… |
| 534 | Drug_Device_Decision_Guide | Guidance | 312.2(b)(5) | …ion: a placebo-only study that otherwise needs no IND is exempt under 312.2(b)(5). \| \| Drug step 3 \| Will you use it exactly as labeled: same indic… |
| 535 | Drug_Device_Decision_Guide | Guidance | 312.2(b)(1) | … IND exempt (outcome B). \| \| Drug step 5 \| Can you show that all five 312.2(b)(1) criteria are met, including that the off-label dose, route, or po… |
| 536 | Drug_Device_Decision_Guide | Guidance | 21 CFR 312.2(b)(1)(iii) | …tability of the risks) associated with the use of the drug product" ( 21 CFR 312.2(b)(1)(iii) ). The full list of criteria is on Drugs, Biologics, and… |
| 537 | Drug_Device_Decision_Guide | Guidance | HRPP 6.2.3.1 | …om the Clinical Research Resources Office (CRRO) before IRB approval (HRPP 6.2.3.1). Studies under an IND are reviewed by the convened IRB (HRPP 12.1.… |
| 538 | Drug_Device_Decision_Guide | Guidance | HRPP 12.1.1 | …HRPP 6.2.3.1). Studies under an IND are reviewed by the convened IRB (HRPP 12.1.1). > Device steps (IDE) Does this device study need an IDE? (21 CFR 8… |
| 539 | Drug_Device_Decision_Guide | Guidance | 21 CFR 812.2 and 812.3(m) | …PP 12.1.1). > Device steps (IDE) Does this device study need an IDE? (21 CFR 812.2 and 812.3(m)) \| Step \| Question \| If yes \| If no \| \| Device s… |
| 540 | Drug_Device_Decision_Guide | Guidance | 812.2(c) | …its risk (outcome E). \| \| Device step 3 \| Does it fit an exemption in 812.2(c)? The common ones: a cleared or approved device used within its label… |
| 541 | Drug_Device_Decision_Guide | Guidance | 812.3(m) | …otential for serious risk, or otherwise a potential for serious risk (812.3(m))? \| FDA IDE needed (outcome D). \| Ask the IRB for a non-significant r… |
| 542 | Drug_Device_Decision_Guide | Guidance | 21 CFR 812.66 | …n NSR request, the study cannot start until the FDA approves an IDE ( 21 CFR 812.66 ). If that happens, you (or the sponsor) must tell the FDA within … |
| 543 | Drug_Device_Decision_Guide | Guidance | 21 CFR 812.150(b)(9) | …appens, you (or the sponsor) must tell the FDA within 5 working days (21 CFR 812.150(b)(9)) and ask the FDA about the device's status (HRPP 12.2.6). T… |
| 544 | Drug_Device_Decision_Guide | Guidance | HRPP 12.2.6 | …ays (21 CFR 812.150(b)(9)) and ask the FDA about the device's status (HRPP 12.2.6). The FDA's risk determination is final. If the IRB grants an abbrev… |
| 545 | Drug_Device_Decision_Guide | Guidance | 21 CFR 812.2(b)(1) | …company is the sponsor, you are the sponsor and take on the duties in 21 CFR 812.2(b)(1) (HRPP 12.2.4). > What to attach at each outcome Outcomes, wha… |
| 546 | Drug_Device_Decision_Guide | Guidance | HRPP 12.2.4 | …or, you are the sponsor and take on the duties in 21 CFR 812.2(b)(1) (HRPP 12.2.4). > What to attach at each outcome Outcomes, what to answer in INSPI… |
| 547 | Drug_Device_Decision_Guide | Guidance | FDA guidance on studies without an IND and on significant and nonsignificant risk device stu | …IRB risk determination; device brochure. \| Still unsure? Ask the FDA; FDA guidance on studies without an IND and on significant and nonsignificant ri… |
| 548 | Drug_Device_Decision_Guide | Guidance | FDA guidance | …al site from NIH-funded academic research centers. It is not official FDA guidance; where it differs from BMC/BUMC policy, follow BMC/BUMC policy. - F… |
| 549 | Radiation_in_Research | Guidance | Section 7.2.2.16.5 | …nformation for every radiation study ( HRPP Policies and Procedures , Section 7.2.2.16.5). Describe the same exams everywhere they appear. The IRB wil… |
| 550 | Radiation_in_Research | Guidance | HRPP 9.4.8 | …ast risk and describe added protections, including pregnancy testing (HRPP 9.4.8). > Level of IRB review, ceded studies, and changes - Review level. T… |
| 551 | Radiation_in_Research | Guidance | Common Rule | …ent protections (no external funding and not otherwise subject to the Common Rule or FDA rules): a single exposure in adults with an effective dose no… |
| 552 | Radiation_in_Research | Guidance | Section 10.2.2.4.1.3 | …with an effective dose no higher than 0.1 mSv, about one chest x-ray (Section 10.2.2.4.1.3). See Expedited and Full Board Review . - Ceded studies. Wh… |
| 553 | Radiation_in_Research | Guidance | 21 CFR 361.1 | …and may need an FDA Investigational New Drug application (IND). Under 21 CFR 361.1 , some basic research (on metabolism, physiology, or biochemistry, … |
| 554 | Radiation_in_Research | Related links | 21 CFR 361.1 | … Policies and Procedures (sections 7.2.2.2, 7.2.2.16.5, 10.2.2.4.1) - 21 CFR 361.1, Radioactive Drug Research Committees (eCFR) Was this page helpful?… |
| 555 | Expanded_Access_Emergency_Use | Expanded Access and Emergency Use of Investigational Product | HRPP 12.3.1 | … describe the outcome as research or include it in a research report (HRPP 12.3.1). If you want to study the product, you need a research protocol and… |
| 556 | Expanded_Access_Emergency_Use | Which path applies | 21 CFR 312.310(d) | …ore treatment; the written submission follows within 15 working days (21 CFR 312.310(d)). \| Notice to the IRB beforehand if possible (not approval), … |
| 557 | Expanded_Access_Emergency_Use | Guidance | 21 CFR 312.305 and 312.310 | …r drugs and biologics, the FDA must find that all of these are true ( 21 CFR 312.305 and 312.310 ): - The patient has a serious or immediately life-th… |
| 558 | Expanded_Access_Emergency_Use | Guidance | 21 CFR 56.102(d) | …ment is available, and there is not enough time to get IRB approval ( 21 CFR 56.102(d) ). If treatment can wait a few days for IRB review, use the non… |
| 559 | Expanded_Access_Emergency_Use | Guidance | 21 CFR 312.310 | …de the product. The treating physician must be a licensed physician ( 21 CFR 312.310 ). If that physician is a resident or fellow, INSPIR requires a S… |
| 560 | Expanded_Access_Emergency_Use | Guidance | HRPP 6.1.3.4 | …dent or fellow, INSPIR requires a Supervising Principal Investigator (HRPP 6.1.3.4). > Non-emergency: individual patient IND (drugs and biologics) - A… |
| 561 | Expanded_Access_Emergency_Use | Guidance | HRPP 12.3.1 | …he Emergency Use report in INSPIR within 5 working days of treatment (HRPP 12.3.1). In Review Path Determination, choose "None of the above," then ans… |
| 562 | Expanded_Access_Emergency_Use | Guidance | HRPP 12.3.4 | …pproval. If it did not, the IRB follows its noncompliance procedures (HRPP 12.3.4). One emergency use of a product at BMC/BUMC without prior review. A… |
| 563 | Expanded_Access_Emergency_Use | Guidance | 21 CFR 56.104(c) | … at BMC/BUMC, for this or any other patient, needs IRB review first ( 21 CFR 56.104(c) ). If treatment will continue, contact the IRB right away about… |
| 564 | Expanded_Access_Emergency_Use | Guidance | HRPP 12.3.2 | …lly acceptable alternative, and there is no time to get IRB approval (HRPP 12.3.2). If time allows, notify the IRB Director (medirb@bu.edu) and get th… |
| 565 | Expanded_Access_Emergency_Use | Guidance | 21 CFR 50.25 | …onsent Template as is; it already contains the FDA-required elements (21 CFR 50.25). A clinical procedure consent alone does not. - Children: obtain p… |
| 566 | Expanded_Access_Emergency_Use | Guidance | 21 CFR 50.23 | … an emergency, consent may be skipped only if all of these are true ( 21 CFR 50.23 ; HRPP 12.3.3): - The patient faces a life-threatening situation re… |
| 567 | Expanded_Access_Emergency_Use | Guidance | HRPP 12.3.3 | …consent may be skipped only if all of these are true ( 21 CFR 50.23 ; HRPP 12.3.3): - The patient faces a life-threatening situation requiring the pro… |
| 568 | Expanded_Access_Emergency_Use | Guidance | 21 CFR 312.310(c)(2) | … 15. \| \| FDA \| Written summary of results, including adverse effects (21 CFR 312.310(c)(2)); annual reports while the IND is active. \| At the end … |
| 569 | Expanded_Access_Emergency_Use | Related links | FDA guidance: IRB Review of Individual Patient Expanded Access Submissions (2023) | … - FDA: Expanded Access - FDA: Expanded Access information for IRBs - FDA guidance: IRB Review of Individual Patient Expanded Access Submissions (2023… |
| 570 | Humanitarian_Use_Devices | Humanitarian Use Devices (HUD) | 21 CFR 814.3 | …dition that affects no more than 8,000 people in the U.S. each year ( 21 CFR 814.3 ). Its effectiveness has not been shown, so federal law allows its … |
| 571 | Humanitarian_Use_Devices | HUD use at BMC in 5 steps | 21 CFR 814 | …Is this application for an FDA approved Humanitarian Use Device under 21 CFR 814?" Complete the Devices section and the IRB Approval for Humanitarian … |
| 572 | Humanitarian_Use_Devices | HUD use at BMC in 5 steps | HRPP 12.4.2 | …B approval before first use. Initial approval is by the convened IRB (HRPP 12.4.2). Do not use the device until you have the approval letter, except i… |
| 573 | Humanitarian_Use_Devices | Guidance | HRPP 7.2.2.23 | …et. \| The HUD application has no question on costs or HUD status, but HRPP 7.2.2.23 requires both. Say in the Proposed Treatment Plan how device and … |
| 574 | Humanitarian_Use_Devices | Guidance | HRPP 12.4.3 | …e of a HUD, and the IRB does not review the clinical consent process (HRPP 12.4.3). Patients still need to understand what they are receiving. Follow … |
| 575 | Humanitarian_Use_Devices | Guidance | FDA guidance suggests written information covering what the device is for, how it is used, r | …nt or only some) and who gives it. If the manufacturer has no packet, FDA guidance suggests written information covering what the device is for, how i… |
| 576 | Humanitarian_Use_Devices | Guidance | HRPP 12.4.2 | … may set limits such as which patients qualify or required follow-up. HRPP 12.4.2: "The progress report must indicate how many patients have been trea… |
| 577 | Humanitarian_Use_Devices | Guidance | HRPP 12.4.6 | …turer, and a serious injury to the manufacturer, within 10 work days (HRPP 12.4.6; 21 CFR 803.30 ). Report these events promptly through BMC's safety … |
| 578 | Humanitarian_Use_Devices | Guidance | 21 CFR 803.30 | …serious injury to the manufacturer, within 10 work days (HRPP 12.4.6; 21 CFR 803.30 ). Report these events promptly through BMC's safety event process… |
| 579 | Humanitarian_Use_Devices | Guidance | 21 CFR 814.126(a) | …lso require medical device reports about a HUD to be sent to the IRB (21 CFR 814.126(a)). [UNVERIFIED: whether the IRB also wants a Reportable Event s… |
| 580 | Humanitarian_Use_Devices | Guidance | 21 CFR 814.124(a) | …te of use, and the reason. Federal rules require this within 5 days ( 21 CFR 814.124(a) ; HRPP 12.4.4). Off-label use. Once the IRB has approved a HUD… |
| 581 | Humanitarian_Use_Devices | Guidance | HRPP 12.4.4 | …eason. Federal rules require this within 5 days ( 21 CFR 814.124(a) ; HRPP 12.4.4). Off-label use. Once the IRB has approved a HUD, a physician may us… |
| 582 | Humanitarian_Use_Devices | Guidance | HRPP 12.4.5 | … HDE holder beforehand and send it a follow-up report on the patient (HRPP 12.4.5). > Research with a HUD Treating patients under the HUD approval is … |
| 583 | Humanitarian_Use_Devices | Guidance | HRPP 12.2.4.1 | …onvened meeting, whether it will accept a non-significant risk claim (HRPP 12.2.4.1). Only the FDA makes FDA determinations. - Reviewing records of pa… |
| 584 | Humanitarian_Use_Devices | Related links | FDA guidance: Humanitarian Device Exemption (HDE) Program (September 2019) | …s (sections 7.2.2.23 and 12.4) - FDA: Humanitarian Device Exemption - FDA guidance: Humanitarian Device Exemption (HDE) Program (September 2019) - 21 … |
| 585 | Humanitarian_Use_Devices | Related links | 21 CFR 814 | …dance: Humanitarian Device Exemption (HDE) Program (September 2019) - 21 CFR 814 Subpart H: Humanitarian Use Devices - Does My Study Need an IND or ID… |
| 586 | ClinicalTrials_gov | Guidance | 42 CFR Part 11 | … the rule the IRB applies at approval. \| \| Federal law (FDAAA 801 and 42 CFR Part 11) \| "Applicable clinical trials": most controlled trials of FDA… |
| 587 | ClinicalTrials_gov | Guidance | NIH policy / Every clinical trial funded in whole or in part by NIH, i | … of FDA-regulated devices (other than small feasibility studies). \| \| NIH policy \| Every clinical trial funded in whole or in part by NIH, includin… |
| 588 | ClinicalTrials_gov | Change for NIH-funded basic experimental studies (BESH) | 42 CFR Part 11 | …for BMC/BUMC studies \| Step \| BMC/BUMC requirement \| Federal minimum (42 CFR Part 11) \| \| Register \| Before final IRB approval \| Within 21 cale… |
| 589 | ClinicalTrials_gov | Change for NIH-funded basic experimental studies (BESH) | 45 CFR 46.116(h) | …er than 60 days after the last study visit by any participant \| Same (45 CFR 46.116(h)) \| \| Leave BMC/BU with an active record \| Contact the PRS A… |
| 590 | ClinicalTrials_gov | Change for NIH-funded basic experimental studies (BESH) | 42 CFR 11.66 | …is a federal grantee, withholding of remaining or future grant funds (42 CFR 11.66). > What the IRB checks - The clinical trial answer. Whether your a… |
| 591 | ClinicalTrials_gov | The required consent statement | 21 CFR 50.25(c) | …age and posting #### The required consent statement FDA regulations ( 21 CFR 50.25(c) ) require this exact statement in the consent form for applicabl… |
| 592 | ClinicalTrials_gov | Posting a consent form ( | Common Rule | …clinical trials. See Consent Templates . #### Posting a consent form (Common Rule) For clinical trials conducted or supported by a federal department … |
| 593 | ClinicalTrials_gov | Posting a consent form (Common Rule) | Common Rule | … trials conducted or supported by a federal department or agency, the Common Rule requires posting one consent form ( 45 CFR 46.116(h) ): "(1) For eac… |
| 594 | ClinicalTrials_gov | Posting a consent form (Common Rule) | 45 CFR 46.116(h) | …rtment or agency, the Common Rule requires posting one consent form ( 45 CFR 46.116(h) ): "(1) For each clinical trial conducted or supported by a Fed… |
| 595 | ClinicalTrials_gov | Posting a consent form (Common Rule) | 2018 Requirements | …45 CFR 46.116(h). If your federally funded study is BESH, read OHRP's 2018 Requirements FAQs and ask the PRS Administrator how it applies to you. [UNV… |
| 596 | ClinicalTrials_gov | Posting a consent form (Common Rule) | HRPP 6.2.1.2 | …ission, or obtain a waiver of this requirement from the IRB Director (HRPP 6.2.1.2); the INSPIR application asks for the date of that consultation. > … |
| 597 | ClinicalTrials_gov | Related links | 42 CFR Part 11 | …ov - NIH clinical trial requirements [UNVERIFIED: link not fetched] - 42 CFR Part 11, clinical trials registration and results (eCFR) - Does My Study … |
| 598 | Genetics_Biospecimens_Repositories | Guidance | GINA | …ection. \| Future use, genetic risks, return of results; Massachusetts GINA language when required. \| \| Return results or findings \| Your return … |
| 599 | Genetics_Biospecimens_Repositories |  | GINA | …the language, including a paragraph for whole genome sequencing. #### GINA and Massachusetts law The federal Genetic Information Nondiscriminati… |
| 600 | Genetics_Biospecimens_Repositories | GINA and Massachusetts law | Genetic Information Nondiscrimination Act | … whole genome sequencing. #### GINA and Massachusetts law The federal Genetic Information Nondiscrimination Act (GINA) limits how health insurers and … |
| 601 | Genetics_Biospecimens_Repositories | GINA and Massachusetts law | GINA | …sachusetts law The federal Genetic Information Nondiscrimination Act (GINA) limits how health insurers and employers with 15 or more employees c… |
| 602 | Genetics_Biospecimens_Repositories | GINA and Massachusetts law | M.G.L. c. 151B | …ends the employment protection to employers with 6 or more employees (M.G.L. c. 151B, sections 1 and 4(19)). The template's genetic risk paragraph cov… |
| 603 | Genetics_Biospecimens_Repositories | GINA and Massachusetts law | M.G.L. c. 111 | …INA language to add the Massachusetts information. Massachusetts law (M.G.L. c. 111, section 70G) also sets written consent rules for genetic testing,… |
| 604 | Genetics_Biospecimens_Repositories | GINA and Massachusetts law | HRPP 7.2.2.7.2.3 | …up, and whether participants can choose not to receive some findings (HRPP 7.2.2.7.2.3). CLIA. Federal CLIA rules apply to labs that report patient-sp… |
| 605 | Genetics_Biospecimens_Repositories | What the IRB needs | HRPP 7.2.2.16.4 | …alysis that is in addition to that required for the study endpoints" (HRPP 7.2.2.16.4). Repository or retention? \|  \| Repository (sole purpose) \| S… |
| 606 | Genetics_Biospecimens_Repositories | What the Retention of Samples or Data section asks | GINA | …ed for research or leftovers will be kept. - Federal-only or outdated GINA language, especially in sponsor consent forms. - A results plan that … |
| 607 | Genetics_Biospecimens_Repositories | Related links | GINA | …- NIH Data Management and Sharing Policy - Genetic discrimination and GINA (National Human Genome Research Institute) - Massachusetts General La… |
| 608 | Remote_Decentralized_Research | Guidance | Section 9.7.2 | …ol, day care, or nursing home" BMC/BUMC HRPP Policies and Procedures, Section 9.7.2 > Kits, devices, and study drugs sent to participants If you will … |
| 609 | Remote_Decentralized_Research | Guidance | 21 CFR Part 11 | …Electronic records and signatures in FDA-regulated research must meet 21 CFR Part 11. See Remote and electronic consent and the 'Documentation of elec… |
| 610 | Deception_Incomplete_Disclosure | Deception and Incomplete Disclosure | 45 CFR 46.116(f)(3) | …lteration of consent, which is allowed only in minimal risk research (45 CFR 46.116(f)(3)). For FDA-regulated studies, 21 CFR 50.22 (in effect since J… |
| 611 | Deception_Incomplete_Disclosure | Deception and Incomplete Disclosure | 21 CFR 50.22 | …nimal risk research (45 CFR 46.116(f)(3)). For FDA-regulated studies, 21 CFR 50.22 (in effect since January 22, 2024) allows a similar waiver or alter… |
| 612 | Deception_Incomplete_Disclosure | Non-exempt studies: alteration or waiver of consent | 45 CFR 46.116(f)(3) | … or an alteration of informed consent," and that all five criteria in 45 CFR 46.116(f)(3) must be met. The criteria are listed on Obtaining Informed C… |
| 613 | Deception_Incomplete_Disclosure | Non-exempt studies: alteration or waiver of consent | HRPP 8.4.3 | …eater risk. For FDA-regulated studies, ask the IRB before you submit; HRPP 8.4.3 describes how the IRB handles minimal risk FDA studies. #### Exempt s… |
| 614 | Deception_Incomplete_Disclosure | Exempt studies: category 3 or local category 13, with advanc | 45 CFR 46.104(d)(3)(iii) | …adults; 3.1 anonymous, 3.2 identifiable) only under this condition in 45 CFR 46.104(d)(3)(iii) : "If the research involves deceiving the subjects rega… |
| 615 | Deception_Incomplete_Disclosure | Exempt studies: category 3 or local category 13, with advanc | HRPP 8.4.3 | … the opportunity to decline to have their data used in the research" (HRPP 8.4.3). - Timing. Usually right after each person's participation ends. A l… |
| 616 | Deception_Incomplete_Disclosure | Related links | 45 CFR 46.116 | …and Procedures (sections 7.2.2.14.1, 8.4.3, 10.2.4.2.1.2, 10.2.4.3) - 45 CFR 46.116, informed consent (eCFR) - 45 CFR 46.104, exempt research (eCFR) -… |
| 617 | Deception_Incomplete_Disclosure | Related links | 45 CFR 46.104 | …3, 10.2.4.2.1.2, 10.2.4.3) - 45 CFR 46.116, informed consent (eCFR) - 45 CFR 46.104, exempt research (eCFR) - American Psychological Association Ethic… |
| 618 | Research_Involving_Children | Research Involving Children | M.G.L. c. 231 | …n In Massachusetts, anyone under 18 is a child for research purposes (M.G.L. c. 231, s. 85P). A minor who can legally consent to the care involved in … |
| 619 | Research_Involving_Children | Guidance | M.G.L. c. 112 | …for sexually transmitted infections or (from age 12) drug dependency (M.G.L. c. 112, s. 12F; for drug dependency from age 12, s. 12E). That does not a… |
| 620 | Research_Involving_Children | Guidance | HRPP 9.2.4.4 | …cides case by case whether such a minor may consent without a parent (HRPP 9.2.4.4), so say so in your application if you expect to enroll them (the f… |
| 621 | Research_Involving_Children | Guidance | 45 CFR 46.404 | …o must give permission \| Review \| \| 1. No greater than minimal risk \| 45 CFR 46.404; 21 CFR 50.51 \| Risk is no more than minimal. \| Usually one … |
| 622 | Research_Involving_Children | Guidance | 21 CFR 50.51 | …mission \| Review \| \| 1. No greater than minimal risk \| 45 CFR 46.404; 21 CFR 50.51 \| Risk is no more than minimal. \| Usually one \| Expedited or… |
| 623 | Research_Involving_Children | Guidance | 45 CFR 46.405 | …B \| \| 2. Greater than minimal risk, with prospect of direct benefit \| 45 CFR 46.405; 21 CFR 50.52 \| Risk is justified by the expected benefit, and… |
| 624 | Research_Involving_Children | Guidance | 21 CFR 50.52 | …r than minimal risk, with prospect of direct benefit \| 45 CFR 46.405; 21 CFR 50.52 \| Risk is justified by the expected benefit, and the balance is a… |
| 625 | Research_Involving_Children | Guidance | 45 CFR 46.406 | … 3. Minor increase over minimal risk, no prospect of direct benefit \| 45 CFR 46.406; 21 CFR 50.53 \| Only a minor increase over minimal risk; experie… |
| 626 | Research_Involving_Children | Guidance | 21 CFR 50.53 | …ase over minimal risk, no prospect of direct benefit \| 45 CFR 46.406; 21 CFR 50.53 \| Only a minor increase over minimal risk; experiences similar to… |
| 627 | Research_Involving_Children | Guidance | 45 CFR 46.407 | …h limited exceptions \| Convened IRB \| \| 4. Not otherwise approvable \| 45 CFR 46.407; 21 CFR 50.54 \| A reasonable opportunity to understand, preve… |
| 628 | Research_Involving_Children | Guidance | 21 CFR 50.54 | …tions \| Convened IRB \| \| 4. Not otherwise approvable \| 45 CFR 46.407; 21 CFR 50.54 \| A reasonable opportunity to understand, prevent, or alleviat… |
| 629 | Research_Involving_Children | Guidance | HRPP 9.2.2 | … research can be approved through expedited review at initial review (HRPP 9.2.2). Category 3 research must be about the children's own disorder or co… |
| 630 | Research_Involving_Children | One parent or two | HRPP 9.2.4.5 | … two The IRB decides whether one or two parents must give permission (HRPP 9.2.4.5). One parent is usually enough for Categories 1 and 2, although the… |
| 631 | Research_Involving_Children | One parent or two | HRPP 2.1.2 | …or equivalent protections (no external funding, no FDA oversight; see HRPP 2.1.2), the IRB may decide one parent is enough (HRPP 9.2.4.5). When the IR… |
| 632 | Research_Involving_Children | Waiving or altering parental permission | 45 CFR 46.408(c) | …dent advocate, takes its place and the waiver is consistent with law (45 CFR 46.408(c)). - FDA-regulated studies (drugs, devices, biologics) cannot us… |
| 633 | Research_Involving_Children | Waiving or altering parental permission | 21 CFR 50.55 | …regulated studies (drugs, devices, biologics) cannot use this waiver; 21 CFR 50.55 has no equivalent. > Child assent Assent is a child's affirmative a… |
| 634 | Research_Involving_Children | When assent is needed | HRPP 9.2.4.3 | …ho cannot assent should still get an explanation they can understand (HRPP 9.2.4.3). #### How BMC/BUMC documents assent - The person who conducts the … |
| 635 | Research_Involving_Children | Tips for the parent forms | HRPP 9.2.4.2 | … a legally authorized representative's consent if they lack capacity (HRPP 9.2.4.2). Your application must say how and when. If you want to keep using… |
| 636 | Research_Involving_Children | Tips for the parent forms | HRPP 12.5 | …tion records must meet the Family Educational Rights and Privacy Act (HRPP 12.5); surveys in schools that receive U.S. Department of Education fundin… |
| 637 | Research_Involving_Children | Tips for the parent forms | HRPP 12.6 | …tion funding may fall under the Protection of Pupil Rights Amendment (HRPP 12.6). [UNVERIFIED: whether the IRB requires a letter of support from the … |
| 638 | Research_Involving_Children | Tips for the parent forms | M.G.L. c. 119 | …hers) must report suspected abuse or neglect under Massachusetts law (M.G.L. c. 119, s. 51A). With adolescents, also decide in advance what you will t… |
| 639 | Research_Involving_Children | Tips for the parent forms | HRPP 9.2.3 | …hen the parents cannot be located or parental rights are being ended (HRPP 9.2.3). Wards can be enrolled in Category 3 or 4 research only if the resea… |
| 640 | Research_Involving_Children | Tips for the parent forms | 45 CFR 46.409 | …als, or similar settings where most child participants are not wards (45 CFR 46.409). The IRB will then require an independent advocate for each ward.… |
| 641 | Research_Involving_Children | Tips for the parent forms | HRPP 10.2.4.3 | …as an abbreviated consent, and given a chance to opt their child out (HRPP 10.2.4.3). \| \| Educational tests, or observing public behavior without ta… |
| 642 | Research_Involving_Children | Tips for the parent forms | HRPP 10.2.4.2.2 and 10.2.4.3 | …and child assent with the same information as an abbreviated consent (HRPP 10.2.4.2.2 and 10.2.4.3). \| \| Benign behavioral interventions (category 3… |
| 643 | Research_Involving_Children | Related links | 45 CFR 46 Subpart D | …ity - BMC/BUMC HRPP Policies and Procedures (section 9.2, Children) - 45 CFR 46 Subpart D, protections for children (eCFR) - 21 CFR 50 Subpart D, chil… |
| 644 | Research_Involving_Children | Related links | 21 CFR 50 Subpart D | …2, Children) - 45 CFR 46 Subpart D, protections for children (eCFR) - 21 CFR 50 Subpart D, children in FDA-regulated research (eCFR) - OHRP guidance o… |
| 645 | Research_Involving_Children | Related links | OHRP guidance on research with children | …R) - 21 CFR 50 Subpart D, children in FDA-regulated research (eCFR) - OHRP guidance on research with children - Mandated Reporting and Safety Plans Wa… |
| 646 | Special_Populations | Quick reference | Subpart B | …uses, neonates \| All research funded by a federal agency that applies Subpart B; otherwise, research that is more than minimal risk to the pregnant p… |
| 647 | Special_Populations | Quick reference | HRPP 9.4 | …r this group, the risks to the pregnancy, and who will give consent \| HRPP 9.4; 45 CFR 46 Subpart B \| \| People who could become pregnant \| Any non… |
| 648 | Special_Populations | Quick reference | 45 CFR 46 Subpart B | …up, the risks to the pregnancy, and who will give consent \| HRPP 9.4; 45 CFR 46 Subpart B \| \| People who could become pregnant \| Any non-exempt st… |
| 649 | Special_Populations | Quick reference | HRPP 7.2.2.10, 9.4.8 | …requirements (if any), and what happens if someone becomes pregnant \| HRPP 7.2.2.10, 9.4.8 \| \| Adults lacking capacity to consent \| Any study that… |
| 650 | Special_Populations | Quick reference | HRPP 9.5 | …authorized representative (LAR) will be, and how assent is obtained \| HRPP 9.5 \| \| Prisoners \| Any non-exempt study that enrolls them, and any stu… |
| 651 | Special_Populations | Quick reference | HRPP 9.3 | …\| The permitted research category and the protections for prisoners \| HRPP 9.3; 45 CFR 46 Subpart C \| ## Pregnancy and people who could become preg… |
| 652 | Special_Populations | Quick reference | 45 CFR 46 Subpart C | …itted research category and the protections for prisoners \| HRPP 9.3; 45 CFR 46 Subpart C \| ## Pregnancy and people who could become pregnant > Whic… |
| 653 | Special_Populations | Pregnancy and people who could become pregnant | Subpart B | …out pregnancy or targets pregnant people: check both, and address the Subpart B criteria below. Boxes marked ** (including "Pregnant persons**" and "… |
| 654 | Special_Populations | Pregnancy and people who could become pregnant | HRPP 9.4.1 | … is more than minimal risk to the pregnant person, fetus, or neonate (HRPP 9.4.1). When they apply, the IRB must find that: - where scientifically app… |
| 655 | Special_Populations | Pregnancy and people who could become pregnant | HRPP 9.4.3 | …; for other research, the IRB decides whether that consent is needed (HRPP 9.4.3). The IRB decides whether a pregnant minor may consent for themselves… |
| 656 | Special_Populations | Pregnancy and people who could become pregnant | HRPP 9.4.4 | … part in decisions about ending a pregnancy or a neonate's viability (HRPP 9.4.4). Research on neonates, fetuses, fetal tissue, or the placenta has fu… |
| 657 | Special_Populations | Pregnancy and people who could become pregnant | HRPP 9.4.5 to 9.4.7 | …ssue, or the placenta has further rules, including Massachusetts law (HRPP 9.4.5 to 9.4.7); contact the IRB early. > Including or excluding pregnant p… |
| 658 | Special_Populations | Pregnancy and people who could become pregnant | HRPP 9.4.8 | …y the risk and describe extra protections, such as pregnancy testing (HRPP 9.4.8). > Contraception, lactation, and pregnancy during the study Contrace… |
| 659 | Special_Populations | Pregnancy and people who could become pregnant | HRPP 9.4.9 | …ormation. They must sign a HIPAA authorization before you collect it (HRPP 9.4.9). See HIPAA in Research . ## Adults lacking capacity to consent Adult… |
| 660 | Special_Populations | Adults lacking capacity to consent | HRPP 9.5 | … and the person's own agreement (assent) is sought whenever possible (HRPP 9.5). > When the IRB can approve it The IRB approves research with adults… |
| 661 | Special_Populations | Adults lacking capacity to consent | HRPP 9.5.1 | …y they must be included, and the risk falls into one of these groups (HRPP 9.5.1): - no more than minimal risk; - more than minimal risk with the pros… |
| 662 | Special_Populations | Adults lacking capacity to consent | HRPP 9.5.2 | …r research in Massachusetts, the IRB ordinarily allows the following (HRPP 9.5.2). This list is BMC/BUMC policy, not a Massachusetts statute, so it do… |
| 663 | Special_Populations | Adults lacking capacity to consent | HRPP 8.4.4 | …ther the person nor an LAR can consent in time follow separate rules (HRPP 8.4.4; for FDA-regulated studies, 21 CFR 50.24 ). Contact the IRB well befo… |
| 664 | Special_Populations | Adults lacking capacity to consent | 21 CFR 50.24 | …in time follow separate rules (HRPP 8.4.4; for FDA-regulated studies, 21 CFR 50.24 ). Contact the IRB well before you submit. ## Prisoners A prisoner … |
| 665 | Special_Populations | Prisoners | HRPP Section 13 | …on, and people held while awaiting arraignment, trial, or sentencing (HRPP Section 13; 45 CFR 46.303). > Planning a study that includes prisoners Rese… |
| 666 | Special_Populations | Prisoners | 45 CFR 46.303 | …ld while awaiting arraignment, trial, or sentencing (HRPP Section 13; 45 CFR 46.303). > Planning a study that includes prisoners Research can involve … |
| 667 | Special_Populations | Prisoners | HRPP 9.3.6 | …search can involve prisoners only if it fits one of these categories (HRPP 9.3.6; 45 CFR 46.306): \| Category \| Condition \| \| Causes, effects, and … |
| 668 | Special_Populations | Prisoners | 45 CFR 46.306 | …nvolve prisoners only if it fits one of these categories (HRPP 9.3.6; 45 CFR 46.306): \| Category \| Condition \| \| Causes, effects, and processes of… |
| 669 | Special_Populations | Prisoners | HRPP 9.3.5 | … application should also address each of the IRB's required findings (HRPP 9.3.5), including that incentives do not impair judgment in the prison sett… |
| 670 | Special_Populations | Prisoners | HRPP 9.3.4 | …may be reviewed by the expedited procedure if it otherwise qualifies (HRPP 9.3.4). For research supported by HHS or other agencies that follow Subpart… |
| 671 | Special_Populations | Prisoners | Subpart C | …P 9.3.4). For research supported by HHS or other agencies that follow Subpart C, the IRB sends a certification to OHRP, and OHRP guidance on prisoner… |
| 672 | Special_Populations | Prisoners | OHRP guidance on prisoner research applies | …ies that follow Subpart C, the IRB sends a certification to OHRP, and OHRP guidance on prisoner research applies. Plan extra time, and get the correct… |
| 673 | Special_Populations | Prisoners | HRPP 10.2.4.2.1.2 | …r population that only incidentally includes prisoners is category 4 (HRPP 10.2.4.2.1.2). Of the BMC/BUMC local categories, 9, 10, and 11 can include … |
| 674 | Special_Populations | Prisoners | HRPP 10.2.4.2.2.2 | … incidentally; 12 and 13 cannot include prisoners, even incidentally (HRPP 10.2.4.2.2.2). In these incidental cases the prisoner requirements do not a… |
| 675 | Special_Populations | Prisoners | HRPP 9.3.1 | …cation printouts] What happens next depends on the study's oversight (HRPP 9.3.1): - Studies with external funding, FDA oversight, or otherwise not el… |
| 676 | Special_Populations | Prisoners | HRPP 2.1.2 | … FDA oversight, or otherwise not eligible for equivalent protections (HRPP 2.1.2): all study activities with that participant stop until the IRB appro… |
| 677 | Special_Populations | Other populations that need extra protections | HRPP 9.6 | … targeted, expect a sign-off from the appropriate official in INSPIR (HRPP 9.6). This includes studies where the participants are the study team's o… |
| 678 | Special_Populations | Other populations that need extra protections | HRPP 9.8 | …ychiatric disorders have added protections when a study targets them (HRPP 9.8), and studies likely to learn that someone is at risk of suicide need… |
| 679 | Special_Populations | Other populations that need extra protections | HRPP 9.9 | …ikely to learn that someone is at risk of suicide need a safety plan (HRPP 9.9). - People with limited English proficiency. See Including Participan… |
| 680 | Special_Populations | Related links | 45 CFR 46 Subpart B | …C/BUMC HRPP Policies and Procedures (sections 9.3 to 9.9 and 8.4.4) - 45 CFR 46 Subpart B: pregnant women, fetuses, and neonates (eCFR) - 45 CFR 46 Su… |
| 681 | Special_Populations | Related links | 45 CFR 46 Subpart C | …- 45 CFR 46 Subpart B: pregnant women, fetuses, and neonates (eCFR) - 45 CFR 46 Subpart C: prisoners (eCFR) - OHRP guidance on research involving pris… |
| 682 | Special_Populations | Related links | OHRP guidance on research involving prisoners | …etuses, and neonates (eCFR) - 45 CFR 46 Subpart C: prisoners (eCFR) - OHRP guidance on research involving prisoners - 21 CFR 50.24: exception from inf… |
| 683 | Special_Populations | Related links | 21 CFR 50.24 | …C: prisoners (eCFR) - OHRP guidance on research involving prisoners - 21 CFR 50.24: exception from informed consent for emergency research (eCFR) - Ma… |
| 684 | Mandated_Reporting_and_Safety_Plans | Mandated Reporting and Safety Plans | HRPP 9.9 | …le at risk for suicide or asks questions that would reveal that risk (HRPP 9.9). And whenever information might be shared outside the study, for exa… |
| 685 | Mandated_Reporting_and_Safety_Plans | Mandated Reporting and Safety Plans | HRPP 8.2.3 | …ed report, the consent process must tell people so before they agree (HRPP 8.2.3). If someone is in immediate danger, call 911. For a participant in c… |
| 686 | Mandated_Reporting_and_Safety_Plans | Quick guide | HRPP 8.2.3 | …ers \| A plan for what you will do, and consent language that says so (HRPP 8.2.3). The IRB expects researchers to report such threats appropriately u… |
| 687 | Mandated_Reporting_and_Safety_Plans | Quick guide | HRPP 9.7.2 | …ools, or nursing homes \| The same, even if you never ask about abuse (HRPP 9.7.2) \| Same as above \| > Suicide safety protocols HRPP Section 9.9 say… |
| 688 | Mandated_Reporting_and_Safety_Plans | Quick guide | HRPP Section 9.9 | …about abuse (HRPP 9.7.2) \| Same as above \| > Suicide safety protocols HRPP Section 9.9 says the protocol must describe: How information about risk f… |
| 689 | Mandated_Reporting_and_Safety_Plans | Quick guide | M.G.L. c. 119 | …t on being a researcher. Each law has its own list (for children, see M.G.L. c. 119, s. 21); it includes physicians, nurses, psychologists, and social… |
| 690 | Mandated_Reporting_and_Safety_Plans | Quick guide | M.G.L. c. 19A | …ort") \| Department of Children and Families \| \| Adults 60 and older \| M.G.L. c. 19A, s. 15 \| Executive Office of Aging & Independence (elder abus… |
| 691 | Mandated_Reporting_and_Safety_Plans | Quick guide | M.G.L. c. 19C | …lts 18 to 59 with a disability who depend on others for daily needs \| M.G.L. c. 19C, s. 10 \| Disabled Persons Protection Commission \| Other duties … |
| 692 | Mandated_Reporting_and_Safety_Plans | Quick guide | HRPP 9.9 | …g. Staff must respond appropriately even in studies with no protocol (HRPP 9.9). > Common reasons for stipulations - A questionnaire with a suicide … |
| 693 | Mandated_Reporting_and_Safety_Plans | Related links | Sections 8.2.3, 9.7.2, 9.9 | … Groups - Research Involving Children - HRPP Policies and Procedures (Sections 8.2.3, 9.7.2, 9.9) - Pregnancy, Adults Lacking Capacity, and Prisoners … |
| 694 | Data_Security_for_Researchers | Guidance | HRPP 8.3.3 | …n can require longer; signed consent forms are kept at least 7 years (HRPP 8.3.3). If you leave before then, name someone who stays and can reach the … |
| 695 | Data_Security_for_Researchers | Guidance | HRPP 7.2.2.3 | … earliest opportunity as consistent with the design of the research" (HRPP 7.2.2.3). When the two seem to conflict. Destroying the master code does no… |
| 696 | Data_Security_for_Researchers | Guidance | HRPP 7.2.2.7.2.2 | …, encrypted flash drives, or a sponsor-provided data capture system" (HRPP 7.2.2.7.2.2). - Secure transfer. Share from an approved OneDrive or SharePo… |
| 697 | Data_Security_for_Researchers | Guidance | HRPP 9.7.2 | …gal proceeding) of identifiable information about research subjects" (HRPP 9.7.2). Studies funded by NIH or the CDC receive one automatically, and the… |
| 698 | Data_Security_for_Researchers | Guidance | HRPP 6.6.5.2 | … at ithelp@bu.edu - The IRB: a privacy incident is a major deviation (HRPP 6.6.5.2). Submit a Reportable Events and New Information (RENI) form in INS… |
| 699 | Data_Retention | Guidance | HRPP 10.2.7.2 | …the IRB receives your team's properly completed Final/Closure Report (HRPP 10.2.7.2); the closure letter lists that date, and that is the date the clo… |
| 700 | Data_Retention | Guidance | HRPP 6.6.7.1 and 8.3.3 | …ments and signed consent forms \| 7 years after the end of the study \| HRPP 6.6.7.1 and 8.3.3; BMC policy #39.04.455; BU policy #FA-002 \| \| FDA, dr… |
| 701 | Data_Retention | Guidance | 21 CFR 312.62(c) | …ved, 2 years after the investigation is stopped and FDA is notified \| 21 CFR 312.62(c) \| \| FDA, devices \| Studies under an IDE \| 2 years after th… |
| 702 | Data_Retention | Guidance | 21 CFR 812.140(d) | … the records are no longer needed to support a marketing submission \| 21 CFR 812.140(d) \| \| HIPAA \| Signed HIPAA authorizations and waiver documen… |
| 703 | Data_Retention | Guidance | 45 CFR 164.508(b)(6) and 164.530(j) | …has no expiration date; ask the Privacy Office how long to keep it. \| 45 CFR 164.508(b)(6) and 164.530(j) \| \| Federal grants \| Records of the awar… |
| 704 | Data_Retention | Guidance | 45 CFR 75.361 | …S at 2 CFR 300.106, effective October 1, 2025); older awards may cite 45 CFR 75.361 \| \| Sponsor contract \| Industry and other sponsored studies \| … |
| 705 | Data_Retention | Guidance | HRPP 6.6.7.1 | …audit, investigation, or lawsuit \| Any study \| Until it is resolved \| HRPP 6.6.7.1; 2 CFR 200.334(a) \| The FDA and grant periods can outlast 7 yea… |
| 706 | Data_Retention | Guidance | 45 CFR 164.512(i)(2)(ii) | …e is a health or research reason to keep them or the law requires it (45 CFR 164.512(i)(2)(ii)(A)(2)). Until this is decided, state in your applicatio… |
| 707 | Data_Retention | Guidance | HRPP 6.6.6 | …and all that is left is analysis, you may be able to close the study (HRPP 6.6.6). You can also close a study when you are only storing identifiable d… |
| 708 | Data_Retention | Guidance | Section 6.6.7 | …ains the responsibility for maintaining research records described in Section 6.6.7, and if the study is closed before the required record retention t… |
| 709 | Data_Sharing | Guidance | HRPP 8.2.5 | …ing to retention must be optional if the study offers direct benefit (HRPP 8.2.5). \| \| Share with a vendor, app, or company \| Answer the third-part… |
| 710 | Data_Sharing | What this means for your IRB submission | HRPP 8.2.5 | …ment, such as PCORI's, does not replace BMC/BUMC consent rules. Under HRPP 8.2.5, if deposit is retention for extra use (any analysis beyond your stud… |
| 711 | Data_Sharing | What this means for your IRB submission | 45 CFR 46.116(b)(9) | …red for future research without asking again, or that it will not be (45 CFR 46.116(b)(9)). If you choose the second, you cannot later deposit de-iden… |
| 712 | Data_Sharing | What this means for your IRB submission | 45 CFR 46.116(c)(7) | …y's consent. Also say whether participants will share in any profits (45 CFR 46.116(c)(7); HRPP 8.2.2). The template's commercial-value paragraph cove… |
| 713 | Data_Sharing | What this means for your IRB submission | HRPP 8.2.2 | … whether participants will share in any profits (45 CFR 46.116(c)(7); HRPP 8.2.2). The template's commercial-value paragraph covers both. The Retentio… |
| 714 | AI_in_Research | Describe the data flow | HRPP 8.2.5 | …rs potential direct benefit, agreeing to future use must be optional (HRPP 8.2.5). Not telling participants about AI. If disclosure would bias results… |
| 715 | AI_in_Research | Describe the data flow | 45 CFR 46.116(f) | …osure. Non-exempt studies need an IRB-approved alteration of consent (45 CFR 46.116(f)); exempt category 3 studies must tell participants up front the… |
| 716 | AI_in_Research | Related links | SACHRP: IRB Considerations on the Use of Artif | …ocedures (section 7.2.2.2) - BU AI tools and the data each may hold - SACHRP: IRB Considerations on the Use of Artificial Intelligence in Human Subjec… |
| 717 | Social_Media_Internet_Research | Guidance | HRPP 7.2.2.6.1 | …ndition, the process should not reveal that condition to anyone else (HRPP 7.2.2.6.1). A comment thread can do exactly that. #### Comments and public … |
| 718 | Social_Media_Internet_Research | Comments and public replies | HRPP 10.2.5.4 | …IRB may consult BMC or BU Communications about social media projects (HRPP 10.2.5.4). See Do I Need IRB Review? The federal definition turns on expect… |
| 719 | Social_Media_Internet_Research | Comments and public replies | 45 CFR 46.102(e)(4) | …ew? The federal definition turns on expectations, not settings. Under 45 CFR 46.102(e)(4) , private information includes "information about behavior t… |
| 720 | Social_Media_Internet_Research | Comments and public replies | HRPP 6.6.3.2 and 6.6.5.2 | …ays after you learn of an unanticipated problem or a major deviation (HRPP 6.6.3.2 and 6.6.5.2). A privacy incident is a major deviation. Report what … |
| 721 | Social_Media_Internet_Research | Comments and public replies | SACHRP: Considerations and Recommendations Con | … platform risks for studies run in online groups. > Further reading - SACHRP: Considerations and Recommendations Concerning Internet Research (federal… |
| 722 | Working_with_Other_Institutions | Guidance | HRPP 2.5.2.1-2.5.2.3 | …e institution with its own IRB. Under the global reliance agreements (HRPP 2.5.2.1-2.5.2.3), for minimal-risk studies reviewed by the BMC/BUMC IRB, CR… |
| 723 | Working_with_Other_Institutions | Guidance | GCP | …or collaborating agreement complete Medical Campus CITI training (and GCP for clinical trials). Give each person's contact information, role, a… |
| 724 | Working_with_Other_Institutions | Guidance | HRPP 10.2.4.1 | …r IRB's exempt determination for our part, submit a cede application (HRPP 10.2.4.1). Adding any external investigator or site after approval requires… |
| 725 | Working_with_Other_Institutions | Guidance | Common Rule | …h a personnel change. > Multi-site research and single IRB review The Common Rule requires a single IRB for most non-exempt research funded or conduct… |
| 726 | Working_with_Other_Institutions | Guidance | 45 CFR 46.114(b)(2) | …ses where the funding agency decides a single IRB is not appropriate (45 CFR 46.114(b)(2)). Under 45 CFR 46.114(b)(1) : Any institution located in the… |
| 727 | Working_with_Other_Institutions | Guidance | 45 CFR 46.114(b)(1) | … decides a single IRB is not appropriate (45 CFR 46.114(b)(2)). Under 45 CFR 46.114(b)(1) : Any institution located in the United States that is engag… |
| 728 | Working_with_Other_Institutions | Boston HealthNet community health centers | GCP | …are external investigators and need Medical Campus CITI training (and GCP for clinical trials). If the study is ceded to an outside IRB, engage… |
| 729 | VA_Research | Research Involving the VA Boston Healthcare System | Common Rule | …VA Boston has its own IRB and research office, and the VA follows the Common Rule as codified for the VA at 38 CFR Part 16, plus VA-specific requireme… |
| 730 | VA_Research | Research Involving the VA Boston Healthcare System | 38 CFR Part 16 | … office, and the VA follows the Common Rule as codified for the VA at 38 CFR Part 16, plus VA-specific requirements in VHA Directive 1200.05. The BMC/… |
| 731 | VA_Research | Research Involving the VA Boston Healthcare System | HRPP 2.5.1 | …IRB each review the parts of a study their institution is engaged in (HRPP 2.5.1); there is no reliance agreement between them. A study that involves … |
| 732 | VA_Research | Guidance | 45 CFR 46.114 | … VA. - Federally funded multi-site studies usually need a single IRB (45 CFR 46.114). If the VA site will keep its own IRB review, attach the funding … |
| 733 | Ceding_Review | Ceding Review to Another IRB | AAHRPP | …E, or a federally supported multi-center trial that chose it. Must be AAHRPP-accredited and use the SMART IRB agreement; for industry trials, it m… |
| 734 | Ceding_Review | Guidance | 45 CFR 46.114 | …ost federally funded U.S. multi-site research must use a single IRB ( 45 CFR 46.114 ). For industry trials, a single IRB is not federally required. Yo… |
| 735 | Ceding_Review | Guidance | AAHRPP | …that is greater than minimal risk, the proposed IRB of record must be AAHRPP-accredited or in the process of obtaining AAHRPP accreditation. For m… |
| 736 | Ceding_Review | Which IRBs we cede to | AAHRPP | …mercial IRB was selected as IRB of record. The commercial IRB must be AAHRPP-accredited and willing to use the SMART IRB agreement. For industry-s… |
| 737 | Ceding_Review | Which IRBs we cede to | HRPP 2.5.3.2 | …ed on or after September 1, 2019), such as for pre-screening records (HRPP 2.5.3.2). See HIPAA in Research . - Local policies : who leads the consent … |
| 738 | Ceding_Review | Which IRBs we cede to | GCP | …reviewing IRB. - Training : current Medical Campus CITI training (and GCP for clinical trials) for every BMC/BUMC team member, including people… |
| 739 | Ceding_Review | Which IRBs we cede to | GINA | …alth information, in a part of the form that applies to our site. \| \| GINA \| If the form mentions GINA, add the Massachusetts-specific language … |
| 740 | Ceding_Review | What to have ready | GCP | …s chosen in the Review Path Determination question. - Expired CITI or GCP training for BMC/BUMC team members. ## Questions Email medirb@bu.edu … |
| 741 | Ceding_Review | Related links | AAHRPP | … cede review seminar video - SMART IRB participating institutions and AAHRPP accredited organizations - International Research - Community-Engaged… |
| 742 | Community_Engaged_Research | Guidance | 45 CFR 46.117(c)(1)(iii) | …search is minimal risk, and you have another way to document consent (45 CFR 46.117(c)(1)(iii); not available for FDA-regulated studies). Request this… |
| 743 | Community_Engaged_Research | Related links | OHRP guidance on engagement of institutions in human subjects research | …HRPP Policies and Procedures (sections 2.7.3, 7.2.2.6.4, and 9.8.1) - OHRP guidance on engagement of institutions in human subjects research - Ceding … |
| 744 | International_Research | Guidance | GDPR | … for example the European Union's General Data Protection Regulation (GDPR) and China's Personal Information Protection Law. The IRB does not ad… |
| 745 | Conflict_of_Interest | Guidance | HRPP Section 13 | … is a conflict; the COI office does. Significant financial interests (HRPP Section 13) \| Type of interest \| Counts as an SFI when \| \| Publicly tra… |
| 746 | Conflict_of_Interest | Guidance | 42 CFR Part 50 | …other Public Health Service agency must also meet the federal rule at 42 CFR Part 50, Subpart F , which adds sponsored travel to the SFI definition an… |
| 747 | Conflict_of_Interest | Related links | 42 CFR Part 50 | …d Procedures (sections 6.5, 7.2.2.5, 7.2.2.6.2, 10.1.1.2.9, and 13) - 42 CFR Part 50, Subpart F (eCFR) Was this page helpful? Yes / No. Tell us what w… |
| 748 | Glossary_A_to_Z | C | HRPP 6.6.6 | …ou close exempt research yourself; no Final/Closure Report is needed (HRPP 6.6.6). Continuing Review and Closing Coded Identifiers are replaced by a s… |
| 749 | Glossary_A_to_Z | C | Common Rule | …e to you, though they may still be PHI under HIPAA. HIPAA in Research Common Rule The federal rules for protecting human subjects in research (45 CFR … |
| 750 | Glossary_A_to_Z | C | 45 CFR 46 | …mon Rule The federal rules for protecting human subjects in research (45 CFR 46, Subpart A). BMC/BUMC applies equivalent protections to some studies … |
| 751 | Glossary_A_to_Z | C | Subpart A | …e federal rules for protecting human subjects in research (45 CFR 46, Subpart A). BMC/BUMC applies equivalent protections to some studies that are no… |
| 752 | Glossary_A_to_Z | E | HRPP 2.1.2 | …record for an outside site, or was approved before February 14, 2011 (HRPP 2.1.2). In practice the IRB treats any external funder as ruling out equiva… |
| 753 | Glossary_A_to_Z | F | Common Rule | …whose results will be submitted to or held for inspection by FDA. The Common Rule exemptions do not apply to it, except the taste and food quality cat… |
| 754 | Glossary_A_to_Z | G | GINA | …s site closure letter. Continuing Review and Closing Back to top ## G GINA The federal Genetic Information Nondiscrimination Act. Consent forms … |
| 755 | Glossary_A_to_Z | G | Genetic Information Nondiscrimination Act | …tter. Continuing Review and Closing Back to top ## G GINA The federal Genetic Information Nondiscrimination Act. Consent forms use template language c… |
| 756 | Glossary_A_to_Z | G | GCP | …MC, and BUMC. Working with Other Institutions Good Clinical Practice (GCP) Training required for everyone on a clinical trial, renewed every 3 … |
| 757 | Glossary_A_to_Z | H | HRPP Section 13 | …ens (identifiable or not) are used to test an investigational device (HRPP Section 13). Do I Need IRB Review? Humanitarian use device (HUD) A device f… |
| 758 | Glossary_A_to_Z | I | HRPP 1.2 | …he human research protection program. They approve the HRPP policies (HRPP 1.2). Policies, Regulations, and Accreditation Interaction, intervention … |
| 759 | Glossary_A_to_Z | S | HRPP Section 13 | …important medical event that needs treatment to prevent one of these (HRPP Section 13). Reporting Problems Short form A brief consent document in the … |
| 760 | Glossary_A_to_Z | W | AAHRPP | …acronyms Acronyms used by the BMC/BUMC IRB \| Acronym \| Stands for \| \| AAHRPP \| Association for the Accreditation of Human Research Protection Pro… |
| 761 | Glossary_A_to_Z | W | 45 CFR 46 | …al Data Warehouse for Research \| \| CFR \| Code of Federal Regulations (45 CFR 46 is the Common Rule; 21 CFR covers FDA) \| \| CITI \| Collaborative … |
| 762 | Glossary_A_to_Z | W | Common Rule | … for Research \| \| CFR \| Code of Federal Regulations (45 CFR 46 is the Common Rule; 21 CFR covers FDA) \| \| CITI \| Collaborative Institutional Tra… |
| 763 | Glossary_A_to_Z | W | GCP | …U.S. Food and Drug Administration \| \| FWA \| Federalwide Assurance \| \| GCP \| Good Clinical Practice \| \| GINA \| Genetic Information Nondiscrimi… |
| 764 | Glossary_A_to_Z | W | GINA | … \| \| FWA \| Federalwide Assurance \| \| GCP \| Good Clinical Practice \| \| GINA \| Genetic Information Nondiscrimination Act \| \| GSDM \| Goldman … |
| 765 | Glossary_A_to_Z | W | Genetic Information Nondiscrimination Act | …A \| Federalwide Assurance \| \| GCP \| Good Clinical Practice \| \| GINA \| Genetic Information Nondiscrimination Act \| \| GSDM \| Goldman School of… |
| 766 | Glossary_A_to_Z | Related links | 45 CFR 46.102 | …s (Section 13, Definitions; Section 14, Abbreviations and Acronyms) - 45 CFR 46.102, Common Rule definitions (eCFR) - 21 CFR 50.3, FDA definitions (eC… |
| 767 | Glossary_A_to_Z | Related links | Common Rule | …Definitions; Section 14, Abbreviations and Acronyms) - 45 CFR 46.102, Common Rule definitions (eCFR) - 21 CFR 50.3, FDA definitions (eCFR) Was this pa… |
| 768 | Glossary_A_to_Z | Related links | 21 CFR 50.3 | …tions and Acronyms) - 45 CFR 46.102, Common Rule definitions (eCFR) - 21 CFR 50.3, FDA definitions (eCFR) Was this page helpful? Yes / No. Tell us wha… |
| 769 | Contact_and_About | Getting help | Sections 6.6.3.2 and 6.6.5.2 | …endar days after you or your staff learn of the event (HRPP Policies, Sections 6.6.3.2 and 6.6.5.2). How to do this is on the Reporting Problems page.… |
| 770 | Contact_and_About | Getting help | Section 7.2.2.18 | …RB, the commercial IRB must bill the sponsor directly (HRPP Policies, Section 7.2.2.18). See the WCG IRB standard fee schedule for 2026 (PDF) . > IRB … |
| 771 | Contact_and_About | About the IRB | AAHRPP | …part of the Human Research Protection Program, which is accredited by AAHRPP, and follows the HRPP Policies and Procedures . > Review panels and b… |
| 772 | FAQ | Getting started | GCP | …Security course. Clinical trials also require Good Clinical Practice (GCP) training. More: Who needs training > Can a student, resident, or fel… |
| 773 | FAQ | Consent | HRPP 8.4.5.3 | … decides who may interpret based on the study's risks and procedures (HRPP 8.4.5.3). Minors may not interpret. For a short form consent, if a team mem… |
| 774 | FAQ | After approval | HRPP 6.6.3.4 | …our next continuing review and in your final report at study closure (HRPP 6.6.3.4), and follow your sponsor's reporting rules. Stop study contact wit… |
| 775 | Announcements | Announcements | HRPP 7.3.2, 7.3.3 | …f before it. The Department Chair or Section Chief still signs first (HRPP 7.3.2, 7.3.3). \| Ancillary Reviews and Sign-Offs \| \| Sept 16, 2026 \| Po… |
| 776 | Announcements | Announcements | HRPP 2.5.4, 6.6.3.2, 6.6.3.3, 6.6.5.2 | …porting and response deadlines now read "7 calendar days" throughout (HRPP 2.5.4, 6.6.3.2, 6.6.3.3, 6.6.5.2 and others). \| Reporting and Monitoring \… |
| 777 | Announcements | Announcements | HRPP 7.2.2.6.5, 8.1.3.4 | … used, and the Screening Questions Full Consent template was removed (HRPP 7.2.2.6.5, 8.1.3.4). \| Recruitment and Screening \| \| Sept 16, 2026 \| Po… |
| 778 | Announcements | Announcements | HRPP 7.2.2.11 | … regardless of method. Consent template Payment language was updated (HRPP 7.2.2.11). \| Paying Research Participants \| \| Sept 16, 2026 \| Policy \|… |
| 779 | Announcements | Announcements | HRPP 10.2.4.2.1.2, 10.2.4.2.2.2 | …ption by combining our local exempt categories with the federal ones (HRPP 10.2.4.2.1.2, 10.2.4.2.2.2). \| Exempt Research \| \| July 20, 2026 \| Poli… |
| 780 | Announcements | Announcements | HRPP 6.6.3.3, 6.6.5.2 | …ov noncompliance and privacy incidents now count as major deviations (HRPP 6.6.3.3, 6.6.5.2). \| Reporting and Monitoring \| \| July 20, 2026 \| Polic… |
| 781 | Announcements | Announcements | HRPP 7.2.2.2 | …when investigators outside BMC use data or samples from BMC patients (HRPP 7.2.2.2). [CHECK IN INSPIR: where these questions appear] \| Ancillary Revi… |
| 782 | Announcements | Announcements | HRPP 7.4.6 | …nd left without a response for 18 months are closed administratively (HRPP 7.4.6). \| Responding to Stipulations \| \| July 20, 2026 \| Policy \| Exem… |
| 783 | Announcements | Announcements | Exempt category 13 | …RPP 7.4.6). \| Responding to Stipulations \| \| July 20, 2026 \| Policy \| Exempt category 13 requires adult subjects who can consent for themselves (… |
| 784 | Announcements | Announcements | HRPP 10.2.4.2.2.2 | …t category 13 requires adult subjects who can consent for themselves (HRPP 10.2.4.2.2.2). \| Exempt Research \| \| July 20, 2026 \| Policy \| Privacy … |
| 785 | Announcements | Announcements | HRPP 11.3.8, 11.4.3.3, 11.4.3.4 | …s go to the privacy officers, and to BU IT when security is involved (HRPP 11.3.8, 11.4.3.3, 11.4.3.4). \| Data Security for Researchers \| \| June 15… |
| 786 | Announcements | Announcements | HRPP 2.5.2.1-2.5.2.3, 7.2.2.18 | …er Campus, so most of these studies need no separate cede submission (HRPP 2.5.2.1-2.5.2.3, 7.2.2.18). \| Working with Other Institutions \| \| May 26… |
| 787 | Announcements | Announcements | HRPP 7.2.2.12.6, 8.4.5.2, 8.4.5.3, 10.1.2 | …n form, and full translation is needed after three uses per language (HRPP 7.2.2.12.6, 8.4.5.2, 8.4.5.3, 10.1.2). \| Short Form Consent Process \| \| … |
| 788 | Announcements | Announcements | HRPP 1.1.2 | … 2026 \| Policy \| IRB oversight extends to BMC Brighton and BMC South (HRPP 1.1.2). \| Policies, Regulations, and Accreditation \| \| Feb 24, 2026 \|… |
| 789 | Announcements | Announcements | HRPP 6.6.9, 6.6.5.2 | …ire registration. Results-posting noncompliance is a major deviation (HRPP 6.6.9, 6.6.5.2). \| ClinicalTrials.gov Requirements \| \| Feb 24, 2026 \| P… |
| 790 | Announcements | Announcements | HRPP 7.4.4, 10.2.5.3 | …ite closure letter. Parent training grants no longer need IRB review (HRPP 7.4.4, 10.2.5.3). \| Continuing Review and Closing a Study \| \| Jan 2026 \… |
| 791 | Announcements | Announcements | HRPP 2.5.2.1 | …nts are added to a BMC/BUMC study through a regular personnel change (HRPP 2.5.2.1). \| Student and Trainee Research \| \| Dec 5, 2025 \| Policy \| Li… |
| 792 | Announcements | Announcements | HRPP 8.4.5 | …ies reorganized; short form consent templates may be posted publicly (HRPP 8.4.5). \| Limited English Proficiency \| \| Oct 2025 \| Templates \| Spani… |
| 793 | Announcements | Announcements | HRPP 7.2.2 | …licy \| New sign-off for studies using the BMC Clinical Research Unit (HRPP 7.2.2). \| Ancillary Reviews and Sign-Offs \| ## Coming soon We are revisi… |
| 794 | Announcements | Things to know | HRPP 10.2.5.1 | …ds or data with HIPAA identifiers about decedents, submit to the IRB (HRPP 10.2.5.1). Dear IRB: Data and specimens from deceased individuals (CR Times… |
| 795 | Announcements | Things to know | HRPP 2.4 | …ers does not engage you; obtaining consent or identifiable data does (HRPP 2.4). The Rules of Engagement (CR Times, June 2025) . Our page: Working w… |
| 796 | Announcements | Things to know | HRPP 2.5.2.3 | …lobal reliance agreements, with no study-by-study reliance agreement (HRPP 2.5.2.3). Streamlining Cross-Campus Research (CR Times, Apr 2026) . Our pag… |
| 797 | Announcements | Things to know | HRPP 10.2.4.1, 6.6.2.2 | …ve no expiration date; a Status Check-In Report is due every 3 years (HRPP 10.2.4.1, 6.6.2.2). Category 13 requires adults who can consent for themsel… |
| 798 | Announcements | Things to know | Exempt Category 13 | …6.6.2.2). Category 13 requires adults who can consent for themselves. Exempt Category 13 (CR Times, Apr 2025, corrected here) . Our page: Exempt Resea… |
| 799 | Announcements | Things to know | HRPP 10.2.4.1 | …privacy protections; a change to the incentive amount alone does not (HRPP 10.2.4.1). Dear IRB: Changing an incentive in an exempt study (CR Times, Se… |
| 800 | Announcements | Things to know | HRPP 8.1.3.7 | …led by an LIP such as a physician, dentist, PA or nurse practitioner (HRPP 8.1.3.7). Dear IRB: PA as LIP (CR Times, Mar 2026) . Our page: Obtaining Co… |
| 801 | Announcements | Things to know | HRPP 8.4.5 | …cted languages and has a use cap before full translation is required (HRPP 8.4.5). Spanish templates are available. Informed Consent with Limited Engl… |
| 802 | Announcements | Things to know | HRPP 7.2.2.6.5, 8.1.3.4 | …answers are kept, a HIPAA authorization or waiver may also be needed (HRPP 7.2.2.6.5, 8.1.3.4). Screening Potential Research Subjects (CR Times, Apr 2… |
| 803 | Announcements | Things to know | HRPP 7.2.2.11 | …ive, and above $2,000 the ID number is required regardless of method (HRPP 7.2.2.11). Things to Know: IRS $2,000 threshold (CR Times, Jan 2026, correc… |
| 804 | Announcements | Things to know | HRPP 6.6.7.1 | …is applies even if your protocol says 5 years, and to exempt studies (HRPP 6.6.7.1). Dear IRB: Retention after closure (CR Times, Oct 2023) and closed… |
| 805 | Announcements | Things to know | HRPP 6.6.3.3 | …fter you receive them; submit the changes themselves as an amendment (HRPP 6.6.3.3). Dear IRB: Submitting a DSMB report (CR Times, Dec 2022, corrected… |
| 806 | Announcements | Things to know | HRPP 7.4.4 | …close a ceded study, include the reviewing IRB's site closure letter (HRPP 7.4.4). Time for Status Check-In (CR Times, Mar 2024, corrected here) . Our… |
| 807 | Announcements | Things to know | 42 CFR 11.64 | …tion dates within 30 days of reaching them, as federal rules require (42 CFR 11.64); our policy sets the 10-month results deadline (HRPP 6.6.9). Prima… |
| 808 | Announcements | Things to know | HRPP 6.6.9 | …equire (42 CFR 11.64); our policy sets the 10-month results deadline (HRPP 6.6.9). Primary and Study Completion Dates (CR Times, Mar 2026) . Our page:… |
| 809 | IRB_Committees | The review panels | HRPP Policies 3.1 | …s, and Accreditation . The IRB does not use subcommittees for review (HRPP Policies 3.1; Executive Board role from 10.2.1.7). ## Who serves on a panel… |
| 810 | IRB_Committees | Who serves on a panel | 45 CFR 46.107(c) | …immediate family of a person who is affiliated with the institution." 45 CFR 46.107(c) Under HRPP Policies 3.2, each BMC/BUMC board has at least five … |
| 811 | IRB_Committees | Who serves on a panel | HRPP Policies 3.2 | …erson who is affiliated with the institution." 45 CFR 46.107(c) Under HRPP Policies 3.2, each BMC/BUMC board has at least five members, including: - a… |
| 812 | IRB_Committees | Who serves on a panel | HRPP 9.3.2 | …ve, who takes part whenever research involving prisoners is reviewed (HRPP 9.3.2). Lawyers from the BMC and BU general counsel offices attend meetings… |
| 813 | IRB_Committees | Meetings | HRPP 5.1, 5.2 | … a schedule the IRB Director sets at the start of each academic year (HRPP 5.1, 5.2). [CHECK: meeting time and Zoom format] A panel can act only with … |
| 814 | IRB_Committees | Meetings | HRPP 5.6 | …an when the study involves an FDA-regulated drug, biologic or device (HRPP 5.6). If your study is on an agenda, you may be invited to answer questio… |
| 815 | IRB_Committees | Current roster | HRPP 3.3.1 | …e IRB updates the posted list within one week of a membership change (HRPP 3.3.1). ## Join the IRB We welcome new members, and we especially need comm… |
| 816 | IRB_Committees | Join the IRB | HRPP 3.3.2 | …frequency] - Term. Appointments are for two years and can be renewed (HRPP 3.3.2). - Training. New members get an orientation, observe at least one me… |
| 817 | IRB_Committees | Join the IRB | HRPP 3.5.1 | …ember before reviewing a study, with an experienced member as mentor (HRPP 3.5.1). Short education sessions open many meetings. - Confidentiality. Mem… |
| 818 | IRB_Committees | Join the IRB | HRPP 5.3 | …entiality. Members keep study materials and discussions confidential (HRPP 5.3). - Compensation. Unaffiliated members receive an honorarium; BMC and… |
| 819 | IRB_Committees | Join the IRB | HRPP 3.6 | …serve without pay. Some expenses, such as parking, may be reimbursed (HRPP 3.6). > How to join or nominate someone Email medirb@bu.edu to say you ar… |
| 820 | IRB_Committees | Join the IRB | HRPP 3.3.1 | …may nominate a potential member; the IRB Director makes appointments (HRPP 3.3.1). People whose jobs involve business development at BMC or BU, such a… |
| 821 | IRB_Committees | Conflicts of interest for board members | 45 CFR 46.107(d) | … has a financial interest in the sponsor or the product being tested (45 CFR 46.107(d)). The member tells the Chair, may answer questions if the Chair… |
| 822 | IRB_Committees | Conflicts of interest for board members | HRPP 3.9 | …he same department as the investigator is not, by itself, a conflict (HRPP 3.9). Current board members. Reviewer templates and training materials ar… |
| 823 | IRB_Committees | Related pages | 45 CFR 46.107 | …P Policies and Procedures, Section 3 (IRB structure and membership) - 45 CFR 46.107, IRB membership - For IRB Board Members (and What Reviewers Look F… |
| 824 | For_Board_Members | Who serves and what they do | HRPP 3.4.1.3, 10.3.2.2 | …ws some expedited submissions and responses to conditional approvals (HRPP 3.4.1.3, 10.3.2.2). \| Yes \| \| Vice Chair \| Acts for the Chair when need… |
| 825 | For_Board_Members | Who serves and what they do | HRPP 3.4.2.3 | ….3, 10.3.2.2). \| Yes \| \| Vice Chair \| Acts for the Chair when needed (HRPP 3.4.2.3). \| Yes \| \| Primary reviewer \| Has expertise in the topic o… |
| 826 | For_Board_Members | Who serves and what they do | HRPP 10.2.1.2 to 10.2.1.4 | … and proposes a motion. Also leads amendments and continuing reviews (HRPP 10.2.1.2 to 10.2.1.4). \| Yes \| \| Secondary reviewer \| For new studies; … |
| 827 | For_Board_Members | Who serves and what they do | HRPP 3.3.4 | … \| Vote in place of an absent or recused member of the same category (HRPP 3.3.4). \| When substituting \| \| Consultants and biostatisticians \| Add… |
| 828 | For_Board_Members | Who serves and what they do | HRPP 3.8, 10.2.1.2 | … review of investigator-initiated trials without outside peer review (HRPP 3.8, 10.2.1.2). \| No \| \| Ex officio members \| BMC and BU general counse… |
| 829 | For_Board_Members | Who serves and what they do | HRPP 5.4 | … 10.2.1.2). \| No \| \| Ex officio members \| BMC and BU general counsel (HRPP 5.4). \| No \| \| IRB staff \| Pre-review submissions, support reviewer… |
| 830 | For_Board_Members | How a convened review works | HRPP 10.2.1.2 | …eviewer, matched to the topic or population, or arrange a consultant (HRPP 10.2.1.2). - Conflict check. A reviewer with a conflict of interest stops, … |
| 831 | For_Board_Members | How a convened review works | HRPP 3.9 | …tudy can be reassigned, and discloses it to the Chair at the meeting (HRPP 3.9). - Materials. The agenda is locked the Friday before the Thursday me… |
| 832 | For_Board_Members | How a convened review works | HRPP 10.2.1.1 | … out at least 5 days before the meeting; every document is in INSPIR (HRPP 10.2.1.1). Investigators have no submission deadline; see Timelines, Grant … |
| 833 | For_Board_Members | How a convened review works | HRPP 3.3.3 | …n review. Reviewers post their comments in INSPIR before the meeting (HRPP 3.3.3). - The meeting. Reviewers present and the panel discusses. Invited i… |
| 834 | For_Board_Members | How a convened review works | HRPP 5.5 | …es. Invited investigators leave before the final discussion and vote (HRPP 5.5). - The vote. A member moves, another seconds, and the motion passes … |
| 835 | For_Board_Members | How a convened review works | HRPP 10.3.1 | …sses with a majority of voting members present, counting abstentions (HRPP 10.3.1). Quorum needs a majority of voting members and a non-scientist, plu… |
| 836 | For_Board_Members | How a convened review works | HRPP 5.6 | …ientist, plus a physician for FDA-regulated products; no proxy votes (HRPP 5.6). What the board can decide \| Motion \| What a yes vote means \| \| Ap… |
| 837 | For_Board_Members | How a convened review works | HRPP 10.3.2.3 | …ach stipulation point by point and the board reviews the study again (HRPP 10.3.2.3). There is no deadline. \| \| Disapprove \| The study must be rede… |
| 838 | For_Board_Members | How a convened review works | HRPP 10.3.2.4 | …ppeal in writing through INSPIR and may ask to appear before the IRB (HRPP 10.3.2.4). \| Source: HRPP 10.3.2. The board also records the risk level, t… |
| 839 | For_Board_Members | How a convened review works | HRPP 10.3.2 | …NSPIR and may ask to appear before the IRB (HRPP 10.3.2.4). \| Source: HRPP 10.3.2. The board also records the risk level, the approval period (how of… |
| 840 | For_Board_Members | How a convened review works | HRPP 10.4.1 | …sk level, the approval period (how often continuing review is needed, HRPP 10.4.1), whether later reviews may be expedited, and separate findings such… |
| 841 | For_Board_Members | What reviewers look for | 45 CFR 46.111(a) | …hall determine that all of the following requirements are satisfied:" 45 CFR 46.111(a) BMC/BUMC policy adds one criterion first: the research design m… |
| 842 | For_Board_Members | What reviewers look for | HRPP 10.1.1.1 | …ust be scientifically appropriate and the degree of risk justifiable (HRPP 10.1.1.1). Reviewers look at the study's purpose and design (the Purpose an… |
| 843 | For_Board_Members | What reviewers look for | 45 CFR 46.111(a)(2) | … research count, not those of care participants would receive anyway (45 CFR 46.111(a)(2)). The question: Do the expected benefits, to participants or… |
| 844 | For_Board_Members | What reviewers look for | § 46.116 | …ed representative, in accordance with, and to the extent required by, § 46.116." The question: Will people truly understand what they are agreeing t… |
| 845 | For_Board_Members | What reviewers look for | § 46.117 | …e appropriately documented or appropriately waived in accordance with § 46.117." The question: Will there be proper evidence that consent happened, … |
| 846 | For_Board_Members | What reviewers look for | 45 CFR 46.404-407 | …ific determinations: - Children: the board decides the risk category (45 CFR 46.404-407; 21 CFR 50.51-54) and whether one or both parents must give pe… |
| 847 | For_Board_Members | What reviewers look for | 21 CFR 50.51-54 | …: - Children: the board decides the risk category (45 CFR 46.404-407; 21 CFR 50.51-54) and whether one or both parents must give permission and how as… |
| 848 | For_Board_Members | What reviewers look for | 46.408 | … one or both parents must give permission and how assent is obtained (46.408). - Prisoners: a prisoner representative reviews and the board makes … |
| 849 | For_Board_Members | What reviewers look for | 46.305(a) | … Prisoners: a prisoner representative reviews and the board makes the 46.305(a) findings. - Pregnant women or fetuses: the board applies 46.204. For … |
| 850 | For_Board_Members | What reviewers look for | 46.204 | …he 46.305(a) findings. - Pregnant women or fetuses: the board applies 46.204. For researchers: Special Populations ; Research Involving Children >… |
| 851 | For_Board_Members | What reviewers look for | 21 CFR 56.111 | …al Populations ; Research Involving Children > FDA-regulated studies (21 CFR 56.111) For studies of drugs, biologics and devices, the FDA's criteria i… |
| 852 | For_Board_Members | What reviewers look for | 21 CFR 56.111(c) | …l research is in compliance with part 50, subpart D of this chapter." 21 CFR 56.111(c) Reviewers also check the drug, device and radiation sections an… |
| 853 | For_Board_Members | Reviewing the consent form | 45 CFR 46.116(a)(5) | …es from standard care; - begins with a short key information section (45 CFR 46.116(a)(5)); covers every required element in 45 CFR 46.116(b), includi… |
| 854 | For_Board_Members | Reviewing the consent form | 45 CFR 46.116(b) | …ation section (45 CFR 46.116(a)(5)); covers every required element in 45 CFR 46.116(b), including purpose, procedures, risks, benefits, alternatives, … |
| 855 | For_Board_Members | Reviewing the consent form | 46.116(c) | …dentifiable data or specimens in the future; and adds the elements in 46.116(c) that apply; - uses the current BMC/BUMC template language where it ap… |
| 856 | For_Board_Members | Continuing review | HRPP 10.1.2 | …formation that would change that, especially about risks or benefits (HRPP 10.1.2). Reviewers check: - Status and enrollment: whether the study is enr… |
| 857 | For_Board_Members | Continuing review | HRPP 6.6.3.4 | …lems, and whether their pattern suggests greater risk than was known (HRPP 6.6.3.4). A data safety monitor’s report can serve as the summary. - Minor … |
| 858 | For_Board_Members | Continuing review | HRPP 6.6.5.3 | … summary. - Minor deviations: reported together at continuing review (HRPP 6.6.5.3). Reviewers look for patterns that suggest risk, a training problem… |
| 859 | For_Board_Members | Continuing review | HRPP 10.4.2 | …napproved changes: whether anything has changed without IRB approval (HRPP 10.4.2). The board may approve the study for another period, approve it and… |
| 860 | For_Board_Members | Amendments | HRPP 10.2.1.3 | …udy, with the proposed changes, still meets every approval criterion (HRPP 10.2.1.3). The review focuses on the changes that affect participants. Revi… |
| 861 | For_Board_Members | Amendments | HRPP 7.4.1.2 | …, the reason for it, and tracked-changes copies of revised documents (HRPP 7.4.1.2). - Risk and benefit: new or increased risks, reduced benefit, and … |
| 862 | For_Board_Members | Amendments | HRPP 10.2.2.4.2.1 | … or scientific merit, and can be reviewed by the expedited procedure (HRPP 10.2.2.4.2.1). - Re-consent: whether people already enrolled must be re-con… |
| 863 | For_Board_Members | Member conflicts of interest | HRPP 3.9 and 5.6 | …he same department as the investigator is not, by itself, a conflict (HRPP 3.9 and 5.6). ## Training for members New members get orientation on the Be… |
| 864 | For_Board_Members | Training for members | Belmont Report | … and 5.6). ## Training for members New members get orientation on the Belmont Report, the regulations, the HRPP Policies and INSPIR. They observe at l… |
| 865 | For_Board_Members | Training for members | HRPP 3.5.1 and 3.5.2 | … that review. Members are encouraged to read the CR Times each month (HRPP 3.5.1 and 3.5.2). ## Join the IRB We welcome new members, especially commun… |
| 866 | For_Board_Members | Related pages | 45 CFR 46.111 | … Board Review - HRPP Policies and Procedures (Sections 3, 5 and 10) - 45 CFR 46.111, criteria for IRB approval - The Belmont Report Was this page help… |
| 867 | For_Board_Members | Related pages | Belmont Report | …ections 3, 5 and 10) - 45 CFR 46.111, criteria for IRB approval - The Belmont Report Was this page helpful? Yes / No. Tell us what was missing. Last r… |
| 868 | Policies_and_Regulations | HRPP Policies and Procedures | HRPP 8.4.5.2 | …HRPP document (PDF) . Our pages cite sections by number (for example, HRPP 8.4.5.2). "Sponsors, researchers, and research staff should always refer to… |
| 869 | Policies_and_Regulations | HRPP Policies and Procedures | HRPP 1.2 | …sed changes, and the BMC and BU Institutional Officials approve them (HRPP 1.2). We announce changes in the CR Times newsletter , on the OHRA websit… |
| 870 | Policies_and_Regulations | HRPP Policies and Procedures | Exempt category 13 | …udy team for 18 months are closed. \| \| July 20, 2026 \| 10.2.4.2.2.2 \| Exempt category 13 requires adults who can consent for themselves. \| \| Jul… |
| 871 | Policies_and_Regulations | Which rules apply to my study | Common Rule | … and where the policies address them \| Rule \| Applies when \| HRPP \| \| Common Rule, 45 CFR 46 , with Subparts B (pregnant persons, fetuses, neonat… |
| 872 | Policies_and_Regulations | Which rules apply to my study | 45 CFR 46 | …e policies address them \| Rule \| Applies when \| HRPP \| \| Common Rule, 45 CFR 46 , with Subparts B (pregnant persons, fetuses, neonates), C (priso… |
| 873 | Policies_and_Regulations | Which rules apply to my study | Subparts B | …s them \| Rule \| Applies when \| HRPP \| \| Common Rule, 45 CFR 46 , with Subparts B (pregnant persons, fetuses, neonates), C (prisoners) and D (chil… |
| 874 | Policies_and_Regulations | Which rules apply to my study | 21 CFR 50 | …r standards apply to most other research \| 2.1, 2.2, 9.2-9.4 \| \| FDA: 21 CFR 50 (consent) and 56 (IRBs) \| Clinical investigations of drugs, device… |
| 875 | Policies_and_Regulations | Which rules apply to my study | 21 CFR 312 | … Clinical investigations of drugs, devices or biologics \| 2.2, 12 \| \| 21 CFR 312 (INDs); 812 (IDEs); 814 Subpart H (humanitarian use devices) \| Dr… |
| 876 | Policies_and_Regulations | Which rules apply to my study | HIPAA Privacy Rule | …device and HUD studies; emergency and expanded access \| 12.1-12.4 \| \| HIPAA Privacy Rule, 45 CFR 164 \| Health information from BMC or another cove… |
| 877 | Policies_and_Regulations | Which rules apply to my study | 45 CFR 164 | …es; emergency and expanded access \| 12.1-12.4 \| \| HIPAA Privacy Rule, 45 CFR 164 \| Health information from BMC or another covered entity \| 7.2.2.… |
| 878 | Policies_and_Regulations | Which rules apply to my study | 42 CFR Part 2 | …lth information from BMC or another covered entity \| 7.2.2.3, 8.5 \| \| 42 CFR Part 2 \| Records from substance use disorder treatment programs \| 7.… |
| 879 | Policies_and_Regulations | Which rules apply to my study | FERPA | …ubstance use disorder treatment programs \| 7.2.2.10, 10.2.4.2.2.2 \| \| FERPA ( 34 CFR 99 ) and PPRA ( 34 CFR 98 ) \| Student records; surveys in sc… |
| 880 | Policies_and_Regulations | Which rules apply to my study | 34 CFR 99 | … use disorder treatment programs \| 7.2.2.10, 10.2.4.2.2.2 \| \| FERPA ( 34 CFR 99 ) and PPRA ( 34 CFR 98 ) \| Student records; surveys in schools fun… |
| 881 | Policies_and_Regulations | Which rules apply to my study | PPRA | …eatment programs \| 7.2.2.10, 10.2.4.2.2.2 \| \| FERPA ( 34 CFR 99 ) and PPRA ( 34 CFR 98 ) \| Student records; surveys in schools funded by the Dep… |
| 882 | Policies_and_Regulations | Which rules apply to my study | 34 CFR 98 | … programs \| 7.2.2.10, 10.2.4.2.2.2 \| \| FERPA ( 34 CFR 99 ) and PPRA ( 34 CFR 98 ) \| Student records; surveys in schools funded by the Department o… |
| 883 | Policies_and_Regulations | Which rules apply to my study | M.G.L. c. 111 | …assachusetts laws that affect research - Genetic testing and consent: M.G.L. c. 111, section 70G. See Genetics, Biospecimens, and Repositories . - Fet… |
| 884 | Policies_and_Regulations | Which rules apply to my study | M.G.L. c. 112 | …70G. See Genetics, Biospecimens, and Repositories . - Fetal research: M.G.L. c. 112, section 12J. - Controlled substances in research: M.G.L. c. 94C, … |
| 885 | Policies_and_Regulations | Which rules apply to my study | M.G.L. c. 94C | …rch: M.G.L. c. 112, section 12J. - Controlled substances in research: M.G.L. c. 94C, section 8, and 105 CMR 700.009. See OHRA's research license page … |
| 886 | Policies_and_Regulations | Which rules apply to my study | 105 CMR 700.009 | …J. - Controlled substances in research: M.G.L. c. 94C, section 8, and 105 CMR 700.009. See OHRA's research license page . - Age of majority (18) and r… |
| 887 | Policies_and_Regulations | Which rules apply to my study | M.G.L. c. 231 | …age . - Age of majority (18) and reporting of child abuse or neglect: M.G.L. c. 231, section 85P, and c. 119, section 51A. See Research Involving Chil… |
| 888 | Policies_and_Regulations | Which rules apply to my study | M.G.L. c. 271 | …bal consent to test; written consent to disclose results). - Raffles: M.G.L. c. 271, section 7A (a raffle raises money by selling tickets, with prizes… |
| 889 | Policies_and_Regulations | Which rules apply to my study | HRPP 2.2 | …g Participants . Where laws conflict, the IRB consults legal counsel (HRPP 2.2). > Research without external funding or FDA oversight BMC and BUMC a… |
| 890 | Policies_and_Regulations | Which rules apply to my study | HRPP 2.1.2 | …s IRB is the IRB of record for an external site. See the full list in HRPP 2.1.2 and Exempt Research . ## Assurance and registration numbers Sponsors … |
| 891 | Policies_and_Regulations | Accreditation | AAHRPP | …ociation for the Accreditation of Human Research Protection Programs (AAHRPP) since 2017 and was reaccredited in December 2025. Confirm our status… |
| 892 | Policies_and_Regulations | How BU and BMC policies fit together | HRPP 1.1.2 | …he School of Public Health and the Goldman School of Dental Medicine (HRPP 1.1.2). One set of HRPP policies covers all of them. Other BMC or BU polici… |
| 893 | Policies_and_Regulations | Federal resources | FDA guidance documents | …ections (OHRP) - FDA clinical trials and human subject protection and FDA guidance documents . - HHS: HIPAA and research . ## Related pages - Contact … |

---

## Appendix C. Open-item tags and placeholders still in the page text, by page

RED = `[chk]` tag, YELLOW = `[ck]` tag, PURPLE = `[unv]` tag, placeholder = bracketed text in running copy, planned/pend/pending/unverified = spans with those classes. Consent_Language_Bank's template fill-ins such as `[name]` are omitted. Where many tags repeat the same text (e.g., "confirm" on INSPIR steps), identical texts within a page are collapsed with a count.

### IRB_Home (3)
| Marker | Location | Text |
|---|---|---|
| placeholder | Start here | [Icon: person with a compass] |
| placeholder | Getting started: new to research? | [Icon: checklist] |
| PURPLE [unv] | intro | [URL and parent page pending Lauren] |

### Hub_Before_You_Submit (1)
| Marker | Location | Text |
|---|---|---|
| PURPLE [unv] | intro | [URL pending Lauren] |

### Case_Reports (2)
| Marker | Location | Text |
|---|---|---|
| placeholder | Quick guide | [UNVERIFIED: confirm with the Privacy Office whether a journal's form can ever stand in for the BMC template] |
| PURPLE [unv] | Journal consent forms | [UNVERIFIED: confirm with the Privacy Office whether a journal's form can ever stand in for the BMC template] |

### Exempt_Research (19)
| Marker | Location | Text |
|---|---|---|
| placeholder | Guidance | [CHECK IN INSPIR: the exempt application is being redesigned; the section list and the section-generation behavior are confirmed only from t |
| placeholder | Guidance | [UNVERIFIED] |
| RED [chk] | How INSPIR category numbers relate to the federal rule | [NOT IN SEPT 2026 PRINTOUTS; CONFIRM: category 4 has sub-options ("check all that apply below"), and INSPIR's prisoner note refers to "(4.1) |
| PURPLE [unv] | What to submit | [CHECK IN INSPIR: the exempt application is being redesigned; the section list and the section-generation behavior are confirmed only from t |
| PURPLE [unv] | After your determination | [UNVERIFIED] |
| planned | BMC/BUMC IRB | Do I Need IRB Review? |
| planned | Limited IRB review | Data Security for Researchers |
| planned | Consent in exempt research: the Exempt Information Sheet | Consent Templates |
| planned | Consent in exempt research: the Exempt Information Sheet | HIPAA in Research |
| planned | Consent in exempt research: the Exempt Information Sheet | Paying Participants |
| planned | What to submit | Preparing a Complete Submission |
| planned | After your determination | Amendments |
| planned | After your determination | Continuing Review, Status Check-Ins, and Closing a Study |
| planned | After your determination | Working with Other Institutions |
| planned | Common reasons for stipulations and how to avoid them | Do I Need IRB Review? |
| planned | Related links | Do I Need IRB Review? |
| planned | Related links | Consent Templates |
| planned | Related links | HIPAA in Research |
| planned | Related links | Continuing Review, Status Check-Ins, and Closing a Study |

### Exempt_Tip_Sheets_Index (1)
| Marker | Location | Text |
|---|---|---|
| PURPLE [unv] | BMC/BUMC IRB |  |

### Exempt_Tip_1 (4)
| Marker | Location | Text |
|---|---|---|
| placeholder | Details | [UNVERIFIED: no local FERPA guidance; confirm whether to mention it] |
| placeholder | Details | [CHECK IN INSPIR: redesign pending; confirm names] |
| RED [chk] | Application sections that matter | [CHECK IN INSPIR: redesign pending; confirm names] |
| PURPLE [unv] | Children and student records | [UNVERIFIED: no local FERPA guidance; confirm whether to mention it] |

### Exempt_Tip_2-1 (4)
| Marker | Location | Text |
|---|---|---|
| placeholder | Details | [CHECK IN INSPIR: redesign pending; confirm names] |
| placeholder | Details | [CHECK IN INSPIR: confirm when this question appears] |
| RED [chk] | Application sections that matter | [CHECK IN INSPIR: redesign pending; confirm names] |
| RED [chk] | Application sections that matter | [CHECK IN INSPIR: confirm when this question appears] |

### Exempt_Tip_2-2 (4)
| Marker | Location | Text |
|---|---|---|
| placeholder | Details | [CHECK IN INSPIR: redesign pending; confirm names] |
| placeholder | Details | [CHECK IN INSPIR: confirm when this question appears] |
| RED [chk] | Application sections that matter | [CHECK IN INSPIR: redesign pending; confirm names] |
| RED [chk] | Application sections that matter | [CHECK IN INSPIR: confirm when this question appears] |

### Exempt_Tip_3-1 (4)
| Marker | Location | Text |
|---|---|---|
| placeholder | Details | [CHECK IN INSPIR: redesign pending; confirm names] |
| placeholder | Details | [CHECK IN INSPIR: confirm when this question appears] |
| RED [chk] | Application sections that matter | [CHECK IN INSPIR: redesign pending; confirm names] |
| RED [chk] | Application sections that matter | [CHECK IN INSPIR: confirm when this question appears] |

### Exempt_Tip_3-2 (4)
| Marker | Location | Text |
|---|---|---|
| placeholder | Details | [CHECK IN INSPIR: redesign pending; confirm names] |
| placeholder | Details | [CHECK IN INSPIR: confirm when this question appears] |
| RED [chk] | Application sections that matter | [CHECK IN INSPIR: redesign pending; confirm names] |
| RED [chk] | Application sections that matter | [CHECK IN INSPIR: confirm when this question appears] |

### Exempt_Tip_4 (4)
| Marker | Location | Text |
|---|---|---|
| placeholder | Details | [CHECK IN INSPIR: category 4 shows sub-options ("check all that apply below") after it is selected; they were not in the September 2026 prin |
| placeholder | Details | [CHECK IN INSPIR: redesign pending; confirm names] |
| RED [chk] | HIPAA and records-only studies | [CHECK IN INSPIR: category 4 shows sub-options ("check all that apply below") after it is selected; they were not in the September 2026 prin |
| RED [chk] | Application sections that matter | [CHECK IN INSPIR: redesign pending; confirm names] |

### Exempt_Tip_5 (4)
| Marker | Location | Text |
|---|---|---|
| placeholder | Details | [CHECK IN INSPIR: redesign pending; confirm names] |
| placeholder | Details | [CHECK IN INSPIR: confirm when this question appears] |
| RED [chk] | Application sections that matter | [CHECK IN INSPIR: redesign pending; confirm names] |
| RED [chk] | Application sections that matter | [CHECK IN INSPIR: confirm when this question appears] |

### Exempt_Tip_6 (4)
| Marker | Location | Text |
|---|---|---|
| placeholder | Details | [CHECK IN INSPIR: redesign pending; confirm names] |
| placeholder | Details | [CHECK IN INSPIR: confirm when this question appears] |
| RED [chk] | Application sections that matter | [CHECK IN INSPIR: redesign pending; confirm names] |
| RED [chk] | Application sections that matter | [CHECK IN INSPIR: confirm when this question appears] |

### Exempt_Tip_9 (3)
| Marker | Location | Text |
|---|---|---|
| placeholder | Details | [CHECK IN INSPIR: redesign pending; confirm names] |
| RED [chk] | Application sections that matter | [CHECK IN INSPIR: redesign pending; confirm names] |
| PURPLE [unv] | BMC/BUMC IRB |  |

### Exempt_Tip_10 (3)
| Marker | Location | Text |
|---|---|---|
| placeholder | Details | [CHECK IN INSPIR: redesign pending; confirm names] |
| RED [chk] | Application sections that matter | [CHECK IN INSPIR: redesign pending; confirm names] |
| PURPLE [unv] | BMC/BUMC IRB |  |

### Exempt_Tip_11 (5)
| Marker | Location | Text |
|---|---|---|
| placeholder | Details | [CHECK IN INSPIR: redesign pending; confirm names] |
| placeholder | Details | [CHECK IN INSPIR: confirm when this question appears] |
| RED [chk] | Application sections that matter | [CHECK IN INSPIR: redesign pending; confirm names] |
| RED [chk] | Application sections that matter | [CHECK IN INSPIR: confirm when this question appears] |
| PURPLE [unv] | BMC/BUMC IRB |  |

### Exempt_Tip_12 (5)
| Marker | Location | Text |
|---|---|---|
| placeholder | Details | [CHECK IN INSPIR: redesign pending; confirm names] |
| placeholder | Details | [CHECK IN INSPIR: confirm when this question appears] |
| RED [chk] | Application sections that matter | [CHECK IN INSPIR: redesign pending; confirm names] |
| RED [chk] | Application sections that matter | [CHECK IN INSPIR: confirm when this question appears] |
| PURPLE [unv] | BMC/BUMC IRB |  |

### Exempt_Tip_13 (7)
| Marker | Location | Text |
|---|---|---|
| placeholder | Examples | [UNVERIFIED: contrast and medical clearance details not confirmed] |
| placeholder | Details | [CHECK IN INSPIR: redesign pending; confirm names] |
| placeholder | Details | [CHECK IN INSPIR: confirm when this question appears] |
| RED [chk] | Application sections that matter | [CHECK IN INSPIR: redesign pending; confirm names] |
| RED [chk] | Application sections that matter | [CHECK IN INSPIR: confirm when this question appears] |
| PURPLE [unv] | BMC/BUMC IRB |  |
| PURPLE [unv] | Examples | [UNVERIFIED: contrast and medical clearance details not confirmed] |

### Expedited_and_Full_Board_Review (19)
| Marker | Location | Text |
|---|---|---|
| placeholder | Guidance | [CHECK: meeting time and Zoom format] |
| placeholder | Questions | [CRRO link to be confirmed] |
| PURPLE [unv] | Board meetings and panels | [CHECK: meeting time and Zoom format] |
| PURPLE [unv] | Questions | [CRRO link to be confirmed] |
| planned | BMC/BUMC IRB | Do I Need IRB Review? |
| planned | BMC/BUMC IRB | Exempt Research |
| planned | How expedited review works | Responding to Stipulations |
| planned | Possible outcomes | Responding to Stipulations |
| planned | How long approval lasts | Continuing review, status check-ins, and closing your study |
| planned | Drug and device studies | Drugs and Devices |
| planned | Common reasons for stipulations and how to avoid them | Do I Need IRB Review? |
| planned | Common reasons for stipulations and how to avoid them | Preparing a Complete Submission |
| planned | Common reasons for stipulations and how to avoid them | Consent Templates |
| planned | Related links | Do I Need IRB Review? |
| planned | Related links | Exempt Research |
| planned | Related links | Responding to Stipulations |
| planned | Related links | Continuing review, status check-ins, and closing your study |
| planned | Related links | Drugs and Devices |
| planned | Related links | Special Populations |

### Expedited_Tip_5 (2)
| Marker | Location | Text |
|---|---|---|
| placeholder | Details | [CHECK IN INSPIR: confirm section names] |
| RED [chk] | Application sections that matter | [CHECK IN INSPIR: confirm section names] |

### Expedited_Tip_9 (2)
| Marker | Location | Text |
|---|---|---|
| placeholder | Details | [CHECK IN INSPIR: confirm the Progress Report form name and fields] |
| RED [chk] | Application sections that matter | [CHECK IN INSPIR: confirm the Progress Report form name and fields] |

### Chart_Review (28)
| Marker | Location | Text |
|---|---|---|
| placeholder | Quick guide: which path fits your chart review | [NOT IN SEPT 2026 PRINTOUTS; CONFIRM] |
| placeholder | When it needs more | [NOT IN SEPT 2026 PRINTOUTS; CONFIRM: no chart review path was printed, and a revision is in progress] |
| placeholder | When it needs more | [UNVERIFIED: BMC local process for preparatory-to-research review] |
| placeholder | When it needs more | [NOT IN SEPT 2026 PRINTOUTS; CONFIRM: whether the chart review section also asks for a date range, and whether the revision removes it] |
| placeholder | When it needs more | [PENDING DECISION: master code retention; see Data Security page] |
| placeholder | When it needs more | [NOT IN SEPT 2026 PRINTOUTS; CONFIRM: wording in the chart review application] |
| placeholder | When it needs more | [NOT IN SEPT 2026 PRINTOUTS; CONFIRM: the full help-icon list] |
| placeholder | Related links | [PENDING] |
| RED [chk] | Quick guide: which path fits your chart review | [NOT IN SEPT 2026 PRINTOUTS; CONFIRM] |
| RED [chk] | The chart review application in INSPIR | [NOT IN SEPT 2026 PRINTOUTS; CONFIRM: no chart review path was printed, and a revision is in progress] |
| RED [chk] | Date ranges and variable lists: what reviewers want | [NOT IN SEPT 2026 PRINTOUTS; CONFIRM: whether the chart review section also asks for a date range, and whether the revision removes it] |
| RED [chk] | Data from other institutions or external databases | [NOT IN SEPT 2026 PRINTOUTS; CONFIRM: wording in the chart review application] |
| RED [chk] | Records with extra protections | [NOT IN SEPT 2026 PRINTOUTS; CONFIRM: the full help-icon list] |
| PURPLE [unv] | What you may look at before approval | [UNVERIFIED: BMC local process for preparatory-to-research review] |
| pend | The chart review application in INSPIR | [PLANNED TASK PAGE] |
| pend | Master codes and storage | [PENDING DECISION: master code retention; see Data Security page] |
| planned | What counts as chart review research | Do I Need IRB Review? |
| planned | The chart review application in INSPIR | How to submit a chart review in INSPIR |
| planned | What you may look at before approval | HIPAA in Research |
| planned | HIPAA waiver for chart reviews | HIPAA in Research |
| planned | Identifiers you really need | De-identified, coded, anonymous, and limited data sets |
| planned | Master codes and storage | Data Security for Researchers |
| planned | Data from other institutions or external databases | Working with Other Institutions |
| planned | Case reports and case series | Case Reports and Case Series |
| planned | Related links | HIPAA in Research |
| planned | Related links | Data Security for Researchers |
| planned | Related links | Do I Need IRB Review? |
| planned | Related links | Working with Other Institutions |

### Preparing_a_Complete_Submission (12)
| Marker | Location | Text |
|---|---|---|
| placeholder | Checklist | [UNVERIFIED: current external site letter process; see reviewer notes] |
| placeholder | Checklist | [UNVERIFIED: whether the IRB wants the executed agreement attached or only referenced] |
| placeholder | Checklist | [CHECK IN INSPIR: the upload screen is not in the September 2026 printouts; confirm where you enter the version] |
| placeholder | Checklist | [CHECK IN INSPIR: the Initial Review Submission Form is not in the September 2026 printouts; confirm the name of its consent attachment sect |
| placeholder | Special routing (ancillary reviews) | [CHECK IN INSPIR: not shown in the September 2026 printouts, which were generated with No] |
| placeholder | Special routing (ancillary reviews) | [UNVERIFIED: current Velos entry instructions and link] |
| RED [chk] | Preparing your documents | [CHECK IN INSPIR: the upload screen is not in the September 2026 printouts; confirm where you enter the version] |
| RED [chk] | Preparing your documents | [CHECK IN INSPIR: the Initial Review Submission Form is not in the September 2026 printouts; confirm the name of its consent attachment sect |
| RED [chk] | When a separate protocol is required | [CHECK IN INSPIR: not shown in the September 2026 printouts, which were generated with No] |
| PURPLE [unv] | What to attach, by study feature | [UNVERIFIED: current external site letter process; see reviewer notes] |
| PURPLE [unv] | What to attach, by study feature | [UNVERIFIED: whether the IRB wants the executed agreement attached or only referenced] |
| PURPLE [unv] | Extra steps for clinical trials | [UNVERIFIED: current Velos entry instructions and link] |

### Application_Section_Tips (10)
| Marker | Location | Text |
|---|---|---|
| placeholder | Common mistakes | [CHECK IN INSPIR: whether the Initial Review Submission Form now asks for home institution] |
| placeholder | Common mistakes | [UNVERIFIED: public process for requesting a Finder update] |
| placeholder | Example answer | [UNVERIFIED: confirm this is standard practice before publishing] |
| placeholder | Common mistakes | [UNVERIFIED: whether the answer should be No for leftover-only studies; one stipulation said so] |
| placeholder | What reviewers look for | [CHECK IN INSPIR: the Initial Review Submission Form question on recruiting BMC/BU Medical Campus employees] |
| RED [chk] | PI home institution: is this a BMC or a BU study? | [CHECK IN INSPIR: whether the Initial Review Submission Form now asks for home institution] |
| RED [chk] | What reviewers look for | [CHECK IN INSPIR: the Initial Review Submission Form question on recruiting BMC/BU Medical Campus employees] |
| PURPLE [unv] | Common mistakes | [UNVERIFIED: public process for requesting a Finder update] |
| PURPLE [unv] | Example answer | [UNVERIFIED: confirm this is standard practice before publishing] |
| PURPLE [unv] | Common mistakes | [UNVERIFIED: whether the answer should be No for leftover-only studies; one stipulation said so] |

### Eligibility_and_Study_Design (4)
| Marker | Location | Text |
|---|---|---|
| placeholder | Can you reach it? | [CHECK IN INSPIR: wording of the population-access question; not in the September 2026 printout] |
| placeholder | After approval | [UNVERIFIED: biostatistics consulting link] |
| PURPLE [unv] | Can you reach it? | [CHECK IN INSPIR: wording of the population-access question; not in the September 2026 printout] |
| PURPLE [unv] | Design, outcomes, and analysis plan | [UNVERIFIED: biostatistics consulting link] |

### Ancillary_Reviews_Sign_Offs (5)
| Marker | Location | Text |
|---|---|---|
| placeholder | Guidance | [UNVERIFIED: current IPS process] |
| placeholder | Guidance | [UNVERIFIED: what RSP asks for] |
| placeholder | Related links | [PENDING] |
| PURPLE [unv] | Checklist: who else reviews your study | [UNVERIFIED: current IPS process] |
| PURPLE [unv] | Checklist: who else reviews your study | [UNVERIFIED: what RSP asks for] |

### Study_Team_Members (8)
| Marker | Location | Text |
|---|---|---|
| placeholder | Guidance | [UNVERIFIED: this exception comes from a 2014 CR Times article, not current HRPP text; confirm it is still IRB practice] |
| placeholder | Guidance | [CHECK IN INSPIR: current role choices] |
| placeholder | Guidance | [UNVERIFIED: internal only if they hold a BMC or BU appointment; otherwise external] |
| placeholder | Guidance | [UNVERIFIED: whether more investigators from an institution already under a signed agreement need an amendment] |
| RED [chk] | Roles in the application | [CHECK IN INSPIR: current role choices] |
| PURPLE [unv] | Who must be listed | [UNVERIFIED: this exception comes from a 2014 CR Times article, not current HRPP text; confirm it is still IRB practice] |
| PURPLE [unv] | Internal or external? | [UNVERIFIED: internal only if they hold a BMC or BU appointment; otherwise external] |
| PURPLE [unv] | Adding or removing people after approval | [UNVERIFIED: whether more investigators from an institution already under a signed agreement need an amendment] |

### Training_Requirements (20)
| Marker | Location | Text |
|---|---|---|
| placeholder | Training Requirements for Study Teams | [PENDING DECISION: HSP refresher] |
| placeholder | Quick reference | [PENDING DECISION: HSP refresher] (×2) |
| placeholder | Quick reference | [UNVERIFIED: renewal] |
| placeholder | Guidance | [PENDING DECISION: HSP refresher] (×5) |
| placeholder | Guidance | [UNVERIFIED: email-matching rule] |
| PURPLE [unv] | Quick reference | [UNVERIFIED: renewal] |
| PURPLE [unv] | How training shows in INSPIR | [UNVERIFIED: email-matching rule] |
| pending | BMC/BUMC IRB | [PENDING DECISION: HSP refresher] |
| pending | Quick reference | [PENDING DECISION: HSP refresher] (×2) |
| pending | GCP for clinical trials | [PENDING DECISION: HSP refresher] |
| pending | Keeping training current | [PENDING DECISION: HSP refresher] (×2) |
| pending | Researchers from other institutions | [PENDING DECISION: HSP refresher] |
| pending | If training expires | [PENDING DECISION: HSP refresher] |

### Student_Trainee_Research (12)
| Marker | Location | Text |
|---|---|---|
| placeholder | Guidance | [UNVERIFIED: confirm the public-facing process for updating the PI home institution list] |
| placeholder | Guidance | [UNVERIFIED: confirm the current process for non-BU students earning credit at their home school] |
| placeholder | Guidance | [UNVERIFIED: recommended practice, not stated in HRPP; confirm Jamie wants it] |
| placeholder | Guidance | [UNVERIFIED: confirm the internship still runs and who to contact; the live page names staff] |
| placeholder | Related links | [replace with article URL on the new CR Times site] |
| PURPLE [unv] | Class and course projects | [UNVERIFIED: no HRPP section states this; confirm wording and whether data already collected in a class project may later be used as seconda |
| PURPLE [unv] | Setting up your application | [UNVERIFIED: confirm the public-facing process for updating the PI home institution list] |
| PURPLE [unv] | Setting up your application | [NOT IN SEPT 2026 PRINTOUTS; CONFIRM: this appears in older stipulations; no printed application question asks for a thesis proposal, and IN |
| PURPLE [unv] | Students from other schools and programs | [UNVERIFIED: confirm the current process for non-BU students earning credit at their home school] |
| PURPLE [unv] | Studying your own students, trainees, or employees | [UNVERIFIED: recommended practice, not stated in HRPP; confirm Jamie wants it] |
| PURPLE [unv] | Common reasons for stipulations | [UNVERIFIED: confirm the internship still runs and who to contact; the live page names staff] |
| PURPLE [unv] | Related links | [replace with article URL on the new CR Times site] |

### INSPIR_Task_Access_and_New_Study (107)
| Marker | Location | Text |
|---|---|---|
| placeholder | INSPIR: get access and submit a new study | [new site URL] (×2) |
| placeholder | What you need | [UNVERIFIED: whether training is required to log in] |
| placeholder | Quick reference | [UNVERIFIED: confirm current reset page] |
| placeholder | Quick reference | [UNVERIFIED: BMC-only accounts] |
| placeholder | Get into INSPIR | [CHECK IN INSPIR: where this checkbox sits] |
| placeholder | How INSPIR's branching works | [new site URL] |
| placeholder | How INSPIR's branching works | [CHECK IN INSPIR: section names follow the Sept 2026 printed headings; the left-hand menu in edit mode may use shorter labels] |
| placeholder | Start and submit a new study | [new site URL] (×3) |
| placeholder | Sign-offs and proxies | [UNVERIFIED: confirm the advice for Special Routing signers] |
| placeholder | Remove a proxy when you return | [UNVERIFIED: confirm IRB still sets proxies on request] |
| placeholder | Avoid common returns | [new site URL] |
| placeholder | Related links | [Preparing a Complete Submission, new site URL] |
| placeholder | Related links | [Do I Need IRB Review?, new site URL] |
| placeholder | Related links | [Consent Form Templates, new site URL] |
| placeholder | Related links | [Respond to Stipulations task page, new site URL] |
| placeholder | Related links | [Amendments, new site URL] |
| RED [chk] | intro | [new site URL] (×2) |
| RED [chk] | Get into INSPIR | [CHECK IN INSPIR: where this checkbox sits] |
| RED [chk] | How INSPIR's branching works | [new site URL] |
| RED [chk] | How INSPIR's branching works | [CHECK IN INSPIR: section names follow the Sept 2026 printed headings; the left-hand menu in edit mode may use shorter labels] |
| RED [chk] | Start and submit a new study | [new site URL] (×3) |
| RED [chk] | Avoid common returns | [new site URL] |
| YELLOW [ck] | Get into INSPIR | confirm (×13) |
| YELLOW [ck] | Start and submit a new study | confirm (×19) |
| YELLOW [ck] | To start from an INSPIR template | confirm (×5) |
| YELLOW [ck] | To upload a consent form you already have | confirm (×9) |
| YELLOW [ck] | Windows | confirm (×3) |
| YELLOW [ck] | Mac | confirm (×9) |
| YELLOW [ck] | Sign-offs and proxies | confirm (×10) |
| YELLOW [ck] | Add a proxy | confirm (×4) |
| YELLOW [ck] | Remove a proxy when you return | confirm (×2) |
| PURPLE [unv] | What you need | [UNVERIFIED: whether training is required to log in] |
| PURPLE [unv] | Quick reference | [UNVERIFIED: confirm current reset page] |
| PURPLE [unv] | Quick reference | [UNVERIFIED: BMC-only accounts] |
| PURPLE [unv] | Sign-offs and proxies | [UNVERIFIED: confirm the advice for Special Routing signers] |
| PURPLE [unv] | Remove a proxy when you return | [UNVERIFIED: confirm IRB still sets proxies on request] |

### INSPIR_Task_Choose_Review_Path (11)
| Marker | Location | Text |
|---|---|---|
| placeholder | INSPIR: choose your review path (Review Path Determination) | [new site URL] (×2) |
| placeholder | What each option opens next | [CHECK IN INSPIR: the cede application is not in the Sept 2026 printouts; list its sections] |
| placeholder | What each option opens next | [CHECK IN INSPIR: the chart review application is not in the Sept 2026 printouts; list its sections] |
| placeholder | Not sure which option to pick? | [new site URL] |
| RED [chk] | intro | [new site URL] (×2) |
| RED [chk] | What each option opens next | [CHECK IN INSPIR: the cede application is not in the Sept 2026 printouts; list its sections] |
| RED [chk] | What each option opens next | [CHECK IN INSPIR: the chart review application is not in the Sept 2026 printouts; list its sections] |
| RED [chk] | If you change your answer | [CHECK IN INSPIR: the printouts show this instruction only for the Navigation Menu and Review for Completeness, not in the Review Path Deter |
| RED [chk] | Not sure which option to pick? | [new site URL] |

### Responding_to_Stipulations (32)
| Marker | Location | Text |
|---|---|---|
| placeholder | What happens after you submit | [CHECK IN INSPIR: current labels] |
| placeholder | What happens after you submit | [CHECK IN INSPIR: outcome label used] |
| placeholder | What happens after you submit | [UNVERIFIED: resubmission route] |
| placeholder | How to respond so it doesn't come back | [UNVERIFIED: whether the IRB wants a tracked copy alongside the clean one; see reviewer notes] |
| placeholder | How to respond so it doesn't come back | [CHECK IN INSPIR: effect of selecting No] |
| placeholder | How to respond so it doesn't come back | [UNVERIFIED: how a study team withdraws a pending initial submission; see reviewer notes] |
| RED [chk] | Review outcomes and what they mean | [CHECK IN INSPIR: current labels] |
| RED [chk] | Review outcomes and what they mean | [CHECK IN INSPIR: outcome label used] |
| RED [chk] | If you disagree or have questions | [CHECK IN INSPIR: effect of selecting No] |
| YELLOW [ck] | The steps of review | confirm |
| YELLOW [ck] | Open the Review Response form | confirm (×4) |
| YELLOW [ck] | Answer each stipulation | confirm |
| YELLOW [ck] | To change the application or the submission form | confirm (×3) |
| YELLOW [ck] | To change a consent form or study document | confirm (×3) |
| YELLOW [ck] | Record your answer | confirm (×4) |
| YELLOW [ck] | Submit the response | confirm (×3) |
| PURPLE [unv] | The steps of review | [UNVERIFIED: staff pre-review for expedited and convened studies is practice shown in INSPIR outcomes ("Administrative Deferral", "Incomplet |
| PURPLE [unv] | Review outcomes and what they mean | [UNVERIFIED: resubmission route] |
| PURPLE [unv] | Writing a complete response | [UNVERIFIED: whether the IRB wants a tracked copy alongside the clean one; see reviewer notes] |
| PURPLE [unv] | How long you have to respond | [UNVERIFIED: how a study team withdraws a pending initial submission; see reviewer notes] |

### Timelines_and_JIT (12)
| Marker | Location | Text |
|---|---|---|
| placeholder | Grant deadlines and NIH Just-in-Time | [UNVERIFIED: BMC/BU grants office practice for delayed-onset aims] |
| placeholder | Grant deadlines and NIH Just-in-Time | [CONFIRM: whether this letter is offered routinely, who issues it, and how to request it] |
| placeholder | Grant deadlines and NIH Just-in-Time | [CONFIRM] |
| placeholder | Grant deadlines and NIH Just-in-Time | [CONFIRM: medirb or the Director's own address] |
| placeholder | Grant deadlines and NIH Just-in-Time | [CONFIRM: office policy on priority requests] |
| placeholder | Does review slow down over the holidays? | [UNVERIFIED: holiday meeting schedule] |
| PURPLE [unv] | When to submit relative to your grant | [UNVERIFIED: BMC/BU grants office practice for delayed-onset aims] |
| PURPLE [unv] | What the IRB can give your sponsor | [CONFIRM: whether this letter is offered routinely, who issues it, and how to request it] |
| PURPLE [unv] | What the IRB can give your sponsor | [CONFIRM] |
| PURPLE [unv] | Asking for priority review | [CONFIRM: medirb or the Director's own address] |
| PURPLE [unv] | Asking for priority review | [CONFIRM: office policy on priority requests] |
| PURPLE [unv] | Does review slow down over the holidays? | [UNVERIFIED: holiday meeting schedule] |

### Before_and_After_Examples (5)
| Marker | Location | Text |
|---|---|---|
| placeholder | Examples by topic | [PENDING DECISION] |
| placeholder | Examples by topic | [CHECK IN INSPIR: whether revisions must be uploaded as a new version of the same document] |
| placeholder | Examples by topic | [an institution-approved platform or device] |
| PURPLE [unv] | 8. When identifiers and the master code will be destroyed | [PENDING DECISION] |
| PURPLE [unv] | 9. Clean, consistent documents | [CHECK IN INSPIR: whether revisions must be uploaded as a new version of the same document] |

### Example_NHSR_and_QI_Requests (8)
| Marker | Location | Text |
|---|---|---|
| placeholder | How to use these examples | [CHECK IN INSPIR: which of the other NHSR yes/no questions still appear after No] |
| placeholder | How to use these examples | [UNVERIFIED: confirm the IRB prefers "No" here on a QI request] |
| placeholder | How to use these examples | [UNVERIFIED: whether the CDW-R keeps a crosswalk for de-identified extracts] |
| placeholder | How to use these examples | [CHECK IN INSPIR: whether case reports needing a letter use the NHSR path; the research question mentions case series of three or fewer] |
| RED [chk] | Example 1: a clinic quality improvement project that is not | [CHECK IN INSPIR: which of the other NHSR yes/no questions still appear after No] |
| RED [chk] | Example 3: a "QI" project that is really research | [CHECK IN INSPIR: whether case reports needing a letter use the NHSR path; the research question mentions case series of three or fewer] |
| PURPLE [unv] | Example 1: a clinic quality improvement project that is not | [UNVERIFIED: confirm the IRB prefers "No" here on a QI request] |
| PURPLE [unv] | Example 2: analysis of a de-identified data set from the CDW | [UNVERIFIED: whether the CDW-R keeps a crosswalk for de-identified extracts] |

### Example_Exempt_Survey (16)
| Marker | Location | Text |
|---|---|---|
| placeholder | The study at a glance | [number] |
| placeholder | Study Procedures | [number] |
| placeholder | Study Procedures | [name and version] |
| placeholder | Study Summary | [number] |
| placeholder | Race / Ethnicity | [CONFIRM: preferred answer for employee-only studies] |
| placeholder | Confidentiality of the Data | [confirm the setting with your REDCap administrator] |
| placeholder | Protected health information without authorization | [CHECK IN INSPIR: whether the rest of the HIPAA questions still display after a No] |
| placeholder | Example attachments | [name, email, and phone number of research team member] |
| placeholder | Example attachments | [PI name and title] |
| placeholder | Example attachments | [REDCap public survey link] |
| placeholder | Example attachments | [date] (×2) |
| placeholder | Example attachments | [name, email, phone] |
| placeholder | Example attachments | [link] |
| placeholder | Example attachments | [Published burnout measure, name and version] |
| PURPLE [unv] | Protected health information without authorization | [CHECK IN INSPIR: whether the rest of the HIPAA questions still display after a No] |

### Example_Exempt_Chart_Review (5)
| Marker | Location | Text |
|---|---|---|
| placeholder | Protecting identifiers | [UNVERIFIED: wording for studies led by BU covered-unit investigators; see the HIPAA sample answers page] |
| placeholder | Related links | [PENDING] |
| PURPLE [unv] | Which path this example uses | [CHECK IN INSPIR: the chart review application is being revised, and it was not among the September 2026 printouts. The section names and qu |
| PURPLE [unv] | Part c. When identifiers will be destroyed | [PENDING DECISION: the IRB is deciding whether the master code must instead be kept for the full 7-year retention period; see Keeping and De |
| PURPLE [unv] | Protecting identifiers | [UNVERIFIED: wording for studies led by BU covered-unit investigators; see the HIPAA sample answers page] |

### Example_Expedited_Interview_Study (20)
| Marker | Location | Text |
|---|---|---|
| placeholder | Race / Ethnicity | [confirm with clinic data] |
| placeholder | Recruitment Material | [date] |
| placeholder | Consent process for screening | [CHECK: confirm with an analyst that the HIPAA Compliance waiver covers the screening question and the Epic check for flyer callers] |
| placeholder | Confidentiality of the Data | [UNVERIFIED: whether ClinCard (Greenphire), the institutional payment system, needs to be listed here] |
| placeholder | Confidentiality of the Data | [UNVERIFIED: confirm the IRB accepts a separate REDCap project as "maintained separately from study files"] |
| placeholder | Destruction of Identifiers | [PENDING DECISION: whether the master code must itself be kept for the 7-year retention period; update this answer when decided] |
| placeholder | Payment | [UNVERIFIED: ClinCard registration fields] |
| placeholder | Study Attachments | [CHECK IN INSPIR: the printouts do not show the Initial Review Submission Form] |
| placeholder | Signature page | [BMC logo] (×2) |
| placeholder | Study staff script | [patient name] |
| placeholder | Study staff script | [name] |
| placeholder | Study staff script | [Clinician name] |
| placeholder | Related links | [PENDING] |
| PURPLE [unv] | Consent process for screening | [CHECK: confirm with an analyst that the HIPAA Compliance waiver covers the screening question and the Epic check for flyer callers] |
| PURPLE [unv] | Confidentiality of the Data | [UNVERIFIED: whether ClinCard (Greenphire), the institutional payment system, needs to be listed here] |
| PURPLE [unv] | Confidentiality of the Data | [UNVERIFIED: confirm the IRB accepts a separate REDCap project as "maintained separately from study files"] |
| PURPLE [unv] | Destruction of Identifiers | [PENDING DECISION: whether the master code must itself be kept for the 7-year retention period; update this answer when decided] |
| PURPLE [unv] | Payment | [UNVERIFIED: ClinCard registration fields] |
| PURPLE [unv] | Study Attachments | [CHECK IN INSPIR: the printouts do not show the Initial Review Submission Form] |

### Example_Pediatric_Study (10)
| Marker | Location | Text |
|---|---|---|
| placeholder | The application, section by section | [CHECK IN INSPIR: the exact questions, and the document category for uploading an assent script] |
| placeholder | The application, section by section | [UNVERIFIED: ClinCard practice for minors] |
| placeholder | The parent consent and permission form: key sections | [UNVERIFIED: confirm the IRB expects the Use and Sharing section for a survey and interview study run by BMC staff in a BMC clinic; see HIPA |
| placeholder | Model assent scripts | [CHECK IN INSPIR: document category] |
| placeholder | Model assent scripts | [name] (×2) |
| RED [chk] | Minors and assent questions in Consent Procedures | [CHECK IN INSPIR: the exact questions, and the document category for uploading an assent script] |
| PURPLE [unv] | Release of identifiable data and Payment | [UNVERIFIED: ClinCard practice for minors] |
| PURPLE [unv] | Confidentiality: mandatory reporting and safety | [UNVERIFIED: confirm the IRB expects the Use and Sharing section for a survey and interview study run by BMC staff in a BMC clinic; see HIPA |
| PURPLE [unv] | Model assent scripts | [CHECK IN INSPIR: document category] |

### Example_Amendment_and_Stipulation_Response (4)
| Marker | Location | Text |
|---|---|---|
| placeholder | Step 2: write the Amendment Description | [CHECK IN INSPIR: Amendment Description label] |
| placeholder | Eight stipulations and model answers | [CHECK IN INSPIR: how a study team detaches a duplicate document in the Review Response form] |
| RED [chk] | Step 2: write the Amendment Description | [CHECK IN INSPIR: Amendment Description label] |
| RED [chk] | Eight stipulations and model answers | [CHECK IN INSPIR: how a study team detaches a duplicate document in the Review Response form] |

### Hub_Consent_HIPAA_Recruitment (1)
| Marker | Location | Text |
|---|---|---|
| PURPLE [unv] | intro | [URL pending Lauren] |

### Consent_Templates (2)
| Marker | Location | Text |
|---|---|---|
| placeholder | Which template do I use? | [CONFIRM with Director] |
| PURPLE [unv] | Which template do I use? | [CONFIRM with Director] |

### Consent_Language_Bank (1)
| Marker | Location | Text |
|---|---|---|
| unverified | Language | [UNVERIFIED: pending Radiation Safety Committee confirmation that this is its standard statement and may be published. Do not publish this e |

### Templates_Forms_Library (14)
| Marker | Location | Text |
|---|---|---|
| placeholder | HIPAA | [CHECK: still current?] (×2) |
| placeholder | Translation and short forms | [PENDING: the legally authorized representative wording in 8 languages awaits Interpreter Services review] |
| placeholder | Other forms and references | [CHECK: still current?] (×3) |
| placeholder | Accessible versions | [CHECK WITH JAMIE: offer and wording] |
| unverified | HIPAA | [CHECK: still current?] (×2) |
| unverified | Translation and short forms | [PENDING: the legally authorized representative wording in 8 languages awaits Interpreter Services review] |
| unverified | Other forms and references | [CHECK: still current?] (×3) |
| unverified | Accessible versions | [CHECK WITH JAMIE: offer and wording] |

### Obtaining_Consent (6)
| Marker | Location | Text |
|---|---|---|
| placeholder | Licensed independent practitioner (LIP) requirement | [CHECK IN INSPIR: confirm the "Approved Consent" study-workspace tab label on screen] |
| placeholder | Licensed independent practitioner (LIP) requirement | [CHECK: whether BMC requires a consent note in Epic for studies involving clinical care] |
| placeholder | What to describe in your application | [UNVERIFIED: whether the COVID-era remote witness-signature process is still accepted] |
| RED [chk] | Documenting consent | [CHECK IN INSPIR: confirm the "Approved Consent" study-workspace tab label on screen] |
| PURPLE [unv] | Documenting consent | [CHECK: whether BMC requires a consent note in Epic for studies involving clinical care] |
| PURPLE [unv] | What to describe in your application | [UNVERIFIED: whether the COVID-era remote witness-signature process is still accepted] |

### Limited_English_Proficiency (8)
| Marker | Location | Text |
|---|---|---|
| placeholder | Guidance | [UNVERIFIED: confirm examples of accepted reasons] |
| placeholder | Guidance | [UNVERIFIED: current BMC-approved vendors and business associate agreement process] |
| placeholder | Guidance | [UNVERIFIED: research request process and any charges to studies] |
| placeholder | Guidance | [UNVERIFIED: confirm current cede practice; see reviewer notes] |
| PURPLE [unv] | If you plan to exclude people with limited English proficien | [UNVERIFIED: confirm examples of accepted reasons] |
| PURPLE [unv] | Interpreters | [UNVERIFIED: current BMC-approved vendors and business associate agreement process] |
| PURPLE [unv] | Interpreters | [UNVERIFIED: research request process and any charges to studies] |
| PURPLE [unv] | Exempt, international, and ceded studies | [UNVERIFIED: confirm current cede practice; see reviewer notes] |

### Short_Form_Consent_Process (29)
| Marker | Location | Text |
|---|---|---|
| placeholder | Guidance | [UNVERIFIED: whether exempt studies may use library short forms, and whether they need approval to do so] |
| placeholder | After the consent discussion | [UNVERIFIED: any BMC requirement to scan consent documents into the electronic health record] |
| placeholder | Short form library | [UPLOAD PENDING: every link in this table points to its planned location in the Office of Research media library; see Link_ToDo_for_Lauren.m |
| PURPLE [unv] | Who can use the short form | [CHECK IN INSPIR: the Non-English Language Consent Forms table still asks for languages one by one; under current policy you list only the l |
| PURPLE [unv] | Who can use the short form | [UNVERIFIED: whether exempt studies may use library short forms, and whether they need approval to do so] |
| PURPLE [unv] | After the consent discussion | [UNVERIFIED: any BMC requirement to scan consent documents into the electronic health record] |
| PURPLE [unv] | Short form library | [UPLOAD PENDING: every link in this table points to its planned location in the Office of Research media library; see Link_ToDo_for_Lauren.m |
| planned | Short form library | Albanian short form (PDF) |
| planned | Short form library | Amharic short form (PDF) |
| planned | Short form library | Arabic short form (PDF) |
| planned | Short form library | Bulgarian short form (PDF) |
| planned | Short form library | Burmese short form (PDF) |
| planned | Short form library | Cambodian (Khmer) short form (PDF) |
| planned | Short form library | Chinese (Simplified) short form (PDF) |
| planned | Short form library | Chinese (Traditional) short form (PDF) |
| planned | Short form library | English short form (PDF) |
| planned | Short form library | Farsi short form (PDF) |
| planned | Short form library | French short form (PDF) |
| planned | Short form library | Greek short form (PDF) |
| planned | Short form library | Haitian Creole short form (PDF) |
| planned | Short form library | Hindi short form (PDF) |
| planned | Short form library | Polish short form (PDF) |
| planned | Short form library | Portuguese short form (PDF) |
| planned | Short form library | Romanian short form (PDF) |
| planned | Short form library | Russian short form (PDF) |
| planned | Short form library | Spanish short form (PDF) |
| planned | Short form library | Swahili short form (PDF) |
| planned | Short form library | Tigrinya short form (PDF) |
| planned | Short form library | Vietnamese short form (PDF) |

### HIPAA_in_Research (9)
| Marker | Location | Text |
|---|---|---|
| placeholder | More than one waiver | [UNVERIFIED: whether waivers still carry an expiration date in the approval letter; see reviewer notes] |
| placeholder | More than one waiver | [confirm the local mechanism with the Privacy Office] |
| placeholder | Identifiers people often miss | [UNVERIFIED: BMC/BUMC local process for preparatory-to-research reviews] |
| placeholder | Identifiers people often miss | [UNVERIFIED: local process] |
| placeholder | Related links | [PENDING] |
| PURPLE [unv] | More than one waiver | [UNVERIFIED: whether waivers still carry an expiration date in the approval letter; see reviewer notes] |
| PURPLE [unv] | More than one waiver | [confirm the local mechanism with the Privacy Office] |
| PURPLE [unv] | Special situations | [UNVERIFIED: BMC/BUMC local process for preparatory-to-research reviews] |
| PURPLE [unv] | Special situations | [UNVERIFIED: local process] |

### HIPAA_Waiver_Sample_Answers (8)
| Marker | Location | Text |
|---|---|---|
| placeholder | Question by question | [start date] |
| placeholder | Question by question | [the key data, for example diagnoses, medications, and dates of treatment] |
| placeholder | Question by question | [number] |
| placeholder | Question by question | [UNVERIFIED: wording for BU covered-unit studies; see reviewer notes] |
| placeholder | Question by question | [dates of service / zip code / ages over 89] |
| placeholder | Question by question | [when data collection and verification are complete / on a stated date] |
| placeholder | Related links | [PENDING] |
| PURPLE [unv] | How you will protect identifiers | [UNVERIFIED: wording for BU covered-unit studies; see reviewer notes] |

### Certificates_of_Confidentiality (2)
| Marker | Location | Text |
|---|---|---|
| placeholder | What a Certificate does not stop | [UNVERIFIED: who signs for BU] |
| PURPLE [unv] | Studies without federal funding | [UNVERIFIED: who signs for BU] |

### Recruitment_and_Screening (9)
| Marker | Location | Text |
|---|---|---|
| placeholder | Guidance | [UNVERIFIED: whether BMC South sites count as internal; see reviewer notes] |
| placeholder | Opt-out letters and MyChart messages | [UNVERIFIED: how study teams send MyChart recruitment messages; bulk MyChart messaging is not currently enabled at BMC] |
| placeholder | Opt-out letters and MyChart messages | [CHECK IN INSPIR: (?) help-icon text on checking the DO NOT MAIL list in Epic; help text does not print] |
| placeholder | Opt-out letters and MyChart messages | [CHECK IN INSPIR: how the dean's office sign-off is routed, likely Special Routing on the Initial Review Submission Form, which the printout |
| placeholder | Related links | [PENDING] |
| PURPLE [unv] | Communications/Marketing review | [UNVERIFIED: whether BMC South sites count as internal; see reviewer notes] |
| PURPLE [unv] | Opt-out letters and MyChart messages | [UNVERIFIED: how study teams send MyChart recruitment messages; bulk MyChart messaging is not currently enabled at BMC] |
| PURPLE [unv] | Opt-out letters and MyChart messages | [CHECK IN INSPIR: (?) help-icon text on checking the DO NOT MAIL list in Epic; help text does not print] |
| PURPLE [unv] | Recruiting students, staff, and professionals | [CHECK IN INSPIR: how the dean's office sign-off is routed, likely Special Routing on the Initial Review Submission Form, which the printout |

### Paying_Participants (26)
| Marker | Location | Text |
|---|---|---|
| placeholder | Quick reference | [PENDING DECISION: confirm guidance for sponsor-paid studies] |
| placeholder | Guidance | [UNVERIFIED: confirm with the CTO; source is internal only] |
| placeholder | Guidance | [PENDING DECISION: IRB handling of pending ClinCard exemptions] |
| placeholder | Guidance | [UNVERIFIED: whether ClinCard requirements apply to BMC Brighton and BMC South studies] |
| placeholder | Guidance | [PENDING DECISION: link to IRB-approved consent language for Candex with a gift card alternative once it is posted on the templates page] |
| placeholder | Guidance | [UNVERIFIED: check the threshold each January] |
| placeholder | Guidance | [UNVERIFIED: whether BMC counts across studies the same way] |
| placeholder | Guidance | [UNVERIFIED: BMC practice] |
| placeholder | Guidance | [UNVERIFIED: legal basis for requiring odds; see reviewer notes] |
| placeholder | Guidance | [PENDING DECISION: IRB and CTO guidance on paying minors directly] |
| placeholder | Guidance | [PENDING DECISION: position on participant referral incentives] |
| placeholder | Guidance | [UNVERIFIED: BMC and BU finance rules for international payments] |
| placeholder | Related links | [PENDING] |
| PURPLE [unv] | Paying with BMC funds: ClinCard | [UNVERIFIED: confirm with the CTO; source is internal only] |
| PURPLE [unv] | Paying with BMC funds: ClinCard | [UNVERIFIED: whether ClinCard requirements apply to BMC Brighton and BMC South studies] |
| PURPLE [unv] | Taxes and Social Security Numbers | [UNVERIFIED: check the threshold each January] |
| PURPLE [unv] | Taxes and Social Security Numbers | [UNVERIFIED: whether BMC counts across studies the same way] |
| PURPLE [unv] | Taxes and Social Security Numbers | [UNVERIFIED: BMC practice] |
| PURPLE [unv] | Prize drawings | [UNVERIFIED: legal basis for requiring odds; see reviewer notes] |
| PURPLE [unv] | Special situations | [UNVERIFIED: BMC and BU finance rules for international payments] |
| pend | Quick reference | [PENDING DECISION: confirm guidance for sponsor-paid studies] |
| pend | Payment schedules and proration | [PENDING DECISION: the IRB is considering adding explicit proration expectations (pay across the study, small completion bonus, single payme |
| pend | Paying with BMC funds: ClinCard | [PENDING DECISION: IRB handling of pending ClinCard exemptions] |
| pend | Paying with BU funds | [PENDING DECISION: link to IRB-approved consent language for Candex with a gift card alternative once it is posted on the templates page] |
| pend | Special situations | [PENDING DECISION: IRB and CTO guidance on paying minors directly] |
| pend | Special situations | [PENDING DECISION: position on participant referral incentives] |

### Hub_Post_Approval (1)
| Marker | Location | Text |
|---|---|---|
| PURPLE [unv] | intro | [URL pending Lauren] |

### Amendments (3)
| Marker | Location | Text |
|---|---|---|
| placeholder | Related links | [Continuing Review page, new site URL] |
| placeholder | Related links | [Monitoring, Reporting and Noncompliance page, new site URL] |
| placeholder | Related links | [Cede Review page, new site URL] |

### Continuing_Review_and_Closing (12)
| Marker | Location | Text |
|---|---|---|
| placeholder | Which applies to my study? | [CHECK IN INSPIR: field label on the study summary] |
| placeholder | When is it due, and when will I be reminded? | [UNVERIFIED: how many days before the due date] |
| placeholder | When is it due, and when will I be reminded? | [CHECK IN INSPIR: who else receives the email] |
| placeholder | If approval lapses or a check-in is missed | [UNVERIFIED: which INSPIR form or email route to use for this request] |
| placeholder | Closing your study | [UNVERIFIED: current practice on expediting closure letters; from a 2022 CR Times article] |
| placeholder | How to submit in INSPIR | [CHECK IN INSPIR] |
| RED [chk] | Which applies to my study? | [CHECK IN INSPIR: field label on the study summary] |
| RED [chk] | When is it due, and when will I be reminded? | [CHECK IN INSPIR: who else receives the email] |
| RED [chk] | How to submit in INSPIR | [CHECK IN INSPIR] |
| PURPLE [unv] | When is it due, and when will I be reminded? | [UNVERIFIED: how many days before the due date] |
| PURPLE [unv] | If approval lapses or a check-in is missed | [UNVERIFIED: which INSPIR form or email route to use for this request] |
| PURPLE [unv] | Closing your study | [UNVERIFIED: current practice on expediting closure letters; from a 2022 CR Times article] |

### Reporting_and_Monitoring (3)
| Marker | Location | Text |
|---|---|---|
| placeholder | What to report and when | [UNVERIFIED: which form] |
| placeholder | Related links | [Responsibilities of the PI, new site URL] |
| PURPLE [unv] | What to report and when | [UNVERIFIED: which form] |

### INSPIR_Task_Change_Approved_Study (94)
| Marker | Location | Text |
|---|---|---|
| placeholder | INSPIR: change an approved study (amendments and personnel) | [new site URL] |
| placeholder | Which task do I need? | [new site URL] |
| placeholder | Start the form | [CHECK IN INSPIR: the guide says to use the Version List icon; its screenshot also shows an Edit Incomplete Submissions column. Which reopen |
| placeholder | Revise the application | [CHECK IN INSPIR: button label not in source] |
| placeholder | Attach documents and submit | [new site URL] (×2) |
| placeholder | Attach documents and submit | [CHECK IN INSPIR: icon name] |
| placeholder | Attach documents and submit | [CHECK IN INSPIR: one guide calls this icon Upload Revised Consent] |
| placeholder | Change study personnel | [new site URL] |
| placeholder | Submit | [new site URL] |
| placeholder | Apply a pool to a new draft | [CHECK IN INSPIR: the guide uses both "Close Setup of Study Personnel" and "Close Setup Key Study Personnel"] |
| placeholder | Related links | [new site URL] (×2) |
| RED [chk] | intro | [new site URL] |
| RED [chk] | Which task do I need? | [new site URL] |
| RED [chk] | Start the form | [CHECK IN INSPIR: the guide says to use the Version List icon; its screenshot also shows an Edit Incomplete Submissions column. Which reopen |
| RED [chk] | Revise the application | [CHECK IN INSPIR: button label not in source] |
| RED [chk] | Attach documents and submit | [new site URL] (×2) |
| RED [chk] | Attach documents and submit | [CHECK IN INSPIR: icon name] |
| RED [chk] | Attach documents and submit | [CHECK IN INSPIR: one guide calls this icon Upload Revised Consent] |
| RED [chk] | Change study personnel | [new site URL] |
| RED [chk] | Submit | [new site URL] |
| RED [chk] | Create a pool from a draft | [CHECK IN INSPIR: the guide calls this section "Grant Key Personnel access to the study"; the September 2026 application printout calls it " |
| RED [chk] | Apply a pool to a new draft | [CHECK IN INSPIR: the guide uses both "Close Setup of Study Personnel" and "Close Setup Key Study Personnel"] |
| RED [chk] | Related links | [new site URL] (×2) |
| YELLOW [ck] | Start the form | confirm (×8) |
| YELLOW [ck] | Describe the change | confirm (×3) |
| YELLOW [ck] | Revise the application | confirm (×3) |
| YELLOW [ck] | Attach documents and submit | confirm (×21) |
| YELLOW [ck] | If you are changing the PI or Supervising PI | confirm (×6) |
| YELLOW [ck] | If you are adding or removing people | confirm (×7) |
| YELLOW [ck] | Submit | confirm (×9) |
| YELLOW [ck] | Create a pool from an existing study | confirm (×2) |
| YELLOW [ck] | Create a pool from a draft | confirm (×3) |
| YELLOW [ck] | Apply a pool to a new draft | confirm (×3) |
| YELLOW [ck] | Add BU Charles River Campus people | confirm (×2) |

### INSPIR_Task_Checkins_Reports_Closing (95)
| Marker | Location | Text |
|---|---|---|
| placeholder | INSPIR: check-ins, reports, and closing a study | [new site URL] (×3) |
| placeholder | Before you start | [CHECK IN INSPIR: whether these three forms still route to the PI] |
| placeholder | Before you start | [new site URL] |
| placeholder | Which form do I use? | [new site URL] |
| placeholder | Continuing review and status check-ins | [new site URL] (×3) |
| placeholder | Continuing review and status check-ins | [CHECK IN INSPIR: current section list; guide shows form version 8.0] |
| placeholder | Close a study | [new site URL] |
| placeholder | Close a study | [CHECK IN INSPIR: policy does not require PI sign-off on final reports; the guide still routes to the PI] |
| placeholder | Close a study | [CHECK IN INSPIR: a Close Exempt Study button also appears on the study's Submissions page] |
| placeholder | Report an event or request an exception | [new site URL] |
| placeholder | Report an event or request an exception | [CHECK IN INSPIR: section names after the first; guide shows form version 12.0] |
| placeholder | Recruitment materials and contact information | [new site URL] (×2) |
| placeholder | Recruitment materials and contact information | [CHECK IN INSPIR: where attachments are added; the guide screenshot shows only the first question] |
| placeholder | Recruitment materials and contact information | [CHECK IN INSPIR: attachment step not shown in the guide] |
| placeholder | Write to the IRB | [CHECK IN INSPIR: the All Studies list also has a Correspond icon] |
| RED [chk] | intro | [new site URL] (×3) |
| RED [chk] | Before you start | [CHECK IN INSPIR: whether these three forms still route to the PI] |
| RED [chk] | Before you start | [new site URL] |
| RED [chk] | Which form do I use? | [new site URL] |
| RED [chk] | Continuing review and status check-ins | [new site URL] (×3) |
| RED [chk] | Continuing review and status check-ins | [CHECK IN INSPIR: current section list; guide shows form version 8.0] |
| RED [chk] | Close a study | [new site URL] |
| RED [chk] | Close a study | [CHECK IN INSPIR: policy does not require PI sign-off on final reports; the guide still routes to the PI] |
| RED [chk] | Close a study | [CHECK IN INSPIR: a Close Exempt Study button also appears on the study's Submissions page] |
| RED [chk] | Report an event or request an exception | [new site URL] |
| RED [chk] | Report an event or request an exception | [CHECK IN INSPIR: section names after the first; guide shows form version 12.0] |
| RED [chk] | Recruitment materials and contact information | [new site URL] (×2) |
| RED [chk] | Recruitment materials and contact information | [CHECK IN INSPIR: where attachments are added; the guide screenshot shows only the first question] |
| RED [chk] | Recruitment materials and contact information | [CHECK IN INSPIR: attachment step not shown in the guide] |
| RED [chk] | Write to the IRB | [CHECK IN INSPIR: the All Studies list also has a Correspond icon] |
| YELLOW [ck] | From the Home page (all forms) | confirm (×3) |
| YELLOW [ck] | From the study's own page | confirm (×3) |
| YELLOW [ck] | Continuing review and status check-ins | confirm (×11) |
| YELLOW [ck] | Close a study | confirm (×10) |
| YELLOW [ck] | Report an event or request an exception | confirm (×11) |
| YELLOW [ck] | Recruitment materials and contact information | confirm (×10) |
| YELLOW [ck] | Write to the IRB | confirm (×7) |

### INSPIR_Task_Records_and_Training (90)
| Marker | Location | Text |
|---|---|---|
| placeholder | INSPIR: records, letters, and training | [new site URL] (×2) |
| placeholder | Track or pull back a submission | [UNVERIFIED: confirm that all sign-offs restart] |
| placeholder | Approval letters and approved documents | [CHECK IN INSPIR: what these show and whether to recommend them] |
| placeholder | Approval letters and approved documents | [CHECK IN INSPIR: filter and column names are read from a screenshot, not described in the guide] |
| placeholder | Training records and certificates | [new site URL] |
| placeholder | When you add someone to a study | [CHECK IN INSPIR: the guide text says "CITI Good Clinical Practice Course" row; the screenshot shows the group named "GCP"] |
| placeholder | When you add someone to a study | [UNVERIFIED: "allow a day" is drawn from the CITI guide's note that certificates are generated the day after completion and the Training pag |
| placeholder | When you add someone to a study | [CHECK IN INSPIR: current label of the save button; the 2023 screenshot shows an older label that names the vendor software] |
| placeholder | A study team member's certificate | [CHECK ON CITI: current affiliation and link names] |
| placeholder | A study team member's certificate | [UNVERIFIED] |
| placeholder | INSPIR and FDA Part 11: the vendor's statement | [new site URL] |
| placeholder | INSPIR and FDA Part 11: the vendor's statement | [UNVERIFIED: confirm the statement is still current for the version of the software in use] |
| placeholder | Related links | [new site URL] (×4) |
| RED [chk] | intro | [new site URL] (×2) |
| RED [chk] | Approval letters and approved documents | [CHECK IN INSPIR: what these show and whether to recommend them] |
| RED [chk] | Approval letters and approved documents | [CHECK IN INSPIR: filter and column names are read from a screenshot, not described in the guide] |
| RED [chk] | Training records and certificates | [new site URL] |
| RED [chk] | When you add someone to a study | [CHECK IN INSPIR: the guide text says "CITI Good Clinical Practice Course" row; the screenshot shows the group named "GCP"] |
| RED [chk] | When you add someone to a study | [CHECK IN INSPIR: current label of the save button; the 2023 screenshot shows an older label that names the vendor software] |
| RED [chk] | A study team member's certificate | [CHECK ON CITI: current affiliation and link names] |
| RED [chk] | INSPIR and FDA Part 11: the vendor's statement | [new site URL] |
| RED [chk] | Related links | [new site URL] (×4) |
| YELLOW [ck] | Track or pull back a submission | confirm (×12) |
| YELLOW [ck] | Approval letters and approved documents | confirm (×13) |
| YELLOW [ck] | Hide a study | confirm (×3) |
| YELLOW [ck] | Show a study that was hidden by mistake | confirm (×3) |
| YELLOW [ck] | Your own training | confirm (×2) |
| YELLOW [ck] | Training for people already on a study | confirm (×3) |
| YELLOW [ck] | When you add someone to a study | confirm (×10) |
| YELLOW [ck] | Your own certificate | confirm (×2) |
| YELLOW [ck] | A study team member's certificate | confirm (×8) |
| PURPLE [unv] | Track or pull back a submission | [UNVERIFIED: confirm that all sign-offs restart] |
| PURPLE [unv] | When you add someone to a study | [UNVERIFIED: "allow a day" is drawn from the CITI guide's note that certificates are generated the day after completion and the Training pag |
| PURPLE [unv] | A study team member's certificate | [UNVERIFIED] |
| PURPLE [unv] | INSPIR and FDA Part 11: the vendor's statement | [UNVERIFIED: confirm the statement is still current for the version of the software in use] |

### Hub_Guidance (1)
| Marker | Location | Text |
|---|---|---|
| PURPLE [unv] | intro | [URL pending Lauren] |

### Drugs_and_Devices (4)
| Marker | Location | Text |
|---|---|---|
| placeholder | Significant or non-significant risk? | [UNVERIFIED: current MCSR contact] |
| placeholder | Questions | [UNVERIFIED: confirm IPS address is current] |
| PURPLE [unv] | Other requirements for FDA-regulated studies | [UNVERIFIED: current MCSR contact] |
| PURPLE [unv] | Questions | [UNVERIFIED: confirm IPS address is current] |

### Radiation_in_Research (8)
| Marker | Location | Text |
|---|---|---|
| placeholder | Guidance | [CHECK IN INSPIR: current question wording] |
| placeholder | Guidance | [UNVERIFIED: confirm with Radiation Safety whether an official template exists and where it will be posted] |
| placeholder | Guidance | [UNVERIFIED: whether BMC/BU has its own Radioactive Drug Research Committee or which committee serves this role] |
| placeholder | Related links | [PENDING] |
| PURPLE [unv] | What to answer in INSPIR | [CHECK IN INSPIR: current question wording] |
| PURPLE [unv] | Dose estimates and what Radiation Safety reviews | [UNVERIFIED: whether Radiation Safety will calculate the estimate for the study team, and whether a separate Radiation Safety Committee appl |
| PURPLE [unv] | Explaining radiation risk in the consent form | [UNVERIFIED: confirm with Radiation Safety whether an official template exists and where it will be posted] |
| PURPLE [unv] | Radioactive drugs and federal rules | [UNVERIFIED: whether BMC/BU has its own Radioactive Drug Research Committee or which committee serves this role] |

### Expanded_Access_Emergency_Use (16)
| Marker | Location | Text |
|---|---|---|
| placeholder | Which path applies | [CHECK IN INSPIR: which application to use] |
| placeholder | Which path applies | [UNVERIFIED] |
| placeholder | Guidance | [UNVERIFIED: urgent and after-hours contact route] |
| placeholder | Guidance | [UNVERIFIED: BMC/BUMC process for continuing treatment after an emergency use] |
| placeholder | Guidance | [UNVERIFIED] |
| placeholder | Guidance | [UNVERIFIED: confirm ceding is the default route] |
| placeholder | Guidance | [UNVERIFIED: continuing review or status check-in requirement while treatment continues] |
| placeholder | Questions | [UNVERIFIED: confirm address is current] |
| PURPLE [unv] | Which path applies | [CHECK IN INSPIR: which application to use] |
| PURPLE [unv] | Which path applies | [UNVERIFIED] |
| PURPLE [unv] | Emergency use of a drug or biologic | [UNVERIFIED: urgent and after-hours contact route] |
| PURPLE [unv] | Emergency use of a drug or biologic | [UNVERIFIED: BMC/BUMC process for continuing treatment after an emergency use] |
| PURPLE [unv] | Devices: emergency and compassionate use | [UNVERIFIED] |
| PURPLE [unv] | Sponsor expanded access programs (more than one patient) | [UNVERIFIED: confirm ceding is the default route] |
| PURPLE [unv] | After treatment: reports and follow-up submissions | [UNVERIFIED: continuing review or status check-in requirement while treatment continues] |
| PURPLE [unv] | Questions | [UNVERIFIED: confirm address is current] |

### Humanitarian_Use_Devices (6)
| Marker | Location | Text |
|---|---|---|
| placeholder | Guidance | [UNVERIFIED: name and link the BMC clinical consent policy] |
| placeholder | Guidance | [UNVERIFIED: BMC route for device reports] |
| placeholder | Guidance | [UNVERIFIED: whether the IRB also wants a Reportable Event submission in INSPIR in addition to the required progress report] |
| PURPLE [unv] | Consent and patient information | [UNVERIFIED: name and link the BMC clinical consent policy] |
| PURPLE [unv] | Continuing oversight and reporting | [UNVERIFIED: BMC route for device reports] |
| PURPLE [unv] | Continuing oversight and reporting | [UNVERIFIED: whether the IRB also wants a Reportable Event submission in INSPIR in addition to the required progress report] |

### ClinicalTrials_gov (7)
| Marker | Location | Text |
|---|---|---|
| placeholder | Change for NIH-funded basic experimental studies (BESH) | [FORM STILL ASKS ABOUT NIH-FUNDED BESH; SEE REVIEWER NOTES] |
| placeholder | Posting a consent form (Common Rule) | [UNVERIFIED: content of the OHRP answer] |
| placeholder | Related links | [UNVERIFIED: link not fetched] |
| placeholder | Related links | [PENDING] |
| PURPLE [unv] | Change for NIH-funded basic experimental studies (BESH) | [FORM STILL ASKS ABOUT NIH-FUNDED BESH; SEE REVIEWER NOTES] |
| PURPLE [unv] | Posting a consent form (Common Rule) | [UNVERIFIED: content of the OHRP answer] |
| PURPLE [unv] | Related links | [UNVERIFIED: link not fetched] |

### Genetics_Biospecimens_Repositories (6)
| Marker | Location | Text |
|---|---|---|
| placeholder | GINA and Massachusetts law | [UNVERIFIED: how the IRB applies 70G to waivers] |
| placeholder | GINA and Massachusetts law | [UNVERIFIED: institutional position on returning non-CLIA results is under review with counsel] |
| placeholder | What the IRB needs | [UNVERIFIED: BMC and BU routing and signatory for GDS certifications] |
| PURPLE [unv] | GINA and Massachusetts law | [UNVERIFIED: how the IRB applies 70G to waivers] |
| PURPLE [unv] | Returning results and incidental findings | [UNVERIFIED: institutional position on returning non-CLIA results is under review with counsel] |
| PURPLE [unv] | What the IRB needs | [UNVERIFIED: BMC and BU routing and signatory for GDS certifications] |

### Surveys_Interviews_Focus_Groups (8)
| Marker | Location | Text |
|---|---|---|
| placeholder | Guidance | [PENDING DECISION: whether a revised guide that keeps the same topics needs an amendment] |
| placeholder | Guidance | [UNVERIFIED: INSPIR version comparison does not work on PDFs] |
| placeholder | Guidance | [PENDING DECISION: Zoom and Teams recording and transcription for BMC and BU studies] |
| placeholder | Guidance | [UNVERIFIED: which alternative training programs the IRB currently accepts] |
| PURPLE [unv] | Submitting your instruments | [UNVERIFIED: INSPIR version comparison does not work on PDFs] |
| PURPLE [unv] | Community interviewers and partners | [UNVERIFIED: which alternative training programs the IRB currently accepts] |
| pend | Submitting your instruments | [PENDING DECISION: whether a revised guide that keeps the same topics needs an amendment] |
| pend | Recordings, photos, and transcripts | [PENDING DECISION: Zoom and Teams recording and transcription for BMC and BU studies] |

### Remote_Decentralized_Research (7)
| Marker | Location | Text |
|---|---|---|
| placeholder | Guidance | [PENDING DECISION: whether BMC studies approved with Zoom must amend] |
| placeholder | Guidance | [UNVERIFIED: BU position on BU Zoom vs. Zoom for HIPAA for identifiable health data in research] |
| placeholder | Guidance | [UNVERIFIED: current IPS process; source is 2020] |
| placeholder | Related links | [PENDING] |
| PURPLE [unv] | Video and phone visits | [PENDING DECISION: whether BMC studies approved with Zoom must amend] |
| PURPLE [unv] | Video and phone visits | [UNVERIFIED: BU position on BU Zoom vs. Zoom for HIPAA for identifiable health data in research] |
| PURPLE [unv] | Kits, devices, and study drugs sent to participants | [UNVERIFIED: current IPS process; source is 2020] |

### Deception_Incomplete_Disclosure (2)
| Marker | Location | Text |
|---|---|---|
| placeholder | When debriefing could itself cause harm | [CONFIRM] |
| PURPLE [unv] | What a debriefing script covers | [CONFIRM] |

### Research_Involving_Children (6)
| Marker | Location | Text |
|---|---|---|
| placeholder | How BMC/BUMC documents assent | [CHECK IN INSPIR: the document category for uploading an assent script] |
| placeholder | Tips for the parent forms | [UNVERIFIED: BMC/BUMC practice for continued data use without re-consent] |
| placeholder | Tips for the parent forms | [UNVERIFIED: whether the IRB requires a letter of support from the school] |
| PURPLE [unv] | How BMC/BUMC documents assent | [CHECK IN INSPIR: the document category for uploading an assent script] |
| PURPLE [unv] | When a participant turns 18 | [UNVERIFIED: BMC/BUMC practice for continued data use without re-consent] |
| PURPLE [unv] | Recruiting children | [UNVERIFIED: whether the IRB requires a letter of support from the school] |

### Special_Populations (14)
| Marker | Location | Text |
|---|---|---|
| placeholder | Pregnancy and people who could become pregnant | [CHECK IN INSPIR: the printouts show which boxes carry **, not the on-screen behavior; confirm the box appears after Save and Continue to Ne |
| placeholder | Pregnancy and people who could become pregnant | [UNVERIFIED: confirm standard practice] |
| placeholder | Pregnancy and people who could become pregnant | [UNVERIFIED: confirm whether a pregnancy during the study must be reported to the IRB and how] |
| placeholder | Adults lacking capacity to consent | [UNVERIFIED: link to BMC Legal guidance on remote LAR consent, if one exists] |
| placeholder | Adults lacking capacity to consent | [UNVERIFIED: confirm the IRB's position; the HRPP manual does not state it] |
| placeholder | Prisoners | [UNVERIFIED: the form itself gives no incidental-prisoner instruction; confirm this is the IRB's current instruction] |
| placeholder | Prisoners | [CHECK IN INSPIR: which submission type to use; not in Sept 2026 application printouts] |
| PURPLE [unv] | Which box do I check? | [CHECK IN INSPIR: the printouts show which boxes carry **, not the on-screen behavior; confirm the box appears after Save and Continue to Ne |
| PURPLE [unv] | Pregnancy testing | [UNVERIFIED: confirm standard practice] |
| PURPLE [unv] | Contraception, lactation, and pregnancy during the study | [UNVERIFIED: confirm whether a pregnancy during the study must be reported to the IRB and how] |
| PURPLE [unv] | Who BMC/BUMC accepts as a legally authorized representative | [UNVERIFIED: link to BMC Legal guidance on remote LAR consent, if one exists] |
| PURPLE [unv] | Assent, objection, and regaining capacity | [UNVERIFIED: confirm the IRB's position; the HRPP manual does not state it] |
| PURPLE [unv] | When prisoners are included only incidentally | [UNVERIFIED: the form itself gives no incidental-prisoner instruction; confirm this is the IRB's current instruction] |
| PURPLE [unv] | If a participant becomes incarcerated | [CHECK IN INSPIR: which submission type to use; not in Sept 2026 application printouts] |

### Mandated_Reporting_and_Safety_Plans (2)
| Marker | Location | Text |
|---|---|---|
| placeholder | Quick guide | [UNVERIFIED: whether BMC policy adds internal notification steps] |
| PURPLE [unv] | Mandated reporting in Massachusetts | [UNVERIFIED: whether BMC policy adds internal notification steps] |

### Data_Security_for_Researchers (21)
| Marker | Location | Text |
|---|---|---|
| placeholder | Data Security for Researchers | [PENDING DECISION: a new Technology section and a rewritten Confidentiality section are in draft; update section names and links when they g |
| placeholder | Guidance | [PENDING DECISION: confirm the BU position that BU studies keep data at BU, including data received from BMC] |
| placeholder | Guidance | [PENDING DECISION: public link to the BMC RTP list; BU users cannot open the intranet page] |
| placeholder | Guidance | [UNVERIFIED: BU Box status] |
| placeholder | Guidance | [UNVERIFIED: confirm the IRB accepts a separate folder on the same system] |
| placeholder | Guidance | [PENDING DECISION: whether BMC and BU require an agreement for every transfer, including de-identified data] |
| placeholder | Guidance | [UNVERIFIED: public link, and a route for BU staff who cannot open BMC ServiceNow] |
| placeholder | Guidance | [PENDING DECISION: confirm this hold rule with the Technology section] |
| placeholder | Guidance | [NOT IN SEPT 2026 PRINTOUTS; CONFIRM: no AI question appears in the Study Application] |
| placeholder | Related links | [PENDING] |
| PURPLE [unv] | Where to store identifiable data and master codes | [UNVERIFIED: BU Box status] |
| PURPLE [unv] | The master code | [UNVERIFIED: confirm the IRB accepts a separate folder on the same system] |
| PURPLE [unv] | Apps, vendors, and AI tools | [UNVERIFIED: public link, and a route for BU staff who cannot open BMC ServiceNow] |
| PURPLE [unv] | Apps, vendors, and AI tools | [NOT IN SEPT 2026 PRINTOUTS; CONFIRM: no AI question appears in the Study Application] |
| pend | BMC/BUMC IRB | [PENDING DECISION: a new Technology section and a rewritten Confidentiality section are in draft; update section names and links when they g |
| pend | Which institution's rules apply | [PENDING DECISION: confirm the BU position that BU studies keep data at BU, including data received from BMC] |
| pend | Where to store identifiable data and master codes | [PENDING DECISION: public link to the BMC RTP list; BU users cannot open the intranet page] |
| pend | Keeping records and destroying identifiers | [PENDING DECISION: whether the master code counts as a study record that must be kept for 7 years; see reviewer notes, where analysts curren |
| pend | Sending and sharing data | [PENDING DECISION: whether BMC and BU require an agreement for every transfer, including de-identified data] |
| pend | Texting, email, and calls with participants | [PENDING DECISION: BMC texting options are under review with RTP and the BMC Privacy Office. Replace this collapsible with the agreed BMC an |
| pend | Apps, vendors, and AI tools | [PENDING DECISION: confirm this hold rule with the Technology section] |

### Data_Retention (11)
| Marker | Location | Text |
|---|---|---|
| placeholder | Guidance | [UNVERIFIED: no BMC or BU rule for minors found; check your sponsor contract] |
| placeholder | Guidance | [PENDING DECISION: confirm this list; the HRPP policy does not define "study records"] |
| placeholder | Guidance | [UNVERIFIED: BMC destruction policy text; a 2022 CR Times article lists shredding, burning, pulping, and pulverizing] |
| placeholder | Guidance | [UNVERIFIED: BMC rule for departing investigators' records] |
| placeholder | Guidance | [CHECK IN INSPIR: exact question wording] |
| PURPLE [unv] | How long to keep records | [UNVERIFIED: no BMC or BU rule for minors found; check your sponsor contract] |
| PURPLE [unv] | How to destroy records securely | [UNVERIFIED: BMC destruction policy text; a 2022 CR Times article lists shredding, burning, pulping, and pulverizing] |
| PURPLE [unv] | If you leave BMC or BU | [UNVERIFIED: BMC rule for departing investigators' records] |
| PURPLE [unv] | What the IRB needs in your application | [CHECK IN INSPIR: exact question wording] |
| pend | What counts as a study record | [PENDING DECISION: confirm this list; the HRPP policy does not define "study records"] |
| pend | The master code and the 7-year rule | [PENDING DECISION: the IRB is deciding whether the master code must be kept for the full retention period. Replace this section with the dec |

### Data_Sharing (8)
| Marker | Location | Text |
|---|---|---|
| placeholder | What this means for your IRB submission | [UNVERIFIED: confirm the office prefers DMS Plans not be attached] |
| placeholder | What this means for your IRB submission | [CONFIRM: whether NIH/PCORI repository deposit of de-identified data counts as retention for extra use] |
| placeholder | What this means for your IRB submission | [PENDING DECISION: IRB position on commercial sharing and on sponsor-required future use in studies with direct benefit] |
| placeholder | What this means for your IRB submission | [UNVERIFIED: BMC-specific DMS support contact] |
| PURPLE [unv] | What this means for your IRB submission | [UNVERIFIED: confirm the office prefers DMS Plans not be attached] |
| PURPLE [unv] | What this means for your IRB submission | [CONFIRM: whether NIH/PCORI repository deposit of de-identified data counts as retention for extra use] |
| PURPLE [unv] | Who can help | [UNVERIFIED: BMC-specific DMS support contact] |
| pend | Sharing with companies and commercial use | [PENDING DECISION: IRB position on commercial sharing and on sponsor-required future use in studies with direct benefit] |

### AI_in_Research (18)
| Marker | Location | Text |
|---|---|---|
| placeholder | AI in Human Subjects Research | [NOT IN SEPT 2026 PRINTOUTS; CONFIRM] |
| placeholder | Guidance | [PENDING DECISION: whether study teams must report AI used only to draft documents or interview guides, with no participant data; see review |
| placeholder | Guidance | [NOT IN SEPT 2026 PRINTOUTS; CONFIRM where the question sits in INSPIR] |
| placeholder | Guidance | [PENDING DECISION: confirm which AI routings hold IRB approval] |
| placeholder | Guidance | [PENDING DECISION: whether BU will add an AI review parallel to RTP] |
| placeholder | Bias, care decisions, and companies | [PENDING DECISION: written BMC position on AI tools and BMC data] |
| placeholder | Describe the data flow | [NOT IN SEPT 2026 PRINTOUTS; CONFIRM: whether the AI questions appear on the amendment form] |
| placeholder | Questions | [UNVERIFIED: public link to the RTP Inquiry form, and a route for BU staff without BMC ServiceNow access] |
| placeholder | Related links | [PENDING] |
| PURPLE [unv] | BMC/BUMC IRB | [NOT IN SEPT 2026 PRINTOUTS; CONFIRM] |
| PURPLE [unv] | Two kinds of AI use | [PENDING DECISION: whether study teams must report AI used only to draft documents or interview guides, with no participant data; see review |
| PURPLE [unv] | The AI questions in INSPIR | [NOT IN SEPT 2026 PRINTOUTS; CONFIRM where the question sits in INSPIR] |
| PURPLE [unv] | What happens after you answer Yes | [PENDING DECISION: confirm which AI routings hold IRB approval] |
| PURPLE [unv] | What happens after you answer Yes | [PENDING DECISION: whether BU will add an AI review parallel to RTP] |
| PURPLE [unv] | Using AI tools in your study | [PENDING DECISION: written BMC position on AI tools and BMC data] |
| PURPLE [unv] | Recordings and AI transcription | [PENDING DECISION: whether Zoom and Teams built-in transcription are acceptable for BMC and for BU studies, and under which accounts; stipul |
| PURPLE [unv] | Adding AI after approval | [NOT IN SEPT 2026 PRINTOUTS; CONFIRM: whether the AI questions appear on the amendment form] |
| PURPLE [unv] | Questions | [UNVERIFIED: public link to the RTP Inquiry form, and a route for BU staff without BMC ServiceNow access] |

### Social_Media_Internet_Research (16)
| Marker | Location | Text |
|---|---|---|
| placeholder | Related links | [PENDING] |
| planned | BMC/BUMC IRB | Recruitment and Screening |
| planned | Recruiting on social media and online | Recruitment and Screening |
| planned | Online surveys and participant panels | Data Security for Researchers |
| planned | Online surveys and participant panels | HIPAA in Research |
| planned | Online surveys and participant panels | Obtaining Consent |
| planned | Online surveys and participant panels | Paying Participants |
| planned | Studying existing online content | Do I Need IRB Review? |
| planned | Platform terms of service | Research Involving Children |
| planned | If something goes wrong | Reporting and Monitoring |
| planned | Related links | Recruitment and Screening |
| planned | Related links | Data Security for Researchers |
| planned | Related links | AI in Human Subjects Research |
| planned | Related links | HIPAA in Research |
| planned | Related links | Paying Participants |
| planned | Related links | Reporting and Monitoring |

### Working_with_Other_Institutions (8)
| Marker | Location | Text |
|---|---|---|
| placeholder | Guidance | [CHECK IN INSPIR: where this question appears] |
| placeholder | Community organizations and other recruitment sites | [UNVERIFIED: current process and template for external site participation letters; see reviewer notes] |
| placeholder | Community organizations and other recruitment sites | [UNVERIFIED: BU office and link for MTAs] |
| placeholder | Related links | [2019 guide; confirm it matches current INSPIR] |
| PURPLE [unv] | Adding external investigators | [CHECK IN INSPIR: where this question appears] |
| PURPLE [unv] | Community organizations and other recruitment sites | [UNVERIFIED: current process and template for external site participation letters; see reviewer notes] |
| PURPLE [unv] | Data use and material transfer agreements | [UNVERIFIED: BU office and link for MTAs] |
| PURPLE [unv] | Related links | [2019 guide; confirm it matches current INSPIR] |

### VA_Research (1)
| Marker | Location | Text |
|---|---|---|
| PURPLE [unv] | Dual appointments | [UNVERIFIED: the 2017 BU and VA agreement that describes this process names signatories who are no longer in those roles; confirm the curren |

### Ceding_Review (4)
| Marker | Location | Text |
|---|---|---|
| placeholder | Which IRBs we cede to | [CHECK IN INSPIR: cede-path section names] |
| placeholder | What to have ready | [UNVERIFIED: the 2019 "Creating Your INSPIR Cede Application" PDF is out of date; replace with a task page] |
| RED [chk] | The cede application in INSPIR | [CHECK IN INSPIR: cede-path section names] |
| PURPLE [unv] | What to have ready | [UNVERIFIED: the 2019 "Creating Your INSPIR Cede Application" PDF is out of date; replace with a task page] |

### Community_Engaged_Research (3)
| Marker | Location | Text |
|---|---|---|
| placeholder | Guidance | [UNVERIFIED: which alternative programs the IRB currently accepts and how completion is documented in INSPIR] |
| PURPLE [unv] | Training for community research staff | [UNVERIFIED: which alternative programs the IRB currently accepts and how completion is documented in INSPIR] |
| pend | Recruiting in community settings | [PENDING DECISION: current process and template for external site participation letters, and whether a site is added by one amendment with t |

### International_Research (10)
| Marker | Location | Text |
|---|---|---|
| placeholder | Guidance | [UNVERIFIED: BMC/BUMC position on serving as IRB of record for foreign sites] |
| placeholder | Guidance | [UNVERIFIED: name and link the BMC and BU offices that advise on international data transfer] |
| placeholder | Guidance | [UNVERIFIED: public contact or link for BMC Research Compliance] |
| placeholder | Guidance | [UNVERIFIED: BMC travel registration requirement] |
| placeholder | Guidance | [CHECK: confirm the IRB wants local context documents attached in the Study Attachments question] |
| RED [chk] | Exempt international studies | [CHECK: confirm the IRB wants local context documents attached in the Study Attachments question] |
| PURPLE [unv] | Local collaborators and engagement | [UNVERIFIED: BMC/BUMC position on serving as IRB of record for foreign sites] |
| PURPLE [unv] | Data that crosses borders | [UNVERIFIED: name and link the BMC and BU offices that advise on international data transfer] |
| PURPLE [unv] | Export controls, travel, and shipping | [UNVERIFIED: public contact or link for BMC Research Compliance] |
| PURPLE [unv] | Export controls, travel, and shipping | [UNVERIFIED: BMC travel registration requirement] |

### Conflict_of_Interest (5)
| Marker | Location | Text |
|---|---|---|
| placeholder | Guidance | [UNVERIFIED: where the disclosure should sit in the consent form; see reviewer notes] |
| placeholder | Guidance | [UNVERIFIED: institutional COI process at BMC and BU] |
| placeholder | Related links | [PENDING] |
| PURPLE [unv] | Disclosing a conflict to participants | [UNVERIFIED: where the disclosure should sit in the consent form; see reviewer notes] |
| PURPLE [unv] | Institutional and non-financial conflicts | [UNVERIFIED: institutional COI process at BMC and BU] |

### Hub_About_the_IRB (1)
| Marker | Location | Text |
|---|---|---|
| PURPLE [unv] | intro | [URL pending Lauren] |

### Contact_and_About (12)
| Marker | Location | Text |
|---|---|---|
| placeholder | Who to contact for what | [CHECK: dedicated reliance mailbox?] |
| placeholder | Getting help | [CHECK: OK to invite draft attachments by email?] |
| placeholder | Getting help | [CHECK: confirm this is the preferred same-day route] |
| placeholder | Getting help | [CHECK: confirm fees apply only to industry-sponsored studies, and who issues invoices] |
| placeholder | Getting help | [CHECK wording] |
| placeholder | About the IRB | [CHECK: program current?] |
| PURPLE [unv] | Who to contact for what | [CHECK: dedicated reliance mailbox?] |
| PURPLE [unv] | Meet with the IRB by video or phone | [CHECK: OK to invite draft attachments by email?] |
| PURPLE [unv] | Urgent problems and reportable events | [CHECK: confirm this is the preferred same-day route] |
| PURPLE [unv] | IRB review fees | [CHECK: confirm fees apply only to industry-sponsored studies, and who issues invoices] |
| PURPLE [unv] | IRB office roles | [CHECK wording] |
| PURPLE [unv] | Serve on the IRB or train with us | [CHECK: program current?] |

### Staff_Directory (6)
| Marker | Location | Text |
|---|---|---|
| placeholder | Leadership | [CHECK wording] |
| placeholder | Board Chairs and Vice Chairs | [CHECK: credentials] (×2) |
| PURPLE [unv] | Leadership | [CHECK wording] |
| PURPLE [unv] | Board Chairs and Vice Chairs | [CHECK: credentials] (×2) |

### Ask_the_IRB (7)
| Marker | Location | Text |
|---|---|---|
| placeholder | Ask the IRB | [PENDING DECISION: response target] |
| placeholder | Where to send your question | [PENDING DECISION] |
| placeholder | Ask a question | [PLANNED: embedded or linked form built in the BU form tool; destination pending Lauren] |
| placeholder | Ask a question | [CHECK: confirm email is an accepted alternative once the form exists] |
| placeholder | What happens next | [CHECK: wording approved by the IRB Director] |
| PURPLE [unv] | Ask a question | [CHECK: confirm email is an accepted alternative once the form exists] |
| PURPLE [unv] | What happens next | [CHECK: wording approved by the IRB Director] |

### FAQ (20)
| Marker | Location | Text |
|---|---|---|
| placeholder | Getting started | [CONFIRM: committee name and contact] |
| placeholder | Review path | [CHECK IN INSPIR] |
| placeholder | Review path | [CONFIRM: office policy on priority requests] |
| placeholder | HIPAA and data | [CONFIRM: list of pre-approved tools and link] |
| placeholder | HIPAA and data | [PENDING DECISION: whether built-in transcription is allowed and under which accounts.] |
| placeholder | Recruitment and screening | [CONFIRM: current status of merged BMC hospital sites] |
| placeholder | After approval | [CONFIRM: exempt deviation handling in HRPP] |
| placeholder | After approval | [CONFIRM: preferred IRB name and number format] |
| placeholder | About the IRB | [CONFIRM: internship still runs and who to contact] |
| placeholder | For research participants | [CONFIRM: whether BMC keeps a research contact opt-out list and how patients use it] |
| PURPLE [unv] | Does stem cell or iPSC research need IRB review? | [CONFIRM: committee name and contact] |
| PURPLE [unv] | I chose the wrong Review Path Determination option. What do | [CHECK IN INSPIR] |
| PURPLE [unv] | My study has a deadline (sponsor activation, grant Just-in-T | [CONFIRM: office policy on priority requests] |
| PURPLE [unv] | Does software I use to record, transcribe, or analyze data c | [CONFIRM: list of pre-approved tools and link] |
| PURPLE [unv] | Can I use Teams or Zoom for interviews, and can I use their | [PENDING DECISION: whether built-in transcription is allowed and under which accounts.] |
| PURPLE [unv] | Can a participant be in my study and another study at the sa | [CONFIRM: current status of merged BMC hospital sites] |
| PURPLE [unv] | What do I do about a deviation in an exempt study? | [CONFIRM: exempt deviation handling in HRPP] |
| PURPLE [unv] | How do I cite IRB approval or exemption in a journal article | [CONFIRM: preferred IRB name and number format] |
| PURPLE [unv] | Can I observe an IRB meeting, do an internship, or work for | [CONFIRM: internship still runs and who to contact] |
| PURPLE [unv] | I do not want to be contacted about research. How do I opt o | [CONFIRM: whether BMC keeps a research contact opt-out list and how patients use it] |

### Announcements (18)
| Marker | Location | Text |
|---|---|---|
| placeholder | Announcements | [PENDING: launch date] (×2) |
| placeholder | Announcements | [UNVERIFIED: date] |
| placeholder | Announcements | [CHECK IN INSPIR: where these questions appear] |
| placeholder | Announcements | [CHECK: whether BMC South follows the same date] |
| placeholder | Coming soon | [PENDING: go-live date] |
| placeholder | Coming soon | [PENDING: Advisory Committee approval and dates] |
| placeholder | Coming soon | [PENDING: date] |
| placeholder | Get notified | [PENDING: Lauren: RSS/email options] |
| PURPLE [unv] | Announcements | [PENDING: launch date] (×2) |
| PURPLE [unv] | Announcements | [UNVERIFIED: date] |
| PURPLE [unv] | Announcements | [CHECK IN INSPIR: where these questions appear] |
| PURPLE [unv] | Announcements | [CHECK: whether BMC South follows the same date] |
| PURPLE [unv] | Coming soon | [PENDING: go-live date] |
| PURPLE [unv] | Coming soon | [PENDING: Advisory Committee approval and dates] |
| PURPLE [unv] | Coming soon | [PENDING: date] |
| PURPLE [unv] | Get notified | [PENDING: Lauren: RSS/email options] |

### IRB_Committees (10)
| Marker | Location | Text |
|---|---|---|
| placeholder | IRB Committees and Board Members | [CHECK: confirm this is the office's preference] |
| placeholder | Meetings | [CHECK: meeting time and Zoom format] |
| placeholder | Join the IRB | [CHECK: current hours and meeting frequency] |
| placeholder | Join the IRB | [CHECK: current recruiting priorities] |
| placeholder | Conflicts of interest for board members | [PENDING DECISION: keep public, or move to a members-only location] |
| PURPLE [unv] | BMC/BUMC IRB | [CHECK: confirm this is the office's preference] |
| PURPLE [unv] | Meetings | [CHECK: meeting time and Zoom format] |
| PURPLE [unv] | What serving involves | [CHECK: current hours and meeting frequency] |
| PURPLE [unv] | How to join or nominate someone | [CHECK: current recruiting priorities] |
| PURPLE [unv] | Conflicts of interest for board members | [PENDING DECISION: keep public, or move to a members-only location] |

### For_Board_Members (1)
| Marker | Location | Text |
|---|---|---|
| placeholder | For IRB Board Members (and What Reviewers Look For) | [PLANNED: internal link behind login] |

### For_Research_Participants (6)
| Marker | Location | Text |
|---|---|---|
| placeholder | For Research Participants | [CHECK: what the IRB approval stamp on a consent form shows, so we can tell participants to look for it] |
| placeholder | For Research Participants | [UNVERIFIED: confirm wording with the BMC Clinical Trial Office] |
| placeholder | For Research Participants | [UNVERIFIED: OHRA community page uses ccr@bmc.org; confirm the current address] |
| PURPLE [unv] | How to check that a study is approved | [CHECK: what the IRB approval stamp on a consent form shows, so we can tell participants to look for it] |
| PURPLE [unv] | Payment and costs | [UNVERIFIED: confirm wording with the BMC Clinical Trial Office] |
| PURPLE [unv] | Other ways to get involved | [UNVERIFIED: OHRA community page uses ccr@bmc.org; confirm the current address] |

### For_Research_Participants_ES (6)
| Marker | Location | Text |
|---|---|---|
| placeholder | Para participantes en investigaciones | [CHECK: what the IRB approval stamp on a consent form shows, so we can tell participants to look for it] |
| placeholder | Para participantes en investigaciones | [UNVERIFIED: confirm wording with the BMC Clinical Trial Office] |
| placeholder | Para participantes en investigaciones | [UNVERIFIED: OHRA community page uses ccr@bmc.org; confirm the current address] |
| PURPLE [unv] | Cómo saber si un estudio está aprobado | [CHECK: what the IRB approval stamp on a consent form shows, so we can tell participants to look for it] |
| PURPLE [unv] | Pagos y costos | [UNVERIFIED: confirm wording with the BMC Clinical Trial Office] |
| PURPLE [unv] | Otras formas de participar | [UNVERIFIED: OHRA community page uses ccr@bmc.org; confirm the current address] |

### Policies_and_Regulations (10)
| Marker | Location | Text |
|---|---|---|
| placeholder | Assurance and registration numbers | [CHECK against OHRP] (×2) |
| placeholder | Assurance and registration numbers | [CHECK: letters need reissue] |
| placeholder | Assurance and registration numbers | [CHECK IN INSPIR: wording of the questions about another site's IRB approval] |
| placeholder | How BU and BMC policies fit together | [CHECK] |
| PURPLE [unv] | Assurance and registration numbers | [CHECK against OHRP] (×2) |
| PURPLE [unv] | Assurance and registration numbers | [CHECK: letters need reissue] |
| PURPLE [unv] | Assurance and registration numbers | [CHECK IN INSPIR: wording of the questions about another site's IRB approval] |
| PURPLE [unv] | Standard operating procedures | [CHECK] |
