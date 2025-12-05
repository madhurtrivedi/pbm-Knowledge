<h1>Utilization Module — Documentation</h1>

<h2>1. Module Purpose</h2>
<p>The Utilization module manages utilization reviews, prior authorization requests, concurrent and retrospective reviews, and utilization reporting. It provides access to utilization request status, clinical details, authorization decisions, and review history.</p>

<ul>
  <li><strong>Primary Unique Identifier:</strong> utilizationId</li>
  <li><strong>Navigation Path:</strong> /utilization</li>
  <li>Access: Left menu → Utilization</li>
</ul>

<h2>2. Utilization List</h2>
<p>The main list displays high-level utilization requests and episodes.</p>

<ul>
  <li>Utilization ID</li>
  <li>Member name</li>
  <li>Provider name</li>
  <li>Status (Approved, Pending, Denied, Under Review, Escalated)</li>
  <li>Type (Admission, Procedure, Medication, Imaging, Home Health)</li>
  <li>Service dates (Start - End)</li>
  <li>Submitted date</li>
  <li>Authorization number (if applicable)</li>
</ul>

<p>Selecting a record opens the Utilization Details view.</p>

<h2>3. Utilization Details Page — Layout and Components</h2>

<h3>Header Section</h3>
<ul>
  <li>Breadcrumb: Home / Utilization / UTL-0001</li>
  <li>Back Button: "Back to Utilization" → /utilization</li>
  <li>Title: "Utilization: UTL-0001"</li>
  <li>Subtitle: "Member Name - Admission: 2025-11-01 → 2025-11-05"</li>
  <li>Action Buttons (top-right): Edit, Print, Share, Create Authorization</li>
</ul>

<h3>Summary Card</h3>
<ul>
  <li>Status: color-coded badge</li>
  <li>Type & Priority</li>
  <li>Requested Dates</li>
  <li>Requested By / Clinician</li>
  <li>Decision / Authorization summary</li>
</ul>

<h3>Tab Navigation</h3>
<p>Tabs (default = Overview): Overview | Requests | Authorizations | Notes | History | Reports | Audit</p>

<h3>Content Area</h3>
<p>Tab-specific content renders below the tab bar.</p>

<h2>4. Tabs Overview</h2>
<p>Base Path: /utilization/[utilizationId]/[tabName]</p>

<h3>4.1 Overview Tab</h3>
<p>Comprehensive utilization summary in a description layout.</p>
<ul>
  <li>Utilization ID</li>
  <li>Member (name & ID) — member ID links to /members/[memberId]</li>
  <li>Provider (name & ID) — provider ID links to /providers/[providerId]</li>
  <li>Service Type</li>
  <li>Requested Start / End Dates</li>
  <li>Status (tag)</li>
  <li>Priority</li>
  <li>Clinical Summary / Diagnosis</li>
  <li>Requested Services</li>
  <li>Authorized Services / Authorization ID (if any)</li>
  <li>Decision Date / Decision By</li>
  <li>Attachments count</li>
  <li>Submitted Date / Processed Date</li>
</ul>
<p>Navigation Paths: /utilization/[utilizationId] or /utilization/[utilizationId]/overview</p>

<h3>4.2 Requests Tab</h3>
<p>Lists each utilization request attempt or update.</p>
<ul>
  <li>Request ID</li>
  <li>Request Type (Initial, Concurrent, Retrospective)</li>
  <li>Requested Dates / Services</li>
  <li>Requesting Clinician</li>
  <li>Status</li>
  <li>Attachments</li>
</ul>
<p>Paths: /utilization/[utilizationId]/requests and /utilization/[utilizationId]/requests/[requestId]</p>

<h3>4.3 Authorizations Tab</h3>
<p>Authorization decisions and details.</p>
<ul>
  <li>Authorization ID / Number</li>
  <li>Authorized Services & Limits</li>
  <li>Valid From / To</li>
  <li>Authorization Status</li>
  <li>Reviewer / Decision Notes</li>
</ul>
<p>Paths: /utilization/[utilizationId]/authorizations and /utilization/[utilizationId]/authorizations/[authId]</p>

<h3>4.4 Notes Tab</h3>
<ul>
  <li>Note ID</li>
  <li>Author</li>
  <li>Note Type (Clinical, Administrative, Escalation)</li>
  <li>Content</li>
  <li>Timestamp</li>
</ul>
<p>User actions: add, edit, filter, and search notes</p>
<p>Path: /utilization/[utilizationId]/notes</p>

<h3>4.5 History Tab</h3>
<p>Chronological timeline of events (submission, review steps, escalations, decisions).</p>
<p>Path: /utilization/[utilizationId]/history</p>

<h3>4.6 Reports Tab</h3>
<p>Utilization metrics and episode-specific reports: length of stay, denial reasons, resource usage.</p>
<p>Paths: /utilization/[utilizationId]/reports and consolidated /utilization/reports</p>

<h3>4.7 Audit Tab</h3>
<p>Audit trail for data changes, access to requests and attachments.</p>
<ul>
  <li>Audit ID</li>
  <li>Action</li>
  <li>User</li>
  <li>Timestamp</li>
  <li>Details</li>
</ul>
<p>Paths: /utilization/[utilizationId]/audit and /utilization/[utilizationId]/audit/[auditId]</p>

<h2>5. Utilization Data Structure</h2>
<p>Core Fields:</p>
<ul>
  <li>id (utilizationId)</li>
  <li>memberName, memberId</li>
  <li>providerName, providerId</li>
  <li>serviceType</li>
  <li>status</li>
  <li>type (Admission, Procedure, Medication, Imaging, HomeHealth)</li>
  <li>priority (High, Standard, Low)</li>
  <li>requestedStartDate, requestedEndDate</li>
  <li>decisionDate, decisionBy</li>
  <li>authorizedServices (array)</li>
  <li>authorizationId</li>
  <li>denialReason</li>
  <li>clinicalSummary</li>
  <li>attachments (count / list)</li>
  <li>createdAt, updatedAt</li>
</ul>

<p>Status Values:</p>
<ul>
  <li>Approved (green)</li>
  <li>Pending (orange)</li>
  <li>Denied (red)</li>
  <li>Under Review (blue)</li>
  <li>Escalated (purple)</li>
</ul>

<h2>6. Page Components and Layout</h2>
<ul>
  <li><strong>Breadcrumb:</strong> auto-generates from URL, capitalizes segments, links parent segments</li>
  <li><strong>Back Button:</strong> returns to /utilization</li>
  <li><strong>Header Card:</strong> title, subtitle, actions (Edit, Print, Share, Create Authorization)</li>
  <li><strong>Summary Card:</strong> two-column summary with status, dates, member</li>
  <li><strong>Tab Navigation:</strong> Overview, Requests, Authorizations, Notes, History, Reports, Audit</li>
</ul>

<h2>7. User Actions and Features</h2>
<ul>
  <li>Search and filter utilization episodes (by ID, member, provider, status, date)</li>
  <li>Create new utilization requests</li>
  <li>Review and make authorization decisions (approve/deny/modify)</li>
  <li>Add clinical notes and escalation entries</li>
  <li>View and download attachments</li>
  <li>Export utilization reports</li>
  <li>View complete audit trails and history</li>
</ul>

<h2>8. Routing Paths</h2>
<ul>
  <li>Utilization List: /utilization</li>
  <li>Utilization Details (Overview): /utilization/[utilizationId]</li>
  <li>Overview Tab: /utilization/[utilizationId]/overview</li>
  <li>Requests List: /utilization/[utilizationId]/requests</li>
  <li>Request Details: /utilization/[utilizationId]/requests/[requestId]</li>
  <li>Authorizations List: /utilization/[utilizationId]/authorizations</li>
  <li>Authorization Details: /utilization/[utilizationId]/authorizations/[authId]</li>
  <li>Notes: /utilization/[utilizationId]/notes</li>
  <li>History: /utilization/[utilizationId]/history</li>
  <li>Reports: /utilization/[utilizationId]/reports</li>
  <li>Audit: /utilization/[utilizationId]/audit</li>
</ul>

<h2>9. Related Modules</h2>
<ul>
  <li>Members Module: /members/[memberId]/utilization</li>
  <li>Providers Module: /providers/[providerId]/utilization</li>
  <li>Authorizations Module</li>
  <li>Claims Module (post-authorization billing)</li>
  <li>Case Management</li>
  <li>Reporting / Analytics</li>
</ul>

<h2>10. Key Features and Functionalities</h2>
<ul>
  <li>Clinical criteria checks and decision documentation</li>
  <li>Concurrent and retrospective review support</li>
  <li>Prior authorization lifecycle and validity tracking</li>
  <li>Escalation workflows and reviewer assignments</li>
  <li>Length-of-stay and utilization analytics</li>
  <li>Complete audit trail and compliance reporting</li>
</ul>
