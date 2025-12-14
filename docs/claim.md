<h1>Claims Module — Documentation</h1>

<h2>1. Module Purpose</h2>
<p>
  The <strong>Claims</strong> module displays the list of all claims in the system. 
  It provides access to claim information such as claim status, service details, financial data, 
  provider information, member details, and claim processing history.
</p>

<p><strong>Primary Unique Identifier:</strong> <code>claimId</code></p>

<p><strong>Navigation Path:</strong> <code>/claims</code></p>
<p>Users can open the module through the left menu → <strong>Claims</strong>.</p>

<hr />

<h2>2. Claims List</h2>
<p>The Claims list page displays the following details:</p>
<ul>
  <li>Claim ID (unique identifier)</li>
  <li>Member name</li>
  <li>Status (Approved, Pending, Denied, Under Review)</li>
  <li>Amount (total claim amount)</li>
</ul>
<p>Selecting a claim opens the Claim Details view.</p>

<p><strong>Navigation Path:</strong> <code>/claims</code></p>

<p><strong>API Details:</strong></p>
<ul>
  <li><strong>URL:</strong> <code>POST /api/claims</code></li>
  <li><strong>Query Parameters:</strong>
    <ul>
      <li><code>ids</code> (optional)</li>
      <li><code>memberName</code> (optional, It is a person's name and not an id)</li>
      <li><code>status</code> (optional)</li>
    </ul>
  </li>
</ul>
<p><strong>Description:</strong>  
This API returns a filtered list of claims:
</p>
<ul>
  <li>If <code>ids</code> is provided, it returns the exact matching list of ids in array</li>
  <li>If <code>memberName</code> is provided, it may return multiple claims for memberName.</li>
  <li>If <code>status</code> is provided, it may return claims based on status.</li>
</ul>

<hr />

<h2>3. Create Claim</h2>
<p>The Create Claim page allows users to submit a new claim by entering member, provider, and prescription details.</p>

<p>The following fields are captured on this page:</p>
<ul>
  <li>Member ID</li>
  <li>Member Name</li>
  <li>Date of Birth</li>
  <li>Gender</li>
  <li>Pharmacy Name</li>
  <li>Group Number</li>
  <li>Provider Name</li>
  <li>Plan Type</li>
  <li>NDC (National Drug Code)</li>
  <li>Final Cost</li>
</ul>

<p>On successful submission, the claim is created and becomes available in the Claims List.</p>

<p><strong>Navigation Path:</strong></p>
<ul>
  <li><code>/claims/createclaim</code></li>
  <li><code>/claims/createclaim?memberId=&lt;memberId&gt;</code> (optional)</li>
</ul>

<p><strong>API Details:</strong></p>
<ul>
  <li><strong>URL:</strong> <code>POST /api/claims/create</code></li>
  <li><strong>Request Body:</strong>
    <ul>
      <li><code>memberId</code> (required if not passed in route)</li>
      <li><code>memberName</code> (required)</li>
      <li><code>dateOfBirth</code> (required)</li>
      <li><code>gender</code> (required)</li>
      <li><code>pharmacyName</code> (required)</li>
      <li><code>groupNumber</code> (required)</li>
      <li><code>providerName</code> (required)</li>
      <li><code>planType</code> (required)</li>
      <li><code>ndc</code> (required)</li>
      <li><code>finalCost</code> (required)</li>
    </ul>
  </li>
</ul>

<p><strong>Description:</strong></p>
<ul>
  <li>If <code>memberId</code> is provided in the route, the Member ID field is pre-populated.</li>
  <li>All required fields must be completed to submit the claim.</li>
  <li>Upon successful creation, a unique Claim ID is generated.</li>
</ul>

<hr />

<h2>4. Claim Details Page — Layout and Components</h2>
<p>When a user navigates to a specific claim (e.g., <code>/claims/CLM001</code>), the page displays:</p>

<h3>4.0 Claim Details Page Structure</h3>

<p><strong>Header Section:</strong></p>
<ul>
  <li><strong>Breadcrumb Navigation:</strong> Shows hierarchical path (Home / Claims / CLM001)</li>
  <li><strong>Back Button:</strong> "Back to Claims" - Returns to claims list</li>
  <li><strong>Claim Title:</strong> Large heading displaying "Claim: CLM001"</li>
  <li><strong>Claim Subtitle:</strong> Secondary info showing "Member Name - Amount" (e.g., "John Doe - $1,250.00")</li>
  <li><strong>Action Buttons (Top Right):</strong>
    <ul>
      <li>Edit button - Allows editing claim information</li>
      <li>Print button - Prints claim details</li>
      <li>Share button - Shares claim information</li>
    </ul>
  </li>
</ul>

<p><strong>Summary Card:</strong></p>
<p>Displays quick overview information in a compact card format:</p>
<ul>
  <li><strong>Status:</strong> Color-coded status badge (Approved/Pending/Denied/Under Review)</li>
  <li><strong>Amount:</strong> Total claim amount</li>
  <li><strong>Submitted Date:</strong> Date when claim was submitted</li>
  <li><strong>Member:</strong> Member name associated with the claim</li>
</ul>

<p><strong>Tab Navigation:</strong></p>
<p>Five tabs for different aspects of the claim:</p>
<ol>
  <li>Overview (default)</li>
  <li>Attachments</li>
  <li>Notes</li>
  <li>History</li>
  <li>Adjudication</li>
</ol>

<p><strong>Content Area:</strong></p>
<p>Displays the content of the selected tab below the tab navigation.</p>

<hr />

<h2>5. Claim Details — Tabs Overview</h2>
<p>A selected claim's details are divided into multiple tabs. Each tab has its own navigation path.</p>
<p><strong>Base Path:</strong> <code>/claims/[claimId]/[tabName]</code></p>

<hr />

<h3>5.1 Overview Tab</h3>
<p><strong>Description:</strong> Displays comprehensive claim information in a detailed descriptions layout.</p>

<p><strong>Page Layout:</strong></p>
<ul>
  <li><strong>Section Title:</strong> "Claim Details" with document icon</li>
  <li><strong>Action Button:</strong> "View Overview" button (top right) - navigates to overview tab</li>
</ul>

<p><strong>Information available (in order of display):</strong></p>
<ol>
  <li><strong>Claim ID</strong> - Unique claim identifier (e.g., CLM001)</li>
  <li><strong>Member</strong> - Member name and ID (e.g., "John Smith (MEM001)")
    <ul>
      <li>Member ID is clickable and links to member profile</li>
    </ul>
  </li>
  <li><strong>Provider</strong> - Provider name and ID (e.g., "Dr. Sarah Johnson (PRV001)")
    <ul>
      <li>Provider ID is clickable and links to provider profile</li>
    </ul>
  </li>
  <li><strong>Service Type</strong> - Type of medical service (e.g., "Cardiology", "Orthopedics")</li>
  <li><strong>Status</strong> - Claim processing status with color-coded tag</li>
  <li><strong>Amount</strong> - Total claim amount (e.g., "$1,250.00")</li>
  <li><strong>Claim Type</strong> - Category with color-coded tag (Medical/Surgical/Dental/Vision)</li>
  <li><strong>Priority</strong> - Priority level with color-coded tag (High/Standard/Low)</li>
  <li><strong>Description</strong> - Detailed description of the claim</li>
  <li><strong>Attachments</strong> - Number of attached files (e.g., "3 files")</li>
  <li><strong>Submitted Date</strong> - Date claim was submitted</li>
  <li><strong>Processed Date</strong> - Date claim was processed (or "Pending" if not yet processed)</li>
</ol>

<p><strong>Display Format:</strong> Bordered descriptions table with label-value pairs</p>

<p><strong>User actions:</strong></p>
<ul>
  <li>View all claim details in organized format</li>
  <li>Click member ID to navigate to member details</li>
  <li>Click provider ID to navigate to provider details</li>
  <li>Click "View Overview" to navigate to <code>/claims/[claimId]/overview</code></li>
</ul>

<p><strong>Navigation Path:</strong> <code>/claims/[claimId]</code> or <code>/claims/[claimId]/overview</code></p>

<hr />

<h3>5.2 Attachments Tab</h3>
<p><strong>Description:</strong> Displays the list of documents and files attached to the claim.</p>

<p><strong>Information for each attachment:</strong></p>
<ul>
  <li>Attachment ID</li>
  <li>Document name</li>
  <li>Document type (PDF, Image, etc.)</li>
  <li>Upload date</li>
</ul>

<p><strong>User actions:</strong></p>
<ul>
  <li>View attachment list</li>
  <li>Select individual attachments for detailed view</li>
  <li>Navigate to specific attachment details</li>
</ul>

<p><strong>Navigation Paths:</strong></p>
<ul>
  <li>Attachments List: <code>/claims/[claimId]/attachments</code></li>
  <li>Attachment Details: <code>/claims/[claimId]/attachments/[attachmentId]</code></li>
  <li>Attachment Audit: <code>/claims/[claimId]/attachments/[attachmentId]/audit</code></li>
  <li>Audit Details: <code>/claims/[claimId]/attachments/[attachmentId]/audit/[auditId]</code></li>
</ul>

<p><strong>Attachment Detail View includes:</strong></p>
<ul>
  <li>Attachment ID</li>
  <li>File name</li>
  <li>File type (with color-coded tags)</li>
  <li>Upload date</li>
  <li>Access to audit trail</li>
</ul>

<p><strong>Audit Information:</strong></p>
<ul>
  <li>Audit ID</li>
  <li>Action performed (Viewed, Downloaded, etc.)</li>
  <li>User who performed the action</li>
  <li>Date and time of action</li>
  <li>Additional details</li>
</ul>

<hr />

<h3>5.3 Notes Tab</h3>
<p><strong>Description:</strong> Displays internal notes, comments, and communication related to the claim.</p>

<p><strong>Information for each note:</strong></p>
<ul>
  <li>Note ID</li>
  <li>Author name</li>
  <li>Note type (Approval, Request, Denial, Note)</li>
  <li>Content/Message</li>
  <li>Date and time</li>
</ul>

<p><strong>Note Types (with color coding):</strong></p>
<ul>
  <li>Approval (green)</li>
  <li>Request (blue)</li>
  <li>Denial (red)</li>
  <li>Note (default)</li>
</ul>

<p><strong>User actions:</strong></p>
<ul>
  <li>View all notes in chronological order</li>
  <li>Add new notes using text area</li>
  <li>Filter and search notes</li>
</ul>

<p><strong>Navigation Path:</strong> <code>/claims/[claimId]/notes</code></p>

<hr />

<h3>5.4 History Tab</h3>
<p><strong>Description:</strong> Displays chronological timeline of events and status changes for the claim.</p>

<p><strong>Examples of history events:</strong></p>
<ul>
  <li>Claim submitted</li>
  <li>Claim reviewed</li>
  <li>Documentation requested</li>
  <li>Claim approved/denied</li>
  <li>Payment processed</li>
  <li>Status updates</li>
</ul>

<p><strong>Display format:</strong> Timeline view showing events in chronological order with dates</p>

<p><strong>Navigation Path:</strong> <code>/claims/[claimId]/history</code></p>

<hr />

<h3>5.5 Adjudication Tab</h3>
<p><strong>Description:</strong> Shows the adjudication process and decision details for the claim.</p>

<p><strong>Information available:</strong></p>
<ul>
  <li>Claim ID</li>
  <li>Adjudication status (Processed, Pending, etc.)</li>
  <li>Adjudication notes</li>
  <li>Processing details</li>
  <li>Decision rationale</li>
</ul>

<p><strong>User actions:</strong></p>
<ul>
  <li>View adjudication status</li>
  <li>Review processing notes</li>
  <li>Access adjudication history</li>
</ul>

<p><strong>Navigation Path:</strong> <code>/claims/[claimId]/adjudication</code></p>

<hr />

<h3>5.6 Audit Tab (within Attachments)</h3>
<p><strong>Description:</strong> Provides audit trail for attachment access and modifications.</p>

<p><strong>Audit Trail Information:</strong></p>
<ul>
  <li>Audit entry ID</li>
  <li>Action performed</li>
  <li>User who performed the action</li>
  <li>Timestamp</li>
  <li>Detailed description</li>
</ul>

<p><strong>Navigation Path:</strong> <code>/claims/[claimId]/attachments/[attachmentId]/audit</code></p>

<p><strong>Detailed Audit View:</strong> <code>/claims/[claimId]/attachments/[attachmentId]/audit/[auditId]</code></p>

<hr />

<h2>6. Claim Data Structure</h2>

<p><strong>Core Claim Fields:</strong></p>
<ul>
  <li><code>id</code> (Claim ID)</li>
  <li><code>memberName</code> (Member's full name)</li>
  <li><code>memberId</code> (Member reference ID)</li>
  <li><code>providerName</code> (Healthcare provider name)</li>
  <li><code>providerId</code> (Provider reference ID)</li>
  <li><code>serviceType</code> (Type of medical service)</li>
  <li><code>status</code> (Claim processing status)</li>
  <li><code>amount</code> (Total claim amount)</li>
  <li><code>submittedDate</code> (Date claim was submitted)</li>
  <li><code>processedDate</code> (Date claim was processed)</li>
  <li><code>description</code> (Claim description)</li>
  <li><code>claimType</code> (Medical, Surgical, Dental, Vision)</li>
  <li><code>priority</code> (High, Standard, Low)</li>
  <li><code>attachments</code> (Number of attached documents)</li>
</ul>

<p><strong>Status Values:</strong></p>
<ul>
  <li>Approved (green tag)</li>
  <li>Pending (orange tag)</li>
  <li>Denied (red tag)</li>
  <li>Under Review (blue tag)</li>
</ul>

<p><strong>Claim Types:</strong></p>
<ul>
  <li>Medical (blue tag)</li>
  <li>Surgical (red tag)</li>
  <li>Dental (green tag)</li>
  <li>Vision (purple tag)</li>
</ul>

<p><strong>Priority Levels:</strong></p>
<ul>
  <li>High (red tag)</li>
  <li>Standard (blue tag)</li>
  <li>Low (green tag)</li>
</ul>

<hr />

<h2>7. Page Components and Layout</h2>

<h3>7.1 Consistent Header Components</h3>
<p>These components appear on all claim detail pages, regardless of which tab is active:</p>

<p><strong>Breadcrumb Navigation:</strong></p>
<ul>
  <li>Format: <code>Home / Claims / [ClaimId]</code></li>
  <li>Each segment is clickable (except the last one)</li>
  <li>Allows quick navigation back to parent pages</li>
</ul>

<p><strong>Back Button:</strong></p>
<ul>
  <li>Icon: Left arrow</li>
  <li>Label: "Back to Claims"</li>
  <li>Action: Returns to claims list page (<code>/claims</code>)</li>
</ul>

<p><strong>Claim Header Card:</strong></p>
<ul>
  <li><strong>Main Title:</strong> "Claim: [ClaimId]" (e.g., "Claim: CLM001")</li>
  <li><strong>Subtitle:</strong> "[Member Name] - [Amount]" (e.g., "John Doe - $1,250.00")</li>
  <li><strong>Action Buttons:</strong>
    <ul>
      <li>Edit (pencil icon) - Opens claim editor</li>
      <li>Print (printer icon) - Prints current view</li>
      <li>Share (share icon) - Shares claim information</li>
    </ul>
  </li>
</ul>

<p><strong>Summary Information Card:</strong></p>
<p>Two-column layout displaying:</p>
<ul>
  <li><strong>Left Column:</strong>
    <ul>
      <li>Status: Color-coded tag badge</li>
      <li>Amount: Total claim amount</li>
    </ul>
  </li>
  <li><strong>Right Column:</strong>
    <ul>
      <li>Submitted Date: When claim was filed</li>
      <li>Member: Member name</li>
    </ul>
  </li>
</ul>

<p><strong>Tab Navigation Bar:</strong></p>
<ul>
  <li>Overview</li>
  <li>Attachments</li>
  <li>Notes</li>
  <li>History</li>
  <li>Adjudication</li>
</ul>
<p>Active tab is highlighted; clicking a tab navigates to that route.</p>

<h3>7.2 Breadcrumb Component Details</h3>
<p>The breadcrumb automatically generates based on the URL path:</p>
<ul>
  <li>Capitalizes each segment</li>
  <li>Converts dynamic segments (like <code>[claimId]</code>) to their actual values</li>
  <li>Makes all segments except the last one clickable</li>
  <li>Uses "/" as separator</li>
  <li>Applies blue color to clickable links</li>
</ul>

<p><strong>Examples:</strong></p>
<ul>
  <li><code>/claims</code> → "Home / Claims"</li>
  <li><code>/claims/CLM001</code> → "Home / Claims / CLM001"</li>
  <li><code>/claims/CLM001/notes</code> → "Home / Claims / CLM001 / Notes"</li>
  <li><code>/claims/CLM001/attachments/ATT-001</code> → "Home / Claims / CLM001 / Attachments / ATT-001"</li>
</ul>

<hr />

<h2>8. User Actions and Features</h2>

<p><strong>Claim List Page:</strong></p>
<ul>
  <li>View all claims in tabular format</li>
  <li>Click on any claim to view details</li>
  <li>Filter and sort claims</li>
  <li>Search claims by ID, member, or provider</li>
</ul>

<p><strong>Claim Details Page:</strong></p>
<ul>
  <li>Navigate between different tabs</li>
  <li>Edit claim information</li>
  <li>Print claim details</li>
  <li>Share claim information</li>
  <li>Download reports</li>
  <li>Add notes and comments</li>
  <li>View complete audit trail</li>
  <li>Track claim processing progress</li>
</ul>

<hr />

<h2>9. Summary of Routing Paths</h2>
<table>
  <tr>
    <th>Feature</th>
    <th>Route</th>
  </tr>
  <tr>
    <td>Claims List or Claims Module</td>
    <td><code>/claims</code></td>
  </tr>
  <tr>
    <td>Claim Details (Overview)</td>
    <td><code>/claims/[claimId]</code></td>
  </tr>
  <tr>
    <td>Overview Tab</td>
    <td><code>/claims/[claimId]/overview</code></td>
  </tr>
  <tr>
    <td>Attachments List</td>
    <td><code>/claims/[claimId]/attachments</code></td>
  </tr>
  <tr>
    <td>Attachment Details</td>
    <td><code>/claims/[claimId]/attachments/[attachmentId]</code></td>
  </tr>
  <tr>
    <td>Attachment Audit</td>
    <td><code>/claims/[claimId]/attachments/[attachmentId]/audit</code></td>
  </tr>
  <tr>
    <td>Specific Audit Entry</td>
    <td><code>/claims/[claimId]/attachments/[attachmentId]/audit/[auditId]</code></td>
  </tr>
  <tr>
    <td>Notes</td>
    <td><code>/claims/[claimId]/notes</code></td>
  </tr>
  <tr>
    <td>History</td>
    <td><code>/claims/[claimId]/history</code></td>
  </tr>
  <tr>
    <td>Adjudication</td>
    <td><code>/claims/[claimId]/adjudication</code></td>
  </tr>
</table>

<hr />

<h2>10. Related Modules</h2>
<p>The Claims module is interconnected with other modules in the system:</p>
<ul>
  <li><strong>Members Module:</strong> Claims are associated with specific members. Users can navigate from a member's profile to view all their claims at <code>/members/[memberId]/claims</code></li>
  <li><strong>Providers Module:</strong> Claims are linked to healthcare providers. Provider-specific claims can be accessed at <code>/providers/[providerId]/claims</code></li>
  <li><strong>Pharmacies Module:</strong> Pharmacy-related claims can be viewed at <code>/pharmacies/[pharmacyId]/claims</code></li>
  <li><strong>Authorizations Module:</strong> Claims may be related to prior authorizations</li>
  <li><strong>Billing Module:</strong> Claim financial data integrates with billing information</li>
</ul>

<hr />

<h2>11. Key Features and Functionalities</h2>

<h3>11.1 Claim Status Management</h3>
<p>Claims can have multiple statuses throughout their lifecycle:</p>
<ul>
  <li><strong>Approved:</strong> Claim has been reviewed and approved for payment</li>
  <li><strong>Pending:</strong> Claim is awaiting review or additional information</li>
  <li><strong>Denied:</strong> Claim has been rejected</li>
  <li><strong>Under Review:</strong> Claim is currently being processed</li>
</ul>

<h3>11.2 Financial Tracking</h3>
<p>Each claim includes comprehensive financial information:</p>
<ul>
  <li>Total claim amount</li>
  <li>Approved/paid amount</li>
  <li>Member responsibility (copay, deductible)</li>
  <li>Processing progress indicator</li>
</ul>

<h3>11.3 Document Management</h3>
<p>The attachments system allows:</p>
<ul>
  <li>Multiple document uploads per claim</li>
  <li>Support for various file types (PDF, images, etc.)</li>
  <li>Complete audit trail for each document</li>
  <li>Track who accessed or downloaded attachments</li>
</ul>

<h3>11.4 Communication and Notes</h3>
<p>The notes system enables:</p>
<ul>
  <li>Internal team communication about claims</li>
  <li>Documentation of decisions and actions</li>
  <li>Categorization by note type</li>
  <li>Timestamped entries with author attribution</li>
</ul>

<h3>11.5 Audit and Compliance</h3>
<p>Comprehensive audit trails for:</p>
<ul>
  <li>Claim status changes</li>
  <li>Document access and modifications</li>
  <li>User actions and timestamps</li>
  <li>Complete claim history timeline</li>
</ul>
