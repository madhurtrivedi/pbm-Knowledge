<h1>Authorizations Module — Documentation</h1>

<h2>1. Module Purpose</h2>
<p>
  The <strong>Authorizations Management</strong> module displays the list of all pre-authorization requests in the system. 
  It provides access to authorization information such as member details, provider information, service types, 
  status tracking, and related documents including appeals and notes.
</p>

<p><strong>Primary Unique Identifier:</strong> <code>authId</code></p>
<p>authId is alphanumeric, without whitespace and of pattern AUTH001</p>

<p><strong>Navigation Path:</strong> <code>/authorizations</code></p>
<p>Users can open the module through the left menu → <strong>Authorizations</strong>.</p>

<hr />

<h2>2. Authorizations List</h2>

<h3>2.1 Overview Statistics</h3>
<p>The Authorizations module displays four key statistics cards at the top of the page:</p>
<ul>
  <li><strong>Total Authorizations:</strong> Total count of all authorization requests in the system</li>
  <li><strong>Approved:</strong> Count of authorizations with Approved status</li>
  <li><strong>Pending:</strong> Count of authorizations with Pending status</li>
  <li><strong>Denied:</strong> Count of authorizations with Denied status</li>
</ul>

<h3>2.2 Search and Filter Functionality</h3>
<p>The page provides comprehensive search and filter capabilities:</p>
<ul>
  <li><strong>Search Bar:</strong> Search authorizations by member name, Authorization ID, or Member ID</li>
  <li><strong>Status Filter:</strong> Filter by status (All Status, Approved, Pending, Denied, In Review)</li>
  <li><strong>Urgency Filter:</strong> Filter by urgency level (All Urgency, Urgent, Standard)</li>
  <li><strong>More Filters Button:</strong> Additional filtering options</li>
  <li><strong>New Authorization Button:</strong> Create a new authorization request in the system</li>
</ul>

<h3>2.3 Authorizations Table</h3>
<p>The Authorizations list table displays the following details for each authorization:</p>
<ul>
  <li>Authorization ID (Auth ID) - clickable link to details</li>
  <li>Member name and Member ID</li>
  <li>Provider name</li>
  <li>Service type (e.g., Specialist Consultation, Surgery, Physical Therapy, MRI Scan)</li>
  <li>Status (Approved, Pending, Denied, In Review)</li>
  <li>Urgency level (Urgent, Standard)</li>
  <li>Amount (estimated or approved amount)</li>
  <li>Submitted date</li>
  <li>Actions (View button, Download button for approved authorizations)</li>
</ul>
<p>Selecting an authorization opens the Authorization Details view.</p>

<p><strong>Table Features:</strong></p>
<ul>
  <li>Pagination with page size options</li>
  <li>Quick jump to specific page</li>
  <li>Total items count display</li>
  <li>Horizontal scroll for smaller screens</li>
  <li>Clickable rows for quick navigation</li>
</ul>

<hr />

<h2>3. Authorization Details — Tabs Overview</h2>
<p>A selected authorization's details are divided into multiple tabs. Each tab has its own navigation path.</p>
<p><strong>Base Path:</strong> <code>/authorizations/[authId]/[tabName]</code></p>

<p><strong>Available Tabs:</strong></p>
<ul>
  <li>Details (default overview)</li>
</ul>

<hr />

<h3>3.1 Details Tab</h3>
<p><strong>Description:</strong> Displays comprehensive authorization information and details.</p>
<p><strong>Information available:</strong></p>
<ul>
  <li>Authorization ID</li>
  <li>Member name and Member ID</li>
  <li>Service type</li>
  <li>Provider name</li>
  <li>Status (Approved, Pending, Denied)</li>
  <li>Urgency level (High, Medium, Low)</li>
  <li>Authorized amount</li>
  <li>Diagnosis information</li>
  <li>Procedure details</li>
  <li>Facility name</li>
  <li>Requested date</li>
  <li>Approved date (if applicable)</li>
  <li>Notes and comments</li>
  <li>Attached documents list</li>
</ul>

<p><strong>User actions:</strong></p>
<ul>
  <li>Edit authorization details</li>
  <li>Approve authorization request</li>
  <li>View attached documents</li>
</ul>

<p><strong>Navigation Path:</strong> <code>/authorizations/[authId]</code> or <code>/authorizations/[authId]/details</code></p>

<h4>3.1.1 Authorization Appeals</h4>
<p><strong>Description:</strong> Shows the list of appeals associated with the authorization request.</p>
<p><strong>Appeal information includes:</strong></p>
<ul>
  <li>Appeal ID</li>
  <li>Member ID</li>
  <li>Reason for appeal (e.g., Claim Denied, Coverage Dispute, Payment Issue)</li>
  <li>Status (Pending, Under Review, Approved, Denied)</li>
  <li>Submitted date</li>
  <li>Description/details</li>
  <li>Actions (View Details button)</li>
</ul>

<p><strong>User actions:</strong></p>
<ul>
  <li>View appeal list</li>
  <li>Click on an appeal to view full details</li>
</ul>

<p><strong>Navigation Path:</strong> <code>/authorizations/[authId]/appeals</code></p>

<h5>3.1.1.1 Appeal Detail</h5>
<p><strong>Description:</strong> Shows the details of the appeal like Appeal Id, Member name, Reason, Status, Priority.</p>
<p><strong>Navigation Path:</strong> <code>/authorizations/[authId]/appeals/[appealId]</code></p>

<h5>3.1.1.2 Appeal Reviews</h5>
<p><strong>Description:</strong> Shows the reviews of the appeal like Review Id, Review by, Status, Comments.</p>
<p><strong>Navigation Path:</strong> <code>/authorizations/[authId]/appeals/[appealId]</code></p>

<h6>3.1.1.2.1 Appeal Review Detail</h6>
<p><strong>Description:</strong> Shows the details of a particular appeal, shows information like Review ID, Appeal ID, Authorization ID and By</p>
<p><strong>Navigation Path:</strong> <code>/authorizations/[authId]/appeals/[appealId]/review/[reviewId]</code></p>

<hr />

<h3>3.2 Permissions Tab</h3>
<p><strong>Description:</strong> Displays the permission for a particular user.</p>

<h3>3.3 History Tab</h3>
<p><strong>Description:</strong> Displays the history for a particular user.</p>

<hr />

<h2>4. Summary of Routing Paths</h2>
<table>
  <tr>
    <th>Feature</th>
    <th>Route</th>
  </tr>
  <tr>
    <td>Authorizations List Or Authorizations module</td>
    <td><code>/authorizations</code></td>
  </tr>
  <tr>
    <td>Authorization Details (Overview)</td>
    <td><code>/authorizations/[authId]</code></td>
  </tr>
  <tr>
    <td>Authorization Appeals</td>
    <td><code>/authorizations/[authId]/appeals</code></td>
  </tr>
  <tr>
    <td>Authorization Appeal Details</td>
    <td><code>/authorizations/[authId]/appeals/[appealId]</code></td>
  </tr>
  <tr>
    <td>Authorization Appeal Details Review</td>
    <td><code>/authorizations/[authId]/appeals/[appealId]/review/[reviewId]</code></td>
  </tr>
</table>
