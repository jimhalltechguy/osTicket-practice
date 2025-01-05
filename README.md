<hr>

<h2>Prerequisites and Installation Instructions for osTicket</h2>

<h3>Prerequisites</h3>
<p>Ensure the following prerequisites are met before installing osTicket:</p>
<ol>
    <li><strong>Server Requirements</strong>
        <ul>
            <li><strong>Operating System:</strong>
                <ul>
                    <li>Linux (recommended: Ubuntu, CentOS)</li>
                    <li>Windows (via WAMP/XAMPP)</li>
                </ul>
            </li>
            <li><strong>Web Server:</strong> Apache or Nginx</li>
            <li><strong>PHP Version:</strong> 7.4 - 8.1 (as of osTicket v1.17)</li>
            <li><strong>Database:</strong> MySQL 5.5 or later (or MariaDB equivalent)</li>
        </ul>
    </li>
    <li><strong>PHP Extensions</strong>
        <ul>
            <li>mysqli</li>
            <li>gd</li>
            <li>gettext</li>
            <li>imap</li>
            <li>mbstring</li>
            <li>xml</li>
            <li>intl</li>
            <li>fileinfo</li>
            <li>json</li>
            <li>phar</li>
            <li>apcu (optional but recommended for caching)</li>
        </ul>
    </li>
    <li><strong>Tools and Packages</strong>
        <ul>
            <li>SSH or terminal access (for server setup)</li>
            <li>FTP client (e.g., FileZilla) or SCP for file uploads</li>
            <li>Text editor (e.g., VSCode or Notepad++)</li>
            <li>A domain or subdomain with DNS configured to point to your server</li>
        </ul>
    </li>
    <li><strong>osTicket Installation Package</strong>
        <ul>
            <li>Download the latest osTicket package from the official osTicket website.</li>
        </ul>
    </li>
</ol>

<hr>

<h3>Installation Instructions</h3>

<h4>Step 1: Prepare the Server</h4>
<ol>
    <li><strong>Update the System:</strong>
        <pre><code>sudo apt update && sudo apt upgrade -y</code></pre>
    </li>
    <li><strong>Install Apache, PHP, and MySQL:</strong>
        <pre><code>sudo apt install apache2 mysql-server php libapache2-mod-php php-mysql -y</code></pre>
    </li>
    <li><strong>Install Required PHP Extensions:</strong>
        <pre><code>sudo apt install php-mbstring php-intl php-xml php-imap php-gd php-json php-gettext php-apcu -y</code></pre>
    </li>
    <li><strong>Secure MySQL:</strong> Run the secure installation wizard:
        <pre><code>sudo mysql_secure_installation</code></pre>
    </li>
    <li><strong>Create a Database for osTicket:</strong>
        <pre><code>
<h4>Step 2: Download and Extract osTicket</h4>
<ol>
    <li><strong>Download osTicket:</strong>
        <pre><code>wget https://github.com/osTicket/osTicket/releases/download/v1.17.2/osTicket-v1.17.2.zip</code></pre>
    </li>
    <li><strong>Extract the Package:</strong>
        <pre><code>sudo apt install unzip -y
<h4>Step 3: Configure File Permissions</h4>
<ol>
    <li><strong>Set Permissions:</strong>
        <pre><code>sudo chown -R www-data:www-data /var/www/html/osticket
<h4>Step 4: Configure Apache</h4>
<ol>
    <li><strong>Create a Virtual Host Configuration:</strong>
        <pre><code>
<h4>Step 5: Install osTicket</h4>
<ol>
    <li>Open your browser and navigate to:
        <pre><code>http://yourdomain.com</code></pre>
    </li>
    <li>Follow the on-screen installer and provide the database details created earlier.</li>
    <li>Delete or rename the <code>setup/</code> directory:
        <pre><code>sudo rm -rf /var/www/html/osticket/setup</code></pre>
    </li>
</ol>

<h4>Step 6: Secure the Installation</h4>
<ol>
    <li><strong>Enable HTTPS:</strong>
        <pre><code>


<hr>

<h2>Post-Installation Set-Up</h2>
<p>Here are step-by-step instructions for post-installation configuration of osTicket to ensure your system is operational and optimized:</p>
<ol>
    <li><strong>Log in to the Admin Panel:</strong>
        <ul>
            <li>Navigate to the osTicket URL (e.g., <code>http://yourdomain.com/scp</code>).</li>
            <li>Enter the admin credentials you set during installation.</li>
        </ul>
    </li>
    <li><strong>Set Up System Preferences:</strong>
        <ul>
            <li>Navigate to: Admin Panel > Settings > System.</li>
            <li>Configure helpdesk details, default email, and timezone.</li>
        </ul>
    </li>
    <li><strong>Configure Email Settings:</strong>
        <ul>
            <li>Set up SMTP and IMAP/POP3 for email sending and fetching.</li>
        </ul>
    </li>
    <li><strong>Customize Ticket Settings:</strong>
        <ul>
            <li>Adjust ticket numbering, auto-responses, and SLA settings.</li>
        </ul>
    </li>
</ol>

<hr>

<h2>Ticket Lifecycle Examples</h2>
<p>Here are examples of ticket lifecycles in osTicket, demonstrating how a ticket moves from creation to resolution:</p>
<ol>
    <li><strong>IT Support Request:</strong> A user submits a ticket for a VPN issue, assigned to IT Support, resolved, and automatically closed after inactivity.</li>
    <li><strong>Customer Service Inquiry:</strong> A customer sends a refund inquiry, assigned to Billing, resolved, and followed up with a confirmation.</li>
    <li><strong>Facility Maintenance Request:</strong> An employee reports a broken air conditioner, routed to Facilities, resolved, and closed after completion.</li>
    <li><strong>Software Bug Report:</strong> A user reports a bug, assigned to Development, resolved by deploying a fix, and verified before closure.</li>
    <li><strong>Priority Escalation:</strong> A system outage ticket marked urgent, escalated to IT Operations, resolved collaboratively, and monitored post-resolution.</li>
</ol>

<p>This detailed guide ensures a comprehensive understanding of setting up, configuring, and using osTicket for effective help desk ticket management.</p>
