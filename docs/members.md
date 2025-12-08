<h1>Members Module — Documentation</h1>

<h2>1. Module Purpose</h2>
<p>
  The <strong>Members</strong> module displays the list of all members in the system. 
  It provides access to member information such as plan details, eligibility, status, 
  personal information, and service-related records.
</p>

<p><strong>Primary Unique Identifier:</strong> <code>memberId</code></p>
<p>memberId is alphanumeric, without whitespace and have a pattern of MEM001</p>

<p><strong>Navigation Path:</strong> <code>/members</code></p>
<p>Users can open the module through the left menu → <strong>Members</strong>.</p>

<hr />

<h2>2. Members List</h2>

<p>The Members List page displays the following details:</p>
<ul>
  <li><strong>Member ID</strong> (unique identifier)</li>
  <li><strong>Member Name</strong></li>
  <li><strong>Plan Type</strong></li>
  <li><strong>Group</strong></li>
  <li><strong>Status</strong> (Active or Inactive)</li>
</ul>

<p>Selecting a member opens the Member Details view.</p>

<p><strong>Navigation Path:</strong> <code>/members</code></p>

<p><strong>API Details:</strong></p>
<ul>
  <li><strong>URL:</strong> <code>GET /api/get-members</code></li>
  <li><strong>Query Parameters:</strong>
    <ul>
      <li><code>memberId</code> (optional)</li>
      <li><code>memberName</code> (optional)</li>
    </ul>
  </li>
</ul>
<p><strong>Description:</strong>  
This API returns a filtered list of members:
</p>
<ul>
  <li>If <code>memberId</code> is provided, it returns the exact matching member.</li>
  <li>If <code>memberName</code> is provided, it may return multiple matching members.</li>
</ul>


<hr />

<h2>3. Member Details — Tabs Overview</h2>
<p>A selected member’s details are divided into multiple tabs. Each tab has its own navigation path.</p>
<p><strong>Base Path:</strong> <code>/members/[memberId]/[tabName]</code></p>

<hr />

<h3>3.1 Overview Tab</h3>
<p><strong>Description:</strong> Displays general member information.</p>
<p><strong>Information available:</strong></p>
<ul>
  <li>Group name</li>
  <li>Dependents</li>
  <li>Phone number</li>
  <li>Email address</li>
  <li>Address</li>
</ul>
<p><strong>Navigation Path:</strong> <code>/members/[memberId]</code></p>

<hr />

<h3>3.2 Authorizations Tab</h3>
<p><strong>Description:</strong> Displays the member’s Prior Authorizations.</p>
<p><strong>Information for each authorization:</strong></p>
<ul>
  <li>Service provided</li>
  <li>Provider name</li>
  <li>Request date</li>
  <li>Approval date</li>
</ul>
<p><strong>Navigation Path:</strong> <code>/members/[memberId]/authorizations</code></p>

<hr />

<h3>3.3 Claims Tab</h3>
<p><strong>Description:</strong> Shows the list of claims associated with the member.</p>
<p><strong>Information for each claim:</strong></p>
<ul>
  <li>Claim number</li>
  <li>Service type</li>
  <li>Status</li>
  <li>Amount</li>
</ul>
<p>
  Selecting a claim opens the Claim Details page inside the Claims module.
</p>
<p><strong>Navigation Path:</strong> <code>/members/[memberId]/claims</code></p>

<hr />

<h3>3.4 Coverage Tab</h3>
<p><strong>Description:</strong> Displays the member’s coverage and policy information.</p>
<p><strong>User actions:</strong></p>
<ul>
  <li>View coverage</li>
  <li>View policies</li>
  <li>Navigate to endorsements</li>
</ul>

<p><strong>Navigation Paths:</strong></p>
<ul>
  <li>Coverage: <code>/members/[memberId]/coverage</code></li>
  <li>Policies: <code>/members/[memberId]/coverage/policies/[policyId]</code></li>
  <li>Endorsements: <code>/members/[memberId]/coverage/policies/[policyId]/endorsements/[endorsementId]</code></li>
</ul>

<hr />

<h3>3.5 Documents Tab</h3>
<p><strong>Description:</strong> Lists documents associated with the member.</p>
<p><strong>Document types may include:</strong></p>
<ul>
  <li>Medical reports</li>
  <li>Insurance cards</li>
  <li>Prescriptions</li>
</ul>
<p><strong>Navigation Path:</strong> <code>/members/[memberId]/documents</code></p>

<hr />

<h3>3.6 History Tab</h3>
<p><strong>Description:</strong> Displays chronological events related to the member.</p>
<p><strong>Examples of history events:</strong></p>
<ul>
  <li>Enrollment</li>
  <li>Authorization approvals</li>
  <li>Claim submissions</li>
  <li>Policy renewals</li>
</ul>
<p><strong>Navigation Path:</strong> <code>/members/[memberId]/history</code></p>

<hr />

<h3>3.7 Profile Tab</h3>
<p><strong>Description:</strong> Shows the member’s complete personal profile.</p>
<p><strong>Profile fields include:</strong></p>
<ul>
  <li>Full name</li>
  <li>Date of birth (DOB)</li>
  <li>Plan type</li>
  <li>Status</li>
  <li>Email</li>
  <li>Phone</li>
  <li>Address</li>
</ul>
<p><strong>Navigation Path:</strong> <code>/members/[memberId]/profile</code></p>

<hr />

<h3>3.8 Notes Tab</h3>
<p><strong>Description:</strong> Displays internal notes and comments about the member.</p>
<p><strong>Navigation Path:</strong> <code>/members/[memberId]/notes</code></p>

<hr />

<h2>4. Summary of Routing Paths</h2>
<table>
  <tr>
    <th>Feature</th>
    <th>Route</th>
  </tr>
  <tr>
    <td>Members List Or Members module</td>
    <td><code>/members</code></td>
  </tr>
  <tr>
    <td>Member Details (Overview)</td>
    <td><code>/members/[memberId]</code></td>
  </tr>
  <tr>
    <td>Authorizations</td>
    <td><code>/members/[memberId]/authorizations</code></td>
  </tr>
  <tr>
    <td>Claims</td>
    <td><code>/members/[memberId]/claims</code></td>
  </tr>
  <tr>
    <td>Coverage</td>
    <td><code>/members/[memberId]/coverage</code></td>
  </tr>
  <tr>
    <td>Coverage Policies</td>
    <td><code>/members/[memberId]/coverage/policies/[policyId]</code></td>
  </tr>
  <tr>
    <td>Endorsements</td>
    <td><code>/members/[memberId]/coverage/policies/[policyId]/endorsements/[endorsementId]</code></td>
  </tr>
  <tr>
    <td>Documents</td>
    <td><code>/members/[memberId]/documents</code></td>
  </tr>
  <tr>
    <td>History</td>
    <td><code>/members/[memberId]/history</code></td>
  </tr>
  <tr>
    <td>Profile</td>
    <td><code>/members/[memberId]/profile</code></td>
  </tr>
  <tr>
    <td>Notes</td>
    <td><code>/members/[memberId]/notes</code></td>
  </tr>
</table>
