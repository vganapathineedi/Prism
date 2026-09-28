# Prism Personas & Responsibility Matrix

## Overview
Complete responsibility breakdown across all 7 Prism personas, including end-users and admin roles.

---

## Quick Reference Table

| Persona | Role | Primary Focus | Key Responsibilities | Dashboards | Permissions |
|---------|------|-----------------|---------------------|------------|-------------|
| **Sarah Chen** | Individual Contributor | Personal work prioritization | ✓ View personal work queue<br>✓ Track capacity<br>✓ Hit informal commitments | Dashboard<br>Queue<br>Sources<br>Capacity | Read own work<br>Delegate to peers |
| **Alex Rodriguez** | Software Engineer (IC) | Personal execution | ✓ Understand task priority<br>✓ Manage time allocation<br>✓ Reduce context-switching | Dashboard<br>Queue<br>Sources<br>Capacity | Read own work<br>Request help |
| **Alex Torres** | Engineering Manager | Team capacity & alignment | ✓ Monitor team workload<br>✓ Identify overallocation<br>✓ Set team priorities<br>✓ Redistribute work | Dashboard (Team)<br>Queue (Team)<br>Capacity<br>Backlog | Read team work<br>Reassign tasks<br>Set priorities<br>Override priority |
| **Jennifer Lee** | VP Engineering | Organizational strategy execution | ✓ Cascade org priorities<br>✓ Monitor focus vs. strategy<br>✓ Identify misalignment<br>✓ Make capacity decisions | Dashboard (Org)<br>Executive View | Set org priorities<br>Drill down by dept<br>View rollups |
| **Marcus** | HR Business Partner | Compliance & people activities | ✓ Surface HR priorities<br>✓ Track completion status<br>✓ Coordinate across teams<br>✓ Ensure compliance | HR Tasks<br>Completion Status | Assign HR tasks<br>View HR workflows<br>Generate reports |
| **Lisa** | Product Manager | Cross-functional work balance | ✓ Prioritize ad-hoc work<br>✓ Protect deep work time<br>✓ Hit commitments<br>✓ Manage stakeholder expectations | Dashboard<br>Queue<br>Capacity<br>Dependencies | Read own work<br>Share context<br>Communicate availability |
| **Devon** | Integration Administrator | Integration lifecycle management | ✓ Discover integrations<br>✓ Configure & test<br>✓ Deploy safely<br>✓ Monitor health<br>✓ Troubleshoot issues | Dashboard<br>Integrations<br>Health Monitor<br>Audit Logs | Configure integrations<br>Deploy<br>Monitor health<br>Manage credentials<br>View logs |
| **Rachel** | Security/Compliance Lead | Governance & compliance | ✓ Approve integrations<br>✓ Enforce compliance<br>✓ Audit logging<br>✓ Generate reports<br>✓ Risk management | Dashboard<br>Integrations<br>Approvals<br>Audit Logs | Approve/deny integrations<br>Set compliance rules<br>View audit trail<br>Generate reports |

---

## Detailed Responsibility Breakdown

### End-User Personas

#### 1. Sarah Chen - Senior Software Engineer (Individual Contributor)
**Core Job:** Execute high-impact work efficiently

| Category | Responsibilities |
|----------|------------------|
| **Work Management** | View prioritized non-project work queue<br>Understand why items are ranked<br>Hit informal commitments |
| **Capacity** | Track hours committed vs. available<br>Know when overallocated<br>Protect focus time |
| **Context** | See work across 4+ sources (email, Slack, manager, org)<br>Understand dependencies<br>Know organizational alignment |
| **Decisions** | Accept/negotiate work<br>Defer lower-priority items<br>Communicate availability |

**Success Metrics:** On-time completion • Fewer missed commitments • Focus time protected

---

#### 2. Alex Rodriguez - Software Engineer (Individual Contributor)
**Core Job:** Execute quality work with clear priorities

| Category | Responsibilities |
|----------|------------------|
| **Work Management** | Understand task priority<br>See full work queue<br>Complete promised work |
| **Capacity** | Manage personal time allocation<br>Reduce context-switching<br>Deliver quality work |
| **Alignment** | Understand manager priorities<br>See how work connects to org goals<br>Know team focus |
| **Coordination** | Request help when needed<br>Share blockers<br>Collaborate on dependencies |

**Success Metrics:** Task completion • Code quality • Team collaboration

---

#### 3. Alex Torres - Engineering Manager
**Core Job:** Align team execution with strategy & manage capacity

| Category | Responsibilities |
|----------|------------------|
| **Team Visibility** | Monitor team's total workload (sprint + non-project)<br>Identify at-risk commitments<br>See overallocation early |
| **Capacity Planning** | Distribute work fairly<br>Prevent burnout<br>Make realistic resource decisions<br>Forecast constraints |
| **Priority Management** | Set team priorities<br>Communicate expectations clearly<br>Override priorities when needed<br>Align team with leadership |
| **Team Health** | Reduce status meetings<br>Identify blockers<br>Spot burnout patterns<br>Adjust workload proactively |
| **Delegation** | Assign ad-hoc work confidently<br>Know who has capacity<br>Redistribute when overallocated<br>Track completion |

**Success Metrics:** Team utilization • Fewer surprises • Meeting reduction • Team morale

---

#### 4. Jennifer Lee - VP Engineering (Senior Executive)
**Core Job:** Ensure strategy translates to execution & make capacity decisions

| Category | Responsibilities |
|----------|------------------|
| **Strategic Alignment** | Communicate organizational priorities once<br>See real-time focus vs. strategy<br>Identify misalignment early<br>Understand if priorities are being executed |
| **Capacity Governance** | Make data-driven resource decisions<br>Understand org-wide constraints<br>Allocate budget and headcount accordingly<br>Plan for growth |
| **Priority Cascade** | Set company/business-unit priorities<br>See them cascade through org<br>Monitor execution<br>Adjust as needed |
| **Risk Management** | Spot strategic risks<br>Understand dependencies across teams<br>Make trade-off decisions<br>Communicate with board |

**Success Metrics:** Strategy-execution alignment • Informed decisions • On-time deliverables

---

#### 5. Marcus - HR Business Partner
**Core Job:** Ensure HR activities don't fall through cracks

| Category | Responsibilities |
|----------|------------------|
| **Activity Management** | Surface HR priorities (onboarding, compliance, training)<br>Track completion status<br>Ensure deadlines are met<br>Coordinate across teams |
| **Coordination** | Assign tasks to finance, IT, managers<br>Reduce manual follow-ups<br>See dependencies<br>Flag delays |
| **Compliance** | Track compliance deadlines<br>Ensure completion rates<br>Generate reports<br>Audit trails |

**Success Metrics:** Reduced onboarding delays • Higher compliance rates • Fewer follow-ups

---

#### 6. Lisa - Product Manager (Cross-functional)
**Core Job:** Balance formal and ad-hoc work across functions

| Category | Responsibilities |
|----------|------------------|
| **Work Balance** | Prioritize ad-hoc requests<br>Protect deep work time<br>Know what's coming<br>Plan capacity |
| **Commitments** | Hit promised deliverables<br>Know true availability<br>Communicate realistically<br>Prevent overcommit |
| **Cross-functional** | Coordinate across teams<br>Share context<br>Manage stakeholder expectations<br>Resolve dependencies |

**Success Metrics:** Balanced workload • Hit commitments • Stakeholder satisfaction

---

### Admin Personas

#### 7. Devon - Integration Administrator
**Core Job:** Manage complete integration lifecycle

| Category | Responsibilities |
|----------|------------------|
| **Discovery** | Browse integration marketplace<br>Understand capabilities<br>Assess org readiness<br>Plan rollout |
| **Configuration** | Set up integrations via wizard<br>Configure auth methods<br>Set data scope & sync frequency<br>Map fields |
| **Testing** | Validate configuration<br>Test connectivity<br>Sample data sync<br>Verify signals |
| **Deployment** | Deploy safely (canary → gradual → full)<br>Monitor rollout<br>Adjust as needed<br>Rollback if issues |
| **Operations** | Monitor integration health<br>Track uptime & latency<br>Manage credentials & rotation<br>Troubleshoot failures |
| **Support** | Respond to integration issues<br>Optimize performance<br>Manage API quotas<br>Document status |

**Success Metrics:** Integration uptime >99% • <1% deployment errors • <15min MTTR

---

#### 8. Rachel - Security/Compliance Lead
**Core Job:** Govern integrations & ensure compliance

| Category | Responsibilities |
|----------|------------------|
| **Approval** | Review integration requests<br>Verify compliance checklist<br>Assess security posture<br>Approve/deny integrations |
| **Compliance** | Define data protection policies<br>Set compliance requirements<br>Enforce audit logging<br>Verify certifications |
| **Risk Management** | Assess vendor security<br>Review data flows<br>Identify privacy risks<br>Mitigate threats |
| **Audit** | Access complete audit logs<br>Generate compliance reports<br>Export audit trails<br>Track all changes |
| **Governance** | Enforce regulatory requirements<br>Set encryption standards<br>Define retention policies<br>Manage vendor assessments |

**Success Metrics:** 100% audit readiness • Zero unauthorized data flows • <2 day approval time

---

## Responsibility Distribution

### By Function

**Work Prioritization & Execution:**
- Sarah Chen, Alex Rodriguez, Lisa - Personal queues & capacity
- Alex Torres - Team-level visibility & coordination

**Organizational Alignment:**
- Jennifer Lee - Strategy cascade & execution monitoring
- Marcus - HR/compliance activities

**Integration & Systems:**
- Devon - Technical setup & operations
- Rachel - Governance & compliance

### By Capability

| Capability | Owner(s) | Watchers |
|-----------|---------|----------|
| Personal queue prioritization | Sarah, Alex R., Lisa | Alex T., Marcus |
| Team capacity planning | Alex T. | Jennifer L. |
| Org priority cascade | Jennifer L. | Alex T., All ICs |
| Integration discovery | Devon | Rachel |
| Integration configuration | Devon | Rachel |
| Integration approval | Rachel | Devon |
| Compliance enforcement | Rachel | Devon, Jennifer L. |
| Audit logging | Rachel | Jennifer L. (for reports) |

---

## Access Matrix

### Data Visibility

| Data Type | Sarah | Alex R. | Alex T. | Jennifer | Marcus | Lisa | Devon | Rachel |
|-----------|-------|---------|---------|----------|--------|------|-------|--------|
| Own work items | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | - | - |
| Team work items | - | - | ✓ | - | - | - | - | - |
| Org work summary | - | - | - | ✓ | - | - | - | - |
| Team capacity | - | - | ✓ | ✓ | - | - | - | - |
| Integration inventory | - | - | - | - | - | - | ✓ | ✓ |
| Integration health | - | - | - | - | - | - | ✓ | ✓ |
| Audit logs | - | - | - | - | - | - | ✓ | ✓ |
| Compliance status | - | - | - | ✓ | ✓ | - | ✓ | ✓ |

### Action Permissions

| Action | Sarah | Alex R. | Alex T. | Jennifer | Marcus | Lisa | Devon | Rachel |
|--------|-------|---------|---------|----------|--------|------|-------|--------|
| View own queue | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | - | - |
| View team queue | - | - | ✓ | - | - | - | - | - |
| Reassign work | - | - | ✓ | - | ✓ | - | - | - |
| Set priorities | - | - | ✓ | ✓ | ✓ | - | - | - |
| Add integrations | - | - | - | - | - | - | ✓ | - |
| Configure integrations | - | - | - | - | - | - | ✓ | - |
| Deploy integrations | - | - | - | - | - | - | ✓ | - |
| Approve integrations | - | - | - | - | - | - | - | ✓ |
| View audit logs | - | - | - | - | - | - | ✓ | ✓ |
| Generate reports | - | - | - | ✓ | ✓ | - | - | ✓ |

---

## Key Insights

1. **No Single Super-User:** Each persona has distinct responsibilities with minimal overlap
2. **Admin Separation:** Devon (operations) and Rachel (governance) have complementary roles
3. **Clear Hierarchies:** IC → Manager → Executive → Org (no cross-cutting authority)
4. **Privacy by Design:** Only managers see team details; only Rachel sees full audit trail
5. **Cascade Clarity:** Jennifer sets org priorities; everyone else receives or acts on them

---

## Notes

- All ICs can delegate work to peers with their permission
- All managers can override team priorities with explanation
- Rachel's approval is required for sensitive integrations (Workday, LMS, custom)
- Devon cannot approve integrations; Rachel cannot configure them
- Audit logs provide full compliance trail for regulatory audits
