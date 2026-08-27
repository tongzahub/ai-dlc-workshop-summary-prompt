# Create an AI-DLC Workshop HTML Presentation from This Repository

## Workshop information

* Customer/Organization: `[กรอกชื่อลูกค้า]`
* Workshop name: `AI-Driven Development Life Cycle Workshop`
* Team/Group name: `[กรอกชื่อกลุ่ม หรือระบุว่าเป็น Multi-Team Workspace]`
* Workshop start: `[YYYY-MM-DD HH:mm]`
* Workshop end: `[YYYY-MM-DD HH:mm]`
* Number of teams: `[กรอกจำนวน หรือให้ตรวจสอบจาก Workspace]`
* Presentation audience: `[ผู้บริหาร / Business Team / Technical Team / ผู้เข้าร่วม Workshop]`
* Presentation language: Thai, retaining important English technical terms
* Output format: Self-contained HTML Presentation
* Output directory: `presentation/`

## Objective

วิเคราะห์ข้อมูลจาก Project Repository และสร้าง Presentation สรุปผล Workshop AI-Driven Development Life Cycle ระยะเวลา 2 วัน โดยต้องตอบคำถามสำคัญต่อไปนี้:

1. Workshop ทั้ง 2 วันทำกิจกรรมอะไรไปบ้าง
2. แต่ละกลุ่มพัฒนา Solution อะไร และมี Business Intent อย่างไร
3. AI-DLC Journey ของแต่ละกลุ่ม ตั้งแต่ Business Intent จนถึง Deployment เป็นอย่างไร
4. Feature ที่พัฒนาได้จริงสอดคล้องกับ Requirement ที่กำหนดไว้มากน้อยเพียงใด
5. Feature ใด Complete, Partial, Blocked หรือ Not Implemented
6. แต่ละกลุ่มพบ Challenges และ Risks อะไร
7. มีการตัดสินใจสำคัญหรือ Decisions อะไรระหว่าง Workshop
8. AI มีบทบาทอย่างไรในแต่ละช่วง
9. Human Oversight และ Human Decision เกิดขึ้นตรงจุดใด
10. ทีมได้เรียนรู้อะไร พบปัญหาอะไร และควรดำเนินการต่ออย่างไรหลัง Workshop

Presentation ต้องใช้ข้อมูลและหลักฐานจาก Repository ห้ามสร้างข้อมูล ตัวเลข ผลการทดสอบ หรือสถานะ Deployment ขึ้นเอง

---

# Phase 1: Analyze the Repository

ก่อนสร้าง Presentation ให้สำรวจ Project Repository อย่างเป็นระบบ

ตรวจสอบข้อมูลจาก:

* Project directory structure
* `README*`
* `docs/`
* Workshop notes
* Requirement documents
* User stories และ Acceptance Criteria
* `.kiro/steering/`
* `.kiro/specs/`
* `.kiro/specs/**/requirements.md`
* `.kiro/specs/**/design.md`
* `.kiro/specs/**/tasks.md`
* Architecture documents
* ADR หรือ Decision records
* Application source code
* Test files และ Test configuration
* Infrastructure as Code
* Deployment configuration
* CI/CD pipelines
* Dockerfile และ Container configuration
* Screenshots, diagrams และ Demo assets
* Git status
* Git branches
* Git log และ Commit history
* Git diff
* Uncommitted changes

หลีกเลี่ยงการวิเคราะห์ข้อมูลจาก:

* `node_modules/`
* `vendor/`
* `dist/`
* `build/`
* Generated files
* Binary files
* Coverage output
* Third-party source code

หาก Workspace มีหลายโฟลเดอร์หรือหลายกลุ่ม ให้แยกวิเคราะห์แต่ละกลุ่มตาม Project directory, Git repository หรือข้อมูลใน `.kiro/specs/`

---

# Phase 2: Identify Workshop Activities and Timeline

ใช้ Workshop start และ Workshop end เป็นช่วงเวลาหลักในการวิเคราะห์

ตรวจสอบ:

* Commit ที่เกิดขึ้นระหว่าง Workshop
* Files ที่ถูกสร้างหรือแก้ไข
* Requirements และ Specs ที่ถูกสร้าง
* Features ที่ถูกพัฒนา
* Tests ที่ถูกเพิ่มหรือแก้ไข
* Infrastructure และ Deployment artifacts
* Documentation และ Architecture artifacts
* Demo หรือ Screenshot ที่สร้างขึ้น
* Uncommitted working-tree changes

แยกข้อมูลให้ชัดเจนเป็น:

* มีอยู่ก่อน Workshop
* สร้างหรือแก้ไขใน Day 1
* สร้างหรือแก้ไขใน Day 2
* เกิดขึ้นหลัง Workshop
* ไม่สามารถระบุเวลาได้

ใช้ Git commit timestamp เป็นหลัก

หากเป็น Uncommitted change ให้ระบุว่า:

“Uncommitted working-tree change — ไม่สามารถยืนยันเวลาที่พัฒนาได้”

อย่านับ Starter Code, Template, Boilerplate หรือ Feature ที่มีอยู่ก่อน Workshop เป็นผลงานของทีม

---

# Phase 3: Summarize the Two-Day Workshop Activities

สร้างสรุปกิจกรรมของ Workshop ทั้ง 2 วันจากหลักฐานที่พบ

## Day 1 — Intent and Inception

ค้นหาและสรุปกิจกรรม เช่น:

* Workshop kickoff
* Introduction to AI-DLC
* Team formation
* Use Case selection
* Business Intent definition
* Target User และ Pain Point analysis
* Mob Elaboration
* Requirement clarification
* User Story creation
* Acceptance Criteria
* Unit of Work
* Feature prioritization
* Architecture discussion
* Initial implementation

## Day 2 — Construction and Operations

ค้นหาและสรุปกิจกรรม เช่น:

* Mob Construction
* Architecture refinement
* Code generation
* Feature implementation
* Code review
* Testing
* Defect resolution
* Integration
* Infrastructure preparation
* Deployment preparation
* Deployment
* Demo
* Feedback
* Retrospective

ใช้เฉพาะกิจกรรมที่มีหลักฐานรองรับ

หากไม่สามารถยืนยันกิจกรรมใดได้ ให้ระบุ:

“ไม่พบหลักฐานใน Repository”

สร้าง Timeline แสดง:

`Day 1: Intent → Inception → Design → Initial Construction`

`Day 2: Construction → Testing → Operations → Deployment/Demo`

---

# Phase 4: Reconstruct the AI-DLC Journey of Each Team

สร้าง AI-DLC Journey แยกสำหรับแต่ละกลุ่ม

Journey ต้องแสดง:

`Business Intent`
→ `Requirements`
→ `User Stories and Acceptance Criteria`
→ `Unit of Work`
→ `Architecture and Design`
→ `Implementation`
→ `Testing`
→ `Deployment`
→ `Demo and Feedback`

สำหรับแต่ละ Stage ให้ระบุ:

* กิจกรรมที่ทำ
* Input
* Output หรือ Artifact
* Tools ที่ใช้
* AI Contribution
* Human Oversight
* Human Decision
* เวลาโดยประมาณ
* สถานะ
* หลักฐานจาก Repository
* Challenge หรือ Blocker

## Business Intent

ค้นหา:

* Business problem
* Target User
* User Pain Point
* Expected Business Value
* Success Criteria
* Use Case ของกลุ่ม

## Inception

ค้นหา:

* Requirements
* User Stories
* Acceptance Criteria
* Units of Work
* Requirement priority
* Business rules
* Assumptions
* Requirement clarification
* Decisions ที่เกิดจาก Mob Elaboration

## Construction

ค้นหา:

* Architecture
* Domain model
* Technology stack
* Source code
* Features implemented
* Integrations
* Tests
* Technical decisions
* Documentation
* Decisions ที่เกิดจาก Mob Construction

## Operations

ค้นหา:

* Infrastructure as Code
* Build process
* CI/CD
* Container configuration
* Environment configuration
* Deployment configuration
* Logging และ Monitoring
* Deployment status
* Operational limitations

หาก Workspace มีเพียงหนึ่งกลุ่ม ให้สร้าง Journey ของกลุ่มนั้นหนึ่งชุด

หากมีหลายกลุ่ม ให้ใช้รูปแบบเดียวกันกับทุกกลุ่มเพื่อให้เปรียบเทียบกันได้

---

# Phase 5: Compare Features with Requirements

สร้าง Requirement-to-Feature Traceability Matrix

ใช้แหล่งข้อมูลตามลำดับความน่าเชื่อถือ:

1. `.kiro/specs/**/requirements.md`
2. Formal Requirement documents
3. User Stories และ Acceptance Criteria
4. Workshop notes และ Task lists
5. README และ Product documentation
6. Tests
7. Implementation code

สำหรับแต่ละ Requirement ให้บันทึก:

* Team
* Requirement ID
* Requirement description
* Priority
* Acceptance Criteria
* Planned Feature
* Implemented Feature
* Related source files
* Related tests
* Implementation status
* Test status
* Deployment status
* Evidence
* Gap หรือ Remark

ใช้สถานะต่อไปนี้เท่านั้น:

* `Complete`
* `Partial`
* `Not Implemented`
* `Blocked`
* `Unable to Verify`
* `Not Applicable`

## Status rules

### Complete

ใช้เมื่อพบ Implementation evidence และ Acceptance Criteria ที่เกี่ยวข้องได้รับการตรวจสอบหรือมี Test/Demo evidence

### Partial

ใช้เมื่อมี Implementation บางส่วน แต่ยังขาด Acceptance Criteria, Test, Integration หรือ Operational readiness

### Not Implemented

ใช้เมื่อมี Requirement แต่ไม่พบ Implementation evidence

### Blocked

ใช้เมื่อพบหลักฐานว่ามี Technical, Environment, Access, Dependency หรือ Business blocker

### Unable to Verify

ใช้เมื่อข้อมูลไม่เพียงพอสำหรับยืนยันสถานะ

หาก Requirement ถูกอนุมานจาก Code ให้ระบุ:

“Inferred Requirement — ไม่พบในเอกสาร Requirement อย่างเป็นทางการ”

คำนวณ Requirement Coverage เฉพาะเมื่อทราบจำนวน Requirement ที่ยืนยันแล้ว:

`Requirement Coverage = Complete Requirements / Total Confirmed Requirements × 100`

รายงาน Partial Requirements แยกต่างหาก

ห้ามรวม Partial เป็น Complete

---

# Phase 6: Analyze Planned vs Delivered Features

เปรียบเทียบ:

* Planned Features
* Complete Features
* Partial Features
* Not Implemented Features
* Blocked Features
* Deferred Features
* Additional Features ที่ไม่ได้อยู่ในแผนเดิม

สำหรับแต่ละ Feature ให้ระบุ:

* Requirement ที่เกี่ยวข้อง
* Workshop commit หรือ change evidence
* Implementation files
* Test evidence
* Demo evidence
* Deployment evidence
* Known limitations
* เหตุผลของ Gap

อย่าถือว่า Feature พร้อมใช้งานจริงเพียงเพราะมี Source Code

---

# Phase 7: Analyze Testing, Demo and Deployment

## Testing

หากปลอดภัยและได้รับอนุญาต ให้รัน Existing Test Command โดย:

* ห้ามแก้ Source Code
* ห้ามแก้ Test
* ห้ามแก้ Snapshot
* ห้ามติดตั้ง Dependency เพิ่ม
* ห้ามเปลี่ยน Configuration

บันทึก:

* Test command
* Pass/Fail
* Tests passed
* Tests failed
* Tests skipped
* Coverage หากมีอยู่แล้ว
* Environment blocker

หากพบ Test files แต่ไม่ได้รัน ให้ระบุ:

“พบ Test files แต่ไม่ได้ยืนยันผลจากการ Execute”

แยกให้ชัดเจนระหว่าง:

* Automated Test
* Manual Test
* Demo Evidence
* Claim ที่ไม่มีหลักฐาน

## Deployment

ใช้สถานะ:

* `Verified Deployed`
* `Deployment Configured but Not Verified`
* `Local Demo Only`
* `Prototype`
* `Blocked`
* `No Deployment Evidence`

ใช้ `Verified Deployed` เฉพาะเมื่อมีหลักฐาน เช่น:

* Deployment URL ที่ตรวจสอบได้
* Successful deployment log
* Successful pipeline result
* Deployment output
* Recorded deployment evidence

การมี Dockerfile, CDK, CloudFormation, Terraform, Pipeline หรือ Deployment Script เพียงอย่างเดียว ให้ใช้:

`Deployment Configured but Not Verified`

ห้าม Deploy Application หรือแก้ Cloud Resources ใน Task นี้

---

# Phase 8: Analyze Challenges, Risks and Decisions

สร้างรายการแยกเป็นสามหมวด

## Challenges

วิเคราะห์ปัญหาที่เกิดขึ้นจริง เช่น:

* Requirement ไม่ชัดเจน
* Scope ใหญ่เกินเวลาของ Workshop
* Technical complexity
* Integration issue
* Dependency issue
* Environment issue
* Access หรือ Permission
* Test failure
* Deployment failure
* Context ที่ให้ AI ไม่เพียงพอ
* ความไม่คุ้นเคยกับ AI Tool

สำหรับแต่ละ Challenge ให้ระบุ:

* Description
* Stage ที่เกิด
* Impact
* Evidence
* วิธีที่ทีมจัดการ
* Current status

## Risks

วิเคราะห์ความเสี่ยง เช่น:

* AI-generated code correctness
* Security
* Data Privacy
* Maintainability
* Requirement misinterpretation
* Missing tests
* Integration readiness
* Operational readiness
* Production readiness
* Over-reliance on AI
* Knowledge transfer

สำหรับแต่ละ Risk ให้ระบุ:

* Risk description
* Likelihood: High / Medium / Low
* Impact: High / Medium / Low
* Evidence
* Proposed mitigation

ห้ามสร้าง Risk score เชิงตัวเลขหากไม่มีเกณฑ์ที่กำหนดไว้

## Decisions

ค้นหาและสรุปการตัดสินใจสำคัญ เช่น:

* Business scope
* Feature priority
* Architecture
* Technology selection
* Data model
* Integration approach
* Security
* Test strategy
* Deployment approach
* Feature ที่ตัดออกหรือเลื่อนออกไป

สำหรับแต่ละ Decision ให้ระบุ:

* Decision
* Reason
* Alternatives considered หากมี
* Decision owner หากมีข้อมูล
* AI proposal หรือ recommendation
* Human validation
* Outcome
* Evidence

หากไม่พบ Decision record ให้ระบุว่า:

“ไม่พบการบันทึก Decision อย่างเป็นทางการใน Repository”

---

# Phase 9: Explain AI and Human Oversight in Each Stage

อธิบายบทบาทของ AI และ Human Oversight แยกตาม AI-DLC Stage

สร้างตารางรูปแบบ:

| AI-DLC Stage | AI Contribution | Human Oversight | Human Decision | Output | Evidence |

พิจารณาบทบาทของ AI เช่น:

* Business Intent clarification
* Requirement decomposition
* Clarifying questions
* User Story generation
* Acceptance Criteria generation
* Unit of Work planning
* Architecture proposal
* Domain model proposal
* Code generation
* Test generation
* Code review assistance
* Documentation
* Troubleshooting
* Infrastructure generation
* Deployment configuration

พิจารณา Human Oversight เช่น:

* Business problem validation
* Business priority
* Requirement approval
* Acceptance Criteria validation
* Architecture decision
* Technology selection
* Security and compliance
* Code review
* Test acceptance
* Risk acceptance
* Deployment approval
* Business acceptance

แยกข้อมูลเป็น:

### Verifiable AI Contribution

มี Artifact หรือหลักฐานใน Repository

### Likely AI-Assisted Work

มีแนวโน้มว่าใช้ AI แต่ไม่สามารถยืนยันได้

### Human Oversight and Decisions

มี Decision หรือ Validation ที่บันทึกไว้

ห้ามกล่าวว่า AI สร้าง Feature หากไม่มีหลักฐานรองรับ

---

# Phase 10: Summarize Lessons Learned and Next Steps

## Lessons Learned

สรุป:

* สิ่งที่ทีมเรียนรู้เกี่ยวกับ AI-DLC
* Stage ที่ AI ช่วยได้มากที่สุด
* Stage ที่ยังต้องพึ่ง Human Judgment
* รูปแบบ Requirement ที่ทำให้ AI ทำงานได้ดี
* Context ที่ AI ต้องการ
* ปัญหาที่เกิดจาก Requirement หรือ Prompt ไม่ชัดเจน
* สิ่งที่ทีมจะทำต่างออกไปครั้งหน้า
* Artifact ที่ควรจัดเก็บเป็น Persistent Context
* Practice ที่ควรนำไปใช้ต่อ

ใช้เฉพาะข้อมูลจาก Workshop notes, Repository artifacts หรือ Retrospective

หากไม่มีข้อมูล ให้แสดงเป็น:

“คำถามสำหรับ Team Retrospective”

อย่าสร้าง Lessons Learned แทนทีม

## Next Steps

แบ่งเป็น:

### Immediate

* แก้ Feature หรือ Defect ที่ค้าง
* เพิ่ม Missing Tests
* ยืนยัน Requirement
* แก้ Security issue
* เตรียม Demo หรือ Deployment evidence

### Next 30 Days

* ทำ Pilot ต่อกับ Use Case จริง
* ปรับ Requirement และ Acceptance Criteria
* เพิ่ม Quality Gate
* ปรับ AI Prompt, Steering หรือ Specs
* เตรียม Deployment environment
* สร้าง Security และ Governance guideline

### Next 60–90 Days

* วัดผล Productivity และ Quality
* เปรียบเทียบกับ Development baseline
* สร้าง Reusable AI-DLC templates
* สร้าง Community of Practice
* ประเมิน Production readiness
* วางแผนขยายผลไปยังทีมอื่น

แยกให้ชัดเจนระหว่าง:

* Recommendation จากหลักฐาน
* รายการที่ทีมบันทึกไว้
* รายการที่ต้องได้รับการตัดสินใจจากผู้บริหาร

---

# Phase 11: Create the Evidence Report

ก่อนสร้าง Presentation ให้สร้าง:

`presentation/workshop-evidence-report.md`

เนื้อหาต้องประกอบด้วย:

1. Repository summary
2. Evidence sources inspected
3. Two-day Workshop activities
4. Workshop Git timeline
5. Team overview
6. AI-DLC Journey of each team
7. Requirements discovered
8. Requirement-to-Feature Traceability Matrix
9. Planned vs Delivered
10. Architecture and technology
11. Test evidence
12. Demo and Deployment evidence
13. Challenges
14. Risks
15. Decisions
16. AI Contribution
17. Human Oversight
18. Lessons Learned
19. Recommended Next Steps
20. Missing or Unverified Information
21. Sensitive information excluded

สำหรับข้อสรุปสำคัญ ให้ระบุหลักฐานโดยใช้:

* File path
* Requirement ID
* Task ID
* Test name
* Commit hash
* Deployment evidence

ห้ามใส่ Secret หรือ Source Code ขนาดใหญ่ในรายงาน

---

# Phase 12: Ask Necessary Questions

หลังจากวิเคราะห์ Repository แล้ว ถ้ามีข้อมูลสำคัญไม่ครบ ให้ถามไม่เกิน 5 คำถาม

ให้ความสำคัญกับ:

1. Business Intent และ Target User
2. กิจกรรม Workshop ที่ไม่ได้บันทึกใน Repository
3. Original Requirements หรือ Success Criteria
4. Demo และ Deployment evidence
5. Human Decisions, Challenges และ Lessons Learned

ในแต่ละคำถาม ให้บอก:

* พบข้อมูลอะไรแล้ว
* ข้อมูลใดยังขาด
* เหตุใดข้อมูลนี้จึงมีผลต่อ Presentation

หากข้อมูลเพียงพอ ให้สร้าง Presentation ต่อได้ทันที

---

# Phase 13: Create the HTML Presentation

สร้าง Presentation ที่:

* ใช้ภาษาไทย
* คงคำศัพท์สำคัญเป็นภาษาอังกฤษ
* เหมาะกับทั้งผู้บริหารและ Technical Team
* เน้น Business Outcome และ Delivery Evidence
* มีประมาณ 14–18 สไลด์
* เพิ่มสไลด์ตามจำนวนกลุ่มเมื่อจำเป็น

## Required slide structure

### Slide 1 — Title

ชื่อ:

“AI-Driven Development Life Cycle Workshop”

คำบรรยาย:

“From Business Intent to Deployment in Two Days”

แสดง:

* Customer
* Workshop date
* Number of participants หากมีข้อมูล
* Number of teams
* Solution หรือ Project names

### Slide 2 — Executive Summary

สรุป:

* จำนวนกลุ่ม
* จำนวน Use Cases
* จำนวน Confirmed Requirements
* Complete/Partial/Blocked Features
* Test status
* Demo status
* Deployment status
* Outcome สำคัญที่สุด

### Slide 3 — Workshop Objectives and AI-DLC Model

อธิบาย:

* Workshop objectives
* Intent
* Inception
* Construction
* Operations
* AI-powered execution
* Human Oversight
* Dynamic Team Collaboration

### Slide 4 — What We Did During the Two-Day Workshop

สรุปกิจกรรม Day 1 และ Day 2

แสดงเป็น Timeline:

* Day 1: Intent, Mob Elaboration, Requirements, Design
* Day 2: Mob Construction, Coding, Testing, Deployment, Demo

ใช้เฉพาะกิจกรรมที่ยืนยันได้

### Slide 5 — Workshop Timeline and Evidence

แสดง Event สำคัญตามเวลาโดยใช้:

* Commit
* Specs
* Source changes
* Tests
* Deployment artifacts
* Demo evidence

แยก Verified และ Estimated events

### Slide 6 — Team Overview

สร้างตาราง:

| Team | Business Intent | Target User | Planned Features | Delivered Features | Test Status | Deployment Status |

### Slide 7 เป็นต้นไป — AI-DLC Journey of Each Team

สร้างอย่างน้อย 1 สไลด์ต่อกลุ่ม

แต่ละสไลด์ต้องแสดง:

* Team name
* Solution
* Business Intent
* Target User
* Requirements
* Architecture
* Features implemented
* Tests
* Deployment
* AI Contribution
* Human Oversight
* Challenge
* Outcome
* Evidence

แสดง Journey:

`Business Intent → Inception → Construction → Testing → Operations → Deployment`

ใช้รูปแบบเดียวกันทุกกลุ่มเพื่อให้เปรียบเทียบได้

### Slide ถัดไป — Requirement-to-Feature Traceability

แสดง:

| Team | Requirement | Priority | Planned Feature | Delivered Result | Status | Test Evidence | Deployment Evidence |

ใช้ Appendix หากข้อมูลมากเกินหนึ่งสไลด์

### Slide ถัดไป — Planned vs Delivered

เปรียบเทียบ:

* Planned
* Complete
* Partial
* Blocked
* Not Implemented
* Additional Features

อธิบาย Gap และสาเหตุ

### Slide ถัดไป — Quality, Testing and Deployment

แสดง:

* Automated tests
* Manual tests
* Acceptance Criteria
* Demo evidence
* CI/CD
* Deployment status
* Production readiness
* Unverified items

### Slide ถัดไป — Challenges, Risks and Decisions

แบ่งเป็น 3 ส่วน:

* Challenges encountered
* Risks identified
* Important decisions

แสดง Impact, Mitigation และ Evidence

### Slide ถัดไป — AI Contribution and Human Oversight

แสดงบทบาท AI และ Human แยกตาม Stage:

* Intent
* Inception
* Construction
* Testing
* Operations
* Deployment

ระบุจุดที่ AI ช่วยเร่งงาน และจุดที่ Human Judgment มีความสำคัญ

### Slide ถัดไป — Cross-Team Insights

เปรียบเทียบ:

* กลุ่มที่ Requirement ชัดเจน
* Stage ที่ทำได้เร็ว
* Stage ที่ติดปัญหา
* AI Contribution ที่เห็นผล
* Human Decision ที่สร้างผลกระทบ
* ปัจจัยที่ทำให้ Deploy สำเร็จหรือไม่สำเร็จ

แยก Fact ออกจาก Observation

### Slide ถัดไป — Lessons Learned

สรุป:

* สิ่งที่เรียนรู้
* สิ่งที่ทำได้ดี
* สิ่งที่ควรปรับปรุง
* AI limitation
* Process improvement
* Questions for Retrospective

### Slide ถัดไป — Recommended Next Steps

แสดง:

* Immediate actions
* Next 30 days
* Next 60–90 days
* Decision หรือ Support ที่ต้องการจากผู้บริหาร

### Slide สุดท้าย — Closing

ชื่อ:

“From Workshop Experiment to Repeatable Delivery”

สรุป:

* What was proven
* What remains incomplete
* What should happen next

---

# HTML Presentation Requirements

สร้างไฟล์หลัก:

`presentation/index.html`

HTML Presentation ต้อง:

* เป็น Self-contained HTML
* เปิดด้วย Web Browser ได้โดยตรง
* ทำงานผ่าน `file://` ได้
* ไม่ต้องใช้ Web Server
* ไม่ใช้ CDN
* ไม่โหลด External JavaScript
* ไม่โหลด External CSS
* ไม่โหลด Remote Font
* ไม่ใช้ Tracking หรือ Analytics
* เขียน CSS และ JavaScript ไว้ภายใน HTML
* ใช้ JavaScript แบบ Vanilla
* ไม่เพิ่ม Dependency ให้ Project
* ไม่แก้ `package.json` หรือ Application manifest
* ไม่ต้อง Build ก่อนเปิด
* ใช้ Layout 16:9
* Responsive สำหรับ Notebook และ Projector
* รองรับ Fullscreen
* รองรับ Keyboard navigation
* `Arrow Right`, `Page Down`, `Space`: Next slide
* `Arrow Left`, `Page Up`: Previous slide
* `Home`: First slide
* `End`: Last slide
* `F`: Fullscreen
* `P`: Print mode
* มีปุ่ม Next/Previous
* มี Slide number
* มี Progress indicator
* มี Print CSS สำหรับ Export เป็น PDF
* ซ่อน Navigation controls ขณะ Print
* หนึ่งสไลด์ต่อหนึ่งหน้าขณะ Print
* ห้ามมี Horizontal scroll
* ห้ามมีข้อความล้นสไลด์
* ห้ามใช้ข้อความเล็กเพื่อบีบข้อมูล
* หากข้อมูลมาก ให้สร้าง Appendix slides

ใช้ Semantic HTML และ Accessible color contrast

หากต้องสร้าง Diagram ให้ใช้:

* HTML และ CSS
* Inline SVG
* Mermaid เฉพาะเมื่อ Library มีอยู่แล้วและทำงานแบบ Offline

ห้ามเชื่อมต่อ Internet เพื่อ Render Diagram

หากใช้ Screenshot หรือ Asset:

* ใช้เฉพาะไฟล์ที่อยู่ใน Repository
* ตรวจสอบว่าไม่มี Secret หรือข้อมูลลับ
* ใช้ Relative path ภายใต้ `presentation/assets/`
* ห้ามใช้ภาพที่ไม่มีสิทธิ์หรือไม่ทราบแหล่งที่มา

เพิ่ม Evidence panel หรือ Speaker Notes แบบซ่อน/ขยายได้ในแต่ละสไลด์ โดยแสดง:

* File paths
* Requirement IDs
* Test names
* Commit hashes
* Evidence confidence

อย่าแสดง Evidence details ที่รบกวนเนื้อหาหลักบนสไลด์

## Visual style

ใช้สไตล์:

* Professional
* Modern
* Executive-friendly
* Clean and minimal
* White หรือ Light background
* Navy/Blue เป็นสีหลัก
* Orange เป็น Accent
* Green/Yellow/Red/Gray สำหรับสถานะ
* Typography อ่านง่าย
* ไม่ใช้ Decorative AI images ที่ไม่มีประโยชน์ต่อเนื้อหา

Status colors:

* Green: Complete/Verified
* Yellow: Partial
* Red: Blocked/Not Implemented
* Gray: Unable to Verify/Not Applicable

หนึ่งสไลด์ควรมีหนึ่ง Key Message และไม่เกิน 4–5 ประเด็นหลัก

---

# Output Files

สร้างไฟล์:

1. `presentation/index.html`
2. `presentation/workshop-evidence-report.md`
3. `presentation/README.md`

ใน `README.md` ให้อธิบาย:

* วิธีเปิด Presentation
* Keyboard shortcuts
* วิธีเข้า Fullscreen
* วิธี Print หรือ Export PDF
* Evidence sources ที่ใช้
* Known limitations
* ข้อมูลที่ยังไม่ได้รับการยืนยัน

---

# Safety and Authorization

Task นี้อนุญาตให้:

* อ่านไฟล์ใน Workspace
* ใช้ Read-only Git commands
* รัน Existing Tests เมื่อปลอดภัยและได้รับอนุญาต
* สร้างไฟล์ภายใต้ `presentation/`

Task นี้ไม่อนุญาตให้:

* แก้ Application source code
* Implement missing features
* แก้ Test
* แก้ Configuration
* แก้ `.kiro/`
* ติดตั้ง Dependency
* Commit
* Push
* Deploy
* แก้ Cloud Resources
* เปิดเผย Secret หรือข้อมูลลูกค้าที่เป็นความลับ

---

# Final Validation

ก่อนจบงาน ให้ตรวจสอบว่า:

* สรุปกิจกรรมของ Workshop ครบทั้ง 2 วัน
* มี AI-DLC Journey ของทุกกลุ่ม
* Journey เริ่มจาก Business Intent และจบที่ Deployment/Demo
* Requirement เชื่อมโยงกับ Feature
* Complete และ Partial ถูกแยกจากกัน
* Challenge, Risk และ Decision มีหลักฐาน
* AI Contribution ไม่ถูกกล่าวเกินหลักฐาน
* Human Oversight แสดงในทุก Stage ที่เกี่ยวข้อง
* Lessons Learned ไม่ถูกสร้างแทนทีม
* Next Steps มีความชัดเจน
* งานก่อน Workshop ไม่ถูกนับเป็นผลงาน Workshop
* Deployment status ไม่ถูกกล่าวเกินจริง
* ไม่มี Secret หรือข้อมูลลับ
* HTML เปิดแบบ Offline ได้
* Keyboard navigation ทำงาน
* Print/Export PDF ทำงาน
* ไม่มีข้อความล้นหรือทับกัน
* Application source code ไม่ถูกแก้ไข

เมื่อเสร็จแล้ว ให้รายงาน:

* Files created
* Teams analyzed
* Workshop activities discovered
* Requirements found
* Complete/Partial/Blocked/Not Implemented counts
* Test status
* Deployment status
* Challenges and risks
* Important decisions
* Missing information
* Unverified claims
