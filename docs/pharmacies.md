
<h1>Pharmacies Module — Documentation</h1>

<h2>1. Module Purpose</h2>
<p>
	The <strong>Pharmacies</strong> module displays the list of all pharmacies in the system.
	It provides access to pharmacy information such as profile details, claims, inventory, orders, and reviews.
</p>

<p><strong>Primary Unique Identifier:</strong> <code>pharmacyId</code></p>

<p><strong>Navigation Path:</strong> <code>/pharmacies</code></p>
<p>Users can open the module through the left menu → <strong>Pharmacies</strong>.</p>

<hr />

<h2>2. Pharmacies List</h2>
<p>The Pharmacies list page displays the following details:</p>
<ul>
	<li>Pharmacy ID (unique identifier)</li>
	<li>Pharmacy name</li>
	<li>Address</li>
	<li>Contact number</li>
	<li>Status (Active or Inactive)</li>
</ul>
<p>Selecting a pharmacy opens the Pharmacy Details view.</p>

<hr />

<h2>3. Pharmacy Details — Tabs Overview</h2>
<p>A selected pharmacy’s details are divided into multiple tabs. Each tab has its own navigation path.</p>
<p><strong>Base Path:</strong> <code>/pharmacies/[pharmacyId]/[tabName]</code></p>

<hr />

<h3>3.1 Profile Tab</h3>
<p><strong>Description:</strong> Displays general pharmacy information.</p>
<p><strong>Information available:</strong></p>
<ul>
	<li>Pharmacy name</li>
	<li>Address</li>
	<li>Phone number</li>
	<li>Email address</li>
	<li>License/registration details</li>
	<li>Status</li>
</ul>
<p><strong>Navigation Path:</strong> <code>/pharmacies/[pharmacyId]</code></p>

<hr />

<h3>3.2 Claims Tab</h3>
<p><strong>Description:</strong> Shows the list of claims associated with the pharmacy.</p>
<p><strong>Information for each claim:</strong></p>
<ul>
	<li>Claim number</li>
	<li>Member name</li>
	<li>Service type</li>
	<li>Status</li>
	<li>Amount</li>
</ul>
<p><strong>Navigation Path:</strong> <code>/pharmacies/[pharmacyId]/claims</code></p>

<hr />

<h3>3.3 Inventory Tab</h3>
<p><strong>Description:</strong> Displays the pharmacy’s inventory of medicines and products.</p>
<p><strong>Information for each item:</strong></p>
<ul>
	<li>Product name</li>
	<li>Quantity available</li>
	<li>Category</li>
	<li>Expiry date</li>
</ul>
<p><strong>Navigation Path:</strong> <code>/pharmacies/[pharmacyId]/inventory</code></p>

<hr />

<h3>3.4 Orders Tab</h3>
<p><strong>Description:</strong> Lists orders placed with or by the pharmacy.</p>
<p><strong>Information for each order:</strong></p>
<ul>
	<li>Order number</li>
	<li>Date</li>
	<li>Status</li>
	<li>Total amount</li>
</ul>
<p><strong>Navigation Path:</strong> <code>/pharmacies/[pharmacyId]/orders</code></p>

<hr />

<h3>3.5 Reviews Tab</h3>
<p><strong>Description:</strong> Displays reviews and ratings for the pharmacy.</p>
<p><strong>Information for each review:</strong></p>
<ul>
	<li>Reviewer name</li>
	<li>Rating</li>
	<li>Comments</li>
	<li>Date</li>
</ul>
<p><strong>Navigation Path:</strong> <code>/pharmacies/[pharmacyId]/reviews</code></p>

<hr />

<h2>4. Summary of Routing Paths</h2>
<table>
	<tr>
		<th>Feature</th>
		<th>Route</th>
	</tr>
	<tr>
		<td>Pharmacies List Or Pharmacies module</td>
		<td><code>/pharmacies</code></td>
	</tr>
	<tr>
		<td>Pharmacy Details (Profile)</td>
		<td><code>/pharmacies/[pharmacyId]</code></td>
	</tr>
	<tr>
		<td>Claims</td>
		<td><code>/pharmacies/[pharmacyId]/claims</code></td>
	</tr>
	<tr>
		<td>Inventory</td>
		<td><code>/pharmacies/[pharmacyId]/inventory</code></td>
	</tr>
	<tr>
		<td>Orders</td>
		<td><code>/pharmacies/[pharmacyId]/orders</code></td>
	</tr>
	<tr>
		<td>Reviews</td>
		<td><code>/pharmacies/[pharmacyId]/reviews</code></td>
	</tr>
</table>
