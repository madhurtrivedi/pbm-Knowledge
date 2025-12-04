<h1>Billing Module — Documentation</h1>

<h2>1. Module Purpose</h2>
<p>
  The <strong>Billing</strong> module displays the list of all invoices and billing records in the system. 
  It provides access to invoice information such as payment status, transaction history, payment details, 
  adjustments, and financial summaries.
</p>

<p><strong>Primary Unique Identifier:</strong> <code>invoiceId</code></p>

<p><strong>Navigation Path:</strong> <code>/billing</code></p>
<p>Users can open the module through the left menu → <strong>Billing</strong>.</p>

<hr />

<h2>2. Billing List</h2>
<p>The Billing list page displays the following details:</p>
<ul>
  <li>Invoice ID (unique identifier)</li>
  <li>Customer/Patient name</li>
  <li>Amount (total invoice amount)</li>
  <li>Status (Paid, Pending, Overdue, Partially Paid)</li>
  <li>Due date</li>
  <li>Created date</li>
</ul>
<p>Selecting an invoice opens the Invoice Details view.</p>

<hr />

<h2>3. Invoice Details — Tabs Overview</h2>
<p>A selected invoice's details are divided into multiple tabs. Each tab has its own navigation path.</p>
<p><strong>Base Path:</strong> <code>/billing/[invoiceId]/[tabName]</code></p>

<hr />

<h3>3.1 Overview Tab</h3>
<p><strong>Description:</strong> Displays comprehensive invoice information.</p>

<p><strong>Information available:</strong></p>
<ul>
  <li>Invoice ID</li>
  <li>Customer/Patient name</li>
  <li>Total amount</li>
  <li>Status (with color-coded tags)</li>
  <li>Due date</li>
  <li>Created date</li>
  <li>Payment method</li>
  <li>Description of services</li>
</ul>

<p><strong>Navigation Path:</strong> <code>/billing/[invoiceId]</code> or <code>/billing/[invoiceId]/overview</code></p>

<hr />

<h3>3.2 Payments Tab</h3>
<p><strong>Description:</strong> Displays the list of all payment transactions related to the invoice.</p>

<p><strong>Information for each payment:</strong></p>
<ul>
  <li>Payment ID</li>
  <li>Payment date</li>
  <li>Payment method</li>
  <li>Amount paid</li>
  <li>Transaction reference</li>
</ul>

<p><strong>Navigation Path:</strong> <code>/billing/[invoiceId]/payments</code></p>

<hr />

<h3>3.3 Notes Tab</h3>
<p><strong>Description:</strong> Displays internal notes and comments about the invoice.</p>

<p><strong>Navigation Path:</strong> <code>/billing/[invoiceId]/notes</code></p>

<hr />

<h3>3.4 Adjustments Tab</h3>
<p><strong>Description:</strong> Displays list of adjustments made to the invoice.</p>

<p><strong>Information for each adjustment:</strong></p>
<ul>
  <li>Adjustment ID</li>
  <li>Adjustment type</li>
  <li>Amount adjusted</li>
  <li>Reason</li>
  <li>Date</li>
</ul>

<p><strong>User actions:</strong></p>
<ul>
  <li>View adjustment list</li>
  <li>Select individual adjustments for detailed view</li>
  <li>Navigate to adjustment details</li>
</ul>

<p><strong>Navigation Paths:</strong></p>
<ul>
  <li>Adjustments List: <code>/billing/[invoiceId]/adjustments</code></li>
  <li>Adjustment Details: <code>/billing/[invoiceId]/adjustments/[adjustmentId]</code></li>
  <li>Adjustment History: <code>/billing/[invoiceId]/adjustments/[adjustmentId]/history</code></li>
  <li>History Entry Details: <code>/billing/[invoiceId]/adjustments/[adjustmentId]/history/[historyId]</code></li>
  <li>History Review: <code>/billing/[invoiceId]/adjustments/[adjustmentId]/history/[historyId]/review</code></li>
  <li>Review Details: <code>/billing/[invoiceId]/adjustments/[adjustmentId]/history/[historyId]/review/[reviewId]</code></li>
  <li>Review Notes: <code>/billing/[invoiceId]/adjustments/[adjustmentId]/history/[historyId]/review/[reviewId]/notes/[noteId]</code></li>
</ul>

<hr />

<h2>4. Invoice Data Structure</h2>

<p><strong>Core Invoice Fields:</strong></p>
<ul>
  <li><code>id</code> (Invoice ID)</li>
  <li><code>customerName</code> (Customer/Patient name)</li>
  <li><code>amount</code> (Total invoice amount)</li>
  <li><code>status</code> (Payment status)</li>
  <li><code>dueDate</code> (Payment due date)</li>
  <li><code>createdDate</code> (Invoice creation date)</li>
</ul>

<p><strong>Status Values:</strong></p>
<ul>
  <li>Paid (green tag)</li>
  <li>Pending (orange tag)</li>
  <li>Overdue (red tag)</li>
  <li>Partially Paid (blue tag)</li>
</ul>

<hr />

<h2>5. Summary of Routing Paths</h2>
<table>
  <tr>
    <th>Feature</th>
    <th>Route</th>
  </tr>
  <tr>
    <td>Billing List or Billing Module</td>
    <td><code>/billing</code></td>
  </tr>
  <tr>
    <td>Invoice Details (Overview)</td>
    <td><code>/billing/[invoiceId]</code></td>
  </tr>
  <tr>
    <td>Overview Tab</td>
    <td><code>/billing/[invoiceId]/overview</code></td>
  </tr>
  <tr>
    <td>Payments</td>
    <td><code>/billing/[invoiceId]/payments</code></td>
  </tr>
  <tr>
    <td>Notes</td>
    <td><code>/billing/[invoiceId]/notes</code></td>
  </tr>
  <tr>
    <td>Adjustments List</td>
    <td><code>/billing/[invoiceId]/adjustments</code></td>
  </tr>
  <tr>
    <td>Adjustment Details</td>
    <td><code>/billing/[invoiceId]/adjustments/[adjustmentId]</code></td>
  </tr>
  <tr>
    <td>Adjustment History</td>
    <td><code>/billing/[invoiceId]/adjustments/[adjustmentId]/history</code></td>
  </tr>
  <tr>
    <td>History Entry Details</td>
    <td><code>/billing/[invoiceId]/adjustments/[adjustmentId]/history/[historyId]</code></td>
  </tr>
  <tr>
    <td>History Review</td>
    <td><code>/billing/[invoiceId]/adjustments/[adjustmentId]/history/[historyId]/review</code></td>
  </tr>
  <tr>
    <td>Review Details</td>
    <td><code>/billing/[invoiceId]/adjustments/[adjustmentId]/history/[historyId]/review/[reviewId]</code></td>
  </tr>
  <tr>
    <td>Review Notes (Deepest Level)</td>
    <td><code>/billing/[invoiceId]/adjustments/[adjustmentId]/history/[historyId]/review/[reviewId]/notes/[noteId]</code></td>
  </tr>
</table>

<hr />

<h2>6. Related Modules</h2>
<p>The Billing module is interconnected with other modules in the system:</p>
<ul>
  <li><strong>Members Module:</strong> Invoices are associated with specific members/patients</li>
  <li><strong>Claims Module:</strong> Billing records are often generated from processed claims</li>
  <li><strong>Payments Module:</strong> Detailed payment processing and transaction management</li>
</ul>

<hr />

<h2>7. Key Features and Functionalities</h2>

<h3>7.1 Invoice Status Management</h3>
<p>Invoices can have multiple statuses throughout their lifecycle:</p>
<ul>
  <li><strong>Paid:</strong> Invoice has been fully paid</li>
  <li><strong>Pending:</strong> Invoice is awaiting payment</li>
  <li><strong>Overdue:</strong> Payment deadline has passed</li>
  <li><strong>Partially Paid:</strong> Some payment received, balance remaining</li>
</ul>

<h3>7.2 Payment Tracking</h3>
<p>The billing system supports:</p>
<ul>
  <li>Multiple payment records per invoice</li>
  <li>Payment method tracking</li>
  <li>Transaction reference numbers</li>
  <li>Payment date tracking</li>
</ul>

<h3>7.3 Adjustment Management</h3>
<p>The adjustments system allows:</p>
<ul>
  <li>Multiple adjustments per invoice</li>
  <li>Detailed adjustment history tracking</li>
  <li>Multi-level review process</li>
  <li>Notes and comments at each level</li>
  <li>Complete audit trail with 6 levels of nesting</li>
</ul>

<h3>7.4 Notes and Communication</h3>
<p>The notes system enables:</p>
<ul>
  <li>Internal team communication about invoices</li>
  <li>Documentation of decisions and actions</li>
  <li>Timestamped entries with author attribution</li>
</ul>
