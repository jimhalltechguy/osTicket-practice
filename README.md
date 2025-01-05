
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">

</head>
<body>
    <h1>Help Desk Ticket Practice using open-source osTicket</h1>
    <p>
        In order to gain more hands-on skills with creating and servicing IT Help Desk tickets, I have installed and configured osTicket - an open-source (Linux Ubuntu) Help Desk ticketing software. Here is a detailed write-up of my experience with setting up, configuring, and using osTicket.
    </p>
</body>
</html>

<h2>Step 1: Prepare the Server</h2>

<h3>Update the System:</h3>
<pre><code>sudo apt update && sudo apt upgrade -y</code></pre>

<h3>Install Apache, PHP, and MySQL:</h3>
<pre><code>sudo apt install apache2 mysql-server php libapache2-mod-php php-mysql -y</code></pre>

<h3>Install Required PHP Extensions:</h3>
<pre><code>sudo apt install php-mbstring php-intl php-xml php-imap php-gd php-json php-gettext php-apcu -y</code></pre>

<h3>Secure MySQL: Run the secure installation wizard:</h3>
<pre><code>sudo mysql_secure_installation</code></pre>

<h3>Create a Database for osTicket:</h3>
<p>Log in to MySQL:</p>
<pre><code>sudo mysql -u root -p</code></pre>

<h2>Download and Extract osTicket</h2>

<h3>Download osTicket:</h3>
<pre><code>wget https://github.com/osTicket/osTicket/releases/download/v1.17.2/osTicket-v1.17.2.zip</code></pre>
<pre><code>sudo apt install unzip -y</pre>

<p>Here are step-by-step instructions for post-installation configuration of osTicket to ensure your system is operational and optimized:</p>

<h2>1. Log in to the Admin Panel</h2>
<ul>
    <li>Open your browser and navigate to the osTicket URL (e.g., <code>http://yourdomain.com/scp</code>).</li>
    <li>Enter the admin credentials you set during installation.</li>
</ul>

<h2>2. Set Up System Preferences</h2>
<ul>
    <li>Navigate to: Admin Panel &gt; Settings &gt; System.</li>
    <li>Configure the following:
        <ul>
            <li><strong>Helpdesk Name:</strong> Enter your organization's name.</li>
            <li><strong>Default Email:</strong> Set the primary email address for outgoing notifications.</li>
            <li><strong>Helpdesk URL:</strong> Verify the base URL of your osTicket installation.</li>
            <li><strong>Timezone:</strong> Choose the correct timezone.</li>
        </ul>
    </li>
    <li>Click Save Changes.</li>
</ul>

<h2>3. Configure Email Settings</h2>
<h3>Set Up Email Sending:</h3>
<ul>
    <li>Navigate to: Admin Panel &gt; Emails &gt; Settings.</li>
    <li>Select an SMTP server for outgoing emails.</li>
    <li>Enter the SMTP details (hostname, port, username, and password).</li>
    <li>Test the connection to ensure emails are being sent.</li>
</ul>
<h3>Set Up Email Fetching:</h3>
<ul>
    <li>Go to Admin Panel &gt; Emails &gt; Emails and click Add New Email.</li>
    <li>Configure an email account for fetching tickets via IMAP/POP3.</li>
    <li>Ensure the email fetching process works by testing it.</li>
</ul>

<h2>4. Customize Ticket Settings</h2>
<ul>
    <li>Navigate to: Admin Panel &gt; Settings &gt; Tickets.</li>
    <li>Configure:
        <ul>
            <li><strong>Default Ticket Number Format:</strong> Set a unique format for ticket numbers.</li>
            <li><strong>Auto-Response Settings:</strong> Enable/disable auto-responses for new tickets and updates.</li>
            <li><strong>Agent Collision Avoidance:</strong> Specify if agents can work on the same ticket simultaneously.</li>
            <li><strong>Ticket Overdue Alerts:</strong> Configure alerts for overdue tickets.</li>
        </ul>
    </li>
    <li>Click Save Changes.</li>
</ul>

<h2>5. Create Help Topics</h2>
<ul>
    <li>Navigate to: Admin Panel &gt; Manage &gt; Help Topics.</li>
    <li>Add topics that categorize incoming tickets (e.g., "Technical Support," "Billing," "Sales").</li>
    <li>Click Add Topic for each help topic.</li>
</ul>

<h2>6. Add Departments</h2>
<ul>
    <li>Navigate to: Admin Panel &gt; Agents &gt; Departments.</li>
    <li>Create departments to assign tickets (e.g., IT Support, HR, Customer Service).</li>
    <li>Assign department-specific email addresses if applicable.</li>
    <li>Configure SLA settings for each department.</li>
</ul>

<h2>7. Configure SLAs (Service Level Agreements)</h2>
<ul>
    <li>Navigate to: Admin Panel &gt; Manage &gt; SLA Plans.</li>
    <li>Create SLA plans to define response and resolution times.</li>
    <li>Assign SLA plans to specific departments or help topics.</li>
</ul>

<h2>8. Set Up User and Agent Roles</h2>
<h3>Create User Groups:</h3>
<ul>
    <li>Go to Admin Panel &gt; Users &gt; User Directory.</li>
    <li>Add or configure user groups (e.g., Customers, Employees).</li>
</ul>
<h3>Add Agents:</h3>
<ul>
    <li>Go to Admin Panel &gt; Agents &gt; Agents.</li>
    <li>Click Add New Agent.</li>
    <li>Assign agents to specific departments.</li>
    <li>Define permissions and roles (e.g., Manager, Staff).</li>
</ul>

<h2>9. Customize Ticket Fields and Forms</h2>
<ul>
    <li>Navigate to: Admin Panel &gt; Manage &gt; Forms.</li>
    <li>Modify the default ticket submission form by adding/removing fields.</li>
    <li>Create custom forms for specific needs.</li>
</ul>

<h2>10. Install Plugins and Add-Ons</h2>
<ul>
    <li>Navigate to: Admin Panel &gt; Manage &gt; Plugins.</li>
    <li>Install necessary plugins (e.g., LDAP Authentication, OAuth2).</li>
    <li>Configure each plugin based on your requirements.</li>
</ul>

<h2>11. Test the System</h2>
<ul>
    <li>Create test tickets as a user and ensure they:
        <ul>
            <li>Generate notifications.</li>
            <li>Appear in the correct departments.</li>
            <li>Follow SLA rules.</li>
            <li>Assign tickets to agents and verify permissions.</li>
        </ul>
    </li>
</ul>

<h2>12. Secure the Installation</h2>
<ul>
    <li>Restrict access to the setup/ directory by deleting or renaming it.</li>
    <li>Ensure file permissions are secure (e.g., read-only for configuration files).</li>
    <li>Enable HTTPS for secure communication.</li>
    <li>Regularly back up the database and files.</li>
</ul>

<h2>13. Monitor and Optimize</h2>
<ul>
    <li>Use the Dashboard (Admin Panel &gt; Dashboard) to monitor ticket trends and agent performance.</li>
    <li>Adjust settings as your helpdesk evolves.</li>
</ul>

<p>This setup ensures a smooth post-installation configuration for osTicket, providing a reliable and organized ticketing system for your team.</p>

<p>Here are some ticket lifecycle examples for osTicket, demonstrating how a ticket moves through the system from creation to resolution and closure:</p>

<h2>Example 1: IT Support Request</h2>
<ol>
    <li><strong>Ticket Creation</strong>
        <ul>
            <li>A user submits a ticket via the customer portal or email with the subject: "Unable to Access VPN."</li>
            <li>osTicket assigns a unique ticket number (e.g., #12345) and sends an auto-response to the user confirming receipt.</li>
        </ul>
    </li>
    <li><strong>Ticket Assignment</strong>
        <ul>
            <li>The ticket is automatically assigned to the "IT Support" department based on the selected Help Topic ("VPN Issues").</li>
            <li>An agent in the IT Support team is assigned the ticket either manually or via auto-assignment rules.</li>
        </ul>
    </li>
    <li><strong>Ticket Processing</strong>
        <ul>
            <li>The agent reviews the ticket and asks the user for more information (e.g., "What error message do you see?").</li>
            <li>The user replies, and the ticket status updates to "Open" or "Active."</li>
        </ul>
    </li>
    <li><strong>Ticket Resolution</strong>
        <ul>
            <li>The agent identifies the issue as a configuration problem and guides the user through resetting their VPN credentials.</li>
            <li>The ticket status changes to "Resolved."</li>
        </ul>
    </li>
    <li><strong>Ticket Closure</strong>
        <ul>
            <li>After 48 hours with no further response from the user, the system automatically closes the ticket.</li>
            <li>The user receives a notification that the ticket is now closed.</li>
        </ul>
    </li>
</ol>

<h2>Example 2: Customer Service Inquiry</h2>
<ol>
    <li><strong>Ticket Creation</strong>
        <ul>
            <li>A customer sends an email asking about the refund process for a product.</li>
            <li>The email generates a ticket in osTicket with the Help Topic "Refund Inquiry."</li>
        </ul>
    </li>
    <li><strong>Ticket Assignment</strong>
        <ul>
            <li>The ticket is assigned to the "Billing and Refunds" department.</li>
            <li>The department manager assigns the ticket to an available agent.</li>
        </ul>
    </li>
    <li><strong>Ticket Processing</strong>
        <ul>
            <li>The agent reviews the request and provides details about the refund process and timeline.</li>
            <li>The agent updates the ticket with the refund approval and marks it as "Resolved."</li>
        </ul>
    </li>
    <li><strong>Ticket Follow-Up</strong>
        <ul>
            <li>The user replies with a thank-you note. The system reopens the ticket briefly to record the response, then closes it again.</li>
        </ul>
    </li>
</ol>

<h2>Example 3: Facility Maintenance Request</h2>
<ol>
    <li><strong>Ticket Creation</strong>
        <ul>
            <li>An employee submits a ticket through the web portal, reporting a broken air conditioner in the office.</li>
            <li>The ticket is categorized under the Help Topic "Facility Maintenance."</li>
        </ul>
    </li>
    <li><strong>Ticket Assignment</strong>
        <ul>
            <li>The ticket is routed to the "Facilities" department.</li>
            <li>An agent assigns the ticket to a specific maintenance technician.</li>
        </ul>
    </li>
    <li><strong>Ticket Processing</strong>
        <ul>
            <li>The technician inspects the issue and logs progress updates (e.g., "Part ordered for repair").</li>
            <li>The ticket is placed in "Pending" status until the part arrives.</li>
        </ul>
    </li>
    <li><strong>Ticket Resolution</strong>
        <ul>
            <li>The air conditioner is repaired, and the technician updates the ticket with the resolution details.</li>
            <li>The ticket is marked as "Resolved."</li>
        </ul>
    </li>
    <li><strong>Ticket Closure</strong>
        <ul>
            <li>The system automatically closes the ticket after three days of inactivity.</li>
        </ul>
    </li>
</ol>

<h2>Example 4: Software Bug Report</h2>
<ol>
    <li><strong>Ticket Creation</strong>
        <ul>
            <li>A user submits a bug report via the osTicket portal, describing an issue with the company's internal software.</li>
            <li>The Help Topic is "Software Bug."</li>
        </ul>
    </li>
    <li><strong>Ticket Assignment</strong>
        <ul>
            <li>The ticket is assigned to the "Development" department.</li>
            <li>The department manager assigns the ticket to a developer.</li>
        </ul>
    </li>
    <li><strong>Ticket Processing</strong>
        <ul>
            <li>The developer investigates the issue and reproduces the bug in a test environment.</li>
            <li>They update the ticket status to "Work in Progress" and log detailed notes.</li>
        </ul>
    </li>
    <li><strong>Ticket Resolution</strong>
        <ul>
            <li>The developer deploys a fix and asks the user to verify if the issue is resolved.</li>
            <li>The user confirms that the bug is fixed.</li>
        </ul>
    </li>
    <li><strong>Ticket Closure</strong>
        <ul>
            <li>The ticket is marked as "Resolved" and closed after a confirmation notification is sent to the user.</li>
        </ul>
    </li>
</ol>

<h2>Example 5: Priority Escalation</h2>
<ol>
    <li><strong>Ticket Creation</strong>
        <ul>
            <li>A customer reports a system outage, marking it as "Urgent."</li>
            <li>The ticket is flagged with high priority.</li>
        </ul>
    </li>
    <li><strong>Ticket Assignment</strong>
        <ul>
            <li>The ticket is assigned to the "IT Operations" department and automatically escalated to the team lead.</li>
        </ul>
    </li>
    <li><strong>Ticket Processing</strong>
        <ul>
            <li>The team lead assigns multiple agents to address the issue.</li>
            <li>Updates are logged in real time as the team works to restore the system.</li>
        </ul>
    </li>
    <li><strong>Ticket Resolution</strong>
        <ul>
            <li>Once the system is operational, the agents update the ticket and notify the customer.</li>
        </ul>
    </li>
    <li><strong>Post-Resolution Follow-Up</strong>
        <ul>
            <li>The ticket remains open for 24 hours to ensure no further issues occur.</li>
            <li>After 24 hours, the ticket is closed.</li>
        </ul>
    </li>
</ol>

<p>These examples demonstrate how osTicket manages different types of tickets, from straightforward inquiries to complex escalations. Each lifecycle is adaptable based on organizational needs and configured workflows.</p>
