# Prism Admin Dashboard Design

## Overview
Admin interface for managing integrations, health monitoring, compliance, and deployment. Two primary actors: **Integration Administrator** (Devon) and **Security/Compliance Lead** (Rachel).

---

## 1. DASHBOARD LAYOUT (Main Hub)

```
┌──────────────────────────────────────────────────────────────────────┐
│ PRISM ADMIN  [Logo]                                  User: Devon   ☉  │
├──────────────────────────────────────────────────────────────────────┤
│                                                                        │
│  LEFT SIDEBAR                    MAIN CONTENT AREA                    │
│  ┌──────────────┐                ┌──────────────────────────────────┐│
│  │ MENU         │                │ DASHBOARD                        ││
│  ├──────────────┤                ├──────────────────────────────────┤│
│  │ Dashboard    │                │                                  ││
│  │ Integrations │                │  QUICK STATUS (Top Cards)        ││
│  │ Health       │                │  ┌───────────┬────────┬────────┐││
│  │ Credentials  │                │  │ 8 Active  │ 2 Down │ 1 Warn ││
│  │ Audit Logs   │                │  │ Apps      │        │ Issues ││
│  │ Settings     │                │  └───────────┴────────┴────────┘││
│  │              │                │                                  ││
│  │  ROLE:       │                │  ACTIVE INTEGRATIONS             ││
│  │  Integration │                │  ┌────────────────────────────┐ ││
│  │  Admin       │                │  │ Name  │ Status  │ Users    │ ││
│  │              │                │  ├────────────────────────────┤ ││
│  │  [Sign Out]  │                │  │ Outlook   │ ✓ OK  │ 523    │ ││
│  │              │                │  │ Slack     │ ✓ OK  │ 456    │ ││
│  │              │                │  │ Workday   │ ✓ OK  │ 500    │ ││
│  │              │                │  │ Jira      │ ⚠ Deg │ 245    │ ││
│  │              │                │  │ LMS       │ ✓ OK  │ 500    │ ││
│  │              │                │  └────────────────────────────┘ ││
│  │              │                │                                  ││
│  │              │                │  PENDING APPROVALS: 2            ││
│  │              │                │  [Rally Integration] [LMS v2]    ││
│  │              │                │                                  ││
│  └──────────────┘                └──────────────────────────────────┘│
│                                                                        │
└──────────────────────────────────────────────────────────────────────┘
```

---

## 2. MAIN DASHBOARD VIEW

### 2.1 Top Quick Stats

```
┌─────────────────────────────────────────────────────────────────┐
│ DASHBOARD - INTEGRATIONS AT A GLANCE                             │
├─────────────────────────────────────────────────────────────────┤
│                                                                   │
│  ┌─────────────┐  ┌─────────────┐  ┌─────────────┐              │
│  │ ACTIVE      │  │ DEGRADED    │  │ DISABLED    │              │
│  │ 8           │  │ 2           │  │ 1           │              │
│  │ (✓ Healthy) │  │ (⚠ Issues)  │  │ (○ Off)     │              │
│  └─────────────┘  └─────────────┘  └─────────────┘              │
│                                                                   │
│  Uptime Last 30 Days: 99.7% │ Avg Sync Latency: 2.3s │         │
│                                                                   │
└─────────────────────────────────────────────────────────────────┘
```

### 2.2 Integration Inventory Card View

```
┌─────────────────────────────────────────────────────────────────┐
│ ACTIVE INTEGRATIONS                                              │
│ [All] [Healthy] [Degraded] [Disabled] | [Sort: A-Z] [+ Add New]│
├─────────────────────────────────────────────────────────────────┤
│                                                                   │
│  ┌──────────────────┐  ┌──────────────────┐  ┌──────────────────┐
│  │ OUTLOOK          │  │ SLACK            │  │ WORKDAY          │
│  ├──────────────────┤  ├──────────────────┤  ├──────────────────┤
│  │ Status: ✓ OK     │  │ Status: ✓ OK     │  │ Status: ✓ OK     │
│  │ Users: 523       │  │ Users: 456       │  │ Users: 500       │
│  │ Uptime: 100%     │  │ Uptime: 100%     │  │ Uptime: 100%     │
│  │ Last Sync: 5min  │  │ Last Sync: 3min  │  │ Last Sync: 1h    │
│  │                  │  │                  │  │                  │
│  │ [Details] [Logs] │  │ [Details] [Logs] │  │ [Details] [Logs] │
│  └──────────────────┘  └──────────────────┘  └──────────────────┘
│
│  ┌──────────────────┐  ┌──────────────────┐  ┌──────────────────┐
│  │ JIRA             │  │ LMS (CANVAS)     │  │ CUSTOM ROADMAP   │
│  ├──────────────────┤  ├──────────────────┤  ├──────────────────┤
│  │ Status: ⚠ Degrad │  │ Status: ✓ OK     │  │ Status: ✗ Error  │
│  │ Users: 245       │  │ Users: 500       │  │ Users: 12        │
│  │ Uptime: 98.5%    │  │ Uptime: 99.9%    │  │ Uptime: 85.2%    │
│  │ Last Sync: 15min │  │ Last Sync: 6min  │  │ Last Sync: 2h    │
│  │ Issue: Quota >80%│  │                  │  │ Issue: Auth fail  │
│  │ [Details] [Logs] │  │ [Details] [Logs] │  │ [Details] [Logs] │
│  └──────────────────┘  └──────────────────┘  └──────────────────┘
│
└─────────────────────────────────────────────────────────────────┘
```

### 2.3 Pending Approvals (Security Lead View)

```
┌─────────────────────────────────────────────────────────────────┐
│ PENDING APPROVALS                                                │
│ Requires review from: Security/Compliance Lead                   │
├─────────────────────────────────────────────────────────────────┤
│                                                                   │
│  ┌──────────────────────────────────────────────────────────┐   │
│  │ Rally Integration (Project Management)                   │   │
│  │ Status: Awaiting Approval                                │   │
│  │ Requested By: Devon (Integration Admin) · 2 days ago     │   │
│  │ Compliance Checklist: 4/5 items approved                 │   │
│  │ Missing: SOC2 Certification                              │   │
│  │                                                           │   │
│  │ [View Details] [Approve] [Request Changes] [Deny]        │   │
│  └──────────────────────────────────────────────────────────┘   │
│                                                                   │
│  ┌──────────────────────────────────────────────────────────┐   │
│  │ LMS v2 (Compliance - Canvas Update)                      │   │
│  │ Status: Awaiting Approval                                │   │
│  │ Requested By: Devon · 4 hours ago                        │   │
│  │ Compliance Checklist: 5/5 items approved ✓               │   │
│  │ Ready: Can approve                                        │   │
│  │                                                           │   │
│  │ [View Details] [Approve] [Request Changes] [Deny]        │   │
│  └──────────────────────────────────────────────────────────┘   │
│                                                                   │
└─────────────────────────────────────────────────────────────────┘
```

---

## 3. INTEGRATION DETAIL VIEW

When clicking on an integration card:

```
┌──────────────────────────────────────────────────────────────────┐
│ JIRA INTEGRATION DETAIL                                           │
├──────────────────────────────────────────────────────────────────┤
│                                                                    │
│ OVERVIEW                          [Edit Config] [Test] [Deploy]   │
│ ┌────────────────────────────────────────────────────────────┐   │
│ │ Status: ⚠ DEGRADED                                         │   │
│ │ Instance: company.atlassian.net                            │   │
│ │ Auth Method: OAuth2                                        │   │
│ │ Last Credential Rotation: 30 days ago                      │   │
│ │ Users Affected: 245                                        │   │
│ │ Deployment Status: Fully Deployed (100%)                  │   │
│ │ Sync Frequency: 30 minutes                                 │   │
│ │ Last Sync: 12 minutes ago                                  │   │
│ │ Next Sync: in 18 minutes                                   │   │
│ └────────────────────────────────────────────────────────────┘   │
│                                                                    │
│ CURRENT ISSUES                                                    │
│ ┌────────────────────────────────────────────────────────────┐   │
│ │ ⚠ API Quota Approaching: 87% of daily limit               │   │
│ │   Recommendation: Increase sync interval or request        │   │
│ │   higher quota from Jira. [Request Quota Increase]         │   │
│ │                                                             │   │
│ │ ⓘ 3 failed syncs in last 24h (auth token refresh issue)   │   │
│ │   Next sync will retry automatically.                      │   │
│ └────────────────────────────────────────────────────────────┘   │
│                                                                    │
│ METRICS (Last 24 Hours)                                           │
│ ┌────────────────────────────────────────────────────────────┐   │
│ │ Items Synced: 198/200  │  Error Rate: 1%  │  Latency: 3.2s │   │
│ │ Total Syncs: 48        │  Success Rate: 99%                    │   │
│ │                                                             │   │
│ │ [24h Graph]                                                 │   │
│ │ ▁▂▂▃▃▂▁▂▃▄▄▃▂▁▂▃▄▅▄▃▂▁▂▂▁ (Success %/hour)             │   │
│ └────────────────────────────────────────────────────────────┘   │
│                                                                    │
│ CAPABILITIES ENABLED                                              │
│ ┌────────────────────────────────────────────────────────────┐   │
│ │ ✓ Deadline Detection    │  Extract deadlines from Jira     │   │
│ │ ✓ Dependency Tracking   │  Track blockers & relationships  │   │
│ │ ✗ Capacity Planning     │  Disabled - not used             │   │
│ │                         │  [Enable]                        │   │
│ └────────────────────────────────────────────────────────────┘   │
│                                                                    │
│ CONFIGURATION                                                     │
│ ┌────────────────────────────────────────────────────────────┐   │
│ │ Data Scope:                                                 │   │
│ │   Filter: key in (PRISM-*) OR assignee = currentUser()    │   │
│ │   Fields: project, epic, deadline, assignee, priority      │   │
│ │   Excluded: spike-*, research-*                            │   │
│ │                                                             │   │
│ │ Sync Schedule:                                              │   │
│ │   Frequency: Every 30 minutes                              │   │
│ │   Last Sync: 2026-09-28 14:32 UTC                          │   │
│ │   Next Sync: 2026-09-28 15:02 UTC                          │   │
│ │                                                             │   │
│ │ [Edit Configuration]                                        │   │
│ └────────────────────────────────────────────────────────────┘   │
│                                                                    │
│ RECENT SYNC LOGS (Last 10 Syncs)                                  │
│ ┌────────────────────────────────────────────────────────────┐   │
│ │ Time            │ Status        │ Items  │ Errors │ Duration│   │
│ ├────────────────────────────────────────────────────────────┤   │
│ │ 14:32 UTC       │ ✓ Success     │ 200    │ 0      │ 2.1s   │   │
│ │ 14:02 UTC       │ ✓ Success     │ 198    │ 2      │ 2.3s   │   │
│ │ 13:32 UTC       │ ⚠ Partial     │ 198    │ 2      │ 3.1s   │   │
│ │ 13:02 UTC       │ ✓ Success     │ 199    │ 1      │ 2.5s   │   │
│ │ [View Full Logs] (548 syncs available)                      │   │
│ └────────────────────────────────────────────────────────────┘   │
│                                                                    │
│ ACTIONS                                                           │
│ [Rotate Credentials] [Test Connection] [Manual Sync] [Disable]   │
│                                                                    │
└──────────────────────────────────────────────────────────────────┘
```

---

## 4. INTEGRATION CONFIGURATION WIZARD

Triggered by "[+ Add New]" or "[Edit Config]":

```
┌──────────────────────────────────────────────────────────────────┐
│ CONFIGURE JIRA INTEGRATION                          Step 2 of 4    │
├──────────────────────────────────────────────────────────────────┤
│                                                                    │
│ STEP 1: Connect Account      ✓                                    │
│ STEP 2: Select Capabilities  ◆ (Current)                         │
│ STEP 3: Configure Sync       ○                                    │
│ STEP 4: Review & Deploy      ○                                    │
│                                                                    │
├──────────────────────────────────────────────────────────────────┤
│                                                                    │
│ WHICH CAPABILITIES DO YOU WANT TO ENABLE?                        │
│                                                                    │
│ ☑ Deadline Detection                                             │
│    Extract deadlines from Jira issues and epics                 │
│    Required fields: dueDate, target dates                        │
│                                                                    │
│ ☑ Dependency Tracking                                            │
│    Track blockers and issue relationships                        │
│    Required fields: issue links, blocking status                 │
│                                                                    │
│ ☐ Team Capacity Planning                                         │
│    Estimate team sprint capacity                                 │
│    Note: Requires sprint estimation (Story Points)              │
│    [?] Why disabled?                                             │
│                                                                    │
│ ☐ Custom Field Mapping (Advanced)                                │
│    Map org-specific custom fields                                │
│    [Advanced Settings]                                           │
│                                                                    │
├──────────────────────────────────────────────────────────────────┤
│                                                                    │
│ [← Back: Connect Account] [Next: Configure Sync →] [Cancel]     │
│                                                                    │
└──────────────────────────────────────────────────────────────────┘
```

### Step 3: Configure Sync

```
┌──────────────────────────────────────────────────────────────────┐
│ CONFIGURE JIRA INTEGRATION                          Step 3 of 4    │
├──────────────────────────────────────────────────────────────────┤
│                                                                    │
│ STEP 1: Connect Account      ✓                                    │
│ STEP 2: Select Capabilities  ✓                                    │
│ STEP 3: Configure Sync       ◆ (Current)                         │
│ STEP 4: Review & Deploy      ○                                    │
│                                                                    │
├──────────────────────────────────────────────────────────────────┤
│                                                                    │
│ DATA SCOPE                                                        │
│                                                                    │
│ Which items should Prism sync?                                   │
│ ┌──────────────────────────────────────────────────────────┐    │
│ │ JQL Filter:                                              │    │
│ │ key in (PRISM-*) OR assignee = currentUser()             │    │
│ │                                                           │    │
│ │ This will sync approximately 200 items                   │    │
│ │ [Test Filter] [JQL Syntax Help]                          │    │
│ └──────────────────────────────────────────────────────────┘    │
│                                                                    │
│ Fields to Extract:                                                │
│ ☑ project     ☑ epic        ☑ deadline    ☑ assignee             │
│ ☑ priority    ☐ description ☐ labels      ☐ components           │
│ [Select All] [Clear All] [Default Set]                          │
│                                                                    │
│ SYNC SCHEDULE                                                     │
│ ┌──────────────────────────────────────────────────────────┐    │
│ │ Frequency:                                               │    │
│ │ ◎ Every 15 minutes   ◉ Every 30 minutes   ○ Every hour   │    │
│ │ ○ Every 6 hours      ○ Once per day                      │    │
│ │                                                           │    │
│ │ ⓘ More frequent sync = faster updates, higher API usage  │    │
│ └──────────────────────────────────────────────────────────┘    │
│                                                                    │
│ EXCLUSIONS (Optional)                                             │
│ ┌──────────────────────────────────────────────────────────┐    │
│ │ Exclude these keys from sync:                            │    │
│ │ spike-*, research-*                                      │    │
│ │ [Add Exclusion Pattern]                                  │    │
│ └──────────────────────────────────────────────────────────┘    │
│                                                                    │
├──────────────────────────────────────────────────────────────────┤
│                                                                    │
│ [← Back] [Next: Review & Deploy →] [Cancel]                     │
│                                                                    │
└──────────────────────────────────────────────────────────────────┘
```

### Step 4: Review & Deploy

```
┌──────────────────────────────────────────────────────────────────┐
│ CONFIGURE JIRA INTEGRATION                          Step 4 of 4    │
├──────────────────────────────────────────────────────────────────┤
│                                                                    │
│ STEP 1: Connect Account      ✓                                    │
│ STEP 2: Select Capabilities  ✓                                    │
│ STEP 3: Configure Sync       ✓                                    │
│ STEP 4: Review & Deploy      ◆ (Current)                         │
│                                                                    │
├──────────────────────────────────────────────────────────────────┤
│                                                                    │
│ PRE-DEPLOYMENT VALIDATION                                         │
│ ┌──────────────────────────────────────────────────────────┐    │
│ │ ✓ Auth credentials valid                                 │    │
│ │ ✓ API connectivity verified                              │    │
│ │ ✓ API quota sufficient (12% of daily limit)              │    │
│ │ ✓ Configuration syntax valid                             │    │
│ │ ✓ Data filter returns 200 items (expected range: 50-500) │    │
│ │ ✓ Signal extraction working (deadlines detected: 145)    │    │
│ │ ✓ All required capabilities supported                    │    │
│ │ ✓ Compliance gates satisfied (SOC2 ✓, GDPR ✓)            │    │
│ │                                                           │    │
│ │ Status: Ready to Deploy ✓                                │    │
│ └──────────────────────────────────────────────────────────┘    │
│                                                                    │
│ DEPLOYMENT STRATEGY                                               │
│ ┌──────────────────────────────────────────────────────────┐    │
│ │ Roll out to:                                              │    │
│ │ ◉ Full deployment (100% of users · 245 users)            │    │
│ │ ○ Canary first (1% · 2-3 users)                          │    │
│ │   Then expand → 25% → 100%                               │    │
│ │                                                           │    │
│ │ ⓘ Canary recommended for first-time integrations         │    │
│ └──────────────────────────────────────────────────────────┘    │
│                                                                    │
│ REQUIRES APPROVAL?                                                │
│ ┌──────────────────────────────────────────────────────────┐    │
│ │ This integration meets all compliance requirements.       │    │
│ │ Approval Status: ✓ Auto-approved (no sensitive data)     │    │
│ │                                                           │    │
│ │ If sensitive, would require: Security/Compliance Lead    │    │
│ └──────────────────────────────────────────────────────────┘    │
│                                                                    │
│ CONFIGURATION SUMMARY                                             │
│ ├──────────────────────────────────────────────────────────┤    │
│ │ Integration: Jira (company.atlassian.net)                │    │
│ │ Auth: OAuth2 (expires in 30 days)                        │    │
│ │ Capabilities: Deadline Detection, Dependency Tracking    │    │
│ │ Sync: Every 30 minutes (~200 items)                      │    │
│ │ Users: 245 (all Jira-using ICs)                          │    │
│ │ Compliance: Auto-approved                                │    │
│ └──────────────────────────────────────────────────────────┘    │
│                                                                    │
├──────────────────────────────────────────────────────────────────┤
│                                                                    │
│ [← Back] [Deploy] [Cancel] [Save as Draft]                      │
│                                                                    │
└──────────────────────────────────────────────────────────────────┘
```

---

## 5. HEALTH MONITORING VIEW

Accessed via "Health" in sidebar:

```
┌──────────────────────────────────────────────────────────────────┐
│ INTEGRATION HEALTH MONITOR                                        │
│ [Real-time] [Last 24h] [Last 7d] [Last 30d]                      │
├──────────────────────────────────────────────────────────────────┤
│                                                                    │
│ UPTIME TREND (Last 7 Days)                                        │
│ ┌──────────────────────────────────────────────────────────┐    │
│ │ 100% ┤          ▁▂▂▃▃▂▁                                   │    │
│ │  99% ┤     ▂▃▃▄▄▃▂ ▂▃▃▄▄▃▂ (Jira)                        │    │
│ │  98% ┤                      ▂▃▃▄▄▃▂▁                      │    │
│ │  97% ┤                                                    │    │
│ │       └──────────────────────────────────────────────────│    │
│ │       Mon   Tue   Wed   Thu   Fri   Sat   Sun           │    │
│ │                                                           │    │
│ │ Overall: 99.7% uptime last 7 days                        │    │
│ └──────────────────────────────────────────────────────────┘    │
│                                                                    │
│ SYNC PERFORMANCE (Last 24 Hours)                                  │
│ ┌──────────────────────────────────────────────────────────┐    │
│ │ Avg Latency: 2.3 seconds  │  P95: 3.8s  │  P99: 4.2s    │    │
│ │ Success Rate: 99.2%       │  Errors: 23/3,048 syncs      │    │
│ │                                                           │    │
│ │ [Latency Chart - Hours 0-24]                             │    │
│ │ 5s  ┤              ▄▅▄                    ▃▄▃            │    │
│ │ 4s  ┤           ▂▃▄▅▆▅▄▃▂                ▂▃▄▅▄▂          │    │
│ │ 3s  ┤    ▁▂▃▄▅▆▇█▇▆▅▄▃▂▁▂▃▄▅▆▇█▇▆▅▄▃▂▁▂▃▄▅▆▇█▇▆▅    │    │
│ │ 2s  ┤ ▁▂▃▄▅▆▇█▇▆▅▄▃▂▁                      ▂▃▄▅       │    │
│ │ 1s  ┤▂▃▄▅▆▇█▇▆▅▄▃▂▁▂▃▄                        ▂▃      │    │
│ │     └──────────────────────────────────────────────────│    │
│ └──────────────────────────────────────────────────────────┘    │
│                                                                    │
│ INTEGRATION COMPARISON TABLE                                      │
│ ┌──────────────────────────────────────────────────────────┐    │
│ │ Integration │ Uptime │ P95 Lat │ Success │ Last Issue    │    │
│ ├──────────────────────────────────────────────────────────┤    │
│ │ Outlook     │ 100%   │ 1.2s    │ 100%    │ None          │    │
│ │ Slack       │ 100%   │ 0.8s    │ 100%    │ 3 days ago    │    │
│ │ Workday     │ 99.9%  │ 2.1s    │ 99.9%   │ 1 day ago     │    │
│ │ Jira        │ 98.5%  │ 3.8s    │ 99.2%   │ 2 hours ago   │    │
│ │ LMS (Canvas)│ 99.9%  │ 1.5s    │ 99.9%   │ 5 days ago    │    │
│ │ Custom Tool │ 85.2%  │ 5.3s    │ 87.4%   │ 2 hours ago   │    │
│ └──────────────────────────────────────────────────────────┘    │
│                                                                    │
│ ALERTS & ISSUES                                                   │
│ ┌──────────────────────────────────────────────────────────┐    │
│ │ ⚠ HIGH PRIORITY                                           │    │
│ │ • Jira: API Quota at 87% (alert if >90%)                 │    │
│ │   [Request Quota Increase] [Reduce Sync Frequency]       │    │
│ │                                                           │    │
│ │ • Custom Tool: 14.8% error rate in last hour              │    │
│ │   Last 5 errors: [Auth Failed] [Timeout] [Auth Failed]   │    │
│ │   [View Logs] [Restart Sync] [Disable Integration]       │    │
│ │                                                           │    │
│ │ ⓘ INFORMATIONAL                                           │    │
│ │ • Workday: Next credential rotation in 5 days             │    │
│ └──────────────────────────────────────────────────────────┘    │
│                                                                    │
└──────────────────────────────────────────────────────────────────┘
```

---

## 6. CREDENTIALS MANAGEMENT VIEW

Accessed via "Credentials" in sidebar:

```
┌──────────────────────────────────────────────────────────────────┐
│ CREDENTIAL MANAGEMENT                                             │
├──────────────────────────────────────────────────────────────────┤
│                                                                    │
│ All credentials are encrypted at rest and rotated automatically   │
│ View audit log: [All Credential Operations]                      │
│                                                                    │
├──────────────────────────────────────────────────────────────────┤
│                                                                    │
│ INTEGRATION CREDENTIALS                                           │
│ ┌──────────────────────────────────────────────────────────┐    │
│ │ Integration │ Method   │ Status    │ Expires   │ Actions  │    │
│ ├──────────────────────────────────────────────────────────┤    │
│ │ Outlook     │ OAuth2   │ ✓ Valid   │ 30 days   │ [Rotate] │    │
│ │             │          │           │           │ [Revoke] │    │
│ ├──────────────────────────────────────────────────────────┤    │
│ │ Slack       │ OAuth2   │ ✓ Valid   │ 60 days   │ [Rotate] │    │
│ │             │          │           │           │ [Revoke] │    │
│ ├──────────────────────────────────────────────────────────┤    │
│ │ Workday     │ OAuth2   │ ✓ Valid   │ 15 days   │ [Rotate] │    │
│ │             │          │           │ (soon!)   │ [Revoke] │    │
│ │             │          │           │           │ [Urgent]●│    │
│ ├──────────────────────────────────────────────────────────┤    │
│ │ Jira        │ OAuth2   │ ✓ Valid   │ 45 days   │ [Rotate] │    │
│ │             │          │           │           │ [Revoke] │    │
│ ├──────────────────────────────────────────────────────────┤    │
│ │ LMS (Canvas)│ API Key  │ ✓ Valid   │ 90 days   │ [Rotate] │    │
│ │             │          │           │           │ [Revoke] │    │
│ ├──────────────────────────────────────────────────────────┤    │
│ │ Custom Tool │ API Key  │ ✗ Expired │ Expired!  │ [Rotate] │    │
│ │             │          │ (2 days)  │           │ [Revoke] │    │
│ └──────────────────────────────────────────────────────────┘    │
│                                                                    │
│ ROTATION POLICY                                                   │
│ ┌──────────────────────────────────────────────────────────┐    │
│ │ Automatic Rotation: ◉ Enabled  ○ Disabled                │    │
│ │ Rotation Interval: 30 days                               │    │
│ │ Notification Before Expiry: 7 days                       │    │
│ │                                                           │    │
│ │ [Update Policy]                                          │    │
│ └──────────────────────────────────────────────────────────┘    │
│                                                                    │
│ ROTATION HISTORY (Last 10 Rotations)                             │
│ ┌──────────────────────────────────────────────────────────┐    │
│ │ Date       │ Integration │ Method  │ Duration │ Status    │    │
│ ├──────────────────────────────────────────────────────────┤    │
│ │ Sep 20     │ Outlook     │ Auto    │ 2.3s     │ ✓ Success │    │
│ │ Sep 15     │ Jira        │ Auto    │ 1.8s     │ ✓ Success │    │
│ │ Sep 10     │ Slack       │ Manual  │ 5.2s     │ ✓ Success │    │
│ │ Sep 05     │ Workday     │ Auto    │ 2.1s     │ ✓ Success │    │
│ │ [View Full History]                                      │    │
│ └──────────────────────────────────────────────────────────┘    │
│                                                                    │
└──────────────────────────────────────────────────────────────────┘
```

---

## 7. AUDIT LOGS VIEW

Accessed via "Audit Logs" in sidebar:

```
┌──────────────────────────────────────────────────────────────────┐
│ AUDIT LOGS                                                        │
│ [All] [Configuration Changes] [Credential Ops] [Approvals] [Syncs]
│ Filter: [Date Range] [User] [Integration] [Action]               │
├──────────────────────────────────────────────────────────────────┤
│                                                                    │
│ RECENT ACTIVITY (Last 100 Events)                                │
│ ┌──────────────────────────────────────────────────────────┐    │
│ │ Date/Time          │ User   │ Action          │ Details   │    │
│ ├──────────────────────────────────────────────────────────┤    │
│ │ Sep 28 14:30 UTC   │ Devon  │ Deployed Jira   │ Rollout:  │    │
│ │                    │        │ to 100%         │ Canary→25%│    │
│ │                    │        │                 │ Approved  │    │
│ ├──────────────────────────────────────────────────────────┤    │
│ │ Sep 28 14:15 UTC   │ Rachel │ Approved Jira   │ Compliance│    │
│ │                    │        │ Integration     │ checklist │    │
│ │                    │        │                 │ passed    │    │
│ ├──────────────────────────────────────────────────────────┤    │
│ │ Sep 28 14:00 UTC   │ Devon  │ Tested Jira     │ Test: ✓   │    │
│ │                    │        │ sync            │ 200 items │    │
│ ├──────────────────────────────────────────────────────────┤    │
│ │ Sep 28 13:45 UTC   │ Devon  │ Configured Jira │ Changed   │    │
│ │                    │        │ integration     │ sync freq │    │
│ │                    │        │                 │ to 30m    │    │
│ ├──────────────────────────────────────────────────────────┤    │
│ │ Sep 25 10:22 UTC   │ Devon  │ Rotated Outlook │ Rotation: │    │
│ │                    │        │ credential      │ ✓ Success │    │
│ ├──────────────────────────────────────────────────────────┤    │
│ │ Sep 22 09:15 UTC   │ Devon  │ Created Jira    │ OAuth2    │    │
│ │                    │        │ integration     │ auth      │    │
│ │                    │        │                 │ connected │    │
│ ├──────────────────────────────────────────────────────────┤    │
│ │ [Load More Events] (25,847 total events)                 │    │
│ └──────────────────────────────────────────────────────────┘    │
│                                                                    │
│ EXPORT AUDIT REPORT                                               │
│ ┌──────────────────────────────────────────────────────────┐    │
│ │ Date Range: [From Date] [To Date]                        │    │
│ │ Format: ◉ PDF  ○ CSV  ○ JSON                             │    │
│ │ [Generate Report]                                        │    │
│ │                                                           │    │
│ │ Recent Reports:                                           │    │
│ │ • 2026-09-28_audit_report.pdf (2.3 MB)   [Download]     │    │
│ │ • 2026-09-21_audit_report.pdf (2.1 MB)   [Download]     │    │
│ └──────────────────────────────────────────────────────────┘    │
│                                                                    │
└──────────────────────────────────────────────────────────────────┘
```

---

## 8. INTEGRATION APPROVAL WORKFLOW (Security Lead)

Modal when clicking "[View Details]" on pending approval:

```
┌──────────────────────────────────────────────────────────────────┐
│ APPROVAL: Rally Integration                          [Requested]  │
├──────────────────────────────────────────────────────────────────┤
│                                                                    │
│ REQUESTED BY: Devon (Integration Administrator)                  │
│ REQUESTED: 2 days ago (Sep 26 10:30 UTC)                         │
│ REASON: "Enable Rally for VP and Director project visibility"   │
│                                                                    │
├──────────────────────────────────────────────────────────────────┤
│                                                                    │
│ INTEGRATION DETAILS                                               │
│ • Type: Project Management (Jira alternative)                    │
│ • Instance: company.rallydev.com                                 │
│ • Users Affected: 245 (PMs, VPs, Directors)                      │
│ • Auth: OAuth2                                                    │
│ • Capabilities: Deadline Detection, Dependency Tracking          │
│ • Sync Frequency: 30 minutes                                      │
│                                                                    │
├──────────────────────────────────────────────────────────────────┤
│                                                                    │
│ COMPLIANCE CHECKLIST                                              │
│ ┌──────────────────────────────────────────────────────────┐    │
│ │ ✓ Data Classification Review                             │    │
│ │   Rally shares project details (medium sensitivity)      │    │
│ │                                                           │    │
│ │ ✓ SOC2 Certification                                     │    │
│ │   Rally: SOC 2 Type II certified                         │    │
│ │   [View Certificate] (expires 2027-03-15)                │    │
│ │                                                           │    │
│ │ ✓ GDPR Compliance                                        │    │
│ │   Rally: GDPR compliant, EU data centers available       │    │
│ │                                                           │    │
│ │ ✗ Data Residency Requirement                             │    │
│ │   Required: Data must stay in US-East-1                  │    │
│ │   Rally: Offers US region ✓                              │    │
│ │   Configuration: Will use us-east-1 endpoint             │    │
│ │                                                           │    │
│ │ ✓ Audit Logging Capability                               │    │
│ │   Rally: Full audit trail available via API              │    │
│ │                                                           │    │
│ │ Summary: 4/5 items complete                              │    │
│ │          1 item pending clarification                    │    │
│ └──────────────────────────────────────────────────────────┘    │
│                                                                    │
│ INFORMATION FOR REVIEWER                                          │
│ ┌──────────────────────────────────────────────────────────┐    │
│ │ Why this integration:                                     │    │
│ │ We need to surface high-level project/portfolio          │    │
│ │ priorities from Rally alongside Jira epic deadlines.     │    │
│ │ This enables VPs to see both engineering and product     │    │
│ │ commitments in Prism.                                    │    │
│ │                                                           │    │
│ │ Comparison with Jira:                                    │    │
│ │ • Rally = Portfolio/roadmap tool (Director/VP level)     │    │
│ │ • Jira = Sprint/epic tool (IC/Manager level)             │    │
│ │ • Both needed for complete priority visibility           │    │
│ │                                                           │    │
│ │ Security Concerns:                                        │    │
│ │ None identified - Rally SOC2, GDPR compliant, US data   │    │
│ │                                                           │    │
│ │ [Request More Info from Devon] [View Test Results]       │    │
│ └──────────────────────────────────────────────────────────┘    │
│                                                                    │
├──────────────────────────────────────────────────────────────────┤
│                                                                    │
│ APPROVAL DECISION                                                 │
│ ┌──────────────────────────────────────────────────────────┐    │
│ │ Your Review Comment (optional):                           │    │
│ │ ┌──────────────────────────────────────────────────────┐ │    │
│ │ │                                                      │ │    │
│ │ │ Reviewed all requirements. Confirmed data will     │ │    │
│ │ │ remain in US-East-1. Looks good to approve.        │ │    │
│ │ │ We can monitor performance for first 7 days.       │ │    │
│ │ │                                                      │ │    │
│ │ └──────────────────────────────────────────────────────┘ │    │
│ │                                                           │    │
│ │ [Approve] [Request Changes] [Deny]                      │    │
│ └──────────────────────────────────────────────────────────┘    │
│                                                                    │
└──────────────────────────────────────────────────────────────────┘
```

---

## 9. INTEGRATION MARKETPLACE/DISCOVERY

Accessed via "[+ Add New]" without an existing integration:

```
┌──────────────────────────────────────────────────────────────────┐
│ INTEGRATION MARKETPLACE                                           │
│ [All] [Recommended] [Stable] [Beta] [Custom]                     │
│ Search: [Find Integration...] [Filter by Type]                   │
├──────────────────────────────────────────────────────────────────┤
│                                                                    │
│ RECOMMENDED FOR YOUR ORG                                          │
│ ┌──────────────────────────────────────────────────────────┐    │
│ │ Rally (Project Management)                               │    │
│ │ Status: ✓ Stable  │  Version: 2.1  │  Users: 1,200 orgs │    │
│ │                                                           │    │
│ │ Agile portfolio management aligned with Jira for        │    │
│ │ director/VP-level strategic prioritization              │    │
│ │                                                           │    │
│ │ Capabilities:                                             │    │
│ │   ✓ Deadline Detection  ✓ Dependency Tracking  ○ Capacity│    │
│ │                                                           │    │
│ │ Requirements:                                             │    │
│ │   • Rally instance (company.rallydev.com)               │    │
│ │   • OAuth2 auth required                                │    │
│ │   • Data residency: US/EU options available             │    │
│ │                                                           │    │
│ │ Compliance:                                               │    │
│ │   ✓ SOC2 Type II  ✓ GDPR  ✓ Audit Logging Capable       │    │
│ │                                                           │    │
│ │ Satisfaction: 4.8/5 ⭐ (847 reviews)                     │    │
│ │                                                           │    │
│ │ [Setup Integration] [View Docs] [Try Sandbox]            │    │
│ └──────────────────────────────────────────────────────────┘    │
│                                                                    │
│ ┌──────────────────────────────────────────────────────────┐    │
│ │ Lattice (Feedback Cycles)                                │    │
│ │ Status: ⚠ Beta  │  Version: 0.9  │  Users: 234 orgs      │    │
│ │                                                           │    │
│ │ OKR tracking and 360 feedback management for strategic   │    │
│ │ alignment and people development                         │    │
│ │                                                           │    │
│ │ Capabilities:                                             │    │
│ │   ✓ Deadline Detection  ✗ Dependency Tracking  ○ Capacity│    │
│ │                                                           │    │
│ │ Status: Early Access (Limited availability)              │    │
│ │ Satisfaction: 4.3/5 ⭐ (45 reviews, Beta testers)        │    │
│ │                                                           │    │
│ │ [Request Access] [View Docs]                             │    │
│ └──────────────────────────────────────────────────────────┘    │
│                                                                    │
│ ALREADY ENABLED                                                   │
│ ┌──────────────────────────────────────────────────────────┐    │
│ │ ✓ Outlook  ✓ Slack  ✓ Workday  ✓ Jira  ✓ LMS (Canvas)   │    │
│ └──────────────────────────────────────────────────────────┘    │
│                                                                    │
│ ADVANCED                                                          │
│ ┌──────────────────────────────────────────────────────────┐    │
│ │ Custom Integration                                        │    │
│ │ Build your own integration using the Prism SDK          │    │
│ │                                                           │    │
│ │ [View SDK Documentation] [Create Custom Integration]     │    │
│ └──────────────────────────────────────────────────────────┘    │
│                                                                    │
└──────────────────────────────────────────────────────────────────┘
```

---

## 10. KEY WORKFLOWS

### Workflow 1: Add New Integration (Integration Admin)

```
Start
  ↓
[Dashboard] → [+ Add New]
  ↓
[Marketplace] → Select Integration (Jira)
  ↓
[Step 1: Connect] → Authorize via OAuth → Test Connection ✓
  ↓
[Step 2: Capabilities] → Select Deadline + Dependency → Continue
  ↓
[Step 3: Config Sync] → Set Filter, Frequency → Test Sample ✓
  ↓
[Step 4: Review] → Pre-deployment validation ✓ → Choose rollout (Canary)
  ↓
[Deploy Canary] → Deploy to 1% of users
  ↓
[Monitor] → Check health for 24h → Expand to 25% → 100%
  ↓
✓ Complete
```

### Workflow 2: Approve Sensitive Integration (Security Lead)

```
Start
  ↓
[Dashboard] → [Pending Approvals] → Click "Rally"
  ↓
[Approval Modal] → Review compliance checklist (4/5 ✓)
  ↓
[Request Info] from Integration Admin if needed
  ↓
[Approve] → Add comment → Submit
  ↓
Integration Admin sees approval → Proceeds with deployment
  ↓
✓ Complete
```

### Workflow 3: Monitor Integration Health (Integration Admin)

```
Daily
  ↓
[Dashboard] → Check status cards → Jira shows ⚠ Degraded
  ↓
[Click Jira Card] → See: API quota at 87%
  ↓
[View Logs] → Last 3 syncs show "quota limit approaching"
  ↓
Options:
  • [Request Quota Increase] → Contact Jira support
  • [Reduce Sync Frequency] → Change from 30m to 1h
  ↓
Choose reduce frequency
  ↓
[Configure] → Set to 1h → Deploy change
  ↓
[Monitor] → Check latency & error rate improve
  ↓
✓ Issue Resolved
```

---

## 11. SECURITY & PERMISSIONS

### Devon (Integration Administrator) Can See:
- ✓ All integrations (overview & detail)
- ✓ Health metrics, logs, errors
- ✓ Configuration settings
- ✓ Can test, deploy, monitor
- ✗ Cannot approve sensitive integrations
- ✗ Cannot access employee work data
- ✗ Cannot rotate credentials (only view)

### Rachel (Security/Compliance Lead) Can See:
- ✓ All integrations (overview only)
- ✓ Compliance requirements & approvals
- ✓ Audit logs (all operations)
- ✓ Can approve/deny integrations
- ✓ Can export compliance reports
- ✗ Cannot modify configurations
- ✗ Cannot access employee work data
- ✗ Cannot view credential secrets

---

## 12. MOBILE/RESPONSIVE CONSIDERATIONS

- Sidebar collapses on mobile → Hamburger menu
- Dashboard cards stack vertically
- Integration detail view: Tabs instead of full page layout
- Health monitoring: Simplified view (last 7 days only)
- Approvals: Full-screen modal with scroll
- Actions (buttons): Context-aware - hide less common options

---

## 13. KEY FEATURES OF THE DESIGN

| Feature | Benefit |
|---------|---------|
| **Card-based Inventory** | Quick glance at integration health |
| **Guided Wizards** | Non-technical admins can setup integrations |
| **Pre-deployment Validation** | Catch errors before they affect users |
| **Phased Rollout UI** | Safe deployments with canary option |
| **Real-time Health Monitoring** | Early warning of issues |
| **Approval Workflows** | Compliance approval integrated into process |
| **Audit Trail** | Complete visibility for compliance reviews |
| **Marketplace Discovery** | Know what integrations are available |
| **Credentials Management** | Secure storage + rotation in one place |
| **Role-based Views** | Integration Admin vs Security Lead see different things |

---

## 14. NEXT STEPS FOR IMPLEMENTATION

1. **Prototype in Figma** - High-fidelity mockups
2. **User Testing** - Test with DevOps/Platform teams
3. **API Design** - Align backend endpoints with UI flows
4. **Security Review** - Credential handling, permission model
5. **Accessibility Audit** - WCAG 2.1 AA compliance
6. **Performance Testing** - Real-time metrics rendering at scale
